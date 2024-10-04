---
title: Customer Journey Analytics에서 만든 대상자를 관리하는 방법 알아보기
description: Customer Journey Analytics에서 대상자를 관리하는 방법 알아보기
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: e131fd78ceee67a05a1ea7256e58b4b34ce44ae5
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 20%

---

# 대상자 관리

대상은 **[!UICONTROL 구성 요소]** > **[!UICONTROL 대상]**&#x200B;을 사용하여 Customer Journey Analytics에서 관리할 수 있습니다.

이전에 생성된 대상을 관리하면 다음 작업을 수행할 수 있습니다.

* 자동 대상자 새로 고침/업데이트를 **예약하거나 예약을 취소**&#x200B;합니다. 일정의 최대 만료 기간은 1년입니다.
* 곧 만료될 예정인 **대상자의 새로 고침 일정을 갱신**&#x200B;합니다. 만료 예정인 대상자는 만료될 예정인 예약된 보고서와 유사하게 처리됩니다. 관리자는 일정이 만료되기 한 달 전에 이메일을 수신합니다.
* **새로 고침 간격** 및 대상이 마지막으로 업데이트된 **시간** 보기
* Customer Journey Analytics에서 대상을 생성하는 데 걸린 **시간**&#x200B;에 대한 통찰력을 얻으십시오. 그리고 활성화를 위해 실시간 고객 플랫폼에 대상을 표시하는 데 걸린 시간입니다.
* 실시간 고객 플랫폼에서 **Customer Journey Analytics의 대상을 활발하게 사용하고 있는지**&#x200B;을(를) 확인하십시오. 또는 (이상적으로) Customer Journey Analytics이 만든 대상을 소비하는 모든 Experience Platform 애플리케이션입니다.

[대상 보기](/help/technotes/access-control.md#user-level-access) 액세스 권한이 있는 경우 대상을 볼 수 있습니다. [대상자 만들기](/help/technotes/access-control.md#user-level-access) 액세스 권한이 있는 경우 대상자를 편집하고 삭제할 수 있습니다. [대상 목록](#audiences-list)에 대상이 표시됩니다.

![대상 관리자](assets/audiences-manager.png)

## 대상 목록

대상자 목록에➊은 다음에 대한 열이 표시됩니다.

| 열 | 설명 |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 하나 이상의 대상을 선택하면 대상 인터페이스 하단에 파란색 작업 표시줄이 나타납니다. 자세한 내용은 [작업](#actions)을 참조하세요. |
| **[!UICONTROL 제목 및 설명]** | 대상자를 만들 때 입력한 제목과 설명입니다. |
| **[!UICONTROL 데이터 보기]** | 이 대상자가 생성된 데이터 보기입니다. |
| **[!UICONTROL 대상자 크기]** | 이 대상자에 있는 총 인원수입니다. |
| **[!UICONTROL 소유자]** | 대상자 소유자 - 대상자를 만든 사람입니다. |
| **[!UICONTROL 새로 고침 빈도]** | 대상을 만들 때 구성된 새로 고침 간격입니다. |
| **[!UICONTROL 태그]** | 이 대상자에 적용되는 태그입니다. |
| **[!UICONTROL 퍼블리싱 상태]** | ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 준비]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 진행 중]** 또는 ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 오류]**&#x200B;을(를) 표시할 수 있습니다. |
| **[!UICONTROL 마지막으로 새로 고침]** | 대상을 마지막으로 새로 고친 시점의 타임스탬프. |
| **[!UICONTROL 마지막 수정일]** | 대상자를 마지막으로 편집하거나 수정한 시점의 타임스탬프. |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을(를) 사용하여 표시할 열을 구성할 수 있습니다. ![검색](/help/assets/icons/Search.svg)을 사용하여 대상자를 검색합니다.

대상자를 편집하려면:

1. 대상자의 제목을 선택합니다. 대상자를 업데이트하려면 **[!UICONTROL 대상자 프로젝트 편집]** 대화 상자를 사용하십시오. 자세한 내용은 [대상 빌더](publish.md#audience-builder)를 참조하십시오.

1. 대상을 다시 게시하려면 **[!UICONTROL 다시 게시]**&#x200B;를 선택하십시오.


## 작업

다음은 예약된 프로젝트 관리자의 일반적인 작업입니다. 컨텍스트 메뉴에서 작업을 선택할 수 있습니다.

| 아이콘 | 액션 | 설명 |
|:---:|---|---|
| ![레이블](/help/assets/icons/Labels.svg) | **[!UICONTROL 태그]** | 선택한 대상자에 태그를 지정합니다. **[!UICONTROL 태그 업데이트: *대상 이름&#x200B;*]**대화 상자의 드롭다운 메뉴에서 태그를 선택하거나 새 태그를 하나 이상 입력하십시오. 저장하려면**[!UICONTROL 저장&#x200B;]**을 선택하십시오. |
| ![삭제](/help/assets/icons/Delete.svg) | **[!UICONTROL 삭제]** | 선택한 대상자를 삭제합니다. |
| ![편집](/help/assets/icons/Edit.svg) | **[!UICONTROL 이름 변경]** | 선택한 대상자의 이름을 변경합니다. **[!UICONTROL 이름 바꾸기: *대상 이름&#x200B;*]**대화 상자를 사용하여 대상 이름을 변경하고**[!UICONTROL 저장&#x200B;]**을 선택하여 저장합니다. |

다음 작업은 예약된 프로젝트를 하나 이상 선택할 때 파란색 작업 표시줄에서 사용할 수 있습니다.

| 아이콘 | 액션 | 설명 |
|:---:|---|---|
| ![닫기](/help/assets/icons/Close.svg) | **[!UICONTROL *x *선택됨]** | 선택한 대상을 선택 취소하려면 을 선택합니다. |
| ![삭제](/help/assets/icons/Delete.svg) | **[!UICONTROL 삭제]** | 선택한 대상자를 삭제합니다. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV로 내보내기]** | 선택한 대상을 `audiences.csv`(이)라는 파일로 내보냅니다. |

## 필터링

필터 패널을 사용하여 [대상자 목록](#audiences-list)을 필터링할 수 있습니다➋. 필터 패널을 표시하거나 숨기려면 ![필터](/help/assets/icons/Filter.svg)를 사용하십시오.

필터 패널은 다음 섹션으로 구성됩니다.

### 데이터 보기

| 데이터 보기 | 설명 |
|---|---|
| ![소유자](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | **[!UICONTROL 데이터 보기]** 섹션을 통해 데이터 보기를 필터링할 수 있습니다. <ul><li>![검색](/help/assets/icons/Search.svg)을 사용하여 필터링하는 데 사용할 데이터 보기를 검색합니다.</li><li>데이터 보기를 두 개 이상 선택할 수 있습니다.</li></ul> |

### 소유자

| 소유자 | 설명 |
|---|---|
| ![소유자](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | **[!UICONTROL 소유자]** 섹션을 통해 소유자를 필터링할 수 있습니다. <ul><li>![검색](/help/assets/icons/Search.svg)을 사용하여 필터링하는 데 사용할 소유자를 검색합니다.</li><li>두 명 이상의 소유자를 선택할 수 있습니다. </li></ul> |

## 새로 고침 빈도

| 새로 고침 빈도 | 설명 |
|---|---|
| ![새로 고침 빈도](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | **[!UICONTROL 새로 고침 빈도]** 섹션을 통해 새로 고침 빈도를 필터링할 수 있습니다. <ul><li>![검색](/help/assets/icons/Search.svg)을 사용하여 필터링하는 데 사용할 새로 고침 빈도를 검색합니다.</li><li>[대상 목록](#audiences-list)의 대상<br/>에 대해 정의된 새로 고침 빈도만 사용 가능한 옵션으로 표시됩니다.</li></ul> |


### 태그

| 태그 | 설명 |
|---|---|
| ![태그](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | **[!UICONTROL 태그]** 섹션을 통해 태그를 필터링할 수 있습니다. <ul><li>![검색](/help/assets/icons/Search.svg)을 사용하여 필터링하는 데 사용할 태그를 검색합니다. |
