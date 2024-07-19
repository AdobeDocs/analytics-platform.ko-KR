---
description: 주요 지표 요약 시각화를 사용하여 두 개의 타임라인에서 지표 성능을 비교할 수 있습니다.
title: 주요 지표 요약
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: 24c2ab4a49b87b11046317a40882dde72a2a49c1
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 85%

---

# 주요 지표 요약

[!UICONTROL 주요 지표 요약 시각화]를 통해 단일 기간 내에서 중요한 지표의 추세를 확인할 수 있습니다. 또한 두 기간에 걸쳐 지표의 성능을 비교할 수 있습니다. 하나의 시각화로 결합된 여러 시각화의 이점을 제공합니다.

* 기본 및 비교 날짜 범위에 대한 지표의 추세를 보여 주는 **[!UICONTROL 선]** 시각화

* 기본 날짜 범위와 비교 날짜 범위 간의 지표 증가 또는 감소를 보여 주는 **[!UICONTROL 요약 백분율 변경]**

* 지표의 현재 총 값([!UICONTROL **요약 번호**])

## 사용 사례

이 시각화는 다음을 포함한 다양한 일반적인 사용 사례를 다룹니다.

* 이번 달 영업 기회 창출이 지난해 같은 기간과 비교해 어떤 모습이었는지 이해하려는 분석가.

* 특정 리드 유형에 대한 리드 생성 방식이 이번 달부터 지난 달까지 어떻게 변화했는지 살펴보는 마케터.

* 이전 분기와 비교하여 신규 예약이 어떻게 변경되었는지 알고자 하는 임원.

## 주요 지표 요약 구성

1. 왼쪽 레일에 있는 **[!UICONTROL 시각화]** 메뉴에서 **[!UICONTROL 주요 지표 요약]** 시각화를 패널로 드래그합니다.

1. 지표, 기본 날짜 범위, 비교 날짜 범위 및 필터(원하는 경우)를 선택하여 시각화를 구성합니다.

   ![지표, 기본 날짜 범위, 비교 날짜 범위 및 세그먼트에 대한 옵션을 표시하는 주요 지표 구성입니다.](assets/key-metric-config.png)

   | 구성 설정 | 정의 |
   | --- | --- |
   | **[!UICONTROL 지표]** | 검사할 지표를 선택합니다. 모든 지표가 지원됩니다. |
   | **[!UICONTROL 기본 날짜 범위]** | 자유 형식 테이블의 현재 날짜 범위입니다. |
   | **[!UICONTROL 비교 날짜 범위]** | 기본 날짜 범위를 비교하는 날짜 범위. |
   | **[!UICONTROL 필터(선택 사항)]** | 이 요약에 특히 관심이 있는 모든 필터. |

   {style="table-layout:auto"}

1. **[!UICONTROL 빌드]**&#x200B;를 클릭합니다.

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

## 출력 보기

![지표, 요약 변경, 요약 번호 및 선 그래프를 표시하는 주요 지표 출력입니다.](assets/key-metric-output.png)

참고:

* **[!UICONTROL 이전 기간]** 선 그래프(항상 회색으로 표시됨)는 구성 단계의 **[!UICONTROL 비교 날짜 범위]**&#x200B;에 해당합니다.

* 구성 중에 비교 날짜 범위가 지정되지 않았거나 시각화 설정에서 숨겨져 있는 경우 기본 날짜 범위에 대한 선 그래프만 표시됩니다. 요약 변경 사항이 표시되지 않습니다.

* 여기에서 선 그래프 위로 마우스를 가져다 대면 개별 날짜에 대한 통계를 볼 수 있습니다.

![방문 통계](assets/key-metric-output2.png)

## 시각화 설정

주요 지표 요약은 중요한 지표의 보고 및 공유를 개선하기 위해 여러 유연한 설정을 제공합니다. 시각화 오른쪽 상단에 있는 톱니바퀴 아이콘을 사용하여 설정에 액세스할 수 있습니다.

![요약 표시 유형, 일반 및 표시 옵션을 보여 주는 주요 지표 요약 설정입니다.](assets/key-metric-settings.png)

| 설정 | 설명 |
| --- | --- |
| **[!UICONTROL 백분율 변경 강조]** | 시각화 중앙에 눈에 띄는 볼드체로 요약 변경 사항 표시 |
| **[!UICONTROL 숫자 값 강조]** | 시각화 중앙에 눈에 띄는 볼드체로 요약 번호 표시 |
| **[!UICONTROL 범례 표시]** | 시각화 하단에 범례 표시 또는 숨기기 |
| **[!UICONTROL 주석 표시]** | 관리자가 추가한 주석 표시 또는 숨기기 |
| **[!UICONTROL 스파크라인 표시]** | 차트 하단에 선 차트를 표시하거나 숨깁니다. 범례가 숨겨져 있으면 더 이상 시각적으로 선을 참조하지 않습니다. |
| **[!UICONTROL 스파크라인에서 최소 및 최대 표시]** | 기본 및 비교 선 차트에서 최소값 및 최대값 표시 또는 숨기기 |
| **[!UICONTROL 비교 보기]** | 비교 데이터를 표시하거나 숨깁니다. 숨겨진 경우 보기에서 비교 선 차트와 요약 변경 오브젝트가 모두 표시되지 않습니다. |
| **[!UICONTROL 총 숫자 표시]** | 요약 번호 표시 또는 숨기기 |
| **[!UICONTROL 원시 차이 표시]** | 기본 날짜 범위와 보조 날짜 범위의 총 지표 값 간의 원시 차이를 표시하거나 숨깁니다. |
| **[!UICONTROL 값 생략]** | 전달되는 통찰력을 단순화하기 위해 숫자 값을 축약합니다(예: 20,000 -> 20K). |

## 시각화 편집

시각화를 빌드한 후에도 원래 구성을 편집할 수 있습니다.

1. 시각화 오른쪽 상단(설정 톱니바퀴 아이콘 옆)에 있는 연필 아이콘을 클릭합니다.

   ![시각화 편집 아이콘](assets/edit-icon.png)

   이제 원래 구성 보기로 돌아갑니다.

1. 지표, 기본 날짜 범위, 비교 날짜 범위 또는 필터를 원하는 대로 변경합니다.
