---
title: Customer Journey Analytics을 위한 스키마 만들기
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 30%

---

# Customer Journey Analytics에 사용할 데이터 세트 만들기

>[!NOTE]
>
>Adobe Analytics 이 설명서는 [업그레이드 Customer Journey Analytics 설문지](https://gigazelle.github.io/cja-ttv/)를 작성한 후 사용해야 합니다.
> 
>조직에 대해 동적으로 생성된 이전 단계를 모두 완료한 후에만 이 페이지의 단계를 따르십시오.
>
>이 페이지의 단계를 완료한 후 [Adobe Analytics에서 조직에 대해 동적으로 생성된 업그레이드 단계를 계속 수행하여 업그레이드 질문을 Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/)하십시오.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

XDM 스키마를 만든 후에는 해당 데이터를 저장하고 관리할 구성을 정의해야 합니다. 이 작업은 데이터 세트를 통해 Adobe Experience Platform에서 수행됩니다.

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

1. [Adobe Analytics에서 업그레이드 Customer Journey Analytics 설문 조사](https://gigazelle.github.io/cja-ttv/)로 조직에 대해 동적으로 생성된 업그레이드 단계를 계속 수행합니다.
