---
description: 계산된 지표를 공유, 필터링, 태그 지정, 승인, 복사, 삭제 및 즐겨찾기로 표시하는 방법에 대해 알아봅니다.
title: 계산된 지표 관리
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 28%

---

# 계산된 지표 관리

중앙 [!UICONTROL 계산된 지표] 관리 인터페이스에서 계산된 지표를 공유, 필터링, 태그 지정, 승인, 이름 변경, 복사, 삭제, 내보내고 즐겨찾기로 표시할 수 있습니다. 계산된 지표를 관리하려면 다음 작업을 수행하십시오.


* 기본 인터페이스에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택한 다음 **[!UICONTROL 계산된 지표]**&#x200B;을(를) 선택하십시오.


## 계산된 지표 관리자

계산된 지표 관리자에는 다음 인터페이스 요소가 있습니다.


![계산된 지표 관리자 인터페이스](assets/calculated-metrics-manager.png)

### 계산된 지표 목록

계산된 지표 목록 ➊에는 사용자가 소유하거나 사용자와 공유된 모든 계산된 지표가 표시됩니다. 목록은 다음과 같습니다.

<!-- I think this table incorrectly talks about quick calculated metrics -->

| 열 | 설명 |
| --- | --- |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 계산된 지표를 ![Star](/help/assets/icons/Star.svg)에 선호하거나 ![StarOutline](/help/assets/icons/StarOutline.svg)에 선호하지 않도록 선택하십시오. [계산된 지표를 즐겨찾기로 표시](/help/components/segments/seg-favorite.md)을 참조하십시오. |
| **[!UICONTROL 제목 및 설명]** | 계산된 지표를 편집하려면 제목 링크를 선택하여 [계산된 지표 빌더](cm-build-metrics.md)를 엽니다. 공유 계산된 지표가 ![공유](/help/assets/icons/ShareAlt.svg)(으)로 표시되어 있습니다. |
| **[!UICONTROL 데이터 보기]** | 이 계산된 지표가 적용되는 데이터 보기. |
| **[!UICONTROL 소유자]** | 계산된 지표의 소유자입니다. 사용자가 소유한 주석 또는 사용자와 공유된 주석만 표시합니다. |
| **[!UICONTROL 태그]** | 이 계산된 지표에 대한 태그를 나열합니다. |
| **[!UICONTROL 다음 사용자와 공유]** | 계산된 지표를 공유한 개인 또는 그룹 수를 표시합니다. **[!UICONTROL 계산된 지표 공유]** 대화 상자를 열려면 선택하십시오. 자세한 내용은 [계산된 지표 공유](cm-sharing.md)를 참조하십시오. |
| **[!UICONTROL 수정한 날짜]** | 계산된 지표를 마지막으로 수정한 날짜 및 시간입니다. |
| **[!UICONTROL 다음에서 사용]** | 계산된 지표가 현재 사용 중인 위치와 각 영역에서 사용 중인 횟수를 보여줍니다. <p>예를 들어, 계산된 지표가 40개의 프로젝트와 2개의 경고에서 사용 중인 경우 이 열의 값은 [!UICONTROL **42개의 구성 요소**]&#x200B;로 표시됩니다. <p>이 열의 값을 선택하여 계산된 지표가 사용되는 위치 분류를 확인합니다(예: [!UICONTROL **프로젝트(40)**], [!UICONTROL **모바일 스코어카드(2)**]). 또한 계산된 지표가 사용되는 항목 목록을 볼 수 있습니다. 예를 들어 해당 프로젝트가 사용되는 프로젝트 목록을 보려면 [!UICONTROL **프로젝트(40)**] 링크를 선택합니다.</p><p>다음 각 영역은 해당 영역에서 사용 중인 계산된 지표의 인스턴스 수를 보여줍니다.</p> <ul><li>[!UICONTROL **프로젝트**]<p>[계산된 지표 빌더에서 ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)하여 모든 프로젝트에 사용할 수 있는 계산된 지표를 포함합니다.</p></li><li>[!UICONTROL **애드혹 구성 요소**]<p>[빠른 계산된 지표로 만든 ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) 계산된 지표를 포함하며 단일 프로젝트 내에서만 사용할 수 있습니다.</p></li><li>[!UICONTROL **예약된 프로젝트**]</li><li>[!UICONTROL **모바일 스코어카드**]</li><li>[!UICONTROL **주석**]</li><li>[!UICONTROL **Report Builder**]<p>이 옵션을 선택하면 다음 데이터 열이 포함된 CSV 파일이 다운로드됩니다.</p><ul><li>Report Builder 이름</li><li>마지막 액세스</li><li>마지막으로 액세스한 IMS 사용자 ID</li><li>마지막으로 액세스한 사용자 이름</li></ul></li></ul><p>이 정보는 구성 요소가 조직의 사용자에게 가치가 있는지, 사용 위치 및 삭제하거나 수정해야 하는지 여부를 확인하는 데 도움이 됩니다.</p><p>이 열을 조회할 때 다음 사항을 고려하십시오.</p><ul><li>이 정보는 시스템 관리자만 사용할 수 있습니다.</li><li>기본적으로 [!UICONTROL **다음에서 사용됨**] 열은 표시되지 않습니다. ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을 사용하여 이 열의 표시를 구성합니다.</li><li>이 정보에는 API 또는 Data Warehouse의 사용이 포함되지 않습니다.</li><li>지정된 구성 요소에 대해 이 열에 데이터가 없지만 [!UICONTROL **마지막으로 사용됨**] 날짜가 있는 경우 구성 요소가 저장되지 않고 분석에 사용되었을 수 있습니다.</li><li>사용량 정보는 2023년 9월부터의 자료만 제공됩니다.</li></ul><p>이 정보와 함께 [데이터 사전](/help/components/data-dictionary/data-dictionary-overview.md)을 사용하면 조직에서 구성 요소가 사용되는 방식을 지속적으로 추적하고 보다 명확하게 파악할 수 있습니다.</p> |
| **[!UICONTROL 마지막 사용]** | 계산된 지표가 마지막으로 사용된 시기 |

{style="table-layout:auto"}

![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을 사용하여 표시할 열을 지정합니다.

### 작업 표시줄

작업 모음 ➋을(를) 사용하여 필터에 대해 작업을 수행할 수 있습니다. 작업 표시줄에는 다음 액션이 포함됩니다.

| 아이콘 | 액션 | 설명 |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 추가]** | [계산된 지표 빌더](cm-build-metrics.md)를 사용하여 다른 계산된 지표를 추가합니다. |
| ![Search](/help/assets/icons/Search.svg) | [!UICONTROL *제목별 검색*] | 목록에서 계산된 지표를 선택하지 않으면 이 검색 필드를 사용하여 필터를 검색합니다. |
| ![레이블](/help/assets/icons/Label.svg) | **[!UICONTROL 태그]** | 선택한 계산된 지표에 태그를 지정합니다. **[!UICONTROL 계산된 지표 태그 지정]** 대화 상자에서 선택한 계산된 지표에 대한 태그를 선택하거나 선택 취소합니다. **[!UICONTROL 저장]**&#x200B;을 선택하여 선택한 계산된 지표에 대한 태그를 저장합니다. 자세한 내용은 [계산된 지표에 태그 지정](cm-tagging.md)을 참조하십시오. |
| ![공유](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 공유]** | 선택한 계산된 지표를 공유합니다. **[!UICONTROL 계산된 지표 공유]** 대화 상자에서 ![검색](/help/assets/icons/Search.svg) *개인 또는 그룹 검색*&#x200B;하거나 **[!UICONTROL 조직]** 또는 **[!UICONTROL 그룹]**&#x200B;을 선택할 수 있습니다. **[!UICONTROL 저장]**&#x200B;을 선택하여 선택한 계산된 지표에 대한 공유 세부 정보를 저장합니다. 자세한 내용은 [계산된 지표 공유](cm-sharing.md)를 참조하십시오. |
| ![삭제](/help/assets/icons/Delete.svg) | **[!UICONTROL 삭제]** | 선택한 계산된 지표를 삭제합니다. 확인 메시지가 표시됩니다. |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 이름 바꾸기]** | 선택한 단일 계산된 지표의 이름을 변경합니다. 선택하면 계산된 지표의 이름을 인라인으로 바꿀 수 있습니다. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 승인]** | 선택한 계산된 지표를 승인합니다. [계산된 지표 승인](cm-approving.md)을 참조하세요. |
| ![복사](/help/assets/icons/Copy.svg) | **[!UICONTROL 복사]** | 선택한 계산된 지표를 복사합니다. 새 계산된 지표가 같은 이름 및 접미사 `(Copy)`(으)로 만들어졌습니다. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV로 내보내기]** | 계산된 지표를 `Calculated  metric List.csv` 파일로 내보냅니다. |

### 활성 필터 표시줄

필터 표시줄 ➌은(는) 필터 패널에서 계산된 지표 목록에 적용된 활성 필터를 표시합니다. ![CrossSize75](/help/assets/icons/CrossSize75.svg)를 사용하여 필터를 빠르게 제거할 수 있습니다. 두 개 이상의 필터가 지정되면 **[!UICONTROL 모두 제거]**&#x200B;를 사용하여 모든 필터를 제거할 수 있습니다.

### 필터 패널

![필터](/help/assets/icons/Filter.svg) **[!UICONTROL 필터]** 왼쪽 패널 ➍을(를) 사용하여 계산된 지표 목록을 필터링할 수 있습니다. 필터 패널에는 필터 유형 및 특정 필터를 적용하는 계산된 지표 수가 표시됩니다. ![필터](/help/assets/icons/Filter.svg)를 선택하여 필터 패널의 디스플레이를 토글합니다.

자세한 내용은 [계산된 지표 목록 필터링](cm-filter.md)을 참조하십시오.


<!-- OLD CONTENT 

The Calculated metric manager shows you all the filters you own and that have been shared with you. Admin-level users can see all custom metrics in the organization. This overview presents the user interface and the capabilities of the Calculated metric manager.

![Calculated metrics window showing available filters.](assets/calc-metric-manager.png)

## Access the Calculated metrics manager

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Calculated metrics**].

## Available actions in the Calculated metrics manager

In the Calculated metrics manager, you can:

* [Filter calculated metrics](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approve calculated metrics](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Tag calculated metrics](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Share calculated metrics](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Export a calculated metric to a CSV file. 

* [Copy calculated metrics](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Delete calculated metrics

## Configure columns

You can configure the information displayed for each calculated metric in the Calculated metrics manager by configuring the columns that are displayed.

To configure the visible columns in the Calculated metrics manager:

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Calculated metrics]**. 

1. In the Calculated metrics manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Calculated metrics manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Favorites  | Displays star icons next to each calculated metric, allowing you to mark calculated metrics as favorites. For more information, see [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Title and description | These values are provided in the Calculated metric builder. To edit the title and description, select the title link to open the Calculated metric builder.  |
   | Report suite | Indicates in which report suite the metric was last saved.  |
   | Owner | Indicates who owns the custom metric. As a non-admin, you can see only metrics you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the metric, either by you or by people who shared the calculated metric with you.  |
   | Shared with | Lists individuals or groups (admin only) or All (admin only) that you shared the calculated metric with. <p>When a calculated metric is being shared, a share icon displays next to the calculated metric name.</p>  |
   | Date modified | Indicates the date when the custom metric was last modified.  |
   | Used in | Shows where calculated metrics are currently being used, and how many times they are being used in each area. <p>For example, if the calculated metric is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**]. <p>Select the value in this column to see the breakdown of where the calculated metrics are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the calculated metrics are being used. For example, to see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of calculated metrics being used in that area:</p> <ul><li>[!UICONTROL **Projects**]<p>Contains calculated metrics that were [created in the calculated metric builder](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains calculated metrics that were [created as quick calculated metrics ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a calculated metric includes another calculated metric in its definition, any use of that calculated metric is not shown in the [!UICONTROL **Used in**] column. If a calculated metric is included in the definition of another type of component (such as a segment), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p> |
   | Last used | Shows the date when the calculated metric was last used in any of the following component types: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, or whether it should be deleted.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |

   {style="table-layout:auto"}

-->