---
title: Web SDK 확장에 대한 로더 태그 구현
description: Web SDK 확장에 대한 로더 태그를 구현하는 방법에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 937a7f31361027438929194f8ccc5aee83c33bc0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 34%

---

# Web SDK 확장에 대한 로더 태그 구현

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

추적할 웹 사이트에 태그를 설치해야 합니다. 즉, 웹 사이트 템플릿의 헤더 태그에 코드를 배치해야 합니다.

다음 프로세스에서는 태그를 참조하는 코드를 가져오는 방법을 설명합니다. 자세한 내용은 Experience Platform 설명서에서 [태그 및 이벤트 전달에 대한 구현 가이드](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides)를 참조하십시오.

태그를 참조하는 코드를 가져오는 경우:

1. 왼쪽 레일에서 **[!UICONTROL 환경]**&#x200B;을 선택합니다.

1. 환경 목록에서 올바른 설치(상자) 버튼을 선택합니다.

   [!UICONTROL 웹 설치 지침] 대화 상자에서 다음과 유사한 스크립트 코드 옆에 있는 복사 버튼을 선택합니다.

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![환경](assets/environment.png)

1. **[!UICONTROL 닫기]**&#x200B;를 선택합니다.

   개발 환경의 코드 대신 Adobe Experience Platform Web SDK 배포 과정을 기준으로 다른 환경(스테이징, 프로덕션)을 선택할 수 있습니다.

   자세한 내용은 [환경](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?)을 참조하십시오.

1. [권장된 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 [동적으로 생성된 업그레이드 단계](https://gigazelle.github.io/cja-ttv/)를 계속 따릅니다.
