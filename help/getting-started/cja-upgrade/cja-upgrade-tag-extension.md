---
title: 태그 속성을 만들고 웹 SDK 확장 추가
description: 태그 속성을 만들고 웹 SDK 확장을 추가하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 40%

---

# 태그에 Web SDK 확장 기능 추가 {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="태그 속성에 플랫폼 Web SDK 확장 기능 추가"
>abstract="태그 속성에 Adobe Experience Platform Web SDK 확장 기능을 추가합니다. 태그 속성에 Web SDK 확장 기능을 추가하는 과정이 간소화되어 완료하는 데 몇 분밖에 걸리지 않습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Experience Platform 내의 태그 기능을 사용하여 사이트에서 코드를 구현하여 데이터를 수집할 수 있습니다. 이는 다른 태그 지정 요구 사항과 함께 코드를 배포할 수 있도록 해 주는 태그 관리 솔루션입니다. 태그는 Adobe Experience Platform Web SDK 확장을 사용하여 Adobe Experience Platform과 원활하게 통합할 수 있도록 해 줍니다.

다음 정보는 태그에 Web SDK 확장을 추가하는 방법을 설명합니다. 자세한 내용은 Experience Platform 설명서에서 [웹 SDK 태그 확장 구성](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)을 참조하십시오. 웹 SDK에는 기본적으로 [!UICONTROL Adobe Experience Cloud ID 서비스]가 포함되어 있으므로 태그에 ID 서비스 확장을 추가할 필요가 없습니다.

[태그를 만든](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) 후에는 Adobe Experience Platform Web SDK 확장을 사용하여 태그를 구성해야 합니다. 이렇게 하면 데이터 스트림을 통해 Adobe Experience Platform으로 데이터를 전송할 수 있습니다.

태그에 웹 SDK 확장을 추가하려면:

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
