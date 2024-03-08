---
description: Real-time Customer Data Platform(Real-Time CDP)와 Customer Journey Analytics 간의 지표 및 대상 멤버십의 일관성에 영향을 미치는 요인에 대해 설명합니다.
title: Real-Time CDP와 Customer Journey Analytics 간의 지표 및 대상 멤버십의 일관성
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 23%

---


# Real-Time CDP와 Adobe Customer Journey Analytics 간의 지표 및 대상 멤버십의 일관성

실제 시나리오에서는 Real-time Customer Data Platform(Real-Time CDP)와 Customer Journey Analytics 간의 지표 및 대상 멤버십의 일관성을 보장할 수 없습니다. 이 문서에서는 그 이유를 설명합니다.

Real-Time CDP와 Customer Journey Analytics 간의 대상 멤버십을 비교할 때는 이 두 도구의 다른 목적에 유의하는 것이 중요합니다. Real-Time CDP는 고객 프로필 데이터를 사용하여 개별 소비자에게 디지털 경험을 제공하는 반면, Customer Journey Analytics은 사용자가 주요 비즈니스 지표 및 세그먼트의 패턴을 이해할 수 있도록 설계되었습니다. Customer Journey Analytics에서 Real-Time CDP로 대상을 게시하면 이러한 도구 사용자는 Customer Journey Analytics에서 얻은 학습을 활용하여 통찰력을 쉽고 기본적으로 &quot;활성화&quot;할 수 있지만, 이러한 도구는 근본적으로 다른 목적을 제공합니다.

## ID 구성의 차이점

Real-Time CDP와 Customer Journey Analytics은 오늘날 개인에 대한 동일한 정의를 공유하지 않습니다. Real-Time CDP는 [아이덴티티 그래프](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html)의 정보에 전적으로 의존하여 병합 프로필을 빌드합니다.

Customer Journey Analytics은 다음을 사용하도록 구성할 수 있습니다. [결합](../stitching/overview.md) 는 데이터 레이크의 데이터 세트에서 식별자를 추출하고 사용자 지정 로직을 적용하여 서로 연결합니다.

앞으로 Customer Journey Analytics은 ID 그래프를 사용할 수 있습니다.

## 데이터세트 구성의 차이점

Real-Time CDP에 데이터를 저장할 수도 있고, Customer Journey Analytics에 데이터를 저장할 수도 있습니다. 고객은 종종 Real-Time CDP와 관련된 것보다 더 많은 내역 데이터를 Customer Journey Analytics에 저장하는 것을 선택합니다. 다른 데이터 세트는 Customer Journey Analytics 보다 Real-Time CDP와 더 관련이 있을 수 있습니다.

## 처리 구성의 차이점

Customer Journey Analytics을 사용하면 필드 결합, 필드 분리 및 포함/제외, 하위 문자열, 값 중복 제거, 세션화, 행 수준 필터링 등 기타 조작과 같은 쿼리 시간에 광범위한 데이터 수정을 수행할 수 있습니다.

Real-Time CDP는 다양한 데이터 조작 도구 세트를 제공합니다. [병합 정책](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html)을 적용하여 어떤 데이터가 우선시되고 어떤 데이터가 결합되어 개인에 대한 통합 보기를 생성할 것인지 결정합니다.

## TTL(Time to Live) 및 데이터 수집의 차이점

Real-Time CDP와 Customer Journey Analytics의 데이터 세트가 동일하더라도 Real-Time CDP는 매우 제한된 내역 창만 유지할 수 있습니다. 그와 대조적으로, Customer Journey Analytics은 수년간의 데이터를 보유하고 있습니다. 또한:

* Customer Journey Analytics 및 Real-Time CDP 고객은 사용자 지정 데이터 보존 기간을 서로 독립적으로 설정할 수 있습니다.

* Real-Time CDP와 Customer Journey Analytics은 데이터 수집에 대한 논리가 다릅니다. Customer Journey Analytics은 개인 ID나 타임스탬프가 없는 레코드를 무시하며 단일 프로필/개인이 가질 수 있는 레코드 수에 대해 엄격한 제한이 있습니다.

* Real-Time CDP 고객은 주로 프로필에 데이터 온보딩을 용이하게 하고 애드혹 쿼리를 위해 레이크 데이터에 7일 동안 액세스할 수 있습니다.

* Customer Journey Analytics 고객을 위한 레이크 데이터에 대한 TTL은 없습니다. 그러나 Customer Journey Analytics 사용자는 연결을 만들 때 Customer Journey Analytics에서 사용자 지정 보존 기간을 설정할 수 있습니다.

* Real-Time CDP의 프로필 저장소를 통해 고객이 구성 가능한 TTL을 사용할 수 있습니다. 고객은 이 TTL을 라이선스 권한 내에서 유지하는 데 필요한 것으로 변경할 수 있습니다.

## 데이터 수집 지연 시간의 차이점

Customer Journey Analytics에는 아직 Real-Time CDP의 실시간 기능이 없으므로 Customer Journey Analytics 보고에는 보고 또는 대상 생성을 위해 데이터를 사용할 수 있기까지 약간의 지연 시간이 포함됩니다. Real-Time CDP는 지연 시간이 다른 여러 시스템을 통해 데이터를 처리합니다.
