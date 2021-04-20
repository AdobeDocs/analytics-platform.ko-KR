---
title: Adobe Experience Platform에 Google Analytics 데이터 인제스트
description: 'Customer Journey Analytics(CJA)를 사용하여 Google Analytics 및 firebase 데이터를 Adobe Experience Platform에 인제스트하는 방법에 대해 설명합니다. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: de822eb00a5e205889b4fa96f729845ad4c7e356
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 7%

---


# Adobe Experience Platform에 Google Analytics 데이터 인제스트

이 사용 사례에서는 Google Analytics 데이터를 데이터 집합으로 Adobe Experience Platform에 인제스트하는 방법에 중점을 둡니다. 내역 데이터와 라이브 데이터를 모두 수집하는 방법에 대해 설명합니다. 한 번 작업을 수행하면 Customer Journey Analytics에 두 데이터 세트를 결합하여 사용자 여정의 크로스 디바이스 보기를 수행할 수 있습니다.

Experience Platform의 데이터 세트는 다음 두 가지 항목으로 구성됩니다.스키마 및 데이터 세트에 있는 실제 레코드. 스키마(이것을 경험 데이터 모델 또는 XDM이라고 함)는 데이터 세트 열과 비슷하며 데이터 자체를 설명하는 블루프린트 또는 규칙과 같습니다. 플랫폼 내에서 Adobe은 다음 2가지 유형의 스키마를 제공합니다.

* Google Analytics 데이터를 자동으로 매핑할 수 있는 기본 스키마(경험 이벤트 스키마라고 함)
* Google Analytics 데이터를 만들고 쉽게 매핑할 수 있는 사용자 정의 스키마

Adobe 데이터 모델의 가장 강력한 측면 중 하나는 모든 고객 상호 작용 데이터를 하나의 공통 스키마로 표준화할 수 있다는 것입니다. 이를 통해 CJA에서 데이터를 결합하는 것이 훨씬 수월해졌습니다.

## 전제 조건

이러한 작업을 수행하려면 다음 액세스 및 권한이 필요합니다.

* Adobe Experience Platform에 액세스
* 범용 Google Analytics(Google Analytics 360 버전) 또는 Google Analytics 4(무료 버전 또는 Google Analytics 360 버전)에 액세스
* Customer Journey Analytics에 액세스 및 [관리 권한](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ko-KR#admin-access-permissions)을(를) 참조하십시오.

Google Analytics 데이터를 Adobe Experience Platform으로 가져오는 방법은 사용 중인 Google Analytics의 버전에 따라 다릅니다.

| 다음 항목을 사용하는 경우 | 필요한 라이선스... | 이 작업 수행... |
| --- | --- | --- |
| **범용 분석** | Google Analytics 360 | 아래 지침의 1-3단계를 수행합니다. |
| **Google Analytics 4** | 무료 GA 버전 또는 Google Analytics 360 | 아래 지침 1단계와 3단계를 수행합니다. 2단계를 수행하지 않아도 됩니다. |

## 내역(채우기) 데이터 인제스트

### 1. Google Analytics 데이터를 BigQuery에 연결

자세한 내용은 [다음 지침](https://support.google.com/analytics/answer/3416092?hl=en)을 참조하십시오. 이러한 지침은 범용 Google Analytics을 기반으로 합니다.

### 2. Google Analytics 세션을 BigQuery의 이벤트로 변환하고 Google 클라우드 스토리지로 내보냅니다.

>[!IMPORTANT]
>
>이 단계는 Universal Analytics 고객에게만 적용됩니다

GA 데이터는 개별 이벤트가 아닌 사용자의 세션으로 데이터의 각 레코드를 저장합니다. 유니버설 분석 데이터를 경험 플랫폼 호환 형식으로 변환하려면 SQL 쿼리를 만들어야 합니다. GA 스키마의 &quot;hits&quot; 필드에 &quot;unnest&quot; 함수를 적용합니다. 다음은 사용할 수 있는 SQL 예입니다.

`SELECT
*,
timestamp_seconds(`` + hit.time) AS `` 
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
`visitStartTimestampyour_bq_table_2021_04_*`,
UNNEST(hits) AS hit 
)`

쿼리가 완료되면 전체 결과를 BigQuery 테이블에 저장합니다.

SQL 쿼리에 대한 지침을 포함하는 [이 지침](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)을 참조하십시오.

다음 비디오에서는 Google Analytics 이벤트를 JSON 형식으로 Google 클라우드 스토리지로 내보내는 다음 단계도 설명합니다. **내보내기 > GCS로 내보내기**&#x200B;를 클릭하면 됩니다. 데이터가 제공되면 Adobe Experience Platform으로 가져올 수 있습니다.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Google 클라우드 스토리지의 데이터를 Experience Platform으로 가져오고 XDM 스키마에 매핑합니다.

Experience Platform에서 **[!UICONTROL 소스]**&#x200B;를 선택하고 **[!UICONTROL Google 클라우드 스토리지]** 옵션을 찾습니다. 여기에서 BigQuery에서 저장한 데이터 세트를 찾을 수 있습니다.

다음 사항에 주의하십시오.

* JSON 형식을 선택해야 합니다.
* 기존 데이터 집합을 선택하거나 새 데이터 집합을 만들 수 있습니다(권장).
* 개별 데이터 세트에 있더라도 내역 Google Analytics 데이터와 라이브 스트리밍 Google Analytics 데이터에 대해 동일한 스키마를 선택해야 합니다. 나중에 [CJA 연결](/help/connections/combined-dataset.md)의 데이터 집합을 병합할 수 있습니다.

지침은 다음 비디오를 보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

GA 이벤트 데이터를 이전에 만든 기존 데이터 세트에 매핑하거나, 선택하는 XDM 스키마를 사용하여 새 데이터 세트를 만들 수 있습니다. 스키마를 선택하면 Experience Platform은 시스템 학습을 적용하여 Google Analytics 데이터의 각 필드를 [XDM 스키마](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en#ui)에 자동으로 미리 매핑합니다.

![](assets/schema-map.png)

매핑은 쉽게 변경할 수 있으며 Google Analytics 데이터에서 파생되거나 계산된 필드를 만들 수도 있습니다. 필드를 XDM 스키마로 매핑한 후에 이 가져오기를 반복 예약하고 수집 프로세스 중에 오류 유효성 검사를 적용할 수 있습니다. 이렇게 하면 가져온 데이터에 아무런 문제가 없습니다.

**&#39;타임스탬프&#39; 계산 필드**

Google Analytics 데이터의 `timestamp` 스키마 필드의 경우 Experience Platform 스키마 UI에 특수 계산 필드를 만들어야 합니다. **[!UICONTROL 계산된 필드 추가]**&#x200B;를 클릭하고 `date` 함수에서 `timestamp` 문자열을 다음과 같이 래핑합니다.

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

그런 다음 이 계산된 필드를 스키마의 타임스탬프 데이터 구조에 저장해야 합니다.

![](assets/timestamp.png)

**&#39;_id&#39; 계산 필드**

`_id` 스키마 필드에 값이 있어야 합니다. CJA는 값이 무엇인지는 중요하지 않습니다. 필드에 &quot;1&quot;을 추가할 수 있습니다.

![](assets/_id.png)

## 실시간 스트리밍 Google Analytics 데이터 인제스트

또한 Google 태그 관리자에서 Adobe Experience Platform으로 바로 실시간 스트리밍 이벤트를 캡처할 수도 있습니다.

### 1. 사용자 지정 변수 추가

Google 태그 관리자 계정에 로그인한 후에는 Adobe과 관련된 일부 사용자 지정 상수 변수를 추가해야 합니다. 고객 이메일, 고객 이름, 언어 및 고객 로그인 상태와 같이 Google Analytics로 전송되는 Google 태그 관리자에 이미 변수가 있을 수 있습니다. 5개의 새 사용자 지정 변수를 정의해야 합니다.

* Adobe Experience Cloud 조직 ID
* DCS 스트리밍 끝점
* Experience Platform 데이터 집합 ID
* 스키마 참조
* 페이지 타임스탬프

이러한 값을 가져오면 모든 Google Analytics 데이터가 올바른 데이터 세트로 전송되고 올바른 스키마가 있습니다. Experience Cloud 조직 또는 방금 언급했던 다른 변수를 모르는 경우 Adobe 계정 관리자가 이를 추적하는 데 도움이 됩니다.

이러한 사용자 지정 변수를 정의하면 이미 Google Analytics으로 보내는 모든 데이터를 Experience Platform에 전송하도록 트리거를 설정할 수 있습니다.

### 2. Google 태그 관리자에서 트리거 설정

이 예에서 &quot;계정 생성&quot; 트리거가 정의되었으며 여기서 `pageUrl equals account-creation`. 이 트리거에 일부 정보를 추가하면 사용자가 인증되고 계정 만들기 페이지가 로드되면 Google Analytics 및 AEP 모두에 데이터가 전송되도록 할 수 있습니다.

[데이터 통합 및 Google 태그 관리자](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=en#module9)를 참조할 수도 있습니다.

지침은 다음 비디오를 보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## CJA에서 Google Analytics 데이터 세트에 대한 연결 만들기

Adobe Experience Platform이 라이브 Google Analytics 데이터를 받기 시작하고 BigQuery에서 내역 Google Analytics 데이터를 채우면 CJA로 바로 이동할 준비가 되며 [첫 번째 연결](/help/connections/create-connection.md)을 만들 수 있습니다. 이 연결을 통해 GA 데이터가 공통 &quot;고객 ID&quot;를 사용하여 다른 모든 고객 데이터와 통합됩니다.

## 다음 단계

* Google Analytics 데이터를 기반으로 데이터 보기 만들기
그런 다음 Google Analytics 데이터가 포함된 연결을 기준으로 [CJA에서 데이터 보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#cja-dataviews)를 만듭니다.

* [작업 공간](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/home.html?lang=en#cja-workspace)에서 놀라운 분석을 수행합니다. 일부 보고 사용 사례는 나중에 다시 확인하십시오.