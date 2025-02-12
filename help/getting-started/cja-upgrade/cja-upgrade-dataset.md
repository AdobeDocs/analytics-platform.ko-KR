---
title: Customer Journey Analytics에 대한 스키마 만들기
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 44%

---

# Customer Journey Analytics에 사용할 데이터 세트 만들기 {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Adobe Experience Platform에 데이터 세트 만들기"
>abstract="데이터 세트는 수집된 데이터가 있는 위치입니다. Adobe Experience Platform에 이 위치를 만듭니다.<br><br>스키마를 염두에 두고 데이터 세트를 만들면 몇 분이면 충분합니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나 [Adobe Analytics-Customer Journey Analytics 업그레이드 설문지](https://gigazelle.github.io/cja-ttv/)를 통해 조직에 대해 동적으로 생성된 업그레이드 단계를 따를 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

데이터 집합은 Adobe Experience Platform에 수집하는 데이터를 저장하고 관리하는 구조입니다.

데이터 세트를 만들려면 다음 작업을 수행하십시오.

1. Adobe Experience Platform의 왼쪽 레일에서 [!UICONTROL 데이터 관리] 내의 **[!UICONTROL 데이터 세트]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 세트 만들기]**&#x200B;를 선택합니다.

   ![데이터 세트 만들기](assets/create-dataset.png)

1. **[!UICONTROL 스키마에서 데이터 세트 만들기]**&#x200B;를 선택합니다.

   ![스키마에서 데이터 세트 만들기](assets/create-dataset-from-schema.png)

1. 이전에 만든 스키마를 선택하고 **[!UICONTROL 다음]**&#x200B;을 선택합니다.

1. 데이터 세트의 이름을 지정하고 (선택 사항) 설명을 제공합니다.

   ![데이터 세트 이름 지정](assets/name-your-datatest.png)

1. **[!UICONTROL 마침]**&#x200B;을 선택합니다.

1. **[!UICONTROL 프로필]** 전환을 선택합니다.

   데이터 세트를 프로필용으로 활성화하라는 메시지가 표시됩니다. 활성화되면 데이터 세트는 수집된 데이터로 실시간 고객 프로필을 강화합니다.

   >[!IMPORTANT]
   >
   >    데이터 세트가 준수하는 스키마가 프로필용으로 활성화된 경우에만 데이터 세트를 프로필용으로 활성화할 수 있습니다.

   ![프로필용으로 스키마 활성화](assets/aepwebsdk-dataset-profile.png)

   데이터 집합을 보고, 미리 보고, 만들고, 삭제하는 방법에 대한 자세한 내용은 [데이터 집합 UI 안내서](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html)를 참조하세요. 실시간 고객 프로필에 대한 데이터 세트를 활성화하는 방법도 배울 수 있습니다.

1. [권장된 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 [동적으로 생성된 업그레이드 단계](https://gigazelle.github.io/cja-ttv/)를 계속 따릅니다.
