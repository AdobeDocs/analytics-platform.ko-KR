---
description: Analysis Workspace에서 테이블을 필터링하고 정렬하는 방법에 대해 설명하는 설명서입니다.
title: 테이블 필터링 및 정렬
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: 4c96089088560da635e2499e7ec770c19c3de0ab
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 69%

---


# 자유 형식 테이블 필터링 및 정렬

Analysis Workspace의 자유 형식 테이블은 대화형 데이터 분석을 위한 기반입니다. 그에 따라 자유 형식 테이블은 수천 개의 정보 행을 포함할 수 있습니다. 데이터를 필터링하고 정렬하는 것은 가장 중요한 정보를 효율적으로 표시하는 데 필수적인 부분이 될 수 있습니다.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## 테이블 필터링

Analysis Workspace의 필터는 가장 중요한 정보를 표시하는 데 도움이 됩니다.

>[!NOTE]
>
> 이 섹션에 설명된 대로 동적 차원 항목만 필터링할 수 있습니다. 정적 차원 항목은 필터링할 수 없습니다. 자세한 내용은 [자유 형식 테이블의 동적 차원 항목과 정적 차원 항목 비교](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

## 자유 형식 테이블 행 필터링

여러 메서드를 사용하여 자유 형식 테이블에서 행을 필터링할 수 있습니다. 

- 행에서 &#39;X&#39;를 클릭합니다
- 표 필터
- 세그먼테이션

각 메서드가 어떻게 영향을 주는지 반드시 읽어 보십시오 [자유 형식 테이블 합계](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### 테이블에서 특정 행을 빠르게 제외

필터 대화 상자를 열지 않고도 테이블에서 특정 행을 빠르게 제외할 수 있습니다.

>[!NOTE]
>
>이 섹션에 설명된 대로 행을 제외하는 경우 [!UICONTROL **항상 항목 제외**] 고급 필터 대화 상자에서 규칙이 자동으로 적용됩니다. ( 필터 아이콘을 선택한 다음, [**[!UICONTROL 고급 표시]**](#apply-a-simple-or-advanced-filter-to-a-table).)

자유 형식 테이블에서 특정 행을 빠르게 제외하려면 다음을 수행합니다.

1. 제외할 행을 마우스로 가리킨 다음 x 아이콘을 선택합니다.

   Shift 키를 누른 상태로 행 범위를 선택하거나 Command 키(Mac) 또는 Ctrl 키(Windows)를 누른 상태로 여러 행을 선택합니다.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### 표에 단순 또는 고급 필터 적용

자유 형식 테이블에서 데이터를 필터링하려면 다음 작업을 수행하십시오.

1. 필터링할 데이터가 포함된 열 위로 마우스를 가져갑니다. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. **필터** 아이콘이 나타나면 선택합니다.

   ![필터 아이콘을 강조 표시하는 자유 형식 테이블입니다.](assets/table-filter-icon.png)

   다음 옵션을 사용할 수 있습니다.

   | 옵션 | 함수 |
   |---------|----------|
   | [!UICONTROL **단어 또는 구 검색**] | 필터링 기준으로 사용할 단어나 구를 지정합니다. 지정한 단어 또는 정확한 구문을 포함하는 행만 표시됩니다. |
   | [!UICONTROL **지정하지 않은 항목 포함(없음)**] | 테이블 차원에 속하지 않는 데이터를 테이블에 표시하려면 이 옵션을 선택합니다. <!--what is this?--> |

1. (선택 사항) 다른 기준 또는 여러 기준으로 필터링하려면 [!UICONTROL **고급 설정 표시**]&#x200B;를 선택합니다.

   다음 고급 필터 옵션을 사용할 수 있습니다.

   | 옵션 | 함수 |
   |---------|----------|
   | [!UICONTROL **지정하지 않은 항목 포함(없음)**] | 테이블 차원에 속하지 않는 데이터를 테이블에 표시하려면 이 옵션을 선택합니다. <!--what is this?--> |
   | [!UICONTROL **일치**] | <p>지정한 모든 기준을 충족하는 데이터만 표시하려면 [!UICONTROL **모든 기준이 충족되는 경우**]&#x200B;를 선택합니다. 이 옵션은 일반적으로 더 세분화된 데이터를 보여 줍니다.</p> <p>지정한 필터 기준 중 하나 이상을 충족하는 데이터만 표시하려면 [!UICONTROL **하나 이상의 기준이 충족되는 경우**]&#x200B;를 선택합니다. 이 옵션은 일반적으로 덜 세분화된 데이터를 보여 줍니다.</p> |
   | [!UICONTROL **기준**] | <p>다음 필터 옵션 중 선택합니다.</p><p>(여러 필터 기준을 추가하려면 [!UICONTROL **행 추가**]&#x200B;를 선택합니다. [!UICONTROL **일치**] 섹션에서 선택하는 옵션에 따라 추가하는 모든 기준이 충족되어야 하는지 또는 일부 기준만 충족되어도 되는지 여부가 결정됩니다.)</p><ul><li><p>[!UICONTROL **구문 포함**]: 지정한 정확한 구문을 포함하는 데이터만 필터링된 결과에 포함됩니다. 단어는 [!UICONTROL **단어 또는 구문 검색 필드**]&#x200B;에 지정된 순서를 따라야 합니다.<p>간단한 검색을 수행할 때 기본 설정입니다.</p></p></li><li><p>[!UICONTROL **검색어를 하나라도 포함**]: 지정한 구문에서 하나 이상의 단어를 포함하는 데이터만 필터링된 결과에 포함됩니다. </p></li><li><p>[!UICONTROL **모든 검색어 포함**]: 지정한 구문의 모든 단어를 포함하는 데이터만 필터링된 결과에 포함됩니다. 단어는 [!UICONTROL **단어 또는 구문 검색 필드**]&#x200B;에 지정된 순서를 따르지 않아도 됩니다.</p></li><li><p>[!UICONTROL **검색어 포함 안 함**]: 지정한 구문의 단어를 포함하지 않는 데이터만 필터링된 결과에 포함됩니다. </p></li><li><p>[!UICONTROL **구문 포함 안 함**]: 지정한 구문을 포함하지 않는 데이터만 필터링된 결과에 포함됩니다. 단어는 [!UICONTROL **단어 또는 구문 검색 필드**]&#x200B;에 지정된 순서를 따라야 합니다.</p></li><li><p>[!UICONTROL **같음**]: 지정한 구문과 정확히 일치하는 데이터만 필터링된 결과에 포함됩니다. </p></li><li><p>[!UICONTROL **같지 않음**]: 지정한 구문과 정확히 일치하지 않는 데이터만 필터링된 결과에 포함됩니다. </p></li><li><p>[!UICONTROL **다음으로 시작**]: 지정한 단어 또는 정확한 구문으로 시작하는 데이터만 필터링된 결과에 포함됩니다. </p></li><li><p>[!UICONTROL **다음으로 끝남**]: 지정한 단어 또는 정확한 구문으로 끝나는 데이터만 필터링된 결과에 포함됩니다. </p></li></ul> |
   | [!UICONTROL **항상 항목 제외**] | 필터링된 데이터에서 제외하려는 항목의 이름을 지정합니다. |

1. [!UICONTROL **적용**]&#x200B;을 선택하여 데이터를 필터링합니다.

   테이블에 필터가 적용되면 **필터** 아이콘(![파란색 필터 아이콘 필터링된 테이블](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg))이 파란색으로 바뀝니다.

### 필터

다음 참조: [필터링 설명서](/help/components/filters/filters-overview.md) 을 참조하십시오.

## 테이블 정렬

Analysis Workspace에서 차원 또는 지표인 열을 기준으로 자유 형식 테이블의 데이터를 정렬할 수 있습니다.

아래쪽 화살표 아이콘(![아래쪽 화살표 아이콘 정렬된 테이블 열](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg))은 데이터가 현재 정렬되는 열의 헤더에 표시됩니다.

1. Analysis Workspace의 자유 형식 테이블에서 차원 또는 지표 이름 옆에 있는 화살표를 클릭합니다.

   정렬 사용 시 다음 사항을 고려하십시오.

   - 아래쪽 화살표는 내림차순으로 정렬하고 위쪽 화살표(기본값)는 오름차순으로 정렬합니다.
   - 차원을 알파벳순 또는 숫자순으로 정렬할 수 있습니다. 예를 들어 워크플로에서 단계 번호가 매겨져 있으며, 단계 번호순으로 정렬할 수 있습니다. 날짜 관련 차원을 날짜순으로 정렬할 수 있습니다. 또는 아래 이미지와 같이 알파벳순으로 데이터 소스를 정렬할 수 있습니다.

   ![정렬 아이콘을 강조 표시하는 데이터 소스 보기.](assets/sort-dimensions.png)


