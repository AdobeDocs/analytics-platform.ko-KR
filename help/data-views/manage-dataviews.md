---
title: 데이터 보기 관리
description: 데이터 보기를 관리하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cb5baf2ec8d3ad4449a9b08d0a025a2d39a11425
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 11%

---


# 데이터 보기 관리


[하나 이상의 데이터 보기를 만들거나 편집한 경우](/help/data-views/create-dataview.md), **[!UICONTROL 데이터 보기]**&#x200B;에서 관리할 수 있습니다.

Customer Journey Analytics의 기본 메뉴 모음에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.

**[!UICONTROL 데이터 보기]** 인터페이스는 사용 가능한 모든 데이터 보기의 테이블을 표시합니다.

![데이터 보기 인터페이스](/help/data-views/assets/data-views.png)

표에서 사용할 수 있는 열과 아이콘은 다음과 같습니다.

| 열 또는 아이콘 | 설명 |
| --- | --- |
| **[!UICONTROL 이름]** | 데이터 보기의 이름입니다. |
| ![정보](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | 데이터 보기에 대한 정보를 보려면 데이터 보기 이름 옆에 있는 ![InfoOutline](/help/assets/icons/InfoOutline.svg)을(를) 선택하십시오.<br/>데이터 보기에 대한 세부 정보가 팝업 창에 표시됩니다. |
| ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | ![자세히](/help/assets/icons/More.svg)를 선택하여 컨텍스트 메뉴를 엽니다. 데이터 보기에서 <br/>![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]** - [편집](#edit-data-views)을(를) 선택할 수 있습니다.<br/>![복사](/help/assets/icons/Copy.svg) **[!UICONTROL 복사]**&#x200B;를 [데이터 보기를 복사](#copy-data-views)합니다.데이터 보기에서 <br/>![삭제](/help/assets/icons/Delete.svg) **[!UICONTROL 삭제]**(으)로 [삭제](#delete-data-views)<br/>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV로 내보내기]**&#x200B;에서 [데이터 보기의 세부 사항을 CSV 파일로 내보내기](#export-data-views-to-csv)로 내보내기.데이터 보기를 위해 <br/>![프로젝트 추가](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL 프로젝트 만들기]** ~ [새 Workspace 프로젝트 만들기](#create-project-from-data-views). |
| **[!UICONTROL 연결]** | 데이터 보기와 연결된 연결의 이름입니다. |
| **[!UICONTROL 샌드박스]** | 데이터 보기와 연결된 샌드박스의 이름입니다. |
| **[!UICONTROL 소유자]** | 데이터 보기의 소유자입니다. |
| **[!UICONTROL Data Insights Agent]** ![InfoOutline](/help/assets/icons/InfoOutline.svg) | 데이터 보기에 대해 [Data Insights Agent](/help/data-analysis-ai.md)이(가) **[!UICONTROL 활성화됨]** 또는 **[!UICONTROL 비활성화됨]**&#x200B;인지 여부를 나타냅니다. <br/>데이터 보기에서 ![Data Insights Agent 상태](/help/assets/icons/InfoOutline.svg)의 팝업을 표시하려면 **[!UICONTROL InfoOutline]**&#x200B;을(를) 선택하십시오. <br/>![Data Insights Agent 사용](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL 통합]** | 다른 솔루션과 통합 나열 예: Adobe Audience Analysis, Content Analytics, Brand Concierge, Journey Optimizer, GenStudio 및 사용 분석. |
| **[!UICONTROL CJA에서 사용]** | Customer Journey Analytics에서 데이터 보기를 사용하는지 여부를 나타냅니다. 이 값은 Adobe Journey Optimizer 통합의 일부로 자동으로 생성되는 데이터 보기의 경우에만 **[!UICONTROL 해제]**&#x200B;입니다. |
| **[!UICONTROL 생성된 일자]** | 데이터 보기가 생성된 타임스탬프. |
| **[!UICONTROL 마지막 수정일]** | 데이터 보기가 가장 최근에 수정된 타임스탬프입니다. |

테이블에 표시할 열을 구성하려면 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을 선택합니다. **[!UICONTROL 표 사용자 지정]** 대화 상자에서 표시할 열을 선택합니다. 그런 다음 **[!UICONTROL 적용]**&#x200B;을 선택합니다.


## 데이터 보기 검색

![검색](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) 상자를 사용하여 데이터 보기를 빠르게 검색할 수 있습니다.

## 데이터 보기 필터링

데이터 보기 목록에 필터를 적용하려면 ![필터](/help/assets/icons/Filter.svg) 아이콘을 선택한 후 다음 필터 옵션 중에서 선택합니다.

| 필터 옵션 | 설명 |
|---------|----------|
| **[!UICONTROL 연결]** | 선택한 연결과 연결된 데이터 보기만 표시됩니다. |
| **[!UICONTROL 소유자]** | 선택한 사람이 소유한 데이터 보기만 표시됩니다. |
| **[!UICONTROL 샌드박스]** | 선택한 샌드박스에서 사용할 수 있는 데이터 보기만 표시됩니다. |
| **[!UICONTROL 통합]** | 선택한 통합이 있는 데이터 보기만 표시됩니다. |
| **[!UICONTROL CJA에서 사용]** | Customer Journey Analytics에서 사용할 수 있는 데이터 보기만 표시하려면 **[!UICONTROL 켜짐]**&#x200B;을 선택하세요. Customer Journey Analytics에서 사용할 수 있도록 아직 활성화되지 않은 데이터 보기만 표시하려면 **[!UICONTROL 해제]**&#x200B;를 선택하십시오. |


## 데이터 보기 만들기

[새 데이터 보기를 만들려면](/help/data-views/create-dataview.md) **[!UICONTROL 새 데이터 보기 만들기]**&#x200B;를 선택하십시오.


## 데이터 보기 편집

[데이터 보기를 편집](/help/data-views/create-dataview.md)하려면:

1. 데이터 보기 이름 옆에 있는 ![자세히](/help/assets/icons/More.svg)를 선택합니다.
1. 컨텍스트 메뉴에서 ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]**&#x200B;을 선택합니다.

또는 다음과 같은 작업을 수행할 수 있습니다.

1. 데이터 보기 행을 선택합니다.
1. 파란색 작업 표시줄에서 ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]**&#x200B;을 선택합니다.


## 데이터 보기 복사

데이터 보기를 복사하려면 다음을 수행합니다.

1. 데이터 보기 이름 옆에 있는 ![자세히](/help/assets/icons/More.svg)를 선택합니다.
1. 컨텍스트 메뉴에서 ![복사](/help/assets/icons/Copy.svg) **[!UICONTROL 복사]**&#x200B;를 선택합니다.

또는 다음과 같은 작업을 수행할 수 있습니다.

1. 하나 이상의 데이터 보기 행을 선택합니다.
1. 파란색 작업 표시줄에서 ![복사](/help/assets/icons/Copy.svg) **[!UICONTROL 복사]**&#x200B;를 선택합니다.

데이터 보기가 복사되고 이름에 **[!UICONTROL (복사)]**&#x200B;이(가) 추가된 목록에 추가됩니다.


## 데이터 보기 삭제

데이터 보기를 삭제하려면 다음을 수행합니다.

1. 데이터 보기 이름 옆에 있는 ![자세히](/help/assets/icons/More.svg)를 선택합니다.
1. 컨텍스트 메뉴에서 ![삭제](/help/assets/icons/Delete.svg) **[!UICONTROL 삭제]**&#x200B;를 선택합니다.

또는 다음과 같은 작업을 수행할 수 있습니다.

1. 하나 이상의 데이터 보기 행을 선택합니다.
1. 파란색 작업 표시줄에서 ![삭제](/help/assets/icons/Delete.svg) **[!UICONTROL 삭제]**&#x200B;를 선택합니다.

하나 이상의 데이터 보기를 삭제하면 **[!UICONTROL 데이터 보기 삭제]** 패널이 영향을 받는 프로젝트를 나타냅니다.

![데이터 보기 삭제](/help/data-views/assets/delete-data-view.png)


* ➊ **[!UICONTROL 확인]**&#x200B;에서 데이터 보기 삭제의 의미가 표시됩니다.
* 데이터 보기를 영구적으로 삭제하려면 **[!UICONTROL 삭제]**&#x200B;를 선택하십시오. 취소하려면 **[!UICONTROL 취소]**&#x200B;를 선택합니다.


## 데이터 보기를 CSV로 내보내기

데이터 보기를 CSV 파일로 내보낼 수 있습니다.

1. 데이터 보기 이름 옆에 있는 ![자세히](/help/assets/icons/More.svg)를 선택합니다.
1. 컨텍스트 메뉴에서 ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV로 내보내기]**&#x200B;를 선택합니다.

또는 다음과 같은 작업을 수행할 수 있습니다.

1. 하나 이상의 데이터 보기 행을 선택합니다.
1. 파란색 작업 표시줄에서 ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV로 내보내기]**&#x200B;를 선택합니다.

선택한 데이터 보기의 세부 정보를 브라우저의 다운로드 폴더에 있는 `Data views List (x).csv` CSV 파일로 내보냅니다.


## 데이터 보기에서 프로젝트 만들기

데이터 보기 인터페이스에서 직접 Workspace 프로젝트를 만들 수 있습니다.

1. 데이터 보기 이름 옆에 있는 ![자세히](/help/assets/icons/More.svg)를 선택합니다.
1. 컨텍스트 메뉴에서 ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL 프로젝트 만들기]**&#x200B;를 선택합니다.

또는 다음과 같은 작업을 수행할 수 있습니다.

1. 데이터 보기 행을 선택합니다.
1. 파란색 작업 표시줄에서 ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL 프로젝트 만들기]**&#x200B;를 선택합니다.


## Data Insights Agent에 대한 데이터 보기 활성화 또는 비활성화

[Data Insights Agent](/help/data-analysis-ai.md)에 대한 데이터 보기를 활성화하거나 비활성화할 수 있습니다.

1. 데이터 보기 이름 옆에 있는 ![자세히](/help/assets/icons/More.svg)를 선택합니다.
1. 컨텍스트 메뉴에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Data Insights Agent에 대해 사용]** 또는 ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Data Insights Agent에 대해 사용 안 함]**&#x200B;을 선택합니다.

또는 다음과 같은 작업을 수행할 수 있습니다.

1. Data Insights Agent에 대해 비활성화되거나 활성화된 데이터 보기 행을 하나 이상 선택합니다.
1. 파란색 작업 표시줄에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Data Insights Agent에 대해 사용]** 또는 ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Data Insights Agent에 대해 사용 안 함]**&#x200B;을 선택합니다.

