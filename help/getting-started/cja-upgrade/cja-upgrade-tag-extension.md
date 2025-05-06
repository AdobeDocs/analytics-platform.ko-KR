---
title: 태그 속성 만들기 및 Web SDK 확장 기능 추가
description: 태그 속성 만들기 및 Web SDK 확장 기능 추가에 대해 자세히 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '302'
ht-degree: 100%

---

# 태그에 Web SDK 확장 기능 추가 {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="태그 속성에 Platform Web SDK 확장 기능 추가"
>abstract="태그 속성에 Adobe Experience Platform Web SDK 확장 기능을 추가합니다. 태그 속성에 Web SDK 확장 기능을 추가하는 과정이 간소화되어 완료하는 데 몇 분밖에 걸리지 않습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

사이트에서 코드를 구현하는 Adobe Experience Platform의 태그 기능을 사용하여 실제로 데이터를 수집할 있습니다. 이는 다른 태그 지정 요구 사항과 함께 코드를 배포할 수 있도록 해 주는 태그 관리 솔루션입니다. 태그는 Adobe Experience Platform Web SDK 확장을 사용하여 Adobe Experience Platform과 원활하게 통합할 수 있도록 해 줍니다.

다음 정보는 태그에 Web SDK 확장 기능을 추가하는 방법을 설명합니다. 추가 정보 Experience Platform 설명서의 [Web SDK 태그 확장 기능 구성](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)을 참조하십시오. Web SDK에는 [!UICONTROL Adobe Experience Cloud ID 서비스]가 기본적으로 제공되므로 태그에 ID 서비스 확장 기능을 추가할 필요가 없습니다.

[태그 만들기](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) 후 Adobe Experience Platform Web SDK 확장 기능을 사용하여 구성해야 합니다. 이렇게 하면 (데이터스트림을 통해_ Adobe Experience Platform으로 데이터를 전송할 수 있습니다.

태그에 Web SDK 확장 기능 추가 방법:

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**&#x200B;로 이동합니다.

1. [!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 확장]**&#x200B;을 선택합니다.

1. 상단 막대에서 **[!UICONTROL 카탈로그]**&#x200B;를 선택합니다.

1. **[!UICONTROL Adobe Experience Platform Web SDK 확장 기능]**&#x200B;을 검색한 후 **[!UICONTROL 설치]**&#x200B;를 선택하여 설치합니다.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. [!UICONTROL 프로덕션 환경], (선택 사항) [!UICONTROL 스테이징 환경] 및 [!UICONTROL 개발 환경]에 대해 샌드박스와 이전에 만든 데이터스트림을 선택합니다.

   ![AEP Web SDK 확장 구성](assets/aepwebsk-extension-datastreams.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

{{upgrade-final-step}}
