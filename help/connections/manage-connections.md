---
title: 연결 관리
description: CJA(Customer Journey Analytics)에서 Experience Platform 데이터 세트에 대한 연결을 관리하는 방법을 설명합니다.
mini-toc-levels: 3
source-git-commit: 1daac64168e656ed1145dac4c34d3df52d155e35
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 8%

---

# 연결 관리

관리자 사용자가 [하나 이상의 연결을 만들었으면 [!UICONTROL 연결] 관리자에서 해당 연결을 관리할 수 있습니다. ](/help/connections/create-connection.md) 연결 경험에 대한 최신 업데이트는 이 페이지에 자세히 설명된 연결 세부 사항 페이지 내에 두 가지 중요한 기능을 추가합니다.

* 이 옵션을 통해 연결의 데이터 세트 상태 및 수집 프로세스&#x200B;**를 확인할 수 있습니다.** 이 상태 점검을 통해 Analysis Workspace으로 이동하여 분석을 시작할 수 있도록 데이터를 사용할 수 있는 시기를 알 수 있습니다.

* 이 옵션을 사용하면 잘못된 구성으로 인해 **데이터 불일치를 식별할 수 있습니다**. 행이 누락되었습니까? yes인 경우 누락된 행과 그 이유는 무엇입니까? 연결 구성 및 CJA에 누락된 데이터가 발생했습니까?

>[!NOTE]
> 이 기능은 일반적으로 2021년 8월 10일에 제공됩니다.

## 연결 관리자 {#connections-manager}

연결 관리자를 사용하여 다음을 수행할 수 있습니다.

* 소유자, 샌드박스, 연결 생성 및 수정 시기 등 모든 연결을 한 눈에 볼 수 있습니다.
* 연결에서 모든 데이터 세트를 봅니다.
* 연결 상태를 확인합니다.
* 연결을 삭제할 수 있습니다.
* 연결 이름을 변경할 수 있습니다.
* 연결에서 데이터 보기를 만들 수 있습니다.

![연결 관리](assets/conn-manager.png)

| 설정 | 설명 |
| --- | --- |
| [!UICONTROL  이름 ] | 연결의 친숙한 이름입니다. 하이퍼링크된 이름을 클릭하면 아래 설명된 연결 세부 정보 페이지로 이동합니다. |
| 연결 정보 | 연결 이름 옆에 있는 정보 아이콘을 클릭하여 다음 정보를 봅니다.![연결 정보 보기](assets/conn-info.png) |
| 연결 편집 | 연결 이름 옆에 있는 줄임표(..)를 클릭한 다음 [!UICONTROL 편집]을 클릭합니다.![연결 ](assets/conn-edit-delete.png) 편집자세한 내용은 아래의 &quot;연결 편집&quot;을 참조하십시오. |
| 연결을 삭제할 수 있습니다 | 연결 이름 옆에 있는 줄임표(...)를 클릭한 다음 [!UICONTROL 삭제]를 클릭합니다. 아래의 &quot;연결 삭제&quot; 제목 아래에 추가 정보가 있습니다. |
| 데이터 뷰 만들기 | 연결 이름 옆에 있는 줄임표(...)를 클릭한 다음 [!UICONTROL 데이터 보기 만들기]를 클릭합니다. 이 작업을 수행하면 이 연결을 기반으로 새 데이터 보기가 만들어집니다. [추가 정보](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL 데이터 세트] | 연결의 일부인 데이터 세트입니다. 하이퍼링크를 클릭하면 연결에 있는 모든 데이터 세트를 볼 수 있습니다. 데이터 세트를 클릭하면 새 탭에서 Adobe Experience Platform에 해당 데이터 세트가 열립니다. |
| [!UICONTROL 샌드박스] | 이 연결이 해당 데이터 세트를 그리는 [Adobe Experience Platform 샌드박스](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) 이 샌드박스는 연결을 처음 만들 때 선택되었습니다. 변경할 수 없습니다. |
| [!UICONTROL 소유자] | 연결을 만든 사용자입니다. |
| [!UICONTROL 데이터 세트 가져오기] | &quot;데이터 스트리밍&quot;이라고 하는 것을 활성화하거나 비활성화할 수 있습니다. |
| [!UICONTROL 만든 날짜] | 연결이 처음 생성된 날짜입니다. |
| [!UICONTROL 마지막 수정 날짜] | 연결이 마지막으로 업데이트된 날짜입니다. |

### 연결 삭제 {#connections-delete}

관리자만 연결을 삭제할 권한이 있습니다. 이 작업은 관리자가 아닌 사용자에게 표시되지 않습니다.

1. 연결 이름 옆에 있는 줄임표(...)를 클릭합니다.
1. [!UICONTROL 삭제]를 클릭합니다.

[!UICONTROL Customer Journey Analytics]에서 연결을 삭제하면 다음과 같은 오류 메시지가 표시됩니다.

* 삭제된 연결을 기반으로 만들어진 모든 데이터 보기는 더 이상 작동하지 않습니다.
* 마찬가지로, 삭제된 연결의 데이터 보기에 의존하는 모든 Analysis Workspace 프로젝트의 작동이 정지됩니다.

[삭제 의미에 ](/help/getting-started/cja-deletion.md) 대해 자세히 알아보십시오.

### 연결 또는 데이터 세트 검색

[!UICONTROL 연결] 제목 아래의 검색 막대를 사용하여 연결을 검색할 수 있습니다.

### 연결 정렬

각 열 헤더를 클릭하고 위나 아래로 정렬하여 연결을 정렬할 수 있습니다.

## 연결 세부 정보 페이지 {#connection-detail}

새 연결 세부 정보 페이지에서는 연결 상태를 자세히 볼 수 있습니다.

이 기능을 사용하면 다음 작업을 수행할 수 있습니다.

* 연결의 데이터 세트 상태 및 수집 프로세스를 확인합니다.
* 레코드를 건너뛰거나 삭제한 구성 문제를 식별합니다.
* 보고에 데이터를 사용할 수 있는 시기를 참조하십시오.

다음은 위젯 및 설정에 대해 설명합니다.

![연결 세부 정보 보기](assets/conn-details.png)

| 위젯/설정 | 설명 |
| --- | --- |
| 데이터 세트 선택기 | 연결에서 하나 또는 모든 데이터 세트를 선택할 수 있습니다. 데이터 세트를 다중 선택할 수 없습니다. 기본값은 [!UICONTROL 모든 데이터 세트]입니다. |
| 달력/날짜 범위 | 날짜 범위는 연결에 데이터를 추가한 시간을 나타냅니다. 모든 표준 달력 사전 설정이 포함됩니다. 날짜 범위를 사용자 지정할 수 있지만 드롭다운에 사용자 지정 날짜 범위가 표시되지 않습니다. |
| [!UICONTROL 사용 ] 가능한 위젯 레코드 | 전체 연결&#x200B;**에 대해 보고 가능한 총 행 수**&#x200B;를 나타냅니다. 이 수는 일정 설정과 독립적입니다. 데이터 세트 선택기에서 데이터 세트를 선택하거나 테이블에서 데이터 세트를 선택하면 변경됩니다. ( 데이터가 추가되면 보고에 데이터를 표시하는 데 1~2시간이 지연됩니다.) |
|  지표 위젯 | 추가/건너뛰기/삭제된 레코드 및 선택한 데이터 세트 및 날짜 범위에 대해 추가된 일괄 처리 수 **를 요약합니다**. |
| [!UICONTROL 추가된 ] 위젯 기록 | 선택한 기간, 선택한 데이터 세트 및 날짜 범위에 대해 **몇 개의 행이 추가되었는지 나타냅니다**. 10분마다 업데이트됨. |
| [!UICONTROL 건너뛴 ] 위젯 레코드 | 선택한 기간, 선택한 데이터 세트 및 날짜 범위에 대해 **선택한 기간에 건너뛴 행 수를 나타냅니다**. 레코드를 건너뛰는 이유는 다음과 같습니다. 타임스탬프, 개인 ID 누락 등이 있습니다. 10분마다 업데이트됨. |
| [!UICONTROL 삭제된 ] 위젯 레코드 | 선택한 기간, 선택한 데이터 세트 및 날짜 범위에 대해 **선택한 기간에 삭제된 행 수를 나타냅니다**. 예를 들어 누군가가 Experience Platform에서 데이터 세트를 삭제했을 수 있습니다. 10분마다 업데이트됨. |
| 데이터 집합 검색 상자 | 데이터 세트 이름 또는 [!UICONTROL 데이터 세트 ID]로 검색할 수 있습니다. |
| [!UICONTROL 데이터 세트] | 연결의 일부인 데이터 세트를 표시합니다. 하이퍼링크를 클릭하면 연결에 있는 모든 데이터 세트를 볼 수 있습니다. |
| [!UICONTROL 데이터 세트 ID] | 이 ID는 Adobe Experience Platform에 의해 자동으로 생성됩니다. |
| [!UICONTROL 배치] | 이 데이터 세트에 추가된 데이터 일괄 처리의 수를 나타냅니다. |
| [!UICONTROL 마지막으로 추가됨] | 이 데이터 세트에 마지막으로 추가된 일괄 처리에 대한 타임스탬프를 표시합니다. |
| [!UICONTROL 데이터 세트 유형] | 이 데이터 세트에 대한 데이터 세트 유형은 [!UICONTROL Event], [!UICONTROL Lookup] 또는 [!UICONTROL Profile]일 수 있습니다. [추가 정보](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| 스키마 | 이 연결의 데이터 세트가 기반으로 하는 Adobe Experience Platform 스키마. |
| **연결 수준의 오른쪽 레일** |  |
| [!UICONTROL 새로 고침] | 연결을 새로 고쳐 최근에 추가한 레코드를 반영하도록 합니다. |
| [!UICONTROL 삭제] | 이 연결을 삭제합니다. |
| [!UICONTROL 데이터 뷰 만들기] | 이 연결을 기반으로 새 데이터 보기를 만듭니다 . [추가 정보](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL 연결 이름] | 연결의 친숙한 이름을 표시합니다. |
| [!UICONTROL 연결 설명] | 이 연결의 목적을 이상적으로 설명하는 보다 자세한 설명을 표시합니다. |
| [!UICONTROL 개인 ID] | Experience Platform의 데이터 세트 스키마에 정의된 ID를 표시합니다. 연결을 만들 때 선택한 [!UICONTROL 개인 ID]입니다. ID가 다른 데이터 세트가 포함된 연결을 만들면 이러한 내용이 보고에 반영됩니다. 데이터 세트를 실제로 병합하려면 동일한 [!UICONTROL 개인 ID]를 사용해야 합니다. |
| [!UICONTROL 샌드박스] | 이 연결이 데이터 세트를 그리는 [Adobe Experience Platform 샌드박스](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en) 이 샌드박스는 연결을 처음 만들 때 선택되었습니다. 변경할 수 없습니다. |
| [!UICONTROL 연결 ID] | 이 ID는 Adobe Experience Platform에서 생성된 시스템입니다. |
| [!UICONTROL IMS 조직 ID] | 프로비저닝된 Experience Cloud 회사와 연관된 [조직 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en)입니다. 이전에 &quot;로그인 회사&quot;라고 했습니다. |
| [!UICONTROL 연결을 이용한 데이터 보기] | 이 연결을 사용하는 모든 데이터 보기를 나열합니다. |
| [!UICONTROL 새 데이터 가져오기] | 내역(채우기) 데이터에 새 데이터 배치를 추가해야 하는지 여부를 나타냅니다. |
| **데이터 세트 수준의 오른쪽 레일** |  |
| [!UICONTROL 데이터 세트 설명] | 이 연결에 있는 각 데이터 세트의 매개 변수를 설명합니다. |
| [!UICONTROL 사용 가능한 레코드] | 달력을 통해 선택한 특정 기간 동안 이 데이터 세트에 대해 수집된 총 행 수를 나타냅니다. 데이터가 추가되면 보고에 데이터가 표시되도록 하는 데는 지연이 없습니다. (단, 새 연결을 만들 때 [지연](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#3.-data-into-customer-여정-analytics)이 있습니다.) |
| [!UICONTROL 추가된 레코드] | 선택한 기간에 추가된 행 수입니다. |
| [!UICONTROL 건너뛴 레코드] | 선택한 기간에 수집하는 동안 건너뛴 행 수입니다. |
| [!UICONTROL 레코드를 건너뛴 오류] | 레코드를 건너뛴 이유는 여기에 표시됩니다. 여기에는 누락된 타임스탬프, 누락된 개인 ID 등이 포함될 수 있습니다. |
| [!UICONTROL 배치 수집] | 이 데이터 세트에 추가된 데이터 일괄 처리의 수입니다. |
| [!UICONTROL 마지막으로 추가됨] | 마지막 일괄 처리가 추가되었을 때. |
| [!UICONTROL 데이터 세트 유형] | [!UICONTROL Event], [!UICONTROL Lookup] 또는 [!UICONTROL Profile] 중 하나를 선택합니다. [추가 정보](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| [!UICONTROL 스키마] | 이 데이터 세트가 기반으로 하는 Adobe Experience Platform 스키마. |
| [!UICONTROL 데이터 세트 ID] | 이 ID는 Adobe Experience Platform에서 생성된 시스템입니다. |
| [!UICONTROL 데이터 채우기] | 채우기(내역) 데이터는 다음 3가지 상태로 추적됩니다. [!UICONTROL 큐에서], [!UICONTROL 진행 중](진행 백분율이 표시됨) 및 [!UICONTROL 완료]. |

### 연결 편집

관리자가 연결을 편집할 수 있습니다. 연결을 선택한 다음 [!UICONTROL 연결 편집]을 클릭하여 이 대화 상자로 이동합니다. 여기에서 다음을 수행할 수 있습니다.

* 새 데이터 가져오기를 시작 및 중지합니다. 이 프로세스를 이전에 &quot;데이터 스트리밍&quot;이라고 했습니다.
* 연결 이름을 변경할 수 있습니다.
