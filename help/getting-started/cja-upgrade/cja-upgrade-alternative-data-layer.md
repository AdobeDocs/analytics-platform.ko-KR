---
title: Customer Journey Analytics으로 업그레이드할 때의 대체 방법
description: Customer Journey Analytics으로 업그레이드할 때의 대체 방법에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 34%

---

# 업그레이드 대안: 데이터 레이어를 Customer Journey Analytics로 전송 {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="Adobe로 데이터 레이어 전송"
>abstract="XDM 오브젝트를 통해 데이터를 전송하는 대신 데이터 오브젝트를 통해 전체 데이터 레이어를 Adobe로 전송할 수 있습니다.<br><br>이 옵션을 사용하면 XDM 오브젝트를 처음부터 직접 채우는 대신 데이터 레이어를 XDM에 매핑할 수 있으므로 구현 시간이 절약됩니다. 그러나 Adobe가 즉시 해석할 수 없는 상당한 양의 데이터가 전송되므로, 이러한 매핑에는 많은 작업이 필요합니다. 또한 이 옵션을 선택하면 나중에 데이터에 추가하는 모든 필드를 데이터스트림의 XDM에 매핑해야 하므로 시간이 지남에 따라 복잡성이 증가합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="Adobe로 데이터 레이어 전송"
>abstract="원하는 시점에 Adobe로 데이터를 전송하도록 구현을 구성하고 JSON 페이로드를 전체 데이터 레이어로 구성합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="XDM에 각 데이터 레이어 요소 할당"
>abstract="모든 데이터 레이어 요소를 원하는 XDM 필드에 매핑합니다. XDM 필드에 매핑되지 않은 데이터 레이어 요소는 Adobe가 해당 데이터를 저장할 위치나 방법을 알 수 없으므로 영구적으로 삭제됩니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Customer Journey Analytics으로 업그레이드할 때 Adobe [Experience Platform Web SDK의 새 구현을 권장](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)합니다. 그러나 타임라인 및 리소스 제한과 같은 여러 요인에 따라 권장되는 업그레이드 단계가 조직에 실용적이지 않을 수 있습니다.

XDM 개체를 사용하여 데이터를 수집하는 대신 전체 데이터 레이어를 Customer Journey Analytics으로 보낼 수 있습니다. 그러나 이 대안은 시간이 지남에 따라 추가적인 복잡성을 도입합니다.

## 장단점

이 메서드는 [Customer Journey Analytics에서 AppMeasurement 데이터 수집 논리를 사용](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)하는 것과 함께 사용할 수 없습니다. 두 메서드가 동일한 작업을 수행하기 때문입니다.

이 업그레이드 대체 요소를 사용할 때의 장점과 단점은 다음과 같습니다.

| 장점 | 단점 |
|----------|---------|
| <ul><li>**Experience Edge Network에서 데이터를 호스팅할 수 있는 모든 이점 제공**: <p>다음과 같은 이점이 있습니다.</p><ul><li>Adobe Experience Platform은 [실시간 개인화 사용 사례](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)를 지원하기 위해 구축되었기 때문에 성능 높은 보고 및 데이터 가용성</li><li>다른 Experience Cloud 제품(AJO, RTCDP 등) 간에 Adobe Experience Cloud 데이터 수집을 위한 구현 통합</li><li>Adobe Analytics 명명법(prop, eVar, 이벤트 등)에 의존하지 않음</li></ul><li>**현재 데이터 계층 논리를 사용합니다**: 이 메서드는 일반적인 웹 SDK 구현 대신 현재 데이터 계층 논리를 사용합니다. 이 접근 방식에서는 일부 구성이 필요하지만 처음부터 완전히 새로운 구현이 필요하지 않으며 데이터 요소나 태그 규칙을 채울 필요가 없습니다. 이를 통해 처음부터 XDM 개체를 채우는 대신 데이터 레이어의 데이터를 XDM에 매핑할 수 있습니다.</li></ul> | <ul><li>**데이터를 플랫폼에 보내려면 매핑이 필요합니다**: 조직에서 Customer Journey Analytics을 사용할 준비가 되면 Adobe Experience Platform의 데이터 세트로 데이터를 보내야 합니다. <p>이 옵션을 사용하면 전체 클라이언트측 데이터 레이어를 데이터 개체에 넣고 Adobe으로 보낼 수 있으므로 Adobe에서 쉽게 해석할 수 없는 상당한 양의 데이터가 생성됩니다. Adobe에서 데이터를 해석할 수 있도록 하려면 데이터스트림 매핑을 사용하여 모든 개별 필드를 원하는 XDM 필드에 매핑해야 합니다.</p></li><li>**엄격한 구현**: 구현은 히트가 전송될 때 데이터 계층이 제공하는 것으로 제한됩니다. 기본 데이터 요구 사항이 있는 조직에서도 이 기능을 사용할 수 있지만, 대부분의 조직에서는 데이터 요소를 채울 수 있는 보다 유연한 구현을 위해 이러한 유형의 엄격한 구현을 피해야 합니다.</li><li>**향후 변경 내용은 구현하기 더 어렵습니다**: 나중에 데이터에 추가하는 필드는 데이터 스트림의 XDM에 매핑해야 합니다.</li></ul> |

{style="table-layout:auto"}

## 기본 단계

전체 데이터 레이어를 Customer Journey Analytics으로 전송하는 기본 단계는 다음과 같습니다.

1. 원하는 시점에 Adobe로 데이터를 전송하도록 구현을 구성하고 JSON 페이로드를 전체 데이터 레이어로 구성합니다.

1. 모든 데이터 레이어 요소를 원하는 XDM 필드에 매핑합니다.

   XDM 필드에 매핑되지 않은 데이터 레이어 요소는 Adobe가 해당 데이터를 저장할 위치나 방법을 알 수 없으므로 영구적으로 삭제됩니다.
