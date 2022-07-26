---
description: Real-time Customer Data Platform(실시간 CDP)와 CJA 간의 지표 및 대상 멤버십 카운트의 일관성에 영향을 주는 요소를 설명합니다.
title: 실시간 CDP와 CJA 간의 지표 및 대상 멤버십 카운트의 일관성
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 769eef205df32865874753859ce79e573db40641
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---


# 실시간 CDP와 CJA 간의 지표 및 대상 멤버십 카운트의 일관성

실제 시나리오에서는 Real-time Customer Data Platform(실시간 CDP) 및 Customer Journey Analytics(CJA)에서 지표와 대상 멤버십 수의 일관성을 보장할 수 없습니다. 이 문서에서는 그 이유를 설명합니다.

실시간 CDP와 CJA 간에 대상 멤버십 수를 비교할 때는 이러한 두 도구의 다른 목적을 염두에 두어야 합니다. 실시간 CDP는 고객 프로필 데이터를 사용하여 개별 소비자에게 디지털 경험을 타깃팅하는 반면 CJA는 사용자가 주요 비즈니스 지표 및 세그먼트의 패턴을 이해할 수 있도록 설계되었습니다. CJA에서 실시간 CDP로 대상 게시를 사용하면 이러한 도구의 사용자가 CJA에서 얻은 지식을 활용하여 쉽고 기본적으로 통찰력을 &quot;활성화&quot;할 수 있지만 이러한 도구는 기본적으로 다른 용도로 사용됩니다.

## ID 구성의 차이점

실시간 CDP와 CJA는 오늘날 한 사람에 대한 동일한 정의를 공유하지 않습니다. 실시간 CDP는 전적으로 [ID 그래프](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=en) 병합된 프로필을 빌드하려면 다음을 수행하십시오.

CJA는 [크로스 채널 분석](/help/connections/cca/overview.md) 는 데이터 레이크의 데이터 세트에서 식별자를 추출하고 사용자 지정 논리를 적용하여 함께 연결합니다.

나중에 CJA에서 ID 그래프를 사용할 수 있습니다.

## 데이터 집합 구성의 차이점

일부 데이터를 실시간 CDP에 배치하거나 CJA에서 사용하도록 선택할 수 있습니다. 종종 고객은 실시간 CDP와 관련된 데이터보다 CJA에 이전 데이터를 추가하도록 선택합니다. 다른 데이터 세트는 CJA보다 실시간 CDP에 더 관련이 있을 수 있습니다.

## 처리 구성의 차이점

CJA에서는 쿼리 시간에 필드 결합, 필드 분할 및 포함/제외, 하위 문자열, 값 중복 제거, 세션 및 행 수준 필터링과 같은 기타 조작과 같은 광범위한 데이터 수정을 수행할 수 있습니다.

실시간 CDP는 다른 데이터 조작 도구 세트를 제공합니다. 적용 [정책 병합](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) 우선 순위를 지정할 데이터와 결합할 데이터를 파악하여 한 사람의 통합 뷰를 생성합니다.

## TTL(Time to Live) 및 데이터 수집의 차이

실시간 CDP와 CJA의 데이터 세트가 동일하더라도 실시간 CDP는 매우 제한된 기록 기간을 유지할 수 있습니다. 반대로 CJA는 수년 동안의 데이터를 보유하고 있습니다. 또한:

* CJA 및 실시간 CDP 고객은 서로 독립적으로 데이터에 대한 사용자 지정 유지 기간을 설정할 수 있습니다.

* 실시간 CDP와 CJA에는 데이터를 수집하기 위한 서로 다른 논리가 있습니다. CJA에서는 개인 ID 또는 타임스탬프가 없는 레코드를 무시하며 단일 프로필/사람이 가질 수 있는 레코드 수에 엄격한 제한을 둡니다.

* 실시간 CDP 고객은 주로 프로필로 데이터를 온보딩하고 임시 쿼리를 위해 레이크에서 데이터에 7일 동안 액세스할 수 있습니다.

* CJA 고객을 위한 레이크에서 데이터에 대한 TTL이 없습니다. 그러나 CJA 사용자는 연결을 만들 때 CJA에서 사용자 지정 유지 기간을 설정할 수 있습니다.

* 실시간 CDP의 프로필 저장소를 통해 고객이 구성할 수 있는 TTL을 사용할 수 있습니다. 고객은 이 TTL을 라이선스 권한 내에 있어야 하는 모든 항목으로 변경할 수 있습니다.

## 데이터 수집 지연의 차이

CJa에는 아직 실시간 CDP의 실시간 기능이 없으며 따라서 보고 또는 대상 생성을 위해 데이터를 사용할 수 있으려면 몇 가지 지연이 CJA 보고에 포함됩니다. 실시간 CDP는 지연이 다른 시스템을 통해 데이터를 처리합니다.
