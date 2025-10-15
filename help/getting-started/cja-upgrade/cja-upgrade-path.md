---
title: Customer Journey Analytics 업그레이드 경로 선택
description: Customer Journey Analytics로 업그레이드할 때 가능한 업그레이드 경로의 장단점에 대해 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '2981'
ht-degree: 98%

---

# 2단계: 업그레이드 경로 선택

+++이 섹션을 확장하여 이 페이지의 정보가 대규모 업그레이드 프로세스에 맞는 위치를 확인합니다. 이전 업그레이드 단계가 모두 완료되었는지 확인합니다.

이 섹션을 계속 진행하기 전에 먼저 이전 업그레이드 작업을 모두 완료했는지 확인합니다.

이 페이지의 정보는 아래 테이블에 강조 표시된 대로 업그레이드 프로세스의 2단계에 대한 내용을 다룹니다.

| 업그레이드 작업 | 세부 사항 |
|---------|----------|
| **1단계: [업그레이드 시작](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Customer Journey Analytics로 업그레이드하는 이점과 기본적인 업그레이드 프로세스에 대해 알아봅니다. |
| <span class="preview">**2단계: 업그레이드 경로 선택**</span> | <span class="preview">Customer Journey Analytics으로 업그레이드할 수 있는 방법은 다양합니다. 조직의 현재 Adobe Analytics 환경과 장기적인 목표에 따라 조직에 가장 적합한 방법을 선택합니다.</span> |
| **3단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 전송하는 프로세스는 2단계에서 선택한 업그레이드 경로에 따라 다릅니다. |
| **4단계: [내역 데이터 유지](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 대부분의 조직에서는 특정 기간 동안 Adobe Analytics 내역 데이터를 보관해야 합니다. 이를 달성하기 위해 다양한 옵션을 사용할 수 있습니다. |
| **5단계: [추가 구현 작업 수행](/help/getting-started/cja-getting-started.md)** | 업그레이드 프로세스의 이 시점에서는 Customer Journey Analytics 환경을 사용할 준비가 되기 전에 다양한 작업을 수행해야 합니다.<p>이러한 추가 작업은 Adobe Analytics의 업그레이드뿐 아니라 새로운 Customer Journey Analytics 구현에도 적용됩니다.</p><p>이러한 작업에는 다음이 포함됩니다.</p><ul><li>다른 데이터를 Experience Platform으로 가져오기</li><li>Platform 데이터 세트와 Customer Journey Analytics 간 연결 만들기</li><li>데이터 보기 만들기</li><li>보고 API 사용량 이식</li><li>데이터 피드 및 Data Warehouse 확인</li><li>프로젝트 및 구성 요소 마이그레이션</li><li>사용자 온보딩 계획 수립</li></ul> <p>자세한 내용은 [Customer Journey Analytics 시작하기](/help/getting-started/cja-getting-started.md)를 참조하십시오. |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>이 페이지의 정보는 다음과 같은 보다 포괄적인 업그레이드 정보로 대체됩니다. <ul><li>**권장되는 업그레이드 단계**<p>자세한 내용은 [Adobe Analytics에서 Customer Journey Analytics로 업그레이드할 때 권장되는 경로](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)를 참조하십시오.</p></li><li>**Customer Journey Analytics 업그레이드 안내서**<p>조직과 고유한 상황에 맞게 업그레이드 단계를 동적으로 생성하는 새로운 업그레이드 안내서가 출시되었습니다.</p><p>Customer Journey Analytics에서 안내서에 액세스하려면 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics로 업그레이드]**&#x200B;를 선택하십시오. 화면에 표시되는 안내를 따르십시오.</p></li></ul>


Customer Journey Analytics로 업그레이드하기로 결정한 후 조직에 최적의 업그레이드 경로를 결정해야 합니다.

Adobe Analytics에서 Customer Journey Analytics로 업그레이드하는 경로는 다음 요소에 따라 달라집니다.

* 기존 Adobe Analytics 구현

* 미래의 목표

이 페이지의 정보를 사용하여 조직의 현재 구현 및 미래 목표와 가장 잘 일치하는 Customer Journey Analytics 업그레이드 경로를 결정합니다.

조직에 최적의 업그레이드 경로를 결정하려면 다음 섹션을 순차적으로 읽어보십시오.

1. 먼저, [사용 가능한 업그레이드 경로를 파악](#understand-upgrade-paths)합니다.

1. 그런 다음 [어떤 업그레이드 경로를 사용할 수 있는지 평가](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation)합니다.

1. 마지막으로, [각 업그레이드 경로의 장점과 단점을 검토](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you)합니다.

## 업그레이드 경로 파악

Adobe Analytics에서 Customer Journey Analytics로 업그레이드할 때 다양한 경로를 사용할 수 있습니다.

일반적으로 각 업그레이드 경로는 업그레이드를 실행하는 데 필요한 노력 수준과 업그레이드가 완료된 후 달성할 수 있는 장기적 실행 가능성에 따라 다릅니다.

다음 테이블에는 각 업그레이드 경로, 노력 수준 및 장기적 실행 가능성이 나열되어 있습니다.

| 업그레이드 경로 | 노력 수준 | 장기적 실행 가능성 |
|---------|----------|---------|
| **Experience Platform Web SDK의 새로운 구현 및 분석 소스 커넥터**</br> Experience Platform Web SDK를 새롭게 구현하여 Customer Journey Analytics를 사용할 수 있습니다. 이렇게 하면 Adobe Experience Platform Edge Network 및 Customer Journey Analytics로 데이터를 전송할 수 있습니다. 또한 Analytics 소스 커넥터를 사용하여 내역 데이터를 Customer Journey Analytics로 가져옵니다.<p>아직 Web SDK를 사용하지 않는 조직의 경우, 이 업그레이드 경로는 단계 수가 적기 때문에 Edge Network로 데이터를 가져오는 것이 가장 간단할 수 있습니다. 그러나 모든 작업이 미리 이루어지기 때문에(예: XDM 스키마 생성) 초기 작업이 더 많이 필요합니다.</p><p>기본 단계는 다음과 같습니다.</p><ol><li>조직을 위한 XDM 스키마를 만듭니다.</li><li>Web SDK를 구현합니다.</li><li>Platform으로 데이터를 전송합니다.</li><li>Analytics 소스 커넥터를 설정합니다.</br>Analytics 소스 커넥터는 과거 Adobe Analytics 데이터를 Customer Journey Analytics로 가져오는 데 사용됩니다.<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--></li></ol><p><!-- **Note:** This is the recommended upgrade path when upgrading to Customer Journey Analytics. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). --></p> | 높음 | 높음 |
| **Experience Platform Web SDK의 새로운 구현**</br> Experience Platform Web SDK를 새롭게 구현하여 Customer Journey Analytics를 사용할 수 있습니다. 이렇게 하면 Adobe Experience Platform Edge Network 및 Customer Journey Analytics로 데이터를 전송할 수 있습니다. <p>아직 Web SDK를 사용하지 않는 조직의 경우, 이 업그레이드 경로는 단계 수가 적기 때문에 Edge Network로 데이터를 가져오는 것이 가장 간단할 수 있습니다. 그러나 모든 작업이 미리 이루어지기 때문에(예: XDM 스키마 생성) 초기 작업이 더 많이 필요합니다.</p><p>기본 단계는 다음과 같습니다.</p><ol><li>조직을 위한 XDM 스키마를 만듭니다.</li><li>Web SDK를 구현합니다.</li><li>Platform으로 데이터를 전송합니다.</li></ol> | 높음 | 높음 |
| **Web SDK를 사용하도록 Adobe Analytics 구현 마이그레이션**</br> Adobe Analytics 구현이 AppMeasurement 또는 Analytics 확장 기능인 경우 Customer Journey Analytics로 전송하기 전에 Adobe Experience Platform Web SDK를 사용하여 데이터를 Edge Network 및 Adobe Analytics로 전송하기 위해 마이그레이션할 수 있습니다.<p>아직 Web SDK를 사용하지 않는 조직의 경우, 데이터를 Edge Network로 전송하는 가장 쉽고 원활한 방법이며, 단계가 더 많지만 Adobe Analytics에서 Customer Journey Analytics로 보다 체계적으로 전환하고 더 구체적인 이정표가 됩니다.</p><p>기본 단계는 다음과 같습니다.</p><ol><li>기존 Adobe Analytics 구현을 Web SDK로 옮기고 모든 것이 Adobe Analytics에서 제대로 작동하는지 확인합니다.</li><li>시간 가능한 경우 조직을 위한 XDM 스키마를 만듭니다.</li><li>데이터스트림 매핑을 사용하여 데이터 오브젝트의 모든 필드를 XDM 스키마에 매핑합니다.</li><li>Platform으로 데이터를 전송합니다.</li></ol> | 중간 | 높음 |
| **기존 Adobe Analytics Web SDK 구현 구성**</br> Adobe Analytics 구현에서 이미 Adobe Experience Platform Web SDK를 사용하고 있는 경우 데이터스트림을 설정하여 Platform으로 데이터를 전송할 수 있습니다. 또는 이미 Platform으로 데이터를 전송하고 있는 경우 Platform 데이터 세트와 Customer Journey Analytics 간의 연결을 생성하기만 하면 됩니다.<p>Customer Journey Analytics에 사용할 데이터를 Platform으로 전송하기 전에 조직의 특정 요구 사항과 사용 중인 다른 Platform 애플리케이션에 맞게 Adobe Analytics 스키마를 업데이트하는 것이 좋습니다.</p><p>기본 단계는 다음과 같습니다.</p><ol><li>Platform으로 데이터 전송을 시작합니다.<p>Adobe Analytics 구현을 통해 이미 Platform으로 데이터를 전송하고 있는 경우 이 단계는 필요하지 않습니다. 이 프로세스의 뒷부분에 설명된 대로 Platform 데이터 세트와 Customer Journey Analytics 간의 연결만 만들면 됩니다.</p></li><li>(선택 사항) 시간 가능한 경우 조직을 위한 XDM 스키마를 만듭니다.</li><li>(조건부) XDM 스키마를 만든 경우 데이터스트림 매핑을 사용하여 데이터 오브젝트의 모든 필드를 XDM 스키마에 매핑합니다.</li></ol> | 낮음 | 높음 |
| **Analytics 소스 커넥터 사용**</br> Adobe Analytics 구현이 AppMeasurement 또는 Analytics 확장 기능인 경우 Customer Journey Analytics의 데이터 보기로 데이터를 전송할 수 있습니다.<p>이는 Customer Journey Analytics으로 데이터를 가져오는 가장 쉬운 방법이지만 장기적으로는 가장 실행 가능성이 낮은 방법입니다.</p> <p>**참고:** 이 업그레이드 경로는 독립적으로 사용할 수 있습니다. 그러나 최상의 결과를 위해 이 업그레이드 경로를 Experience Platform Web SDK의 새로운 구현과 함께 사용하는 것을 권장합니다. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--> </p> | 낮음 | 낮음 |

{style="table-layout:auto"}

다음 다이어그램을 사용하여 각 업그레이드 경로가 노력 수준과 장기적 실행 가능성 측면에서 스펙트럼의 어디에 속하는지 시각화할 수 있습니다.

![cja 업그레이드 경로](assets/cja-upgrade-path-chart.png)

## 현재 Adobe Analytics 구현을 기반으로 사용 가능한 업그레이드 경로 평가

각 유형의 Adobe Analytics 구현에 대해 모든 업그레이드 경로를 사용할 수 있는 것은 아닙니다.

아래 정보를 사용하면 조직에 가장 적합한 업그레이드 경로를 이해하는 데 도움이 됩니다.

더욱 구체적인 조언, 지침 또는 지원이 필요한 경우 Adobe 담당자에게 문의하십시오.

| 기존 Adobe Analytics 구현 | 사용 가능한 업그레이드 경로 |
|---------|----------|
| AppMeasurement | <ul><li>Experience Platform Web SDK의 새로운 구현</li><li>Adobe Analytics를 Web SDK로 마이그레이션</li><li>Analytics 소스 커넥터</li><li>(권장) Analytics 소스 커넥터를 사용한 Experience Platform Web SDK의 새로운 구현</li></ul> |
| Adobe Analytics 확장 | <ul><li>Experience Platform Web SDK의 새로운 구현</li><li>Adobe Analytics를 Web SDK로 마이그레이션</li><li>Analytics 소스 커넥터</li><li>(권장) Analytics 소스 커넥터를 사용한 Experience Platform Web SDK의 새로운 구현</li></ul> |
| Web SDK | <ul><li>Adobe Analytics Web SDK 구현을 구성하여 Platform으로 데이터 전송</li><li>(권장) Analytics 소스 커넥터를 사용한 Experience Platform Web SDK의 새로운 구현</li></ul> |

{style="table-layout:auto"}

## 사용할 수 있는 업그레이드 경로의 장점과 단점 검토

업그레이드 경로의 장단점은 기존 Adobe Analytics 구현에 따라 다릅니다.

아래 정보를 사용하여 적합한 업그레이드 경로를 결정하기 전에 [업그레이드 경로 파악](#understand-migration-methods)의 정보를 검토하십시오.

>[!NOTE]
>
>다음 섹션에서 설명하는 각 업그레이드 경로는 독립적으로 사용할 수 있지만 Adobe는 현재 Adobe Analytics 구현에 관계없이 Adobe Analytics에서 Customer Journey Analytics로 업그레이드할 때 두 가지 업그레이드 접근 방식을 권장합니다. **Adobe Analytics 소스 커넥터**&#x200B;와 **Experience Platform Web SDK의 새로운 구현**.
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### Adobe implementations 구현의 경우: AppMeasurement 및 Adobe implementations 확장 기능 사용

다음은 AppMeasurement 또는 Adobe Analytics 확장 기능을 사용하여 Adobe Analytics를 구현한 조직에서 사용할 수 있는 업그레이드 경로입니다. 각 섹션을 확장하여 각 업그레이드 경로의 장단점을 확인합니다.

#### 업그레이드 경로

+++Experience Platform Web SDK의 새로운 구현

| 장점 | 단점 |
|----------|---------|
| <ul><li>**Experience Edge Network에서 데이터 호스팅의 모든 장점을 제공합니다**. <p>이러한 장점은 다음과 같습니다.</p><ul><li>Adobe Experience Platform은 [실시간 개인화 사용 사례](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ko)를 지원하도록 구축되었기 때문에 뛰어난 성능의 보고 및 데이터 가용성</li><li>다른 Experience Cloud 제품(AJO, RTCDP 등) 간 Adobe Experience Cloud 데이터 수집을 위한 구현 통합</li><li>Adobe Analytics 명명법(Prop, eVar, 이벤트 등)에 의존하지 않음</li></ul></li><li>**미래 지향적**: 향후 구현 업데이트가 더 쉬워집니다.</li></ul> | <ul><li>**처음부터 새로운 구현 필요**: 새로운 구현을 처음부터 수행해야 한다는 점은 다음과 같은 단점이 있습니다. </li><ul><li>**시간 소모**: 처음부터 새로운 구현을 시작해야 하기 때문에 가장 시간이 많이 걸리고 까다로운 업그레이드 경로입니다.</li><li>**XDM에서 전체 스키마 재생성**: Web SDK 구현을 시작하기 전에 XDM에서 전체 스키마를 다시 만들어야 합니다.</li><li>**규칙과 데이터 요소 재생성**: Web SDK 구현을 시작하기 전에 Adobe Analytics 구현에서 모든 규칙 조건과 데이터 요소를 다시 만들어야 합니다.</li></ul><li>**내역 데이터 유지를 고려하지 않음:** Adobe는 Customer Journey Analytics로 업그레이드한 후에도 내역 데이터를 유지하려면 Experience Platform Web SDK의 새로운 구현과 함께 Analytics 소스 커넥터를 사용할 것을 권장합니다. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**원래 구현 데이터와 새로운 구현 데이터 비교를 고려하지 않음:** Adobe는 Customer Journey Analytics로 업그레이드한 후 데이터를 비교하기 위해 Experience Platform Web SDK의 새로운 구현과 함께 Analytics 소스 커넥터를 사용할 것을 권장합니다. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

+++Adobe Analytics을 Experience Platform Web SDK으로 마이그레이션

| 장점 | 단점 |
|----------|---------|
| <ul><li>**Experience Edge Network에서 데이터 호스팅의 모든 장점을 제공합니다**. <p>이러한 장점은 다음과 같습니다.</p><ul><li>Adobe Experience Platform은 [실시간 개인화 사용 사례](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ko)를 지원하도록 구축되었기 때문에 뛰어난 성능의 보고 및 데이터 가용성</li><li>다른 Experience Cloud 제품(AJO, RTCDP 등) 간 Adobe Experience Cloud 데이터 수집을 위한 구현 통합</li><li>Adobe Analytics 명명법(Prop, eVar, 이벤트 등)에 의존하지 않음</li></ul><li>**기존 구현 사용**: 이 접근 방식은 일부 구현 변경이 필요하지만 처음부터 완전히 새로운 구현이 필요하지는 않습니다. 기존 Adobe Analytics 보고에 영향을 주지 않으면서 구현 로직을 최소한으로 변경하여 기존 데이터 레이어와 코드를 사용할 수 있습니다.</li><li>**향후 조직을 위한 XDM 스키마를 생성할 수 있도록 유연성 향상**: 기존 Adobe Analytics 구현을 마이그레이션하여 Web SDK를 사용하고 모든 것이 Adobe Analytics에서 제대로 작동하는지 확인한 후 XDM 스키마를 생성할 수 있습니다. 이러한 유연성 덕분에 Customer Journey Analytics을 보다 체계적이고 신중하게 업그레이드할 수 있습니다.</li></ul> | <ul><li>**Platform으로 데이터를 전송하기 위해 매핑 필요**: 조직에서 Customer Journey Analytics를 사용할 준비가 되면 Adobe Experience Platform의 데이터 세트로 데이터를 보내야 합니다. 이 액션을 수행하려면 데이터 오브젝트의 모든 필드가 XDM 스키마 필드에 할당되는 데이터스트림 매핑 도구의 항목이어야 합니다. 매핑은 이 워크플로에서 한 번만 수행하면 되며, 구현 변경이 필요하지 않습니다. 그러나 XDM 오브젝트에서 데이터를 전송할 때는 추가적인 단계가 필요하지 않습니다.</li><li>**기술 부채**: 이 접근 방식은 기존 구현의 수정된 형태를 사용하기 때문에 필요할 때 구현 논리를 추적하고 향후 변경 사항을 수행하는 것이 어려울 수 있습니다. </li></ul> |

{style="table-layout:auto"}

+++

+++Analytics 소스 커넥터 사용

| 장점 | 단점 |
|----------|---------|
| <ul><li>가장 시간이 적게 걸리며 까다로운 업그레이드 경로. <p>최소한의 투자로 데이터가 Customer Journey Analytics로 빠르게 마이그레이션됩니다.</p></li></ul> | <ul><li>**데이터가 Edge Network로 전송되지 않습니다**. <p>이로 인해 다음과 같은 단점이 발생합니다.</p><ul><li>모든 업그레이드 경로에 대한 보고에서 가장 높은 수준의 [지연](/help/technotes/guardrails.md#latencies) 발생, 실시간 개인화 사용 사례에 최적화되지 않음.</li><li>데이터는 다른 Adobe Experience Platform 애플리케이션과 공유할 수 없으며 Customer Journey Analytics에만 국한됨</li><li>Adobe Analytics 명명법(Prop, eVar, 이벤트 등)에 의존</li></ul><li>**향후 Web SDK로의 전환이 어려움**: 결국에는 Experience Platform Web SDK가 제공하는 이점을 활용하고 싶을 것입니다. Experience Platform Web SDK를 사용하려면 새로 구현해야 합니다.</li><li>**스키마에서 Analytics 경험 이벤트 필드 그룹 사용**: 이 필드 그룹은 Customer Journey Analytics 스키마에 필요하지 않은 여러 Adobe Analytics 이벤트를 추가합니다. 이로 인해 Customer Journey Analytics에 필요한 것보다 더 복잡하고 혼란스러운 스키마가 생길 수 있습니다.</li></ul><p>이러한 단점 때문에 Adobe는 Experience Platform Web SDK의 새로운 구현과 함께 Analytics 소스 커넥터를 사용할 것을 권장합니다. <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></p> |

{style="table-layout:auto"}

+++

### Adobe Analytics 구현의 경우: Web SDK 사용

다음 업그레이드 경로는 Experience Platform Web SDK로 Adobe Analytics를 구현한 조직에서 사용할 수 있습니다.

이 업그레이드 경로를 선택할 때는 스키마도 선택해야 합니다.

#### 업그레이드 경로

+++Adobe Analytics Web SDK 구현을 구성하여 Platform으로 데이터 전송

| 장점 | 단점 |
|----------|---------|
| Adobe Analytics 구현에서 이미 Web SDK를 사용하고 있는 경우 이 업그레이드 경로가 권장됩니다.<ul><li>**Experience Edge Network에서 데이터 호스팅의 모든 장점을 제공합니다**. <p>이러한 장점은 다음과 같습니다.</p><ul><li>Adobe Experience Platform은 [실시간 개인화 사용 사례](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ko)를 지원하도록 구축되었기 때문에 뛰어난 성능의 보고 및 데이터 가용성</li><li>다른 Experience Cloud 제품(AJO, RTCDP 등) 간 Adobe Experience Cloud 데이터 수집을 위한 구현 통합</li><li>Adobe Analytics 명명법(Prop, eVar, 이벤트 등)에 의존하지 않음</li></ul><li>**기존 구현 사용**: 이 접근 방식은 일부 구현 변경이 필요하지만 처음부터 완전히 새로운 구현이 필요하지는 않습니다. 기존 Adobe Analytics 보고에 영향을 주지 않으면서 구현 로직을 최소한으로 변경하여 기존 데이터 레이어와 코드를 사용할 수 있습니다.</li><li>**XDM 스키마를 사용하기 위한 옵션 제공**: 기존 Adobe Analytics 스키마를 사용하거나 데이터 오브젝트의 XDM 스키마 및 필드를 XDM 스키마에 매핑할 수 있습니다. [XDM 스키마](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/home#xdm-schemas)는 필요한 모든 필드를 정의할 수 있는 유연한 스키마이며, 관련된 필드만 정의할 수 있습니다. <p>자체 XDM 스키마를 사용하는 것의 이점에 대한 자세한 내용은 아래의 “자체 XDM 스키마 사용”을 참조하십시오.</p></li><li>**규칙과 데이터 요소 유지**: 새로운 규칙 액션이 필요하지만 최소한의 변경으로 기존 데이터 요소와 규칙 조건을 재사용할 수 있습니다.</li><li>**미래 지향적**: 자체 XDM 스키마를 사용하도록 선택하면 향후 구현 업데이트가 더 쉬워집니다.</li></ul> | 없음 |

{style="table-layout:auto"}

+++

#### 스키마 선택

Adobe Analytics Web SDK 구현을 구성하여 Platform으로 데이터를 전송할 수 있는 업그레이드 경로를 선택한 경우, 사용할 스키마를 선택할 수 있습니다.

기존 Adobe Analytics 스키마를 사용할지, 아니면 다른 Platform 서비스를 사용하기 시작하면서 조직의 요구에 더 잘 맞추기 위해 자신의 XDM 스키마로 업데이트할지 선택할 수 있습니다.

+++Adobe Analytics Web SDK 구현에 Adobe Analytics 스키마 사용

| 장점 | 단점 |
|----------|---------|
| <p>Adobe Analytics 스키마 사용의 장점은 다음과 같습니다.</p><ul><li>업그레이드의 용이성<p>이미 Adobe Experience Platform Web SDK를 사용하여 Adobe Analytics로 데이터를 전송하고 있는 경우 데이터스트림에 서비스를 추가하여 Adobe Experience Platform으로 데이터를 전송할 수 있습니다(이 서비스는 Customer Journey Analytics 구성에서 사용할 수 있음).</p></li></ul> | <p>Adobe Analytics 스키마 사용의 단점은 다음과 같습니다.</p><ul><li>Adobe Analytics 스키마를 사용하면 다른 Platform 애플리케이션과 함께 사용할 수 있다는 점에서 제한이 없지만 다른 방식보다 더 복잡한 스키마를 만들 수 있습니다. Adobe Analytics 스키마에는 조직에서 사용할 가능성이 낮은 Adobe Analytics에만 국한된 오브젝트가 많이 포함되어 있기 때문입니다.<p>스키마 변경이 필요할 때 업데이트가 필요한 필드를 찾기 위해 수천 개의 사용되지 않은 필드를 선별해야 합니다.</p></li></ul> |

+++

+++Adobe Analytics Web SDK 구현에 고유한 XDM 스키마 사용

| 장점 | 단점 |
|----------|---------|
| <ul><p>자체 XDM 스키마를 업데이트하는 것의 장점은 다음과 같습니다.</p><ul><li>조직의 요구와 사용하는 특정 Platform 애플리케이션에 맞춘 간소화된 스키마.</li><p>스키마 변경이 필요할 때 업데이트가 필요한 필드를 찾기 위해 수천 개의 사용되지 않은 필드를 선별해야 할 필요가 없습니다.</p></ul> | <p>자체 XDM 스키마를 업데이트하는 것의 단점은 다음과 같습니다.</p><ul><li>스키마를 업데이트하는 것은 Platform으로 데이터를 전송하기 전에 필요한 시간이 많이 소요되는 프로세스입니다.</li></ul> |

+++

## Adobe Experience Platform으로 데이터 보내기

위의 정보를 사용하여 업그레이드 경로를 선택한 후 선택한 업그레이드 경로에 따라 [Adobe Experience Platform으로 데이터를 전송](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)하는 방법에 대해 알아보십시오
