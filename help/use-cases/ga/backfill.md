---
title: Google Analytics 내역 데이터를 Adobe Experience Platform에 수집
description: CJA(Customer Journey Analytics)을 사용하여 Google Analytics 데이터를 Adobe Experience Platform으로 수집하는 방법을 설명합니다.
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: f65f13d696ad2045f58ccb5c9ef7fed45eb9d68c
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 9%

---


# Google Analytics 내역 데이터를 Adobe Experience Platform에 수집

이 페이지에서는 Google Analytics 기록 데이터를 Customer Journey Analytics 내의 데이터 보기에서 해당 데이터 세트를 참조할 수 있도록 Adobe Experience Platform에 데이터 세트로 수집하는 방법에 중점을 둡니다. 이 페이지의 단계를 [라이브 Google Analytics 구현 구성](streaming.md)에서 반복되는 데이터 세트를 생성합니다. 이 기록 데이터 세트를 현재 구현의 데이터 세트와 결합하여 Customer Journey Analytics의 데이터를 현재 데이터와 채워진 데이터와 함께 원활하게 볼 수 있습니다.

## 사전 요구 사항

이러한 작업을 달성하려면 다음의 액세스 및 권한이 필요합니다.

* Adobe Experience Platform에 액세스
* Google Analytics 액세스(GA Standard 또는 GA 360)
* [관리자 액세스](/help/getting-started/cja-access-control.md) Customer Journey Analytics

## BigQuery 내보내기 설정

Universal Analytics 속성의 데이터 구조가 Google Analytics 4 속성의 데이터 구조와 다릅니다. 데이터를 내보낼 속성 유형을 기준으로 BigQuery 내보내기를 설정합니다.

* [범용 Analytics 속성에 대한 BigQuery 내보내기 설정](https://support.google.com/analytics/answer/3416092)
* [Google Analytics 4 속성에 대해 BigQuery 내보내기 설정](https://support.google.com/analytics/answer/9823238)

### 범용 Analytics 속성에 대한 추가 요구 사항

>[!NOTE]
>
>이 섹션은 Universal Analytics 속성에만 적용됩니다. GA4 속성에서 내보내는 경우, [Google Cloud Platform으로 데이터 내보내기](#export-gcp).

범용 Analytics 속성은 각 레코드를 개별 이벤트 대신 사용자의 세션으로 저장합니다. Universal Analytics 데이터를 Adobe Experience Platform과 호환되는 형식으로 변환하는 SQL 쿼리가 필요합니다. 적용 `UNNEST` 함수에 대한 `hits` GA 스키마의 필드를 만든 후 BigQuery 표로 저장합니다.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

```sql
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
         `example_bq_table_*`,
         UNNEST(hits) AS hit 
   )
```

## Google Cloud Platform으로 데이터 내보내기 {#export-gcp}

Google Cloud Platform에서 **내보내기 > GCS로 내보내기**. Google 클라우드 스토리지에 데이터가 있으면 Adobe Experience Platform으로 가져올 준비가 된 것입니다.

## Google 클라우드 스토리지의 데이터를 Experience Platform으로 가져옵니다

1. Adobe Experience Platform에서 **[!UICONTROL 소스]** 왼쪽에 있습니다.
1. 카탈로그에서 **[!UICONTROL Google 클라우드 스토리지]** 선택 사항입니다. 클릭 **[!UICONTROL 데이터 추가]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>내역 및 라이브 스트리밍 Google Analytics 데이터를 모두 가져오려면 두 데이터 세트에 대해 동일한 스키마를 사용해야 합니다. CJA에서 [결합된 데이터 세트](/help/connections/combined-dataset.md).

GA 이벤트 데이터를 이전에 만든 기존 데이터 세트에 매핑하거나 선택한 XDM 스키마를 사용하여 데이터 세트를 만들 수 있습니다. 스키마를 선택하면 Experience Platform이 머신 러닝을 적용해 Google Analytics 데이터의 각 필드를 해당 [XDM 스키마](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html#ui)에 자동으로 사전 매핑합니다.

![스키마 맵](../assets/schema-map.png)

필드를 XDM 스키마에 매핑하는 작업이 끝나면 되풀이하여 이 가져오기를 예약하고 수집 프로세스 중에 오류 유효성 검사를 적용할 수 있습니다. 이 유효성 검사에서는 가져온 데이터에 문제가 없습니다.

## 필수 XDM 필드

Platform의 특정 XDM 필드에 데이터를 올바르게 처리하려면 올바른 형식이 필요합니다.

* **`timestamp`**: Experience Platform 스키마 UI에서 특별한 계산된 필드를 만듭니다. 클릭 **[!UICONTROL 계산된 필드 추가]** 그리고 `timestamp` 문자열의 `date` 함수:

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   계산된 필드를 스키마의 타임스탬프 데이터 구조에 저장합니다.

   ![타임스탬프](../assets/timestamp.png)

* **`_id`**: 이 필드에는 값이 있어야 합니다. CJA는 값이 무엇인지에 관심이 없습니다. 필드에 &quot;1&quot;을 추가할 수 있습니다.

   ![ID](../assets/_id.png)

## 다음 단계

* Adobe Experience Platform으로 스트리밍할 현재 데이터가 있는 경우 를 참조하십시오 [Google Analytics 데이터에 대한 스트리밍 설정](streaming.md).
* 채워진 데이터에 대한 보고를 시작하려면 다음을 참조하십시오 [연결 만들기](/help/connections/create-connection.md).
