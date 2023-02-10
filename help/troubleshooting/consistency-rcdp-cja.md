---
description: Real-Time CDP(Real-time Customer Data Platform)와 CJA 간의 지표 및 대상 멤버십의 일관성에 영향을 미치는 요인을 설명합니다.
title: Real-Time CDP와 CJA 간의 지표 및 대상 멤버십의 일관성
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 34ee7954329d7dc8520031a977bb83d6e1bf3d3d
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 94%

---


# Real-Time CDP와 CJA 간의 지표 및 대상 멤버십의 일관성

실제 시나리오에서는 Real-Time CDP(Real-time Customer Data Platform)와 CJA(Customer Journey Analytics) 간의 지표 및 대상 멤버십의 일관성을 보장할 수 없습니다. 이 문서에서는 그 이유를 설명합니다.

Real-Time CDP와 CJA 간의 대상 멤버십을 비교할 때는 두 도구의 다른 목적에 유의하는 것이 중요합니다. Real-Time CDP는 고객 프로필 데이터를 사용하여 개별 소비자에게 디지털 경험을 제공하는 반면, CJA는 사용자가 주요 비즈니스 지표 및 세그먼트의 패턴을 이해할 수 있도록 설계되었습니다. CJA에서 Real-Time CDP로의 대상 게시를 통해 이러한 도구의 사용자는 CJA에서 얻은 학습을 활용하여 통찰력을 쉽고 기본적으로 “활성화”할 수 있지만, 이러한 도구는 근본적으로 다른 목적을 제공합니다.

## ID 구성의 차이점

Real-Time CDP와 CJA는 오늘날 개인에 대한 동일한 정의를 공유하지 않습니다. Real-Time CDP는 [ID 그래프](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=ko-kr)의 정보에 전적으로 의존하여 병합 프로필을 빌드합니다.

CJA는 데이터 레이크의 데이터 세트에서 식별자를 추출하고 사용자 지정 로직을 적용하여 서로 연결하는 [크로스 채널 분석](/help/cca/overview.md)을 사용하도록 구성할 수 있습니다.

앞으로 CJA는 ID 그래프를 사용할 수 있습니다.

## 데이터세트 구성의 차이점

Real-Time CDP에 데이터를 저장할 수도 있고, CJA에 데이터를 저장할 수도 있습니다. 고객은 종종 Real-Time CDP와 관련된 것보다 더 많은 내역 데이터를 CJA에 저장하는 것을 선택합니다. 다른 데이터 세트는 CJA보다 Real-Time CDP와 더 관련이 있을 수 있습니다.

## 처리 구성의 차이점

CJA는 필드 결합, 필드 분리 및 포함/제외, 하위 문자열, 값 중복 제거, 세션화, 행 수준 필터링 등 기타 조작과 같은 쿼리 시간에 광범위한 데이터 수정을 허용합니다.

Real-Time CDP는 다양한 데이터 조작 도구 세트를 제공합니다. [병합 정책](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=ko-kr)을 적용하여 어떤 데이터가 우선시되고 어떤 데이터가 결합되어 개인에 대한 통합 보기를 생성할 것인지 결정합니다.

## TTL(Time to Live) 및 데이터 수집의 차이점

Real-Time CDP와 CJA의 데이터 세트가 동일하더라도 Real-Time CDP는 매우 제한된 내역 창만 유지할 수 있습니다. 대조적으로, CJA는 수년간의 데이터를 보유하고 있습니다. 또한:

* CJA 및 Real-Time CDP 고객은 사용자 지정 데이터 보존 기간을 서로 독립적으로 설정할 수 있습니다.

* Real-Time CDP와 CJA는 데이터 수집에 대한 논리가 다릅니다. CJA는 개인 ID 또는 타임스탬프가 없는 레코드를 무시하며 단일 프로필/개인이 가질 수 있는 레코드 수에 대해 엄격한 제한이 있습니다.

* Real-Time CDP 고객은 주로 프로필에 데이터 온보딩을 용이하게 하고 애드혹 쿼리를 위해 레이크 데이터에 7일 동안 액세스할 수 있습니다.

* CJA 고객용 레이크 데이터에 대한 TTL은 없습니다. 그러나 CJA 사용자는 연결을 생성할 때 CJA에서 사용자 지정 보존 기간을 설정할 수 있습니다.

* Real-Time CDP의 프로필 저장소를 통해 고객이 구성 가능한 TTL을 사용할 수 있습니다. 고객은 이 TTL을 라이선스 권한 내에서 유지하는 데 필요한 것으로 변경할 수 있습니다.

## 데이터 수집 지연 시간의 차이점

CJA에는 아직 실시간 CDP의 실시간 기능이 없으며 따라서 CJA 보고에는 보고 또는 대상 생성을 위해 데이터를 사용할 수 있으려면 몇 가지 지연이 포함됩니다. Real-Time CDP는 지연 시간이 다른 여러 시스템을 통해 데이터를 처리합니다.
