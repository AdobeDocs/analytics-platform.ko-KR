---
title: Customer Journey Analytics으로 업그레이드할 때의 대체 방법
description: Customer Journey Analytics으로 업그레이드할 때의 대체 방법에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 2b66e2db9b22bab5304fe981e58828d4ae9fabbd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 0%

---

# 업그레이드 대체 요소: Experience Platform Web SDK 및 Customer Journey Analytics과 함께 AppMeasurement 데이터 수집 사용 {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="웹 SDK에서 AppMeasurement 논리 사용"
>abstract="XDM 개체를 통해 데이터를 보내는 대신 데이터 개체를 통해 모든 변수를 AppMeasurement 형식으로 보냅니다.<br><br>이 옵션을 사용하면 처음부터 XDM 개체를 채우지 않고 AppMeasurement 논리를 XDM에 매핑할 수 있으므로 구현 시간이 절약됩니다. 하지만 나중에 추가하는 필드는 데이터 스트림의 XDM에 매핑해야 하므로 시간이 지남에 따라 복잡성이 증가합니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analytics 업그레이드 확인 목록](https://gigazelle.github.io/cja-ttv/)의 질문에 답변할 때 이 페이지의 정보를 사용하십시오.

Customer Journey Analytics으로 업그레이드할 때 Adobe [Experience Platform Web SDK의 새 구현을 권장](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)합니다. 그러나 타임라인 및 리소스 제한과 같은 여러 요인에 따라 권장되는 업그레이드 단계가 조직에 실용적이지 않을 수 있습니다.

XDM 개체를 사용하여 데이터를 수집하는 대신 웹 SDK에서 AppMeasurement 또는 Analytics 확장 데이터 수집 로직을 사용하여 Platform 및 Customer Journey Analytics으로 데이터를 전송할 수 있습니다. 그러나 이 대안은 시간이 지남에 따라 추가적인 복잡성을 도입합니다.

## 장단점

이 메서드는 [전체 데이터 레이어를 Customer Journey Analytics으로 보내기](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)와 함께 사용할 수 없습니다. 두 메서드가 동일한 작업을 수행하기 때문입니다. (이 방법은 전체 데이터 레이어를 Adobe으로 보내는 것이 좋습니다. prop과 evar가 모두 데이터를 거치기 때문에 더욱 세련되었다.__adobe.analytics._variable-name_.)

이 업그레이드 대체 요소를 사용할 때 다음과 같은 장점과 단점을 고려하십시오.

| 장점 | 단점 |
|----------|---------|
| <ul><li>**Experience Edge Network에서 데이터를 호스팅할 수 있는 모든 이점 제공**: <p>다음과 같은 이점이 있습니다.</p><ul><li>Adobe Experience Platform은 [실시간 개인화 사용 사례](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)를 지원하기 위해 구축되었기 때문에 성능 높은 보고 및 데이터 가용성</li><li>다른 Experience Cloud 제품(AJO, RTCDP 등) 간에 Adobe Experience Cloud 데이터 수집을 위한 구현 통합</li><li>Adobe Analytics 명명법(prop, eVar, event 등)에만 국한되지 않음</li></ul><li>**기존 구현을 사용**: 이 방법을 사용하려면 일부 구현을 변경해야 하지만 처음부터 완전히 새로운 구현이 필요하지 않습니다. 이를 통해 처음부터 XDM 오브젝트를 채우는 대신 AppMeasurement 논리를 XDM에 매핑할 수 있습니다.</li></ul> | <ul><li>**데이터를 플랫폼에 보내려면 매핑이 필요합니다**: 조직에서 Customer Journey Analytics을 사용할 준비가 되면 Adobe Experience Platform의 데이터 세트로 데이터를 보내야 합니다. 이 작업을 수행하려면 데이터 개체의 모든 필드가 XDM 스키마 필드에 할당하는 데이터 스트림 매핑 도구의 항목이어야 합니다. 매핑은 이 워크플로우에 대해 한 번만 수행하면 되며 구현 변경을 수반하지 않습니다. 그러나 XDM 개체에서 데이터를 전송할 때는 필요하지 않은 추가 단계입니다.</li><li>**시간이 지남에 따라 복잡성이 증가합니다**: 나중에 추가하는 모든 필드는 데이터 스트림의 XDM에 매핑되어야 합니다.<p>새 필드가 구현에 추가될 때마다 다음 중 하나를 수행할 수 있습니다.</p><ul><li>**옵션 1:** 데이터 개체에서 임의의 새 evar 또는 새 prop을 채운 다음 원하는 XDM 필드에 매핑합니다.<p>이 프로세스는 클라이언트측 구현에 대한 일관성을 유도하지만 매핑이 필요합니다.</p></li><li>**옵션 2:** 데이터 개체를 레거시 구현으로 두고 모든 새 필드에 대해 XDM 개체만 채우기를 시작합니다.<p>이 프로세스에서는 매핑이 필요하지 않지만, 일부 변수는 데이터 개체에만 있고, 다른 변수는 XDM 개체에만 있습니다. 구현 문제를 해결해야 할 때는 언제든지 두 위치로 이동해야 합니다. 내부 워크플로우가 이에 적합한지 확인하십시오.</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## 기본 단계

Adobe Analytics 구현(AppMeasurement 또는 Analytics 확장)을 마이그레이션하여 웹 SDK을 사용하여 Customer Journey Analytics으로 데이터를 전송하는 기본 단계는 다음과 같습니다.

1. (선택 사항) Adobe Analytics 구현을 마이그레이션하여 Adobe Experience Platform Web SDK을 사용하고 Edge Network으로 데이터 전송을 시작합니다.

   기존 Adobe Analytics 구현을 마이그레이션하여 웹 SDK을 사용하고 모든 것이 Adobe Analytics에서 작동하는지 확인할 수 있는 선택적 단계입니다. 이를 구성하고 Adobe Analytics의 데이터가 만족스러우면 Edge Network에서 Customer Journey Analytics으로 데이터를 보낼 수 있습니다.

   이러한 유연성으로 인해 Customer Journey Analytics으로 보다 계획적이고 신중하게 업그레이드할 수 있습니다.

   이 작업을 수행하는 방법에 대한 자세한 내용은 Adobe Analytics 설명서에서 다음 문서를 참조하십시오.

   * [태그를 사용하여 웹 SDK으로 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [JavaScript을 사용하여 웹 SDK으로 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Edge Network에서 Customer Journey Analytics으로 데이터를 전송합니다.

   1. 데이터 개체를 통해 모든 변수를 AppMeasurement 형식으로 보냅니다.

      자세한 내용은 [Adobe Analytics에 대한 데이터 개체 변수 매핑](https://experienceleague.adobe.com/ko/docs/analytics/implementation/aep-edge/data-var-mapping)을 참조하십시오.

   1. 아직 만들지 않은 경우 조직에 대한 XDM 스키마를 만듭니다.

      자세한 내용은 [Customer Journey Analytics Web SDK 구현에 사용할 사용자 지정 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)를 참조하십시오.

   1. 데이터 스트림 매핑을 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다.

      자세한 내용은 Experience Platform 설명서의 [데이터 수집을 위한 데이터 준비](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)에서 [매핑](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping)을 참조하십시오.

