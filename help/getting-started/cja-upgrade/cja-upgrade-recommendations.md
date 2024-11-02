---
title: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ea16705e96047cbcf41e428d2018ea7c72b2afac
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 6%

---

# Adobe Analytics에서 Customer Journey Analytics으로 업그레이드

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드 프로세스를 시작하기 전에 먼저 권장되는 업그레이드 단계를 이해합니다.

>[!NOTE]
>
>이 섹션에 설명된 업그레이드 단계는 모든 조직이 Adobe Analytics에서 Customer Journey Analytics으로 성공적으로 업그레이드하는 데 사용할 수 있는 권장 업그레이드 단계입니다.
>
>그러나 타임라인 및 리소스 제한과 같은 여러 요인에 따라 권장되는 업그레이드 단계가 조직에 실용적이지 않을 수 있습니다. 이 경우 [Adobe Analytics을 사용하여 업그레이드 Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/)를 통해 조직의 고유한 환경에 맞는 업그레이드 단계를 동적으로 생성합니다.

## 대부분의 조직에 권장되는 업그레이드 단계

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 단계는 Customer Journey Analytics에 기본 데이터 수집 방법인 Experience Platform Web SDK의 새로운 구현입니다. Web SDK와 함께 Adobe에서는 내역 Adobe Analytics 데이터를 유지하고 병렬 데이터 비교를 수행하려면 Analytics 소스 커넥터를 사용하는 것이 좋습니다.

Customer Journey Analytics으로 완전히 전환하면 Analytics 소스 커넥터를 끄고 Experience Platform Web SDK를 독점적으로 사용할 수 있습니다.

### 높은 수준의 권장 업그레이드 프로세스

1. **Experience Platform Web SDK 구현**

   Experience Platform Web SDK의 새로운 구현은 Customer Journey Analytics을 위한 데이터를 수집하는 가장 좋은 방법입니다. Customer Journey Analytics 구현을 위한 가장 성능적이고, 간단하며, 미래에 대비할 수 있는 방법이기 때문에 Customer Journey Analytics을 최대한 활용할 수 있는 최상의 토대를 제공합니다.

   * Adobe Experience Platform은 실시간 개인화 사용 사례를 지원하기 위해 구축되었으므로 성능 높은 보고 및 데이터 가용성

   * 다른 Experience Cloud 제품(AJO, RTCDP 등) 간에 Adobe Experience Cloud 데이터 수집을 위한 구현 통합

   * Adobe Analytics 명명법(prop, eVar, 이벤트 등)에 의존하지 않음

1. **Adobe Analytics 소스 커넥터 설정**

   Customer Journey AnalyticsAdobe 에서 Experience Platform Web SDK 를 사용하는 것으로 원활하게 전환하려면 Adobe Analytics 소스 커넥터 를 사용하는 것이 좋습니다. 이렇게 하면 이전 데이터를 유지하고 새 Experience Platform Web SDK 구현의 데이터와 나란히 Customer Journey Analytics에서 기존 Adobe Analytics 구현의 데이터를 볼 수 있습니다.

   Analytics 소스 커넥터를 사용하면 다음 작업을 수행할 수 있습니다.

   * 이전 Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform 및 Customer Journey Analytics으로 가져옵니다.

     내역 Adobe Analytics 데이터를 유지해야 하는 동안 Analytics 소스 커넥터를 계속 실행할 수 있습니다.

   * Customer Journey Analytics 내에서 원래 Adobe Analytics 구현(AppMeasurement, Analytics 확장 또는 Web SDK 확장)으로 수집된 데이터를 봅니다. 이 데이터를 새 웹 SDK 구현의 데이터와 나란히 비교할 수 있습니다.

     차이점을 잘 알고 있을 때까지 Analytics 소스 커넥터를 계속 실행할 수 있습니다. <!--elaborate on what those differences are? -->

   독립 실행형 구현으로서의 Analytics 소스 커넥터는 Customer Journey Analytics 사용을 위한 장기적인 권장 방법이 아닙니다. 이는 지연 시간이 길고, 복잡하고 복잡한 스키마, Adobe Analytics 명명법(prop, eVar 등)에 의존하고, 결국 소스 커넥터에서 권장되는 웹 SDK 구현으로 이동하기 어렵기 때문입니다.

### 자세한 권장 업그레이드 단계

다음 단계는 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 권장 프로세스를 보여줍니다.

조직의 고유한 환경 및 요구 사항에 따라 이러한 권장 단계는 조직에 적합하지 않을 수 있습니다. 이 경우 [Adobe Analytics을 사용하여 업그레이드 Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/)를 통해 조직의 고유한 환경에 맞는 업그레이드 단계를 동적으로 생성합니다.

1. [XDM 스키마 아키텍처를 계획하십시오](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Adobe Experience Platform에서 원하는 사용자 지정 스키마를 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. [Adobe Experience Platform에서 데이터 세트를 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. 현재 Adobe Analytics 구현을 설명하는 섹션을 확장한 다음 관련 단계를 완료합니다.

   +++AppMeasurement을 사용하는 Adobe Analytics 구현의 경우

   1. [Adobe Experience Platform에서 데이터 스트림을 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

   +++Analytics 확장(태그)을 사용하는 Adobe Analytics 구현의 경우

   1. [Adobe Experience Platform에서 데이터 스트림을 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

+++ Web SDK를 사용하는 Adobe Analytics 구현의 경우

   추가 단계는 필요하지 않습니다.

+++

1. [데이터스트림에 서비스로 Adobe Experience Platform 추가](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. 다음 표를 사용하여 Customer Journey Analytics에서 계속 사용할 Adobe Analytics 기능을 식별한 다음 제공된 정보를 사용하여 Customer Journey Analytics 업그레이드의 일부로 해당 기능을 구성하는 방법을 알아보십시오.

   | Adobe Analytics 기능 | Customer Journey Analytics을 위한 구현 요구 사항 | 추가 정보 |
   |---------|----------|---------|
   | 분류 데이터 | 분류 데이터를 포함하는 각 차원에 대한 조회 데이터 세트를 만듭니다. |  |
   | 마케팅 채널 | 마케팅 채널 파생 필드를 만듭니다. |  |
   | Activity Map 오버레이 및 링크 추적 | 해당 사항 없음 | Adobe은 현재 Customer Journey Analytics에 대한 Activity Map 오버레이 지원을 작업 중입니다. |
   | 데이터 피드 | 구현 중에 구성이 필요하지 않습니다.<br/>[Customer Journey Analytics의 다양한 내보내기 옵션에 대해 알아봅니다](/help/analysis-workspace/export/export-project-overview.md). | Customer Journey Analytics에서 데이터 피드에 대한 직접 대체를 아직 사용할 수 없지만 Analysis Workspace에서 Customer Journey Analytics 보고서를 내보내 타사 도구에서 사용하거나 외부 데이터와 결합할 수 있습니다. |
   | Data Warehouse | 구현 중에 구성이 필요하지 않습니다.<br/>[Customer Journey Analytics의 전체 테이블 내보내기에 대해 알아봅니다](/help/analysis-workspace/export/export-cloud.md). | Customer Journey Analytics 전체 테이블 내보내기는 Adobe Analytics에서 Data Warehouse 보고서가 발전한 것이며 현재 Data Warehouse에서 사용할 수 없는 많은 새로운 자주 요청하는 기능이 추가되었습니다. |
   | 스트리밍 미디어 데이터 |  |  |

1. (선택 사항) Analytics 소스 커넥터를 사용하여 Adobe Analytics에서 내역 데이터를 가져옵니다.

   자세한 내용은 [소스 커넥터를 사용하여 데이터 수집 및 사용](/help/data-ingestion/sources.md)에서 [소스 커넥터 사용](/help/data-ingestion/sources.md#use-a-source-connector)을 참조하세요.

1. 다음 표를 사용하여 원하는 Customer Journey Analytics 기능을 식별한 다음 제공된 정보를 사용하여 Customer Journey Analytics 업그레이드의 일부로 해당 기능을 구성하는 방법을 알아보십시오.

   | 원하는 Customer Journey Analytics 기능 | Customer Journey Analytics을 위한 구현 요구 사항 | 추가 정보 |
   |---------|----------|---------|
   | 웹 데이터를 콜 센터 데이터와 같은 다른 채널의 데이터와 연결 | 연결을 만든 후(이후 단계에서 설명) Customer Journey Analytics에서 연결에 추가 데이터 세트를 추가합니다. |  |
   | RTCDP와 통합 | 스키마에서 프로필 활성화 및 RTCDP에서 사용할 프로필 데이터 세트 만들기 | 이 작업은 XDM 스키마를 생성하는 동안 수행해야 합니다. |
   | Adobe Journey Optimizer과 통합 | Adobe Journey Optimizer에서 사용하려면 구현의 개인화 개체를 사용하십시오 |  |

1. 원하는 Customer Journey Analytics 구현을 설명하는 섹션을 확장한 다음 관련 단계를 완료합니다.

   +++수동 구현(JS 파일)

   1. [사이트에 alloy.js 추가](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

+++

   +++태그

   1. [Adobe Experience Platform 데이터 수집에서 태그 속성을 만듭니다](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/quick-start#create-a-property).

+++

+++ API

   1. Edge Network API를 사용하여 데이터를 원하는 데이터 스트림으로 전송합니다.

+++

1. [Customer Journey Analytics에 연결을 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. [Customer Journey Analytics에서 데이터 보기를 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [데이터가 Customer Journey Analytics으로 흘러가고 있는지 확인](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [프로젝트 및 구성 요소 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

1. 이전 구현의 데이터와 새 구현의 데이터를 비교하고, 차이점과 차이점이 존재하는 이유를 이해해야 합니다.

1. 사용자 온보딩을 계획합니다.

   Adobe Analytics와 마찬가지로 Analysis Workspace는 Customer Journey Analytics의 주요 사용자 대상 도구입니다. 단, Customer Journey Analytics에서 Analysis Workspace를 사용할 때 사용자가 알아 두어야 할 몇 가지 주요 차이점이 있습니다.

   사용자가 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점을 숙지할 수 있도록 충분한 시간(3~6개월)을 할애하도록 하십시오.

   Adobe Analytics와 Customer Journey Analytics의 주요 차이점에 대한 자세한 내용은 [Adobe Analytics 사용자를 위한 사용 안내서](/help/getting-started/aa-to-cja-user.md)를 참조하십시오.

1. AppMeasurement 데이터 수집을 비활성화합니다.

1. Analytics 소스 커넥터를 비활성화합니다.

   Experience Platform Web SDK 구현을 사용하면 내역 Adobe Analytics 데이터에 대해서만 Analytics 소스 커넥터가 필요하며 원래 구현의 데이터를 새 구현의 데이터와 비교합니다.

   새 구현의 내역 데이터가 충분하고 Customer Journey Analytics의 보고 차이점에 익숙할 경우 Analytics 소스 커넥터를 꺼야 합니다.

## 조직에 대한 업그레이드 단계를 동적으로 생성

타임라인 및 리소스 제한과 같은 여러 요인에 따라 [권장 업그레이드 단계 이해](#1-understand-the-recommended-upgrade-steps)에 설명된 권장 업그레이드 단계가 조직에 실용적이지 않을 수 있습니다.

조직의 고유 환경에 대한 업그레이드 단계를 동적으로 생성하려면 다음을 수행합니다.

1. [Adobe Analytics에서 업그레이드 Customer Journey Analytics 설문지](https://gigazelle.github.io/cja-ttv/)를 작성합니다.

   이 설문지를 작성한 후 조직 요구 사항에 맞는 최적의 업그레이드 단계를 요약한 단계별 지침이 제공됩니다. 기존 Adobe Analytics 환경 및 Customer Journey Analytics 목표에 가장 적합한 업그레이드 단계입니다.

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









