---
title: 주석 관리
description: Workspace에서 주석을 관리하는 방법
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 6%

---

# 주석 관리

중앙 [!UICONTROL 주석] 관리 인터페이스에서 주석을 공유, 필터링, 태그 지정, 승인, 복사, 삭제하고 주석을 즐겨찾기로 표시할 수 있습니다. 주석을 관리하려면:

* 기본 인터페이스에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택한 다음 **[!UICONTROL 주석]**&#x200B;을 선택하십시오.


>[!NOTE]
>
>모든 프로젝트에 주석을 사용할 수 있도록 설정하지 않은 한 특정 Workspace 프로젝트 내에서 만든 주석은 [!UICONTROL 주석] 관리자에 표시되지 않습니다.
>

## 주석 관리자

주석 관리자에는 다음과 같은 인터페이스 요소가 있습니다.

![주석 인터페이스](assets/annotations-manager.png)

### 주석 목록

주석 목록에➊은 사용자가 소유한 모든 주석, 모든 프로젝트에 범위가 지정된 주석 및 사용자와 공유된 주석이 표시됩니다. 목록에는 다음 열이 있습니다.

| 열 | 설명 |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 주석을 ![Star](/help/assets/icons/Star.svg)하거나 ![StarOutline](/help/assets/icons/StarOutline.svg)을(를) 해제하려면 선택하십시오. |
| **[!UICONTROL 제목 및 설명]** | Annotation Builder에 제공됩니다. 제목과 설명을 편집하려면 제목 링크를 선택합니다. [주석 빌더](/help/components/annotations/create-annotations.md#annotation-builder)를 엽니다. 공유 주석이 ![공유](/help/assets/icons/ShareAlt.svg)(으)로 표시되어 있습니다. |
| **[!UICONTROL 데이터 보기]** | 이 주석이 적용되는 데이터 보기입니다. |
| **[!UICONTROL 소유자]** | 주석의 소유자입니다. 사용자는 소유한 주석 또는 사용자와 공유된 주석만 볼 수 있습니다. |
| **[!UICONTROL 적용 날짜 범위]** | 이 주석이 적용되는 날짜 또는 날짜 범위입니다. |
| **[!UICONTROL 태그]** | 이 주석의 태그입니다. |
| **[!UICONTROL 다음 사용자와 공유]** | 주석을 공유한 개인 또는 그룹입니다. **[!UICONTROL 구성 요소 공유]** 대화 상자를 열려면 선택하세요. |
| **[!UICONTROL 수정한 날짜]** | 주석을 마지막으로 수정한 날짜와 시간을 표시합니다. |

{style="table-layout:auto"}

표시할 열을 지정하려면 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을(를) 사용합니다.

### 작업 표시줄

작업 표시줄을 사용하여 주석에 대한 작업을 수행할 수 있습니다➋. 작업 모음 에는 다음 작업이 포함되어 있습니다.

| 액션 | 설명 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 추가]** | [주석 빌더](create-annotations.md#annotation-builder)를 사용하여 다른 주석을 추가하십시오. |
| ![검색](/help/assets/icons/Search.svg) [!UICONTROL *제목별 검색*] | 목록에서 주석을 선택하지 않은 경우 이 검색 필드를 사용하여 주석을 검색합니다. |
| ![레이블](/help/assets/icons/Label.svg) **[!UICONTROL 태그]** | 선택한 주석에 태그를 지정합니다. **[!UICONTROL 태그 구성 요소]** 대화 상자에서 선택한 주석에 대한 태그를 선택하거나 선택 취소합니다. **[!UICONTROL 저장]**&#x200B;을 선택하여 선택한 주석에 대한 태그를 저장합니다. |
| ![공유](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 공유]** | 선택한 주석을 공유합니다. **[!UICONTROL 구성 요소 공유]** 대화 상자에서 ![검색](/help/assets/icons/Search.svg) *개인 또는 그룹 검색*&#x200B;하거나 **[!UICONTROL 조직]** 또는 **[!UICONTROL 그룹]**&#x200B;을 선택할 수 있습니다. **[!UICONTROL 저장]**&#x200B;을 선택하여 선택한 주석에 대한 공유 세부 정보를 저장합니다. 자세한 내용은 [주석 공유](#share-annotations)를 참조하십시오. |
| ![삭제](/help/assets/icons/Delete.svg) **[!UICONTROL 삭제]** | 선택한 주석을 삭제합니다. 확인을 묻는 메시지가 표시됩니다. |
| ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 이름 바꾸기]** | 선택한 단일 주석의 이름을 변경합니다. 선택하면 인라인 주석의 이름을 변경할 수 있습니다. |
| ![복사](/help/assets/icons/Copy.svg) **[!UICONTROL 복사]** | 선택한 주석을 복사합니다. 새 주석은 동일한 이름과 접미사를 사용하여 만들어집니다(복사). |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV로 내보내기]** | 주석을 `Annotations List.csv` 파일로 내보냅니다. |

### 활성 필터 막대

필터 모음에 ➌ 활성 필터(있는 경우)가 표시됩니다. ![CrossSize75](/help/assets/icons/CrossSize75.svg)를 사용하여 필터를 빠르게 제거할 수 있습니다. 필터를 두 개 이상 지정한 경우 **[!UICONTROL 모두 제거]**&#x200B;를 사용하여 모든 필터를 제거할 수 있습니다.

### 필터 패널

**[!UICONTROL 필터]** 왼쪽 패널을 사용하여 주석을 필터링할 수 있습니다➍. 필터 패널에는 필터 유형 및 필터를 적용하는 주석 수가 표시됩니다. 필터 패널의 표시를 전환하려면 ![필터](/help/assets/icons/Filter.svg)를 선택하십시오.

필터 목록을 필터링하려면 다음을 수행합니다.

1. ![필터](/help/assets/icons/Filter.svg)를 선택하여 필터 패널을 엽니다. 필터 목록에 더 많은 공간이 필요한 경우 ![필터](/help/assets/icons/Filter.svg)를 한 번 더 선택하여 패널을 닫을 수 있습니다.
1. 사용 가능한 [필터 섹션](#filter-sections)을 사용하여 주석을 필터링할 수 있습니다.

   >[!INFO]
   >
   >*항목*&#x200B;은(는) [주석 목록](manage-annotations.md#annotations-list)에 표시된 주석 항목을 참조합니다.
   > 

#### 섹션 필터링

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


필터 구성에 따라 [주석 목록](manage-annotations.md#annotations-list)이 자동으로 업데이트됩니다. [활성 필터 모음](manage-annotations.md#active-filter-bar)에서 구성된 필터를 볼 수 있습니다.


## 주석 편집

다음 두 가지 방법으로 주석을 편집할 수 있습니다.

* Workspace 프로젝트에서 [구성 요소 정보](/help/components/use-components-in-workspace.md#component-info) 아이콘을 사용하십시오.

* [[!UICONTROL 주석] 목록](#annotations-list)에서 주석의 제목을 선택합니다.

[주석 빌더](/help/components/annotations/create-annotations.md#annotation-builder)를 사용하여 주석을 편집합니다.

## 주석 공유

주석을 공유하거나 사용자와 공유된 주석을 사용하여 작업할 때 다음 사항이 적용됩니다.

* 다른 사용자와 공유하는 프로젝트의 프로젝트 전용 주석은 해당 사용자에 대해 표시됩니다. 사용자는 이러한 프로젝트 전용 주석을 편집하거나 삭제할 수 없습니다.
* 주석을 저장하고 사용자와 직접 공유하는 경우, 해당 사용자는 관리자 권한이 있는 경우에만 주석을 편집하고 삭제할 수 있습니다.

* 프로젝트가 공유되면 해당 프로젝트에서 생성된 주석은 해당 프로젝트에만 표시됩니다. 주석이 직접 공유되는 경우 해당 주석이 표시될 수 있는 모든 프로젝트에 주석이 표시됩니다.

## 주석 및 시간대

모든 주석은 타임스탬프와 함께 생성되지만 시간 또는 시간대 정보는 포함되지 않습니다. 보고 시 패널에 대해 구성된 데이터 보기의 시간대가 사용됩니다.
