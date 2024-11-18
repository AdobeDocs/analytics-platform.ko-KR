---
description: 주요 지표 요약 시각화를 사용하여 두 개의 타임라인에서 지표 성능을 비교할 수 있습니다.
title: 주요 지표 요약
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 40%

---

# 주요 지표 요약 {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_keymetricsummary_button"
>title="주요 지표 요약"
>abstract="선, 요약 변경 및 요약 번호 차트의 조합으로 구성된 시각화를 만듭니다. 이 시각화를 사용하여 두 기간 간에 지표가 얼마나 중요한 트렌드인지 비교합니다."

<!-- markdownlint-enable MD034 -->


![주요 지표](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 주요 지표 요약]** 시각화를 통해 단일 기간 내에서 중요한 지표의 추세를 확인할 수 있습니다. 또한 두 기간에 걸쳐 지표의 성능을 비교할 수 있습니다. 하나의 시각화로 결합된 여러 시각화의 이점을 제공합니다.

* **[!UICONTROL 선]** 시각화는 기본 및 비교 날짜 범위에 대한 지표의 추세를 보여줍니다

* **[!UICONTROL 요약 백분율 변경]**&#x200B;은 기본 날짜 범위와 비교 날짜 범위 간의 지표 증가 또는 감소를 보여 줍니다

* 지표의 현재 총 값([!UICONTROL **요약 번호**])

이 시각화는 다음을 포함한 다양한 일반적인 사용 사례를 다룹니다.

* 이번 달 영업 기회 창출이 지난해 같은 기간과 비교해 어떤 모습이었는지 이해하려는 분석가.

* 특정 리드 유형에 대한 리드 생성 방식이 이번 달부터 지난 달까지 어떻게 변화했는지 살펴보는 마케터.

* 이전 분기와 비교하여 신규 예약이 어떻게 변경되었는지 알고자 하는 임원.

## 사용

1. ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 주요 지표 요약]** 시각화를 추가합니다. [패널에 시각화 추가](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)를 참조하십시오.

1. **[!UICONTROL 지표]**, **[!UICONTROL 기본 날짜 범위]**, **[!UICONTROL 비교 날짜 범위]**(선택 사항) 및 **[!UICONTROL 필터]**(선택 사항)를 선택하여 시각화를 구성합니다.

   ![지표, 기본 날짜 범위, 비교 날짜 범위 및 세그먼트에 대한 옵션을 표시하는 주요 지표 구성입니다.](assets/key-metrics-config.png)

   | 옵션 | 설명 |
   | --- | --- |
   | **[!UICONTROL 지표]** | 검사할 지표를 선택합니다. 모든 지표가 지원됩니다. |
   | **[!UICONTROL 기본 날짜 범위]** | 자유 형식 테이블의 현재 날짜 범위입니다. |
   | **[!UICONTROL 비교 날짜 범위]** | 기본 날짜 범위를 비교하는 날짜 범위. |
   | **[!UICONTROL 필터(선택 사항)]** | 이 요약에 특히 관심이 있는 모든 필터. |

   {style="table-layout:auto"}

1. **[!UICONTROL 빌드]**&#x200B;를 선택합니다.

<!--## How the Key Metric Summary visualization handles the comparison date range

(This will probably release in January. Per Jaden Howell)

* If the primary date range is set to the panel date range, there are 2-6 options that are considered 'relative' to the primary date range. These usually include the previous period (same amount of time immediately proceeding the primary date range), and 52 weeks prior to that date range.

* If the comparison date range is set to one of the 'relative' options, upon updating the primary date range, the comparison date range updates to the period immediate preceding the panel date range.

* If your comparison date range is *not* set to a 'relative' option, then updating the panel date range changes your primary date range, but has no effect on the comparison date range.

**Example 1**

Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a relative date range, one of: 'Previous day', 'Same day last week', 'Same day 4 weeks prior', 'Same day last month', 'Same day last year', or 'Same day 52 weeks prior'.
When I change the panel's date range to 'This month', the comparison date range will update to 'Previous month'.

**Example 2**
 
Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a non-relative date range, such as 'Feb 2nd, 2022', 'Highest sales day', 'Last week', etc. 

>[!NOTE]
>
>Last week is relative to the day the project is opened on, but it is not based on the panel's date range of 'Yesterday'. In other cases, such as if the panel's date range was 'This week', it may be relative.

When you change the panel's date range to '4 days ago', the comparison date range remains at the previous selection. -->

주요 지표 요약의 출력은 다음과 같습니다.

![지표, 요약 변경, 요약 번호 및 선 그래프를 표시하는 주요 지표 출력입니다.](assets/key-metrics.png)

* **[!UICONTROL 이전 기간]** 선 그래프(항상 회색으로 표시됨)는 구성 단계의 **[!UICONTROL 비교 날짜 범위]**&#x200B;에 해당합니다.

* 구성 중에 비교 날짜 범위가 지정되지 않았거나 시각화 설정에서 숨겨져 있는 경우 기본 날짜 범위에 대한 선 그래프만 표시됩니다. 요약 변경 사항이 숨겨져 있습니다.

* 여기에서 선 그래프 위로 마우스를 가져다 대면 개별 날짜에 대한 통계를 볼 수 있습니다.


## 구성

시각화를 빌드한 후 원래 구성을 편집할 수 있습니다.

1. 시각화 상단에 있는 ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 시각화 구성]**&#x200B;을 선택합니다.

   원래 구성 대화 상자로 돌아갑니다.

1. 설정을 원하는 대로 변경합니다. 현재 설정을 재설정하려면 **[!UICONTROL 재설정]**&#x200B;을(를) 선택하십시오. **[!UICONTROL 빌드]**&#x200B;를 선택하여 시각화를 다시 빌드합니다.

## 설정

시각화 설정의 일부로, 특정 주요 지표 요약 설정을 사용할 수 있습니다.

| 설정 | 설명 |
|---|---|
| **[!UICONTROL 요약 표시 유형]** | **[!UICONTROL 백분율 변경 강조]** 또는 **[!UICONTROL 숫자 값 강조]** 중에서 선택하세요. |
| **[!UICONTROL 추세선 표시]** | 시각화에 추세선을 표시합니다. |
| **[!UICONTROL 추세선에 최대 및 최소 표시]** | 추세선에 최대값과 최소값을 표시합니다. |
| **[!UICONTROL 비교 백분율 및 추세선 표시]** | 추세선과 비교 백분율을 표시합니다. 선택하지 않으면 둘 다 숨겨집니다. |
| **[!UICONTROL 숫자 값 옵션]** | **[!UICONTROL 총 숫자 표시]** 또는 **[!UICONTROL 원시 차이 표시]**. |
| **[!UICONTROL 값 생략]** | **[!UICONTROL 값 생략]**&#x200B;을 선택하여 숫자 값을 지능적으로 축약합니다. 선택한 경우 숫자를 입력하여 약어의 양을 정의합니다. 예: <br/><table><tr><td>**원래 값**</td><td>**약어**</td><td>**결과**</td></tr><tr><td>US$12,011,141.25</td><td>선택되지 않음</td><td  align="right">US$12,011,141.25</td></tr><tr><td>US$12,011,141.25</td><td>선택됨, 1로 설정</td><td align="right">1,200만 달러</td></tr><tr><td>US$12,011,141.25</td><td>선택됨, 2로 설정</td><td  align="right">1,200만 달러</td></tr><tr><td>US$12,011,141.25</td><td>선택됨, 2로 설정</td><td align="right">1,201.1만달러</td></tr><tr><td>US$12,011,141.25</td><td>선택, 3으로 설정</td><td align="right">1,201.1만달러</td></tr></table> |

>[!MORELIKETHIS]
>
>[패널에 시각화 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[시각화 설정](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[시각화 컨텍스트 메뉴](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
