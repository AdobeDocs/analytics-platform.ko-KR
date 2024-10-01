---
description: Analysis Workspace의 데이터 사전을 사용하면 용도, 승인, 중복 등의 Analysis Workspace의 다양한 구성 요소를 분류하고 추적할 수 있습니다.
title: 데이터 사전의 항목 편집
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 60%

---

# 데이터 사전의 구성 요소 항목 편집

Customer Journey Analytics 관리자는 주어진 데이터 보기에 대한 데이터 사전의 구성 요소 항목을 편집할 수 있습니다. 모든 변경 사항은 데이터 보기의 모든 사용자에게 표시됩니다.

데이터 사전의 구성 요소를 편집하는 방법:

1. 편집할 구성 요소가 포함된 Analysis Workspace 프로젝트로 이동합니다.

1. Analysis Workspace의 단추 패널에서 **데이터 사전** 아이콘을 선택합니다. (데이터 사전에 액세스하는 다른 방법은 [데이터 사전 개요](/help/components/data-dictionary/data-dictionary-overview.md)의 “데이터 사전 액세스”에 설명되어 있음)

   데이터 사전 창이 표시됩니다.

   ![사전 상태를 표시하는 데이터 사전 관리자 보기](assets/data-dictionary-admin.png)

1. 드롭다운 메뉴에서 올바른 데이터 보기가 선택되어 있는지 확인합니다. 기본적으로 이미 있는 데이터 보기가 표시됩니다.

1. (선택 사항) 검색 필드에서 편집하려는 구성 요소의 이름을 입력하기 시작합니다.

   구성 요소 유형은 색상 및 아이콘으로 식별할 수 있습니다. **Dimension** ![Dimension 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)은 주황색이고, **필터** ![세그먼트 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)은 파란색이고, **날짜 범위** ![날짜 범위 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)은 자주색이고, **지표** ![지표 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)은 녹색입니다. Adobe 아이콘은 계산된 지표 템플릿 또는 필터 템플릿을 나타내며, 계산기 아이콘 ![계산기 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)은(는) 조직의 Analytics 관리자가 만든 계산된 지표를 나타냅니다.

   {{dd-filter-criteria}}

1. (선택 사항) 구성 요소 목록을 정렬하려면 **정렬** 아이콘 ![구성 요소 정렬 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)을 선택한 후 다음 필터링 옵션 중 하나를 선택하십시오.

{{components-sort-options}}

1. 구성 요소 목록에서 편집할 구성 요소를 선택합니다.

1. 구성 요소 이름 옆에 있는 **편집** 아이콘 ![데이터 사전 편집 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)을 선택합니다.

1. 구성 요소에 대한 다음 정보를 편집합니다.

{{dd-component-information}}

1. **저장** 아이콘 ![데이터 사전 저장 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg)을 클릭하여 변경 사항을 저장합니다.
