---
title: Analytics Source 커넥터 데이터와 Adobe Analytics 비교
description: Adobe Analytics 및 Customer Journey Analytics에서 유사한 보고서를 볼 때 데이터의 차이점을 이해합니다.
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: 쿼리 서비스;쿼리 서비스;SQL 구문
source-git-commit: d96404479aabe6020566e693245879b5ad4fad9c
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 4%

---

# Analytics Source 커넥터 데이터와 Adobe Analytics 비교

조직에서 Customer Journey Analytics을 채택함에 따라 Adobe Analytics과 Customer Journey Analytics 간의 데이터에 몇 가지 차이가 있음을 알 수 있습니다. 이러한 차이는 정상이며 여러 가지 이유로 발생할 수 있습니다. Customer Journey Analytics은 Adobe Analytics에서 데이터에 대한 몇 가지 제한 사항을 개선할 수 있도록 설계되었습니다. 이러한 유연성으로 인해 Customer Journey Analytics에서 데이터를 해석하는 방식에 약간의 차이가 발생할 수 있습니다. 이 문서를 사용하여 Customer Journey Analytics 및 Adobe Analytics에서 데이터를 처리하는 방식의 잠재적 차이점을 이해합니다.

이 페이지에서는 사용자가 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko)를 사용하여 Adobe Analytics 데이터를 Adobe Experience Platform으로 수집한 다음 Customer Journey Analytics에서 [연결](/help/connections/overview.md) 및 [데이터 보기](/help/data-views/data-views.md)를 만들었다고 가정합니다.

![The data flow from Adobe Analytics through the data connector to Adobe Experience Platform and to Custoer Journey Analytics using CJA connections.](assets/compare.png)

보고 플랫폼마다 데이터가 다를 수 있는 가능한 이유는 다음과 같습니다.

* **다른 데이터 세트 또는 보고서 세트**: Adobe Analytics의 보고서 세트와 Source 커넥터가 데이터를 가져오는 보고서 세트가 동일한지 확인하십시오.
* **일정 설정**: Adobe Analytics의 보고서 세트에는 표준 시간대와 구성할 수 있는 다른 일정 설정이 포함되어 있습니다. 마찬가지로 Customer Journey Analytics의 데이터 보기에는 제어할 수 있는 별도의 설정이 있습니다. 패리티를 원하는 경우 이러한 설정이 제품 간에 일치하는지 확인하십시오.
* **추가 데이터 세트**: Customer Journey Analytics에서는 단일 연결 내에 여러 데이터 세트를 포함하는 기능을 제공합니다. 이러한 차이점에는 추가 이벤트 데이터 세트, 프로필 데이터 세트 또는 조회 데이터 세트가 포함됩니다. 이 기능은 Adobe Analytics과 Customer Journey Analytics의 주요 차별화 요소이므로 insight은 크로스 채널 데이터를 사용할 수 있습니다.
* **결합된 데이터 세트**: Adobe에서는 두 데이터 세트 간에 개인 ID를 분석하여 결합된 ID가 포함된 새 데이터 세트를 만듭니다. 이러한 [결합된 데이터 세트](/help/stitching/overview.md)에는 Adobe Analytics 보고서 세트에서 제공하는 것 이상의 추가 데이터가 포함되어 있습니다.
* **데이터 원본**: Customer Journey Analytics에는 요약 데이터 원본 또는 트랜잭션 ID 데이터 원본을 포함하여 Adobe Analytics 보고서 세트에 업로드된 [데이터 원본](https://experienceleague.adobe.com/ko/docs/analytics/import/data-sources/overview) 형식이 포함되어 있지 않습니다.
* **Dimension 및 지표 설정**: 데이터 보기 내에서 모든 차원과 지표는 조직에서 변경할 수 있는 자체 설정을 포함합니다. 이러한 변경 사항은 보고서 실행 시 적용되므로 소급하여 적용됩니다. Adobe Analytics의 Dimension 및 지표 설정은 데이터 수집 방법을 변경하므로 해당 변경 사항이 해당 시점부터 적용됩니다. 두 제품 중 하나에서 구성 요소 설정을 변경한 경우 보고 차이를 만들 수 있습니다. 특정 차원에 중점을 두는 경우 속성 및 지속성 설정이 Adobe Analytics과 Customer Journey Analytics 간에 일치하는지 확인하십시오.

  >[!TIP]
  >
  >Adobe에서는 Adobe Analytics의 차원에 &#39;[!UICONTROL 가장 최근(마지막)]&#39; 할당을 사용할 것을 강력히 권장합니다. 이 할당 설정을 사용하면 Customer Journey Analytics에서 보다 많은 속성 유연성을 사용할 수 있습니다.

* **방문 정의**: 데이터 보기 자체에는 개별 차원 및 지표 설정 외에도 방문자 데이터의 해석 방법을 근본적으로 변경하는 설정이 포함되어 있습니다. 예를 들어, Adobe Analytics의 [가상 보고서 세트](https://experienceleague.adobe.com/ko/docs/analytics/components/virtual-report-suites/vrs-about)와 유사한 세그먼트를 전체 데이터 보기에 적용할 수 있습니다. 방문 기간의 정의를 변경하거나 원하는 이벤트에서 새 방문을 자동으로 시작할 수도 있습니다. 이러한 설정은 Customer Journey Analytics과 Adobe Analytics 간의 보고 차이에 주목할 만한 영향을 줄 수 있습니다.

## 제품 간 레코드 수 확인

위의 모든 설정이 유사하게 표시되고 제품 간 레코드 수를 최소한 확인하려는 경우 다음 단계를 사용할 수 있습니다.

1. Adobe Experience Platform [쿼리 서비스](https://experienceleague.adobe.com/ko/docs/experience-platform/query/home)에서 다음 타임스탬프별 총 레코드 쿼리를 실행합니다.

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. Adobe Analytics [데이터 피드](https://experienceleague.adobe.com/ko/docs/analytics/export/analytics-data-feed/data-feed-overview)에서 원하는 날짜 범위에 대한 피드 파일을 생성합니다. 각 파일 내의 행 수를 계산하여 다음 행을 식별하고 제외합니다.

   * `exclude_hit`이(가) `0`이(가) 아닙니다(두 제품의 Analysis Workspace에서 제외된 데이터).
   * `hit_source`은(는) `0`, `3`, `5`, `7`, `8`, `9` 또는 `10`(데이터 원본 및 기타 히트 아님 데이터)입니다.
   * `page_event`은(는) `53` 또는 `63`입니다(스트리밍 미디어 keep-alive 히트).

   위의 기준과 일치하는 행은 Analytics Source 커넥터 수집 워크플로우에서 제외되므로 데이터 피드 행을 계산할 때도 제외되어야 합니다.

1. Query Services의 총 레코드는 동일한 기간 동안 데이터 피드의 행 수와 일치해야 합니다.
