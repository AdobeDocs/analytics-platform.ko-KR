---
description: 작업 공간의 프로젝트 공유 및 프로젝트 역할
keywords: Analysis Workspace sharing
title: 작업 공간 프로젝트 공유
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 10%

---


# 작업 공간 프로젝트 공유

>[!NOTE] Customer Journey Analytics의 Analysis Workspace 설명서를 보고 있습니다. 이 기능은 기존 Adobe Analytics의 [Analysis Workspace과 약간 다릅니다](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html). [추가 정보...](/help/getting-started/cja-aa.md)

공유하면 조직의 다른 Analysis Workspace 사용자가 프로젝트를 사용할 수 있습니다. 적용한 모든 [조정](curate.md) 기능은 받는 사람이 프로젝트를 열 때 반영됩니다.

## 프로젝트 역할

3개의 프로젝트 역할 중 하나에 받는 사람을 추가할 수 있습니다. 프로젝트 역할은 사용자 및 특정 프로젝트 ID에 연결되어 있습니다.

>[!NOTE]
> 프로젝트 역할은 Experience Cloud 관리 콘솔에서 관리되는 사용자 권한과 독립적입니다.

| 역할 | 프로젝트 제어 |
|---|---|
| 편집 가능 | 수신자는 프로젝트 및 기능에 대한 변경 내용을 공동 소유자로서 저장할 수 있습니다.<br>이 역할은 프로젝트에서 동료와 공동 작업을 하려는 경우 유용합니다. |
| 복제 가능 | 수신자는 다른 이름으로 저장을 할 수 있고 왼쪽 레일에 액세스할 수 있습니다. 상호 작용이 제한되지 않습니다.<br>이 역할은 조직의 데이터 및 Analysis Workspace 사용 방법을 이해하지만 저장된 프로젝트를 변경하지 않으려는 사용자에게 프로젝트를 공유하려는 경우에 유용합니다. |
| 보기 가능 | 받는 사람은 다른 이름으로 저장할 수 없으며 왼쪽 레일에 액세스할 수 없습니다. 상호 작용도 제한됩니다.<br>이 역할은 일반적으로 조직의 데이터 구조, Analysis Workspace 또는 Adobe Analytics에 익숙하지 않은 사용자에게 프로젝트를 공유하려는 경우에 유용합니다. 그러나 안전한 환경에서 데이터와 통찰력을 소비해야 합니다.<br>프로젝트 경험 [을 볼 수 있음에 대해 자세히 알아보십시오](/help/analysis-workspace/curate-share/view-only-projects.md). |

### 할당된 역할 없음

받는 사람에게 역할이 할당되지 않고 프로젝트에 대한 링크([!UICONTROL 공유][!UICONTROL > 프로젝트]가져오기 링크 [!UICONTROL )를 받는 경우] &quot;볼 수있는&quot; 역할에 기본적으로 배치됩니다.

### 여러 역할 할당

받는 사람이 여러 역할에 배치되면 항상 가장 높은 제어력을 받게 됩니다. 이는 사용자가 개별 및 그룹의 일부로 모두 추가되는 경우에 발생할 수 있습니다. 예를 들어 사용자 1에 편집 가능 및 [!UICONTROL &quot;볼 수] &quot; 역할이 주어지면  프로젝트에 대한 &quot;편집 가능&quot;컨트롤이 부여됩니다.

### 관리자 및 역할

&quot;복제 [!UICONTROL가능&quot;][!UICONTROL 또는] &quot;볼 수있음&quot;에 배치된 관리자는 프로젝트를 열 때 제한된 경험을 받게 됩니다. 원하는 경우 관리자는 구성 요소 [!UICONTROL > 프로젝트] 를 통해 [!UICONTROL 언제든지 자신의 역할을] &quot;편집 가능&quot;으로 [!UICONTROL 늘릴 수]있습니다.

## 공유 프로젝트에 받는 사람 추가

공유 프로젝트에 받는 사람을 추가하려면:

1. 공유 **[!UICONTROL > 프로젝트]** **[!UICONTROL 공유를 클릭합니다]**.
저장하지 않은 변경 사항이 있으면 먼저 프로젝트를 저장하라는 메시지가 표시됩니다.
1. 받는 사람 또는 사용자 그룹을 추가합니다.
각 역할에 대한 설명은 맨 위의 도움말 아이콘을 참조하십시오.
1. (선택 사항) 포함된 프로젝트 구성 요소(세그먼트, 계산된 지표 및 날짜 범위)를 모든 받는 사람과 공유합니다.
공유 후 이러한 구성 요소는 수신자의 작업 영역의 구성 요소 드롭다운에 나타납니다. 이 설정은 지속되지 않으며 공유 시 하나의 동작입니다.
1. (선택 사항) 이 페이지를 수신자의 랜딩 페이지로 설정합니다.
이 설정은 유지되지 않습니다. 공유 시의 단일 작업입니다.
1. 공유를 클릭합니다.
또한 조정 및 공유 **[!UICONTROL 를 클릭하여 프로젝트 조정을]** 자동으로 적용할 수도 있습니다. 프로젝트가 이미 공유된 경우 이 단추에는 **[!UICONTROL 업데이트]** 및 **[!UICONTROL 조정 및 업데이트가 표시됩니다]**. 프로젝트 조정에 대한 자세한 [내용을 살펴보십시오](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/curate-share/curate.html).

![](assets/share-proj-modal.png)

## 받는 사람 그룹에 공유

모든 사용자는 수신자의 집합인 그룹에 프로젝트를 공유할 수 있습니다. Adobe Analytics에서 그룹은 Adobe Experience Cloud의 제품 프로필로 정의됩니다.

* 관리자는 &quot;모두&quot;를 비롯한 모든 그룹과 공유할 수 있습니다.
* 관리자가 아닌 사용자는 &quot;모두&quot;를 제외하고 자신이 구성원으로 있는 그룹과 공유할 수 있습니다.

## 프로젝트 관리자에서 프로젝트 공유

[구성 요소] > [ [!UICONTROL 프로젝트]에서 프로젝트를 공유할 수도] 있습니다 . 위의 동일한 단계에 따라 단일 프로젝트를 공유할 수 있습니다.

여러 프로젝트를 공유하도록 선택하면 받는 사람이 각 프로젝트에 대한 기존 수신자 목록에 추가됩니다. 예:

* 프로젝트 A는 1, 2, 3 사용자와 공유됩니다.
* 프로젝트 B는 4, 5, 6 사용자와 공유됩니다.
* 프로젝트 A와 B를 선택하면 4와 7명의 사용자가 수신자 목록에 추가됩니다. 각 프로젝트에 대한 새 수신자 목록:
   * 프로젝트 A: 1, 2, 3, 4, 7
   * 프로젝트 B: 4, 5, 6, 7
   ![](assets/mult-proj-sharing.png)
