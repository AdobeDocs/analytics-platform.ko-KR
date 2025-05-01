---
title: Report Builder에서 데이터 보기를 선택하는 방법
description: Adobe Report Builder에서 데이터 보기를 선택하는 방법을 설명합니다.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# 데이터 보기 선택

드롭다운 메뉴에서 데이터 보기를 선택하거나 셀에서 데이터 보기를 선택하여 데이터 블록을 새 데이터 보기로 자동으로 업데이트할 수 있습니다.

## 셀에서 데이터 보기 선택

셀에서 데이터 보기를 선택하면 다른 데이터 보기를 사용하여 데이터 블록을 쉽게 새로 고칠 수 있습니다. 별도의 데이터 블록을 사용하여 완전히 새로운 보고서를 작성하는 대신 셀에서 선택한 데이터 보기로 데이터 블록을 새로 고칠 수 있습니다.

다음과 같은 경우 셀에서 데이터 보기를 선택하면 유용합니다.

* 구조가 서로 유사하거나 동일한 여러 데이터 보기.
* 사용자 지정된 구성 요소 및 레이아웃을 포함하는 복잡한 데이터 블록 형식입니다.

셀에서 데이터 보기를 선택하려면 먼저 데이터 블록을 빌드하고 데이터 블록 외부의 셀에 여러 데이터 보기를 할당합니다. 그런 다음 **[!UICONTROL 셀의 데이터 보기]** 패널을 사용하여 다른 데이터 보기에서 데이터 블록을 새로 고칩니다.

1. 데이터 블록을 만듭니다. 데이터 블록 만들기에 대한 자세한 내용은 [데이터 블록 만들기](/help/report-builder/create-a-data-block.md)를 참조하십시오.

1. **[!UICONTROL 데이터 보기]**&#x200B;에서 ![데이터 보기 선택기](/help/assets/icons/DataViewSelector.svg)을(를) 선택합니다.

1. 데이터 블록 외부의 ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg)을(를) 사용하여 셀을 선택합니다.

1. 끌어서 놓기를 사용하여 **[!UICONTROL 셀의 데이터 보기에 추가할 데이터 보기 선택]**&#x200B;에서 하나 이상의 데이터 보기를 추가합니다. 또는 데이터 보기를 두 번 선택하여 **[!UICONTROL 포함된 데이터 보기]** 목록에 추가할 수 있습니다.

   * ![검색](/help/assets/icons/Search.svg) **[!UICONTROL _데이터 보기 선택_]**&#x200B;을 사용하여 데이터 보기를 검색할 수 있습니다.
   * ![MoreSmall](/help/assets/icons/MoreSmall.svg)을 사용하여 컨텍스트 메뉴를 열면 **[!UICONTROL 포함된 데이터 보기]** 목록에서 데이터 보기를 위아래로 이동할 수 있습니다.
   * ![CrossSize75](/help/assets/icons/CrossSize75.svg)을(를) 사용하여 **[!UICONTROL 포함된 데이터 보기]** 목록에서 데이터 보기를 삭제하십시오.

   ![셀에서 데이터 보기 선택](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. 선택한 데이터 보기를 선택한 셀에 적용하려면 **[!UICONTROL 적용]**&#x200B;을 선택합니다.


## 셀에서 데이터 보기 변경

1. 시트에서 데이터 보기 셀 위치를 선택합니다.
1. Report Builder 허브에서 **[!UICONTROL 빠른 편집]**&#x200B;의 **[!UICONTROL 셀에서 데이터 보기]** 링크를 선택합니다.
1. **[!UICONTROL 데이터 보기]** 드롭다운 메뉴에서 데이터 보기를 선택하십시오.

   ![셀에서 데이터 보기 변경](assets/change-data-view-from-cell.png){zoomable="yes"}
1. 선택 사항입니다. 변경 시 **[!UICONTROL 데이터 블록 새로 고침]**&#x200B;을 선택합니다.

1. **[!UICONTROL 적용]**&#x200B;을 선택합니다. Report Builder은 선택한 데이터 보기에 따라 데이터 블록을 새로 고칩니다.
