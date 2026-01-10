---
title: Customer Journey Analytics에 사용할 스키마 설계
description: Customer Journey Analytics의 유연성을 잠금 해제하는 XDM 스키마를 디자인하는 동시에 Adobe Analytics에서 실용적인 마이그레이션 경로를 지원하는 방법에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 3dc53d6955eab3048ebf8a7c9d232b4b5739c6bd
workflow-type: tm+mt
source-wordcount: '1455'
ht-degree: 9%

---

# Customer Journey Analytics에 사용할 스키마 설계 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="스키마 설계"
>abstract="조직 내에서 데이터 수집 요구 사항에 대해 논의하고 Adobe Experience Platform에서 사용할 스키마를 빌드하는 방법을 결정합니다. 이 단계는 조직에 맞춘 스키마를 사용하는 권장 프로세스를 사용하고자 하기 때문에 나타납니다. 이 단계를 올바르게 수행하는 것이 매우 중요합니다. 조직 내 모든 팀이 일치하는 스키마를 적용하면 데이터 수집이 훨씬 쉬워지기 때문입니다.<br><br>조직 내 모든 관련자들이 통합된 스키마를 구성하는 데 소요되는 예상 시간은 1~2개월입니다. 이 기간은 조정해야 하는 팀의 수와 정렬할 차원과 지표의 수에 따라 크게 달라집니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe은 [Adobe Experience Platform 데이터 수집](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/home)을 구현할 때 Customer Journey Analytics에 대한 사용자 지정 [XDM(Experience Data Model](https://experienceleague.adobe.com/ko/docs/experience-platform/collection/home)) 스키마를 만들 것을 권장합니다. 이 스키마를 만드는 작업은 일반적으로 구현 변경 사항이나 코드를 터치하기 전에 수행됩니다. 사용자 지정 스키마를 사용하면 Adobe Analytics에서 제한을 상속하거나 수천 개의 미사용 필드를 관리하지 않고 간결한 조직별 데이터 계약을 디자인할 수 있습니다. 조직에서 사용할 수 있는 스키마 유형에 대한 자세한 내용은 [Customer Journey Analytics용 스키마 선택](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)을 참조하세요.

스키마는 데이터를 장기적으로 구조화하는 방법에 대한 세련된 버전을 위한 것입니다. 스키마를 변경하면 데이터 수집, 유효성 검사 및 다운스트림 서비스에 영향을 주기 때문에 많은 비용이 소요됩니다. 비즈니스 요구 사항이 허용하면 시간이 지남에 따라 스키마에 을 추가할 수 있습니다. 하지만 데이터가 스키마 필드로 유입되기 시작하면 스키마 필드를 제거할 수 없습니다.

## 스키마와 데이터 보기 비교

Customer Journey Analytics용 데이터 파이프라인에는 데이터 수집 및 데이터 해석을 위한 별도의 영역이 포함되어 있습니다. Adobe Analytics에서 업그레이드할 때 일반적인 단계는 XDM에서의 동작을 사용하여 prop 및 eVar를 다시 만들려고 하는 것입니다. 대신 웹 SDK을 사용하여 데이터를 수집하고 [데이터 보기](/help/data-views/data-views.md)를 사용하여 보고서에서 해당 데이터를 해석하는 방법을 결정합니다.

| 레이어 | 주요 목적 | 속한 항목 | 속하지 않는 항목 |
|---|---|---|---|
| **XDM 스키마** | 수집된 데이터의 내구성 구조 및 의미 정의 | 이벤트 및 엔티티 모양, 필드 의미, 관계, 허용된 값, 여러 채널 재사용 | 번호가 매겨진 &quot;슬롯&quot;(eVar1/prop1), 속성/지속성 논리, 보고별 해결 방법 |
| **데이터 보기** | 수집된 데이터가 분석에서 작동하는 방식 정의 | 구성 요소 설정, 속성 및 지속성 비헤이비어, 파생 필드, 필터링된 지표, 계산된 지표 | 필드의 기본 의미. 스키마에서 해당 의미가 안정적이어야 합니다. |

## 스키마를 Adobe Analytics 데이터 수집과 비교

Customer Journey Analytics이 사용하는 Experience Data Model은 대부분의 다른 Analytics 솔루션(Adobe Analytics 포함)보다 훨씬 더 많은 유연성을 제공합니다. 견고한 스키마를 설정하는 것은 다른 Analytics 제품에 존재하는 제약 조건을 전달할 수 없는 조직의 기회입니다.

| 일반적인 Adobe Analytics 습관 | XDM + CJA에서의 더 나은 접근 방식 |
|---|---|
| 번호가 매겨진 슬롯(`eVar1`-`eVar250`, `prop1`-`prop75`) 주위로 디자인 | 안정적인 의미를 갖는 필드(예: `search.term`, `content.category`, `user.membershipTier`)를 만들고 일관되게 재사용 |
| 데이터 모델에 지속성/할당/만료 인코딩 | 스키마에서 지속적인 팩트를 캡처하고 데이터 보기 수준에서 속성 및 지속성 동작을 적용합니다. |
| 보고 동작을 달성하기 위해 여러 변수에서 동일한 값을 복제합니다 | 값을 한 번 저장하고 데이터 보기에서 여러 구성 요소(차원/지표)를 만듭니다 |
| 원하는 모든 카운트에 대해 고유한 &quot;지표 필드&quot;를 만듭니다. | 올바른 팩트(종종 열거형/부울/문자열)를 한 번 캡처한 다음 지표를 데이터 보기에서 필터링된 카운트로 정의합니다 |
| 변수를 &quot;사전 해결&quot; 보고로 디자인 | 팩트를 안정적으로 캡처하도록 스키마를 디자인하고 데이터 보기를 사용하여 보고 의미 체계를 해결합니다. |

## 일반 속성을 사용하여 스키마 설정

여러 이벤트에 걸쳐 표시되는 재사용 가능한 속성 세트를 표준화할 때 채널 간 통합 스키마가 가능합니다. 예를 들면 다음과 같습니다.

* **경험 컨텍스트:** 사이트/앱 이름, 환경, 로케일, 채널, 브랜드
* **여정 컨텍스트:** 캠페인 식별자, 참조 컨텍스트, 실험 식별자
* **사용자 상태:** 로그인 상태, 멤버십 계층, 계정 유형
* **상호 작용 세부 정보:** 상호 작용 이름/유형, UI 영역, 요소 레이블, 오류 범주

채널에 상관없이 필드가 나타내는 내용을 표준화하는 것이 핵심이다. 동일한 개념을 실제로 다른 개념을 나타내지 않는 한 여러 채널에서 동일한 개념을 다르게 모델링하지 마십시오. 예를 들어 웹 캠페인 ID와 모바일 캠페인 ID에 대해 별도의 스키마 필드가 없는 것이 좋습니다. 별도의 스키마 필드를 사용하면 광고 지출 데이터에 대한 크로스 채널 수익률을 설정하는 것이 더 어려워집니다. 보고에서 차별화가 필요한 경우 채널별로 세그먼트화하거나 여러 필드를 연결하여 구별할 수 있습니다. 동일한 스키마 필드를 차원 또는 지표 수에 관계없이 사용할 수 있습니다.

단일 스키마 전략을 유지하면서 여러 채널을 지원하는 실용적인 방법은 **코어 + 확장** 패턴을 사용하는 것입니다.

* 채널 및 팀 전체에 광범위하게 적용되는 **코어:** 필드
* **확장:** 필요한 위치에만 적용되는 채널 또는 도메인별 필드 그룹(웹 상호 작용, 상거래, 모바일 라이프사이클, 서버측 세부 사항)

이 패턴은 모든 팀이 채널에 적용되지 않는 필드를 채우도록 하지 않고 단일 조직 스키마 전략을 지원합니다.

## 적합한 표준 필드 그룹 선호

Adobe에서는 요구 사항과 일치하는 표준화된 필드 그룹을 사용하고, 조직별 개념을 위해 사용자 지정 필드로 확장하는 것이 좋습니다.

표준 필드 그룹은 일반적으로 다음 작업을 수행하는 데 도움이 됩니다.

* 알려진 필드 의미 체계를 사용하여 모호성 감소
* 팀 간 더 쉽게 조정
* Adobe Experience Platform 애플리케이션 간의 상호 운용성 지원

다음과 같은 경우 사용자 정의 필드가 적절합니다.

* 조직에 표준 필드에 완전히 매핑되지 않는 개념이 있습니다
* 보고, 거버넌스 또는 활성화 요구 사항을 충족하려면 추가 속성이 필요합니다
* 비즈니스별 분류 체계(예: 내부 콘텐츠 범주)를 나타내려고 합니다

## &quot;지표 의미&quot;가 어디에 사는지 결정

Adobe Analytics에서 많은 팀이 `events` 변수를 지표가 이동하는 위치로 처리합니다. Customer Journey Analytics에서는 계산해야 하는 항목과 지표를 해석하는 방법에 따라 여러 가지 방법으로 지표를 모델링할 수 있습니다.

스키마를 디자인할 때는 팩트를 사용하십시오. 예: `error.type = "validation"`, `user.isLoggedIn = true`, `checkout.step = "shipping"`. 데이터 보기에서 지표를 해당 팩트에 대한 카운트 및 필터링된 카운트로 정의합니다. 예:

* `checkout.step`(enum/string)은 다음 기능을 제공할 수 있습니다.
   * &quot;체크아웃: 배송 단계에 도달함&quot;(위치: `checkout.step == "shipping"`)
   * &quot;체크아웃: 결제 단계 도달&quot;
* `error.type`(enum/string)은 다음 기능을 제공할 수 있습니다.
   * &quot;유효성 검사 오류&quot;
   * &quot;인증 오류&quot;
* `user.isLoggedIn`(부울)이(가) 다음 기능을 제공할 수 있습니다.
   * &quot;인증된 세션&quot;
   * &quot;인증된 전환&quot;

>[!TIP]
>
>나중에 전용 필드와 파생 필드 중 어떤 것이 되어야 하는지 여부를 결정할 때, 광범위하게 유용하고 안정적인 경우 스키마에 지속적인 팩트를 캡처하는 것이 좋습니다. 수집 후 파생 필드를 사용하여 데이터를 수정하거나 모양을 변경할 수 있습니다.

## 스키마 수하물을 사용하지 않고 전환하는 동안 Adobe Analytics과의 패리티 유지

일부 조직에서는 Customer Journey Analytics으로 업그레이드하는 동안 Adobe Analytics 보고를 계속해야 합니다. 다음 접근 방식을 사용하여 Analytics 특정 아티팩트를 장기 스키마 디자인에 도입하지 않고도 패리티를 유지할 수 있습니다.

1. **Adobe Analytics에서 인식하고 자동으로 매핑하는 XDM 필드 경로 사용:** 인식된 XDM 필드를 Edge Network을 통해 Adobe Analytics으로 보낼 때 추가 구성 없이 [자동으로 매핑](https://experienceleague.adobe.com/ko/docs/analytics/implementation/aep-edge/xdm-var-mapping)됩니다.
1. **조직별 개념에 사용자 지정 XDM 필드 사용:** Analytics 변수에 자동으로 매핑되지 않은 모든 XDM 필드는 Adobe Analytics에서 [컨텍스트 데이터 변수](https://experienceleague.adobe.com/ko/docs/analytics/implementation/vars/page-vars/contextdata)&#x200B;(으)로 전달됩니다.
1. **Adobe Analytics 처리 규칙을 사용하여 해당 컨텍스트 데이터 변수를 props/eVars에 매핑합니다.** [처리 규칙](https://experienceleague.adobe.com/ko/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/processing-rules/pr-overview) 최종적으로 사용자 지정 XDM 필드를 eVar 또는 prop에 매핑할 수 있습니다. 이 개념은 Adobe Analytics에서 패리티 보고를 지원하면서 스키마를 깔끔하고 Customer Journey Analytics을 중심으로 합니다.

## 이해 당사자 식별 및 소유권 정의

필드 의미가 합의되고 유지될 때 스키마 설계가 성공합니다. 조직 구조는 다르지만 일반적으로 다음 역할이 참여합니다.

* **Analytics 관리자/분석가**: 보고 질문을 정의하고 필드가 의미 있는 개념을 나타내는지 검증하며 데이터 보기의 분석 의미 체계를 검토합니다.
* **개발자/구현 소유자**: 웹 SDK을 사용하여 필드를 안정적으로 수집할 수 있도록 하고 데이터 레이어/앱 계측을 조정합니다.
* **데이터 설계자/엔지니어**: 스키마 일관성, 도메인 간 재사용 및 다운스트림 서비스와의 호환성을 보장합니다.
* **개인 정보 보호/거버넌스 관련자**: 데이터 최소화, 동의 예상 및 데이터 사용 제한을 검토합니다.

스키마 변경에 대한 명확한 소유자를 정의합니다. 절제된 변경 제어를 가진 안정적인 스키마는 다운스트림 손상을 방지하고 재작업을 줄입니다. 추적 거버넌스 워크플로 또는 도구 를 사용하여 요청을 대중화하고 시간에 따른 변경 제어를 관리하는 것이 좋습니다.

## 개인 정보 및 거버넌스 고려 사항

스키마 디자인은 조직의 개인정보 처리방침에 따라 개인정보 및 거버넌스 기대치를 반영해야 합니다. 스키마를 설계할 때 다음 사항을 고려하십시오.

* 정의된 사용 사례를 지원하는 데 필요한 사항만 수집합니다.
* 동의 및 데이터 사용 요구 사항이 수집 전략에 반영되었는지 확인합니다. 자세한 내용은 [웹 SDK을 사용하여 고객 동의 데이터를 처리](https://experienceleague.adobe.com/ko/docs/experience-platform/landing/governance-privacy-security/consent/sdk)를 참조하십시오.
* Adobe Experience Platform 거버넌스 도구 내에서 중요한 필드에 어떻게 레이블이 지정되고 제어되는지 생각해 보십시오. 자세한 내용은 [Adobe Customer Journey Analytics 및 데이터 거버넌스](/help/privacy/privacy-overview.md)를 참조하십시오.

## 다음 단계

스키마 아키텍처를 설정하고 동의하면 Adobe Experience Platform에서 작성을 시작할 수 있습니다. 자세한 내용은 [Customer Journey Analytics에서 사용할 사용자 지정 스키마 만들기](cja-upgrade-schema-create.md)를 참조하십시오.
