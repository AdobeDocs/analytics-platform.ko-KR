---
description: Analysis Workspace의 데이터 사전을 사용하면 용도, 승인, 중복 등의 Analysis Workspace의 다양한 구성 요소를 분류하고 추적할 수 있습니다.
title: 데이터 사전 보기
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: d431e781eb18eb3f4904094972c218a9e80980d9
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 59%

---

# 데이터 사전의 구성 요소 정보 보기

데이터 사전을 사용하면 구성 요소 설명, 유사한 구성 요소, 구성 요소가 자주 사용되는 다른 구성 요소 등 구성 요소에 대한 정보를 볼 수 있습니다.

데이터 사전의 구성 요소에 대한 정보 보기:

1. 확인할 구성 요소가 포함된 Analysis Workspace 프로젝트로 이동합니다.

1. Analysis Workspace의 왼쪽 레일에서 [!UICONTROL **데이터 사전**] 아이콘을 선택합니다. (데이터 사전에 액세스하는 다른 방법은 [데이터 사전 개요](/help/components/data-dictionary/data-dictionary-overview.md)의 “데이터 사전 액세스”에 설명되어 있음)

   데이터 사전 창이 표시됩니다.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 보려는 구성 요소가 포함된 데이터 보기가 드롭다운 메뉴에서 선택되었는지 확인합니다. 기본적으로 이미 있는 데이터 보기가 표시됩니다.

1. (선택 사항) 검색 필드에서 확인하려는 구성 요소의 이름을 입력하기 시작합니다.

   구성 요소 유형은 색상과 아이콘을 모두 사용하여 식별할 수 있습니다. **Dimension** ![Dimension 아이콘](assets/dimension-icon.png) 주황색이고, **세그먼트** ![세그먼트 아이콘](assets/segment-icon.png) 파란색, **날짜 범위** ![날짜 범위 아이콘](assets/date-range-icon.png) 보라색이고 **지표** ![지표 아이콘](assets/default-metric-icon.png) 녹색입니다. Adobe 아이콘 ![Adobe 아이콘](assets/default-calc-metric-icon.png) 계산된 지표 템플릿 또는 세그먼트 템플릿과 계산기 아이콘을 나타냅니다 ![계산기 아이콘](assets/calculated-metric-icon-created.png) 조직의 Analytics 관리자가 만든 계산된 지표를 표시합니다.

{{dd-filter-criteria}}

1. (선택 사항) **정렬** 아이콘 ![구성 요소 정렬 아이콘](assets/component-sort-icon.png)을 선택한 다음, 다음 필터 옵션 중 하나를 선택하여 구성 요소 목록을 정렬합니다.

   {{components-sort-options}}

1. 구성 요소 목록에서 확인할 구성 요소를 선택합니다.

   구성 요소에 대한 다음 정보가 표시됩니다.

   {{dd-component-information}}

1. (선택 사항) 데이터 사전에서 Analysis Workspace로 구성 요소를 드래그합니다.
