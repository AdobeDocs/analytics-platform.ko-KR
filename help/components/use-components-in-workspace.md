---
description: Analysis Workspace에서 프로젝트에 구성 요소를 추가하는 방법을 알아봅니다
title: Analysis Workspace의 구성 요소 사용
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 7%

---

# Analysis Workspace의 구성 요소 사용

구성 요소는 Analysis Workspace에서 프로젝트의 실제 데이터를 구성합니다. 구성 요소는 차원, 지표, 세그먼트 및 날짜 범위로 구성됩니다. 구성 요소를 시각화 또는 패널로 드래그하여 프로젝트에 추가할 수 있습니다.

추가할 수 있는 구성 요소 유형에 대한 자세한 내용은 [구성 요소 개요](/help/components/overview.md)를 참조하십시오.

>[!TIP]
>
>각 구성 요소에 대한 자세한 내용은 ![InfoOutline](/help/assets/icons/InfoOutline.svg)을(를) 사용하십시오. 자세한 내용은 [구성 요소 정보](#component-info)를 참조하세요.

## 프로젝트에 구성 요소 추가

1. [Analysis Workspace에서 프로젝트를 만듭니다](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Analysis Workspace의 프로젝트에 패널을 추가](/help/analysis-workspace/c-panels/panels.md#create-a-panel) 또는 [시각화를 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)합니다. 빈 프로젝트에 구성 요소를 추가하는 경우 자유 형식 테이블 시각화가 이미 생성됩니다.

1. 단추 패널에서 ![조정](/help/assets/icons/Curate.svg) **[!UICONTROL 구성 요소]**&#x200B;를 선택합니다. 왼쪽 패널에 사용 가능한 모든 구성 요소가 표시됩니다. 자세한 내용은 [인터페이스](/help/analysis-workspace/home.md#interface)를 참조하세요.

1. 추가할 구성 요소로 스크롤하거나 구성 요소를 검색한 다음 프로젝트 내의 패널이나 시각화로 드래그합니다.

1. 원할 경우 구성 요소를 패널 헤더의 세그먼트 드롭 영역으로 드래그할 수 있습니다. 이 드래그 앤 드롭은 구성 요소를 세그먼트로 정의하고 세그먼트를 패널 내의 모든 콘텐츠에 적용합니다.
패널의 세그먼트 드롭 영역을 사용하여 패널을 세그먼트화하는 방법에 대한 자세한 내용은 [패널 개요](/help/analysis-workspace/c-panels/panels.md)의 [드롭 영역](/help/analysis-workspace/c-panels/panels.md#drop-zone)을 참조하십시오.

1. 자세한 내용은 다음 섹션을 참조하십시오.

   * [프로젝트에 차원 추가](#add-dimensions-to-a-project)

   * [프로젝트에 지표 추가](#add-metrics-to-a-project)

   * [프로젝트에 세그먼트 추가](#add-segments-to-a-project)

   * [프로젝트에 날짜 범위 추가](#add-date-ranges-to-a-project)

### 프로젝트에 차원 추가

[차원](/help/components/dimensions/overview.md)은(는) 일반적으로 문자열 값을 포함하는 Customer Journey Analytics의 변수입니다. 반면에, [지표](/help/components/calc-metrics/calc-metr-overview.md)는 차원에 연결된 숫자 값을 포함합니다. 기본 보고서는 숫자 값 (지표) 열에 대해 문자열 값 (차원) 행을 보여 줍니다.

1. [프로젝트에 구성 요소 추가](#add-components-to-a-project)에 설명된 대로 Analysis Workspace에서 프로젝트에 차원을 추가하기 시작합니다.

1. 다음 방법 중 하나를 선택하여 차원을 추가하고 분석할 데이터 유형을 결정합니다.

   ![차원 추가](/help/components/assets/add-dimension.gif)

   * Analysis Workspace의 시각화 (예: 자유 형식 테이블)로 차원을 드래그합니다.

   * [프로젝트에 세그먼트 추가](#add-filters-to-a-project)에 설명된 대로 왼쪽 패널에서 세그먼트 드롭 영역으로 차원을 하나 이상 드래그하여 빠른 세그먼트를 만듭니다.

1. Analysis Workspace에서 차원 및 차원 항목을 다른 구성 요소와 선택적으로 분류할 수 있습니다. 자세한 내용은 [Workspace에서 차원 분류](/help/components/dimensions/t-breakdown-fa.md)를 참조하십시오.

Analysis Workspace에서 차원을 사용하는 방법에 대한 자세한 내용은 [차원 미리 보기](/help/components/dimensions/view-dimensions.md), [차원 분류](/help/components/dimensions/t-breakdown-fa.md) 및 [시간 분할 차원](/help/components/dimensions/time-parting-dimensions.md)을 참조하십시오.

### 프로젝트에 지표 추가

지표를 사용하면 Analysis Workspace에서 데이터 포인트를 수량화할 수 있습니다. 이들은 일반적으로 시각화에서 열로 사용되며 차원에 연결됩니다.

Analysis Workspace에서 프로젝트에 지표를 추가하려면 다음을 수행하십시오.

1. [프로젝트에 구성 요소 추가](#add-components-to-a-project)에 설명된 대로 Analysis Workspace에서 프로젝트에 지표를 추가하기 시작합니다.



1. 다음 방법 중 하나를 선택하여 Analysis Workspace에서 지표를 추가합니다.

   ![지표 추가](/help/components/assets/add-metric.gif)

   * 프로젝트의 날짜 기간 동안 지표가 트렌드를 표시되게 하려면 빈 자유 형식 테이블의 지표 드롭 영역으로 지표를 드래그합니다.

   * 차원이 있을 때 지표를 드래그하여 각 차원 항목에 대한 해당 지표를 확인합니다.

   * 기존 지표 헤더 위로 지표를 드래그하여 대체합니다.

   * 기존 지표 헤더의 왼쪽 옆에 있는 지표를 드래그하여 새 지표를 추가합니다.

   * 기존 지표 헤더의 위 또는 아래에 지표를 끌어 놓아 지표 겹침을 만듭니다.


지표에 대한 자세한 내용은 [지표](/help/components/apply-create-metrics.md)를 참조하십시오.

### 프로젝트에 세그먼트 추가

[세그먼트](/help/components/filters/filters-overview.md)를 사용하면 특성이나 특정 상호 작용에 따라 개인, 세션 또는 이벤트의 하위 집합을 식별할 수 있습니다.

다음 방법 중 하나로 Analysis Workspace의 세그먼트를 사용할 수 있습니다.

* 패널에 세그먼트 추가
패널에 세그먼트를 추가하면 세그먼트가 패널 내의 모든 컨텐츠에 적용됩니다.
패널의 세그먼트 드롭 영역을 사용하여 패널을 세그먼트화하는 방법에 대한 자세한 내용은 [패널 개요](/help/analysis-workspace/c-panels/panels.md)의 [드롭 영역](/help/analysis-workspace/c-panels/panels.md#drop-zone)을 참조하십시오.

* 시각화에 세그먼트 추가
자유 형식 테이블의 열에 세그먼트를 추가하면 해당 세그먼트는 테이블 열 내의 모든 컨텐츠에 적용됩니다. 폴아웃 시각화의 일부로 세그먼트를 추가할 수도 있습니다.

* 구성 요소에서 세그먼트 사용
[계산된 지표](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), [주석](/help/components/annotations/create-annotations.md#annotation-builder) 또는 [세그먼트](/help/components/filters/filter-builder.md)와 같은 구성 요소를 정의할 때 세그먼트를 정의의 일부로 사용할 수 있습니다.


### 프로젝트에 날짜 범위 추가

[날짜 범위](/help/components/date-ranges/overview.md)는 Analysis Workspace에서 보고 기간을 결정하며, 프로젝트 내의 하나 이상의 패널과 일부 시각화(예: 자유 형식 테이블)에 적용할 수도 있습니다.

각 패널에는 기본적으로 날짜 범위가 포함되어 있습니다. 패널의 날짜 범위를 업데이트하는 방법에는 여러 가지가 있습니다. Analysis Workspace에서 패널의 날짜 범위를 업데이트하는 한 가지 방법은 왼쪽 패널에서 날짜 범위 구성 요소를 드래그하는 것입니다.

1. [프로젝트에 구성 요소 추가](#add-components-to-a-project)에 설명된 대로 Analysis Workspace에서 프로젝트에 날짜 범위를 추가합니다.

1. 왼쪽 패널의 날짜 범위를 다음으로 끌어서 놓습니다.

   * 패널의 날짜 범위를 수정하려면 현재 날짜 범위를 선택합니다.

     ![날짜 범위를 삭제합니다](assets/add-date-range.gif)

   * 자유 형식 테이블 시각화의 지표 또는 차원입니다. 자세한 내용은 [날짜 범위 사용](/help/components/date-ranges/overview.md#use-date-ranges)을 참조하세요.

Analysis Workspace에서 날짜 범위를 사용하고 관리하는 방법에 대한 자세한 내용은 [날짜 범위 개요](/help/components/date-ranges/overview.md)를 참조하십시오.

## 구성 요소 정보

구성 요소 위로 마우스를 가져가면 ![추가 정보](/help/assets/icons/InfoOutline.svg)를 표시할 수 있습니다. 선택하면 구성 요소에 대한 추가 정보가 포함된 팝업이 표시됩니다.

![구성 요소 정보](assets/component-info.png)

액세스 제어에 따라 다음 작업을 수행할 수 있습니다.

* 구성 요소에 대한 ![책갈피](/help/assets/icons/Bookmark.svg) [!UICONTROL 데이터 사전] 정의에 액세스합니다.
* 구성 요소가 정의된 ![편집](/help/assets/icons/Edit.svg) 구성 요소 빌더 또는 데이터 보기에 액세스합니다.
