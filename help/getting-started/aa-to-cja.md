---
title: Adobe Analytics의 발전
description: Adobe Analytics 데이터를 Customer Journey Analytics 데이터로 변환하는 단계
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 37d9e8e84e1982d63f2173601d75f0b7fa552b73
workflow-type: tm+mt
source-wordcount: '1495'
ht-degree: 93%

---

# Adobe Analytics의 발전

조직이 Customer Journey Analytics을 사용하기 위해 진화할 때 이러한 단계를 통해 데이터를 준비하고 두 기술 간의 중요한 차이점을 파악하십시오. 이 문서는 관리자 대상자를 대상으로 합니다.

## 데이터 준비

Customer Journey Analytics로의 원활한 이전을 위해 Adobe Analytics 데이터를 준비하는 것은 데이터 무결성 및 보고 일관성에 중요합니다.

### 1. ID 수집 {#identities}

고객 여정을 이해하는 데 가장 중요한 요소는 각 단계에서 고객을 파악하는 것입니다. Customer Journey Analytics의 경우 모든 채널에 존재하는 식별자와 해당 데이터를 사용하면 Customer Journey Analytics 내에서 여러 소스를 결합할 수 있습니다.
ID의 예로는 고객 ID, 계정 ID 또는 이메일 ID가 있습니다. ID의 종류(하나 이상 보유할 수 있음)가 무엇이든 각 ID에 대해 다음과 같은 사항을 고려해야 합니다.

* ID가 존재하거나 Customer Journey Analytics로 가져오려는 모든 데이터 소스에 추가할 수 있습니다.
* 데이터의 각 행에 ID가 채워집니다.
* 아이디에 PII(사용자 식별 정보)는 포함되지 않습니다. 민감할 수 있는 모든 항목에 해싱을 적용합니다.
* ID는 모든 소스에서 동일한 형식(동일한 길이, 동일한 해시 방법 등)을 사용합니다.

Adobe Analytics와 같은 데이터 세트에서 ID는 모든 데이터 행에 존재하지 않을 수 있지만 보조 ID는 존재합니다. 이 경우, 고객이 ECID를 통해서만 식별되고 ID가 수집되는 경우(예: 고객 인증 시) 교차 채널 분석(“결합”이라고도 함)을 사용하여 행 간의 간격을 메울 수 있습니다. [자세히 알아보기](../stitching/overview.md)

### 2. 변수 정렬 {#variables}

Analytics 데이터를 Customer Journey Analytics 데이터로 변환하는 가장 간단한 방법은 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko-KR)를 사용하여 [글로벌 보고서 세트](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=ko-KR)를 Experience Platform으로 수집하는 것입니다. 이 커넥터는 Adobe Analytics 변수를 Experience Platform의 XDM 스키마 및 데이터 세트에 직접 매핑하므로 Customer Journey Analytics에 쉽게 연결할 수 있습니다.

전체 글로벌 보고서 세트가 항상 구현 가능한 것은 아닙니다. 여러 보고서 세트를 Customer Journey Analytics으로 가져오려는 경우 두 가지 옵션이 있습니다.

* 변수를 해당 보고서 세트 간에 정렬하도록 계획하십시오. 예를 들어 보고서 세트 1의 eVar1은 [!UICONTROL 페이지]를 지정할 수 있습니다. 보고서 세트 2의 eVar1은 [!UICONTROL 내부 캠페인]를 지정할 수 있습니다. Customer Journey Analytics로 가져오면 이들 변수가 단일 eVar1 차원으로 혼합되어 정확하지 않으며 혼동을 주는 보고를 초래할 수 있습니다.

* [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko-KR) 기능을 사용하여 변수를 매핑합니다. 모든 보고서 세트가 동일한 공통 변수 설계를 사용하는 경우 더 쉬워지지만 새로운 Experience Platform [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko-KR#mapping) 기능을 사용하는 경우에는 필요하지 않습니다. 이 옵션을 사용하면 데이터 스트림 (또는 속성) 수준에 있는 매핑된 값별로 변수를 참조할 수 있습니다.

[!UICONTROL 고유 수 초과] 또는 [!UICONTROL 낮은 트래픽] 문제로 인해 글로벌 보고서 세트로 이동하는 데 불편을 겪었다면 Customer Journey Analytics에는 [차원에 대한 카디널리티 제한](/help/components/dimensions/high-cardinality.md)이 없습니다. 이를 통해 고유 값을 표시하고 계산할 수 있습니다.

다음은 [보고서 세트를 다른 스키마와 결합](/help/use-cases/aa-data/combine-report-suites.md)하는 사용 사례입니다.

### 3. 마케팅 채널 (재)구성 {#marketing-channels}

기존 Adobe Analytics 마케팅 채널 설정은 Customer Journey Analytics에서 동일하게 적용되지 않습니다. 이는 다음 두 가지 이유에 기인한 것입니다.

* Adobe Experience Platform으로 수집된 Adobe Analytics 데이터의 처리 수준 및

* Customer Journey Analytics의 보고서 시간 특성

Adobe는 [업데이트된 마케팅 채널 구현을 위한 모범 사례](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=ko-KR)를 게시했습니다. 이러한 업데이트된 권장 사항을 사용하면 Attribution IQ를 통해 Adobe Analytics에 이미 있는 기능을 최대한 활용하는 데 도움이 됩니다. 또한 정상적으로 Customer Journey Analytics로 전환할 수 있도록 지원합니다.

Customer Journey Analytics 데이터 보기의 일부로 [파생 필드](../data-views/derived-fields/derived-fields.md)가 도입됨에 따라 [마케팅 채널 기능 템플릿](../data-views/derived-fields/derived-fields.md#function-templates)을 사용하여 마케팅 채널 또한 비파괴적이고 소급 적용되는 방식으로 지원됩니다.

### 4. Analytics 소스 커넥터와 Experience Platform SDK 비교 및 사용 결정 {#connector-vs-sdk}

Adobe Analytics 고객은 Analytics 소스 커넥터를 사용하여 Adobe Experience Platform 및 Customer Journey Analytics에서 보고서 세트를 쉽게 활용할 수 있습니다. Analytics 소스 커넥터 사용에 대한 자세한 내용은 [Adobe Analytics에서 데이터를 수집하고 Customer Journey Analytics에서 사용하는 방법](../data-ingestion/analytics.md)에 대한 빠른 시작 안내서를 참조하십시오. 또한 [UI에서 Adobe Analytics 소스 연결 만들기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko-KR)를 참조하십시오.

[Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko-KR) 데이터 수집이 발전함에 따라 Adobe Experience Platform Edge Network가 포함된 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=ko-KR) 또는 [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=ko-KR)로 마이그레이션하고자 할 수 있습니다. SDK의 일반적인 구현은 데이터를 Adobe Analytics로 전송하지만 Adobe Experience Platform으로 직접 데이터를 전송할 수 있는 새로운 옵션이 생깁니다. 그런 다음 Adobe Analytics로 전송된 데이터를 유지하면서 Customer Journey Analytics로 수집할 수 있습니다.

이 방법은 데이터 수집 가능성을 크게 확장합니다. 더 이상 필드 수에 대한 제한이나 데이터 요소를 Analytics와 같은 Prop, eVar 및 이벤트에 매핑할 필요가 없습니다. 다양한 유형의 스키마 요소를 무제한으로 사용하고 Customer Journey Analytics [데이터 보기](/help/data-views/data-views.md)를 사용하여 여러 방식으로 나타낼 수 있습니다. Adobe Experience Platform으로 직접 전송하면 Adobe Analytics를 통한 데이터 처리 시간이 생략되므로 데이터 가용성 속도가 빨라집니다.

**Experience Platform SDK 사용의 이점:**

* 필요한 모든 필드를 정의할 수 있는 유연한 스키마
* Adobe Analytics 명명법(Prop, eVar, 이벤트 등)에 의존하지 않음
* 글자 수 제한 없음 (Prop의 경우 100자)
* Adobe Experience Platform에서 보다 빠른 데이터 가용성을 통해 [실시간 개인화 사용 사례](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=ko-KR) 개선
* 방문자 식별 정확도 향상을 위한 [자사 디바이스 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=ko-KR)

**Experience Platform SDK 사용의 단점**

다음 Adobe Analytics 기능 또는 구성 요소는 지원되지 않습니다.

* 봇 필터링
* 스트리밍 미디어 측정
* 라이브스트림 또는 라이브스트림 트리거

### 5. Adobe Analytics의 프로젝트 및 구성 요소를 Customer Journey Analytics에 매핑

Adobe Analytics 관리자는 Adobe Analytics 프로젝트 및 관련 구성 요소를 Customer Journey Analytics으로 마이그레이션할 수 있습니다.

마이그레이션 프로세스에는 다음이 포함됩니다.

* Customer Journey Analytics에서 Adobe Analytics 프로젝트 다시 만들기

* Adobe Analytics 보고서 세트의 차원 및 지표를 Customer Journey Analytics 데이터 보기의 차원 및 지표에 매핑합니다.

마이그레이션을 시작하기 전에 먼저 [Adobe Analytics에서 Customer Journey Analytics으로 구성 요소 및 프로젝트 마이그레이션 준비](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html).

필요한 모든 준비를 마치면 다음을 수행할 수 있습니다. [Adobe Analytics에서 Customer Journey Analytics으로 구성 요소 및 프로젝트 마이그레이션](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html).

## 중요한 차이점에 대비

### 보고 시간 처리에 익숙해지기 {#report-time}

Adobe Analytics에서의 보고는 상당한 양의 데이터 사전 처리에 의존하여 [!UICONTROL eVar]에서 볼 수 있는 지속성과 같은 결과를 초래합니다. 반대로 Customer Journey Analytics는 보고서 실행 시 이러한 계산을 처리합니다.

[!UICONTROL 보고서 처리 시간]을 사용하면 기본 데이터 수집 방법을 변경할 필요 없이 소급 설정을 적용하고 여러 버전의 변수 지속성을 생성할 수 있습니다.

이러한 변화로 인해 특히 만료 기간이 긴 변수의 경우 데이터 보고 방식에 약간의 차이가 발생합니다. [가상 보고서 세트](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ko-KR)를 사용하여 보고서 처리 시간이 보고에 어떤 영향을 미칠 수 있는지 평가할 수 있습니다.

### 중요한 세그먼트 및 계산된 지표 식별 {#segments-calcmetrics}

Adobe Analytics 세그먼트(Customer Journey Analytics에서는 [!UICONTROL 필터]라고 함) 및 계산된 지표는 Customer Journey Analytics와 호환되지 않습니다. 대부분의 경우 이들 구성 요소는 사용 가능한 새 스키마 및 데이터를 사용하여 Customer Journey Analytics에서 다시 빌드할 수 있습니다.

사용자가 시스템 간 전환할 때 최대한 원활하게 전환하도록 하려면 다음과 같은 방법을 통해 계획을 수립하십시오.

1. 이들 구성 요소 중 가장 중요한 요소를 식별합니다.

2. 해당 요소의 정의를 문서화하고,

3. Customer Journey Analytics에서 [필터](/help/components/filters/filters-overview.md) 및 [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md)로 복제하기 위해 데이터에 어떤 필드가 필요한지 식별합니다.

다음은 몇 가지 가이드 비디오입니다.

* [Adobe Analytics 세그먼트를 Customer Journey Analytics로 이동](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=ko-KR)

* [계산된 지표를 Adobe Analytics에서 Customer Journey Analytics로 이동](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=ko-KR)

### 기타 고려 사항

* 강력한 Customer Journey Analytics 데이터 보기를 사용하면 Customer Journey Analytics 내에서 지표 및 차원을 훨씬 유연하게 정의할 수 있습니다. 예를 들어 차원 값을 사용하여 지표의 정의가 될 수 있습니다. [자세히 알아보기](/help/use-cases/data-views/data-views-usecases.md)

* Adobe Analytics에서 [사용자 정의 캘린더](/help/components/date-ranges/custom-date-ranges.md)를 정의한 경우 Customer Journey Analytics 내에서 유사한 캘린더 기능을 사용할 수 있습니다. 캘린더가 올바르게 정의되었는지 확인해야 합니다.

* Customer Journey Analytics에서 사용자 정의 방문/세션 시간 초과를 정의하고 새 세션을 시작하는 지표를 정의할 수 있습니다. 다양한 세션 정의를 사용하여 데이터 보기를 만들고 Adobe Analytics에서 가능했던 것 이상의 통찰력을 얻을 수 있습니다. 이 기능은 특히 모바일 데이터 세트에 유용할 수 있습니다.

* 사용자를 위한 데이터 사전을 제공하거나 스키마 요소의 Experience Platform 필드 이름을 포함하도록 SDR을 확장합니다.

## 다음 단계

Customer Journey Analytics로 이동한 후 데이터 불일치가 발견되는 경우 원래 Adobe Analytics 데이터와 현재 Customer Journey Analytics의 Adobe Analytics 데이터를 비교할 수 있습니다. [자세히 알아보기](/help/troubleshooting/compare.md)
