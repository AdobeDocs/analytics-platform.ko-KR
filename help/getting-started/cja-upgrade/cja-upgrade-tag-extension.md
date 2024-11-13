---
title: 태그 속성 만들기 및 웹 SDK 확장 추가
description: 태그 속성을 만들고 웹 SDK 확장을 추가하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ccc6df56771cd9f83bbd7a8570e32d7ed63a0ced
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 23%

---

# 태그에 Web SDK 확장 추가

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

Adobe Experience Platform 내의 태그 기능을 사용하여 사이트에서 코드를 구현하여 데이터를 수집할 수 있습니다. 이는 다른 태그 지정 요구 사항과 함께 코드를 배포할 수 있도록 해 주는 태그 관리 솔루션입니다. 태그는 Adobe Experience Platform Web SDK 확장을 사용하여 Adobe Experience Platform과 원활하게 통합할 수 있도록 해 줍니다.

다음 정보는 태그에 Web SDK 확장을 추가하는 방법을 설명합니다. 자세한 내용은 Experience Platform 설명서에서 [Web SDK 태그 확장 구성](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)을 참조하십시오. Web SDK에는 기본적으로 [!UICONTROL Adobe Experience Cloud ID 서비스]가 포함되어 있으므로 ID 서비스 확장을 태그에 추가할 필요가 없습니다.

[태그를 만든](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) 후에는 Adobe Experience Platform Web SDK 확장을 사용하여 태그를 구성해야 합니다. 이렇게 하면 데이터 스트림을 통해 Adobe Experience Platform으로 데이터를 전송할 수 있습니다.

태그에 Web SDK 확장을 추가하려면:

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. [!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 확장]**&#x200B;을 선택합니다.

1. 상단 막대에서 **[!UICONTROL 카탈로그]**&#x200B;를 선택합니다.

1. **[!UICONTROL Adobe Experience Platform Web SDK 확장]**&#x200B;을 검색하거나 스크롤한 다음 **[!UICONTROL 설치]**&#x200B;를 선택하여 설치합니다.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. [!UICONTROL 프로덕션 환경], (선택 사항) [!UICONTROL 스테이징 환경] 및 [!UICONTROL 개발 환경]에 대해 샌드박스와 이전에 만든 데이터스트림을 선택합니다.

   ![AEP Web SDK 확장 구성](assets/aepwebsk-extension-datastreams.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

1. [권장된 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 [동적으로 생성된 업그레이드 단계](https://gigazelle.github.io/cja-ttv/)를 계속 따릅니다.