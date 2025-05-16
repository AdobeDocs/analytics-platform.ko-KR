---
title: Customer Journey Analytics에서 만든 대상자를 관리하는 방법 알아보기
description: Customer Journey Analytics에서 대상자를 관리하는 방법 알아보기
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: ht
source-wordcount: '768'
ht-degree: 100%

---

# 대상자 관리

Customer Journey Analytics에서 **[!UICONTROL 구성 요소]** > **[!UICONTROL 대상자]**&#x200B;를 사용하여 대상자를 관리할 수 있습니다.

## 대상자 관리 작업 이해

이전에 생성된 대상자를 관리하면 다음과 같은 작업을 수행할 수 있습니다.

* 자동 대상자 새로 고침/업데이트를 **예약하거나 예약을 취소**&#x200B;합니다. 일정의 최대 만료 기간은 1년입니다.
* 곧 만료될 예정인 **대상자의 새로 고침 일정을 갱신**&#x200B;합니다. 만료 예정인 대상자는 만료될 예정인 예약된 보고서와 유사하게 처리됩니다. 관리자는 일정이 만료되기 한 달 전에 이메일을 수신합니다.
* **새로 고침 간격** 및 **대상자가 마지막으로 업데이트된 시간** 보기
* Customer Journey Analytics에서 **대상자를 만드는 데 걸린 시간**&#x200B;에 대한 인사이트를 얻을 수 있습니다. 활성화를 위해 Real-time Customer Platform에 대상자가 나타나는 데 걸린 시간입니다.
* Customer Journey Analytics의 대상자가 **Real-time Customer Platform에서 적극적으로 활용**&#x200B;되고 있는지 확인합니다. 또는 (이상적으로) Customer Journey Analytics에서 만든 대상자를 소비하는 모든 Experience Platform 애플리케이션을 확인합니다.

[대상자 보기](/help/technotes/access-control.md#user-level-access) 액세스 권한이 있으면 대상자를 볼 수 있습니다. [대상자 만들기](/help/technotes/access-control.md#user-level-access) 액세스 권한이 있으면 대상자를 편집하고 삭제할 수 있습니다.

## 대상자 목록에서 대상자 보기

대상자 목록은 ➊ 기존 대상자를 보여 줍니다.

![대상자 관리자](assets/audiences-manager.png)

대상자 목록을 보려면 다음 작업을 수행합니다.

1. Customer Journey Analytics에서 **[!UICONTROL 구성 요소]** > **[!UICONTROL 대상자]**&#x200B;를 선택합니다.

1. (선택 사항) ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을 사용하여 표시할 열을 구성할 수 있습니다.

1. (선택 사항) ![검색](/help/assets/icons/Search.svg)을 사용하여 대상자를 검색합니다.

   다음 열에서 각 대상자에 대한 정보를 제공합니다.

   | 열 | 설명 |
   | --- | --- |
   | ![SelectBox](/help/assets/icons/SelectBox.svg) | 하나 이상의 대상자를 선택하면 대상자 인터페이스 하단에 파란색 작업 표시줄이 나타납니다. 자세한 내용은 [액션](#actions)을 참조하십시오. |
   | **[!UICONTROL 제목 및 설명]** | 대상자를 만들 때 입력한 제목과 설명. |
   | **[!UICONTROL 데이터 보기]** | 이 대상자가 생성된 데이터 보기. |
   | **[!UICONTROL 대상자 크기]** | 이 대상자에 있는 총 인원수. |
   | **[!UICONTROL 소유자]** | 대상자의 소유자 - 대상자를 만든 사람. |
   | **[!UICONTROL 새로 고침 빈도]** | 대상자가 생성될 때 구성된 새로 고침 간격. |
   | **[!UICONTROL 태그]** | 이 대상자에 적용되는 태그. |
   | **[!UICONTROL 게시 상태]** | ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 준비]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 진행 중]** 또는 ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 오류]**&#x200B;를 표시할 수 있습니다. |
   | **[!UICONTROL 마지막으로 새로 고침]** | 대상자를 마지막으로 새로 고친 때의 타임스탬프 |
   | **[!UICONTROL 마지막 수정일]** | 대상자를 마지막으로 편집 또는 수정한 때의 타임스탬프. |

## 대상자 편집

언제든지 대상자 그룹의 설정을 편집할 수 있습니다. 대상자(일회성 대상자 또는 반복 대상자)를 편집하는 경우 다시 게시해야 합니다.

대상자를 편집하는 방법은 다음과 같습니다.

1. Customer Journey Analytics에서 **[!UICONTROL 구성 요소]** > **[!UICONTROL 대상자]**&#x200B;를 선택합니다.

   대상자 페이지가 표시됩니다.

1. 편집하려는 대상자의 제목을 선택합니다.

   **[!UICONTROL 대상자 편집]** 대화 상자가 표시됩니다.

1. 대상자에 대해 사용 가능한 필드를 업데이트할 수 있습니다. 업데이트할 수 있는 필드에 대한 정보는 [대상자 만들기 및 게시](/help/components/audiences/publish.md) 문서의 [대상자 빌더](/help/components/audiences/publish.md#audience-builder)를 참조하십시오.

1. **[!UICONTROL 다시 게시]**&#x200B;를 선택합니다.

## 액션

다음은 예약된 프로젝트 관리자의 일반적인 액션입니다. 컨텍스트 메뉴에서 액션을 선택할 수 있습니다.

| 아이콘 | 액션 | 설명 |
|:---:|---|---|
| ![레이블](/help/assets/icons/Labels.svg) | **[!UICONTROL 태그]** | 선택한 대상자에 태그를 지정합니다. **[!UICONTROL 태그 업데이트: *대상자 이름&#x200B;*]**대화 상자의 드롭다운 메뉴에서 태그를 선택하거나 하나 이상의 새 태그를 입력합니다. 저장하려면**[!UICONTROL 저장&#x200B;]**을 선택합니다. |
| ![삭제](/help/assets/icons/Delete.svg) | **[!UICONTROL 삭제]** | 선택한 대상자를 삭제합니다. |
| ![편집](/help/assets/icons/Edit.svg) | **[!UICONTROL 이름 바꾸기]** | 선택한 대상자의 이름을 변경합니다. **[!UICONTROL 이름 바꾸기: *대상자 이름&#x200B;*]**대화 상자를 사용하여 대상자의 이름을 바꾸고**[!UICONTROL 저장&#x200B;]**을 선택하여 저장합니다. |

하나 이상의 예약된 프로젝트를 선택하면 파란색 작업 표시줄에서 다음 액션을 사용할 수 있습니다.

| 아이콘 | 액션 | 설명 |
|:---:|---|---|
| ![닫기](/help/assets/icons/Close.svg) | **[!UICONTROL *x *선택됨]** | 선택한 대상자를 선택 취소합니다. |
| ![삭제](/help/assets/icons/Delete.svg) | **[!UICONTROL 삭제]** | 선택한 대상자를 삭제합니다. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV로 내보내기]** | 선택한 대상자를 `audiences.csv` 이름의 파일로 내보냅니다. |

## 대상자 목록 필터링

필터 패널 ➋을 사용하여 [대상자 목록](#audiences-list)을 필터링할 수 있습니다. 필터 패널을 표시하거나 숨기려면 ![필터](/help/assets/icons/Filter.svg)를 사용합니다.

![대상자 관리자](assets/audiences-manager.png)

필터 패널은 다음 섹션으로 구성되어 있습니다.

### 데이터 보기

| 데이터 보기 | 설명 |
|---|---|
| ![소유자](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | **[!UICONTROL 데이터 보기]** 섹션에서는 데이터 보기를 필터링할 수 있습니다. <ul><li>필터링할 데이터 보기를 검색하려면 ![검색](/help/assets/icons/Search.svg)을 사용합니다.</li><li>둘 이상의 데이터 보기를 선택할 수 있습니다.</li></ul> |

### 소유자

| 소유자 | 설명 |
|---|---|
| ![소유자](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | **[!UICONTROL 소유자]** 섹션에서는 소유자를 필터링할 수 있습니다. <ul><li>필터링할 소유자를 검색하려면 ![검색](/help/assets/icons/Search.svg)을 사용합니다.</li><li>둘 이상의 소유자를 선택할 수 있습니다. </li></ul> |

## 새로 고침 빈도

| 새로 고침 빈도 | 설명 |
|---|---|
| ![새로 고침 빈도](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | **[!UICONTROL 새로 고침 빈도]** 섹션에서는 새로 고침 빈도를 필터링할 수 있습니다. <ul><li>필터링할 새로 고침 빈도를 검색하려면 ![검색](/help/assets/icons/Search.svg)을 사용합니다.</li><li>[대상자 목록](#audiences-list)에서 대상자<br/>에 대해 정의된 새로 고침 빈도만 가능한 옵션으로 표시됩니다.</li></ul> |


### 태그

| 태그 | 설명 |
|---|---|
| ![태그](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | **[!UICONTROL 태그]** 섹션에서는 태그를 필터링할 수 있습니다. <ul><li>필터링할 태그를 검색하려면 ![검색](/help/assets/icons/Search.svg)을 사용합니다. |
