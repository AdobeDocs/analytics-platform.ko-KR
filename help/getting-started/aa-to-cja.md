---
title: Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션
description: Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션하는 단계
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 2a330a430b48eb753d269e1165e95b61cb5fb483
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 5%

---

# Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션 준비

데이터를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션하기 전에 이러한 고려 사항을 살펴보고 데이터를 준비하며 두 기술 간의 중요한 차이점을 파악하십시오.

## 데이터 준비

Adobe Analytics 데이터를 준비하여 Customer Journey Analytics으로 원활하게 이동할 수 있다면 데이터 무결성 및 보고 일관성을 유지하는 데 매우 중요합니다.

### 1. ID 수집

고객 여정을 이해하는 데 가장 중요한 구성 요소는 각 단계에서 고객이 누구인지를 파악하는 것입니다. Customer Journey Analytics의 경우, 모든 채널에 있는 식별자와 해당 데이터에 대한 식별자가 있으면 CJA 내에서 여러 소스를 함께 결합할 수 있습니다.
ID의 예로는 고객 ID, 계정 ID 또는 이메일 ID가 있을 수 있습니다. ID(및 여러 ID가 있을 수 있음)가 무엇이든 각 ID에 대해 다음 사항을 고려해야 합니다.

* ID가 존재하거나 CJA로 가져올 모든 데이터 소스에 추가할 수 있습니다
* ID는 데이터의 각 행에 채워집니다
* ID에 PII가 없습니다. 민감할 수 있는 모든 항목에 해시를 적용합니다.
* ID는 모든 소스(동일한 길이, 동일한 해시 메서드 등)에서 동일한 형식을 사용합니다.

Adobe Analytics과 같은 데이터 세트에서 ID는 모든 데이터 행에 존재하지 않을 수 있지만 보조 ID는 존재할 수 있습니다. 이 경우 고객이 ECID로만 식별되고 ID가 수집될 때(예: 고객이 인증을 받을 때) 크로스 채널 분석(이전의 &quot;필드 기반 결합&quot;이라고 함)을 사용하여 행 간 간격을 연결할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=ko-KR)

### 2. 변수 정렬

Adobe Analytics 데이터를 Customer Journey Analytics으로 가장 간단한 마이그레이션은 [Adobe Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko-KR). 이 커넥터는 Adobe Analytics 변수를 AEP의 XDM 스키마 및 데이터 세트에 직접 매핑하며 CJA에 쉽게 연결할 수 있습니다.

전체 글로벌 보고서 세트가 항상 구현에 적합하지 않을 수 있습니다. 여러 보고서 세트를 Customer Journey Analytics으로 가져오려는 경우, 해당 보고서 세트에 변수를 일치시킬 계획을 세워야 합니다.

예를 들어 보고서 세트 1의 eVar1은 [!UICONTROL 페이지]를 지정할 수 있습니다. 보고서 세트 2에서 eVar 1은 [!UICONTROL 내부 캠페인]. CJA로 가져오면 이러한 변수가 단일 eVar1 차원으로 혼합되어 혼동을 일으킬 수 있고 부정확한 보고가 생성됩니다.

관련 문제로 인해 글로벌 보고서 세트로 이동하지 않은 경우 [!UICONTROL 고유 수가 초과되었습니다.] 또는 [!UICONTROL 낮은 트래픽]: CJA에는 [차원의 카디널리티 제한](/help/components/dimensions/high-cardinality.md). 이렇게 하면 모든 고유 값이 표시되고 카운트될 수 있습니다.

### 3. (Re) 마케팅 채널 구성

기존 Adobe Analytics 마케팅 채널 설정은 CJA에서 동일하게 수행되지 않습니다. 이유는 두 가지가 있습니다.

* Adobe Experience Platform에 수집된 Adobe Analytics 데이터의 처리 수준입니다.

* Customer Journey Analytics의 보고서 시간 특성

Adobe이 게시됨 [마케팅 채널 구현에 대한 모범 사례를 업데이트했습니다](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=en). 이러한 업데이트된 권장 사항은 Attribution IQ에서 이미 사용 중인 기능을 최대한 활용할 수 있도록 도와줍니다. 또한 Customer Journey Analytics으로 전환할 때 성공을 설정하게 됩니다.

### 4. Analytics 소스 커넥터와 Experience Platform SDK의 사용을 결정합니다

로서의 [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 데이터 수집이 발전하면 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=en) 또는 [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=en) Adobe Experience Platform Edge Network와 함께 사용할 수 있습니다. 일반적인 SDK 구현에서는 데이터를 Adobe Analytics으로 전송하지만 새로운 기회는 Adobe Experience Platform으로 직접 데이터를 전송할 수 있는 기회를 제공합니다. 그런 다음 Adobe Analytics에 전송된 데이터를 유지하는 동시에 Customer Journey Analytics에 수집할 수 있습니다.

이 메서드는 데이터 수집에 대한 가능성을 크게 확장합니다. 더 이상 필드 수에 제한이 없거나 데이터 요소를 Analytics와 같은 prop, eVar 및 이벤트에 매핑할 필요가 없습니다. 다양한 유형의 무제한 스키마 요소를 사용하고 CJA를 사용하여 여러 가지 방법으로 나타낼 수 있습니다 [데이터 보기](/help/data-views/data-views.md). Adobe Analytics을 통한 데이터 처리 시간이 제거되어 Adobe Experience Platform으로 바로 전송될 때 데이터 가용성 속도가 증가합니다.

**Experience Platform SDK를 사용할 때의 이점**

* 필요한 필드를 정의하는 유연한 스키마
* Adobe Analytics 명명법(prop, eVar, 이벤트 등)에 의존하지 않음
* 문자 제한 문제 없음(prop의 경우 100자)
* Adobe Experience Platform의 신속한 데이터 가용성

**Experience Platform SDK 사용의 단점**

다음 Adobe Analytics 구성 요소는 지원되지 않습니다.

* 마케팅 채널
* 보트 필터링
* 지역, 도메인, 장치 조회
* Analytics for Target (A4T)

## 중요한 차이점 준비

### 보고서 처리 시간 편이성

Adobe Analytics의 보고는 상당한 양의 데이터 사전 처리를 사용하여 eVar에 표시되는 지속성과 같은 결과를 생성합니다. Customer Journey Analytics은 보고서 실행 시 이러한 계산을 실행합니다.

보고서 처리 시간을 사용하면 기본 데이터 수집 방법을 변경하지 않고도 소급 적용되는 설정을 적용하고 여러 버전의 변수 지속성을 만들 수 있습니다.

이 변경으로 인해 특히 긴 만료 기간이 있는 변수의 경우 데이터 보고 방식에 일부 차이가 발생합니다. 보고서 시간 처리가 보고서를 사용하여 보고에 미치는 영향을 평가하는 것으로 시작할 수 있습니다 [가상 보고서 세트](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html).

### 중요 세그먼트 및 계산된 지표 식별

Adobe Analytics 세그먼트(CJA에서 필터라고 함) 및 계산된 지표는 Customer Journey Analytics과 호환되지 않습니다. 대부분의 경우 이러한 구성 요소를 사용 가능한 새로운 스키마 및 데이터를 사용하여 CJA에서 다시 빌드할 수 있습니다.

사용자가 시스템 간을 전환할 때 최대한 원활한 전환을 수행하려면 다음을 계획하십시오

1. 이러한 구성 요소에서 가장 중요한 요소 식별

1. 정의 및

1. CJA에서 이를 복제하는 데 필요한 필드 식별 [필터](/help/components/filters/filters-overview.md) 및 [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md).

다음은 안내하는 비디오 두 가지 목록입니다.

* [Adobe Analytics 세그먼트를 Customer Journey Analytics으로 이동](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en)

* [계산된 지표를 Adobe Analytics에서 Customer Journey Analytics로 이동](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)
