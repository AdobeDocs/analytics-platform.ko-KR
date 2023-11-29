---
title: Customer Journey Analytics의 구성 요소는 무엇입니까?
description: Customer Journey Analytics이 제공하는 구성 요소와 보고 시 이러한 구성 요소를 사용하는 방법을 알아봅니다.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 79%

---

# 구성 요소 개요

구성 요소는 보고서에서 사용하거나 보고 기능을 보완하는 Customer Journey Analytics의 기능입니다. 다음 단계를 사용하여 이러한 구성 요소를 관리할 수 있습니다.

1. Adobe ID 자격 증명을 사용하여 [analytics.adobe.com](https://analytics.adobe.com)에 로그인합니다.
2. 헤더 메뉴에서 [!UICONTROL 구성 요소] > [!UICONTROL 구성 요소]로 이동합니다.

다음 구성 요소를 관리할 수 있습니다.

* [**주석**](/help/components/annotations/overview.md): 상황별 데이터 뉘앙스와 통찰력을 조직에 전달합니다.
* [**대상**](/help/components/audiences/audiences-overview.md): Customer Journey Analytics에서 발견된 대상자를 만들고 게시합니다. [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko-kr) 고객 타겟팅 및 개인화를 위한 Adobe Experience Platform의 RTCDP.
* [**필터**](filters/filters-overview.md): 강력하고 집중된 대상 필터를 빌드하고, 관리하고, 공유하고, 보고서에 적용합니다. 필터를 사용하여 특성 또는 상호 작용에 따라 개인 하위 집합을 식별할 수 있습니다.
* [**계산된 지표**](calc-metrics/calc-metr-overview.md): 보고에 사용할 새 구성 요소로 지표 및 공식 사용
* [**데이터 사전**](/help/components/data-dictionary/data-dictionary-overview.md): 사용자와 관리자 모두가 Analytics 환경의 구성 요소를 추적하고 더 잘 이해할 수 있도록 지원합니다.
* [**날짜 범위**](date-ranges/create.md): Analysis Workspace에서 제공하는 날짜 범위 사용자 정의 및 세분화.
* [**Dimension**](/help/components/dimensions/view-dimensions.md): Dimension은 일반적으로 문자열 값을 포함하는 변수입니다. 일반적인 차원은 페이지 및 참조 도메인을 포함합니다.
* [**지표**](/help/components/apply-create-metrics.md): Analysis Workspace에서 데이터 포인트를 수량화할 수 있습니다.
* [**프로젝트**](/help/analysis-workspace/home.md): Analysis Workspace에서 프로젝트 구성 및 유지 관리.

## Analysis Workspace 구성 요소

Analysis Workspace의 구성 요소는 프로젝트로 드래그하여 놓을 수 있는 지표, 차원, 필터 및 시간 세부기간으로 구성됩니다. 사용자 정의 날짜 범위와 같은 만든 사용자 정의 구성 요소는 이러한 패널에 추가됩니다.

구성 요소 패널에 액세스하려면 왼쪽 레일에서 **[!UICONTROL 구성 요소]** 아이콘을 클릭하십시오. 왼쪽 레일 아이콘이나 [핫키](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)를 사용하여 패널(빈 패널, [자유 형식 패널](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [빠른 인사이트](/help/analysis-workspace/c-panels/quickinsight.md) 또는 [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md) 패널), [시각화](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) 및 구성 요소 간을 전환할 수 있습니다.

![구성 요소 아이콘](assets/components.png)

프로젝트에서의 구성 요소 사용에 대한 자세한 내용은 [프로젝트 만들기](/help/analysis-workspace/home.md)를 참조하십시오.

## 구성 요소 작업

다양한 방법으로(개별적으로 또는 두 개 이상을 선택하여) 구성 요소를 관리할 수 있습니다. 구성 요소를 마우스 오른쪽 버튼으로 클릭하거나 구성 요소 목록의 맨 위에서 **[!UICONTROL 액션]**&#x200B;을 클릭하십시오.

>[!NOTE]
>
>시간 구성 요소에는 이 작업이 적용되지 않습니다.

| 구성 요소 작업 | 설명 |
| --- | --- |
| 태그 | 구성 요소에 태그를 적용하여 구성 요소를 구성하거나 관리합니다. 그러면 각 구성 요소 관리자에 [!UICONTROL Analytics] > [!UICONTROL 구성 요소] > [!UICONTROL 필터] 또는 [!UICONTROL Analytics] > [!UICONTROL 구성 요소] > [!UICONTROL 프로젝트]와 같이 표시됩니다 |
| 즐겨찾기 | 구성 요소를 즐겨찾기 목록에 추가합니다. 그러면 각 구성 요소 관리자에 [!UICONTROL Analytics] > [!UICONTROL 구성 요소] > [!UICONTROL 필터] 또는 [!UICONTROL Analytics] > [!UICONTROL 구성 요소] > [!UICONTROL 프로젝트]와 같이 표시됩니다. |
| 승인 | 정형화되도록 구성 요소를 승인합니다. 그러면 각 구성 요소 관리자에 [!UICONTROL Analytics] > [!UICONTROL 구성 요소] > [!UICONTROL 필터] 또는 [!UICONTROL Analytics] > [!UICONTROL 구성 요소] > [!UICONTROL 프로젝트]와 같이 표시됩니다 |
| 공유 | 필터에만 적용됩니다. |
| 삭제 | 필터에만 적용됩니다. |

지표, 필터 및 날짜 만들기에 대한 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## 구성 요소 관리 {#actions}

왼쪽 레일에서 바로 구성 요소를 관리할 수 있습니다.

1. 구성 요소를 마우스 오른쪽 버튼으로 클릭합니다.

   또는

   구성 요소를 선택한 다음 구성 요소 목록 상단의 **작업**(점 3개) 아이콘을 선택합니다.

   >[!TIP]
   >
   >   Shift 키를 누르거나 Command(Mac) 또는 Ctrl(Windows) 키를 누른 상태에서 여러 구성 요소를 선택할 수 있습니다.


   ![구성 요소 작업 목록](assets/component-actions.png)

   | 구성 요소 작업 | 설명 |
   |--- |--- |
   | [!UICONTROL **태그**] | 구성 요소에 태그를 적용하여 구성 요소를 구성하거나 관리합니다. 그런 다음 필터를 클릭하거나 #을 입력하여 왼쪽 레일에서 태그로 검색할 수 있습니다. 태그는 구성 요소 관리자에서 필터 역할도 합니다. |
   | [!UICONTROL **즐겨찾기**] | 구성 요소를 즐겨찾기 목록에 추가합니다. 태그와 마찬가지로 왼쪽 레일에서 즐겨찾기로 검색하고 구성 요소 관리자에서 즐겨찾기별로 필터링할 수 있습니다. |
   | [!UICONTROL **승인**] | 구성 요소를 승인됨으로 표시하여 해당 구성 요소가 조직에서 승인되었음을 사용자에게 알립니다. 태그와 마찬가지로 왼쪽 레일에서 승인됨으로 검색하고 구성 요소 관리자에서 승인됨별로 필터링할 수 있습니다. |
   | [!UICONTROL **공유**] | 조직의 사용자와 구성 요소를 공유합니다. 이 옵션은 필터 또는 계산된 지표와 같은 사용자 지정 구성 요소에만 사용할 수 있습니다. |
   | [!UICONTROL **삭제**] | 더 이상 필요하지 않은 구성 요소를 삭제하십시오. 이 옵션은 필터 또는 계산된 지표와 같은 사용자 지정 구성 요소에만 사용할 수 있습니다. |

사용자 정의 구성 요소는 해당 구성 요소 관리자를 통해 관리할 수도 있습니다. 예를 들어 [필터 관리](/help/components/filters/manage-filters.md).

## 구성 요소 목록 검색, 필터링 및 정렬

Analysis Workspace의 왼쪽 레일에 있는 구성 요소 목록을 검색하고, 필터링하고, 정렬하여 특정 구성 요소를 빠르게 찾을 수 있습니다.

### 구성 요소 목록 검색

1. 왼쪽 레일에서 **구성 요소** 아이콘(![구성 요소 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg))을 선택합니다.

2. 검색 필드에 프로젝트에서 사용하려는 구성 요소의 이름을 입력하기 시작합니다.

   구성 요소 유형은 색상 및 아이콘으로 식별할 수 있습니다. **Dimension** ![Dimension 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) 주황색이고 **필터** ![필터 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 파란색, **날짜 범위** ![날짜 범위 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 은 자주색이고, **지표** ![지표 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) 녹색입니다. Adobe 아이콘 ![Adobe 아이콘](assets/default-calc-metric-icon.png) 계산된 지표 템플릿 또는 필터 템플릿과 계산기 아이콘을 나타냅니다. ![계산기 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) 는 조직의 Analytics 관리자가 만든 계산된 지표를 나타냅니다.

3. 드롭다운 목록에 표시되는 구성 요소를 선택합니다.

### 구성 요소 목록 필터링

1. 왼쪽 레일에서 **구성 요소** 아이콘(![구성 요소 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg))을 선택합니다.

2. 다음 항목 선택 **필터** 아이콘 ![데이터 사전 필터 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)).

   또는

   검색 필드에 파운드 기호(#)를 입력합니다.

3. 다음 필터 옵션 중 하나를 선택하여 구성 요소 목록을 필터링합니다.

   | 옵션 | 함수 |
   |---------|----------|
   | [!UICONTROL **승인됨**] | 관리자가 승인함으로 표시된 구성 요소만 표시합니다. |
   | [!UICONTROL **즐겨찾기**] | 즐겨찾기 목록에 있는 구성 요소만 표시합니다. 즐겨찾기 목록에 구성 요소를 추가하는 방법에 대한 자세한 내용은 [구성 요소 관리](#manage-components). |
   | [!UICONTROL **차원**] | 차원인 구성 요소만 표시합니다. |
   | [!UICONTROL **지표**] | 지표인 구성 요소만 표시합니다. |
   | [!UICONTROL **필터**] | 필터인 구성 요소만 표시합니다. |
   | [!UICONTROL **날짜 범위**] | 날짜 범위인 구성 요소만 표시합니다. |
   | [!UICONTROL **모두 표시**] | 모든 구성 요소를 표시합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **승인되지 않음**] | 관리자가 승인함으로 표시하지 않은 구성 요소만 표시합니다. 관리자가 검토 및 승인이 필요한 구성 요소를 식별할 때 유용합니다. 이 옵션은 관리자만 사용할 수 있습니다. |

4. (선택 사항) 목록을 더 다듬기 위해 [구성 요소 목록 정렬](#sort-the-component-list)에 설명된 대로 구성 요소 목록을 정렬할 수 있습니다.

### 구성 요소 목록 정렬

{{release-limited-testing-section}}

1. (선택 사항) [구성 요소 목록 필터링](#filter-the-component-list)에 설명된 대로 구성 요소 목록에 필터를 적용합니다.

2. 왼쪽 레일에서 **구성 요소** 아이콘(![구성 요소 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg))을 선택합니다.

3. **정렬** 아이콘(![구성 요소 정렬 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg))을 선택한 후 다음 필터 옵션 중 하나를 선택하여 구성 요소 목록을 정렬합니다.

   {{components-sort-options}}

## 구성 요소 액세스 권한

Analysis Workspace에서 관리자는 보고 시 어떤 구성 요소가 사용자에게 노출되도록 할지 [선별](/help/analysis-workspace/curate-share/curate.md)할 수 있습니다.
