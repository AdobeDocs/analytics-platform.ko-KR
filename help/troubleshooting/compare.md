---
title: Adobe Analytics 데이터와 비교
description: Adobe Analytics 데이터를 Customer Journey Analytics의 데이터와 비교하는 방법 알아보기
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: 쿼리 서비스;쿼리 서비스;SQL 구문
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: ht
source-wordcount: '831'
ht-degree: 100%

---

# Adobe Analytics 데이터와 비교

조직에서 Customer Journey Analytics를 채택함에 따라 Adobe Analytics와 Customer Journey Analytics 간의 데이터 차이가 있을 수 있습니다. 이는 정상이며 여러 가지 이유로 발생할 수 있습니다. Customer Journey Analytics는 AA에서의 데이터에 대한 몇 가지 제한 사항을 개선할 수 있도록 설계되었습니다. 그러나 예기치 않거나 의도하지 않은 불일치가 발생할 수 있습니다. 이 문서는 귀하와 귀하의 팀이 데이터 무결성에 대한 우려로 방해받지 않고 Customer Journey Analytics를 사용할 수 있도록 이러한 차이점을 진단하고 해결하는 데 도움이 되도록 설계되었습니다.

[Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko)를 통해 Adobe Analytics 데이터를 Adobe Experience Platform에 수집한 다음 이 데이터 세트를 사용하여 Customer Journey Analytics 연결을 생성했다고 가정해 보겠습니다.

![The data flow from Adobe Analytics through the data connector to Adobe Experience Platform and to Custoer Journey Analytics using CJA connections.](assets/compare.png)

그런 다음 데이터 보기를 생성하고 Customer Journey Analytics에서 이 데이터를 보고하는 동안 Adobe Analytics의 보고 결과와 불일치하는 것을 발견합니다.

다음은 원래 Adobe Analytics 데이터와 현재 Customer Journey Analytics의 Adobe Analytics 데이터를 비교하기 위해 따라야 할 몇 가지 단계입니다.

## 사전 요구 사항

* Adobe Experience Platform의 Analytics 데이터 세트에 조사 중인 날짜 범위에 대한 데이터가 포함되어 있는지 확인합니다.

* Analytics에서 선택한 보고서 세트가 Adobe Experience Platform에 포함된 보고서 세트와 일치하는지 확인합니다.

## 1단계: Adobe Analytics에서 발생 횟수 지표 실행

[발생 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ko) 지표는 지정된 차원이 설정되거나 지속된 히트 수를 보여 줍니다.

1. Analytics > [!UICONTROL 작업 영역]에서 차원으로 보고할 날짜 범위를 [!UICONTROL 자유 형식] 테이블로 드래그합니다.

1. [!UICONTROL 발생 횟수] 지표는 해당 날짜 범위에 자동으로 적용됩니다.

1. 비교에 사용할 수 있도록 이 프로젝트를 저장합니다.

## 2단계: 결과를 Customer Journey Analytics의 [!UICONTROL 타임스탬프별 총 레코드]와 비교

이제 Analytics의 [!UICONTROL 발생 횟수]를 Customer Journey Analytics의 타임스탬프별 총 레코드와 비교합니다.

Analytics 소스 커넥터에 의해 삭제된 레코드가 없는 경우 타임스탬프별 총 레코드는 발생 횟수와 일치해야 합니다. 아래 섹션을 참조하십시오.

>[!NOTE]
>
>이는 ([결합](/help/stitching/overview.md)을 통해) 결합된 데이터 세트가 아닌 일반 평균 값 데이터 세트에만 적용됩니다. Customer Journey Analytics에서 사용 중인 개인 ID에 대한 처리는 비교 작업을 수행하는 데 있어 매우 중요합니다. 특히 결합이 켜져 있는 경우 Adobe Analytics에서 복제하기가 항상 쉽지는 않을 수 있습니다.

1. Adobe Experience Platform [쿼리 서비스](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=ko)에서 다음 [!UICONTROL 타임스탬프별 총 레코드] 쿼리를 실행합니다.

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

1. [Analytics 데이터 피드](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ko)에서 일부 행이 Analytics 소스 커넥터에 의해 필터링되었는지 여부를 원시 데이터에서 식별합니다.

   XDM 스키마로 변환하는 동안 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko)가 특정 행을 필터링할 수 있습니다. 전체 행이 변환에 적합하지 않은 이유는 여러 가지가 있을 수 있습니다. 다음 Analytics 필드 중 하나라도 이러한 값이 포함된 경우 전체 행이 필터링됩니다.

   | Analytics 필드 | 행이 삭제되는 값 |
   | --- | --- |
   | Opt_out | y, Y |
   | In_data_only | 0이 아님 |
   | Exclude_hit | 0이 아님 |
   | Bot_id | 0이 아님 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   hit\_source에 대한 자세한 내용은 [데이터 열 참조](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ko)를 참조하십시오. page\_event에 대한 자세한 내용은 [페이지 이벤트 조회](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html?lang=ko)를 참조하십시오.

1. 커넥터가 행을 필터링한 경우 [!UICONTROL 발생 횟수] 지표에서 해당 행을 뺍니다. 결과 숫자는 Adobe Experience Platform 데이터 세트의 이벤트 수와 일치해야 합니다.

## Adobe Experience Platform에서 수집하는 동안 레코드가 필터링되거나 건너뛸 수 있는 이유

Customer Journey Analytics [연결](/help/connections/create-connection.md)을 사용하면 데이터 세트 간 공통 개인 ID를 기반으로 여러 데이터 세트를 가져오고 결합할 수 있습니다. 백엔드에서 중복 제거를 적용합니다. 타임스탬프를 기반으로 이벤트 데이터 세트에 대한 전체 외부 연결 또는 합을 적용한 다음 개인 ID를 기반으로 프로필 및 조회 데이터 세트에 대한 내부 연결을 적용합니다.

다음은 Adobe Experience Platform에서 데이터를 수집하는 동안 레코드를 건너뛸 수 있는 몇 가지 이유입니다.

* **타임스탬프 누락** – 이벤트 데이터 세트에서 타임스탬프가 누락된 경우 해당 레코드는 수집 중에 완전히 무시되거나 건너뜁니다.

* **개인 ID 누락** – (이벤트 데이터 세트 및/또는 프로필/조회 데이터 세트에서) 누락된 개인 ID로 인해 해당 레코드가 무시되거나 건너뜁니다. 그 이유는 레코드를 연결할 공통 ID나 일치하는 키가 없기 때문입니다.

* **유효하지 않거나 큰 개인 ID** – 잘못된 ID를 사용하면 시스템이 연결할 데이터 세트 중에서 유효한 공통 ID를 찾을 수 없습니다. 경우에 따라 개인 ID 열에 “정의되지 않음“ 또는 “00000000”과 같은 잘못된 개인 ID가 있습니다. 한 달에 1백만 번 이상 이벤트에 나타나는 개인 ID(숫자와 문자의 조합 포함)는 특정 사용자 또는 개인에게 할당할 수 없습니다. 잘못된 것으로 분류됩니다. 이러한 레코드는 시스템으로 수집될 수 없으며 오류 유발 수집 및 보고를 초래할 수 있습니다.
