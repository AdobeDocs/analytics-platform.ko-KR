---
description: Real-Time CDP(Real-time Customer Data Platform)와 Customer Journey Analytics 간의 지표 및 대상자 멤버십의 일관성에 영향을 미치는 요인을 설명합니다.
title: 지표 및 대상자 멤버십의 일관성
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 7c906e30d54362713f5013c8661ee523938d4b0f
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 88%

---


# 지표 및 대상자 멤버십의 일관성

실제 시나리오에서는 Real-Time CDP(Real-time Customer Data Platform)와 Customer Journey Analytics 간의 지표 및 대상자 멤버십의 일관성을 보장할 수 없습니다. 이 문서에서는 그 이유를 설명합니다.

Real-Time CDP와 Customer Journey Analytics 간의 대상자 멤버십을 비교할 때는 두 도구의 다른 목적에 유의하는 것이 중요합니다. Real-Time CDP는 고객 프로필 데이터를 사용하여 개별 소비자에게 디지털 경험을 제공하는 반면, Customer Journey Analytics는 사용자가 주요 비즈니스 지표 및 세그먼트의 패턴을 이해할 수 있도록 설계되었습니다. Customer Journey Analytics에서 Real-Time CDP로의 대상자 게시를 통해 이러한 도구의 사용자는 Customer Journey Analytics에서 얻은 학습을 활용하여 인사이트를 쉽고 기본적으로 “활성화”할 수 있지만, 이러한 도구는 근본적으로 다른 목적을 제공합니다.

## ID 구성의 차이점

Real-Time CDP와 Customer Journey Analytics는 오늘날 개인에 대한 동일한 정의를 공유하지 않습니다. Real-Time CDP는 [ID 그래프](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=ko)의 정보에 전적으로 의존하여 병합 프로필을 빌드합니다.

[결합](../stitching/overview.md)을 사용하도록 Customer Journey Analytics을 구성할 수 있습니다. 결합 메커니즘으로 [필드 기반 결합](/help/stitching/fbs.md)을(를) 사용하는 경우 데이터 레이크의 데이터 세트에서 식별자를 지정하여 해당 데이터 세트의 데이터를 향상된 병합 프로필로 데이터 세트를 상승시키기 위한 목적으로 결합합니다. 결합 메커니즘으로 [그래프 기반 결합](/help/stitching/gbs.md)을 사용하는 경우 유사한 프로세스가 지정된 ID 네임스페이스를 기반으로 ID 그래프를 사용합니다.


## 데이터 세트 구성의 차이점

Real-Time CDP에 데이터를 저장할 수도 있고, Customer Journey Analytics에 데이터를 저장할 수도 있습니다. 경우에 따라 고객은 Real-Time CDP와 관련된 것보다 더 많은 내역 데이터를 Customer Journey Analytics에 저장합니다. 다른 데이터 세트는 Customer Journey Analytics보다 Real-Time CDP와 더 관련이 있을 수 있습니다.

## 처리 구성의 차이점

Customer Journey Analytics를 사용하면 필드 결합, 필드 분리 및 포함/제외, 하위 문자열, 값 중복 제거, 세션화, 행 수준 필터링 등 기타 조작 등 쿼리 시간에 광범위한 데이터 수정이 가능합니다.

Real-Time CDP는 다양한 데이터 조작 도구 세트를 제공합니다. [병합 정책](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=ko)을 적용하여 어떤 데이터가 우선시되고 어떤 데이터가 결합되어 개인에 대한 통합 보기를 생성할 것인지 결정합니다.

## TTL(Time to Live) 및 데이터 수집의 차이점

Real-Time CDP와 Customer Journey Analytics의 데이터 세트가 동일하더라도 Real-Time CDP는 매우 제한된 기간 동안의 기록만 유지할 수 있습니다. 반대로 Customer Journey Analytics에는 수년간의 데이터가 저장되어 있을 가능성이 높습니다. 또한

* Customer Journey Analytics 및 Real-Time CDP 고객은 사용자 정의 데이터 보존 기간을 서로 독립적으로 설정할 수 있습니다.

* Real-Time CDP CDP와 Customer Journey Analytics는 데이터 수집 논리가 다릅니다. Customer Journey Analytics는 개인 ID 또는 타임스탬프가 없는 레코드를 무시하며 단일 프로필/개인이 가질 수 있는 레코드 수에 대해 엄격한 제한이 있습니다.

* Real-Time CDP 고객은 레이크 데이터에 7일 동안 액세스하여 주로 프로필에 데이터 온보딩을 용이하게 하고 애드혹을 쿼리할 수 있습니다.

* Customer Journey Analytics 고객용 레이크 데이터에 대한 TTL은 없습니다. 그러나 Customer Journey Analytics 사용자는 연결을 생성할 때 Customer Journey Analytics에서 사용자 정의 보존 기간을 직접 설정할 수 있습니다.

* Real-Time CDP의 프로필 저장소를 통해 고객이 구성 가능한 TTL을 사용할 수 있습니다. 고객은 이 TTL을 라이선스 권한 내에서 유지하는 데 필요한 것으로 변경할 수 있습니다.

## 데이터 수집 지연 시간의 차이점

Customer Journey Analytics에는 아직 Real-Time CDP의 실시간 기능이 없으므로 Customer Journey Analytics 보고에는 보고 또는 대상자 생성을 위해 데이터를 사용할 수 있기까지 약간의 지연 시간이 포함됩니다. Real-Time CDP는 지연 시간이 다른 여러 시스템을 통해 데이터를 처리합니다.
