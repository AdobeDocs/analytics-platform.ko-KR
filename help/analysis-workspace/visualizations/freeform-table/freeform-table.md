---
title: 자유 형식 테이블 개요
description: 자유 형식 테이블은 Analysis Workspace에서 데이터를 분석하는 기반입니다.
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: 141c95b23695c09dd194c61c7cef0ce34e05ac33
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 27%

---

# 자유 형식 테이블 개요 {#freeform-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="자유 형식 테이블"
>abstract="차원, 세그먼트, 지표 및 날짜 범위를 사용하여 작성할 수 있는 빈 자유 형식 테이블 시각화를 만듭니다. 자유 형식 테이블을 다른 시각화의 기반으로 사용할 수 있습니다."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_이 문서에서는 자유 형식 테이블 시각화에 대해_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;을(를) 설명합니다._<br/>_이 문서의 ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)_**Adobe Analytics**버전에 대한 [자유 형식 테이블](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table)을 참조하세요.__

>[!ENDSHADEBOX]


Analysis Workspace에서 ![테이블](/help/assets/icons/Table.svg) **[!UICONTROL 자유 형식 테이블]** 시각화는 대화형 데이터 분석의 기반입니다. [구성 요소](/help/components/overview.md) 조합을 행과 열로 끌어다 놓아 분석에 사용할 사용자 정의 테이블을 만들 수 있습니다. 각 구성 요소가 삭제되면 테이블이 즉시 업데이트되므로 빠르고 더 깊이 분석할 수 있습니다.

![여러 웹 페이지에 대한 방문 및 온라인 주문을 포함하여 행과 열의 구성 요소를 표시하는 자유 형식 테이블.](assets/opening-section.png)

[!UICONTROL 자유 형식 테이블]을 만들고 구성하려면:

* ![테이블](/help/assets/icons/Table.svg) **[!UICONTROL 자유 형식 테이블]** 시각화를 추가합니다. [패널에 시각화 추가](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)를 참조하십시오.

## 자동화된 테이블

테이블을 만드는 가장 빠른 방법은 구성 요소를 빈 프로젝트, 패널 또는 자유 형식 테이블에 직접 놓는 것입니다. 자유 형식 테이블은 권장 형식으로 작성됩니다. [튜토리얼을 확인하십시오](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace).

![방문 구성 요소가 있는 새 패널이 작업 공간으로 드롭되었습니다.](assets/automated-table.png)

## 자유 형식 테이블 빌더

먼저 테이블에 여러 구성 요소를 추가한 다음 데이터를 렌더링하려는 경우 **[!UICONTROL 테이블 빌더 사용]**&#x200B;을 선택할 수 있습니다. 빌더를 활성화한 상태에서 차원, 분류, 지표 및 필터를 끌어다 놓아 보다 복잡한 질문에 대한 답변을 제공하는 표를 작성할 수 있습니다. **[!UICONTROL 빌드]**&#x200B;를 선택하면 데이터가 업데이트됩니다.

![자유 형식 테이블 빌더에서 ](assets/table-builder.png)을(를) 표시

## 상호 작용

다음과 같은 다양한 방법으로 자유 형식 테이블과 상호 작용하고 사용자 정의할 수 있습니다.

### 필터링 및 정렬

* 테이블의 데이터를 [필터링 및 정렬](filter-and-sort.md)할 수 있습니다.

### 다른 결과를 표시했던

* ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg)를 사용하여 하나 이상의 행에서 빠르게 [새 시각화를 만들기](../freeform-analysis-visualizations.md#visualize)할 수 있습니다.
* 프로젝트의 [보기 밀도](/help/analysis-workspace/build-workspace-project/view-density.md)를 조정하여 더 많은 행을 단일 화면에 맞출 수 있습니다.
* 페이지 매김이 발생하기 전에 각 차원 행에 최대 400개의 행을 표시할 수 있습니다. 페이지에 더 많은 행을 표시하려면 첫 번째 열 헤더에서 **[!UICONTROL 행]** 옆의 숫자를 선택하십시오. 첫 번째 열 머리글에서 ![V자형 화살표](/help/assets/icons/ChevronRight.svg)를 사용하여 다른 페이지로 이동합니다.
* 추가 구성 요소로 행을 분류할 수 있습니다. 한 번에 여러 행을 분류하려면 여러 행을 선택한 다음 선택한 행 위로 다음 구성 요소를 드래그합니다. [분류](/help/components/dimensions/t-breakdown-fa.md)에 대해 자세히 알아보십시오.
* 행을 [필터링](/help/components/filters/filters-overview.md)하여 축소된 항목 세트를 표시할 수 있습니다. 추가 설정은 [행 설정](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)에서 사용할 수 있습니다.

### 열

* 구성 요소를 열 내에 스택하여 필터가 적용된 지표, 탭 간 분석 등을 만들 수 있습니다.
* 각 열의 보기는 [열 설정](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)에서 조정할 수 있습니다.
* [상황에 맞는 메뉴](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)를 통해 몇 가지 작업을 사용할 수 있습니다. 이 메뉴에서는 표 머리글, 행 또는 열 선택 여부에 따라 다른 작업을 제공합니다.


## 설정

![설정](/help/assets/icons/Setting.svg)을 선택하여 **[!UICONTROL 테이블 설정]**&#x200B;을 표시합니다. 다음 특정 시각화 [설정](../freeform-analysis-visualizations.md#settings)을 사용할 수 있습니다.

### 데이터 소스

| 옵션 | 설명 |
|---|---|
| **[!UICONTROL 연결된 시각화]**. | 연결된 시각화를 모두 나열합니다. |
| **[!UICONTROL 데이터 원본 표시]** | 이 옵션을 선택하지 않으면 시각화를 위한 데이터 소스로 작동하는 자유 형식 테이블이 Workspace에서 숨겨집니다. |

### 설정

| 옵션 | 설명 |
|---|---|
| **[!UICONTROL 각 열의 날짜가 같은 행에서 모두 시작하도록 맞춥니다]** | 날짜를 각 열에서 동일한 행의 시작으로 정렬하거나 정렬하지 않음. |


## 컨텍스트 메뉴

시각화 헤더에서 다음 [컨텍스트 메뉴](../freeform-analysis-visualizations.md#context-menu) 옵션을 사용할 수 있습니다.

| 옵션 | 설명 |
| --- | --- |
| **[!UICONTROL 복사된 시각화 삽입]**n | 복사한 시각화를 프로젝트 내의 다른 위치 또는 완전히 다른 프로젝트에 붙여넣기(삽입)합니다. |
| **[!UICONTROL 클립보드에 데이터 복사]** | 시각화에서 클립보드로 데이터를 복사합니다. |
| **[!UICONTROL 선택 항목을 클립보드에 복사]** | 시각화에서 클립보드로 선택 항목을 복사합니다. |
| **[!UICONTROL CSV로 항목 다운로드(*차원 이름*)]** | 시각화의 차원 항목(최대 50,000개)을 즉시 로컬 장치에 다운로드합니다. 선택한 차원에 대한 최대 50,000개의 차원 항목. |
| **[!UICONTROL 시각화 복사]** | 시각화를 복사하여 프로젝트 내의 다른 위치 또는 완전히 다른 프로젝트에 시각화를 삽입할 수 있습니다. |
| **[!UICONTROL 데이터 CSV 다운로드]** | 시각화의 표시된 데이터를 로컬 장치에 즉시 다운로드합니다. |
| **[!UICONTROL 전체 테이블 내보내기...]** | 전체 테이블을 지정된 클라우드 위치로 내보냅니다. [클라우드로 Customer Journey Analytics 보고서 내보내기](../../export/export-cloud.md)를 참조하십시오. |
| **[!UICONTROL 시각화 복제]** | 시각화의 정확한 복제본을 만듭니다. |
| **[!UICONTROL 설명 편집]** | 시각화에 대한 텍스트 설명을 추가(또는 편집)합니다. [텍스트](../text.md)를 참조하세요. |
| **[!UICONTROL 시각화 링크 가져오기]** | 시각화에 직접 링크를 복사하여 공유합니다. 링크 공유 대화 상자에 링크가 표시됩니다. 복사 를 선택하여 클립보드에 링크를 복사합니다. |
| **[!UICONTROL 시작]** | 현재 시각화에 대한 구성을 삭제하여 처음부터 다시 구성할 수 있습니다. |


>[!MORELIKETHIS]
>
>[패널 내에 시각화 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[시각화 설정](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[시각화 컨텍스트 메뉴](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
