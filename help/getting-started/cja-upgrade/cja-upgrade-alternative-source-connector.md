---
title: Analytics 소스 커넥터만 사용하여 Customer Journey Analytics로 업그레이드
description: Analytics 소스 커넥터 및 맵 필드를 만드는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 94%

---

# 업그레이드 대안: Analytics 소스 커넥터만 사용하여 Customer Journey Analytics로 업그레이드 {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Analytics 소스 커넥터만 사용"
>abstract="(권장하지 않음) Analytics 소스 커넥터를 Customer Journey Analytics의 유일한 구현 경로로 사용할 수 있습니다. <br><br>이 옵션을 사용하면 Customer Journey Analytics에 데이터를 빠르게 전송하여 구현 시간을 절약할 수 있습니다. 그러나 이 솔루션은 지연 시간이 길고 향후 Adobe Analytics에서 이동하기 어려운 등 다양한 단점을 가지고 있습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

권장하지는 않지만 Analytics 소스 커넥터를 Customer Journey Analytics의 유일한 구현 경로로 사용할 수 있습니다. 그러나 이러한 유형의 업그레이드와 관련 내재된 단점으로 인해 새로운 Experience Platform Web SDK 구현과 함께 Analytics 소스 커넥터를 사용하는 것이 좋습니다. 권장되는 업그레이드 경로에 대한 자세한 내용은 [Adobe Analytics에서 Customer Journey Analytics로 업그레이드할 때 권장되는 경로](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)를 참조하십시오.

## 장점과 단점

아래 표의 정보를 사용하여 Customer Journey Analytics으로 업그레이드할 때만 소스 커넥터를 사용할 때의 장점과 단점을 이해하십시오.

| 장점 | 단점 |
|----------|---------|
| <ul><li>가장 시간이 적게 걸리며 까다로운 업그레이드 경로. <p>데이터는 Customer Journey Analytics으로 빠르고 쉽게 마이그레이션됩니다.</p></li></ul> | <ul><li>**데이터가 Edge Network로 전송되지 않습니다**. <p>이로 인해 다음과 같은 단점이 발생합니다.</p><ul><li>모든 업그레이드 경로에 대한 보고에서 가장 높은 수준의 [지연](/help/technotes/guardrails.md#latencies) 발생, 실시간 개인화 사용 사례에 최적화되지 않음.</li><li>데이터는 다른 Adobe Experience Platform 애플리케이션과 공유할 수 없으며 Customer Journey Analytics에만 국한됨</li><li>Adobe Analytics 명명법(Prop, eVar, 이벤트 등)에 의존</li></ul><li>**향후 Web SDK로의 전환이 어려움**: 결국에는 Experience Platform Web SDK가 제공하는 이점을 활용하고 싶을 것입니다. Experience Platform Web SDK를 사용하려면 새로 구현해야 합니다.</li><li>**스키마에서 Analytics 경험 이벤트 필드 그룹 사용**: 이 필드 그룹은 Customer Journey Analytics 스키마에 필요하지 않은 여러 Adobe Analytics 이벤트를 추가합니다. 이로 인해 Customer Journey Analytics에 필요한 것보다 더 복잡하고 혼란스러운 스키마가 생길 수 있습니다.</li><li>**Adobe Analytics와 Customer Journey Analytics에 대한 라이선스 모두 필요**: Analytics 소스 커넥터를 사용하려면 Adobe Analytics와 Customer Journey Analytics에 대한 비용을 모두 지불해야 합니다.</li></ul> |

{style="table-layout:auto"}

## 기본 단계

Customer Journey Analytics의 유일한 구현 경로로 Analytics 소스 커넥터를 사용하기로 결정한 경우 [소스 커넥터를 사용하여 데이터 수집 및 사용](/help/data-ingestion/sources.md)에 설명된 구현 단계를 따릅니다.

