---
title: 주석 관리
description: Analysis Workspace에서 주석을 관리하는 방법
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 91%

---

# 주석 관리

중앙 [!UICONTROL 주석] 관리 인터페이스에서 주석을 공유, 필터링, 태그 지정, 승인, 복사 및 삭제하고 주석을 즐겨찾기로 표시할 수 있습니다. 주석을 관리하는 방법:

* 메인 인터페이스에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택한 다음 **[!UICONTROL 주석]**&#x200B;을 선택합니다.


>[!NOTE]
>
>모든 프로젝트에 주석이 제공되지 않는 한 특정 Workspace 프로젝트 내에서 만든 주석이 [!UICONTROL 주석] 관리자에 표시되지 않습니다.
>

## 주석 관리자

주석 관리자에는 다음 인터페이스 요소가 있습니다.

![Annotations interface](assets/annotations-manager.png)

### 주석 목록

주석 목록 ➊에는 사용자가 소유한 모든 주석, 모든 프로젝트에 범위가 지정된 주석, 사용자와 공유된 주석이 표시됩니다. 목록은 다음과 같습니다.

| 열 | 설명 |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 주석을 ![Star](/help/assets/icons/Star.svg) 즐겨찾기에 추가하거나 ![StarOutline](/help/assets/icons/StarOutline.svg) 추가하지 않을지 선택합니다. |
| **[!UICONTROL Title and description]** | Annotation Builder에 제공됩니다. 제목 및 설명을 편집하려면 제목 링크를 선택하고 [주석 빌더](/help/components/annotations/create-annotations.md#annotation-builder)를 엽니다. 공유된 주석은 ![Share](/help/assets/icons/ShareAlt.svg)로 표시됩니다. |
| **[!UICONTROL 데이터 보기]** | 이 주석이 적용되는 데이터 보기입니다. |
| **[!UICONTROL 소유자]** | 주석 소유자. 사용자가 소유한 주석 또는 사용자와 공유된 주석만 표시합니다. |
| **[!UICONTROL 적용된 날짜 범위]** | 이 주석이 적용되는 날짜 또는 날짜 범위입니다. |
| **[!UICONTROL 태그]** | 이 주석의 태그입니다. |
| **[!UICONTROL 다음 사용자와 공유]** | 주석을 공유한 개인 또는 그룹을 표시합니다. **[!UICONTROL 구성 요소 공유]** 대화 상자를 열지 선택합니다. |
| **[!UICONTROL 수정한 날짜]** | 주석을 마지막으로 수정한 날짜와 시간을 표시합니다. |

{style="table-layout:auto"}

![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을 사용하여 표시할 열을 지정합니다.

### 작업 표시줄

작업 모음 ➋을(를) 사용하여 주석에 대해 작업을 수행할 수 있습니다. 작업 표시줄에는 다음 액션이 포함됩니다.

| 아이콘 | 액션 | 설명 |
|:--:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 추가]** | [주석 빌더](create-annotations.md#annotation-builder)를 사용하여 다른 주석을 추가합니다. |
| ![Search](/help/assets/icons/Search.svg) | [!UICONTROL *제목별 검색*] | 주석이 목록에서 선택되지 않은 경우 이 검색 필드를 사용하여 주석을 검색합니다. |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 태그]** | 선택한 주석에 태그를 지정합니다. **[!UICONTROL 구성 요소에 태그 지정]** 대화 상자에서 선택한 주석의 태그를 선택하거나 선택 취소합니다. **[!UICONTROL 저장]**&#x200B;을 선택하여 선택한 주석의 태그를 저장합니다. |
| ![Share](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 공유]** | 선택한 주석을 공유합니다. **[!UICONTROL 구성 요소 공유]** 대화 상자에서 *개인 또는 그룹 검색* ![Search](/help/assets/icons/Search.svg)을 하거나 **[!UICONTROL 조직]** 또는 **[!UICONTROL 그룹]**&#x200B;을 선택할 수 있습니다. **[!UICONTROL 저장]**&#x200B;을 선택하여 선택한 주석에 대한 공유 세부 정보를 저장합니다. 자세한 내용은 [주석 공유](#share-annotations)를 참조하십시오. |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 삭제]** | 선택한 주석을 삭제합니다. 확인 메시지가 표시됩니다. |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 이름 바꾸기]** | 선택한 단일 주석 이름을 바꿉니다. 선택한 경우 주석 이름을 인라인으로 바꿀 수 있습니다. |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL 복사]** | 선택한 주석을 복사합니다. 새로운 주석이 동일한 이름과 접미사로 생성됩니다(복사). |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV로 내보내기]** | 주석을 `Annotations List.csv` 파일로 내보냅니다. |

### 활성 필터 표시줄

필터 표시줄 ➌에 활성 필터(있는 경우)가 표시됩니다. ![CrossSize75](/help/assets/icons/CrossSize75.svg)를 사용하여 필터를 빠르게 제거할 수 있습니다. 두 개 이상의 필터가 지정되면 **[!UICONTROL 모두 제거]**&#x200B;를 사용하여 모든 필터를 제거할 수 있습니다.

### 필터 패널

왼쪽 패널 **[!UICONTROL 에서]**&#x200B;필터➍를 사용하여 주석을 필터링할 수 있습니다. 필터 패널에는 필터 유형 및 해당 필터를 처리하는 주석의 수가 표시됩니다. ![Filter](/help/assets/icons/Filter.svg)를 선택하여 필터 패널의 디스플레이를 토글합니다.

필터 목록을 필터링하는 방법:

1. ![Filter](/help/assets/icons/Filter.svg)를 선택하여 필터 패널을 엽니다. 필터 목록에 추가 공간이 필요한 경우 ![Filter](/help/assets/icons/Filter.svg)를 한 번 더 선택하여 패널을 닫을 수 있습니다.
1. 제공되는 [섹션 필터링](#filter-sections)을 사용하여 주석을 필터링할 수 있습니다.

   >[!INFO]
   >
   >*항목*&#x200B;은 [주석 목록](manage-annotations.md#annotations-list)에 표시된 주석 항목을 의미합니다.
   > 

#### 섹션 필터링

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


[주석 목록](manage-annotations.md#annotations-list)은 필터 구성을 기준으로 자동으로 업데이트됩니다. [활성 필터 표시줄](manage-annotations.md#active-filter-bar)에서 구성된 필터를 확인할 수 있습니다.


## 주석 편집

다음 두 가지 방법으로 주석을 편집할 수 있습니다.

* Workspace 프로젝트에서 [구성 요소 정보](/help/components/use-components-in-workspace.md#component-info) 아이콘을 사용합니다.

* [[!UICONTROL 주석] 목록](#annotations-list)에서 주석 제목을 선택합니다.

[주석 빌더](/help/components/annotations/create-annotations.md#annotation-builder)를 사용하여 주석을 편집합니다.

## 주석 공유

주석을 공유하거나 사용자와 공유된 주석을 사용하여 작업할 때 다음이 적용됩니다.

* 다른 사용자와 공유하는 프로젝트 전용 주석이 해당 사용자에게 표시됩니다. 사용자는 이 프로젝트 전용 주석을 편집하거나 삭제할 수 없습니다.
* 주석을 저장하고 주석을 다른 사용자와 직접 공유하는 경우 해당 사용자는 관리자 권한을 보유한 경우에만 주석을 편집 및 삭제할 수 있습니다.

* 프로젝트가 공유되면 해당 프로젝트에서 생성된 주석은 해당 프로젝트에만 표시됩니다. 주석이 직접 공유되는 경우 해당 주석이 표시될 수 있는 모든 프로젝트에 주석이 표시됩니다.

## 주석 및 시간대

모든 주석은 타임스탬프와 함께 생성되지만 시간이나 시간대 정보는 포함되지 않습니다. 보고 시 패널에 구성된 데이터 보기의 시간대를 사용합니다.
