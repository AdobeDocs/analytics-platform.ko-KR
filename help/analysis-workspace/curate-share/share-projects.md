---
description: 작업 영역의 프로젝트 공유 및 프로젝트 역할
keywords: Analysis Workspace 공유
title: 프로젝트 공유
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '2091'
ht-degree: 68%

---

# 프로젝트 공유

Analysis Workspace 프로젝트를 다음 유형의 사람과 공유할 수 있습니다.

* Adobe Customer Journey Analytics에 액세스할 수 있는 조직의 사용자 및 그룹

  편집, 복제 또는 보기 액세스 권한 공유 가능

* Customer Journey Analytics 액세스 권한이 없는 조직의 사용자 및 그룹

  수신자는 읽기 전용 액세스 권한 보유

* 조직 외부의 사람

  수신자는 읽기 전용 액세스 권한 보유

공유 전 적용한 모든 [조정](curate.md) 기능은 수신자가 프로젝트를 열 때 반영됩니다.

다음은 프로젝트 공유에 대한 비디오 개요입니다.

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## 조직의 Customer Journey Analytics 사용자 및 그룹과 공유 {#Add}

조직의 기존 Customer Journey Analytics 사용자 또는 그룹과 프로젝트를 공유할 수 있습니다. 이 섹션에 설명된 대로 프로젝트를 공유할 때 공유하는 사용자에게는 이미 Customer Journey Analytics 계정이 있어야 합니다.

사용자 또는 그룹과 특정 역할을 공유하거나 링크를 공유할 수 있습니다.

* [특정 프로젝트 역할 공유](#share-a-specific-project-role)

* [프로젝트에 대한 링크 공유](#share-a-link-to-a-project)

## 특정 프로젝트 역할 공유

조직의 사용자 및 그룹과 특정 프로젝트 역할을 공유할 때는 다음 사항을 고려해 보십시오.

* 프로젝트 역할(**[!UICONTROL 원본 편집]**, **[!UICONTROL 사본 편집]** 및 **[!UICONTROL 읽기 전용]**)은 사용자 및 특정 프로젝트 ID에 연결되어 있습니다. 프로젝트 역할은 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=ko-KR)에서 관리하는 사용자 권한과 다릅니다.

* Customer Journey Analytics에서 그룹은 의 제품 프로필로 정의됩니다. [Adobe Experience Cloud 관리 콘솔](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=ko-KR). 관리자는 “모두”를 비롯한 모든 그룹과 공유할 수 있습니다. 관리자가 아닌 사용자는 “모두”를 제외하고 자신이 구성원으로 있는 그룹과 공유할 수 있습니다.

* 여러 역할에 배치된 사용자는 항상 가장 높은 경험을 받게 됩니다. 사용자가 개인과 그룹의 일부로 모두 추가되는 경우 여러 역할에 배치될 수 있습니다. 예를 들어 사용자에게 개인으로서 **[!UICONTROL 원본 편집]** 역할이 주어지고 및 그룹의 구성원으로 **[!UICONTROL 읽기 전용]** 역할이 주어지면 해당 사용자에게는 **[!UICONTROL 원본 편집]** 프로젝트 경험이 제공됩니다.

* **[!UICONTROL 사본 편집]** 또는 **[!UICONTROL 읽기 전용]** 역할에 배치된 관리자는 프로젝트를 열 때 제한된 경험을 받게 됩니다. 관리자는 다음 절차에 설명된 대로 프로젝트를 자신과 공유하고 편집 역할을 부여하여 자신의 역할을 **[!UICONTROL 원본 편집]**&#x200B;으로 변경할 수 있습니다.

* 여러 프로젝트를 공유하도록 선택하면 수신자가 각 프로젝트에 대한 기존 수신자 목록에 추가됩니다.

  예를 들어 프로젝트 A는 수신자 1, 2 및 3에게 공유되고, 프로젝트 B는 수신자 4, 5 및 6에게 공유됩니다.

  그러면 프로젝트 A와 B는 수신자 4와 7에게 공유됩니다. 이제 프로젝트 A에 대한 새 공유 목록은 1, 2, 3, 4 및 7이고 프로젝트 B에 대한 새 공유 목록은 4, 5, 6 및 7입니다.

조직의 사용자 또는 그룹과 특정 프로젝트 역할을 공유하려면 다음 작업을 수행합니다.

1. Customer Journey Analytics에서 [!UICONTROL **작업 영역**] 탭을 선택한 다음 를 선택합니다 [!UICONTROL **프로젝트**] 왼쪽 레일에서.

1. 공유하려는 한 개 이상의 프로젝트 옆에 있는 확인란을 선택한 다음 [!UICONTROL **공유**]&#x200B;를 선택합니다.

   또는

   개별 프로젝트만 공유하려면 공유하려는 프로젝트를 연 다음 **[!UICONTROL 공유]** > **[!UICONTROL Workspace 사용자와 공유]**를 선택합니다.
저장되지 않은 변경 사항이 있는 경우 먼저 프로젝트를 저장하라는 메시지가 표시됩니다.

   프로젝트 공유 대화 상자가 표시됩니다. 대화 상자의 [!UICONTROL **링크로 공유**] 및 [!UICONTROL **설정**] 섹션은 단일 프로젝트를 공유하는 경우에만 표시됩니다.

   ![프로젝트 공유 창.](assets/share-proj-modal.png)

1. 제공된 역할 필드 중 하나에 수신자 또는 수신자 그룹을 추가합니다.

   **원본 편집:** 수신자는 프로젝트 및 기능에 대한 변경 내용을 공동 소유자로서 **[!UICONTROL 저장]**&#x200B;할 수 있습니다. 이 역할은 프로젝트를 다른 동료와 공동 관리하려는 경우 유용합니다. 여기에는 공유 프로젝트에 대한 수신자 목록 편집, 삭제 및 수정 등이 포함됩니다. <br>참고: Analysis Workspace는 현재 라이브 공동 작업을 지원하지 않으므로 주어진 시간에 한 명의 사용자만 프로젝트를 편집하는 것이 좋습니다. 프로젝트를 동시에 저장하는 경우 마지막 버전이 유지됩니다.

   **사본 편집:** 수신자는 **[!UICONTROL 다른 이름으로 저장]**&#x200B;하고 왼쪽 레일에 액세스할 수 있습니다. 이 역할에서는 프로젝트 상호 작용이 제한되지 않습니다. 이 역할은 조직의 데이터를 이해하고 Analysis Workspace 사용 방법을 알고 있지만 프로젝트를 변경하지 않으려는 사용자에게 프로젝트를 공유하려는 경우에 유용합니다.

   **읽기 전용:** 수신자는 **[!UICONTROL 저장]** 또는 **[!UICONTROL 다른 이름으로 저장]**&#x200B;할 수 없으며 왼쪽 레일에 액세스할 수 없습니다. 상호 작용이 제한됩니다. 이 역할은 일반적으로 조직의 데이터 구조, Analysis Workspace 또는 Customer Journey Analytics에 익숙하지 않은 사용자에게 프로젝트를 공유하려는 경우에 유용합니다. 그럼에도 불구하고, 안전한 환경에서 데이터와 인사이트를 소비해야 합니다. [읽기 전용 프로젝트 경험](/help/analysis-workspace/curate-share/view-only-projects.md)에 대해 자세히 알아보십시오.

1. (조건부) 단일 프로젝트를 공유하는 경우 프로젝트를 공유할 때 다음 옵션을 활성화할지 여부를 선택합니다.

   * **포함된 프로젝트 구성 요소 공유:** 필터, 계산된 지표 및 날짜 범위를 모든 수신자와 공유합니다. 이러한 구성 요소가 공유되면 수신자 작업 영역의 [구성 요소] 드롭다운에 표시됩니다. 이 설정은 공유 시점에만 수행되는 일회성 작업으로, 유지되지 않습니다.

   * **수신자의 랜딩 페이지로 설정:** 이 페이지를 수신자의 랜딩 페이지로 설정합니다. 이 설정은 공유 시점에만 수행되는 일회성 작업으로, 유지되지 않습니다.

1. **[!UICONTROL 공유]**&#x200B;를 선택합니다. (프로젝트가 이미 공유된 경우 [!UICONTROL **업데이트**]&#x200B;를 선택합니다.)

   또는

   **[!UICONTROL 조정 및 공유]**&#x200B;를 선택하여 프로젝트 조정을 자동으로 적용합니다. (프로젝트가 이미 공유된 경우 **[!UICONTROL 조정 및 업데이트]**&#x200B;를 선택합니다.) [프로젝트 조정](curate.md)에 대한 자세한 내용을 살펴보십시오.

## 프로젝트에 대한 링크 공유

이 섹션에 설명된 대로 링크를 공유할 때는 다음 사항을 고려해 보십시오.

* 링크를 사용하는 수신자는 프로젝트에 액세스하기 전에 Customer Journey Analytics에 로그인해야 합니다.

* 수신자가 역할이 할당되지 않은 상태에서 프로젝트에 대한 [링크](/help/analysis-workspace/curate-share/shareable-links.md)를 받은 경우(**[!UICONTROL 공유] > [!UICONTROL 프로젝트 링크 가져오기]**) 수신자는 기본적으로 역할을 받게 됩니다. 관리자는 **[!UICONTROL 원본 편집]** 역할을, 관리자가 아닌 사용자는 **[!UICONTROL 사본 편집]** 역할을 받습니다.

조직의 사용자와 프로젝트 링크를 공유하려면 다음 작업을 수행합니다.

1. 프로젝트를 저장합니다. 저장되지 않은 변경 사항이 있는 경우 링크를 공유하기 전에 프로젝트를 저장하라는 메시지가 표시됩니다.

1. **[!UICONTROL 공유]** > **[!UICONTROL Workspace 사용자와 공유]**&#x200B;를 선택한 다음 **[!UICONTROL 링크로 공유]** 필드 옆의 **[!UICONTROL 복사]**&#x200B;를 선택합니다.

   ![공유 프로젝트 는 링크로 공유 필드를 강조 표시합니다.](assets/share-proj-modal.png)

1. 조직의 사용자와 링크를 공유합니다. 예를 들어 공유된 링크를 이메일, 내부 웹 사이트 등에 붙여넣을 수 있습니다.

## 모두와 프로젝트 공유(로그인 필요 없음) {#share-public-link}

다음을 부여할 수 있습니다 [읽기 전용 액세스](/help/analysis-workspace/curate-share/view-only-projects.md) Customer Journey Analytics 액세스 권한이 없는 사람에게 Analysis Workspace 프로젝트를 제공할 수 있습니다. 이러한 사용자에는 다음이 포함될 수 있습니다.

* 조직 외부의 사람

* 조직 내에서 Customer Journey Analytics 액세스 권한이 없는 사람

>[!NOTE]
>
>Customer Journey Analytics 액세스 권한이 없는 사용자와 Analysis Workspace 프로젝트를 공유할 때는 다음 사항을 고려하십시오.
>
>* Customer Journey Analytics 관리자가에 설명된 대로 이러한 방식으로 프로젝트를 공유하는 기능은 비활성화할 수 있습니다 [환경 설정](/help/analysis-workspace/user-preferences.md). 이 섹션에 설명된 대로 프로젝트를 공유할 수 없는 경우 Customer Journey Analytics 관리자가 이 기능을 비활성화했습니다.
>
>* 확장된 시각화가 50개를 초과하는 프로젝트는 Customer Journey Analytics 액세스 권한이 없는 사용자와 공유할 수 없습니다.
>
>* 공유하는 사용자는 다음 기간 동안 프로젝트에 적용된 모든 필터를 볼 수 있습니다. [큐레이션](curate.md).
> 
>* 공유받는 사용자는 프로젝트 날짜 범위를 변경할 수 있습니다. 공유 주체인 사용자가 프로젝트에 대해 설정한 날짜 범위가 기본적으로 표시됩니다.
>
>* 많은 사용자가 동시에 특정 링크에 액세스하려고 하면 프로젝트에 액세스하는 것이 불가능할 수 있습니다. 기본적으로 190명 이상의 사용자가 5분마다 단일 링크에 액세스할 수 있습니다. 조직이 이 제한에 도달하면 5분 동안 기다린 후 링크에 다시 액세스해 보십시오.
>
>* 조직에서 Healthcare Shield를 라이선스할 경우 SSO(Single Sign-On) 또는 Adobe ID으로 인증된 사용자만 프로젝트를 공유할 수 있으며 인증되지 않은 사용자와 프로젝트를 공유할 수는 없습니다. 회사의 내부 데이터 거버넌스 정책을 준수하여 이 기능을 사용하고 적절한 권한이 있는 사용자와 PHI(개인 건강 정보)가 포함된 프로젝트 링크만 공유하는 것은 사용자의 책임입니다.

다음 비디오 데모 및 관련 문서에서는 모두와 링크를 공유하는 것과 관련된 옵션을 설명합니다.

>[!VIDEO](https://video.tv.adobe.com/v/3420093/?learn=on)

Analysis Workspace 프로젝트를 누구와도 공유하려면 다음 작업을 수행하십시오.

1. 공유하려는 Analysis Workspace 프로젝트를 엽니다.

1. **[!UICONTROL 공유]** > **[!UICONTROL 모두와 공유]**&#x200B;를 클릭합니다.

   저장되지 않은 변경 사항이 있는 경우 프로젝트를 저장하라는 메시지가 표시됩니다.

   <!-- Add screen shot of new modal -->

1. **[!UICONTROL 링크 활성화됨]** 옵션이 아직 활성화되지 않은 경우 활성화합니다.

   이 옵션을 선택하면 모두와 공유할 수 있는 프로젝트 링크가 만들어집니다. 이 옵션을 비활성화하면 언제든지 프로젝트에 대한 액세스를 비활성화할 수 있습니다.

   프로젝트 소유자가 이 링크의 소유자에 해당합니다. Analytics 관리 안내서의 [사용자 자산 전송 또는 계정 만료 설정](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html)에 설명된 대로 프로젝트 소유권이 이전된 경우에만 링크 소유권을 다른 사용자에게 이전할 수 있습니다.

1. 다음 보안 옵션을 사용할지 여부를 선택합니다(이 옵션은 Customer Journey Analytics 관리자가 제어할 수 있음).

   * **[!UICONTROL Experience Cloud 인증 필요]:**

     이 옵션이 활성화된 경우 프로젝트에 액세스할 수 있는 사용자는 공유 중인 프로젝트가 생성된 Adobe Experience Cloud 조직에 로그인할 수 있는 사용자만 됩니다. 그러나 공유받는 사용자가 Adobe Analytics에 액세스할 필요는 없습니다.

     Customer Journey Analytics 관리자는에 설명된 대로 회사에 대해 이 환경 설정을 구성할 수 있습니다. [환경 설정](/help/analysis-workspace/user-preferences.md). 관리자가 이 옵션을 구성한 방식에 따라 다음 시나리오가 발생할 수 있습니다.

      * 이 옵션이 표시되지 않으면 Customer Journey Analytics 관리자가 이 기능을 활성화하지 않은 것입니다.

      * 이 옵션이 활성화되어 있고 비활성화할 수 없는 경우, 이는 Customer Journey Analytics 관리자가 Analysis Workspace 프로젝트에 액세스하는 모든 사용자에게 Experience Cloud 인증을 요구함을 의미합니다. 이는 Healthcare Shield를 허가한 조직의 경우 항상 해당됩니다.

1. 다음 옆에 **[!UICONTROL 누구와도 공유(로그인 필요 없음)]** 필드를 클릭하고 **링크 복사** 아이콘 ![링크 복사 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Link_18_N.svg))를 클릭하여 링크를 시스템 클립보드에 복사합니다.

1. 프로젝트에 액세스하도록 할 사람에게 링크를 공유합니다. 예를 들어 이메일에 링크를 붙여넣을 수 있습니다.

   링크를 공유하는 사람은 누구나 Analysis Workspace 프로젝트를 볼 수 있습니다.

1. (선택 사항) **새 링크 생성** 아이콘 ![링크 생성 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)을 클릭하여 이전에 프로젝트 링크를 받은 사용자의 액세스 권한을 제거할 수 있습니다. 프로젝트에 액세스하도록 할 사용자와 공유할 수 있는 새 링크가 생성됩니다.

1. **[!UICONTROL 닫기]**&#x200B;를 선택하여 공유 대화 상자를 닫습니다. 변경 내용은 자동으로 저장됩니다.

## 사용자와 공유한 프로젝트 보기

누군가가 [특정 프로젝트 역할을 공유](#share-a-specific-project-role)하여 사용자와 프로젝트를 공유하는 경우 [Analytics 랜딩 페이지의 프로젝트 탭](/help/getting-started/landing.md#navigate-the-projects-tab)에서 공유 프로젝트에 액세스할 수 있습니다.

다른 사용자가 링크를 공유하여 프로젝트를 귀하와 공유하는 경우(다음 중 하나에서) [프로젝트 탭 공유](#share-a-link-to-a-project) 또는 를 사용하여 [모든 사람과 공유 링크](#share-a-project-with-anyone-no-login-required))을 클릭하여 프로젝트에 액세스하려는 경우 공유된 링크를 사용해야 합니다. 예를 들어 링크가 이메일, 내부 웹 사이트 등을 통해 공유되었을 수 있습니다.

## 임베드된 구성 요소 공유

다음은 해당 주제에 대한 비디오입니다.

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## FAQ {#FAQs}

| 질문 | 답변 |
|---|---|
| 두 명의 편집자가 동시에 프로젝트를 저장하면 어떻게 됩니까? | 변경 사항은 병합되지 않고 마지막으로 저장한 프로젝트 버전이 유지됩니다. Analysis Workspace는 현재 실시간 공동 작업을 지원하지 않습니다. |
| 관리자는 어떤 프로젝트 경험을 보게 됩니까? | 에 배치된 관리자 **[!UICONTROL 사본 편집]** 또는 **[!UICONTROL 읽기 전용]** 역할이 프로젝트를 열 때 제한된 경험을 받게 됩니다. 원하는 경우 관리자는 자신의 역할을 다음과 같이 늘릴 수 있습니다. **[!UICONTROL 원본 편집]** 까지 언제든지 **[!UICONTROL 구성 요소] > [!UICONTROL 프로젝트]**. |
| 수신자가 하나의 역할에서 개인 또는 그룹의 구성원으로서의 다른 역할에 배치되면 어떻게 됩니까? | 수신자가 여러 역할에 배치되면 항상 더 높은 경험을 받게 됩니다. 예를 들어 수신자에게 **[!UICONTROL 원본 편집]** 개인으로서의 역할 및 **[!UICONTROL 보기 가능]** 그룹의 구성원으로서의 역할은 **[!UICONTROL 원본 편집]** 프로젝트 경험. |
| 프로젝트 링크를 열면 수신자는 어떤 경험을 얻을 수 있습니까? | 수신자는 공유 모달에서 지정한 역할을 받습니다. 수신자에게 역할이 할당되지 않고 프로젝트에 대한 링크를 받은 경우(**[!UICONTROL 공유]** > **[!UICONTROL Workspace 사용자와 공유]**, 이후 **[!UICONTROL 링크로 공유]** 필드 옆의 **[!UICONTROL 복사]** 선택) 기본적으로 역할을 받게 됩니다. 관리자는 **[!UICONTROL 원본 편집]** 역할을, 관리자가 아닌 사용자는 **[!UICONTROL 사본 편집]** 역할을 받습니다. |
