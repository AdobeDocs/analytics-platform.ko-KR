---
title: AA 데이터를 CJA 데이터와 비교
description: Adobe Analytics 데이터를 Customer Journey Analytics의 데이터와 비교하는 방법을 알아봅니다
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
source-git-commit: b0d29964c67d8a6a847a05dbe113b8213b346f9b
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 4%

---


# Adobe Analytics 데이터를 CJA 데이터와 비교

Analytics 소스 커넥터를 통해 Adobe Analytics 데이터를 AEP에 수집한 다음 이 데이터 세트를 사용하여 CJA 연결을 만들었다고 가정해 보겠습니다.

![데이터 흐름](assets/compare.png)

그런 다음 데이터 보기를 만든 후 CJA에서 이 데이터를 보고하면서 Adobe Analytics의 보고 결과와 불일치를 발견했습니다.

원본 Adobe Analytics 데이터를 이제 Customer Journey Analytics에 있는 Adobe Analytics 데이터와 비교하는 몇 가지 단계는 다음과 같습니다.

## 사전 요구 사항

* AEP의 Analytics 데이터 세트에 조사 중인 날짜 범위에 대한 데이터가 포함되어 있는지 확인합니다.

* Analytics에서 선택한 보고서 세트가 Adobe Experience Platform에 수집된 보고서 세트와 일치하는지 확인합니다.


## 1단계: Adobe Analytics에서 발생 횟수 지표를 실행합니다

다음 [발생 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en) 지표는 주어진 차원이 설정되거나 지속된 히트의 수를 보여줍니다.

1. Analytics >에서 [!UICONTROL 작업 공간]을 눌러 보고하려는 날짜 범위를 차원으로 드래그합니다 [!UICONTROL 자유 형식] 테이블.

1. 다음 [!UICONTROL 발생 횟수] 지표는 해당 날짜 범위에 자동으로 적용됩니다.

1. 비교에서 사용할 수 있도록 이 프로젝트를 저장하십시오.

## 2단계: 결과를 다음으로 비교 [!UICONTROL 타임스탬프별 총 레코드] CJA에서

이제 을(를) 비교합니다 [!UICONTROL 발생 횟수] analytics에서 Customer Journey Analytics의 타임스탬프별 총 레코드 수

Analytics 소스 커넥터에 의해 삭제된 레코드가 없는 경우 타임스탬프별 총 레코드 수가 발생 횟수와 일치해야 합니다. 아래 섹션을 참조하십시오.

>[!NOTE]
>
>이 작업은 결합된 데이터 세트( 를 통해)가 아니라 일반 mid 값 데이터 세트에만 작동합니다 [크로스 채널 분석](/help/connections/cca/overview.md)). CJA에서 사용되는 개인 ID를 회계는 비교를 수행하는 데 매우 중요합니다. 특히 크로스 채널 분석 기능이 설정된 경우 AA에서 복제하는 것이 항상 쉽지는 않을 수 있습니다.

1. Adobe Experience Platform에서 [쿼리 서비스](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html)를 입력하여 타임스탬프별 다음 총 레코드 수 쿼리를 실행합니다.

```
SELECT Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) as Day, \ 
        Count(_id) AS Records 
        FROM  {dataset} \ 
        WHERE timestamp>=from_utc_timestamp('{fromDate}','UTC') \ 
        AND timestamp<from_utc_timestamp('{toDate}','UTC') \ 
        AND timestamp IS NOT NULL \ 
        AND enduserids._experience.aaid.id IS NOT NULL  \ 
        GROUP BY Day \ 
        ORDER BY Day; 
```

1. in [Analytics 데이터 피드](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ko-KR)를 사용하여 원시 데이터에서 일부 행을 Analytics 소스 커넥터에서 삭제할 수 있는지 확인합니다.

   다음 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko-KR) XDM 스키마로 변환하는 동안 행이 삭제될 수 있습니다. 전체 행이 변환에 적합하지 않은 여러 이유가 있을 수 있습니다. 다음 Analytics 필드에 이러한 값이 있으면 전체 행이 삭제됩니다.

   | Analytics 필드 | 삭제되는 원인이 되는 값 |
   | --- | --- |
   | 옵트아웃(_O) | `y, Y` |
   | In_data_only | 0 아님 |
   | Exclude_hit | 0 아님 |
   | 보트_id | 0 아님 |
   | Hit_source | 0,3,5,7,8,9,10 |
   | Page_event | 53,63 |

1. 커넥터가 행을 삭제한 경우 발생 횟수 지표에서 해당 행을 제외합니다. 결과 숫자는 AEP 데이터 세트에 있는 이벤트 수와 일치해야 합니다.

## AEP에서 수집하는 동안 레코드가 삭제되거나 건너뛸 수 있는 이유

CJA [연결](/help/connections/create-connection.md) 을(를) 사용하면 데이터 세트 간에 공통 개인 ID를 기반으로 여러 데이터 세트를 함께 가져와서 결합할 수 있습니다. 백엔드에서 중복 제거를 적용합니다. 타임스탬프를 기반으로 하는 이벤트 데이터 세트에서 전체 외부 조인 또는 결합을 수행한 다음 개인 ID를 기반으로 프로필 및 조회 데이터 세트에 대한 내부 참여를 만듭니다.

AEP에서 데이터를 수집하는 동안 레코드를 건너뛸 수 있는 몇 가지 이유는 다음과 같습니다.

* **타임스탬프가 누락됨** - 이벤트 데이터 세트에서 타임스탬프가 누락된 경우 이러한 레코드는 수집 중에 완전히 무시되거나 건너뜁니다. 데이터 세트를 함께 결합할 수 있기 때문입니다.

* **개인 ID가 없습니다.** - 개인 ID가 누락되어(이벤트 데이터 세트 및/또는 프로필/조회 데이터 세트에서) 해당 레코드가 무시되거나 건너뜁니다. 그 이유는 레코드에 조인할 일반적인 ID 또는 일치하는 키가 없기 때문입니다.

* **잘못된 개인 ID** - 잘못된 ID를 사용하는 경우 시스템에서 조인할 데이터 세트 간에 유효한 공통 ID를 찾을 수 없습니다. 경우에 따라 개인 ID 열에 &quot;정의되지 않음&quot; 또는 &quot;00000000&quot;과 같은 잘못된 개인 ID가 있습니다.

* **큰 개인 ID** - 월 100만 번 이상의 이벤트에 표시되는 숫자와 문자의 조합이 있는 개인 ID는 특정 사용자 또는 개인에게 귀속될 수 없습니다. 잘못된 것으로 분류됩니다. 이러한 레코드를 시스템에 수집할 수 없으며 오류가 발생하기 쉬운 수집 및 보고가 발생합니다.


