---
description: 지난달, 지난해 등과 비교한 내용과 같은 Analysis Workspace의 비교 데이터를 쉽게 시각화할 수 있습니다.
title: 콤보 차트 시각화
feature: Visualizations
exl-id: 06faa997-3a4e-4c41-b64e-64a15ada6552
role: User
source-git-commit: 590a3ddbe988d27341fe96a3fa866960d1641e24
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 44%

---

# 콤보 {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_combo_button"
>title="콤보"
>abstract="우선 자유 형식 테이블을 만들지 않고도 콤보 차트 시각화를 빠르게 만듭니다."

<!-- markdownlint-enable MD034 -->


![주석](/help/assets/icons/ComboChart.svg) **[!UICONTROL 콤보]** 시각화를 사용하면 먼저 표를 만들지 않고도 비교 시각화를 빠르게 만들 수 있습니다. 데이터의 트렌드를 선/막대 조합으로 쉽게 볼 수 있습니다.

[!UICONTROL 콤보]를 사용하여 다음을 수행할 수 있습니다.

* 이번 주 주문을 지난달과 지난해 같은 시기의 주문과 비교합니다.
* 동일한 차트에서 여러 지표(예: [!UICONTROL 개인] 및 [!UICONTROL 매출])를 빠르게 분석하고 비교합니다.
* 시간대의 함수(예: [!UICONTROL 누적 평균])에 대해 지표를 분석합니다.

주의 사항:

* 단일 [!UICONTROL 콤보 차트]에 여러 비교를 추가할 수 있습니다.
* 하나 이상의 비교를 추가하는 경우 [!UICONTROL 시간 비교]와 같이 동일한 유형이어야 합니다.
* 최대 5개의 비교를 추가할 수 있습니다.
* 지표에 최대 3개의 필터를 적용할 수 있습니다.
* 계산된 지표는 콤보 차트에서 지원되지 않습니다.

## Use

1. ![댓글](/help/assets/icons/ComboChart.svg) [!UICONTROL 콤보] 시각화를 추가합니다. [패널에 시각화 추가](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)를 참조하세요.

1. 드롭다운 목록에서 X축의 차원과 Y축의 지표를 선택합니다.

1. 사용할 [!UICONTROL 선 비교]의 형식을 선택하십시오.

   | 선 비교 유형 | 정의 |
   | --- | --- |
   | **[!UICONTROL 시간 비교]** | 예를 들어 가장 일반적인 비교 유형은 4주 전과 이 기간을 비교하는 것입니다. [!UICONTROL 시간 비교]를 선택한 경우 비교할 기간에 대해 2차 선택을 합니다.<p>![선택한 기간과 비교 및 기간에 대한 보조 선택 필드](assets/combo-time-period.png) |
   | **[!UICONTROL 함수]** | [!UICONTROL 평균]과 같은 함수를 비교에 도입할 수 있습니다. [지원되는 함수](#supported-functions) 목록을 참조하십시오.<p>![선택한 함수 및 사용 가능한 지원되는 함수 목록을 표시하는 [기본 비교] 드롭다운 메뉴입니다.](assets/combo-functions.png) |
   | **[!UICONTROL 보조 지표]** | 예를 들어 [!UICONTROL 수익]을 다른 지표와 비교할 수 있습니다.<p>![두 지표를 비교하는 콤보 차트입니다.](assets/combo-2metrics-settings.png) |

   {style="table-layout:auto"}

1. **[!UICONTROL 빌드]**&#x200B;를 선택합니다.

   출력은 다음과 유사합니다.

   ![현재 기간을 막대 차트로 표시하는 콤보 차트 및 선 차트 ](assets/combo-output.png)의 비교 기간

   현재 기간이 막대 차트에 표시됩니다. 선 차트는 비교 기간을 나타냅니다. 선 차트의 점을 *바벨*&#x200B;이라고 합니다.

## 지원되는 함수

**[!UICONTROL 함수]**&#x200B;을(를) [!UICONTROL 선 비교 형식](으)로 선택하면 선택한 지표의 함수가 반환됩니다.

| 함수 | 정의 |
| --- | --- |
| **[!UICONTROL 열 합계]** | 열 내의 한 지표에 대한 모든 숫자 값을 추가합니다(차원의 요소들에 대해). |
| **[!UICONTROL 누적 평균]** | 마지막 N개 행의 평균을 반환합니다. |
| **[!UICONTROL 중간값]** | 열에 있는 지표에 대한 중간값을 반환합니다. 중앙값은 숫자 집합의 가운데 있는 숫자입니다. 숫자의 절반에는 중앙값보다 크거나 같은 값이 있고, 숫자의 절반에는 중앙값보다 작거나 같은 값이 있습니다. |
| **[!UICONTROL 누적]** | N개 행의 누적 합계입니다. |
| **[!UICONTROL 열 최대값]** | 지표 열에 대한 차원 요소 세트에서 가장 큰 값을 반환합니다. |
| **[!UICONTROL 평균]** | 지표에 대한 산술 평균 또는 평균을 반환합니다. |
| **[!UICONTROL 열 최소값]** | 지표 열에 대한 차원 요소 세트에서 가장 작은 값을 반환합니다. |

{style="table-layout:auto"}

다음은 수익 지표에 대한 누적 평균의 예입니다.

![누적 평균을 보여 주는 콤보 차트](assets/combo-cumul-avg.png)

다음은 누적 평균 및 평균 함수가 모두 포함된 콤보 차트의 예입니다.

![누적 평균 및 평균 함수를 모두 표시하는 콤보 차트입니다.](assets/combo-three-functions.png)

>[!MORELIKETHIS]
>
>[패널에 시각화 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[시각화 설정](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[시각화 컨텍스트 메뉴](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>