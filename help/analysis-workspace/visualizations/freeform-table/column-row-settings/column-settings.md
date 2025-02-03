---
description: 열 설정을 편집하여 열 서식을 구성하는 방법에 대해 알아봅니다. 열 서식 일부는 조건부일 수 있습니다.
title: 열 설정
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 21%

---

# [!UICONTROL 열 설정]

[!UICONTROL 열 설정]을 사용하면 열 서식을 구성할 수 있으며, 열 서식 일부는 조건부일 수 있습니다.


>[!BEGINSHADEBOX]

데모 비디오는 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [자유 형식 테이블의 행 및 열 설정](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"}을 참조하십시오.

{{videoaa}}

>[!ENDSHADEBOX]


[!UICONTROL 열 설정]에 액세스하려면 열 머리글에서 ![열 설정](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)을 선택하세요.

![열 설정](assets/column-settings.png)


한 번에 여러 열의 설정을 편집할 수 있습니다. 여러 열을 선택하고 선택한 열 중 하나에서 ![설정](/help/assets/icons/Setting.svg)을(를) 선택합니다. 변경한 내용은 셀이 선택된 모든 열에 적용됩니다.

| 옵션 | 설명 |
| --- | --- |
| **[!UICONTROL 합계 표시]** | 열의 클라이언트측 합계를 표시합니다. 이 합계는 세션 또는 개인과 같은 지표에 대한 중복 제거를 **하지 않습니다**. |
| **[!UICONTROL 총계 표시]** | 열의 서버측 합계를 표시합니다. 총계는 세션 또는 개인과 같은 지표에 대한 중복 제거를 수행합니다. |
| **[!UICONTROL 스파크라인 표시]** | 열 머리글에 꺾은선형 차트를 표시합니다. |
| **[!UICONTROL 숫자]** | 셀에 지표에 대한 숫자 값을 표시할지 또는 숨길지 여부를 결정합니다. 예를 들어 지표가 페이지 조회수이면 숫자 값은 행 항목에 대한 페이지 조회수입니다. |
| **[!UICONTROL 비율]** | 셀에 지표에 대한 퍼센트 값을 표시할지 또는 숨길지 여부를 결정합니다. 예를 들어 지표가 페이지 보기 횟수이면, 퍼센트 값은 행 항목에 대한 페이지 보기 횟수를 해당 열에 대한 총 페이지 보기 횟수로 나눈 수입니다.  참고: 100%보다 큰 백분율이 정확성을 보장할 수 있습니다. 열 너비가 너무 커지는 것을 방지하기 위해 상한을 1,000%로 이동할 수 있습니다. |
| **[!UICONTROL 예외 항목 표시]** | 이 열의 값에 대해 예외 항목 탐지가 실행되는지 확인합니다. |
| **[!UICONTROL 예측 표시]** | 이 열에 예측 값이 표시되는지 여부를 결정합니다. |
| **[!UICONTROL 머리글 텍스트 줄바꿈]** | 자유 형식 테이블의 머리글 텍스트를 줄바꿈하여 머리글을 더 읽기 쉽게 하고 테이블을 더 공유하기 쉽게 합니다. 래핑은 PDF 렌더링 및 긴 이름이 있는 지표에 유용합니다. 기본적으로 사용됩니다. |
| **[!UICONTROL 0을 값 없음으로 해석]** | 값이 0인 셀에 대해 0을 표시할지 아니면 빈 셀을 표시할지를 결정합니다. 이러한 해석은 한 달의 각 날에 대한 데이터를 보고 미래 날짜의 데이터를 볼 때 유용합니다.  이후 날짜에 대해 0을 표시하는 대신 빈 셀이 표시됩니다. 차트는 이 설정도 준수합니다. 즉, 차트에 값이 0인 줄 또는 막대가 표시되지 않습니다. |
| **[!UICONTROL 배경]** | 막대그래프 및 조건부 서식을 포함하여, 셀에 모든 셀 서식을 표시할지 또는 숨길지를 결정합니다. |
| **[!UICONTROL 막대 그래프]** | 열에 대한 합계와 상대적인 셀 값을 나타내는 가로 막대 그래프를 표시합니다. |
| **[!UICONTROL 조건부 서식]** | 조건부 서식을 사용합니다. 아래의 [섹션](#conditional-formatting)을 참조하세요. |
| **[!UICONTROL 테이블 셀 미리 보기]** | 각 셀이 현재 선택된 서식 선택 사항이 적용되면 어떻게 나타나는지에 대한 미리보기. |
| **[!UICONTROL 비기본 속성 모델 사용]** | 기본값이 아닌 속성 모델을 사용합니다. 아래의 [섹션](#use-non-default-attribution-model)을 참조하세요. |

## 조건부 서식 {#conditional-formatting}

조건부 서식을 지정하면 정의할 수 있는 상한, 중간점 및 하한에 서식이 적용됩니다. [!UICONTROL 사용자 지정] 제한을 선택하지 않은 경우 자유 형식 테이블 내에서 조건부 서식을 적용할 수도 분류에서 자동으로 활성화됩니다.

![조건부 서식](./assets/conditional-formatting.png)

| 조건부 서식 옵션 | 설명 |
| --- | --- |
| **[!UICONTROL 사용 비율 제한]** | 절댓값이 아니라 백분율에 따라 제한 범위 변경. 백분율 제한 범위는 비율만 기반으로 한 지표(예: 바운스 비율)와 카운트와 백분율이 있는 지표(예: 페이지 보기 수)에 작동합니다. |
| **[!UICONTROL 자동 생성됨]** | 데이터를 기반으로 상한/중간/하한을 자동으로 계산. 상한은 이 열에서 가장 큰 값입니다. 하한은 가장 낮은 값이며, 중간점은 상한과 하한의 평균입니다. |
| **[!UICONTROL 사용자 정의]** | **[!UICONTROL 상한]**, **[!UICONTROL 중간점]** 및 **[!UICONTROL 하한]**&#x200B;을(를) 수동으로 할당하십시오. 제한을 통해 열 값이 양호, 평균 또는 나쁨일 때를 유연하게 결정할 수 있습니다. |
| **[!UICONTROL 조건부 서식 팔레트]** | 사전 구성된 색상 세트를 셀에 적용합니다. 사용 가능한 네 가지 색상 구성표 중 어떤 색상 구성표를 선택하느냐에 따라 서로 다른 색상이 높은 값, 중간점 값 및 낮은 값에 할당됩니다. <br> 테이블에서 차원을 바꾸면 조건부 서식 제한이 재설정됩니다. 지표를 바꾸면 해당 열에 대한 제한이 재계산됩니다 (지표는 X축에 있고 차원은 Y축에 있음). |

## 비기본 속성 모델 사용 {#use-non-default-attribution-model}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel"
>title="비기본 속성 모델 사용"
>abstract="선택한 열에 기본이 아닌 속성 모델을 사용합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel_disabled"
>title="비기본 속성 모델 사용"
>abstract="이 지표에는 기본이 아닌 속성 모델을 사용할 수 없습니다."

<!-- markdownlint-enable MD034 -->



[데이터 보기](/help/data-views/component-settings/attribution.md)에 구성된 기본 속성 모델을 재정의할 수 있습니다.

>[!NOTE]
>
>구성 요소의 속성을 기본값이 아닌 속성 모델로 업데이트할 때에는 다음 사항을 고려하십시오.
>
>* **보고서에서 *단일 차원과 함께 구성 요소를 사용하는 경우*:** 구성 요소의 속성은 기본이 아닌 속성 모델을 사용하는 경우 할당 모델을 무시합니다.
>
>* **보고서에서 구성 요소를 *여러 차원과 함께 사용하는 경우*:** 구성 요소의 속성은 기본이 아닌 속성 모델을 사용하는 경우 할당 모델을 유지합니다.
>
>   여러 차원은 [클라우드로 데이터를 내보내는](/help/analysis-workspace/export/export-cloud.md)경우에만 사용할 수 있습니다.
>
> 할당에 대한 자세한 내용은 [지속성 구성 요소 설정](/help/data-views/component-settings/persistence.md)을 참조하십시오.

Analysis Workspace에서 지표에 대해 기본값이 아닌 속성 모델을 사용하려면 다음 작업을 수행하십시오.

1. **[!UICONTROL 기본값이 아닌 속성 모델 사용]**&#x200B;을 선택합니다. 이미 선택한 경우 **[!UICONTROL 편집]**&#x200B;을(를) 사용하여 속성 모델을 편집하십시오. 또는 선택을 해제하여 기본 속성 모델로 돌아갑니다.

   ![데이터 설정 옵션을 강조 표시하는 열 설정 옵션: 기본이 아닌 속성 모드를 사용하십시오.](assets/attribution-checkbox.png)

2. **[!UICONTROL 열 속성 모델]**&#x200B;에서 **[!UICONTROL 모델]** 및 **[!UICONTROL 전환 확인 기간]**&#x200B;을 선택하세요. 전환 확인 기간은 각 전환에 적용되는 데이터 속성 기간을 결정합니다.

   ![선형을 표시하는 열 기여도 분석 모델 옵션입니다.](assets/attribution-select.png)


### 속성 모델

{{attribution-models-details}}

### 전환 확인 기간

{{attribution-lookback-window}}



>[!MORELIKETHIS]
>
>* [데이터 소스 관리](/help/analysis-workspace/visualizations/t-sync-visualization.md)
