---
title: Customer Journey Analytics에서 Report Builder를 사용하여 데이터 블록을 관리하는 방법
description: Report Builder에서 관리 기능을 사용하는 방법을 설명합니다.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: 22b06eaf9f224188699aa241de1d1daad8a14619
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 21%

---

# 데이터 블록 관리

[!UICONTROL 데이터 블록 관리자]를 사용하여 통합 문서의 모든 데이터 블록을 보고 관리할 수 있습니다. [!UICONTROL 데이터 블록 관리자]는 특정 데이터 블록을 찾을 수 있는 검색, 필터 및 정렬 기능을 제공합니다. 하나 이상의 데이터 블록을 선택한 후 선택한 데이터 블록을 편집, 삭제 또는 새로 고칠 수 있습니다.

## 데이터 블록 보기

통합 문서의 모든 데이터 블록을 나열하는 표를 보려면 ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**&#x200B;를 선택하십시오.

![모든 데이터 블록의 목록을 보는 관리 옵션입니다.](./assets/image53.png){zoomable="yes"}

**[!UICONTROL 데이터 블록 관리자]**&#x200B;는 통합 문서에 있는 모든 데이터 블록이 있는 테이블을 표시합니다.

![통합 문서에 있는 모든 데이터 블록의 목록입니다.](./assets/image52.png){zoomable="yes"}

![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을(를) 사용하여 표시할 열을 선택할 수 있습니다.

## 데이터 블록 정렬

표시된 열을 기준으로 데이터 블록 테이블을 정렬할 수 있습니다. 예를 들어 데이터 보기, 세그먼트, 날짜 범위 및 기타 변수를 기준으로 데이터 블록을 정렬할 수 있습니다.

데이터 블록 테이블을 정렬하려면 열 머리글을 선택합니다. 정렬 순서를 반대로 하려면 동일한 열 머리글을 선택합니다.


## 데이터 블록 검색

![검색](/help/assets/icons/Search.svg) **[!UICONTROL _검색_]** 필드를 사용하여 데이터 블록 테이블에서 원하는 항목을 찾습니다. 예를 들어 데이터 블록 또는 데이터 보기에 포함된 지표를 검색할 수 있습니다. 날짜 범위, 수정된 날짜 또는 마지막 실행 날짜 열에 표시되는 날짜를 검색할 수도 있습니다.


## 데이터 블록 편집

데이터 보기 및 날짜 범위 데이터 블록을 편집할 수 있습니다. 또는 데이터 블록에 적용된 세그먼트입니다.

예를 들어 하나 이상의 데이터 블록에서 기존 세그먼트를 새 세그먼트로 바꿀 수 있습니다.

1. 업데이트할 데이터 블록을 선택합니다. 최상위 확인란을 선택하여 모든 데이터 블록을 선택하거나 개별 데이터 블록을 선택할 수 있습니다.

   ![연필 편집 아이콘](./assets/image56.png){zoomable="yes"}

1. ![편집](/help/assets/icons/Edit.svg)을 선택하여 **[!UICONTROL 빠른 편집]** 창을 표시합니다.

   ![빠른 편집 창](./assets/image58.png){zoomable="yes"}

1. 데이터 보기, 날짜 범위 또는 세그먼트를 업데이트하는 링크를 선택합니다. **[!UICONTROL 빠른 편집]** - **[!UICONTROL 세그먼트]**&#x200B;에서 선택한 데이터 블록의 세그먼트를 추가, 제거 또는 업데이트할 수 있습니다.

   ![빠른 편집 창의 세그먼트 추가 필드](./assets/image59.png){zoomable="yes"}

## 데이터 블록 새로 고침

데이터 블록 테이블을 새로 고치려면 ![새로 고침](/help/assets/icons/Refresh.svg)을 선택하세요.

데이터 블록이 새로 고쳐졌는지 확인하려면 새로 고침 상태 아이콘을 표시합니다.

- 데이터 블록을 새로 고침하면 ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg)이 표시됩니다.

- 새로 고침에 실패한 데이터 블록에 ![AlertRed](/help/assets/icons/AlertRed.svg)이(가) 표시됩니다.


## 데이터 블록 삭제

하나 이상의 데이터 블록을 삭제하려면 다음을 수행합니다.

1. 하나 이상의 데이터 블록을 선택합니다.
1. ![삭제](/help/assets/icons/Delete.svg)를 선택합니다.
1. 삭제를 취소하려면 **[!UICONTROL 데이터 블록 삭제]** 대화 상자에서 **[!UICONTROL 삭제]**&#x200B;를 선택하거나 **[!UICONTROL 취소]**&#x200B;를 선택합니다.

## 그룹 데이터 블록

**[!UICONTROL 그룹화 기준]** 드롭다운 메뉴를 사용하여 데이터 블록을 그룹화하거나 열 제목을 선택할 수 있습니다.

데이터 블록을 열별로 정렬하려면 열 제목을 선택합니다. 데이터 블록을 그룹별로 그룹화하려면 **[!UICONTROL 그룹화 기준]** 드롭다운 메뉴에서 그룹 이름을 선택합니다. 예를 들어 아래 스크린샷에는 데이터 보기별로 그룹화된 데이터 블록이 표시됩니다.

그룹화를 사용하여 세그먼트와 같은 공통 요소를 수정할 데이터 블록을 빠르게 선택할 수 있습니다.

![시트별 그룹 목록을 표시하는 데이터 블록 관리자](./assets/group-data-blocks.png){zoomable="yes"}

