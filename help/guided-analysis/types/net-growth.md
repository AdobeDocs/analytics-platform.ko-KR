---
title: 순성장 분석
description: 사용자가 증가하고 있습니까, 감소하고 있습니까?
feature: Adobe Product Analytics, Guided Analysis
keywords: 제품 분석
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: be617c59cd2fced0031fda1130b86e638bee8f68
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 93%

---

# [!UICONTROL 순성장] 분석 {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="순성장"
>abstract="사용자가 증가하고 있습니까, 감소하고 있습니까?"

<!-- markdownlint-enable MD034 -->

![순성장](/help/assets/icons/NetGrowth.svg) **[!UICONTROL 순성장]** 분석은 특정 기간 동안 사용자가 늘어나거나 줄어드는 비율에 대한 인사이트를 제공합니다. 가로축은 시간 간격이고, 세로축은 성장 측정값입니다.

각 데이터 포인트는 다음 공식을 사용하여 계산된 순성장을 나타냅니다.

`([New users] + [Return users]) / [Dormant users]`

이 공식의 결과는 비율입니다. `1`의 순성장은 균형을 나타내므로 이 제품은 줄어든 수만큼 사용자를 확보했습니다. 순성장이 `1` 보다 높다는 것은 긍정적인 성장을 의미하며, 휴면 사용자보다 신규 + 재방문 사용자가 더 많았습니다. 마찬가지로, 순성장이 `1`보다 낮으면 손실을 의미하며, 휴면 사용자가 신규 + 재방문 사용자보다 더 많았습니다.

[활성](active-growth.md) 분석과 유사하게 사용자는 다음과 같이 정의됩니다.

* **[!UICONTROL 신규]**: 사용자는 현재 기간 동안 활동했지만 이전에는 활동하지 않았습니다. 차트 범례에서 “[!UICONTROL 신규 사용자]” 위에 마우스를 가져다 대면 새로운 사용자를 확인하기 위해 분석이 얼마나 과거를 전환되었는지 확인할 수 있습니다. 전환 확인 범위는 선택한 날짜 범위 및 간격에 따라 동적으로 결정됩니다.
* **[!UICONTROL 복귀]**: 사용자는 현재 기간에는 활동적이었지만 바로 이전 기간에는 활동적이지 않았으나, 예전에는 특정 시점에 활동적이었습니다. 차트 범례에서 “[!UICONTROL 복귀 사용자]” 위에 마우스를 가져다 대면 복귀 사용자를 확인하기 위해 분석이 얼마나 과거를 전환되었는지 확인할 수 있습니다. 전환 확인 범위는 선택한 날짜 범위 및 간격에 따라 동적으로 결정됩니다.
* **[!UICONTROL 휴면]**: 사용자는 바로 이전 기간에는 활동적이었으나 현재 기간에는 활동적이지 않습니다. 휴면 사용자는 전체 활성 사용자 수에 포함되지 않습니다.

>[!NOTE]
>
>반복 사용자는 사용자 수의 증가나 감소를 나타내지 않으므로 이 계산에는 반영되지 않습니다.

>[!VIDEO](https://video.tv.adobe.com/v/3423464/?quality=12&learn=on&captions=kor)


## 사용 사례

이 분석의 사용 사례는 다음과 같습니다.

* **성과 평가**: 새로운 사용자 확보 측면에서 제품의 전반적인 성과를 평가할 수 있습니다. 성장 추세를 추적하면 제품이 원하는 속도로 사용자를 유치하고 유지하고 있는지 더 잘 이해할 수 있습니다.
* **사용자 확보 분석**: 사용자 확보 전략의 효과를 평가할 수 있습니다. 사용자 증가의 원천, 예를 들어 검색 엔진, 캠페인 또는 기타 마케팅 채널을 분석하면 가장 중요한 성장 원천을 파악할 수 있어 자원을 적절히 배분할 수 있습니다.
* **이탈 분석**: 순성장의 공식에는 이탈(휴면 사용자)이 포함됩니다. 시간이 지남에 따라 사용자 기반의 전반적인 건강 상태를 평가할 수 있습니다. 순성장이 `1` 보다 일관되게 낮으면 이탈이 많다는 것을 의미하므로, 유지 전략을 실행하는 데 도움이 될 수 있습니다.

## 인터페이스

가이드 분석 인터페이스 개요는 [인터페이스](../overview.md#interface)에서 확인하십시오. 다음 설정은 이 분석에만 적용됩니다.

### 쿼리 레일

쿼리 레일을 사용하면 다음 구성 요소를 구성할 수 있습니다.

* **[!UICONTROL 보기]**: 이 분석과 [활성 증가](active-growth.md) 간을 전환합니다.
* **[!UICONTROL 이벤트]**: 측정하려는 이벤트. 이 분석은 사용자 기반이므로, 해당 기간 내에 이벤트와 한 번 상호 작용한 사용자는 활성 사용자로 간주됩니다. 쿼리에 하나의 이벤트를 포함할 수 있습니다.
* **[!UICONTROL 다음으로 계산됨]**: 선택한 이벤트에 적용할 계산 방법입니다. <ul><li>**[!UICONTROL 옵션]**&#x200B;에는 [!UICONTROL 사용자 수] 및 [!UICONTROL 사용자 비율]이 포함됩니다.</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 추가 **[!UICONTROL B2B 옵션]**&#x200B;은(는) Customer Journey Analytics B2B edition에서 사용할 수 있습니다. [!UICONTROL 글로벌 계정], [!UICONTROL 계정], [!UICONTROL 구매 그룹], [!UICONTROL 기회], [!UICONTROL 글로벌 계정의 백분율], [!UICONTROL 계정의 백분율], [!UICONTROL 구매 그룹의 백분율] 및 [!UICONTROL 기회의 백분율].</li></ul>
* **[!UICONTROL 세그먼트]**: 측정하려는 세그먼트. 쿼리에 하나의 세그먼트를 포함할 수 있습니다.

### 시간 비교

{{apply-time-comparison}}

### 날짜 범위

분석에 원하는 날짜 범위. 이 설정에는 두 가지 구성 요소가 있습니다.

* **[!UICONTROL 간격]**: 추세 데이터를 보려는 날짜별 세부 기간. 유효한 옵션으로는 시간별, 일별, 주별, 월별, 분기별이 있습니다. 동일한 날짜 범위는 차트의 데이터 포인트 수와 테이블의 열 수에 영향을 미치는 다양한 간격을 가질 수 있습니다. 예를 들어 일일 세분 기간으로 3일에 걸친 분석을 보면 데이터 포인트가 3개만 표시되는 반면, 시간별 세분 기간으로 3일에 걸친 분석에서는 72개의 데이터 포인트가 표시됩니다.
* **[!UICONTROL 날짜]**: 시작 및 종료 날짜. 순환 날짜 범위 사전 설정과 이전에 저장된 사용자 정의의 범위를 편리하게 사용할 수 있으며, 캘린더 선택기를 사용하여 고정된 날짜 범위를 선택할 수도 있습니다.

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
