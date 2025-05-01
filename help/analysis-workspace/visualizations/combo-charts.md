---
description: Analysis Workspace에서 지난달, 지난해 등과 비교한 내용과 같은 비교 데이터를 쉽게 시각화할 수 있습니다.
title: 콤보 차트 시각화
feature: Visualizations
exl-id: 06faa997-3a4e-4c41-b64e-64a15ada6552
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 97%

---

# 콤보 {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_combo_button"
>title="콤보"
>abstract="우선 자유 형식 테이블을 만들지 않고도 콤보 차트 시각화를 빠르게 만듭니다."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_이 문서에서는_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;의 콤보 시각화에 대해 설명합니다._

_이 문서의_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 버전은 [콤보](https://experienceleague.adobe.com/ko/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts)를 참조하십시오._

>[!ENDSHADEBOX]


![콤보 차트](/help/assets/icons/ComboChart.svg) **[!UICONTROL 콤보]** 시각화 기능을 사용하면 먼저 표를 만들지 않고도 비교 시각화를 빠르고 쉽게 만들 수 있습니다. 데이터의 트렌드를 선/막대 조합으로 쉽게 볼 수 있습니다.

[!UICONTROL 콤보] 사용:

* 이번 주 주문을 지난달과 지난해 같은 시기의 주문과 비교해 보십시오.
* 동일한 차트에서 여러 지표(예: [!UICONTROL 개인] 및 [!UICONTROL 수익])를 빠르게 분석하고 비교합니다.
* 시간대의 함수(예: [!UICONTROL 누적 평균])에 대해 지표를 분석합니다.

주의 사항:

* 단일 [!UICONTROL 콤보 차트]에 여러 비교를 추가할 수 있습니다.
* 하나 이상의 비교를 추가하는 경우 [!UICONTROL 시간 비교]와 같이 동일한 유형이어야 합니다.
* 최대 5개의 비교를 추가할 수 있습니다.
* 지표에 최대 3개의 세그먼트를 적용할 수 있습니다.
* 계산된 지표는 콤보 차트에서 지원되지 않습니다.

## 사용

1. ![댓글](/help/assets/icons/ComboChart.svg) [!UICONTROL 콤보] 시각화를 추가합니다. [패널 내에 시각화 추가](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)를 참조하십시오.

1. 드롭다운 메뉴에서 X축의 차원과 Y축의 지표를 선택합니다.

1. 사용하려는 [!UICONTROL 선 비교] 유형을 선택합니다.

   | 선 비교 유형 | 정의 |
   | --- | --- |
   | **[!UICONTROL 시간 비교]** | 예를 들어 가장 일반적인 비교 유형은 4주 전과 이 기간을 비교하는 것입니다. [!UICONTROL 시간 비교]를 선택한 경우 비교할 기간에 대해 2차 선택을 합니다.<p>![선택한 기간과 2차 선택 필드로 설정한 기간을 비교하는 선입니다.](assets/combo-time-period.png) |
   | **[!UICONTROL 함수]** | [!UICONTROL 평균]과 같은 함수를 비교에 도입할 수 있습니다. [지원되는 함수](#supported-functions) 목록을 참조하십시오.<p>![선택한 기능과 사용 가능한 지원 기능 목록을 표시하는 선 비교 드롭다운 메뉴입니다.](assets/combo-functions.png) |
   | **[!UICONTROL 보조 지표]** | 예를 들어 [!UICONTROL 수익]을 다른 지표와 비교할 수 있습니다.<p>![두 가지 지표를 비교하는 콤보 차트입니다.](assets/combo-2metrics-settings.png) |

   {style="table-layout:auto"}

1. **[!UICONTROL 빌드]**&#x200B;를 선택합니다.

   출력은 다음과 유사합니다.

   ![막대 차트로 표시된 현재 기간과 선 차트로 표시된 비교 기간을 포함한 콤보 차트 ](assets/combo-output.png)

   현재 기간은 막대 차트로 표시됩니다. 비교 기간은 선 차트로 표시됩니다. 선 차트의 점을 “*바벨*”이라고 합니다.

## 지원되는 함수

[!UICONTROL 선 비교 유형]으로 **[!UICONTROL 함수]**&#x200B;를 선택하면 선택한 지표의 함수가 반환됩니다.

| 함수 | 정의 |
| --- | --- |
| **[!UICONTROL 열 합계]** | 열 내의 한 지표에 대한 모든 숫자 값을 추가합니다(차원의 요소들에 대해). |
| **[!UICONTROL 누적 평균]** | 마지막 N개 행의 평균을 반환합니다. |
| **[!UICONTROL 중간값]** | 열에 있는 지표에 대한 중간값을 반환합니다. 중간은 숫자 세트의 중간에 있는 숫자입니다. 이 값의 반은 중간값보다 크거나 같은 값이고 다른 반은 중간값보다 작거나 같습니다. |
| **[!UICONTROL 누적]** | N개 행의 누적 합계입니다. |
| **[!UICONTROL 열 최대값]** | 지표 열에 대한 차원 요소 세트에서 가장 큰 값을 반환합니다. |
| **[!UICONTROL 평균]** | 지표에 대한 산술 평균 또는 평균을 반환합니다. |
| **[!UICONTROL 열 최소값]** | 지표 열에 대한 차원 요소 세트에서 가장 작은 값을 반환합니다. |

{style="table-layout:auto"}

다음은 수익 지표에 대한 누적 평균의 예입니다.

![누적 평균을 보여 주는 콤보 차트](assets/combo-cumul-avg.png)

다음은 누적 평균 및 평균 함수가 모두 포함된 콤보 차트의 예입니다.

![누적 평균 및 평균 함수가 모두 포함된 콤보 차트입니다.](assets/combo-three-functions.png)

>[!MORELIKETHIS]
>
>[패널 내에 시각화 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[시각화 설정](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[시각화 컨텍스트 메뉴](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
