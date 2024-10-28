---
title: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# Adobe Analytics에서 Customer Journey Analytics으로 업그레이드

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드 프로세스를 시작하기 전에 먼저 권장되는 업그레이드 단계를 이해합니다.

타임라인 및 리소스 제한과 같은 여러 요인에 따라 권장되는 업그레이드 단계가 조직에 실용적이지 않을 수 있습니다. 권장되는 업그레이드 단계를 이해한 후 설문지를 완료하여 조직의 고유 상황에 맞는 업그레이드 단계를 동적으로 생성합니다.

## 1. 권장되는 업그레이드 단계 이해

>[!NOTE]
>
>이 섹션에 설명된 업그레이드 단계는 모든 조직이 Adobe Analytics에서 Customer Journey Analytics으로 성공적으로 업그레이드하는 데 사용할 수 있는 권장 업그레이드 단계입니다.
>
>그러나 타임라인 및 리소스 제한과 같은 여러 요인에 따라 권장되는 업그레이드 단계가 조직에 실용적이지 않을 수 있습니다. 권장되는 업그레이드 단계를 이해하면 [Adobe Analytics 업그레이드 Customer Journey Analytics 설문지](https://gigazelle.github.io/cja-ttv/)를 작성하여 조직의 고유한 환경에 맞는 업그레이드 단계를 동적으로 생성하십시오.

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 단계는 Customer Journey Analytics에 기본 데이터 수집 방법인 Experience Platform Web SDK의 새로운 구현입니다. Web SDK와 함께 Adobe에서는 내역 Adobe Analytics 데이터를 유지하고 병렬 데이터 비교를 수행하려면 Analytics 소스 커넥터를 사용하는 것이 좋습니다.

Customer Journey Analytics으로 완전히 전환하면 Analytics 소스 커넥터를 끄고 Experience Platform Web SDK를 독점적으로 사용할 수 있습니다.

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

## 2. 조직에 대한 업그레이드 단계를 동적으로 생성

타임라인 및 리소스 제한과 같은 여러 요인에 따라 [권장 업그레이드 단계 이해](#1-understand-the-recommended-upgrade-steps)에 설명된 권장 업그레이드 단계가 조직에 실용적이지 않을 수 있습니다.

조직의 고유 상황에 맞게 동적으로 생성된 업그레이드 단계를 보려면 다음과 같이 하십시오.

1. [Adobe Analytics에서 업그레이드 Customer Journey Analytics 설문지](https://gigazelle.github.io/cja-ttv/)를 작성합니다.

   이 설문지를 작성한 후, 조직에 고유한 최적의 업그레이드 단계를 요약한 단계별 지침이 제공됩니다. 기존 Adobe Analytics 환경 및 Customer Journey Analytics 목표에 가장 적합한 업그레이드 단계입니다.

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









