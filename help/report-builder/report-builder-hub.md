---
title: Report Builder 허브
description: Report Builder 허브에 대해 알아봅니다.
role: User
feature: Report Builder
type: Documentation
exl-id: 119bd0b5-0d07-407f-b6e9-ef43352bad31
solution: Customer Journey Analytics
source-git-commit: 1e19e0c79617d27c7039b695c70ca5026fcaf357
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 25%

---

# Report Builder 허브

Report Builder 허브는 Excel 리본 모음에서 ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**&#x200B;을(를) 선택하면 Excel 통합 문서 내에 표시되는 오른쪽 창입니다.

Report Builder 허브를 사용하여 데이터 블록을 만들거나 업데이트하거나 삭제하거나 관리합니다.

Report Builder 허브에는 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 만들기]**, ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL 관리]** 및 ![일정](/help/assets/icons/Calendar.svg) **[!UICONTROL 일정]** 단추, **[!UICONTROL 명령]** 패널 및 **[!UICONTROL 빠른 편집]** 패널이 있습니다.

![Report Builder 허브](assets/hub51.png){zoomable="yes"}


선택

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 만들기]** - [새 데이터 블록 만들기](create-a-data-block.md).
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL 관리]** - [기존 데이터 블록 관리](manage-reportbuilder.md).
* ![일정](/help/assets/icons/Calendar.svg) **[!UICONTROL 일정]**&#x200B;에서 [전자 메일로 통합 문서를 보낼 일정을 관리](schedule-reportbuilder.md)합니다.

## 명령 패널

**[!UICONTROL 명령]** 패널을 사용하여 선택한 셀 또는 이전 작업과 호환되는 명령에 액세스합니다.

| 명령 | 사용 가능한 경우... | 용도 |
|------|------------------|--------|
| ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 데이터 블록 편집]** | 선택한 셀 또는 셀 범위는 하나의 데이터 블록에만 속합니다. | 데이터 블록을 편집하는 데 사용합니다. |
| ![새로 고침](/help/assets/icons/Refresh.svg) **[!UICONTROL 데이터 블록 새로 고침]** | 선택 항목에 하나 이상의 데이터 블록이 포함되어 있습니다. 명령은 선택 항목의 데이터 블록만 새로 고칩니다. | 하나 이상의 데이터 블록을 새로 고치는 데 사용합니다. |
| ![문서 새로 고침](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL 모든 데이터 블록 새로 고침]** | 통합 문서에는 하나 이상의 데이터 블록이 있습니다. | 통합 문서의 모든 데이터 블록을 새로 고치는 데 사용 |
| ![보내기](/help/assets/icons/Send.svg) **[!UICONTROL 통합 문서 보내기]** | 통합 문서에는 하나 이상의 데이터 블록이 있습니다. | [전자 메일로 통합 문서를 파일로 보내기](schedule-reportbuilder.md)하는 데 사용합니다. |
| ![복사](/help/assets/icons/Copy.svg) **[!UICONTROL 데이터 블록 복사]** | 선택한 셀 또는 셀 범위가 하나 이상의 데이터 블록의 일부입니다. | 데이터 블록을 복사하는 데 사용합니다. |
| ![잘라내기](/help/assets/icons/Cut.svg) **[!UICONTROL 데이터 블록 잘라내기]** | 선택한 셀 또는 셀 범위가 하나 이상의 데이터 블록의 일부입니다. | 데이터 블록을 잘라냅니다. |
| ![삭제](/help/assets/icons/Delete.svg) **[!UICONTROL 데이터 블록 삭제]** | 선택한 셀 또는 셀 범위는 하나의 데이터 블록에만 속합니다. | 데이터 블록을 삭제하는 데 사용 |

## 빠른 편집 패널

스프레드시트에서 하나 이상의 데이터 블록을 선택하면 Report Builder에 **[!UICONTROL 빠른 편집]** 패널이 표시됩니다. **[!UICONTROL 빠른 편집]** 패널을 사용하여 하나 이상의 데이터 블록의 매개 변수를 동시에 변경할 수 있습니다.

**[!UICONTROL 빠른 편집]** 섹션을 사용할 때 변경한 내용은 선택한 모든 데이터 블록에 적용됩니다.

### 데이터 보기

데이터 블록은 선택한 데이터 보기에서 데이터를 가져옵니다. 워크시트에서 여러 데이터 블록이 선택되어 있고 동일한 데이터 보기에서 데이터를 가져오지 않는 경우 **데이터 보기** 링크에 **[!UICONTROL _다중_]**&#x200B;이 표시됩니다.

데이터 보기를 변경하면 선택 항목의 모든 데이터 블록에 새 데이터 보기가 적용됩니다. 데이터 블록의 구성 요소는 ID를 기반으로 새 데이터 보기와 일치합니다. 데이터 블록에서 구성 요소를 찾을 수 없으면 구성 요소가 제거되고 **[!UICONTROL 잘못된 값]**(으)로 대체되거나 특정 구성 요소에 대해 ![AlertRed](/help/assets/icons/AlertRed.svg)이(가) 표시됩니다.

데이터 보기를 변경하려면 **[!UICONTROL 데이터 보기]** 드롭다운 메뉴에서 새 데이터 보기를 선택하십시오.


### 날짜 범위

**날짜 범위**&#x200B;는 선택한 데이터 블록의 날짜 범위를 보여 줍니다. 여러 날짜 범위가 있는 여러 데이터 블록을 선택한 경우 **[!UICONTROL 날짜 범위]** 링크에 **[!UICONTROL _다중_]**&#x200B;이 표시됩니다.

### 세그먼트

**세그먼트** 링크는 선택한 데이터 블록에서 사용하는 세그먼트의 요약 목록을 표시합니다. 여러 세그먼트가 적용된 여러 데이터 블록을 선택한 경우 **세그먼트** 링크에 **[!UICONTROL _다중_]**&#x200B;이 표시됩니다.

>[!MORELIKETHIS]
>
>[데이터 보기 선택](select-data-view.md)
>[날짜 범위 선택](select-date-range.md)
>[필터 ](work-with-filters.md) 작업
>
