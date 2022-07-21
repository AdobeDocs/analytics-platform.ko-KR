---
description: Real-time Customer Data Platform(실시간 CDP)와 CJA 간의 지표 일관성에 영향을 주는 요소를 설명합니다.
title: 실시간 CDP와 CJA 간의 지표 일관성
role: Admin
feature: CJA Basics
source-git-commit: 2318b303c981ad556dc61a3419af4cce9fbbf92b
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 2%

---


# 실시간 CDP와 CJA 간의 지표 일관성

실제 시나리오에서는 Real-time Customer Data Platform(실시간 CDP) 및 Customer Journey Analytics(CJA) 전체에서 지표의 일관성을 보장할 수 없습니다. 이 문서에서는 그 이유를 설명합니다.

## CJA는 아직 ID 그래프를 사용하지 않습니다

CDP와 CJA는 오늘날 한 사람에 대한 동일한 정의를 공유하지 않습니다. CJA는 아직 [ID 그래프](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ko) ...의 정의를 알려주다. 실시간 CDP는 Identity Graph의 정보를 활용하여 병합된 프로필을 작성합니다.

CJA에서는 [필드 기반 결합](/help/connections/cca/overview.md) 는 데이터 레이크의 데이터 세트에서 식별자를 추출하고 사용자 지정 논리를 적용하여 함께 연결합니다. 중간 미래에는 CJA가 [Adobe Experience Platform Identity 서비스](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) 실시간 CDP와 CJA에서 공유된 id를 확인할 수 있도록 data lake로 내보냅니다.

>[!IMPORTANT]
>
>Adobe Experience Platform Identity 서비스를 모든 Adobe Experience Platform 애플리케이션에 대한 진실의 ID 소스로 설정해도 애플리케이션 간에 지표가 자동으로 일관되지 않습니다. 이유를 알아보려면 계속 읽어보십시오.

## 애플리케이션 데이터 유연성

Experience Platform은 실시간 고객 프로필과 데이터 레이크 간에 데이터를 동일하게 유지하기 위해 엄격한 적용을 적용하지 않습니다. 일부 사용 사례는에서 데이터를 처리합니다 [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/profile/profile-overview.html?lang=en) (활성화) 이외의 다른 템플릿은 [데이터 레이크](https://business.adobe.com/blog/basics/data-lake) (보고 및 쿼리 서비스).

실시간 CDP 고객은 일반적으로 Adobe Experience Platform 데이터 레이크에서 Profile로 유입되는 데이터의 100%가 없습니다. 이것은 설계에 의한 것입니다. 고객은 프로필 레이크에서 데이터를 명시적으로 활성화해야 합니다. CJA를 사용하면 데이터 분석가가 실시간 CDP에 대해 활성화된 데이터와 상관없이 데이터 레이크에서 분석을 위해 가져올 데이터를 자유롭게 선택할 수 있습니다.

## 응용 프로그램별 수정자

CJA에서는 쿼리 시간에 필드 결합, 필드 분할 및 통화 변환, 값 중복 제거, 세션 및 행 수준 필터링과 같은 기타 조작과 같은 광범위한 데이터 수정을 수행할 수 있습니다. CDP에서는 이러한 기능을 사용할 수 없습니다.

마찬가지로 실시간 CDP가 적용됩니다 [정책 병합](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) 우선 순위를 지정할 데이터와 결합할 데이터를 파악하여 한 사람의 통합 뷰를 생성합니다. 이러한 구성은 각 애플리케이션의 논리 내에 견고하게 유지되며 공유되지 않습니다.

## 읽기 시간과 쓰기 시간 동작 비교

실시간 CDP를 사용하려면 최신 ID 그래프를 사용하여 시점 프로필 결합을 필요로 합니다.

* 실시간 CDP는 활성화를 위해 프로필 정보를 실시간으로 조합하도록 설계되었습니다.

* 지정된 사용자에 대해 설정된 식별자에 대한 모든 변경 사항을 실시간으로 수용할 수 있습니다.

* 전환 확인 기간은 세그먼트 정의에 의해 제어됩니다.

CJA에서는 ID 그래프 내보내기를 사용하여 적시에 데이터를 결합해야 합니다.

* CJA에서는 데이터를 분석할 준비가 되기 전에 색인 지정, 공유 및 그룹화와 같은 복잡한 사전 처리 단계를 적용합니다.

* 지정된 사용자의 개인 식별자는 사전 처리 단계에 대한 중요한 입력입니다. 이후에 개인 식별자를 변경하면 재처리 비용이 크게 발생합니다.

* 전환 확인 기간은 애플리케이션 수준에서 제어됩니다.

## TTL(Time to Live) 및 데이터 수집의 차이

실시간 CDP와 CJA의 데이터 세트가 동일하더라도 실시간 CDP는 매우 제한된 기록 기간을 유지할 수 있습니다. 반대로 CJA는 수년 동안의 데이터를 보유하고 있습니다. 또한:

* CJA 및 실시간 CDP 고객은 서로 독립적으로 데이터에 대한 사용자 지정 유지 기간을 설정할 수 있습니다.

* 실시간 CDP와 CJA에는 데이터를 수집하기 위한 서로 다른 논리가 있습니다. CJA에서는 개인 ID 또는 타임스탬프가 없는 레코드를 무시하며 단일 프로필/사람이 가질 수 있는 레코드 수에 엄격한 제한을 둡니다.

* 실시간 CDP 고객은 주로 프로필로 데이터를 온보딩하고 임시 쿼리를 위해 레이크에서 데이터에 7일 동안 액세스할 수 있습니다.

* CJA 고객을 위한 레이크에서 데이터에 대한 TTL이 없습니다. 그러나 CJA 사용자는 연결을 만들 때 CJA에서 사용자 지정 유지 기간을 설정할 수 있습니다.

* 실시간 CDP의 프로필 저장소를 통해 고객이 구성할 수 있는 TTL을 사용할 수 있습니다. 고객은 이 TTL을 라이선스 권한 내에 있어야 하는 모든 항목으로 변경할 수 있습니다.

## GDPR(일반 데이터 보호 규정) 처리 차이점

실시간 CDP와 Data Lake에서 GDPR 및 데이터 위생을 위한 데이터 처리 로직은 전혀 다릅니다. 우리는 하나의 접근법을 향해 노력하고 있습니다.

## 데이터 수집 지연의 차이

CJA 보고에는 보고 또는 대상을 만들 때 데이터를 사용할 수 있게 되기 전에 몇 가지 지연이 포함됩니다. 실시간 CDP는 지연이 다른 시스템을 통해 데이터를 처리합니다.