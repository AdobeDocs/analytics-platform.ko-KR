---
description: Analysis Workspace에서 프로젝트에 구성 요소를 추가하는 방법을 알아봅니다
title: Analysis Workspace에서 구성 요소 사용
feature: Components
role: User
source-git-commit: d3f90414494b52aba9736fef83423e4a1b2508b5
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 16%

---

# Analysis Workspace에서 구성 요소 사용

구성 요소는 Analysis Workspace에서 프로젝트의 실제 데이터를 구성합니다. 구성 요소는 차원, 지표, 세그먼트 및 날짜 범위로 구성됩니다. 구성 요소를 시각화 또는 패널로 드래그하여 프로젝트에 추가할 수 있습니다.

추가할 수 있는 구성 요소 유형에 대한 개요는 를 참조하십시오. [구성 요소 개요](/help/components/overview.md).

>[!TIP]
>
>각 구성 요소에 대한 자세한 내용을 보려면 Analysis Workspace의 왼쪽 레일에서 구성 요소 이름 옆에 있는 정보 아이콘을 선택하십시오.

## 프로젝트에 구성 요소 추가 시작

1. [Analysis Workspace에서 프로젝트 만들기](/help/analysis-workspace/build-workspace-project/create-projects.md) 아직 안왔으면

1. [패널 추가](/help/analysis-workspace/c-panels/panels.md) 또는 [시각화 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) Analysis Workspace의 프로젝트에 연결합니다.

   빈 프로젝트에 구성 요소를 추가하면 자유 형식 테이블 시각화가 자동으로 만들어집니다.

1. 왼쪽 레일에서 **[!UICONTROL 구성 요소]** 아이콘을 선택합니다.

   ![](assets/build-components.png)

1. 추가할 구성 요소로 스크롤하거나 구성 요소를 검색한 다음 프로젝트 내의 패널이나 시각화로 드래그합니다.

   예를 들어 세그먼트를 패널 헤더의 세그먼트 드롭 영역으로 드래그할 수 있습니다.

   ![드롭 영역에 세그먼트 드롭](assets/filter-dropzone.png)

1. 자세한 내용을 보려면 추가하는 구성 요소 유형에 따라 다음 섹션 중 하나를 계속 진행하십시오.

   * [프로젝트에 차원 추가](#add-dimensions-to-a-project)

   * [프로젝트에 지표 추가](#add-metrics-to-a-project)

   * [프로젝트에 세그먼트 추가](#add-segments-to-a-project)

   * [프로젝트에 날짜 범위 추가](#add-date-ranges-to-a-project)

## 프로젝트에 차원 추가

[Dimension](/help/components/dimensions/overview.md) 는 일반적으로 문자열 값을 포함하는 Adobe Analytics의 변수입니다. 반면에, [지표](/help/components/calc-metrics/calc-metr-overview.md)는 차원에 연결된 숫자 값을 포함합니다. 기본 보고서는 숫자 값 (지표) 열에 대해 문자열 값 (차원) 행을 보여 줍니다.

1. 에 설명된 대로 Analysis Workspace에서 프로젝트에 차원을 추가합니다. [프로젝트에 구성 요소 추가 시작](#begin-adding-components-to-a-project).

1. 다음 방법 중 하나를 선택하여 차원을 추가하고 분석할 데이터 유형을 결정합니다.

   * Analysis Workspace의 시각화 (예: 자유 형식 테이블)로 차원을 드래그합니다.

     ![프로젝트에 차원 추가](assets/add-dimensions.png)

   * 에 설명된 대로 왼쪽 레일에서 세그먼트 드롭 영역으로 하나 이상의 차원을 드래그하여 임시 세그먼트를 만듭니다. [프로젝트에 세그먼트 추가](#add-segments-to-a-project).

Analysis Workspace에서 차원을 사용하는 방법에 대한 자세한 내용은 [차원 미리 보기](/help/components/dimensions/view-dimensions.md), [차원 분류](/help/components/dimensions/t-breakdown-fa.md), 및 [차원 시간 분할](/help/components/dimensions/time-parting-dimensions.md).

## 프로젝트에 지표 추가

지표를 사용하면 Analysis Workspace에서 데이터 포인트를 수량화할 수 있습니다. 이들은 일반적으로 시각화에서 열로 사용되며 차원에 연결됩니다.

Analysis Workspace에서 프로젝트에 지표를 추가하려면 다음을 수행하십시오.

1. 에 설명된 대로 Analysis Workspace에서 프로젝트에 지표 추가를 시작합니다. [프로젝트에 구성 요소 추가 시작](#begin-adding-components-to-a-project).

1. 다음 방법 중 하나를 선택하여 Analysis Workspace에서 지표를 추가합니다.

   * 프로젝트의 날짜 기간 동안 지표가 트렌드를 표시되게 하려면 빈 자유 형식 테이블의 지표 드롭 영역으로 지표를 드래그합니다.

     ![프로젝트에 지표 추가](assets/add-metrics.png)

   * 해당 지표를 각 차원 항목과 비교하여 보려면 차원이 존재할 때 지표를 드래그하십시오.

   * 기존 지표 헤더 위로 지표를 드래그하여 대체합니다.

   * 지표를 헤더 옆으로 드래그하면 두 지표를 나란히 볼 수 있습니다.

지표에 대한 자세한 내용은 [계산된 지표 개요](/help/components/calc-metrics/calc-metr-overview.md).

## 프로젝트에 필터 추가

[필터](/help/components/filters/filters-overview.md) 특성 또는 특정 상호 작용에 따라 방문자 하위 집합을 식별할 수 있습니다.

Analysis Workspace에서 프로젝트에 필터를 추가하려면 다음을 수행하십시오.

1. 에 설명된 대로 Analysis Workspace에서 프로젝트에 필터 추가를 시작합니다. [프로젝트에 구성 요소 추가 시작](#begin-adding-components-to-a-project).

1. 다음 방법 중 하나를 선택하여 패널 필터링을 시작합니다.

   * 개별 필터를 왼쪽 레일에서 세그먼트 드롭 영역으로 드래그합니다.

     ![드롭 영역에 필터 드롭](assets/filter-dropzone.png)

   * Shift 또는 Ctrl 키를 누른 상태로 왼쪽 레일에서 여러 세그먼트를 선택한 다음 Shift 키를 누른 상태로 세그먼트를 세그먼트 드롭 영역에 드롭합니다.

     ![드롭 영역에 여러 필터 드롭](assets/filter-dropzone-multiple.png)

     이렇게 하면 패널 사용자가 적용할 필터를 선택할 수 있는 드롭다운 메뉴가 만들어집니다. 드롭다운 메뉴에는 [!UICONTROL **필터 없음**] 사용자가 선택할 수 있는 옵션이며, 이로 인해 패널이 필터링되지 않습니다.

     (x)를 선택하여 드롭다운 메뉴에서 모든 옵션을 제거할 수 있습니다. 를 제거하면 [!UICONTROL **필터 없음**] 옵션을 설정한 경우 필터가 필요합니다.

   * 세그먼트가 아닌 구성 요소를 드롭 영역으로 드래그하여 임시 세그먼트를 만듭니다. 이렇게 하면 세그먼트 빌더로 이동하는 데 드는 시간과 노력을 절약할 수 있습니다. 이러한 방식으로 생성된 세그먼트는 자동으로 히트 수준 세그먼트로 정의됩니다. 이 정의는 세그먼트 옆에 있는 정보 아이콘(i)을 클릭한 다음 연필 모양의 편집 아이콘을 클릭하고 세그먼트 빌더에서 편집하여 수정할 수 있습니다.

     애드혹 세그먼트는 빠른 세그먼트의 한 종류이며 프로젝트에 로컬입니다. 공개로 설정하지 않으면 왼쪽 레일에 표시되지 않습니다.

     자세한 내용은 [빠른 필터](/help/components/filters/quick-filters.md)를 참조하십시오.

패널의 세그먼트 드롭 영역을 사용하여 패널을 필터링하는 방법에 대한 자세한 내용은 [놓기 영역](/help/analysis-workspace/c-panels/panels.md#drop-zone) 위치: [패널 개요](/help/analysis-workspace/c-panels/panels.md).

## 프로젝트에 날짜 범위 추가

[날짜 범위](/help/components/date-ranges/custom-date-ranges.md) Analysis Workspace에서 보고 기간을 결정하며 프로젝트 내의 하나 이상의 패널에 적용할 수 있습니다.

각 패널에는 기본적으로 날짜 범위가 포함되어 있습니다. 패널의 날짜 범위를 업데이트하는 방법에는 여러 가지가 있습니다. Analysis Workspace에서 패널의 날짜 범위를 업데이트하는 한 가지 방법은 왼쪽 레일에서 날짜 범위 구성 요소를 드래그하는 것입니다.

1. 에 설명된 대로 Analysis Workspace에서 프로젝트에 날짜 범위를 추가하기 시작합니다. [프로젝트에 구성 요소 추가 시작](#begin-adding-components-to-a-project).

1. 날짜 범위를 왼쪽 레일에서 패널의 오른쪽 상단에 있는 현재 날짜 범위로 드래그합니다.

   ![날짜 범위 삭제](assets/daterange-drop.png)

Analysis Workspace에서 달력 및 날짜 범위를 사용하는 방법에 대한 자세한 내용은 [달력 및 날짜 범위 개요](/help/components/date-ranges/custom-date-ranges.md).
