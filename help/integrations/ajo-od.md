---
title: Adobe Journey Optimizer 의사 결정 관리를 Adobe Customer Journey Analytics과 통합
description: Adobe Journey Optimizer 의사 결정 관리에서 생성한 데이터를 가져와 Customer Journey Analytics 내에서 Analysis Workspace을 사용하여 분석합니다.
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 20%

---

# Adobe Customer Journey Analytics과 의사 결정 관리 통합


Adobe Journey Optimizer [의사 결정 관리](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) 마케팅 오퍼의 중앙 라이브러리와 Adobe Experience Platform에서 만든 풍부한 실시간 프로필에 규칙과 제한을 적용하여 고객에게 적시에 적절한 오퍼를 제공하도록 도와주는 의사 결정 엔진을 통해 손쉽게 개인화할 수 있습니다.

의사 결정 관리는 Adobe Journey Optimizer의 일부이며 과 통합됩니다. 또한 풍부한 기능을 사용하여 Adobe Journey Optimizer에 정의된 여정 및 캠페인과 독립적으로 사용할 수도 있습니다 [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) 지원.

다음 단계를 수행하여 의사 결정 관리에서 생성된 데이터를 가져와 Customer Journey Analytics에서 고급 분석을 수행할 수 있습니다.

## 의사 결정 관리에서 Adobe Experience Platform으로 데이터 보내기

Adobe Experience Platform은 의사 결정 관리와 Customer Journey Analytics 간의 중앙 데이터 소스 및 연결 역할을 합니다. 의사 결정 관리의 데이터가 Experience Platform에 수집됩니다. **자동으로** 또는 의 일부로서 **명시적으로 전송된 경험 이벤트** (예: 노출 횟수 또는 클릭 수). 다음을 참조하십시오 [데이터 수집 시작하기](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) 을 참조하십시오.

## 연결 만들기

의사 결정 관리 데이터가 Adobe Experience Platform에 있으면 [연결](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ko-KR) 의사 결정 관리 데이터 세트를 기반으로 합니다. 또는 의사 결정 관리 데이터 세트를 기존 연결에 추가할 수 있습니다.

다음 데이터 세트를 선택하고 구성합니다.

| 데이터 세트 | 데이터 세트 유형 | 연결 설정 | 설명 |
| --- | --- | --- | --- |
| ODE DecisionEvents - _샌드박스_ 의사 결정 | 이벤트 | 개인 ID: `IdentityMap` | [의사 결정 관리] 의사 결정 이벤트에 대해 자동 생성된 데이터를 포함합니다. _샌드박스_ 는 특정 샌드박스 이름을 나타냅니다. |
| Adobe Journey Optimizer 메시지 피드백 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | 메시지 게재 이벤트를 포함합니다. |
| Adobe Journey Optimizer 이메일 추적 경험 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | 이메일 추적 이벤트를 포함합니다. |
| Adobe Journey Optimizer 푸시 추적 경험 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | 푸시 추적 이벤트를 포함합니다. |
| Adobe Journey Optimizer 엔티티 데이터 세트 | 조회 | 키: `_id`<br>일치하는 키: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 여정 및 캠페인 메타데이터를 모든 Adobe Journey Optimizer 이벤트 데이터에 연결하는 분류를 포함합니다. |

{style="table-layout:auto"}

## 데이터 보기 만들기

연결을 만든 다음에는 하나 이상의 [데이터 보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ko-KR)를 만들어 Customer Journey Analytics에서 사용할 수 있는 차원 및 지표를 구성할 수 있습니다.

>[!NOTE]
>
>Adobe Journey Optimizer과 Customer Journey Analytics 간의 데이터 불일치는 일반적으로 1~2% 미만입니다. 최근 2시간 이내에 수집된 데이터의 경우 더 큰 불일치가 발생할 수 있습니다. 오늘을 제외한 날짜 범위를 사용하여 처리 시간을 포함한 불일치를 완화할 수 있습니다.

### 차원 구성

데이터 보기에서 다음 차원을 만들어 의사 결정 관리의 유사한 차원과 거의 동일한 결과를 얻을 수 있습니다. 차원 사용자 정의 옵션에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

| 차원 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- |
| 활동 이름 | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | 구성 요소 유형: 차원 |
| 컨테이너 식별자 | `_experience.decisioning.containerID` | 구성 요소 유형: 차원 |
| 상관 관계 식별자 | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | 구성 요소 유형: 차원 |
| 결정 옵션 이름 | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | 구성 요소 유형: 차원 |
| 대체 결정 옵션 이름 | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | 구성 요소 유형: 차원 |
| 배치 이름 | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | 구성 요소 유형: 차원 |

{style="table-layout:auto"}


### 지표 구성

데이터 보기에서 다음 지표를 만들어 의사 결정 관리의 유사한 지표와 거의 동등성을 달성할 수 있습니다. 지표 사용자 정의 옵션에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

| 지표 | 설명 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- | --- |
| 이벤트 유형(예: 특정 이벤트를 참조하도록 이름 바꾸기) `Feedback` 대상 `message.feedback`) [1] | 특정 유형의 이벤트 금액 | `eventType` | 구성 요소 유형: 지표<br/>**[!UICONTROL 포함/제외 값 설정&#x200B;]**: 켜짐<br/>**[!UICONTROL 일치]**: [!UICONTROL 모든 기준이 충족되는 경우]<br/>**[!UICONTROL 기준&#x200B;]**:**[!UICONTROL &#x200B;다음과 같음&#x200B;]**`message.feedback` |
| 의사 결정 옵션 점수 | 단일 범위의 컨텍스트에서 결정 옵션에 대해 계산된 값입니다. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | 구성 요소 유형: 지표 |
| 대체 결정 옵션 점수 | 단일 범위의 컨텍스트에서 대체 결정 옵션에 대해 계산된 값입니다. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | 구성 요소 유형: 지표 |
| 오퍼 닫기 | 다른 직접적인 상호 작용 없이 거부되거나 거부된 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.display` | 구성 요소 유형: 지표 |
| 오퍼 표시 | 프로필에 표시된 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.display` | 구성 요소 유형: 지표 |
| 오퍼 상호 작용 | 프로필에 표시된 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.interact` | 구성 요소 유형: 지표 |
| 오퍼 보내기 | 프로필로 전송된 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.send` | 구성 요소 유형: 지표 |
| 오퍼 트리거 | 클라이언트 SDK에서 표시하도록 선택한 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 구성 요소 유형: 지표 |
| 오퍼 구독 취소 | 나중에 표시되지 않도록 프로필에서 요청한 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 구성 요소 유형: 지표 |

{style="table-layout:auto"}

[1] 사용 가능한 다양한 이벤트 유형에 대해 여러 지표를 정의할 수 있습니다. 다음을 참조하십시오 [포함/제외 값 구성 요소 설정](/help/data-views/component-settings/include-exclude-values.md) 추가 정보.
