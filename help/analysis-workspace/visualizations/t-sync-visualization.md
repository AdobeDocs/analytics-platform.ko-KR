---
description: 시각화를 동기화하면 시각화에 해당하는 데이터 테이블 또는 데이터 소스를 제어할 수 있습니다.
keywords: Analysis Workspace;시각화를 데이터 소스와 동기화
title: 데이터 소스 관리
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 27%

---

# 데이터 소스 관리 {#manage-data-sources}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="선택 사항 잠금"
>abstract="이 설정을 활성화하여 시각화를 데이터 소스의 선택한 위치 또는 선택한 항목에 잠급니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="테이블 표시"
>abstract="**[!UICONTROL 테이블 표시]**&#x200B;를 선택하면 현재 시각화에 대한 새 데이터 소스를 생성하여 원래 데이터 소스와 분리시킬 수 있습니다."

<!-- markdownlint-enable MD034 -->



시각화를 동기화하면 시각화에 해당하는 데이터 테이블 또는 데이터 소스를 제어할 수 있습니다.

>[!TIP]
>
>시각화 제목 옆에 있는 ![StatusOrange](/help/assets/icons/StatusOrange.svg)의 색상으로 어떤 시각화가 관련되는지 알 수 있습니다. 색상이 일치하면 시각화가 동일한 데이터 소스를 기준으로 한다는 것을 의미합니다.
>

데이터 소스를 표시하거나 숨길 수 있습니다. 선택 항목을 선택한 위치 또는 선택한 항목에 잠글 수도 있습니다. 이러한 설정은 새 데이터가 유입될 때 시각화가 변경되는 (또는 변경되지 않는) 방식을 결정합니다.

![다음 섹션에 설명된 옵션을 표시하는 데이터 Source 옵션 대화 상자입니다.](assets/lock-selection.png)


| 옵션 | 설명 |
|--- |--- |
| **[!UICONTROL 데이터 원본]** | 드롭다운 메뉴에서 시각화의 기반이 되는 데이터 소스를 선택합니다. |
| **[!UICONTROL 연결된 시각화]** | 연결된 시각화를 모두 나열합니다. 데이터 소스(자유 형식 테이블)에 적용됩니다. |
| **[!UICONTROL 데이터 원본 표시]** | 시각화에 해당하는 데이터 소스(자유 형식 테이블)를 표시하거나 숨길 수 있습니다. |
| **[!UICONTROL 선택 사항 잠금]** | 해당 데이터 테이블에서 현재 선택한 데이터에 시각화 ![LockClosed](/help/assets/icons/LockClosed.svg)을(를) 잠그려면 이 옵션을 선택하십시오. 활성화한 후 다음 중 하나를 선택합니다.  <ul><li>**선택한 위치**: 해당 데이터 테이블에서 선택한 **위치**&#x200B;에서 시각화가 잠겨 있습니다. 이러한 위치는 이러한 위치의 특정 항목이 변경되더라도(예를 들어 정렬 또는 필터링으로 인해) 계속 시각화됩니다. 예를 들어 이 시각화에서 데이터 소스에 나열된 상위 5개의 캠페인 이름을 항상 표시하려면 이 옵션을 선택합니다. 어떤 캠페인 이름이 표시되든.</li> <li>**선택한 항목**: 현재 해당 데이터 테이블에서 선택된 특정 **항목**&#x200B;에 대해 시각화가 잠겨 있습니다. 이러한 항목은 표에 있는 항목 간에 순위가 변경되더라도 계속 시각화됩니다. 예를 들어 이 시각화의 데이터 소스에 나열된 동일한 5개의 특정 캠페인 이름을 항상 표시하려면 이 옵션을 선택합니다. 그 캠페인 이름들이 어떻게 순위가 매겨지든.</li></ul>시각화가 연결된 데이터 테이블에 더 이상 표시되지 않는 데이터에 잠겨 있는 경우 새 테이블을 생성할 수 있습니다. 원본 데이터 원본과 별도로 현재 시각화에 대한 새 데이터 원본을 생성하려면 **[!UICONTROL 테이블 표시]**&#x200B;를 선택하십시오. |
