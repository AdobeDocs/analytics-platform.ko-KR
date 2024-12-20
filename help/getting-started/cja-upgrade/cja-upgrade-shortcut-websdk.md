---
title: 업그레이드 바로 가기 AppMeasurement 또는 Analytics 확장 구현을 마이그레이션하여 웹 SDK 사용
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 83927cf0-b3b4-42b4-9ca5-0c81c091383f
source-git-commit: daa07b603caa613ca49b61c2e8e461d558459f57
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 9%

---

# 업그레이드 단축키: Web SDK를 사용하도록 AppMeasurement 또는 Analytics 확장 구현 마이그레이션 {#shortcut-migrate-websdk}

>[!NOTE]
>
>Adobe Analytics 이 설명서는 [업그레이드 Customer Journey Analytics 설문지](https://gigazelle.github.io/cja-ttv/)의 일부로 사용해야 합니다.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="Web SDK를 사용하도록 Analytics 구현 마이그레이션"
>abstract="XDM 오브젝트를 통해 데이터를 전송하는 대신 데이터 오브젝트를 통해 모든 변수를 AppMeasurement 형식으로 전송할 수 있습니다. 이 단축키를 사용하면 AppMeasurement 논리를 계속 사용하여 플랫폼으로 데이터를 전송할 수 있습니다."

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics으로 업그레이드할 때 [ Adobe은 Experience Platform 웹 SDK의 새 구현을 권장합니다](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). 그러나 타임라인 및 리소스 제한과 같은 여러 요인에 따라 권장되는 업그레이드 단계가 조직에 실용적이지 않을 수 있습니다.

Adobe Analytics 구현이 AppMeasurement 또는 Analytics 확장 기능인 경우 업그레이드 단축키를 사용할 수 있습니다. 이 단축키를 사용하면 Adobe Experience Platform 구현을 마이그레이션하여 Adobe Analytics Web SDK을 사용하여 데이터를 Customer Journey Analytics으로 보내기 전에 Edge Network 및 Adobe Analytics으로 전송하기 시작할 수 있습니다.

## 장단점

업그레이드 단축키의 다음과 같은 장점과 단점을 고려하여 AppMeasurement 또는 Analytics 확장 구현을 마이그레이션하여 웹 SDK을 사용하십시오.

| 장점 | 단점 |
|----------|---------|
| <ul><li>**Experience Edge Network에서 데이터를 호스팅할 수 있는 모든 이점 제공**: <p>다음과 같은 이점이 있습니다.</p><ul><li>Adobe Experience Platform은 [실시간 개인화 사용 사례](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)를 지원하기 위해 구축되었기 때문에 성능 높은 보고 및 데이터 가용성</li><li>다른 Experience Cloud 제품(AJO, RTCDP 등) 간에 Adobe Experience Cloud 데이터 수집을 위한 구현 통합</li><li>Adobe Analytics 명명법(prop, eVar, 이벤트 등)에 의존하지 않음</li></ul><li>**기존 구현을 사용**: 이 방법을 사용하려면 일부 구현을 변경해야 하지만 처음부터 완전히 새로운 구현이 필요하지 않습니다. 기존 Adobe Analytics 보고에 영향을 주지 않고 구현 논리를 최소한으로 변경하여 기존 데이터 레이어 및 코드를 사용할 수 있습니다.</li><li>**나중에 조직에 대한 XDM 스키마를 만들 수 있는 유연성을 제공합니다**: 기존 Adobe Analytics 구현을 마이그레이션하여 Web SDK을 사용하고 모든 것이 Adobe Analytics에서 작동하는지 확인한 다음 XDM 스키마를 만들 수 있습니다. 이러한 유연성으로 인해 Customer Journey Analytics으로 보다 체계적이고 신중하게 업그레이드할 수 있습니다.</li></ul> | <ul><li>**데이터를 플랫폼에 보내려면 매핑이 필요합니다**: 조직에서 Customer Journey Analytics을 사용할 준비가 되면 Adobe Experience Platform의 데이터 세트로 데이터를 보내야 합니다. 이 작업을 수행하려면 데이터 개체의 모든 필드가 XDM 스키마 필드에 할당하는 데이터 스트림 매핑 도구의 항목이어야 합니다. 매핑은 이 워크플로우에 대해 한 번만 수행하면 되며 구현 변경을 수반하지 않습니다. 그러나 XDM 개체에서 데이터를 전송할 때는 필요하지 않은 추가 단계입니다.</li><li>**기술적 부담**: 이 방법은 기존 구현의 수정된 형식을 사용하므로 구현 논리를 추적하고 필요한 경우 나중에 변경을 수행하는 것이 더 어려울 수 있습니다. </li></ul> |

{style="table-layout:auto"}

## 기본 단계

업그레이드 바로 가기를 사용하여 AppMeasurement 또는 Analytics 확장 구현을 마이그레이션하여 웹 SDK을 사용하기로 결정한 경우 [Adobe Analytics에서 조직에 대해 동적으로 생성된 단계에 새 단계를 추가하여 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)합니다.

웹 SDK을 사용하도록 AppMeasurement 또는 Analytics 확장 구현을 마이그레이션하는 기본 단계는 다음과 같습니다.

1. Platform으로 데이터 전송을 시작합니다.

   Adobe Analytics 구현으로 이미 데이터를 Platform에 전송하는 경우 이 단계는 필요하지 않습니다. 이 프로세스의 뒷부분에서 설명한 대로 플랫폼 데이터 세트와 Customer Journey Analytics 간에 연결을 만들면 됩니다.

1. (선택 사항) 시간이 있을 때 조직에 대한 XDM 스키마를 만듭니다.

1. (조건부) XDM 스키마를 생성한 경우, 데이터스트림 매핑을 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다.
