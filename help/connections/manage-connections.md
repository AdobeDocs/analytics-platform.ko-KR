---
title: Customer Journey Analytics에서 연결을 관리하는 방법 알아보기
description: Customer Journey Analytics에서 Experience Platform 데이터 세트에 대한 연결을 관리하는 방법을 설명합니다.
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: f229b6c9241660d3e8a386638ae68d4cb3627ba1
workflow-type: tm+mt
source-wordcount: '4163'
ht-degree: 74%

---

# 연결 관리 {#manage-connections}

>[!CONTEXTUALHELP]
>id="connections_use_ajo"
>title="Journey Optimizer 연결 사용"
>abstract="Journey Optimizer과 함께 고급 Customer Journey Analytics 보고 기능을 활용합니다."

>[!CONTEXTUALHELP]
>id="connections_cancel_ajo"
>title="Journey Optimizer 연결 취소"
>abstract="Journey Optimizer의 고급 Customer Journey Analytics 보고 기능을 취소합니다."


[연결을 한 개 이상 만들거나 편집](/help/connections/create-connection.md)하면 **[!UICONTROL 연결]**&#x200B;에서 해당 연결을 관리할 수 있습니다. [!UICONTROL 연결] 인터페이스를 사용하면 다음 작업을 수행할 수 있습니다.

* 연결의 소유자, 샌드박스, 연결 생성 및 수정 시간에 관한 정보를 포함하여 모든 연결을 한눈에 볼 수 있습니다.
* 연결을 편집할 수 있습니다.
* 연결을 삭제할 수 있습니다.
* 연결에서 데이터 보기를 만들 수 있습니다.
* 모든 데이터 세트를 연결하여 볼 수 있습니다.
* 연결의 데이터 세트 및 수집 프로세스의 상태를 확인할 수 있습니다. 예를 들어 Analysis Workspace에서 보고 및 분석을 시작할 수 있도록 데이터를 언제 사용할 수 있는지 알 수 있습니다.
* 구성 오류로 인해 발생하는 모든 데이터 불일치를 식별할 수 있습니다. 혹시 누락된 행이 있습니까? 그렇다면 어떤 행이 누락되었고 이유는 무엇입니까? 연결을 잘못 구성하여 Customer Journey Analytics에서 데이터가 누락되었습니까?
* 모든 연결에서 수집된 행과 보고 가능한 행의 사용에 대한 인사이트를 얻을 수 있습니다.

[!UICONTROL 연결]에는 [[!UICONTROL 목록]](#list)과 [[!UICONTROL 사용]](#usage)이라는 두 가지 인터페이스가 있습니다.


## 목록

**[!UICONTROL 목록]** 인터페이스는 연결의 기본 인터페이스입니다. 선택하지 않은 경우, **[!UICONTROL 목록]** 탭을 선택하여 인터페이스에 액세스합니다.

![목록 보기](assets/list-view.png)

[!UICONTROL 목록] 인터페이스는 사용 가능한 모든 연결의 테이블을 보여 줍니다. 검색 ![검색](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) 상자를 사용하여 연결을 빠르게 검색할 수 있습니다.

테이블에서 사용할 수 있는 열이나 아이콘은 다음과 같습니다.

| 열 또는 아이콘 | 설명 |
| --- | --- |
| **[!UICONTROL _이름_]** | 연결에 대한 친숙한 이름입니다. [연결의 세부 정보](#connection-details)를 보려면 하이퍼링크 이름을 선택하십시오. |
| ![정보](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | [!UICONTROL 데이터 세트 포함], [!UICONTROL 샌드박스], [!UICONTROL 소유자] 등에 대한 정보를 보려면 연결 이름 옆에 있는 ![정보](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)를 선택합니다.<p>팝업 창에 데이터 세트에 대한 세부 정보가 표시됩니다. <p>![연결 정보 팝업](assets/connection-info-popup.png) |
| ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 컨텍스트 메뉴를 열려면 ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)를 선택하십시오. 다음 항목을 선택할 수 있습니다. <p>연결을 ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 편집]**&#x200B;하여 [편집](#edit-a-connection)하세요.<p>연결을 ![삭제](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 삭제]**(으)로 [삭제](#delete-a-connection)합니다.<p>연결을 위해 ![데이터 보기](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 새 데이터 보기 만들기]**&#x200B;에서 [새 데이터 보기 만들기](#create-a-data-view)로 이동합니다.<p>![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 연결 맵]**&#x200B;을(를) 사용하여 연결에 대한 [연결 맵](#map-a-connection)을(를) 봅니다. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}<br/>**[!UICONTROL 연결 유형&#x200B;]** | 연결 유형: **[!UICONTROL 사용자]** 기반 또는 **[!UICONTROL 계정]** 기반 연결. |
| **[!UICONTROL 데이터 세트]** | 연결의 일부인 데이터 세트에 대한 하나 이상의 링크. 데이터 세트 하이퍼링크를 선택하면 이 연결의 데이터 세트를 볼 수 있습니다. 선택한 연결에 더 많은 데이터 세트가 포함된 경우, **[!UICONTROL +*x* 자세히]**&#x200B;를 선택하여 **[!UICONTROL 데이터 세트 포함]** 패널을 표시합니다. 이 패널에는 모든 데이터 세트에 대한 링크와 연결에 포함된 특정 데이터 세트를 ![검색](/help/assets/icons/Search.svg)하는 옵션이 표시됩니다.<p>![데이터 세트 포함됨](assets/datasets-included.png)<p>데이터 세트 이름을 선택하여 새 탭에서 Experience Platform 인터페이스에서 데이터 세트를 엽니다. |
| **[!UICONTROL 샌드박스]** | 이 연결이 데이터 세트를 가져오는 출처가 되는 [Experience Platform 샌드박스](https://experienceleague.adobe.com/ko/docs/experience-platform/sandbox/home). 이 샌드박스는 연결을 만들 때 선택합니다. 연결이 저장되면 샌드박스를 변경할 수 없습니다. |
| **[!UICONTROL 소유자]** | 연결을 만든 사람입니다. |
| **[!UICONTROL 새 데이터 가져오기]** | 데이터 세트에 대한 새 데이터 가져오기 상태: <p>![녹색 상태](assets/status-green.svg)   새 데이터를 가져오도록 구성된 데이터 세트의 경우 **[!UICONTROL _x _켜짐]**<p>![상태 회색](assets/status-gray.svg)   **[!UICONTROL _x 꺼짐_]** 새 데이터를 가져오도록 구성되지 않은 데이터 세트의 경우. |
| **[!UICONTROL 생성된 일자]** | 연결을 처음 만든 타임스탬프. |
| **[!UICONTROL 마지막 수정일]** | 연결을 마지막으로 업데이트한 타임스탬프. |
| **[!UICONTROL 채우기 데이터]** | 데이터 세트 전체의 채우기 데이터 상태.<p>![상태 빨간색](assets/status-red.svg)   **[!UICONTROL _x _채우기 실패]**&#x200B;데이터 세트 전체에서 실패한 채우기 수에 대해,<p>![상태 주황색](assets/status-orange.svg)   **[!UICONTROL _x _채우기 처리]**&#x200B;데이터 세트 전체의 처리 채우기 수에 대해,<p>![상태 녹색](assets/status-green.svg)   **[!UICONTROL _x _채우기 완료]**&#x200B;데이터 세트에 대해 완료된 채우기 수에 대해<p>![상태 회색](assets/status-gray.svg)   **[!UICONTROL _꺼짐_]** 연결에 있는 데이터 세트에 대해 채우기가 정의되지 않은 경우. |

테이블에 표시할 열을 구성하려면 ![열 설정](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)을 선택합니다. 표 맞춤화 대화 상자에서 표시할 열을 선택합니다.

### 연결 편집

연결을 편집하는 방법은 다음과 같습니다.

1. 연결 이름 옆에 있는 ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)를 선택합니다.
1. 컨텍스트 메뉴에서 ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 편집]**&#x200B;을 선택합니다.

또는 다음과 같은 작업을 수행할 수 있습니다.

1. 연결 행을 선택합니다.

1. 파란색 작업 표시줄에서 ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 편집]**&#x200B;을 선택합니다.

자세한 내용은 [연결 만들기 또는 편집](create-connection.md)을 참조하십시오.


### 연결 삭제 {#connections-delete}

연결을 삭제하는 방법은 다음과 같습니다.

1. 연결 이름 옆에 있는 ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)를 선택합니다.
1. ![삭제](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 삭제]**&#x200B;를 선택합니다.

또는 다음과 같은 작업을 수행할 수 있습니다.

1. 연결 행을 선택합니다.

1. 파란색 작업 표시줄에서 ![삭제](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 삭제]**&#x200B;을(를) 선택합니다.

연결을 삭제하면 **[!UICONTROL 연결 삭제]** 패널에 어떤 데이터 보기가 삭제되고 어떤 작업 영역 프로젝트가 영향을 받는지가 표시됩니다.

* ➊ **[!UICONTROL 정보]**&#x200B;에서 연결 삭제의 의미가 표시됩니다.

  ![연결 삭제](assets/delete-connection.png)

  **[!UICONTROL 계속]**&#x200B;을 선택하여 삭제를 확인합니다.

* ➋ **[!UICONTROL 확인]**&#x200B;에서 **[!UICONTROL 연결 이름 입력]**&#x200B;에 연결 이름을 입력하고 **[!UICONTROL 삭제]**&#x200B;를 선택하여 연결을 삭제합니다. 취소하려면 **[!UICONTROL 취소]**&#x200B;를 선택합니다.

연결 삭제에 대한 자세한 내용은 [삭제 영향](/help/technotes/deletion.md)을 참조하십시오.


### 연결에 대한 데이터 보기 만들기

연결에 대한 데이터 보기를 만들려면 다음을 수행하십시오.

1. 연결 이름 옆에 있는 ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)를 선택합니다.
1. ![데이터 보기 추가](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 새 데이터 보기 만들기]**&#x200B;를 선택합니다.

또는 다음과 같은 작업을 수행할 수 있습니다.

1. 연결 행을 선택합니다.

1. 파란색 작업 표시줄에서 ![데이터 보기 추가](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 데이터 보기 만들기]**&#x200B;를 선택합니다.

자세한 내용은 [데이터 보기 만들기 또는 편집](/help/data-views/create-dataview.md)을 참조하십시오.


### 연결 매핑

연결의 일부인 데이터 세트 간의 관계를 자세히 설명하는 [연결 맵](/help/connections/create-connection.md#connection-map)을 보려면 다음을 수행합니다.

1. 연결 이름 옆에 있는 ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)를 선택합니다.
1. ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 연결 맵]**&#x200B;을 선택합니다.

### 연결 세부 정보 {#connection-detail}

연결에 대한 세부 정보로 이동하려면 연결 테이블에서 하이퍼링크된 연결 이름을 선택합니다.

![위젯과 설정을 보여 주는 모든 데이터 세트 창](assets/conn-details.png)

연결 세부 정보 인터페이스는 연결 상태를 자세히 보여 줍니다. 다음과 같은 작업을 수행할 수 있습니다.

* 이를 통해 연결의 데이터 세트 상태 및 수집 프로세스 상태를 점검할 수 있습니다.
* 레코드 생략 또는 삭제를 초래한 구성 문제를 파악할 수 있습니다.
* 데이터를 보고에 사용할 수 있게 되는 시기를 알 수 있습니다.

| 사용자 인터페이스 | 설명 |
| --- | --- |
| ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 연결 편집]** | 연결 세부 정보를 편집하려면 ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 연결 편집]**&#x200B;을 선택합니다. 자세한 내용은 [연결 만들기 또는 편집](create-connection.md)을 참조하십시오. |
| **[!UICONTROL *데이터 세트 선택기&#x200B;*]** | 연결에 대한 세부 사항을 표시할 데이터 세트를 하나 또는 모두 선택하십시오. 다수의 데이터 세트를 선택할 수는 없습니다. 기본값은 **[!UICONTROL 모든 데이터 세트]**&#x200B;로 설정되어 있습니다. |
| **[!UICONTROL *날짜 범위 선택기&#x200B;*]** | 연결에 대한 세부 사항을 표시할 데이터 범위를 선택하십시오. 시작 날짜, 종료 날짜를 편집하거나 ![캘린더](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)를 선택하여 날짜 범위 선택기를 엽니다. 날짜 범위 선택기에서 미리 정의된 기간 중 하나(예: **[!UICONTROL 지난 6개월]**)를 사용하여 날짜 범위를 선택하거나 캘린더를 사용하여 시작 날짜와 종료 날짜를 선택합니다. 연결 세부 정보에 새 날짜 범위를 적용하려면 **[!UICONTROL 적용]**&#x200B;을 선택하세요. |
| **[!UICONTROL 이벤트 데이터 기록 사용 가능]** | **전체 연결에 대해** 보고 가능한 총 이벤트 데이터 세트 행 수. 이 카운트는 날짜 범위 또는 데이터 세트 선택과 독립적입니다. |
| [!UICONTROL **[!UICONTROL 지표]**] | 추가, 생략, 삭제된 이벤트, 조회, 프로필, 요약 데이터 세트 레코드와 추가된 배치 수를 요약합니다. 이 지표는 **선택한 데이터 세트 및 날짜 범위**&#x200B;를 기반으로 합니다.<p>**[!UICONTROL 세부 정보 확인]**&#x200B;을 선택하면 **[!UICONTROL 생략된 세부 정보 확인]** 팝업이 표시됩니다. 팝업에는 건너뛴 레코드 수와 모든 이벤트 데이터 세트 또는 선택한 데이터 세트의 이유가 나열됩니다.<p>![건너뛴 레코드](assets/skipped-records.png)<p>더 많은 정보가 담긴 ![정보](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)를 선택합니다. [!UICONTROL 빈 방문자 ID]와 같은 일부 건너뛴 이유로 팝업에 [쿼리 서비스](https://experienceleague.adobe.com/ko/docs/experience-platform/query/home)에서 데이터 집합에서 건너뛴 레코드를 쿼리하는 데 사용할 수 있는 **[!UICONTROL EQS에 대한 샘플 PSQL]**(쿼리 서비스에 대한 Experience Platform)이 표시됩니다. ![복사](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL EQS용 샘플 PSQL 복사]**&#x200B;를 선택해 SQL을 복사합니다. |
| **[!UICONTROL 추가된 레코드]** | 선택한 기간 **선택한 데이터 세트 및 날짜 범위에 대해 얼마나 많은 행이 추가되었는지 나타내는 시각화**. 10분마다 업데이트됩니다. |
| **[!UICONTROL 생략된 레코드]** | 선택한 기간 **선택한 데이터 세트 및 날짜 범위에 대해 얼마나 많은 행이 생략되었는지 보여 주는 시각화**. 기록 생략의 이유에는 타임스탬프 누락, 개인 ID 또는 계정 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"} 누락 또는 잘못된 ID 등이 포함됩니다. 10분마다 업데이트됩니다. <p>잘못된 ID(예: [!UICONTROL 개인 ID]에 `undefined` 또는 `00000000` 또는 특정 월에 1백만 번 이상 이벤트에 나타나는 숫자 및 문자의 조합이 사용되는 경우)는 특정 사용자 또는 개인의 속성으로 할당될 수 없는 ID입니다. 이러한 행은 시스템으로 수집될 수 없으며 오류 유발 수집 및 보고를 초래할 수 있습니다. 잘못된 개인 ID 또는 계정 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}을(를) 수정하려면 3가지 옵션이 있습니다.<ul><li>[결합](/help/stitching/overview.md)을 사용해서 정의되지 않은 또는 모두 영으로 된 사용자 ID를 유효한 사용자 ID로 변경합니다.</li><li>사용자 ID를 지우면 해당 ID는 수집 중에 건너뜁니다(잘못된 또는 모두 영으로 된 사용자 ID보다 선호됨).</li><li>데이터를 수집하기 전에 사용자의 시스템 내에서 모든 잘못된 사용자 ID를 수정합니다.</li></ul> |
| **[!UICONTROL 삭제된 레코드]** | 선택한 기간 **선택한 데이터 세트 및 날짜 범위에 대해 얼마나 많은 행이 삭제되었는지 보여 주는 시각화**. 예를 들어 누군가가 [!DNL Experience Platform]에서 데이터 세트를 삭제했을 수도 있습니다. 10분마다 업데이트됩니다.<p>일부 시나리오에서는 이 값에 결합이나 일부 조회 데이터 세트 업데이트와 같이 교체된 레코드도 포함될 수 있습니다. 이 예제를 생각해 보겠습니다.</p><ul><li>하나의 레코드를 XDM 개인 프로필 데이터 세트에 업로드하면 Customer Journey Analytics가 프로필 조회 데이터로 수집하도록 구성됩니다. 연결 세부 정보에서 이 데이터 세트에는 1개의 레코드가 추가되었다고 표시됩니다.</li><li>원본 레코드의 복제본을 동일한 AEP 데이터 세트에 업로드하면 이제 두 개의 레코드가 포함됩니다. Customer Journey Analytics는 프로필 또는 계정([!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}) 조회 데이터 세트에서 추가 레코드를 수집합니다. 프로필 또는 계정 레코드가 해당 개인 ID 또는 계정 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}에 대한 연결에서 이미 수집되어 있는 경우 Customer Journey Analytics은 이전 버전을 삭제하고 새 프로필 데이터를 추가합니다. Customer Journey Analytics은 수집된 개인 ID 또는 계정 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}에 대한 최신 프로필 조회 데이터만 유지하므로 연결 세부 정보에서 이 작업은 추가된 1개 레코드 및 삭제된 1개 레코드를 나타냅니다.</li><li>전체적으로 AEP 데이터 세트에는 동일한 두 개의 레코드가 포함되어 있습니다. 별도로, Customer Journey Analytics 연결 세부 정보는 수집된 데이터의 상태를 표시합니다. 이 프로필 데이터 세트에 대해 2개의 레코드가 추가되고 1개의 레코드가 삭제되었습니다. </li></ul> |
| ![검색](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | 데이터 세트 검색 필드. 데이터 세트 이름 또는 데이터 세트 ID로 데이터 세트 테이블을 검색할 수 있습니다. |
| [!UICONTROL 데이터 세트 테이블] | 연결에 포함된 데이터 세트입니다. 자세한 내용은 아래 표를 참조하십시오. 선택한 데이터 세트에 대한 연결 세부 정보만 표시하려면 단일 데이터 세트 ![SelectBox](/help/assets/icons/SelectBox.svg)을(를) 선택하십시오. 이는 **[!UICONTROL _데이터 집합 선택기_]**&#x200B;에서 데이터 집합을 선택하는 것과 같습니다. |

데이터 세트 테이블에는 각 데이터 세트에 대해 다음 열이 표시됩니다.

| 열 | 설명 |
| --- | --- |
| **[!UICONTROL 데이터 세트]** | 데이터 세트의 이름입니다. 하이퍼링크를 선택하면 Experience Platform UI에서 새 탭에서 데이터 세트를 열 수 있습니다. 해당 행이나 확인란을 선택하면 선택한 데이터 세트에 대한 세부 정보만 표시됩니다. |
| **[!UICONTROL 데이터 세트 ID]** | Experience Platform에서 생성한 데이터 세트 ID입니다. |
| **[!UICONTROL 추가된 레코드]** | 선택한 날짜 범위 동안 연결에 추가된 데이터 세트 레코드(행)의 수입니다. |
| **[!UICONTROL 생략된 레코드]** | 선택한 날짜 범위 동안 연결을 위한 데이터 전송 중 건너뛴 데이터 세트 레코드(행)의 수입니다. |
| **[!UICONTROL 삭제된 레코드]** | 선택한 날짜 범위 동안 연결에서 제거된 데이터 세트 레코드(행)의 수입니다. |
| **[!UICONTROL 추가된 배치]** | 선택한 날짜 범위 동안 연결에 추가된 배치 수입니다. |
| **[!UICONTROL 마지막으로 추가됨]** | 연결에 추가된 최신 일괄 처리의 타임스탬프. |
| **[!UICONTROL 데이터 소스 유형]** | 소스 유형. 연결에 데이터 세트를 추가할 때 소스 유형을 정의합니다. |
| **[!UICONTROL 데이터 세트 유형]** | [데이터 집합 형식](create-connection.md#dataset-types)입니다. 유형은 [!UICONTROL 이벤트], [!UICONTROL 프로필], [!UICONTROL 조회] 또는 [!UICONTROL 요약]일 수 있습니다. |
| **[!UICONTROL 스키마]** | 해당 데이터 세트가 기반으로 삼는 Experience Platform 스키마입니다. |
| **[!UICONTROL 새 데이터 가져오기]** | 데이터 세트에 대한 새 데이터 가져오기 상태: <p>![상태 녹색](assets/status-green.svg)   **[!UICONTROL _x _켜짐]**&#x200B;새 데이터를 가져오도록 구성된 데이터 세트의 경우<p>![상태 회색](assets/status-gray.svg)   **[!UICONTROL _x 꺼짐_]** 새 데이터를 가져오지 않도록 구성된 데이터 세트의 경우. |
| **[!UICONTROL 데이터 변환]** | 해당 B2B 조회 데이터 세트의 변환 상태. 자세한 내용은 [B2B 조회를 위해 데이터 세트 변환](transform-datasets-b2b-lookups.md)을 참조하십시오.<p>![상태 녹색](assets/status-green.svg)   **[!UICONTROL _x _켜짐]**&#x200B;변환이 가능한 해당 데이터 세트의 경우, <p>![상태 회색](assets/status-gray.svg)   **[!UICONTROL _x 꺼짐_]** 변환이 가능하지 않은 해당 데이터 세트의 경우<p>**[!UICONTROL 없음]** 다른 모든 데이터 세트에는 변환이 적용되지 않는 경우. |
| **[!UICONTROL 채우기 데이터]** | 데이터 세트의 채우기 데이터 상태.<p>![상태 빨간색](assets/status-red.svg)   **[!UICONTROL _x _채우기 실패]**&#x200B;실패한 채우기의 수에 대해,<p>![상태 빨간색](assets/status-orange.svg)   **[!UICONTROL _x _채우기 처리]**&#x200B;처리 채우기 수에 대해,<p>![상태 녹색](assets/status-green.svg)   **[!UICONTROL _x _채우기 완료]**&#x200B;완료된 채우기 수에 대해<p>![상태 회색](assets/status-gray.svg)   **[!UICONTROL _꺼짐_]** 채우기가 구성되지 않은 경우. |

>[!IMPORTANT]
>
>2021년 8월 13일 이전에 수집된 데이터는 [!UICONTROL 연결] 인터페이스에 반영되지 않습니다.
>

#### 연결 패널

데이터 세트 테이블에서 개별 데이터 세트를 선택하지 않으면 오른쪽 패널에 연결 옵션 및 세부 정보가 표시됩니다.

| 옵션 | 설명 |
| --- | --- |
| ![새로 고침](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 새로 고침]** | 연결을 새로 고치고 최근 추가된 레코드를 반영하려면 ![새로 고침](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 새로 고침]**&#x200B;을 선택합니다. |
| ![삭제](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 삭제]** | 이 연결을 [삭제](#delete-a-connection)합니다. |
| ![데이터 보기 추가](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 데이터 보기 만들기]** | 이 연결을 기반으로 [데이터 보기를 만듭니다](#create-a-data-view). 자세한 내용은 [데이터 보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/data-views)를 참조하십시오. |
| **[!UICONTROL 연결 이름]** | 연결의 알기 쉬운 이름. |
| **[!UICONTROL 연결 설명]** | 연결에 대한 설명입니다. |
| **[!UICONTROL 샌드박스]** | 이 연결이 데이터 세트를 가져오는 출처가 되는 [Experience Platform 샌드박스](https://experienceleague.adobe.com/ko/docs/experience-platform/sandbox/home). 이 샌드박스는 연결을 만들 때 선택합니다. 연결이 저장되면 샌드박스를 변경할 수 없습니다. |
| **[!UICONTROL 연결 ID]** | 연결에 대해 생성된 식별자. ![복사](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg)를 사용하여 값을 복사할 수 있습니다. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}<br/>**[!UICONTROL 기본 ID 유형&#x200B;]** | 연결의 기본 ID 유형: 사용자 기반 연결의 경우 **[!UICONTROL 개인]**, 계정 기반 연결의 경우 **[!UICONTROL 계정]**. |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}<br/>**[!UICONTROL 컨테이너&#x200B;]** | 연결에 대해 구성된 컨테이너입니다. |
| **[!UICONTROL 연결을 이용한 데이터 보기]** | 이 연결을 사용하는 데이터 보기입니다. |
| **[!UICONTROL 새 데이터 가져오기]** | 데이터 세트에 대한 새 데이터 가져오기 상태: <p>![상태 녹색](assets/status-green.svg)   **[!UICONTROL _x _켜짐]**&#x200B;새 데이터를 가져오기 위해 구성된 데이터 세트 수에 대해<p>![상태 회색](assets/status-gray.svg)   **[!UICONTROL _x 꺼짐_]** 새로운 데이터 가져오기가 꺼진 데이터 세트 수에 대해. |
| **[!UICONTROL 채우기 데이터]** | 데이터 세트에 대한 채우기 데이터 상태.<p>![상태 빨간색](assets/status-red.svg)   **[!UICONTROL _x _채우기 실패]**&#x200B;데이터 세트 전체에서 실패한 채우기 수에 대해,<p>![상태 빨간색](assets/status-orange.svg)   **[!UICONTROL _x _채우기 처리]**&#x200B;데이터 세트 전체의 처리 채우기 수에 대해,<p>![상태 녹색](assets/status-green.svg)   **[!UICONTROL _x _채우기 완료]**&#x200B;데이터 세트에 대해 완료된 채우기 수에 대해<p>![상태 회색](assets/status-gray.svg)   **[!UICONTROL _꺼짐_]** 연결에 있는 데이터 세트에 대해 채우기가 정의되지 않은 경우. |
| **[!UICONTROL 데이터 변환]** | 해당 B2B 조회 데이터 세트의 변환 상태. 자세한 내용은 [B2B 조회를 위해 데이터 세트 변환](transform-datasets-b2b-lookups.md)을 참조하십시오.<p>![상태 녹색](assets/status-green.svg)   **[!UICONTROL _x _켜짐]**&#x200B;변환이 가능한 데이터 세트 수에 대해. |
| **[!UICONTROL 작성자]** | 연결을 만든 사람의 이름. |
| **[!UICONTROL 마지막 수정일]** | 연결에 대한 마지막 변경의 타임스탬프. |
| **[!UICONTROL 마지막 수정자]** | 연결을 마지막으로 수정한 사람의 이름입니다. |

#### 데이터 세트 패널

데이터 세트 테이블에서 데이터 세트 열을 선택하면 연결 인터페이스의 오른쪽에 있는 패널에 선택한 데이터 세트의 세부 정보가 표시됩니다.

| 세부 사항 | 설명 |
| --- | --- |
| [!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}<br/>**[!UICONTROL 글로벌 계정 ID &#x200B;]** | 연결에 대한 글로벌 계정 ID로 지정한 ID입니다. 글로벌 계정 컨테이너가 구성된 계정 기반 연결에만 적용됩니다. |
| [!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}<br/>**[!UICONTROL 계정 ID &#x200B;]** | 연결에 대한 계정 ID로 지정한 ID입니다. 글로벌 계정 컨테이너가 구성되지 않은 계정 기반 연결에만 적용됩니다. |
| **[!UICONTROL 개인 ID]** | 연결에 대한 개인 ID로 지정한 ID입니다. |
| **[!UICONTROL 키]** | 조회 데이터 세트에 대해 지정한 키. |
| **[!UICONTROL 일치하는 키]** | 조회 데이터 세트에 대해 지정한 일치하는 키. |
| **[!UICONTROL 타임스탬프]** | 이벤트 데이터 세트에 대해 정의된 타임스탬프. |
| **[!UICONTROL 사용 가능한 레코드]** | 캘린더를 통해 선택한 특정 기간 동안 이 데이터 세트에 대해 수집된 행의 총 수. 데이터가 추가되고 난 후 보고에 표시되기까지의 지연 시간은 없습니다. 그러나 새로운 연결을 만들면 [지연 시간](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-faq)이 생깁니다. |
| **[!UICONTROL 추가된 레코드]** | 선택한 날짜 범위 동안 연결에 추가된 데이터 세트 레코드(행)의 수입니다. |
| **[!UICONTROL 생략된 레코드]** | 선택한 날짜 범위 동안 연결을 위한 데이터 전송 중 건너뛴 데이터 세트 레코드(행)의 수입니다. |
| **[!UICONTROL 추가된 배치]** | 연결에 추가된 배치 수입니다. |
| **[!UICONTROL 삭제된 레코드]** | 선택한 날짜 범위 동안 연결에서 제거된 데이터 세트 레코드(행)의 수입니다. |
| **[!UICONTROL 마지막으로 추가됨]** | 연결에 추가된 최신 일괄 처리의 타임스탬프. |
| **[!UICONTROL 새 데이터 가져오기]** | 데이터 세트에 대한 새 데이터 가져오기 상태: <p>![상태 녹색](assets/status-green.svg)   **[!UICONTROL _x _켜짐]**&#x200B;새 데이터를 가져오도록 구성된 데이터 세트의 경우<p>![상태 회색](assets/status-gray.svg)   **[!UICONTROL _x 꺼짐_]** 새 데이터를 가져오지 않도록 구성된 데이터 세트의 경우. |
| **[!UICONTROL 채우기 데이터]** | 데이터 세트의 채우기 데이터 상태.<p>![상태 빨간색](assets/status-red.svg)   **[!UICONTROL _x _채우기 실패]**&#x200B;실패한 채우기의 수에 대해,<p>![상태 빨간색](assets/status-orange.svg)   **[!UICONTROL _x _채우기 처리]**&#x200B;처리 채우기 수에 대해,<p>![상태 녹색](assets/status-green.svg)   **[!UICONTROL _x _채우기 완료]**&#x200B;완료된 채우기 수에 대해<p>![상태 회색](assets/status-gray.svg)   **[!UICONTROL _꺼짐_]** 채우기가 구성되지 않은 경우.<p>데이터 세트의 이전 채우기에 대한 개요가 있는 대화 상자를 표시하려면 선택합니다. <img src="./assets/pastbackfill.svg" alt="이전 채우기" width="15"/> **[!UICONTROL 이전 채우기]**. |
| **[!UICONTROL 데이터 소스 유형]** | 데이터 세트가 연결에 추가될 때 정의된 데이터 소스 유형입니다. |
| **[!UICONTROL 데이터 세트 유형]** | [데이터 집합 형식](create-connection.md#dataset-types)입니다. |
| **[!UICONTROL 스키마]** | 이 데이터 세트가 기반으로 삼는 Experience Platform 스키마. |
| **[!UICONTROL 데이터 세트 ID]** | Experience Platform에서 생성된 데이터 세트 ID. |


## 사용 {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="주요 사용 지표"
>abstract="핵심 및 내역 보고 가능 행에 대한 월별 및 전체 데이터를 제공합니다."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="월별 수집된 행"
>abstract="매달 시스템에 추가된 총 레코드 수를 측정하여 데이터 증가 및 수집 비율에 대한 인사이트를 제공합니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="월별 보고 가능한 행"
>abstract="보고에 사용할 수 있는 행 수를 추적합니다. 보고 가능한 행은 수집된 행에서 수집 중에 건너뛰거나 삭제된 행을 뺀 것입니다. 보고 가능한 행은 결제 및 데이터 사용량에 대한 주요 지표로 사용됩니다."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="세부 분류."
>abstract="연결, 데이터 세트, 샌드박스 및 태그별로 자세한 지표를 조회할 수 있으며, 데이터의 CSV 파일을 다운로드할 수도 있습니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="다른 데이터 세트"
>abstract="2024년 9월 이전 몇 개월 동안 데이터는 데이터 세트 수준에서 수집되었고, 명확성을 위해 *다른 데이터 세트*&#x200B;로 표시됩니다. 2024년 9월부터 데이터는 세부적인 데이터 세트 수준에서 수집되고 *다른 데이터 세트*&#x200B;는 더 이상 표시되지 않습니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="알 수 없는 데이터 세트나 연결"
>abstract="알 수 없는 데이터 세트나 연결은 해당 ID를 사용하여 표시합니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="데이터를 사용할 수 없음"
>abstract="시스템 제한으로 2024년 9월 이전의 내역 데이터는 사용할 수 없습니다. 2024년 9월부터 지표를 수집하여 표시합니다. 차트는 타임라인에서 지난 18개월을 보여 주며, 데이터가 제공됨에 따라 향후 데이터가 표시됩니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="핵심 보고 가능 행"
>abstract="지난 13개월 동안 사용 가능한 총 행 수입니다. 예: 2024년 2월 1일의 수는 2023년 1월부터 2024년 1월까지의 이벤트 타임스탬프에서 사용 가능한 합계 행을 보여 줍니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="내역 보고 가능 행"
>abstract="13개월 이상 지난 해당 기간의 사용 가능한 총 행 수입니다. 예: 2024년 2월 1일의 수는 2023년 1월 이전 이벤트 타임스탬프에서 사용 가능한 합계 행을 보여 줍니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="주요 사용 지표"
>abstract="핵심 및 내역 보고 가능 행에 대한 월별 및 전체 데이터를 제공합니다."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="월별 수집된 행"
>abstract="매달 시스템에 추가된 총 레코드 수를 측정하여 데이터 증가 및 수집 비율에 대한 인사이트를 제공합니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="월별 보고 가능한 행"
>abstract="보고에 사용할 수 있는 행 수를 추적합니다. 보고 가능한 행은 수집된 행에서 수집 중에 건너뛰거나 삭제된 행을 뺀 것입니다. 보고 가능한 행은 결제 및 데이터 사용량에 대한 주요 지표로 사용됩니다."
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="세부 분류."
>abstract="연결, 데이터 세트, 샌드박스 및 태그별로 자세한 지표를 조회할 수 있으며, 데이터의 CSV 파일을 다운로드할 수도 있습니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="다른 데이터 세트"
>abstract="2024년 9월 이전 몇 개월 동안 데이터는 데이터 세트 수준에서 수집되었고, 명확성을 위해 *다른 데이터 세트*&#x200B;로 표시됩니다. 2024년 9월부터 데이터는 세부적인 데이터 세트 수준에서 수집되고 *다른 데이터 세트*&#x200B;는 더 이상 표시되지 않습니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="알 수 없는 데이터 세트나 연결"
>abstract="알 수 없는 데이터 세트나 연결은 해당 ID를 사용하여 표시합니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="데이터를 사용할 수 없음"
>abstract="시스템 제한으로 2024년 9월 이전의 내역 데이터는 사용할 수 없습니다. 2024년 9월부터 지표를 수집하여 표시합니다. 차트는 타임라인에서 지난 18개월을 보여 주며, 데이터가 제공됨에 따라 향후 데이터가 표시됩니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="핵심 보고 가능 행"
>abstract="지난 13개월 동안 사용 가능한 총 행 수입니다. 예: 2024년 2월 1일의 수는 2023년 1월부터 2024년 1월까지의 이벤트 타임스탬프에서 사용 가능한 합계 행을 보여 줍니다."
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="내역 보고 가능 행"
>abstract="13개월 이상 지난 해당 기간의 사용 가능한 총 행 수입니다. 예: 2024년 2월 1일의 수는 2023년 1월 이전 이벤트 타임스탬프에서 사용 가능한 합계 행을 보여 줍니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="핵심 보고 가능 행"
>abstract="핵심 보고 가능 행은 집계된 합계가 아닌 스냅샷 값입니다. 이러한 값은 선택한 날짜 범위의 마지막 달을 기준으로 동적으로 업데이트됩니다. 고객이 1월~3월을 선택하는 경우, 값은 3월의 스냅샷을 반영합니다."

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="내역 보고 가능 행"
>abstract="내역 보고 가능 행은 집계된 합계가 아닌 스냅샷 값입니다. 이러한 값은 선택한 날짜 범위의 마지막 달을 기준으로 동적으로 업데이트됩니다. 고객이 1월~3월을 선택하는 경우, 값은 3월의 스냅샷을 반영합니다."

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="누적 보고 가능 행"
>abstract="누적 보고 가능 행은 집계된 합계가 아닌 스냅샷 값입니다. 이러한 값은 선택한 날짜 범위의 마지막 달을 기준으로 동적으로 업데이트됩니다. 고객이 1월~3월을 선택하는 경우, 값은 3월의 스냅샷을 반영합니다."

<!-- markdownlint-enable MD034 -->



[!UICONTROL 사용] 인터페이스는 모든 연결에서 수집되고 보고 가능한 행의 사용량을 보여 줍니다. 선택하지 않은 경우, **[!UICONTROL 사용]** 탭을 선택하여 인터페이스에 액세스합니다.

이 인터페이스는 Customer Journey Analytics 사용량이 계약상 합의된 내용을 준수하는지 여부를 확인할 수 있도록 지원합니다. 모니터링 목적 외에도 사용 인터페이스를 사용하여 Customer Journey Analytics 라이선스 갱신을 계획할 수 있습니다.

사용 인터페이스에서는 다음 지표를 사용합니다.

| 지표 이름 | 설명 |
|---|---|
| 내역 보고 가능 행 | 13개월 이상 기간에 대한 행의 수. |
| 핵심 보고 가능 행 | 지난 13개월 동안의 행 수. |
| 수집된 행 | 특정 기간 동안 수집된 행의 수. |
| 보고 가능한 행 | 특정 기간 동안 연결의 일부로 있는 데이터 행의 수. |
| 누적 행 | 특정 월까지 수집되는 행의 수. |

>[!NOTE]
>
>데이터는 2024년 7월부터 핵심, 과거 및 전체 기록에 대해 수집됩니다. 계정 관리자에게 이전 내역 데이터를 문의하십시오.
>



사용 인터페이스는 두 개의 패널로 구성됩니다.

* **[!UICONTROL 주요 사용 지표]** 패널: 보고 가능한 핵심 데이터와 내역 데이터를 행으로 제공합니다. 패널은 또한 핵심 데이터 행과 내역 데이터 행 모두에 대해 이전 달과 비교한 백분율 변화를 추적합니다.

  패널에 다음 항목이 포함된 시각화가 표시됩니다.

   * **[!UICONTROL 핵심 데이터 보고 가능 행]**.

     지난 13개월 동안 보고 가능한 행의 수. 요약 숫자는 지난달(예: 2024년 12월)의 핵심 보고 가능 행 수(예: 7억4천1백만)입니다.

   * **[!UICONTROL 내역 데이터 보고 가능 행]**.

     13개월을 넘은 기간에 대해 보고 가능한 행의 수. 요약 숫자는 지난달(예: 2024년 12월)의 내력 보고 가능 행 수(예: 1억2천7백만)입니다.

  시각화에서 스택 막대 위에 마우스를 가져다 대면 해당 막대의 특정 부분에 대한 행 수가 팝업으로 표시됩니다(예시).


  ![주요 사용 지표](assets/usage-key-usage-metrics.png)

* 다음에 대해 3개의 하위 패널을 보여 주는 결합 패널:

+++ 수집된 행

  **[!UICONTROL 수집된 행]**: 하위 패널을 매달 시스템에 추가된 총 레코드 수를 측정하여 데이터 증가 및 수집 비율에 대한 인사이트를 제공합니다. 하위 패널은 이번 달의 총 수집된 행 수와 이전 달과의 변화에 대한 요약을 제공합니다.

  ![수집된 행](assets/usage-ingested-rows.png)

  시각화의 데이터 포인트 위에 마우스를 가져다 대면 더 자세한 정보가 담긴 팝업이 표시됩니다.

+++

+++ 보고 가능한 행

  **[!UICONTROL 보고 가능한 행]**: 시각화는 건너뛴 행과 삭제된 행을 수집된 행에서 차감하여 보고에 사용할 수 있는 행 수를 추적하며, 이는 결제 및 데이터 사용량에 대한 주요 지표로 사용됩니다. 하위 패널에는 두 가지 요약이 제공됩니다.

   * **[!UICONTROL 지난달 총계]**: 이번 달까지의 보고 가능한 총 행의 요약.
   * **[!UICONTROL 이번 달]**: 이번 달의 총 보고 가능 행과 지난달 대비 변경 사항에 대한 요약.

  ![보고 가능한 행](assets/usage-reportable-rows.png)

  시각화의 데이터 포인트 위에 마우스를 가져다 대면 더 자세한 정보가 담긴 팝업이 표시됩니다.

+++

+++ 세부 분류

  **[!UICONTROL 세부 분류]** 테이블을 사용하면 연결, 데이터 세트, 샌드박스 및 태그별로 자세한 지표를 볼 수 있습니다. 데이터 세트 이름은 보고 기간 동안 수정될 수 있으므로, 데이터 세트는 이름 대신 ID를 사용하여 보고됩니다. 알 수 없는 데이터 세트나 연결은 ID를 사용하여 보고됩니다.

  2024년 9월 이전 몇 개월 동안 데이터는 데이터 세트 수준에서 수집되었고, 명확성을 위해 [!UICONTROL 다른 데이터 세트]로 표시됩니다. 2024년 9월부터 데이터는 세분화된 데이터 세트 수준으로 수집되며 [!UICONTROL 다른 데이터 세트]는 더 이상 나타나지 않습니다.

   * 세부 분류를 변경하려면 **[!UICONTROL 보기 기준]**&#x200B;과 **[!UICONTROL 분류 기준]**&#x200B;의 조합을 선택합니다.

     | **[!UICONTROL 보기 기준]** 옵션 | **[!UICONTROL 분류 기준]** 옵션 |
     |---|---|
     | **[!UICONTROL 연결]** | **[!UICONTROL -]** 및 **[!UICONTROL 데이터 세트]** |
     | **[!UICONTROL 데이터 세트]** | **[!UICONTROL -]** |
     | **[!UICONTROL 샌드박스]** | **[!UICONTROL 연결]** |
     | **[!UICONTROL 태그]** | **[!UICONTROL 연결]** |

  ![세부 분류](assets/usage-detail-breakdown.png)

+++

  보고할 **[!UICONTROL 시간 범위]**&#x200B;를 월 단위로 정의할 수 있습니다. ![캘린더](/help/assets/icons/Calendar.svg)를 사용하여 시간 범위를 선택합니다.

>[!MORELIKETHIS]
>
>[연결 설정 보기, 문제 해결 및 수정](https://experienceleague.adobe.com/ko/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja) 튜토리얼.
>&#x200B;>[Customer Journey Analytics 사용량 관리](/help/technotes/estimate-usage.md)
>
