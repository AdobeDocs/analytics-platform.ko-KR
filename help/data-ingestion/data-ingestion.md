---
title: 데이터 수집 개요
description: 데이터를 Customer Journey Analytics로 수집할 수 있는 다양한 방법 이해
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 5de8c0daaa7eea0a9ab993d256e2b0a14f37301e
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 7%

---


# 데이터 수집 개요

데이터를 Customer Journey Analytics로 수집하는 방법은 여러 가지가 있습니다. 일부 고객은 기존 Adobe Analytics 데이터를 이전하려는 것으로 간주하며 일부는 Adobe Experience Platform으로 직접 수집된 데이터를 사용한다고 가정합니다.

>[!IMPORTANT]
>
>모든 시나리오에서 원하는 데이터 _사용_ Customer Journey Analytics에서 는 실제로 _수집된 항목_ Adobe Experience Platform.


의 앞부분에 표시된 고급 Customer Journey Analytics 아키텍처를 참조하십시오. [개요](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en):

![고객 여정 분석](./assets/cja-architecture.png)

위의 아키텍처의 데이터 세트는 다양한 소스에서 발생할 수 있습니다. 일괄 데이터, 스트리밍 데이터, 현재 Adobe Analytics 배포의 데이터, Adobe Experience Platform Web/Mobile SDK를 사용하여 웹 사이트/모바일 앱을 추적함으로써 얻은 데이터 또는 Adobe이 소스 커넥터를 제공하는 타사 데이터 공급자로부터 받은 데이터. 이러한 데이터 세트 중 많은 수를 사용할 수 있습니다.

설명서의 이 섹션에서는 다양한 시나리오에 대한 빠른 시작 안내서를 제공합니다.

## 기존 Adobe Analytics에서 데이터 수집 및 사용

이미 Adobe Analytics을 배포했으며 이 데이터를 Adobe Experience Platform에서 수집하고 Customer Journey Analytics의 다른 채널 및 데이터 소스의 데이터와 함께 사용, 결합 및 분석하려고 합니다.

자세한 내용은 [기존 Adobe Analytics에서 데이터 수집 및 사용](./analytics.md) 추가 정보.

## Adobe Experience Platform Web SDK 및 Edge 네트워크를 통해 데이터 수집 및 사용

Adobe 기술을 사용하여 웹 사이트를 분석하고 다른 솔루션에서 마이그레이션하거나 방문자의 행동을 추적하려고 합니다. Adobe Experience Platform SDK 및 Edge Network를 사용하는 구현에 대한 Adobe의 우수 사례를 따라 데이터를 수집하려는 경우 그런 다음 수집된 데이터를 Customer Journey Analytics의 다른 채널 및 데이터 소스의 데이터와 사용, 결합 및 분석할 수 있습니다.

자세한 내용은 [Adobe Experience Platform Web SDK 및 Edge 네트워크를 통해 데이터 수집 및 사용](./aepwebsdk.md) 추가 정보.

## 배치 데이터 수집 및 사용

고객 행동을 더 잘 이해하고 고객 상호 작용을 분석하는 데 도움이 되는 세부 정보를 제공하는 관련 배치 데이터를 사용할 수 있습니다. 이러한 배치 데이터의 예로는 CRM 시스템의 CSV, JSON 또는 Parquet 형식으로 작성된 플랫 파일, 충성도 애플리케이션 또는 Adobe에서 현재 소스 커넥터를 제공하지 않는 다른 솔루션의 플랫 파일이 있습니다. 이 일괄 처리 데이터를 Adobe Experience Platform에 섭취하면 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터를 사용, 결합 및 분석할 수 있습니다.

자세한 내용은 [배치 데이터 수집 및 사용](./batch.md) 추가 정보.

## 스트리밍 데이터 수집 및 사용

CRM 시스템, ERP 시스템 또는 기타 소스와 같은 관련 데이터 소스가 있으며, 이러한 데이터 소스를 통해 고객 행동을 더 잘 이해하고 고객 상호 작용을 분석할 수 있습니다. 해당 데이터 소스는 HTTP 또는 공용 클라우드 스트리밍 인프라를 통해 통신할 수 있지만 Adobe에서 현재 소스 커넥터를 제공하지 않습니다. 이 스트리밍 데이터를 실시간으로 Adobe Experience Platform에 섭취하면 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터를 사용, 결합 및 분석할 수 있습니다.

자세한 내용은 [스트리밍 데이터 수집 및 사용](./streaming.md) 추가 정보.

## 소스 커넥터를 사용하여 데이터 수집 및 사용

소스 커넥터에서 지원하는 소스에서 사용할 수 있는 데이터가 있습니다. 소스 커넥터는 Adobe, 자사 및 타사 애플리케이션에서 Adobe Experience Platform으로 데이터를 수집할 수 있는 구성 가능한 구성입니다. 자세한 내용은 [소스 커넥터 개요](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ko-KR) 사용 가능한 소스 커넥터에 대한 개요입니다. 소스 커넥터를 사용하여 소스의 데이터를 Adobe Experience Platform으로 쉽게 수집한 다음 Customer Journey Analytics의 다른 채널 및 데이터 소스의 데이터를 사용, 결합 및 분석할 수 있습니다.

자세한 내용은 [소스 커넥터를 사용하여 데이터 수집 및 사용](./sources.md) 추가 정보.

