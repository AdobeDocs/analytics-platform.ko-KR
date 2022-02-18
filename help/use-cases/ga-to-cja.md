---
title: Google Analytics 데이터를 Adobe Experience Platform으로 수집
description: 'CJA(Customer Journey Analytics)를 사용하여 Google Analytics 데이터를 Adobe Experience Platform에 수집하는 방법을 설명합니다. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '1178'
ht-degree: 100%

---


# Google Analytics 데이터를 Adobe Experience Platform으로 수집

이 활용 사례는 데이터 세트로서의 Google Analytics 데이터를 Adobe Experience Platform에 수집하는 방법을 중점적으로 다룹니다. 여기에서는 내역 데이터와 라이브 데이터를 모두 수집하는 방법에 대해 설명합니다. 이 과정이 완료되고 나면 Customer Journey Analytics에서 두 데이터 세트를 결합하여 사용자의 여정을 여러 디바이스 간에 한눈에 볼 수 있습니다.

Experience Platform의 데이터 세트는 두 가지 요소인 스키마 그리고 데이터 세트의 실제 기록으로 구성됩니다. 스키마(줄여서 Experience Data Model 또는 XDM으로 부름)는 데이터 세트의 열과 같으며 데이터 자체를 설명하는 블루프린트 또는 규칙과도 같습니다. 플랫폼 내에서 Adobe는 두 가지 유형의 스키마를 제공합니다.

* Google Analytics 데이터를 자동으로 매핑할 수 있는 기본 스키마(Experience Event 스키마라고 함)
* Google Analytics 데이터를 만들고 쉽게 매핑할 수 있는 사용자 정의 스키마

Adobe의 데이터 모델이 갖는 가장 강력한 측면 중 하나는 모든 고객 상호 작용 데이터를 하나의 공통 스키마로 표준화할 수 있다는 것입니다. 이를 통해 데이터를 CJA에 결합하는 일은 훨씬 더 쉬워집니다.

## 전제 조건

이러한 작업을 달성하려면 다음의 액세스 및 권한이 필요합니다.

* Adobe Experience Platform에 액세스
* 범용 Google Analytics(Google Analytics 360 버전) 또는 Google Analytics 4(무료 버전 또는 Google Analytics 360 버전)에 액세스
* Customer Journey Analytics에 액세스 및 그 [관리자 권한](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ko-KR#admin-access-permissions)

Google Analytics 데이터를 Adobe Experience Platform으로 가져오는 방법은 사용 중인 Google Analytics의 버전에 따라 다릅니다.

| 다음 항목을 사용하는 경우 | 필요한 라이선스... | 이 작업 수행... |
| --- | --- | --- |
| **범용 Analytics** | Google Analytics 360 | 아래 지침 중 1~3단계 수행 |
| **Google Analytics 4** | 무료 GA 버전 또는 Google Analytics 360 | 아래 지침 중 1 및 3단계를 수행합니다. 2단게는 수행할 필요가 없습니다. |

## 내역(채우기) 데이터 수집

### 1. Google Analytics 데이터를 BigQuery에 연결

자세한 정보는 [이 지침](https://support.google.com/analytics/answer/3416092?hl=ko)을 참조하십시오. 참고로 이 지침들은 범용 Google Analytics를 기반으로 합니다.

### 2. Google Analytics 세션을 BigQuery의 이벤트로 변환하고 Google Cloud Storage로 내보내기

>[!IMPORTANT]
>
>이 단계는 범용 Analytics 고객에만 해당

GA 데이터는 각 기록을 그 데이터 안에 개별 이벤트가 아닌 사용자 세션으로서 보관합니다. 범용 Analytics 데이터를 Experience Platform 호환 포맷으로 변환하려면 SQL 쿼리를 만들어야 합니다. GA 스키마에서 &quot;unnest&quot; 함수를 &quot;히트&quot; 필드에 적용합니다. 다음의 SQL 예를 사용할 수 있습니다.

```
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `your_bq_table_2021_04_*`,
         UNNEST(hits) AS hit 
   )
```

쿼리가 완료되면 BigQuery 테이블에 완료 결과를 저장합니다.

[이 지침](https://support.google.com/analytics/answer/7029846?hl=ko&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)을 참조하십시오. 여기에 SQL 쿼리 관련 지침도 포함되어 있습니다.

다음의 비디오는 그 다음 단계인 Google Analytics 이벤트를 JSON 포맷으로 Google Cloud Storage에 내보내는 방법에 대해서도 설명합니다. 간단하게 **내보내기 > GCS로 내보내기**&#x200B;를 클릭하면 됩니다. 내보내기가 완료되면 데이터가 Adobe Experience Platform으로 옮겨질 수 있게 준비됩니다.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Google Cloud Storage에서 Experience Platform으로 데이터 가져오기 및 XDM 스키마에 매핑

Experience Platform에서 **[!UICONTROL 소스]**&#x200B;를 선택하고 **[!UICONTROL Google Cloud Storage]** 옵션을 찾습니다. 간단하게 여기에서, BigQuery로부터 저장한 데이터 세트를 찾으면 됩니다.

다음 사항에 주의하십시오.

* JSON 포맷을 선택해야 합니다.
* 기존 데이터 세트를 선택하거나, 새 데이터 세트를 만들 수 있습니다(권장).
* 내역 Google Analytics 데이터와 라이브 스트리밍 Google Analytics 데이터가 개별 데이터 세트를 가지고 있는 경우에도 두 데이터에 동일한 스키마를 선택해야 합니다. 이후 여러 데이터 세트를 하나의 [CJA 연결](/help/connections/combined-dataset.md)에 병합할 수 있습니다.

이 비디오의 지침을 참조하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

선택한 XDM 스키마를 사용하여, 이전에 생성한 기존의 데이터 세트에 GA 이벤트 데이터를 매핑하거나 새 데이터 세트를 만들 수 있습니다. 스키마를 선택하면 Experience Platform이 머신 러닝을 적용해 Google Analytics 데이터의 각 필드를 해당 [XDM 스키마](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko-KR#ui)에 자동으로 사전 매핑합니다.

![](assets/schema-map.png)

매핑은 변경하기가 매우 쉬우며 심지어 Google Analytics 데이터에서 파생된 또는 계산된 필드를 생성할 수 있습니다. XM 스키마로의 필드 매핑을 완료한 뒤에는 이 가져오기를 반복해서 예약할 수 있을 뿐 아니라 수집 프로세스 중 오류 유효성 검사를 적용할 수도 있습니다. 이 기능은 가져온 데이터에 아무 문제도 없음을 보장해 줍니다.

**&#39;타임스탬프&#39; 계산된 필드**

Google Analytics 데이터의 `timestamp` 스키마 필드의 경우, Experience Platform 스키마 UI에서 특별한 계산된 필드를 만들어야 합니다. **[!UICONTROL 계산된 필드 추가]**&#x200B;를 클릭하고 `date` 함수에서 `timestamp` 문자열을 다음과 같이 래핑합니다.

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

그 후 이 계산된 필드를 스키마의 타임스탬프 데이터 구조에 저장해야 합니다.

![](assets/timestamp.png)

**&#39;_id&#39; 계산된 필드**

`_id` 스키마 필드는 그 안에 값을 포함해야 합니다. CJA는 그 값이 무엇이든 상관하지 않습니다. 이 필드에 간단하게 &quot;1&quot;을 추가할 수 있습니다.

![](assets/_id.png)

## 라이브 스트리밍 Google Analytics 데이터 수집

Google Tag Manager에서 Adobe Experience Platform으로 바로 라이브 스트리밍 이벤트를 캡처할 수도 있습니다.

### 1. 사용자 정의 변수 추가

Google Tag Manager 계정에 로그인한 후에 Adobe와 관련된 일부 사용자 정의 상수 변수를 추가해야 합니다. 아마도 고객 이메일, 고객 이름, 언어, 고객 로그인 상태 등 Google Analytics로 전달되는 변수가 Google Tag Manager에 이미 있을 것입니다. 이외에 5개의 새로운 사용자 정의 변수를 정의해야 합니다.

* Adobe Experience Cloud org ID
* DCS 스트리밍 끝점
* Experience Platform 데이터 세트 ID
* 스키마 참조
* 페이지 타임스탬프

이러한 값을 가져오면 모든 Google Analytics 데이터 획득이 올바른 데이터 세트로 전달되고 알맞은 스키마를 갖게 됩니다. Experience Cloud Org 또는 그 외에 방금 언급한 다른 변수 중 어느 것이든 잘 모르는 경우 Adobe 계정 관리자가 추적을 도와줄 수 있습니다.

이 사용자 정의 변수들을 정의한 뒤에는 이미 Google Analytics로 전달하고 있는 모든 데이터를 Experience Platform에도 전송하는 트리거를 설정할 수 있습니다.

### 2. Google Tag Manager에서 트리거 설정

이 예에서는 &quot;계정 만들기&quot; 트리거(`pageUrl equals account-creation`)가 정의되었습니다. 이 트리거에 몇 가지 정보를 추가하면, 사용자의 인증이 성공적으로 이루어지고 및 계정 만들기 페이지가 로드될 때 Google Analytics 및 AEP 모두에 데이터가 전달되게 할 수 있습니다.

[데이터 수집 및 Google Tag Manager](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=ko-KR#module9)의 내용도 참조하십시오.

이 비디오의 지침을 참조하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## CJA에서 Google Analytics 데이터 세트에 대한 연결 만들기

Adobe Experience Platform이 라이브 Google Analytics 데이터를 수신하기 시작하고 BigQuery로부터 내역 Google Analytics 데이터를 채웠다면 CJA로 바로 이동하여 [첫 번째 연결을 만들 수 있습니다](/help/connections/create-connection.md). 이 연결은 일반적인 &quot;고객 ID&quot;를 사용하여 GA 데이터를 다른 모든 고객 데이터와 결합합니다.

## 다음 단계

* Google Analytics 데이터가 포함된 연결을 기반으로 [데이터 보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ko-KR#cja-dataviews)를 만듭니다.

* Workspace](/help/use-cases/ga-to-cja-reporting.md)에서 놀라운 [분석을 수행합니다.