---
title: Customer Journey Analytics의 구성 요소는 무엇입니까?
description: Customer Journey Analytics가 제공하는 구성 요소와 보고 시 그러한 구성 요소를 사용할 수 있는 방법을 알아봅니다.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 33%

---

# 구성 요소 개요

구성 요소는 시각화(예: 자유 형식 테이블)에 사용하거나 보고 기능을 보완하는 Customer Journey Analytics의 기능입니다.

기본 Customer Journey Analytics 인터페이스에서 구성 요소를 관리하려면 다음을 수행하십시오.

1. 상단 표시줄에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택합니다.
1. 관리할 수 있는 구성 요소에 대한 개요를 보려면 **[!UICONTROL 구성 요소]**&#x200B;를 선택하고 메뉴에서 관리할 구성 요소를 직접 선택하십시오.

다음 구성 요소를 관리할 수 있습니다.

* [필터](filters/filters-overview.md): 강력하고 집중적인 대상자 필터를 작성, 관리, 공유하고 보고서에 적용합니다. 필터를 사용하여 특성 또는 상호 작용에 따라 사용자 하위 세트를 식별할 수 있습니다.
* [계산된 지표](calc-metrics/calc-metr-overview.md): 보고에 사용할 새 구성 요소로 지표 및 공식 사용
* [날짜 범위](date-ranges/create.md): Analysis Workspace에서 제공하는 날짜 범위 사용자 정의 및 세분화입니다.
* [주석](/help/components/annotations/overview.md): 상황별 데이터 뉘앙스와 인사이트를 조직에 전달합니다.
* [지능형 경고](/help/components/c-intelligent-alerts/intelligent-alerts.md): 변경된 백분율 또는 특정 데이터 포인트를 기반으로 알림을 받을 수 있습니다.
* [예약된 프로젝트](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager): 예약된 프로젝트를 관리합니다.
* [환경 설정](/help/analysis-workspace/user-preferences.md): Analysis Workspace 환경 설정을 관리합니다.
* [대상](/help/components/audiences/audiences-overview.md): 타깃팅 및 개인화를 위해 Customer Journey Analytics에서 [Real-time Customer Data Platform Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home)(으)로 대상을 만들고 게시합니다.
* [내보내기](/help/components/exports/manage-export-locations.md): 내보내기 계정 및 위치를 관리합니다.


## Analysis Workspace 구성 요소

Analysis Workspace의 구성 요소는 Workspace 프로젝트의 패널 및 시각화에 끌어서 놓을 수 있는 지표, 차원, 필터 및 날짜 범위로 구성됩니다. 만든 사용자 지정 구성 요소는 계산된 지표 또는 사용자 지정 날짜 범위와 같이 이러한 패널에 추가됩니다.

구성 요소 패널에 액세스하려면 단추 패널에서 ![조정](/help/assets/icons/Curate.svg) **[!UICONTROL 구성 요소]**&#x200B;를 선택하십시오.

![왼쪽 레일의 구성 요소 아이콘이 강조 표시된 Workspace 패널](assets/components.png)

프로젝트에서 구성 요소를 사용하는 방법에 대한 자세한 내용은 [프로젝트 만들기](/help/analysis-workspace/home.md)를 참조하십시오.


+++ 구성 요소의 가능성을 보여주는 비디오 보기:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

+++

## 구성 요소 관리 {#actions}

Analysis Workspace의 **[!UICONTROL 구성 요소]** 메뉴를 사용하여 새 구성 요소를 빠르게 만들 수 있습니다. 자세한 내용은 [Analysis Workspace 메뉴](/help/analysis-workspace/home.md#menu)를 참조하세요.

구성 요소를 관리할 수 있습니다(개별적으로 또는 둘 이상을 선택하여).

1. 구성 요소를 하나 이상 선택합니다.

1. 컨텍스트 메뉴 또는 ![MoreVertical](/help/assets/icons/MoreVertical.svg) 구성 요소 작업 단추(구성 요소 상단)에서 다음 작업 중 하나를 선택합니다.


   >[!TIP]
   >
   >**[!UICONTROL Shift]**&#x200B;을 누르거나 **[!UICONTROL Command]**(macOS) 또는 **[!UICONTROL Ctrl]**(Windows)을 눌러 여러 구성 요소를 선택할 수 있습니다.


   ![태그, 즐겨찾기, 승인, 공유 및 삭제를 보여 주는 구성 요소 작업 목록입니다.](assets/component-menu.gif){width=100%}

   | 구성 요소 작업 | 설명 |
   |--- |--- |
   | ![레이블](/help/assets/icons/Label.svg) [!UICONTROL **태그**] | 구성 요소에 태그를 적용하여 구성 요소를 구성하거나 관리합니다. 그런 다음 ![필터](/help/assets/icons/Filter.svg) 필터를 선택하거나 `#`을(를) 입력하여 왼쪽 패널에서 태그로 검색할 수 있습니다. 태그는 구성 요소 관리자에서 필터 역할도 합니다. |
   | ![별](/help/assets/icons/Star.svg) [!UICONTROL **즐겨찾기**] | 구성 요소를 즐겨찾기 목록에 추가합니다. 태그와 마찬가지로 왼쪽 패널에서 즐겨찾기로 검색하고 구성 요소 관리자에서 즐겨찾기별로 필터링할 수 있습니다. |
   | ![StarOutline](/help/assets/icons/StarOutline.svg) **[!UICONTROL 즐겨찾기에서 제거]** | 즐겨찾기 목록에서 구성 요소를 제거합니다. |
   | ![확인 표시](/help/assets/icons/Checkmark.svg) [!UICONTROL **승인**] | 구성 요소를 승인됨으로 표시하여 해당 구성 요소가 조직에서 승인되었음을 사용자에게 알립니다. 태그와 마찬가지로 왼쪽 패널에서 승인됨으로 검색하고 필터링할 수 있습니다. ![확인 표시](/help/assets/icons/Checkmark.svg)는 승인된 구성 요소를 식별합니다. |
   | ![공유](/help/assets/icons/Share.svg) [!UICONTROL **공유**] | 조직의 사용자와 구성 요소를 공유합니다. 이 옵션은 필터 또는 계산된 지표와 같은 사용자 정의 구성 요소에만 사용할 수 있습니다. |
   | ![삭제](/help/assets/icons/Delete.svg) [!UICONTROL **삭제**] | 더 이상 필요하지 않은 구성 요소를 삭제하십시오. 이 옵션은 필터 또는 계산된 지표와 같은 사용자 정의 구성 요소에만 사용할 수 있습니다. |

사용자 정의 구성 요소는 해당 구성 요소 관리자를 통해 관리할 수도 있습니다. 예를 들어 [필터 관리](/help/components/filters/manage-filters.md)를 참조하십시오.

## 구성 요소 목록 관리

Analysis Workspace의 왼쪽 패널에서 구성 요소 목록을 검색, 필터링 및 정렬하여 특정 구성 요소를 찾을 수 있습니다.

### 검색

1. 왼쪽 패널에서 **구성 요소** ![구성 요소 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)을 선택합니다.

2. 검색 필드에 프로젝트에서 사용하려는 구성 요소의 이름을 입력하기 시작합니다.

   색상과 아이콘은 구성 요소의 유형을 식별합니다. **Dimension** ![Dimension 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)은 주황색이고, **필터** ![필터 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)은 파란색이고, **날짜 범위** ![날짜 범위 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)은 자주색이고, **지표** ![지표 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)은 녹색입니다.<br/>Adobe 아이콘 ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg)은(는) 계산된 지표 템플릿 또는 필터 템플릿을 나타냅니다. 계산기 아이콘 ![계산기 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)은(는) 조직의 관리자가 만든 계산된 지표를 나타냅니다.

3. 드롭다운 목록에서 구성 요소를 선택합니다.

### 필터링

1. 왼쪽 패널에서 **구성 요소** 아이콘 ![구성 요소 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)을 선택합니다.

2. **필터** ![데이터 사전 필터 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)을 선택하거나 검색 필드에 `#`을(를) 입력하십시오.

3. 다음 필터 옵션 중 하나를 선택하여 구성 요소 목록을 필터링합니다.

   | 아이콘 | 필터 옵션 | 설명 |
   |---------|---|----------|
   | ![확인 표시](/help/assets/icons/Checkmark.svg) | **[!UICONTROL 승인됨]** | 관리자가 승인함으로 표시된 구성 요소만 표시합니다. |
   | ![별](/help/assets/icons/Star.svg) | **[!UICONTROL 즐겨찾기]** | 즐겨찾기 목록에 있는 구성 요소만 표시합니다. <br/>즐겨찾기 목록에 구성 요소를 추가하는 방법에 대한 자세한 내용은 [구성 요소 관리](#manage-components)를 참조하십시오. |
   | ![차원](/help/assets/icons/Dimensions.svg) | **[!UICONTROL 차원]** | 차원인 구성 요소만 표시합니다. |
   | ![이벤트](/help/assets/icons/Event.svg) | **[!UICONTROL 지표]** | 지표인 구성 요소만 표시합니다. |
   | ![세그먼테이션](/help/assets/icons/Segmentation.svg) | **[!UICONTROL 필터]** | 필터인 구성 요소만 표시합니다. |
   | ![캘린더](/help/assets/icons/Calendar.svg) | **[!UICONTROL 날짜 범위]** | 날짜 범위의 구성 요소만 표시합니다. |
   | ![레이블](/help/assets/icons/Label.svg) | **[!UICONTROL *태그 이름&#x200B;*]** | 선택한 특정 태그가 있는 구성 요소만 표시합니다. Adobe의 [기본 계산된 지표](/help/components/calc-metrics/default-calcmetrics.md)인 Adobe 템플릿에 전용 태그를 사용할 수 있습니다. |

   필터를 제거하려면 필터에서 ![CrossSize75](/help/assets/icons/CrossSize75.svg)을(를) 선택하십시오.

4. [구성 요소 목록 정렬](#sort-the-component-list)에 설명된 대로 구성 요소 목록을 선택적으로 정렬할 수 있습니다.

### 정렬

<!-- {{release-limited-testing-section}}-->

1. (선택 사항) [구성 요소 목록 필터링](#filter-the-component-list)에 설명된 대로 구성 요소 목록에 필터를 적용합니다.

2. 왼쪽 패널에서 **구성 요소** ![구성 요소 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)을 선택합니다.

3. **정렬** ![구성 요소 정렬 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)을 선택한 다음 다음 필터 옵션 중 하나를 선택하여 구성 요소 목록을 정렬합니다.

다음 정렬 옵션을 사용할 수 있습니다.

{{components-sort-options}}

## 액세스 권한

Analysis Workspace에서 관리자는 보고 시 사용자에게 노출되는 구성 요소를 [조정](/help/analysis-workspace/curate-share/curate.md)할 수 있습니다.
