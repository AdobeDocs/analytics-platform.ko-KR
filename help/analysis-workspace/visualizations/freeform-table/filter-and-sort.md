---
description: Analysis Workspace에서 테이블을 필터링하고 정렬하는 방법에 대해 설명하는 설명서입니다.
title: 테이블 필터링 및 정렬
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 99%

---

# 자유 형식 테이블 필터링 및 정렬

Analysis Workspace의 자유 형식 테이블은 대화형 데이터 분석을 위한 기반입니다. 그에 따라 자유 형식 테이블은 수천 개의 정보 행을 포함할 수 있습니다. 데이터를 필터링하고 정렬하는 것은 가장 중요한 정보를 효율적으로 표시하는 데 필수적인 부분이 될 수 있습니다.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## 테이블 필터링

Analysis Workspace의 필터는 가장 중요한 정보를 표시하는 데 도움이 됩니다.

>[!NOTE]
>
> 이 섹션에 설명된 대로 동적 차원 항목만 필터링할 수 있습니다. 정적 차원 항목은 필터링할 수 없습니다. 자세한 내용은 [자유 형식 테이블의 동적 차원 항목과 정적 차원 항목](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)을 참조하십시오.

여러 가지 방법을 사용하여 자유 형식 테이블에서 행을 필터링할 수 있습니다.

- 테이블에서 특정 행 제외
- 테이블에 필터 적용
- 대상자 필터 사용

각 방법이 [자유 형식 테이블 합계](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)에 어떤 영향을 미치는지 꼭 읽어보시기 바랍니다.

### 테이블에서 특정 행 제외

![필터](/help/assets/icons/Filter.svg) **[!UICONTROL 필터]**&#x200B;를 사용하지 않고도 테이블에서 특정 행을 빠르게 제외할 수 있습니다.

>[!NOTE]
>
>이 섹션에 설명된 대로 행을 제외하면 [!UICONTROL 항상 항목 제외] 규칙이 [!UICONTROL 고급] 필터 대화 상자에 자동으로 추가됩니다. ![필터](/help/assets/icons/Filter.svg) 필터 아이콘을 선택한 다음 [**[!UICONTROL 고급 표시]**](#apply-a-simple-or-advanced-filter-to-a-table)를 선택하면 적용된 규칙을 볼 수 있습니다.

자유 형식 테이블에서 특정 행을 제외하는 방법:

1. 제외하려는 행 위에 마우스를 가져다 대고 ![닫기](/help/assets/icons/Close.svg)를 선택합니다.

   ***Shift*** 키를 누른 채로 여러 행을 선택하거나 ***cmd*** 키(Mac) 또는 ***ctrl*** 키(Windows)를 눌러 여러 행을 선택합니다.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### 테이블에 간단한 필터나 고급 필터 적용

자유 형식 테이블에서 데이터를 필터링하려면 다음 작업을 수행하십시오.

1. 필터링하려는 데이터가 포함된 열 위로 마우스를 가져다 댑니다. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. ![필터](/help/assets/icons/Filter.svg) **필터**&#x200B;가 나타나면 선택합니다.

   ![필터 아이콘을 강조 표시한 자유 형식 테이블.](assets/table-filter-icon.png)

   **[!UICONTROL 검색]** 대화 상자에서 사용할 수 있는 옵션은 다음과 같습니다.

   ![단순 필터](assets/filter-simple.png){width="500"}

   | 옵션 | 함수 |
   |---------|----------|
   | [!UICONTROL **“값 없음” 포함**] | 선택한 차원에 대해 값이 없는 데이터에 대해 테이블에 **[!UICONTROL 값 없음]** 행을 표시하려면 이 옵션을 선택합니다. **[!UICONTROL 값 없음]** 행을 숨기려면 이 옵션의 선택을 취소합니다. |
   | [!UICONTROL **단어 또는 구문 검색**] | 필터링할 단어나 구문을 지정합니다. 지정한 단어 또는 정확한 구문을 포함하는 행만 표시됩니다. |


1. (선택 사항) 다른 기준 또는 여러 기준으로 필터링하려면 [!UICONTROL **고급 설정 표시**]&#x200B;를 선택합니다.

   다음과 같은 고급 필터 옵션을 사용할 수 있습니다.

   ![단순 필터](assets/filter-advanced.png){width=500}

   | 옵션 | 함수 |
   |---------|----------|
   | [!UICONTROL **“값 없음” 포함**] | 선택한 차원에 대해 값이 없는 데이터에 대해 테이블에 **[!UICONTROL 값 없음]** 행을 표시하려면 이 옵션을 선택합니다. **[!UICONTROL 값 없음]** 행을 숨기려면 이 옵션의 선택을 취소합니다. |
   | [!UICONTROL **일치**] | 지정한 모든 기준을 충족하는 데이터만 표시하려면 [!UICONTROL **모든 기준이 충족되는 경우**]&#x200B;를 선택합니다. 이 옵션은 일반적으로 더 세분화된 데이터를 보여 줍니다.<br/><br/>지정한 필터 조건 중 하나 이상을 충족하는 데이터만 표시하려면 [!UICONTROL **하나 이상의 조건이 충족되는 경우**]&#x200B;를 선택합니다. 이 옵션은 일반적으로 덜 세분화된 데이터를 보여 줍니다. |
   | [!UICONTROL **기준**] | 다음 필터 옵션 중 선택합니다.<br/><ul><li>[!UICONTROL **구문 포함**] (기본): 지정한 정확한 구문을 포함하는 데이터만 필터링된 결과에 포함됩니다. 단어는 [!UICONTROL **단어 또는 구문 검색 필드**]&#x200B;에 지정된 순서를 따라야 합니다.</li><li>[!UICONTROL **검색어를 하나라도 포함**]: 지정한 구문에서 하나 이상의 단어를 포함하는 데이터만 필터링된 결과에 포함됩니다. </li><li>[!UICONTROL **모든 검색어 포함**]: 지정한 구문의 모든 단어를 포함하는 데이터만 필터링된 결과에 포함됩니다. 단어는 [!UICONTROL **단어 또는 구문 검색 필드**]&#x200B;에 지정된 순서를 따르지 않아도 됩니다.</li><li>[!UICONTROL **검색어 포함 안 함**]: 지정한 구문의 단어를 포함하지 않는 데이터만 필터링된 결과에 포함됩니다. </li><li>[!UICONTROL **구문 포함 안 함**]: 지정한 구문을 포함하지 않는 데이터만 필터링된 결과에 포함됩니다. 단어는 [!UICONTROL **단어 또는 구문 검색 필드**]&#x200B;에 지정된 순서를 따라야 합니다.</li><li>[!UICONTROL **같음**]: 지정한 구문과 정확히 일치하는 데이터만 필터링된 결과에 포함됩니다. </li><li>[!UICONTROL **같지 않음**]: 지정한 구문과 정확히 일치하지 않는 데이터만 필터링된 결과에 포함됩니다. </li><li>[!UICONTROL **다음으로 시작**]: 지정한 단어 또는 정확한 구문으로 시작하는 데이터만 필터링된 결과에 포함됩니다. </li><li>[!UICONTROL **다음으로 끝남**]: 지정한 단어 또는 정확한 구문으로 끝나는 데이터만 필터링된 결과에 포함됩니다. </li></ul>여러 필터 조건을 추가하려면 ![추가](/help/assets/icons/Add.svg) [!UICONTROL **행 추가**]&#x200B;를 선택합니다. [!UICONTROL **일치**]&#x200B;에 대해 선택한 옵션은 **[!UICONTROL 모든 조건이 충족되는 경우]** 또는 **[!UICONTROL 임의의 조건이 충족되는 경우]**&#x200B;를 결정합니다. |
   | [!UICONTROL **항상 항목 제외**] | 필터링된 데이터에서 제외하려는 항목의 이름을 지정합니다. |

1. **[!UICONTROL 적용]**&#x200B;을 선택하여 데이터를 필터링합니다. **[!UICONTROL 지우기]**&#x200B;를 선택하여 입력을 모두 지웁니다. **[!UICONTROL 취소]**&#x200B;를 선택하여 취소하고 대화 상자를 닫습니다. <br/>색상이 지정된 ![필터](/help/assets/icons/FilterColored.svg) **필터** 아이콘은 필터가 테이블에 적용될 때 세부 정보를 표시합니다.

### 대상 세그먼트 사용

자세한 내용은 [필터 개요](/help/components/filters/filters-overview.md)를 참조하십시오.

## 테이블 정렬

Analysis Workspace의 차원 또는 지표 열을 기준으로 자유 형식 테이블의 데이터를 정렬할 수 있습니다. 화살표는 데이터가 정렬되는 방식을 나타냅니다(내림차순의 경우 **↓** 오름차순의 경우 **↑**).

![정렬](assets/sorting.gif)
