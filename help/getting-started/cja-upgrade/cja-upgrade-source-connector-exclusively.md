---
title: Analytics 소스 커넥터만 사용하여 Customer Journey Analytics으로 업그레이드
description: Analytics 소스 커넥터를 만들고 필드를 매핑하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 07570641949e17d30b7f9f5b38eb95c29c5176c0
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Analytics 소스 커넥터만 사용하여 Customer Journey Analytics으로 업그레이드

>[!NOTE]
> 
>[Customer Journey Analytics 업그레이드 확인 목록](https://gigazelle.github.io/cja-ttv/)의 질문에 답변할 때 이 페이지의 정보를 사용하십시오.

권장되지는 않지만 Analytics 소스 커넥터를 Customer Journey Analytics의 유일한 구현 경로로 사용할 수 있습니다. 그러나 이러한 유형의 업그레이드와 관련된 고유한 단점 때문에 Adobe에서는 Experience Platform Web SDK의 새로운 구현과 함께 Analytics 소스 커넥터를 사용하는 것이 좋습니다. 이 권장 업그레이드 경로에 대한 자세한 내용은 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 [권장 경로](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)를 참조하십시오.

다음 정보를 사용하여 소스 커넥터만 사용할 때의 장단점을 이해하십시오.

| 장점 | 단점 |
|----------|---------|
| <ul><li>시간 소모가 적고 까다로운 업그레이드 경로. <p>데이터는 Customer Journey Analytics으로 빠르고 쉽게 마이그레이션됩니다.</p></li></ul> | <ul><li>**데이터가 Edge Network으로 전송되지 않음**: <p>이로 인해 다음과 같은 단점이 발생합니다.</p><ul><li>모든 업그레이드 경로에서 보고의 최고 수준인 [지연](/help/technotes/guardrails.md#latencies)입니다. 실시간 개인화 사용 사례에 최적화되지 않았습니다.</li><li>데이터는 다른 Adobe Experience Platform 애플리케이션과 공유할 수 없습니다. Customer Journey Analytics 전용으로만 제한됩니다</li><li>Adobe Analytics 명명법(prop, eVar, 이벤트 등)에 의존</li></ul><li>**나중에 Web SDK로 이동하기 어려움**: Experience Platform Web SDK에서 제공하는 이점에 액세스하려고 할 수 있습니다. Experience Platform Web SDK를 사용하려면 새 구현을 수행해야 합니다.</li><li>**스키마에서 Analytics Experience Event 필드 그룹을 사용합니다**: 이 필드 그룹은 Customer Journey Analytics 스키마에 필요하지 않은 많은 Adobe Analytics 이벤트를 추가합니다.  이로 인해 Customer Journey Analytics에 필요한 것보다 더 복잡하고 복잡한 스키마가 발생할 수 있습니다.</li><li>**Adobe Analytics과 Customer Journey Analytics 모두에 대한 라이선스가 필요합니다**: Analytics 소스 커넥터를 사용하려면 Adobe Analytics과 Customer Journey Analytics 모두에 대한 비용을 지불해야 합니다.</li></ul> |

{style="table-layout:auto"}

