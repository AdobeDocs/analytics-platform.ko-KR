---
description: Analysis Workspace의 데이터 사전을 사용하면 용도, 승인, 중복 등의 Analysis Workspace의 다양한 구성 요소를 분류하고 추적할 수 있습니다.
title: 데이터 사전 보기
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 75%

---

# 데이터 사전의 구성 요소 정보 보기

데이터 사전을 사용하면 구성 요소 설명, 유사한 구성 요소, 구성 요소가 자주 사용되는 다른 구성 요소 등 구성 요소에 대한 정보를 볼 수 있습니다.

데이터 사전의 구성 요소에 대한 정보 보기:

1. 확인할 구성 요소가 포함된 Analysis Workspace 프로젝트로 이동합니다.

1. Analysis Workspace의 왼쪽 패널에서 [!UICONTROL **데이터 사전**] 아이콘을 선택합니다. (데이터 사전에 액세스하는 다른 방법은 [데이터 사전 개요](/help/components/data-dictionary/data-dictionary-overview.md)의 “데이터 사전 액세스”에 설명되어 있음)

   데이터 사전 창이 표시됩니다.

   ![Dimension, 지표, 세그먼트 및 날짜 범위에 대한 빠른 필터를 보여 주는 데이터 사전 창](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 보려는 구성 요소가 포함된 데이터 보기가 드롭다운 메뉴에서 선택되어 있는지 확인합니다. 기본적으로 이미 있는 데이터 보기가 표시됩니다.

1. (선택 사항) 검색 필드에서 확인하려는 구성 요소의 이름을 입력하기 시작합니다.

   구성 요소 유형은 색상 및 아이콘으로 식별할 수 있습니다. **Dimension** ![Dimension 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)은 주황색이고, **필터** ![세그먼트 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)은 파란색이고, **날짜 범위** ![날짜 범위 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)은 자주색이고, **지표** ![지표 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)은 녹색입니다. Adobe 아이콘(![Adobe 아이콘](assets/default-calc-metric-icon.png))은 계산된 지표 템플릿 또는 필터 템플릿을 나타내고 계산기 아이콘(![계산기 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg))은 조직의 Analytics 관리자가 만든 계산된 지표를 나타냅니다.

{{dd-filter-criteria}}

1. (선택 사항) 구성 요소 목록을 정렬하려면 **정렬** 아이콘 ![구성 요소 정렬 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)을 선택한 후 다음 필터링 옵션 중 하나를 선택하십시오.

   {{components-sort-options}}

1. 구성 요소 목록에서 확인할 구성 요소를 선택합니다.

   구성 요소에 대한 다음 정보가 표시됩니다.

   {{dd-component-information}}

1. (선택 사항) 데이터 사전에서 Analysis Workspace로 구성 요소를 드래그합니다.
