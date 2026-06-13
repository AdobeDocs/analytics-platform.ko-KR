---
title: GA4 데이터 모델이 Customer Journey Analytics에 매핑되는 방법
description: GA4의 이벤트 기반 데이터 모델이 Customer Journey Analytics에서 XDM 스키마 및 데이터 세트로 변환되는 방법을 이해합니다.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: a5f9e2c7-3b1d-4a8e-b6f0-2c9d7e4a5180
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 692
ht-degree: 0%

---


# GA4 데이터 모델이 Customer Journey Analytics에 매핑되는 방법

GA4와 Customer Journey Analytics은 모두 이벤트 기반 플랫폼으로, Universal Analytics에서보다 서로 간의 데이터 모델 번역을 더 직접적으로 만듭니다. GA4의 이벤트 및 매개 변수가 Customer Journey Analytics의 XDM 필드 및 데이터 세트에 대응하는 방식을 이해하면 보고서를 더 쉽게 해석하고 구현 팀과 공동 작업을 수행할 수 있습니다.

## GA4의 이벤트 기반 데이터 모델

GA4의 모든 상호 작용은 컨텍스트를 제공하는 선택적 **매개 변수** 집합이 있는 명명된 작업인 **event**&#x200B;입니다. 페이지 보기, 세션 또는 목표에 대한 별도의 객체 유형은 없으며 모두 이벤트입니다.

| GA4 이벤트 유형 | 예 |
|---|---|
| 자동 수집됨 | `page_view`, `session_start`, `first_visit`, `scroll` |
| 향상된 측정 | `file_download`, `video_start`, `form_submit` |
| 권장 | `purchase`, `add_to_cart`, `sign_up` |
| 사용자 정의 | 정의한 모든 이벤트 이름 |

각 이벤트는 최대 25개의 매개 변수를 전달할 수 있습니다. 예를 들어 `purchase` 이벤트는 일반적으로 `transaction_id`, `value`, `currency` 및 `items`을(를) 매개 변수로 포함합니다.

## Customer Journey Analytics에서 데이터를 저장하는 방법

Customer Journey Analytics은 **Adobe Experience Platform**&#x200B;에서 데이터를 가져옵니다. 플랫폼의 데이터는 **데이터 세트**&#x200B;에 저장되며, 각 데이터 세트는 **XDM(Experience Data Model)**&#x200B;을 사용하여 빌드된 **스키마**&#x200B;을(를) 따릅니다. XDM은 고객 경험 데이터를 표현하기 위한 Adobe의 개방형 표준입니다.

Customer Journey Analytics에서 사용되는 데이터 세트 유형은 다음 세 가지가 있습니다.

| CJA 데이터 세트 유형 | GA4 상당 | 보유 수량 |
|---|---|---|
| [!UICONTROL 이벤트 데이터 세트] | GA4 이벤트 스트림 | 시계열 상호 작용(페이지 보기 수, 클릭 수, 구매) |
| [!UICONTROL 프로필 데이터 세트] | GA4 사용자 속성 | 개인 수준 특성(CRM 필드, 충성도 상태, 인구 통계) |
| [!UICONTROL 조회 데이터 세트] | 참조 테이블로 사용되는 GA4 사용자 지정 차원 | 키-값 참조 데이터 (제품 카탈로그, 캠페인 이름) |

Customer Journey Analytics에는 eVar, prop 또는 성공 이벤트가 없습니다. 모든 차원 및 지표는 XDM 스키마 필드에서 직접 가져온 것입니다. 고유한 차원 값의 수에는 제한이 없습니다.

## 자동으로 수집된 이벤트

GA4는 SDK을 통해 자동으로 이벤트 세트를 수집합니다. 다음 표는 이러한 이벤트를 해당 XDM 또는 Customer Journey Analytics에 해당하는 이벤트에 매핑합니다.

| GA4 자동 수집 이벤트 | XDM / Customer Journey Analytics 동등 항목 |
|---|---|
| `page_view` | `xdm.web.webPageDetails.pageViews`(표준 XDM 필드) |
| `session_start` | 세션 시작(자동, 데이터 보기 세션 정의당) |
| `first_visit` | [!UICONTROL 첫 번째 세션] 세그먼트 |
| `scroll` | 사용자 지정 이벤트(명시적 구현 매핑 필요) |
| `click` | `xdm.web.webInteraction`개 필드(구현 필요) |
| `video_start` / `video_complete` | 미디어 컬렉션 스키마 필드(Adobe 스트리밍 미디어 서비스 포함) |
| `purchase` | `xdm.commerce.purchases`, `xdm.commerce.order`(표준 XDM 상거래 스키마) |
| `add_to_cart` | `xdm.commerce.productListAdds`(표준 XDM 상거래 스키마) |

>[!NOTE]
>
>웹 SDK을 사용하여 구현할 때 GA4의 향상된 측정 이벤트(예: 스크롤, 파일 다운로드 또는 비디오)에는 XDM 필드에 대한 명시적 매핑이 필요합니다. GA4의 SDK이 처리하는 것과 같은 방식으로 자동 수집되지 않습니다.

## 사용자 지정 이벤트 및 매개 변수

GA4에서 사용자 지정 이벤트에는 이름과 최대 25개의 매개 변수가 있습니다. Customer Journey Analytics에서 사용자 지정 이벤트는 구현 중에 정의된 사용자 지정 XDM 스키마 필드에 매핑됩니다.

* **이벤트 이름**&#x200B;이(가) XDM 필드의 필드 값이 됩니다(일반적으로 [`xdm.eventType`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent)).
* 각 **parameter**&#x200B;은(는) 별도의 XDM 스키마 필드가 됩니다. [데이터 보기를 구성](/help/data-views/component-settings/overview.md)할 때 모든 XDM 필드가 차원 또는 지표로 노출될 수 있습니다.

>[!NOTE]
>
>조직의 사용자 지정 이벤트에 대한 특정 XDM 필드 경로는 웹 SDK 구현 중에 결정됩니다. 보고서를 작성하기 전에 구현 팀과 협력하여 특정 필드 매핑을 이해합니다. 자세한 내용은 [스키마 설계](../cja-upgrade/cja-upgrade-schema-architect.md)를 참조하십시오.

## 사용자 속성

GA4 사용자 속성은 사용자에 설정된 영구 속성입니다(예: `membership_tier` 또는 `account_type`). Customer Journey Analytics에서 이러한 데이터는 플랫폼의 **프로필 데이터 세트**&#x200B;에 매핑됩니다.

프로필 데이터 세트는 이벤트 데이터와 별도로 수집되며 공유 개인 ID를 사용하여 Customer Journey Analytics에서 이 데이터 세트에 결합됩니다. 이 컨텍스트에서 사용되는 일반적인 개인 ID에는 고객 ID 또는 이메일 해시가 포함됩니다. 참여하면 해당 프로필 속성을 이벤트 수준 데이터와 함께 Analysis Workspace의 차원으로 사용할 수 있습니다.

이 접근 방식을 사용하면 Customer Journey Analytics에서 GA4의 사용자 속성 모델보다 더 많은 유연성을 사용할 수 있습니다. GA4는 SDK에 정의된 사용자 속성으로 사용자를 제한하지만, Customer Journey Analytics 프로필 데이터 세트는 결합 가능한 식별자를 공유하는 한 모든 시스템(CRM, 로열티 플랫폼, 지원 레코드)의 모든 속성을 포함할 수 있습니다.

조직에서 여전히 GA 데이터를 Adobe Experience Platform으로 가져와야 하는 경우, 관리자 관련 설정 가이드는 [Google Analytics 내역 데이터 수집](/help/use-cases/third-party/ga/backfill.md) 및 [Google Analytics 데이터 스트리밍 구성](/help/use-cases/third-party/ga/streaming.md)을 참조하십시오.
