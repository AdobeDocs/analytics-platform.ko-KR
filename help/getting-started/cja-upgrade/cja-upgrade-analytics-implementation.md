---
title: Adobe Analytics 구현 및 Customer Journey Analytics 업그레이드에 미치는 영향 이해
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 3827bafd85a03e8574667095b372aa61afb6756b
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 9%

---

# Adobe Analytics 구현 및 Customer Journey Analytics 업그레이드에 미치는 영향 이해

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

Customer Journey Analytics으로 업그레이드하는 방법은 다양하지만, 각 유형의 Adobe Analytics 구현에 대해 일부 업그레이드 경로를 사용할 수 있는 것은 아닙니다. 그러나 권장되는 업그레이드 경로는 조직에서 Adobe Analytics을 구현하는 방법에 관계없이 사용할 수 있습니다.

아래 정보를 사용하여 현재 Adobe Analytics 구현 및 조직에서 사용할 수 있는 업그레이드 경로를 이해할 수 있습니다.

보다 구체적인 조언, 안내 또는 지원이 필요한 경우 Adobe 담당자에게 문의하십시오.

| 기존 Adobe Analytics 구현 | 설명 | 사용 가능한 업그레이드 경로 |
|---------|----------|----------|
| AppMeasurement | JavaScript용 AppMeasurement은 지금까지 Adobe Analytics을 구현하는 일반적인 방법이었습니다.<p>이 AppMeasurement 유형에 대한 자세한 내용은 [JavaScript용 구현으로 Adobe Analytics 구현](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)을 참조하십시오.</p> | <ul><li>(권장) Analytics Source 커넥터를 사용한 Experience Platform Web SDK의 새로운 구현</li><li>Experience Platform 웹 SDK의 새로운 구현</li><li>웹 SDK로 Adobe Analytics 마이그레이션</li><li>Analytics Source 커넥터</li></ul> |
| Adobe Analytics 확장(태그) | <p>Adobe Experience Platform의 태그는 다른 태그 지정 요구 사항과 함께 Analytics 코드를 배포할 수 있도록 해 주는 태그 관리 솔루션입니다. Adobe는 다른 솔루션 및 제품과의 통합을 제공하며 사용자 정의 코드를 배포할 수 있도록 해 줍니다. 따라서 사이트에서 코드를 업데이트하기 위해 조직의 개발 팀에 의존하지 않고도 이러한 모든 작업을 수행할 수 있습니다.</p><p>이 구현 유형에 대한 자세한 내용은 [Analytics 확장을 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)을 참조하십시오</p> | <ul><li>(권장) Analytics Source 커넥터를 사용한 Experience Platform Web SDK의 새로운 구현</li><li>Experience Platform 웹 SDK의 새로운 구현</li><li>웹 SDK로 Adobe Analytics 마이그레이션</li><li>Analytics Source 커넥터</li></ul> |
| Experience Platform Web SDK (alloy.js) | Web SDK Experience Platform은 Adobe Analytics을 구현하기 위해 Adobe이 현재 권장하는 방법입니다. Adobe Experience Platform Edge Network을 사용하면 여러 제품으로 전송되는 데이터를 중앙 위치에 전송할 수 있습니다. <p>이 구현 유형에 대한 자세한 내용은 [Adobe Experience Platform Edge Network을 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)을 참조하십시오.</p> | <ul><li>(권장) Analytics Source 커넥터를 사용한 Experience Platform Web SDK의 새로운 구현</li><li>Platform으로 데이터를 전송하도록 Adobe Analytics Web SDK 구현 구성</li></ul> |
| Experience Platform Web SDK 확장 프로그램(태그) | Web SDK Experience Platform은 웹 데이터용 Adobe Analytics을 구현하기 위해 Adobe이 현재 권장하는 방법입니다. Adobe Experience Platform Edge Network을 사용하면 여러 제품으로 전송되는 데이터를 중앙 위치에 전송할 수 있습니다. <p>이 구현 유형에 대한 자세한 내용은 [https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)을(를) 참조하십시오</p> | <ul><li>(권장) Analytics Source 커넥터를 사용한 Experience Platform Web SDK의 새로운 구현</li><li>Platform으로 데이터를 전송하도록 Adobe Analytics Web SDK 구현 구성</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK는 모바일 데이터용 Adobe Analytics을 구현하기 위해 Adobe이 현재 권장하는 방법입니다. Adobe Experience Platform Edge Network을 사용하면 여러 제품으로 전송되는 데이터를 중앙 위치에 전송할 수 있습니다.<p>Adobe Experience Platform Mobile SDK는 모바일 앱에서 Adobe의 Experience Cloud 솔루션 및 서비스를 강화하는 데 도움이 됩니다. </p><p>이 구현 유형에 대한 자세한 내용은 [Adobe Experience Platform Mobile SDK를 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)을 참조하십시오.</p> | <ul><li>(권장) Analytics Source 커넥터를 사용한 Experience Platform Web SDK의 새로운 구현</li><li>Platform으로 데이터를 전송하도록 Adobe Analytics Web SDK 구현 구성</li></ul> |

{style="table-layout:auto"}
