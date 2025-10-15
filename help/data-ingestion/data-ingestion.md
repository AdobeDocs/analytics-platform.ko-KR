---
title: 데이터 수집 개요
description: 데이터를 Customer Journey Analytics로 수집할 수 있는 다양한 방법 이해
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: ec56bc657961b2e4e8318ab14cd676288398462f
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 100%

---

# 데이터 수집 개요

데이터를 Customer Journey Analytics로 수집하는 방법은 여러 가지가 있습니다. 일부 고객은 기존 Adobe Analytics 데이터를 이전하려는 것으로 간주하며 일부는 Adobe Experience Platform로 수집된 데이터를 사용한다고 가정합니다.

>[!IMPORTANT]
>
>모든 시나리오에서 Customer Journey Analytics에 _사용_&#x200B;하려는 데이터는 실제로 Adobe Experience Platform에서 _수집_&#x200B;됩니다.


다음은 높은 수준의 Customer Journey Analytics 아키텍처입니다.

![고객 여정 분석 아키텍처](/help/getting-started/assets/cja-overview.svg)

이 아키텍처는 고객 여정 분석을 통해 다음 작업을 수행하는 방법을 보여줍니다.

* [연결](/help/connections/overview.md)에서 여러 ![Data](/help/assets/icons/Data.svg) 데이터 세트를 결합합니다.
* 연결에서 정의한 데이터 세트에서 사용할 수 있는 필드를 기반으로 하여 [데이터 보기](/help/data-views/data-views.md)에서 ![Dimensions](/help/assets/icons/Dimensions.svg) 차원 및 ![Event](/help/assets/icons/Event.svg) 지표를 정의하고 구성합니다.
* 데이터 보기의 차원 및 지표를 기반으로 하여 [프로젝트](/help/analysis-workspace/home.md)에서 ![ViewTable](/help/assets/icons/ViewTable.svg) 보고서 및 시각화(예: ![Line](/help/assets/icons/GraphTrend.svg) 라인 및 ![Area](/help/assets/icons/GraphAreaStacked.svg) 영역)를 빌드합니다.

아키텍처의 데이터 세트는 다음의 다양한 소스에서 가져올 수 있습니다.

* 배치 데이터,

* 스트리밍 데이터,

* 현재 Adobe Analytics 배포 데이터,

* Adobe Experience Platform Web/Mobile SDK를 사용하는 웹 사이트/모바일 앱 추적 데이터,

* Adobe Experience Platform Edge Network Server API를 사용하여 데스크탑 애플리케이션, 콘솔 게임, 셋톱박스 또는 IoT 디바이스를 추적하여 얻은 데이터 또는

* Adobe가 소스 커넥터를 제공하는 서드파티 데이터 제공업체의 데이터.

이러한 데이터 세트가 많을 수 있습니다.

설명서의 이 섹션에서는 다양한 시나리오에 대한 빠른 시작 안내서를 제공합니다.

## 수집 우선순위 지정 및 지연

데이터가 24시간인지, 48시간인지 또는 7일인지 여부에 관계없이 90분(SLT) 이내에 Customer Journey Analytics에서 이벤트 데이터를 수집할 수 있습니다.

이 기능은 회사에서 구입한 SKU 패키지에 따라 다릅니다.

* 우선순위 수집 기본: 90분 내 24시간 이전 데이터 SLT 처리 (**CJA Foundation** 및 **CJA Select**&#x200B;에 사용 가능)

* 우선순위 수집 중간: 90분 내 72시간 이전 데이터 SLT 처리 (**CJA Prime**&#x200B;에 사용 가능)

* 우선순위 수집 고급: 90분 내 1주 전 데이터 SLT 처리 (**CJA Ultimate**&#x200B;에서 사용 가능)

## 기존 Adobe Analytics에서 데이터 수집 및 사용

이미 Adobe Analytics를 배포했으며, Adobe Experience Platform에서 이 데이터를 수집하고 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석하려고 합니다.

자세한 내용은 [기존 Adobe Analytics에서 데이터 수집 및 사용](./analytics.md)을 참조하십시오.


## Edge Network를 통해 데이터 수집 및 사용

### Adobe Experience Platform Web SDK 사용

Adobe 기술을 사용하여 웹 사이트를 분석하고, 잠재적으로 다른 솔루션에서 마이그레이션하거나 사용자 행동 추적을 시작하려고 합니다. Adobe Experience Platform SDK 및 Edge Network를 사용하는 Adobe의 구현 모범 사례에 따라 데이터를 수집하려고 합니다. 그런 다음 수집된 데이터를 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석할 수 있습니다.

자세한 내용은 [Adobe Experience Platform Web SDK를 통해 데이터 수집 및 사용](./aepwebsdk.md)을 참조하십시오.

### Adobe Experience Platform Mobile SDK 사용

Adobe 기술을 사용하여 모바일 앱을 분석하고, 잠재적으로 다른 솔루션에서 마이그레이션하거나 사용자 행동 추적을 시작하려고 합니다. Adobe Experience Platform SDK 및 Edge Network를 사용하는 Adobe의 구현 모범 사례에 따라 데이터를 수집하려고 합니다. 그런 다음 수집된 데이터를 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석할 수 있습니다.

자세한 내용은 [Adobe Experience Platform Mobile SDK를 통해 데이터 수집 및 사용](./aepmobilesdk.md)을 참조하십시오.

### Adobe Experience Platform Edge Network Server API 사용

Adobe 기술을 사용하는 데스크탑 애플리케이션, 게임 콘솔에서 플레이되는 게임, 셋톱박스에서 비디오 스트리밍 애플리케이션 사용 또는 IoT 디바이스를 분석하려고 합니다. 잠재적으로 다른 솔루션에서 마이그레이션하거나 이들 디바이스에서 사용자 행동 추적을 시작하려고 합니다. Adobe Experience Platform Edge Network Server API 및 Edge Network를 사용하는 Adobe의 구현 모범 사례에 따라 데이터를 수집하려고 합니다. 그런 다음 수집된 데이터를 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석할 수 있습니다.

자세한 내용은 [Adobe Experience Platform Edge Network Server API를 통해 데이터 수집 및 사용](./serverapi.md)을 참조하십시오.

## 배치 데이터 수집 및 사용

고객 행동을 더 잘 파악하고 고객 상호 작용을 분석하는 데 도움이 되는 세부 정보를 제공하는 관련 배치 데이터를 사용할 수 있습니다. 이러한 배치 데이터의 예는 CRM 시스템, 로열티 애플리케이션 또는 Adobe에서 현재 소스 커넥터를 제공하지 않는 기타 솔루션의 CSV, JSON 또는 Parquet 형식의 플랫 파일입니다. 이 배치 데이터를 Adobe Experience Platform으로 수집하여 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석할 수 있습니다.

자세한 내용은 [배치 데이터 수집 및 사용](./batch.md)을 참조하십시오.

## 스트리밍 데이터 수집 및 사용

고객 행동을 더 잘 파악하고 고객 상호 작용을 분석하는 데 도움이 되는 세부 정보를 제공하는 CRM 시스템, ERP 시스템 또는 다른 소스와 같은 관련 데이터 소스를 사용할 수 있습니다. 해당 데이터 소스는 Adobe에서 현재 소스 커넥터를 제공하지 않는 HTTP 또는 공용 클라우드 스트리밍 인프라를 통해 통신할 수 있습니다. 이 스트리밍 데이터를 Adobe Experience Platform으로 실시간 수집하여 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석할 수 있습니다.

자세한 내용은 [스트리밍 데이터 수집 및 사용](./streaming.md)을 참조하십시오.

## 소스 커넥터를 사용하여 데이터 수집 및 사용

소스 커넥터에서 지원하는 소스의 데이터를 사용할 수 있습니다. 소스 커넥터는 Adobe, 퍼스트 파티 및 서드파티 애플리케이션의 데이터를 Adobe Experience Platform으로 수집할 수 있는 구성 가능한 구성입니다. 사용 가능한 소스 커넥터의 개요는 [소스 커넥터 개요](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ko)를 참조하십시오. 소스 커넥터를 사용하여 소스의 데이터를 Adobe Experience Platform으로 쉽게 수집한 다음 Customer Journey Analytics에서 다른 채널 및 데이터 소스의 데이터로 사용하고, 결합하고, 분석할 수 있습니다.

자세한 내용은 [소스 커넥터를 사용하여 데이터 수집 및 사용](./sources.md)을 참조하십시오.

## 애드 혹 데이터 수집 및 사용

Experience Platform에서 단일 데이터 세트만 필요하며 XDM(경험 데이터 모델) 스키마를 구성할 필요가 없는 애드 혹 데이터를 사용할 수 있습니다. 이 시나리오를 애드 혹 스키마라고 합니다. 애드혹 스키마는 CSV 파일 수집 및 특정 종류의 소스 연결 생성을 포함하여 Experience Platform의 다양한 데이터 수집 워크플로에 사용됩니다.

[애드 혹 데이터 수집 및 사용](./adhoc.md)을 참조하십시오.

>[!MORELIKETHIS]
>
>블로그: [Adobe Customer Journey Analytics의 데이터 처리 및 수집에 대한 자세한 내용](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-closer-look-at-data-processing-amp-ingestion-in-adobe-customer/ba-p/665091?profile.language=ko)

