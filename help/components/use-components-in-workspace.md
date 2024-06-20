---
description: Analysis Workspace에서 프로젝트에 구성 요소를 추가하는 방법을 알아봅니다
title: Analysis Workspace의 구성 요소 사용
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 697503bba56f44159df7a2f6a0e60a0a4178266d
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 16%

---

# Analysis Workspace의 구성 요소 사용

구성 요소는 Analysis Workspace에서 프로젝트의 실제 데이터를 구성합니다. 구성 요소는 차원, 지표, 필터 및 날짜 범위로 구성됩니다. 구성 요소를 시각화 또는 패널로 드래그하여 프로젝트에 추가할 수 있습니다.

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

1. 추가하려는 구성 요소를 스크롤하거나 검색한 다음, 프로젝트 내의 패널이나 시각화로 드래그합니다.

1. (선택 사항) 구성 요소를 패널 헤더의 필터 드롭 영역으로 드래그합니다.

   필터는 패널 내의 모든 콘텐츠에 적용됩니다.

   패널의 필터 드롭 영역을 사용하여 패널을 필터링하는 방법에 대한 자세한 내용은 [놓기 영역](/help/analysis-workspace/c-panels/panels.md#drop-zone) 위치: [패널 개요](/help/analysis-workspace/c-panels/panels.md).

   ![드롭 영역에 필터를 드래그합니다.](assets/filter-dropzone.png)

1. 자세한 내용을 보려면 추가하는 구성 요소 유형에 따라 다음 섹션 중 하나를 계속 진행하십시오.

   * [프로젝트에 차원 추가](#add-dimensions-to-a-project)

   * [프로젝트에 지표 추가](#add-metrics-to-a-project)

   * [프로젝트에 필터 추가](#add-filters-to-a-project)

   * [프로젝트에 날짜 범위 추가](#add-date-ranges-to-a-project)

## 프로젝트에 차원 추가

[Dimension](/help/components/dimensions/overview.md) 는 일반적으로 문자열 값을 포함하는 Adobe Analytics의 변수입니다. 반면에, [지표](/help/components/calc-metrics/calc-metr-overview.md)는 차원에 연결된 숫자 값을 포함합니다. 기본 보고서는 숫자 값 (지표) 열에 대해 문자열 값 (차원) 행을 보여 줍니다.

1. 에 설명된 대로 Analysis Workspace에서 프로젝트에 차원을 추가합니다. [프로젝트에 구성 요소 추가 시작](#begin-adding-components-to-a-project).

1. 다음 방법 중 하나를 선택하여 차원을 추가하고 분석할 데이터 유형을 결정합니다.

   * Analysis Workspace의 시각화 (예: 자유 형식 테이블)로 차원을 드래그합니다.

     ![프로젝트에 차원 추가](assets/add-dimensions.png)

   * 에 설명된 대로 임시 필터를 생성하려면 왼쪽 레일에서 필터 드롭 영역으로 차원을 하나 이상 드래그합니다 [프로젝트에 필터 추가](#add-filters-to-a-project).

1. (선택 사항) 다른 구성 요소와 함께 Analysis Workspace에서 차원 및 차원 항목을 분류할 수 있습니다.

   자세한 내용은 [작업 영역에서 차원 분류](/help/components/dimensions/t-breakdown-fa.md).

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

다음 방법 중 하나로 Analysis Workspace에서 필터를 사용할 수 있습니다.

### 패널에 필터 추가

패널에 필터를 추가하면 필터가 패널 내의 모든 컨텐츠에 적용됩니다.

패널의 필터 드롭 영역을 사용하여 패널을 필터링하는 방법에 대한 자세한 내용은 [놓기 영역](/help/analysis-workspace/c-panels/panels.md#drop-zone) 위치: [패널 개요](/help/analysis-workspace/c-panels/panels.md).

### 자유 형식 테이블의 열에 필터 추가

자유 형식 테이블의 열에 필터를 추가하면 해당 필터가 테이블 열 내의 모든 컨텐츠에 적용됩니다.

### 계산된 지표를 만들 때 필터 사용

계산된 지표 빌더에서는 지표 정의 내에서 필터를 적용할 수 있습니다.

자세한 내용은 [필터링된 지표](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md).

## 프로젝트에 날짜 범위 추가

[날짜 범위](/help/components/date-ranges/custom-date-ranges.md) Analysis Workspace에서 보고 기간을 결정하며 프로젝트 내의 하나 이상의 패널에 적용할 수 있습니다.

각 패널에는 기본적으로 날짜 범위가 포함되어 있습니다. 패널의 날짜 범위를 업데이트하는 방법에는 여러 가지가 있습니다. Analysis Workspace에서 패널의 날짜 범위를 업데이트하는 한 가지 방법은 왼쪽 레일에서 날짜 범위 구성 요소를 드래그하는 것입니다.

1. 에 설명된 대로 Analysis Workspace에서 프로젝트에 날짜 범위를 추가하기 시작합니다. [프로젝트에 구성 요소 추가 시작](#begin-adding-components-to-a-project).

1. 날짜 범위를 왼쪽 레일에서 패널의 오른쪽 상단에 있는 현재 날짜 범위로 드래그합니다.

   ![날짜 범위 삭제](assets/daterange-drop.png)

Analysis Workspace에서 달력 및 날짜 범위를 사용하는 방법에 대한 자세한 내용은 [달력 및 날짜 범위 개요](/help/components/date-ranges/custom-date-ranges.md).
