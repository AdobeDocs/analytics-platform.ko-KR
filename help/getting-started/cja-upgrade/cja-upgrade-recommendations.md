---
title: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 단계에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1629'
ht-degree: 8%

---

# Adobe Analytics에서 Customer Journey Analytics으로 업그레이드

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 [권장되는 업그레이드 단계](#recommended-upgrade-steps-for-most-organizations)를 따를 수 있습니다. 또는 조직의 고유 상황에 맞게 [업그레이드 단계를 동적으로 생성](#dynamically-generate-upgrade-steps-for-your-organization)할 수 있습니다.

## 대부분의 조직에 권장되는 업그레이드 단계 {#upgrade-process}

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 권장 프로세스는 Experience Platform Web SDK의 새로운 구현이며, Customer Journey Analytics에서 선호하는 데이터 수집 방법입니다. 웹 SDK과 함께 Adobe에서는 Analytics 소스 커넥터를 사용하여 Customer Journey Analytics으로 전환하는 것을 권장합니다. Analytics 소스 커넥터를 사용하여 이전 Adobe Analytics 데이터를 유지하고 병렬 데이터 비교를 수행할 수 있습니다.

Experience Platform Web SDK을 사용하여 내역 데이터가 충분하고 Customer Journey Analytics으로 완전히 전환한 후에는 Analytics 소스 커넥터를 끄고 웹 SDK을 독점적으로 사용할 수 있습니다.

>[!NOTE]
>
>이 섹션에 설명된 업그레이드 단계가 조직에 실용적이지 않은 경우 Customer Journey Analytics 업그레이드 안내서 를 사용하여 조직의 고유 상황에 맞는 업그레이드 단계를 동적으로 생성합니다. (Customer Journey Analytics에서 가이드에 액세스하려면 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics으로 업그레이드]**&#x200B;를 선택합니다. 화면에 표시되는 안내를 따릅니다.)

### 높은 수준 권장 업그레이드 프로세스 {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Adobe Analytics의 이전 데이터"
>abstract="Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform 및 Customer Journey Analytics로 가져옵니다."

<!-- markdownlint-enable MD034 -->

1. **지속적인 데이터 수집을 위해 Experience Platform Web SDK 구현**

   Experience Platform Web SDK의 새로운 구현은 Customer Journey Analytics에 대한 데이터를 수집하는 가장 좋은 방법입니다. Customer Journey Analytics 구현을 위한 가장 성능적이고, 간단하며, 미래에 대비할 수 있는 방법이기 때문에 Customer Journey Analytics을 최대한 활용할 수 있는 최고의 기반을 제공합니다.

   * Adobe Experience Platform은 실시간 개인화 사용 사례를 지원하기 위해 구축되었으므로 성능 높은 보고 및 데이터 가용성

   * 다른 Experience Cloud 제품(AJO, RTCDP 등) 간에 Adobe Experience Cloud 데이터 수집을 위한 구현 통합

   * Adobe Analytics 명명법(prop, eVar, 이벤트 등)에 의존하지 않음

1. **이전 데이터를 가져올 Adobe Analytics 소스 커넥터 설정**

   Customer Journey Analytics에서 Experience Platform Web SDK을 사용하는 것으로 원활하게 전환하는 데 도움이 되도록 Adobe에서는 Adobe Analytics 소스 커넥터 를 사용하는 것이 좋습니다. 이렇게 하면 Customer Journey Analytics의 기존 Adobe Analytics 구현에서 새 Experience Platform 웹 SDK 구현의 데이터와 나란히 내역 데이터를 유지하고 데이터를 볼 수 있습니다.

   Analytics 소스 커넥터를 사용하면 다음 작업을 수행할 수 있습니다.

   * Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform 및 Customer Journey Analytics로 가져옵니다.

     내역 Adobe Analytics 데이터를 유지해야 하는 동안 Analytics 소스 커넥터를 계속 실행할 수 있습니다.

   * Customer Journey Analytics 내에서 원래 Adobe Analytics 구현(AppMeasurement, Analytics 확장 또는 Web SDK 확장)으로 수집된 데이터를 봅니다. 이 데이터를 새 웹 SDK 구현의 데이터와 나란히 비교할 수 있습니다.

     차이점을 잘 알고 있을 때까지 Analytics 소스 커넥터를 계속 실행할 수 있습니다. <!--elaborate on what those differences are? -->

   독립 실행형 구현으로서의 Analytics 소스 커넥터는 Customer Journey Analytics 사용에 권장되는 장기적인 방법이 아닙니다. 이는 지연 시간이 길고, 복잡하고 복잡한 스키마, Adobe Analytics 명명법(prop, eVar 등)에 의존하고, 결국 Analytics 소스 커넥터에서 권장되는 웹 SDK 구현으로 이동하기 어렵기 때문입니다.

### 자세한 권장 업그레이드 단계

다음 단계에서는 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 권장 프로세스에 대해 간략히 설명합니다.

각 단계는 보다 자세한 프로세스에 대한 높은 수준의 설명을 제공합니다. 각 단계에 대한 링크를 따라 관련 작업을 완료한 후 이 페이지로 돌아와 프로세스의 다음 단계를 계속합니다.

1. [XDM 스키마 아키텍처를 계획하십시오](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Adobe Experience Platform에서 원하는 사용자 지정 스키마를 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   스키마를 생성할 때 다음 옵션을 고려하십시오.

   * Customer Journey Analytics을 RTCDP과 통합하려면 [Customer Journey Analytics에서 사용할 XDM 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)에 설명된 대로 스키마에서 **[!UICONTROL 프로필]** 옵션을 활성화해야 합니다. 이 옵션이 활성화된 경우 이 스키마를 기반으로 한 데이터 세트에 데이터를 수집하면 해당 데이터가 실시간 고객 프로필에 병합됩니다.

   * 스트리밍 미디어 데이터를 포함하려면 [스트리밍 데이터를 수집 및 사용하도록 스키마를 구성](/help/data-ingestion/streaming.md)해야 합니다.

1. [Adobe Experience Platform에서 데이터 세트를 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (선택 사항) Adobe Analytics에서 분류 데이터를 사용하는 경우 Customer Journey Analytics에서 분류 데이터를 데이터 세트에 추가할 수 있습니다.

   이렇게 하려면 [분류 데이터를 포함하는 각 차원에 대한 조회 데이터 집합을 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. AppMeasurement 또는 Analytics 확장 기능(태그)을 사용하는 Adobe Analytics 구현의 경우 [Adobe Experience Platform에서 데이터 스트림을 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Web SDK을 사용하는 Adobe Analytics 구현의 경우 데이터 스트림이 이미 있습니다. 자세한 내용은 [데이터를 플랫폼으로 보내도록 기존 Adobe Analytics Web SDK 구현 구성](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)을 참조하십시오.

1. [데이터스트림에 서비스로 Adobe Experience Platform 추가](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (선택 사항) Customer Journey Analytics을 Adobe Journey Optimizer과 통합하려면 Adobe Journey Optimizer에서 사용할 개인화 개체를 구현에 사용하십시오.

1. Customer Journey Analytics 구현을 위해 Experience Platform Web SDK을 구현하는 방법을 설명하는 섹션을 확장한 다음 관련 단계를 완료합니다.

   +++수동 구현(JS 파일)

   1. [사이트에 alloy.js 추가](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. XDM 개체를 채우고 데이터스트림으로 보냅니다.

+++

   +++태그

   1. [태그 속성을 만들고 Adobe Experience Platform Web SDK 확장을 추가합니다](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [태그 속성에 Adobe Experience Platform Web SDK 확장 기능 추가](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [사이트에서 로더 태그를 구현합니다](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [태그에 XDM 데이터 수집 논리 추가](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Edge Network API를 사용하여 데이터를 원하는 데이터 스트림으로 전송합니다.

+++

1. [웹 SDK 구현이 데이터 집합에 데이터를 보내고 있는지 확인](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Customer Journey Analytics에서 연결을 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (선택 사항) 웹 데이터를 콜 센터 데이터와 같은 다른 채널의 데이터와 연결합니다.

   [콜센터 및 웹 데이터 가져오기](/help/use-cases/cross-channel/call-center.md)에 설명된 대로 Customer Journey Analytics 연결에 추가 데이터 세트를 추가하여 이 작업을 수행할 수 있습니다.

1. [Customer Journey Analytics에서 데이터 보기를 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [데이터가 Customer Journey Analytics의 데이터 보기로 이동하는지 확인](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [프로젝트 및 구성 요소 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (선택 사항) Adobe Analytics에서 마케팅 채널을 사용하는 경우 [Customer Journey Analytics에서 마케팅 채널 파생 필드를 만들 수 있습니다](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   파생 필드는 Customer Journey Analytics 실시간 보고의 중요한 측면입니다. 파생 필드를 사용하면 사용자 정의 가능한 규칙 빌더를 통해 즉석에서 (복잡한) 데이터 조작을 정의할 수 있습니다.

   파생 필드의 한 가지 사용은 하나 이상의 조건(예: URL 매개 변수, 페이지 URL 또는 페이지 이름)을 기반으로 적절한 마케팅 채널을 결정하는 파생된 마케팅 채널 필드를 정의하는 것입니다.

   파생 필드에서 [마케팅 채널 함수 템플릿](/help/data-views/derived-fields/derived-fields.md#marketing-channels)을(를) 사용하여 마케팅 채널의 파생 필드를 신속하게 만듭니다.

1. 이전 구현의 Adobe Analytics 데이터와 새 구현의 Customer Journey Analytics 데이터를 비교하고, 차이점 및 차이점이 존재하는 이유를 이해해야 합니다. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Analytics 소스 커넥터를 사용하여 Adobe Analytics에서 내역 데이터 가져오기:

   >[!NOTE]
   >
   >이전에 Analytics 소스 커넥터를 만들지 않은 경우 다음 단계를 사용하십시오.
   >
   >Customer Journey Analytics에서 Analytics 소스 커넥터를 이미 사용하고 있는 경우 [Analytics 소스 커넥터에서 Customer Journey Analytics용 웹 SDK으로 전환](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)의 단계를 따르십시오.

   1. [Analytics 소스 커넥터용 XDM 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Analytics 소스 커넥터가 없는 경우 [Analytics 소스 커넥터를 만들고 필드를 XDM 스키마에 매핑하십시오](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      또는

      Analytics 소스 커넥터가 이미 있는 경우 [소스 커넥터의 필드를 XDM 스키마에 매핑](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)하십시오.

   1. [연결에 Analytics 원본 커넥터 데이터 집합을 추가](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)합니다.

1. 사용자 온보딩을 계획합니다.

   Adobe Analytics와 마찬가지로 Analysis Workspace는 Customer Journey Analytics의 주요 사용자 대상 도구입니다. 단, Customer Journey Analytics에서 Analysis Workspace를 사용할 때 사용자가 알아 두어야 할 몇 가지 주요 차이점이 있습니다.

   사용자가 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점을 숙지할 수 있도록 충분한 시간(3~6개월)을 할애하도록 하십시오.

   Adobe Analytics와 Customer Journey Analytics의 주요 차이점에 대한 자세한 내용은 [Adobe Analytics 사용자를 위한 사용 안내서](/help/getting-started/aa-to-cja-user.md)를 참조하십시오.

1. Customer Journey Analytics의 [기능 지원에 대해 알아보세요](/help/getting-started/aa-vs-cja/cja-aa.md). 대부분의 Adobe Analytics 기능은 Customer Journey Analytics에서 지원되며, Customer Journey Analytics에서 많은 추가 기능을 사용할 수 있습니다.

1. Customer Journey Analytics 웹 SDK 구현이 완료되고 수집 중인 데이터에 익숙해지면 Adobe Analytics을 비활성화하십시오.

   Adobe은 Customer Journey Analytics을 구현한 후 일정 기간 동안 Adobe Analytics 환경을 계속 실행할 것을 권장합니다.

   업그레이드 중이나 업그레이드 후 Adobe Analytics을 사용하는 방법과 Adobe Analytics을 사용하지 않도록 설정하는 제안 시점에 대한 자세한 내용은 [Customer Journey Analytics으로 업그레이드한 후 Adobe Analytics이 필요한 시간 평가](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)를 참조하십시오.

## 조직에 대한 업그레이드 단계를 동적으로 생성

타임라인 및 리소스 제한과 같은 여러 요인에 따라 [권장 업그레이드 단계 이해](#1-understand-the-recommended-upgrade-steps)에 설명된 권장 업그레이드 단계가 조직에 실용적이지 않을 수 있습니다.

조직의 고유 환경에 대한 업그레이드 단계를 동적으로 생성하려면 다음을 수행합니다.

1. Customer Journey Analytics 업그레이드 안내서를 완료합니다.

   Customer Journey Analytics에서 가이드에 액세스하려면 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics으로 업그레이드]**&#x200B;를 선택합니다. 화면에 표시되는 안내를 따릅니다.

   이 업그레이드 안내서를 완료한 후 조직 요구 사항에 맞는 최적의 업그레이드 단계를 설명하는 단계별 지침이 제공됩니다. 기존 Adobe Analytics 환경 및 Customer Journey Analytics 목표에 가장 적합한 업그레이드 단계입니다.

1. 생성된 단계별 지침에 따라 Customer Journey Analytics으로 업그레이드하십시오.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->
