---
description: 라인 시각화를 사용하여 트렌드(시간 기반) 데이터 세트를 나타냅니다.
title: 라인
feature: Visualizations
exl-id: b68aa8dc-2c96-4c49-8d3c-d94804aab479
role: User
source-git-commit: bf5853a1d23d6e648024016a64dc67d09da3fbb4
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 22%

---

# 라인 {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="라인"
>abstract="일정 기간 동안 값이 어떻게 변하는지를 보여 주는 선 시각화를 만듭니다. 라인 시각화는 시간을 차원으로 사용하는 경우에만 사용할 수 있습니다."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*이 문서는&#x200B;**Customer Journey Analytics**의 선 시각화에 대해 설명합니다.이 문서의&#x200B;**Adobe Analytics**버전은 <br/>줄](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/line)을 참조하세요.*[

>[!ENDSHADEBOX]


![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Line]** 시각화는 일정 기간 동안 값이 어떻게 변하는지를 보여 주기 위해 선을 사용하여 지표를 나타냅니다. 시간을 차원으로 사용하는 경우에만 선 시각화를 사용할 수 있습니다.

<!--
>[!NOTE]
>
>The Line visualization soon feature [intelligent captions](/help/analysis-workspace/visualizations/intelligent-captions.md).

The Line visualization represents metrics using a line to show how values change over a period of time. A line chart can be used only when time is used as a dimension.
-->

![라인 시각화](assets/line-viz.png)


## 설정

[시각화 설정](freeform-analysis-visualizations.md#settings)의 일부로 특정 선 시각화 설정을 사용할 수 있습니다.

| 설정 | 설명 |
|---|---|
| **[!UICONTROL 세부 기간]** | 세부 기간 드롭다운에서 을 선택하여 트렌드 시각화를 일별에서 주별, 월별 등으로 변경합니다. 세부기간은 데이터 소스 테이블에서도 업데이트됩니다. |
| **[!UICONTROL 최소 표시]** <br/>**[!UICONTROL 최대 표시&#x200B;]** | 최소값 및 최대값 레이블을 오버레이하여 지표의 최소값과 최대값을 강조 표시할 수 있습니다. 최소/최대 값은 차원 내의 전체 값 집합이 아니라 시각화에 표시되는 데이터 포인트에서 파생됩니다.<br/>![최소값 및 최대값 레이블이 있는 오버레이입니다.](assets/min-max-labels.png) |
| **[!UICONTROL 추세선 표시]** | 회귀 또는 이동 평균 추세선을 라인 시리즈에 추가하도록 선택할 수 있습니다. 추세선은 데이터에서 더 명확한 패턴을 묘사하는 데 도움이 됩니다. 선택한 경우 목록에서 모델을 선택합니다. 사용 가능한 모델에 대한 개요 및 설명은 [모델](#models)을 참조하세요.<br/>![선형 추세선](assets/show-linear-trendline.png). |

>[!TIP]
>
>오늘(부분 데이터) 또는 미래 날짜를 포함하지 않는 데이터에 추세선을 적용하는 것이 좋습니다. 오늘 또는 미래 날짜는 추세선을 왜곡합니다. 그러나 미래 날짜를 포함해야 하는 경우 데이터에서 0을 제거하여 해당 날짜에 대한 왜곡을 방지하십시오. 시각화의 데이터 소스 테이블로 이동하여 지표 열을 선택한 다음 **[!UICONTROL 열 설정]** > **[!UICONTROL 0을 값 없음으로 해석]**&#x200B;합니다.



### 모델

모든 회귀 모델 추세선은 정규방정식을 사용하여 맞춰집니다.

| 모델 | 설명 |
| --- | --- |
| **[!UICONTROL 선형]** | 간단한 선형 데이터 세트에 가장 적합한 직선을 만들고 데이터가 일정한 속도로 증가 또는 감소하는 경우 유용합니다. 수식: `y = a + b * x` |
| **[!UICONTROL 로그]** | 가장 잘 맞는 곡선을 만들며 데이터의 변경 속도가 빠르게 증가 또는 감소하다가 수평을 유지하는 경우 유용합니다. 로그 트렌드 라인은 음수 값과 양수 값을 사용할 수 있습니다. 수식: `y = a + b * log(x)` |
| **[!UICONTROL 지수]** | 곡선을 만들고 데이터가 지속적으로 증가하는 비율로 증가하거나 감소할 때 유용합니다. 데이터에 0이나 음수 값이 있는 경우에는 이 옵션을 사용하지 마십시오. 수식: `y = a + e^(b * x)` |
| **[!UICONTROL 전원]** | 곡선을 만들고 특정 비율로 증가하는 측정을 비교하는 데이터 세트에 유용합니다. 데이터에 0이나 음수 값이 있는 경우에는 이 옵션을 사용하지 마십시오. 수식: `y = a * x^b` |
| **[!UICONTROL 이차]** | 포물선(위 또는 아래로 오목)과 같은 모양의 데이터 세트에 가장 잘 맞습니다. 수식: `y = a + b * x + c * x^2` |
| **[!UICONTROL 이동 평균]** | 평균 세트를 기반으로 부드러운 추세선을 만듭니다. 롤링 평균이라고도 하는 이동 평균은 특정 수의 데이터 포인트([!UICONTROL 세부기간] 선택에 의해 결정됨)를 사용하고 평균을 계산하여 선의 한 지점으로 사용합니다. 예를 들어 7일 이동 평균 또는 4주 이동 평균이 있습니다. |

>[!MORELIKETHIS]
>
>[패널에 시각화 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[시각화 설정](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[시각화 컨텍스트 메뉴](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

