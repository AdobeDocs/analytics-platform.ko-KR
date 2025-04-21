---
description: Analysis Workspace의 데이터 사전을 사용하면 용도, 승인, 중복 등의 Analysis Workspace의 다양한 구성 요소를 분류하고 추적할 수 있습니다.
title: 구성 요소 정보 보기
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 64%

---

# 구성 요소 정보 보기

데이터 사전을 사용하면 구성 요소 설명, 유사한 구성 요소, 구성 요소가 자주 사용되는 다른 구성 요소 등 구성 요소에 대한 정보를 볼 수 있습니다.

데이터 사전의 구성 요소에 대한 정보 보기:

1. 확인할 구성 요소가 포함된 Analysis Workspace 프로젝트로 이동합니다.

1. Analysis Workspace의 왼쪽 패널에서 [!UICONTROL **데이터 사전**] 아이콘을 선택합니다. (데이터 사전에 액세스하는 다른 방법은 [데이터 사전 개요](/help/components/data-dictionary/data-dictionary-overview.md)의 “데이터 사전 액세스”에 설명되어 있음)

   데이터 사전 창이 표시됩니다.

   ![차원, 지표, 세그먼트 및 날짜 범위에 대한 빠른 세그먼트를 표시하는 데이터 사전 창](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 보려는 구성 요소가 포함된 데이터 보기가 드롭다운 메뉴에서 선택되어 있는지 확인합니다. 기본적으로 이미 있는 데이터 보기가 표시됩니다.

1. (선택 사항) 검색 필드에서 확인하려는 구성 요소의 이름을 입력하기 시작합니다.

   구성 요소 유형은 색상 및 아이콘으로 식별할 수 있습니다. **차원**(![차원 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg))은 주황색, **세그먼트**(![세그먼트 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg))는 파란색, **날짜 범위**(![날짜 범위 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg))는 보라색, **지표**(![지표 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg))는 녹색입니다. Adobe 아이콘 ![Adobe 아이콘](assets/default-calc-metric-icon.png)은(는) 계산된 지표 템플릿 또는 세그먼트 템플릿을 나타내고 계산기 아이콘 ![계산기 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)은(는) 조직의 Analytics 관리자가 만든 계산된 지표를 나타냅니다.

1. (선택 사항) **필터** 아이콘 ![데이터 사전 필터 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)을 선택한 후 다음 세그먼트 옵션 중 하나를 선택하여 구성 요소 목록을 세그먼트화합니다.

   | 옵션 | 함수 |
   |---------|----------|
   | [!UICONTROL **승인됨**] | 관리자가 승인함으로 표시한 구성 요소만 표시합니다. |
   | [!UICONTROL **즐겨찾기**] | 즐겨찾기 목록에 있는 구성 요소만 표시합니다. 즐겨찾기 목록에 구성 요소를 추가하는 방법에 대한 자세한 내용은 [구성 요소 개요](/help/components/overview.md)를 참조하십시오. |
   | [!UICONTROL **차원**] | 차원인 구성 요소만 표시합니다. (이 옵션은 데이터 사전에 처음 액세스할 때 [!UICONTROL **빠른 세그먼트**] 탭에서도 사용할 수 있습니다.) |
   | [!UICONTROL **지표**] | 지표인 구성 요소만 표시합니다. (이 옵션은 데이터 사전에 처음 액세스할 때 [!UICONTROL **빠른 세그먼트**] 탭에서도 사용할 수 있습니다.) |
   | [!UICONTROL **세그먼트**] | 세그먼트인 구성 요소만 표시합니다. (이 옵션은 데이터 사전에 처음 액세스할 때 [!UICONTROL **빠른 세그먼트**] 탭에서도 사용할 수 있습니다.) |
   | [!UICONTROL **날짜 범위**] | 날짜 범위인 구성 요소만 표시합니다. (이 옵션은 데이터 사전에 처음 액세스할 때 [!UICONTROL **빠른 세그먼트**] 탭에서도 사용할 수 있습니다.) |
   | [!UICONTROL **모두 표시**] | 모든 구성 요소를 표시합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **승인되지 않음**] | 관리자가 승인함으로 표시하지 않은 구성 요소만 표시합니다. 관리자가 검토 및 승인이 필요한 구성 요소를 식별할 때 유용합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **설명 누락**] | 설명 필드에 아직 설명이 없는 구성 요소만 표시합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **중복 항목 표시**] | 선택한 데이터 보기에서 다른 구성 요소와 이름 또는 설명이 동일한 구성 요소만 표시합니다. 여기에는 사용자가 만든 구성 요소와 Adobe에서 제공하는 구성 요소가 포함됩니다. 중복 항목으로 표시하려면 이름이나 설명이 정확히 일치해야 합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **최근 데이터 없음**] | 지난 90일 동안 데이터를 수집하지 않은 구성 요소만 표시합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **Adobe에서 생성됨**] <!-- I don't see this option--> | Adobe에서 제작한 구성 요소만 표시합니다. 조직의 관리자 또는 다른 사용자가 만든 구성 요소는 표시되지 않습니다. |

   {style="table-layout:auto"}

1. (선택 사항) **정렬** 아이콘 ![구성 요소 정렬 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)을 선택한 후 다음 세그먼트 옵션 중 하나를 선택하여 구성 요소 목록을 정렬합니다.

   {{components-sort-options}}

1. 구성 요소 목록에서 확인할 구성 요소를 선택합니다.

   구성 요소에 대한 다음 정보가 표시됩니다.

   | 옵션 | 함수 |
   |---------|----------|
   | [!UICONTROL **승인됨**] | <p>관리자가 구성 요소를 검토하고 승인했음을 나타냅니다.</p><p>관리자에게는 [!UICONTROL **승인 취소**] 옵션이 표시됩니다. 이 옵션을 선택하면 구성 요소가 사용자에게 “승인되지 않음”으로 표시됩니다.</p> |
   | [!UICONTROL **승인되지 않음**] | <p>관리자가 아직 구성 요소를 검토하고 승인하지 않았음을 나타냅니다.</p><p>관리자에게는 [!UICONTROL **승인**] 옵션이 표시됩니다. 이 옵션을 선택하면 구성 요소가 사용자에게 “승인됨”으로 표시됩니다.</p> |
   | [!UICONTROL **컨텍스트 레이블**] | 이 필드는 구성 요소의 컨텍스트 레이블이 데이터 보기에서 업데이트된 경우에만 나타납니다. <p>자세한 내용은 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하세요. </p> |
   | [!UICONTROL **설명**] | 구성 요소의 의도된 기능을 설명합니다. (이 정보는 [구성 요소 설명 추가](/help/components/add-component-descriptions.md)에 설명된 대로 Analytics 관리자가 추가함) |
   | [!UICONTROL **다음과 함께 자주 사용됨**] | <p>현재 보고 있는 구성 요소와 함께 가장 일반적으로 사용되는 구성 요소를 표시합니다.</p><p>지표, 계산된 지표, 차원, 세그먼트 및 날짜 범위의 5가지 기본 구성 요소 유형에서 최대 5가지 구성 요소가 표시됩니다.</p><p>이 목록은 지난 90일 동안의 데이터를 기반으로 합니다. 볼 수 있는 액세스 권한이 있는 구성 요소만 표시됩니다.</p><p>관리자는 [!UICONTROL **항상 포함**] 및 [!UICONTROL **항상 제외**] 드롭다운 영역에서 원하는 구성 요소를 선택해서 이 섹션에서 사용자에게 표시되는 구성 요소를 조정할 수 있습니다. 사용자에게 표시되는 구성 요소를 조정하기 전에 먼저 **모두 표시** 세그먼트를 적용하여 다른 관리자가 추가했을 수 있는 사용자와 공유되지 않은 구성 요소를 보고 있는지 확인하십시오.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | [!UICONTROL **다음과 유사**] | <p>현재 보고 있는 구성 요소와 유사한 이름이 있는 구성 요소를 표시합니다.</p><p>지표, 계산된 지표, 차원, 세그먼트 및 날짜 범위의 5가지 기본 구성 요소 유형에서 최대 5가지 구성 요소가 표시됩니다.</p><p>볼 수 있는 액세스 권한이 있는 구성 요소만 표시됩니다.</p><p>데이터 보기에 있는 모든 중복 구성 요소가 여기에 표시됩니다. Analytics 관리자는 [데이터 사전 상태 모니터링](/help/components/data-dictionary/monitor-data-dictionary-health.md)에 설명된 대로 모든 중복 구성 요소를 식별하고 제거해야 합니다.</p><p>관리자는 [!UICONTROL **항상 포함**] 및 [!UICONTROL **항상 제외**] 드롭다운 영역에서 원하는 구성 요소를 선택해서 이 섹션에서 사용자에게 표시되는 구성 요소를 조정할 수 있습니다. 사용자에게 표시되는 구성 요소를 조정하기 전에 먼저 **모두 표시** 세그먼트를 적용하여 다른 관리자가 추가했을 수 있는 사용자와 공유되지 않은 구성 요소를 보고 있는지 확인하십시오.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**참고:** 현재 **다음과 유사** 섹션에는 사용자가 만든 구성 요소만 포함되고 Adobe에서 제공하는 구성 요소는 포함되지 않습니다. Adobe 제공 구성 요소는 향후 릴리스에 추가될 예정입니다.</p> |
   | [!UICONTROL **제품 호환성**] | Customer Journey Analytics에서 이 계산된 지표를 사용할 수 있는 위치를 나타냅니다. <p>가능한 값은 다음과 같습니다.</p><ul><li>[!UICONTROL **Customer Journey Analytics의 모든 곳**]: 계산된 지표는 Analysis Workspace, Report Builder 등을 포함하여 모든 Customer Journey Analytics 전체에서 사용할 수 있습니다.</li><li>[!UICONTROL **Customer Journey Analytics의 모든 곳(실험 제외)**]: 계산된 지표는 실험 패널을 제외한 Customer Journey Analytics 전반에서 사용할 수 있습니다.</li> <p>계산된 지표를 실험에 사용할 수 있는지 여부를 결정하는 기준에 대한 자세한 내용은 [실험 패널](/help/analysis-workspace/c-panels/experimentation.md)의 [실험 패널에서 계산된 지표 사용](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel)을 참조하십시오.</p></ul> |
   | [!UICONTROL **태그**] | 구성 요소에 적용된 모든 태그가 표시됩니다. 관리자 액세스 권한이 있는 사용자는 구성 요소를 편집할 때 태그를 추가할 수 있습니다. |
   | [!UICONTROL **구성 요소 유형**] | 차원, 지표, 세그먼트 또는 날짜 범위 등 구성 요소의 유형을 나열합니다. |
   | [!UICONTROL **작성자**] | 구성 요소를 생성한 사용자 이름을 표시합니다. |
   | [!UICONTROL **미리보기**] | Analysis Workspace에서 구성 요소가 어떻게 보이는지 미리보기를 표시합니다. |
   | [!UICONTROL **마지막 수정일**] | 구성 요소가 마지막으로 수정된 날짜를 표시합니다. 이 섹션은 세그먼트, 지표, 계산된 지표 및 날짜 범위를 볼 때 표시됩니다. |

   {style="table-layout:auto"}

1. (선택 사항) 데이터 사전에서 Analysis Workspace로 구성 요소를 드래그합니다.
