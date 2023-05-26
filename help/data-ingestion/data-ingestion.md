---
title: 데이터 수집 개요
description: 데이터를 Customer Journey Analytics로 수집할 수 있는 다양한 방법 이해
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 96%

---

# 데이터 수집 개요

데이터를 Customer Journey Analytics로 수집하는 방법은 여러 가지가 있습니다. 일부 고객은 기존 Adobe Analytics 데이터를 이전하려는 것으로 간주하며 일부는 Adobe Experience Platform로 수집된 데이터를 사용한다고 가정합니다.

>[!IMPORTANT]
>
>모든 시나리오에서, Customer Journey Analytics에 _사용_&#x200B;하려는 데이터는 실제로 Adobe Experience Platform에서 _수집_&#x200B;됩니다.


앞 [개요](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ko)에 표시된 높은 수준의 Customer Journey Analytics 아키텍처를 참조하십시오.

![Customer Journey Analytics](./assets/cja-architecture.png)

위 아키텍처의 데이터 세트는 다음의 다양한 소스에서 가져올 수 있습니다.

- 배치 데이터,

- 스트리밍 데이터,

- 현재 Adobe Analytics 배포 데이터,

- Adobe Experience Platform Web/Mobile SDK를 사용하는 웹 사이트/모바일 앱 추적 데이터 또는

- Adobe가 소스 커넥터를 제공하는 서드파티 데이터 제공업체의 데이터.

이러한 데이터 세트가 많을 수 있습니다.

설명서의 이 섹션에서는 다양한 시나리오에 대한 빠른 시작 안내서를 제공합니다.

## 기존 Adobe Analytics에서 데이터 수집 및 사용

이미 Adobe Analytics를 배포했으며, Adobe Experience Platform에서 이 데이터를 수집하고 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석하려고 합니다.

자세한 내용은 [기존 Adobe Analytics에서 데이터 수집 및 사용](./analytics.md)을 참조하십시오.

## Adobe Experience Platform Web SDK 및 Edge Network를 통해 데이터 수집 및 사용

Adobe 기술을 사용하여 웹 사이트를 분석하거나 다른 솔루션에서 마이그레이션하거나 사용자의 행동을 추적할 수 있습니다. Adobe Experience Platform SDK 및 Edge Network를 사용하는 Adobe의 구현 모범 사례에 따라 데이터를 수집하려고 합니다. 그런 다음 수집된 데이터를 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석할 수 있습니다.

자세한 내용은 [Adobe Experience Platform Web SDK 및 Edge Network를 통해 데이터 수집 및 사용](./aepwebsdk.md)을 참조하십시오.

## 배치 데이터 수집 및 사용

고객 행동을 더 잘 파악하고 고객 상호 작용을 분석하는 데 도움이 되는 세부 정보를 제공하는 관련 배치 데이터를 사용할 수 있습니다. 이러한 배치 데이터의 예는 CRM 시스템, 로열티 애플리케이션 또는 Adobe에서 현재 소스 커넥터를 제공하지 않는 기타 솔루션의 CSV, JSON 또는 Parquet 형식의 플랫 파일입니다. 이 배치 데이터를 Adobe Experience Platform으로 수집하여 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석할 수 있습니다.

자세한 내용은 [배치 데이터 수집 및 사용](./batch.md)을 참조하십시오.

## 스트리밍 데이터 수집 및 사용

고객 행동을 더 잘 파악하고 고객 상호 작용을 분석하는 데 도움이 되는 세부 정보를 제공하는 CRM 시스템, ERP 시스템 또는 다른 소스와 같은 관련 데이터 소스를 사용할 수 있습니다. 해당 데이터 소스는 Adobe에서 현재 소스 커넥터를 제공하지 않는 HTTP 또는 공용 클라우드 스트리밍 인프라를 통해 통신할 수 있습니다. 이 스트리밍 데이터를 Adobe Experience Platform으로 실시간 수집하여 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석할 수 있습니다.

자세한 내용은 [스트리밍 데이터 수집 및 사용](./streaming.md)을 참조하십시오.

## 소스 커넥터를 사용하여 데이터 수집 및 사용

소스 커넥터에서 지원하는 소스의 데이터를 사용할 수 있습니다. 소스 커넥터는 Adobe, 퍼스트 파티 및 서드파티 애플리케이션의 데이터를 Adobe Experience Platform으로 수집할 수 있는 구성 가능한 구성입니다. 사용 가능한 소스 커넥터의 개요는 [소스 커넥터 개요](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ko)를 참조하십시오. 소스 커넥터를 사용하여 소스의 데이터를 Adobe Experience Platform으로 쉽게 수집한 다음 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석할 수 있습니다.

자세한 내용은 [소스 커넥터를 사용하여 데이터 수집 및 사용](./sources.md)을 참조하십시오.
