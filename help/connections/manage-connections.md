---
title: Customer Journey Analytics에서 연결을 관리하는 방법 알아보기
description: Customer Journey Analytics(Customer Journey Analytics)의 Experience Platform 데이터 세트에 대한 연결을 관리하는 방법을 설명합니다.
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 0cf1f69d5623a827cba64427c8db614b690968a0
workflow-type: tm+mt
source-wordcount: '2484'
ht-degree: 26%

---

# 연결 관리

다음 작업을 완료하면 [하나 이상의 연결을 만들거나 편집함](/help/connections/create-connection.md)에서 관리할 수 있습니다. **[!UICONTROL 연결]**. 연결을 통해 다음 작업을 수행할 수 있습니다.

* 소유자, 샌드박스 및 연결 생성 및 수정 시기를 포함하여 모든 연결을 한 눈에 볼 수 있습니다.
* 연결을 편집합니다.
* 연결을 삭제할 수 있습니다.
* 연결에서 데이터 보기를 만들 수 있습니다.
* 모든 데이터 세트를 연결하여 볼 수 있습니다.
* 연결의 데이터 세트 상태 및 수집 프로세스 상태를 확인합니다. 예를 들어, Analysis Workspace에서 보고 및 분석을 시작할 수 있도록 가 데이터를 사용하는 경우입니다.
* 구성 오류로 인해 발생하는 모든 데이터 불일치를 식별합니다. 혹시 누락된 행이 있습니까? 그렇다면 어떤 행이 누락되었고 이유는 무엇입니까? 연결을 잘못 구성하여 Customer Journey Analytics에서 데이터가 누락되었습니까?


표는 사용 가능한 모든 연결을 보여 줍니다. 검색을 사용하여 연결을 빠르게 검색할 수 있습니다 ![검색](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) 상자.

표에서 다음 열/아이콘을 사용할 수 있습니다.

| 열 / 아이콘 | 설명 |
| --- | --- |
| [!UICONTROL 이름] | 연결에 대한 친숙한 이름입니다. 연결 세부 정보를 보려면 하이퍼링크된 이름을 선택합니다. 다음을 참조하십시오 [연결 세부 정보](#connection-details). |
| ![정보](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | 다음에 대한 정보를 보려면 다음과 같이 하십시오. [!UICONTROL 데이터 세트 포함됨], [!UICONTROL 샌드박스], [!UICONTROL 소유자]외 을(를) 선택합니다 ![정보](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) 연결 이름 옆에 있습니다.<p>팝업 창에 세부 정보가 표시됩니다. <p><img src="./assets/conn-info.png" alt="연결 정보 보기" width="50%" /> |
| ![데이터 보기](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | 종료 [데이터 보기 만들기](#create-a-data-view) 연결에 대해 을 선택합니다. ![데이터 보기](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) . 이 아이콘은 데이터 보기가 연결에 이미 연결되어 있지 않은 경우에만 표시됩니다. |
| ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 선택 ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 끝: <p>![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [편집](#edit-a-connection) 연결입니다.<p>![삭제](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [삭제](#delete-a-connection) 연결입니다.<p>![데이터 보기](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [새 데이터 보기 만들기](#create-a-data-view). 연결에 대한 추가 데이터 보기를 만들 때 사용합니다. |
| [!UICONTROL 데이터 세트] | 연결에 포함된 데이터 세트에 대한 하나 이상의 링크를 표시합니다. 데이터 세트 하이퍼링크를 선택하여 연결에서 데이터 세트를 볼 수 있습니다. 선택한 연결에 포함된 데이터 세트가 더 있을 경우 **[!UICONTROL +*x* 기타]** 을 표시하려면 **[!UICONTROL 데이터 세트 포함됨]** 패널. 이 패널에는 모든 데이터 세트에 대한 링크와 연결에 포함된 특정 데이터 세트를 검색하는 옵션이 표시됩니다.<p><img src="./assets/datasets-included.png" alt="포함된 데이터 자산" width="50%" /><p>데이터 세트 이름을 선택하면 Experience Platform UI의 데이터 세트가 새 탭에서 열립니다. |
| [!UICONTROL 샌드박스] | 다음을 표시합니다. [Experience Platform 샌드박스](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) 이 연결이 데이터 세트를 가져오는 출처. 이 샌드박스는 처음에 이 연결을 만들었을 때 선택된 것이며 이는 변경할 수 없습니다. |
| [!UICONTROL 소유자] | 연결을 만든 사람입니다. |
| [!UICONTROL 새 데이터 가져오기] | 데이터 세트에 대한 새 데이터 가져오기 상태를 표시합니다. <p><span style="color:green">●</span>   **[!UICONTROL _x _날짜]**새 데이터를 가져오도록 구성된 데이터 세트 수에 대해 및&lt;/<p><span style="color:gray">●</span>   **[!UICONTROL _x 끄기_]** 새 데이터 가져오기 기능을 해제한 데이터 세트 수에 대해 설명합니다. |
| [!UICONTROL 만든 날짜] | 연결이 생성된 시점의 타임스탬프입니다. |
| [!UICONTROL 마지막 수정일] | 연결을 마지막으로 업데이트할 때의 타임스탬프입니다. |
| [!UICONTROL 채우기 데이터] | 데이터 세트 간 데이터 채우기의 상태를 표시합니다.<p><span style="color:red">●</span>   **[!UICONTROL _x _다시 채우기 실패]**데이터 세트 간 실패한 다시 채우기 횟수<p><span style="color:orange">●</span>   **[!UICONTROL _x _다시 채우기 처리 중]**데이터 세트 간 처리 다시 채우기 횟수<p><span style="color:green">●</span>   **[!UICONTROL _x _다시 채우기 완료됨]**데이터 세트에 대해 완료된 채우기 횟수<p><span style="color:grey">●</span>   **[!UICONTROL _끔_]** 연결의 데이터 세트에 대해 백필이 정의되지 않은 경우. |

을 사용하여 표시할 열을 구성할 수 있습니다. ![열 설정](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). 다음을 표시합니다. **표 맞춤화** 테이블에서 열을 설정/해제할 수 있는 대화 상자입니다.

## 연결 편집

관리자가 연결을 편집할 수 있습니다.

1. 선택 ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 연결 이름 옆에
1. 선택 ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 편집]** 컨텍스트 메뉴 아래의 제품에서 사용할 수 있습니다.

또는 다음을 수행할 수 있습니다.

1. 연결 행을 선택합니다.

1. 선택 ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 편집]** 파란색 막대에서.

연결을 편집할 때 다음 작업을 수행할 수 있습니다.

* 새 데이터 가져오기를 시작 및 중지합니다.
* 연결 이름을 변경할 수 있습니다.
* 데이터 세트를 새로 고칩니다.
* 연결에서 데이터 세트를 제거합니다.

다음을 참조하십시오 [연결 만들기 또는 편집](create-connection.md) 추가 정보.


## 연결 삭제 {#connections-delete}

관리자가 연결을 삭제할 수 있도록 허용합니다.

1. 선택 ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 연결 이름 옆에 있습니다.
1. 선택 ![삭제](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 삭제]**.

또는 다음을 수행할 수 있습니다.

1. 연결 행을 선택합니다.

1. 선택 ![삭제](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 삭제]** 파란색 막대에서.

연결을 삭제할 때 **[!UICONTROL 연결 삭제]** 패널은 삭제되는 데이터 보기와 영향을 받는 작업 영역 프로젝트를 나타냅니다.

<img src="./assets/delete-connection.png" alt="연결 삭제" width="50%" />

선택 **[!UICONTROL 계속]** 연결을 삭제합니다.

다음을 참조하십시오 [의미 삭제](/help/admin/cja-deletion.md) 연결 삭제의 의미에 대한 자세한 정보.


## 데이터 보기 만들기

관리자가 연결에 대한 데이터 보기를 만들 수 있습니다.

* 연결과 연결된 데이터 보기가 없는 경우:

   1. 선택 ![데이터 보기 추가](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) 연결 이름 옆에 있습니다.

* 연결에 대해 하나 이상의 데이터 보기가 이미 만들어진 경우:

   1. 선택 ![자세히](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 연결 이름 옆에 있습니다.
   1. 선택 ![데이터 보기 추가](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 새 데이터 보기 만들기]**.

또는 다음을 수행할 수 있습니다.

1. 연결 행을 선택합니다.

1. 선택 ![데이터 보기 추가](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 데이터 보기 만들기]** 파란색 단추 모음에서 를 클릭합니다.

자세한 내용은 [데이터 보기 만들기 또는 편집](/help/data-views/create-dataview.md)을 참조하십시오.

## 연결 세부 정보 {#connection-detail}

연결에 대한 세부 정보로 이동하려면 연결 테이블에서 연결 이름을 선택합니다.

![위젯 및 설정을 표시하는 모든 데이터 세트 창](assets/conn-details.png)

연결 세부 정보 인터페이스는 연결 상태에 대한 세부 보기를 제공합니다. 다음과 같은 작업을 수행할 수 있습니다.

* 이를 통해 연결의 데이터 세트 상태 및 수집 프로세스 상태를 점검할 수 있습니다.
* 레코드를 건너뛰거나 삭제할 수 있는 구성 문제를 식별합니다.
* 데이터를 보고에 사용할 수 있게 되는 시기를 알 수 있습니다.

| 사용자 인터페이스 | 설명 |
| --- | --- |
| ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL 연결 편집] | 연결의 세부 정보를 편집하려면 다음을 선택합니다. ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 연결 편집]** . 다음을 참조하십시오 [연결 만들기 또는 편집](create-connection.md) 추가 정보. |
| 데이터 세트 선택기 | 연결 안에 있는 한 개의 데이터 세트 또는 모든 데이터 세트를 선택할 수 있습니다. 다수의 데이터 세트를 선택할 수는 없습니다. 기본값은 [!UICONTROL 모든 데이터 세트]로 설정되어 있습니다. |
| 날짜 범위 선택기 | 시작 및/또는 종료 날짜를 편집하거나 선택 ![캘린더](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 을 클릭하여 데이터 범위 선택기를 엽니다. 날짜 범위 선택기에서 사전 정의된 기간(예: **[!UICONTROL 지난 6개월]**) 또는 달력을 사용하여 시작 날짜와 종료 날짜를 선택합니다. 선택 **[!UICONTROL 적용]** 새 데이터 범위를 적용합니다. |
| [!UICONTROL 사용 가능한 이벤트 데이터 레코드] | 전체 연결&#x200B;**에 대해 보고 가능한 총 이벤트 데이터 세트 행 수**&#x200B;를 나타냅니다. 이 수는 어떠한 달력 설정과도 관련이 없습니다. 카운트는 데이터 세트 선택기에서 또는 표에서 데이터 세트를 선택하면 변경됩니다. 데이터가 추가되면 보고에 데이터를 표시하는 데 1~2시간의 지연 시간이 있습니다. |
| [!UICONTROL 지표] | **선택한 데이터 세트 및 날짜 범위**&#x200B;에 대한 추가/생략/삭제된 이벤트 기록 및 추가된 배치 수를 요약합니다.<p>선택 **[!UICONTROL 세부 사항 확인]** 표시 방법 **[!UICONTROL 건너뛴 세부 정보 확인]** 팝업, 모든 이벤트 데이터 세트 또는 선택한 데이터 세트에 대해 생략된 레코드 수 및 이유를 나열합니다.<p><img src="./assets/skipped-records.png" width="70%"/><p>선택 ![정보](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) 팝업에 추가 정보를 추가합니다. 다음과 같은 생략된 이유로 [!UICONTROL 빈 방문자 ID]에서 사용할 수 있는 EQS(Query Service에 대한 Experience Platform)에 대한 샘플 PSQL이 팝업에 표시됩니다. [쿼리 서비스](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ko) 를 입력하여 데이터 세트에서 건너뛴 레코드를 쿼리합니다. 선택 ![복사](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL EQS에 대한 샘플 PSQL 복사]** SQL을 복사합니다. |
| [!UICONTROL 추가된 레코드] | 선택된 기간 내에 **선택한 데이터 세트 및 날짜 범위**&#x200B;에 대해 얼마나 많은 행이 추가되었는지 나타냅니다. 10분마다 업데이트됩니다. |
| [!UICONTROL 생략된 레코드] | 선택된 기간 내에 **선택한 데이터 세트 및 날짜 범위**&#x200B;에 대해 얼마나 많은 행이 생략되었는지 나타냅니다. 기록 생략의 이유에는 타임스탬프 누락, 누락된 또는 잘못된 개인 ID 등이 포함됩니다. 10분마다 업데이트됩니다. <p>잘못된 개인 ID(예를 들면 [!UICONTROL 개인 ID]에 &quot;정의되지 않은&quot; 또는 &quot;00000000&quot; 또는 1달 동안 1백만 번 이상 하나의 이벤트에 나타나는 숫자 및 문자의 조합이 사용되는 경우)는 특정 사용자 또는 개인의 속성으로 할당될 수 없습니다. 이러한 ID는 시스템에서 수집될 수 없으며 오류 유발 수집 및 보고를 초래할 수 있습니다. 잘못된 개인 ID를 수정할 수 있는 세 가지 방법이 있습니다.<ul><li>사용 [결합](/help/stitching/overview.md) 정의되지 않은 또는 모두 영으로 된 사용자 ID를 유효한 사용자 ID로 채우기.</li><li>사용자 ID를 지우면 해당 ID는 수집 중에 건너뜁니다(잘못된 또는 모두 영으로 된 사용자 ID보다 선호됨).</li><li>데이터를 수집하기 전에 사용자의 시스템 내에서 모든 잘못된 사용자 ID를 수정합니다.</li></ul> |
| [!UICONTROL 레코드] 삭제됨 | 선택된 기간 내에 **선택한 데이터 세트 및 날짜 범위**&#x200B;에 대해 얼마나 많은 행이 삭제되었는지 나타냅니다. 예를 들어 누군가가 Experience Platform에서 데이터 세트를 삭제했을 수도 있습니다. 10분마다 업데이트됩니다. |
| ![검색](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _데이터 세트 이름 또는 ID 검색_ | 데이터 세트 검색 필드. 데이터 세트 이름이나 [!UICONTROL 데이터 세트 ID]. |
| [!UICONTROL 데이터 세트 테이블] | 연결에 포함된 데이터 세트를 표시합니다. |
| [!UICONTROL 데이터 세트] | 연결에 포함된 데이터 세트의 이름을 표시합니다. 하이퍼링크를 선택하여 Experience Platform UI의 데이터 세트를 새 탭에서 열 수 있습니다. 행 또는 확인란을 선택하여 선택한 데이터 세트에 대한 세부 사항만 표시할 수 있습니다. |
| [!UICONTROL 데이터 세트 ID] | Experience Platform에 의해 자동으로 생성됩니다. |
| [!UICONTROL 추가된 레코드] | 선택한 시간 간격 동안 연결에 추가된 데이터 세트 레코드/행 수입니다. |
| [!UICONTROL 생략된 레코드] | 선택한 시간 간격 동안 연결을 위한 데이터 전송 중 건너뛴 데이터 세트 레코드/행 수입니다. |
| [!UICONTROL 삭제된 레코드] | 선택한 시간 간격 동안 연결에서 제거된 데이터 세트 레코드/행 수입니다. |
| [!UICONTROL 배치 추가됨] | 데이터 세트 배치 수가 연결에 추가되었습니다. |
| [!UICONTROL 마지막으로 추가됨] | 연결에 추가된 데이터 세트에서 최신 일괄 처리의 타임스탬프. |
| [!UICONTROL 데이터 소스 유형] | 데이터 세트의 소스 유형입니다. 연결을 만들 때 소스 유형을 정의합니다. |
| [!UICONTROL 데이터 세트 유형] | 이 데이터 세트의 데이터 세트 유형입니다. 유형은 다음과 같을 수 있습니다 [!UICONTROL 이벤트], [!UICONTROL 조회], 또는 [!UICONTROL 프로필]. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#configure-dataset) |
| 스키마 | 데이터 세트가 기반으로 삼는 Experience Platform 스키마입니다. |
| [!UICONTROL 새 데이터 가져오기] | 데이터 세트에 대한 새 데이터 가져오기 상태를 표시합니다. <p><span style="color:green">●</span>   **[!UICONTROL _x _날짜]**데이터 세트가 새 데이터를 가져오도록 구성된 경우<p><span style="color:gray">●</span>   **[!UICONTROL _x 끄기_]** 데이터 세트가 새 데이터 가져오기를 가져오지 않도록 구성된 경우. |
| [!UICONTROL 채우기 데이터] | 데이터 집합에 대한 데이터 채우기 상태를 표시합니다.<p><span style="color:red">●</span>   **[!UICONTROL _x _다시 채우기 실패]**실패한 다시 채우기 횟수의 경우<p><span style="color:orange">●</span>   **[!UICONTROL _x _다시 채우기 처리 중]**다시 채우기 처리 횟수의 경우<p><span style="color:green">●</span>   **[!UICONTROL _x _다시 채우기 완료됨]**완료된 다시 채우기 횟수<p><span style="color:grey">●</span>   **[!UICONTROL _끔_]** 백필이 구성되지 않은 경우 |

>[!IMPORTANT]
>
>2021년 8월 13일 이전에 수집된 데이터는 [!UICONTROL 연결] 인터페이스.

### 연결 패널

데이터 세트 테이블에서 데이터 세트를 선택하지 않으면 연결 인터페이스 오른쪽의 패널에 연결 옵션 및 세부 정보가 표시됩니다.

| 옵션 / 세부 정보 | 설명 |
| --- | --- |
| ![새로 고침](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL 새로 고침] | 연결을 새로 고치고 최근에 추가한 레코드가 반영되도록 하려면 다음을 선택합니다. ![새로 고침](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 새로 고침]**. |
| ![삭제](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 삭제]** | [삭제](#delete-a-connection) 이 연결. |
| ![데이터 보기 추가](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 데이터 보기 만들기]** | [데이터 보기 만들기](#create-a-data-view) 이 연결을 기반으로 합니다. 다음을 참조하십시오 [데이터 보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html) 추가 정보. |
| [!UICONTROL 연결 이름] | 연결의 알기 쉬운 이름을 표시합니다. |
| [!UICONTROL 연결 설명] | 이 연결의 목적을 설명하는 더 자세한 설명을 표시합니다. |
| [!UICONTROL 샌드박스] | 다음 [Experience Platform 샌드박스](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) 이 연결이 데이터 세트를 가져오는 출처. 이 샌드박스는 처음 연결을 만들 때 선택됩니다. 이는 변경할 수 없습니다. |
| [!UICONTROL 연결 ID] | 이 ID는 Experience Platform에서 생성됩니다. 다음을 사용할 수 있습니다. ![복사](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) 를 클릭하여 ID를 복사합니다. |
| [!UICONTROL 연결을 이용한 데이터 보기] | 이 연결을 사용하는 데이터 보기를 모두 나열합니다. |
| [!UICONTROL 새 데이터 가져오기] | 데이터 세트에 대한 새 데이터 가져오기 상태를 표시합니다. <p><span style="color:green">●</span>   **[!UICONTROL _x _날짜]**새 데이터를 가져오도록 구성된 데이터 세트 수에 대해<p><span style="color:gray">●</span>   **[!UICONTROL _x 끄기_]** 새 데이터 가져오기 기능을 해제한 데이터 세트 수에 대해 설명합니다. |
| [!UICONTROL 채우기 데이터] | 데이터 세트의 데이터 채우기 상태를 표시합니다.<p><span style="color:red">●</span>   **[!UICONTROL _x _다시 채우기 실패]**데이터 세트 간 실패한 다시 채우기 횟수<p><span style="color:orange">●</span>   **[!UICONTROL _x _다시 채우기 처리 중]**데이터 세트 간 처리 다시 채우기 횟수<p><span style="color:green">●</span>   **[!UICONTROL _x _다시 채우기 완료됨]**데이터 세트에 대해 완료된 채우기 횟수<p><span style="color:grey">●</span>   **[!UICONTROL _끔_]** 연결의 데이터 세트에 대해 백필이 정의되지 않은 경우. |
| [!UICONTROL 작성자] | 연결을 만든 사람의 이름을 표시합니다. |
| [!UICONTROL 마지막 수정일] | 연결에 대한 마지막 변경 사항의 타임스탬프를 표시합니다. |
| [!UICONTROL 마지막 수정자] | 연결을 마지막으로 수정한 사람을 표시합니다. |

### 데이터 세트 패널

데이터 세트 테이블에서 데이터 세트를 선택하면 연결 인터페이스 오른쪽의 패널에 선택한 데이터 세트에 대한 세부 정보가 표시됩니다.

| 세부 사항 | 설명 |
| --- | --- |
| [!UICONTROL 개인 ID] | Experience Platform의 데이터 세트 스키마에 정의된 ID를 표시합니다. 이는 연결 생성 중 선택한 개인 ID입니다. ID가 다른 데이터 세트를 포함하는 연결을 만들면 이러한 내용이 보고에 반영됩니다. 데이터 세트를 병합하려면 데이터 세트 간에 동일한 개인 ID를 사용해야 합니다. |
| [!UICONTROL 키] | 조회 데이터 세트에 대해 지정한 키를 표시합니다. |
| [!UICONTROL 일치하는 키] | 조회 데이터 세트에 대해 지정한 일치하는 키를 표시합니다. |
| [!UICONTROL 타임스탬프] | 이벤트 데이터 세트에 대해 정의된 타임스탬프를 표시합니다. |
| [!UICONTROL 사용 가능한 레코드] | 달력을 통해 선택한 특정 기간 동안 이 데이터 세트에 대해 수집된 행의 총 수를 나타냅니다. 데이터가 추가되고 난 후 보고에 표시되기까지의 지연 시간은 없습니다. 하지만 새 연결을 만들 때는 [지연](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL 추가된 레코드] | 선택한 기간 내에 얼마나 많은 행이 추가되었는지를 나타냅니다. |
| [!UICONTROL 삭제된 레코드] | 선택한 기간 동안 얼마나 많은 레코드가 삭제되었는지를 나타냅니다. |
| [!UICONTROL 배치 추가됨] | 이 데이터 세트에 얼마나 많은 데이터 배치가 추가되었는지 나타냅니다. |
| [!UICONTROL 생략된 레코드] | 선택한 기간 내에 수집 중 얼마나 많은 행이 생략되었는지를 나타냅니다.<p>기록 생략의 이유에는 타임스탬프 누락, 누락된 또는 잘못된 개인 ID 등이 포함됩니다. 10분마다 업데이트됩니다.<p>잘못된 개인 ID(예를 들면 [!UICONTROL 개인 ID]에 &quot;정의되지 않은&quot; 또는 &quot;00000000&quot; 또는 1달 동안 1백만 번 이상 하나의 이벤트에 나타나는 숫자 및 문자의 조합이 사용되는 경우)는 특정 사용자 또는 개인의 속성으로 할당될 수 없습니다. 이러한 ID는 시스템에서 수집될 수 없으며 오류 유발 수집 및 보고를 초래할 수 있습니다. 잘못된 개인 ID를 수정할 수 있는 세 가지 방법이 있습니다.<ul><li>사용 [결합](/help/stitching/overview.md) 정의되지 않은 또는 모두 영으로 된 사용자 ID를 유효한 사용자 ID로 채우기.</li><li>사용자 ID를 지우면 해당 ID는 수집 중에 건너뜁니다(잘못된 또는 모두 영으로 된 사용자 ID보다 선호됨).</li><li>데이터를 수집하기 전에 사용자의 시스템 내에서 모든 잘못된 사용자 ID를 수정합니다.</li></ul> |
| [!UICONTROL 마지막으로 추가됨] | 마지막 배치가 추가된 시간을 표시합니다. |
| [!UICONTROL 새 데이터 가져오기] | 데이터 세트에 대한 새 데이터 가져오기 상태를 표시합니다. <p><span style="color:green">●</span>   **[!UICONTROL _x _날짜]**데이터 세트가 새 데이터를 가져오도록 구성된 경우<p><span style="color:gray">●</span>   **[!UICONTROL _x 끄기_]** 데이터 세트가 새 데이터 가져오기를 가져오지 않도록 구성된 경우. |
| [!UICONTROL 채우기 데이터] | 데이터 집합에 대한 데이터 채우기 상태를 표시합니다.<p><span style="color:red">●</span>   **[!UICONTROL _x _다시 채우기 실패]**실패한 다시 채우기 횟수의 경우<p><span style="color:orange">●</span>   **[!UICONTROL _x _다시 채우기 처리 중]**다시 채우기 처리 횟수의 경우<p><span style="color:green">●</span>   **[!UICONTROL _x _다시 채우기 완료됨]**완료된 다시 채우기 횟수<p><span style="color:grey">●</span>   **[!UICONTROL _끔_]** 백필이 구성되지 않은 경우<p>데이터 세트에 대한 과거 채우기 개요가 포함된 대화 상자를 표시하려면 을 선택합니다. <img src="./assets/pastbackfill.svg" alt="이전 채우기" width="2%" /> **[!UICONTROL 지난 다시 채우기]**. |
| [!UICONTROL 데이터 소스 유형] | 연결에 데이터 세트를 추가할 때 정의된 데이터 소스 유형. |
| [!UICONTROL 데이터 세트 유형] | [!UICONTROL 이벤트], [!UICONTROL 조회] 또는 [!UICONTROL 프로필]입니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#configure-dataset) |
| [!UICONTROL 스키마] | 이 데이터 세트가 기반으로 삼는 Experience Platform 스키마를 표시합니다. |
| [!UICONTROL 데이터 세트 ID] | 이 데이터 세트 ID는 Experience Platform에서 생성됩니다. |


>[!MORELIKETHIS]
>
>[연결 설정 보기, 문제 해결 및 수정](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html?lang=en) 튜토리얼.
