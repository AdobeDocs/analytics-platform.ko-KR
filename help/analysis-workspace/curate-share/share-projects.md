---
description: 작업 영역의 프로젝트 공유 및 프로젝트 역할
keywords: Analysis Workspace 공유
title: 프로젝트 공유
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 100%

---

# 프로젝트 공유

공유를 하면 프로젝트를 조직의 다른 Analysis Workspace 사용자가 사용할 수 있습니다. 적용한 모든 [조정](curate.md) 기능은 수신자이 프로젝트를 열 때 반영됩니다.

## 프로젝트 역할 {#Roles}

3개의 프로젝트 역할 중 하나에 수신자를 추가할 수 있습니다. 프로젝트 역할은 사용자 및 특정 프로젝트 ID에 연결되어 있습니다. 프로젝트 역할은 [Adobe Experience Cloud 관리 콘솔](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=ko-KR)에서 관리되는 사용자 권한과 독립적입니다.

| 역할 | 프로젝트 제어 |
|---|---|
| 편집 가능 | 수신자는 프로젝트 및 기능에 대한 변경 내용을 공동 소유자로서 **[!UICONTROL 저장]**&#x200B;할 수 있습니다. 이 역할은 프로젝트를 다른 동료와 공동 관리하려는 경우 유용합니다. 여기에는 공유 프로젝트에 대한 수신자 목록 편집, 삭제 및 수정 등이 포함됩니다. <br>참고: Analysis Workspace는 현재 라이브 공동 작업을 지원하지 않으므로 주어진 시간에 한 명의 사용자만 프로젝트를 편집하는 것이 좋습니다. 프로젝트를 동시에 저장하는 경우 마지막 버전이 유지됩니다. |
| 복제 가능 | 수신자는 **[!UICONTROL 다른 이름으로 저장]**&#x200B;하고 왼쪽 레일에 액세스할 수 있습니다. 이 역할에서는 프로젝트 상호 작용이 제한되지 않습니다. 이 역할은 조직의 데이터 및 Analysis Workspace 사용 방법을 이해하지만 프로젝트를 변경하지 않으려는 사용자에게 프로젝트를 공유하려는 경우에 유용합니다. |
| 보기 가능 | 수신자는 다른 이름으로 저장을 할 수 없고 왼쪽 레일에 액세스할 수 없습니다. 상호 작용이 제한됩니다. 이 역할은 일반적으로 조직의 데이터 구조, Analysis Workspace 또는 Customer Journey Analytics에 익숙하지 않은 사용자에게 프로젝트를 공유하려는 경우에 유용합니다. 그러나 안전한 환경에서 데이터와 인사이트를 소비해야 합니다.<br>프로젝트 경험 볼 수 있음[에 대해 자세히 알아보십시오](/help/analysis-workspace/curate-share/view-only-projects.md). |

>[!IMPORTANT]
> 2020년 6월 18일 이전에 추가된 프로젝트 수신자는 프로젝트 역할로 마이그레이션되었습니다. 관리자 사용자가 역할 **[!UICONTROL 편집 가능]** 및 관리자가 아닌 사용자가 **[!UICONTROL 복제 가능]** 역할로 마이그레이션되었습니다. 이러한 역할은 이전에 경험했던 것과 동일한 프로젝트 경험을 제공합니다. 또한 모든 그룹 (&quot;모두&quot; 포함)이 **[!UICONTROL 복제 가능]** 역할로 마이그레이션되었습니다.

### 할당된 역할 없음 (프로젝트 링크 수신자)

수신자에게 역할이 지정되지 않고 프로젝트에 대한 [링크](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=ko-KR)를 받은 경우 (**[!UICONTROL 공유]> [!UICONTROL 프로젝트 링크 가져오기]**) 수신자는 기본적으로 역할을 받게 됩니다. 관리자는 **[!UICONTROL 편집 가능]**&#x200B;하고 관리자가 아닌 사용자는 **[!UICONTROL 복제 가능]**&#x200B;합니다.

### 여러 역할 할당

수신자가 여러 역할에 배치되면 항상 가장 높은 경험을 받게 됩니다. 이는 수신자가 개인과 그룹의 일부로 모두 추가되는 경우에 발생할 수 있습니다. 예를 들어 수신자에게 개인으로서 **[!UICONTROL 편집 가능]** 역할 및 그룹의 구성원으로 **[!UICONTROL 볼 수 있음]** 역할이 주어지면, 해당 사용자에게는 프로젝트 **[!UICONTROL 편집 가능]** 환경이 제공됩니다.

### 관리자 및 역할

**[!UICONTROL 복제 가능]** 또는 역할 **[!UICONTROL 볼 수 있음]**&#x200B;에 배치된 관리자는 프로젝트를 열 때 제한된 경험을 받게 됩니다. 원하는 경우 관리자는 **[!UICONTROL 구성 요소] > [!UICONTROL 프로젝트]**&#x200B;를 통해 언제든지 **[!UICONTROL 편집 가능]**&#x200B;한 역할을 늘릴 수 있습니다.

## 공유 프로젝트에 수신자 추가 {#Add}

공유 프로젝트에 수신자를 추가하려면:

1. **[!UICONTROL 공유]** > **[!UICONTROL 프로젝트 공유]**를 클릭합니다.
저장하지 않은 변경 사항이 있으면 먼저 프로젝트를 저장하라는 메시지가 표시됩니다.
1. 수신자 또는 수신자 그룹을 추가합니다.
각 역할에 대한 설명은 맨 위의 도움말 아이콘을 참조하십시오.
1. (선택 사항) 모든 수신자와 임베드된 구성 요소(필터, 계산된 지표 및 날짜 범위)를 공유할 수 있습니다.
이러한 구성 요소가 공유되면 수신자 작업 영역의 구성 요소 드롭다운에 표시됩니다. 이 설정은 유지되지 않습니다. 공유 시의 단일 작업입니다.
1. (선택 사항) 이 페이지를 수신자의 랜딩 페이지로 설정합니다.
이 설정은 유지되지 않습니다. 공유 시의 단일 작업입니다.
1. 공유를 클릭합니다.
또한 **[!UICONTROL 조정 및 공유]**&#x200B;를 클릭하여 프로젝트 조정을 자동으로 적용할 수도 있습니다. 프로젝트가 이미 공유된 경우 이 버튼에는 **[!UICONTROL 업데이트]** 및 **[!UICONTROL 조정 및 업데이트]**&#x200B;가 표시됩니다. [프로젝트 조정](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=ko-KR)에 대한 자세한 내용을 살펴보십시오.

![](assets/share-proj-modal.png)

## 수신자 그룹에 공유 {#Groups}

모든 사용자는 수신자의 집합인 그룹에 프로젝트를 공유할 수 있습니다. Customer Journey Analytics에서 그룹은 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)에서 제품 프로필로 정의됩니다.

* 관리자는 &quot;모두&quot;를 비롯한 모든 그룹과 공유할 수 있습니다.
* 관리자가 아닌 사용자는 &quot;모두&quot;를 제외하고 자신이 구성원으로 있는 그룹과 공유할 수 있습니다.

## 프로젝트 링크 공유 {#Links}

**[!UICONTROL 공유] > [!UICONTROL 프로젝트 가져오기]**&#x200B;에서 프로젝트 링크를 가져올 수 있습니다. 클릭하면 수신자는 로그인한 후 프로젝트에 참여해야 합니다. 수신자가 역할에 배치되지 않은 경우 기본 역할을 받게 됩니다. 관리자는 **[!UICONTROL 편집 가능]**&#x200B;하고 관리자가 아닌 사용자는 **[!UICONTROL 복제 가능]**&#x200B;합니다. Workspace 프로젝트에 연결된 공유 가능한 링크를 만드는 방법에 대해 [자세히 알아보십시오](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html).

## 프로젝트 관리자에서 프로젝트 공유 {#Manager}

**[!UICONTROL 구성 요소] > [!UICONTROL 프로젝트]**&#x200B;에서 프로젝트를 공유할 수도 있습니다. 위의 동일한 단계에 따라 단일 프로젝트를 공유할 수 있습니다. 여러 프로젝트를 공유하도록 선택하면 수신자가 각 프로젝트에 대한 기존 수신자 목록에 추가됩니다.

예:

* 프로젝트 A는 수신자 1, 2, 3에게 공유됨
* 프로젝트 B는 수신자 4, 5, 6에게 공유됨

프로젝트 A와 B를 선택하면 수신자 4 및 7이 공유 목록에 추가됩니다. 이제 각 프로젝트에 대한 새 공유 목록이 표시됩니다.

* 프로젝트 A: 1, 2, 3, 4, 7
* 프로젝트 B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## FAQ {#FAQs}

| 질문 | 답변 |
|---|---|
| 두 명의 편집자가 동시에 프로젝트를 저장하면 어떻게 됩니까? | 변경 사항은 병합되지 않고 마지막으로 저장한 프로젝트 버전이 유지됩니다. Analysis Workspace는 현재 실시간 공동 작업을 지원하지 않습니다. |
| 관리자는 어떤 프로젝트 경험을 보게 됩니까? | **[!UICONTROL 복제 가능]** 또는 역할 **[!UICONTROL 볼 수 있음]**&#x200B;에 배치된 관리자는 프로젝트를 열 때 제한된 경험을 받게 됩니다. 원하는 경우 관리자는 **[!UICONTROL 구성 요소] > [!UICONTROL 프로젝트]**&#x200B;를 통해 언제든지 **[!UICONTROL 편집 가능]**&#x200B;한 역할을 늘릴 수 있습니다. |
| 수신자가 하나의 역할에서 개인 또는 그룹의 구성원으로서의 다른 역할에 배치되면 어떻게 됩니까? | 수신자가 여러 역할에 배치되면 항상 더 높은 경험을 받게 됩니다. 예를 들어 수신자에게 개인으로서 **[!UICONTROL 편집 가능]** 역할 및 그룹의 구성원으로 **[!UICONTROL 볼 수 있음]** 역할이 주어지면, 해당 사용자에게는 프로젝트 **[!UICONTROL 편집 가능]** 환경이 제공됩니다. |
| 프로젝트 링크를 열면 수신자는 어떤 경험을 얻을 수 있습니까? | 수신자는 공유 모달에서 지정한 역할을 받습니다. 수신자에게 역할이 할당되지 않고 프로젝트에 대한 링크를 받은 경우 (**[!UICONTROL 공유]> [!UICONTROL 프로젝트 링크 가져오기]**) 기본적으로 역할을 받게 됩니다. 관리자는 **[!UICONTROL 편집 가능]**&#x200B;하고 관리자가 아닌 사용자는 **[!UICONTROL 복제 가능]**&#x200B;합니다. |
