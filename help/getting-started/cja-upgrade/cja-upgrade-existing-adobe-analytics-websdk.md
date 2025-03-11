---
title: 데이터를 Platform으로 보내도록 기존 Adobe Analytics Web SDK 구현을 구성합니다
description: 기존 Adobe Analytics 웹 SDK 구현 구성에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1459a512-bfa8-4805-97e8-5b6acc6e4ac9
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 1%

---

# 데이터를 Platform으로 보내도록 기존 Adobe Analytics Web SDK 구현을 구성합니다 {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="데이터 스트림에서 Adobe Analytics를 서비스로 제거"
>abstract="웹 SDK 데이터가 완전히 작동하면 플랫폼 관리자와 함께 데이터 스트림에서 Adobe Analytics as a service를 제거합니다. 이를 수행하기 전에 사용자가 Adobe Analytics을 사용에서 Customer Journey Analytics으로 전환했는지 확인하십시오."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics 구현에서 이미 Adobe Experience Platform Web SDK을 사용하고 있는 경우 데이터 스트림을 설정하여 데이터를 플랫폼으로 전송할 수 있습니다. 또는 이미 데이터를 Platform으로 전송하는 경우 Platform 데이터 세트와 Customer Journey Analytics 간에 연결을 만들면 됩니다.


## 장단점

기존 Adobe Analytics Web SDK 구현을 구성하여 Platform에 데이터를 전송할 때의 다음과 같은 장단점을 고려하십시오.

| 장점 | 단점 |
|----------|---------|
| Adobe Analytics 구현에서 이미 웹 SDK을 사용하고 있는 경우 기본 업그레이드 경로입니다.<ul><li>**Experience Edge Network에서 데이터를 호스팅할 수 있는 모든 이점 제공**: <p>다음과 같은 이점이 있습니다.</p><ul><li>Adobe Experience Platform은 [실시간 개인화 사용 사례](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)를 지원하기 위해 구축되었기 때문에 성능 높은 보고 및 데이터 가용성</li><li>다른 Experience Cloud 제품(AJO, RTCDP 등) 간에 Adobe Experience Cloud 데이터 수집을 위한 구현 통합</li><li>Adobe Analytics 명명법(prop, eVar, 이벤트 등)에 의존하지 않음</li></ul><li>**기존 구현을 사용**: 이 방법을 사용하려면 일부 구현을 변경해야 하지만 처음부터 완전히 새로운 구현이 필요하지 않습니다. 기존 Adobe Analytics 보고에 영향을 주지 않고 구현 논리를 최소한으로 변경하여 기존 데이터 레이어 및 코드를 사용할 수 있습니다.</li><li>**XDM 스키마를 사용하는 옵션을 제공합니다**: 기존 Adobe Analytics 스키마를 사용하거나 XDM 스키마를 만들고 데이터 개체의 필드를 XDM 스키마에 매핑하도록 선택할 수 있습니다. [XDM 스키마](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas)은(는) 필요한 모든 필드를 정의하는 유연한 스키마이며 관련된 필드만 정의합니다. <p>고유한 XDM 스키마를 사용할 때의 장점에 대한 자세한 내용은 아래의 &quot;고유한 XDM 스키마 사용&quot;을 참조하십시오.</p></li><li>**규칙과 데이터 요소를 유지합니다**: 새로운 규칙 작업이 필요하지만 최소한의 변경 사항으로 기존 데이터 요소와 규칙 조건을 다시 사용할 수 있습니다.</li><li>**미래 대비**: 자체 XDM 스키마를 사용하도록 선택하면 향후 구현 업데이트가 더 쉬워집니다.</li></ul> | <ul><li>**데이터를 플랫폼에 보내려면 매핑이 필요합니다**: 조직에서 Customer Journey Analytics을 사용할 준비가 되면 Adobe Experience Platform의 데이터 세트로 데이터를 보내야 합니다. 이 작업을 수행하려면 데이터 개체의 모든 필드가 XDM 스키마 필드에 할당하는 데이터 스트림 매핑 도구의 항목이어야 합니다. 매핑은 이 워크플로우에 대해 한 번만 수행하면 되며 구현 변경을 수반하지 않습니다. 그러나 XDM 개체에서 데이터를 전송할 때는 필요하지 않은 추가 단계입니다.</li><li>**시간이 지남에 따라 복잡성이 증가합니다**: 나중에 추가하는 모든 필드는 데이터 스트림의 XDM에 매핑되어야 합니다.<p>새 필드가 구현에 추가될 때마다 다음 중 하나를 수행할 수 있습니다.</p><ul><li>**옵션 1:** 데이터 개체에서 임의의 새 evar 또는 새 prop을 채운 다음 원하는 XDM 필드에 매핑합니다.<p>이 프로세스는 클라이언트측 구현에 대한 일관성을 유도하지만 매핑이 필요합니다.</p></li><li>**옵션 2:** 데이터 개체를 레거시 구현으로 두고 모든 새 필드에 대해 XDM 개체만 채우기를 시작합니다.<p>이 프로세스에서는 매핑이 필요하지 않지만, 일부 변수는 데이터 개체에만 있고, 다른 변수는 XDM 개체에만 있습니다. 구현 문제를 해결해야 할 때는 언제든지 두 위치로 이동해야 합니다. 내부 워크플로우가 이에 적합한지 확인하십시오.</p></li></ul> |

{style="table-layout:auto"}

## 구현 단계

1. Edge Network에서 플랫폼으로 데이터 전송을 시작합니다. 데이터 개체를 통해 모든 변수를 AppMeasurement 형식으로 보냅니다.

   자세한 내용은 [Adobe Analytics에 대한 데이터 개체 변수 매핑](https://experienceleague.adobe.com/ko/docs/analytics/implementation/aep-edge/data-var-mapping)을 참조하십시오.

1. 스키마를 선택합니다.

   기존 Adobe Analytics 스키마를 사용할지 또는 XDM 스키마를 만들어 다른 Platform 서비스를 사용하기 시작할 때 조직의 요구 사항에 보다 잘 부합하도록 할 수 있습니다.

   Adobe에서는 XDM 스키마를 생성할 것을 권장합니다. 자세한 내용은 [Customer Journey Analytics Web SDK 구현에 사용할 사용자 지정 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)를 참조하십시오.

   +++Adobe Analytics 스키마 사용

   | 장점 | 단점 |
   |----------|---------|
   | <p>Adobe Analytics 스키마를 사용할 때의 장점은 다음과 같습니다.</p><ul><li>간편한 업그레이드<p>이미 Adobe Experience Platform Web SDK을 사용하여 Adobe Analytics으로 데이터를 전송하는 경우 데이터스트림에 서비스를 추가하여 데이터를 Adobe Experience Platform으로 전송할 수 있습니다(그런 다음 Customer Journey Analytics 구성에서 사용할 수 있음).</p></li></ul> | <p>Adobe Analytics 스키마를 사용할 때의 단점은 다음과 같습니다.</p><ul><li>Adobe Analytics 스키마를 사용해도 다른 Platform 애플리케이션과 함께 사용할 수 있는 방법에는 제한이 없지만 보다 복잡한 스키마가 생성됩니다. 이는 Adobe Analytics 스키마에 조직에서 사용할 가능성이 낮은 Adobe Analytics과 관련된 많은 개체가 포함되어 있기 때문입니다.<p>스키마를 변경해야 하는 경우, 업데이트가 필요한 필드를 찾으려면 사용되지 않은 수천 개의 필드를 살펴봐야 합니다.</p></li></ul> |

+++

   +++XDM 스키마 만들기

   | 장점 | 단점 |
   |----------|---------|
   | <ul><p>고유한 XDM 스키마로 업데이트하는 장점에는 다음이 포함됩니다.</p><ul><li>조직의 요구 사항과 사용하는 특정 Platform 애플리케이션에 맞게 조정된 간소화된 스키마.</li><p>스키마를 변경해야 하는 경우, 업데이트가 필요한 필드를 찾기 위해 사용하지 않는 수천 개의 필드를 검색하지 않아도 됩니다.</p></ul> | <p>자체 XDM 스키마로 업데이트할 때의 단점은 다음과 같습니다.</p><ul><li>스키마를 업데이트하는 것은 플랫폼으로 데이터를 보내기 전에 필요한 시간이 오래 걸리는 프로세스입니다.</li></ul> |

+++

1. 데이터 스트림 매핑을 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다.

   자세한 내용은 Experience Platform 설명서의 [데이터 수집을 위한 데이터 준비](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)에서 [매핑](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping)을 참조하십시오.

{{upgrade-final-step}}
