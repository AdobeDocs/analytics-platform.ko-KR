---
title: Customer Journey Analytics 마이그레이션 방법 선택
description: Customer Journey Analytics으로 마이그레이션할 때 발생할 수 있는 마이그레이션 방법의 장점과 단점에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '1930'
ht-degree: 3%

---

# 2단계: Customer Journey Analytics 마이그레이션 방법 선택

+++이 페이지의 정보는 대규모 마이그레이션 프로세스의 일부입니다. 이 섹션을 확장하여 마이그레이션 프로세스에서 이 정보가 어디에 적합한지 확인하십시오. </br></br>이 페이지의 정보를 계속 진행하기 전에 이전의 모든 마이그레이션 단계를 완료해야 합니다.

이 섹션을 계속하기 전에 먼저 이전 마이그레이션 작업을 모두 완료했는지 확인하십시오.

이 페이지의 정보에는 아래 표에 강조 표시된 대로 2단계가 포함됩니다.

| 마이그레이션 작업 | 세부 사항 |
|---------|----------|
| **1단계: [마이그레이션 시작](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analytics으로 마이그레이션하는 것의 이점 및 기본 마이그레이션 프로세스에 대해 알아봅니다. |
| <span class="preview">**2단계: [마이그레이션 방법 선택](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">Customer Journey Analytics으로 마이그레이션하는 데 다양한 방법을 사용할 수 있습니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 조직에 가장 적합한 방법을 선택합니다.</span> |
| **3단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 보내는 프로세스는 1단계에서 선택한 마이그레이션 방법에 따라 다릅니다. |
| **4단계: [XDM 스키마에 데이터 매핑 계획](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM 스키마](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 는 Adobe Experience Platform에서 데이터의 구조를 일관되고 재사용 가능한 방식으로 설명하는 데 사용됩니다. 여러 시스템에서 데이터를 일관되게 정의하면 의미를 쉽게 유지할 수 있으므로 데이터의 가치를 얻을 수 있습니다.<p>대부분의 마이그레이션 방법을 사용하려면 새 XDM 스키마를 만들거나 데이터 스트림 매핑을 사용하여 기존 Adobe Analytics 스키마를 XDM에 매핑해야 합니다.</p> |
| **5단계: [이전 데이터 유지](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다. |
| **6단계: [플랜 사용자 온보딩](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 사용자에게 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점에 익숙해질 수 있는 충분한 시간(3~6개월)을 제공해야 합니다. |
| **7단계: [보고 API 사용 포트](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics 보고 API의 형식은 동일하지만 다른 끝점을 사용합니다. Adobe Analytics 보고 API의 보고 API 사용을 Customer Journey Analytics 보고 API로 포팅합니다. |
| **8단계: [데이터 피드 및 Data Warehouse 바꾸기](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analytics에서 사용 중이던 데이터 피드 및 Data Warehouse 기능을 대체하기 위해 Customer Journey Analytics에서 사용할 수 있는 내보내기 옵션을 사용하는 방법을 결정합니다. |
| **9단계: [프로젝트 및 구성 요소 마이그레이션](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics의 구성 요소 마이그레이션 영역에서 프로젝트 및 관련 구성 요소를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션할 수 있습니다. |

{style="table-layout:auto"}

+++

Customer Journey Analytics으로 마이그레이션하기로 결정한 후 조직에 대한 최적의 마이그레이션 방법을 결정해야 합니다.

Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션하기 위해 선택하는 방법은 다음 요인에 따라 다릅니다.

* 기존 Adobe Analytics 구현

* 미래를 위한 여러분의 목표

다음 섹션을 사용하여 조직의 현재 구현 및 향후 목표에 가장 적합한 Customer Journey Analytics 마이그레이션 방법을 결정합니다.

## 마이그레이션 방법 이해

Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션하기 위한 다양한 마이그레이션 방법이 있습니다.

일반적으로 각 마이그레이션 방법은 마이그레이션을 실행하는 데 필요한 노력 수준과 마이그레이션이 완료된 후 달성되는 장기 생존력에서 차이가 있습니다.

다음 표에는 각 마이그레이션 방법, 작업 수준 및 장기 실행 가능성이 나열되어 있습니다.

| 마이그레이션 메서드 | 작업량 | 장기적 생존 가능성 |
|---------|----------|---------|
| **웹 SDK의 새로운 구현**</br>&#x200B;새로운 Adobe Experience Platform Web SDK 구현을 수행하여 Adobe Experience Platform Edge Network에 데이터를 전송할 수 있습니다 <!-- what is the correct branding -->. <p>아직 Web SDK에 없는 조직의 경우, 이 마이그레이션 방법은 데이터를 Edge Network으로 가져올 때 가장 간단할 수 있지만(단계 수가 가장 적음), XDM 스키마를 만드는 등 모든 작업이 미리 수행됩니다.</p><p>기본 단계는 다음과 같습니다.</p><ol><li>조직에 대한 XDM 스키마 만들기</li><li>웹 SDK 구현</li><li>플랫폼으로 데이터 보내기</li></ol> | 높음 | 높음 |
| **웹 SDK를 사용하도록 Adobe Analytics 구현 마이그레이션**</br> Adobe Analytics 구현이 AppMeasurement 또는 Analytics 확장 기능인 경우 Customer Journey Analytics으로 전송하기 전에 Adobe Experience Platform Web SDK를 사용하여 데이터를 Edge Network으로 전송하기 시작하도록 마이그레이션할 수 있습니다. <!-- what else? --><p>이는 데이터를 Edge Network으로 가져오는 가장 쉽고 원활한 방법입니다. 더 많은 단계가 필요하지만 보다 가시적인 이정표를 통해 보다 방법적인 전환을 제공합니다.</p><p>기본 단계는 다음과 같습니다.</p><ol><li>기존 Adobe Analytics 구현을 웹 SDK로 이동하고 모든 것이 제대로 작동하는지 확인하십시오.</li><li>시간이 지남에 따라 조직에 대한 XDM 스키마를 만듭니다.</li><li>데이터 스트림 매핑을 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다.</li><li>플랫폼으로 데이터 보내기</li></ol> | 중재 | 높음 |
| **기존 Adobe Analytics Web SDK 구현을 구성하여 데이터를 Customer Journey Analytics으로 전송**</br> Adobe Analytics 구현에서 이미 웹 SDK를 사용 중인 경우 데이터를 Customer Journey Analytics으로 전송할 수 있습니다.<p>데이터를 Customer Journey Analytics으로 보내기 전에 조직 및 사용할 다른 Platform 애플리케이션의 특정 요구 사항에 맞게 Adobe Analytics 스키마를 업데이트하는 것이 좋습니다.</p><p>기본 단계는 다음과 같습니다.</p><ol><li>Customer Journey Analytics으로 데이터 전송을 시작합니다.<!-- What's involved here? Just point it at CJA? --></li><li>(선택 사항) 시간이 있을 때 조직에 대한 XDM 스키마를 만듭니다.</li><li>데이터 스트림 매핑을 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다.</li></ol> | 낮음 | 높음 |
| **Analytics 소스 커넥터**</br> Adobe Analytics 구현이 AppMeasurement 또는 Analytics 확장 기능인 경우 Customer Journey Analytics의 데이터 보기로 데이터 전송을 시작할 수 있습니다.<p>이는 데이터를 Customer Journey Analytics에 가져오는 가장 쉬운 방법이지만 장기적으로 가장 실행 가능성이 낮은 방법입니다.</p> | 낮음 | 낮음 |

{style="table-layout:auto"}

다음 다이어그램을 사용하여 각 마이그레이션 방법이 노력 수준과 각 방법이 달성하는 장기 생존력 측면에서 스펙트럼에 미치는 위치를 시각화할 수 있습니다.

![cja 마이그레이션 메서드](assets/cja-migration-methods.png)

## 현재 Adobe Analytics 구현을 기반으로 사용 가능한 마이그레이션 방법을 평가합니다

각 유형의 Adobe Analytics 구현에 일부 마이그레이션 방법을 사용할 수 있는 것은 아닙니다.

아래 정보를 일반적인 지침으로 사용하여 조직에 가장 적합한 마이그레이션 방법을 이해하십시오.

보다 구체적인 조언, 안내 또는 지원이 필요한 경우 Adobe 담당자에게 문의하십시오.

| Adobe Analytics 구현 | 사용 가능한 마이그레이션 메서드 |
|---------|----------|
| AppMeasurement | <ul><li>웹 SDK의 새로운 구현</li><li>웹 SDK로 Adobe Analytics 마이그레이션</li><li>Analytics 소스 커넥터</li></ul> |
| Adobe Analytics 확장 | <ul><li>웹 SDK의 새로운 구현</li><li>웹 SDK로 Adobe Analytics 마이그레이션</li><li>Analytics 소스 커넥터</li></ul> |
| Web SDK | <ul><li>Adobe Analytics Web SDK 구현을 구성하여 Customer Journey Analytics에 데이터 보내기</li></ul> |

{style="table-layout:auto"}

## 사용 가능한 마이그레이션 방법의 장단점을 따져보십시오.

기존 Adobe Analytics 구현에 따라 주어진 마이그레이션 방법의 장점과 단점이 다릅니다.

아래 정보를 사용하여 자신에게 적합한 마이그레이션 방법을 결정하기 전에 다음 정보를 검토하십시오. [마이그레이션 방법 이해](#understand-migration-methods) 아직 안왔으면

### AppMeasurement 및 Adobe Analytics 확장

다음 표는 AppMeasurement 또는 Adobe Analytics 확장을 사용하여 Adobe Analytics을 구현한 조직에서 사용할 수 있는 마이그레이션 방법을 보여 줍니다.

| 마이그레이션 메서드 | 장점 | 단점 |
|---------|----------|---------|
| **웹 SDK의 새로운 구현** | <ul><li>유연한 스키마인 XDM 스키마를 사용하여 필요한 필드를 정의합니다</li><li>Adobe Analytics 명명법(Prop, eVar, 이벤트 등)에 의존하지 않음</li><li>글자 수 제한 없음 (Prop의 경우 100자)</li><li>Adobe Experience Platform은 강력한 성능을 제공하도록 구축되었으므로 뛰어난 성능 보고 및 데이터 가용성 [실시간 개인화 사용 사례](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>미래 지향적 기능(모든 최신 기능 수신)</li><li>다른 Experience Cloud 제품(AJO, RTCDP 등) 간에 Adobe Experience Cloud 데이터 수집을 위한 태그를 통합합니다.</li><li>방문자 식별 정확도 향상을 위한 [자사 디바이스 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html)</li></ul> | <ul><li>가장 많은 시간이 소요되고 까다로운 마이그레이션 방법<p>웹 SDK 구현을 시작하기 전에 XDM에서 전체 스키마를 다시 만들어야 합니다.</p></li></ul> |
| **웹 SDK로 Adobe Analytics 마이그레이션** | <ul><li>Adobe Analytics 구현에 이미 구성된 규칙 및 데이터 요소를 유지합니다.</li><li>기존 Adobe Analytics 보고에 영향을 주지 않고 웹 SDK로 이동할 수 있습니다.</li><li>조직의 XDM 스키마를 나중에 생성할 수 있는 유연성을 제공합니다.</br>Customer Journey Analytics에는 Adobe Analytics 경험 이벤트 필드 그룹이 필요하지 않습니다. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Adobe Analytics 명명법(Prop, eVar, 이벤트 등)에 의존하지 않음</li><li>글자 수 제한 없음 (Prop의 경우 100자)</li><li>Adobe Experience Platform은 강력한 성능을 제공하도록 구축되었으므로 뛰어난 성능 보고 및 데이터 가용성 [실시간 개인화 사용 사례](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>미래 지향적 기능(모든 최신 기능 수신)</li><li>다른 Experience Cloud 제품(AJO, RTCDP 등) 간에 Adobe Experience Cloud 데이터 수집을 위한 태그를 통합합니다.</li><li>방문자 식별 정확도 향상을 위한 [자사 디바이스 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html)</li></ul> | <ul><li>데이터 스트림 매핑을 사용하여 나중에 XDM 스키마를 준수해야 합니다.</li><li>기술적 부채가 발생해요. 예를 들어 이전 AppMeasurement 또는 Analytics 확장 코드가 남아 있을 수 있습니다. </li></ul> |
| **Analytics 소스 커넥터** | <ul><li>시간이 가장 많이 소요되고 까다로운 마이그레이션 방법 <p>최소한의 투자로 신속하게 Customer Journey Analytics으로 데이터 마이그레이션</p></li></ul> | <ul><li>데이터는 Edge Network으로 전송되지 않으며 다른 Adobe Experience Platform 애플리케이션과 공유할 수 없습니다. Customer Journey Analytics 전용으로만 제한됩니다<li>향후 웹 SDK로 이동하기 어려움</li><li>스키마에서 Analytics 경험 이벤트 필드 그룹을 사용합니다.</br>이 필드 그룹은 Customer Journey Analytics 스키마에 필요하지 않은 많은 Adobe Analytics 이벤트를 추가합니다.  이로 인해 Customer Journey Analytics에 필요한 것보다 더 복잡하고 복잡한 스키마가 발생할 수 있습니다.</li><li>최고 수준 [지연](/help/admin/guardrails.md#latencies) 모든 구현 방법 간</li></ul> |

{style="table-layout:auto"}

### Web SDK

다음 표는 웹 SDK를 사용하여 Adobe Analytics을 구현한 조직에서 사용할 수 있는 마이그레이션 방법을 보여 줍니다.

| 마이그레이션 메서드 | 장점 | 단점 |
|---------|----------|---------|
| **Adobe Analytics Web SDK 구현을 구성하여 Customer Journey Analytics에 데이터 보내기** | Adobe Analytics 구현에서 이미 웹 SDK를 사용하고 있는 경우 기본 마이그레이션 방법입니다. <p>이 구현 방법을 사용하는 경우 기존 Adobe Analytics 스키마를 사용할지 여부를 선택할 수 있습니다. 또는 다른 Platform 애플리케이션을 사용하기 시작할 때 조직의 요구 사항에 보다 잘 부합하도록 XDM 스키마로 업데이트할 수 있습니다.</p><p>**Adobe Analytics 스키마 사용**</p><p>Adobe Analytics 스키마를 사용할 때의 장점은 다음과 같습니다.</p><ul><li>간편한 마이그레이션<p>Adobe Experience Platform Web SDK를 사용하여 이미 Adobe Analytics으로 데이터를 전송 중인 경우 데이터 스트림에 서비스를 추가하여 데이터를 Adobe Experience Platform으로 전송할 수 있습니다(그런 다음 Customer Journey Analytics 구성에서 사용할 수 있음).</p></li></ul><p>Adobe Analytics 스키마를 사용할 때의 단점은 다음과 같습니다.</p><ul><li>Adobe Analytics 스키마를 사용해도 다른 Platform 애플리케이션과 함께 사용할 수 있는 방법에는 제한이 없지만 보다 복잡한 스키마가 생성됩니다. 이는 Adobe Analytics 스키마에 조직에서 사용하지 않을 수 있는 Adobe Analytics과 관련된 많은 개체가 포함되어 있기 때문입니다.<p>스키마를 변경해야 하는 경우, 업데이트가 필요한 필드를 찾으려면 사용되지 않은 수천 개의 필드를 살펴봐야 합니다.</p></li></ul><p>**XDM 스키마 사용**</p><p>XDM 스키마 업데이트의 이점은 다음과 같습니다.</p><ul><li>조직의 요구 사항과 사용하는 특정 Platform 애플리케이션에 맞게 조정된 간소화된 스키마.</li><p>스키마를 변경해야 하는 경우, 업데이트가 필요한 필드를 찾기 위해 사용하지 않는 수천 개의 필드를 검색하지 않아도 됩니다.</p></ul><p>XDM 스키마 업데이트의 단점은 다음과 같습니다.</p><ul><li>스키마를 업데이트하는 것은 Customer Journey Analytics으로 데이터를 보내기 전에 필요한 시간이 많이 걸리는 프로세스입니다.</li></ul> | 없음 |

{style="table-layout:auto"}

## 그런 다음 Adobe Experience Platform으로 데이터 보내기

위의 정보를 사용하여 마이그레이션 방법을 선택한 후 방법 알아보기 [Adobe Experience Platform에 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) 선택한 마이그레이션 방법에 따라 다릅니다.