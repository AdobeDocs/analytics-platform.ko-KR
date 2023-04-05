---
title: CJA(Adobe Journey Optimizer 의사 결정 관리)와 Customer Journey Analytics 통합
description: Adobe Journey Optimizer 의사 결정 관리에서 생성한 데이터를 가져와 Customer Journey Analytics 내에서 Analysis Workspace을 사용하여 분석합니다.
source-git-commit: f9ee0db464c49339bc36b144e18ef4aea4f4f033
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 18%

---

# 의사 결정 관리와 Customer Journey Analytics 통합


Adobe Journey Optimizer [의사 결정 관리](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) Adobe Experience Platform에서 만든 풍부한 실시간 프로필에 규칙과 제한을 적용하여 고객에게 적합한 오퍼를 적시에 보낼 수 있도록 하는 마케팅 오퍼의 중앙 라이브러리 및 의사 결정 엔진을 사용하여 개인화를 쉽게 할 수 있습니다.

의사 결정 관리는 AJO(Adobe Journey Optimizer)의 일부이며 AJO)와 통합됩니다. 또한 풍부한 기능을 사용하여 AJO에 정의된 여정 및 캠페인과 독립적으로 사용할 수도 있습니다 [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) 지원.

다음 단계를 수행하여 결정 관리에서 생성한 데이터를 가져와서 CJA(Customer Journey Analytics)에서 고급 분석을 수행할 수 있습니다.

## 의사 결정 관리에서 Adobe Experience Platform으로 데이터 보내기

Adobe Experience Platform은 의사 결정 관리와 Customer Journey Analytics 간의 중앙 데이터 소스 및 링크 역할을 합니다. 의사 결정 관리의 데이터는 Experience Platform에 수집됩니다 **자동으로** 또는 의 일부로 **명시적으로 보낸 경험 이벤트** (예: 노출 횟수 또는 클릭 수). 자세한 내용은 [데이터 수집 시작](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) 자세한 내용

## 연결 만들기

의사 결정 관리 데이터가 Adobe Experience Platform에 있으면 [연결](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ko-KR) 결정 관리 데이터 세트 기반. 또는 기존 연결에 결정 관리 데이터 세트를 추가할 수 있습니다.

다음 데이터 세트를 선택하고 구성합니다.

| 데이터 세트 | 데이터 세트 유형 | 연결 설정 | 설명 |
| --- | --- | --- | --- |
| ODE DecisionEvents - _샌드박스_ 의사 결정 | 이벤트 | 개인 ID: `IdentityMap` | 의사 결정 관리 의사 결정 이벤트에 대해 자동으로 생성된 데이터를 포함합니다. _샌드박스_ 는 특정 샌드박스 이름을 나타냅니다. |
| AJO 메시지 피드백 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | 메시지 게재 이벤트를 포함합니다. |
| AJO 이메일 추적 경험 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | 이메일 추적 이벤트를 포함합니다. |
| AJO 푸시 추적 경험 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | 푸시 추적 이벤트를 포함합니다. |
| AJO 엔티티 데이터 세트 | 조회 | 키: `_id`<br>일치하는 키: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 모든 AJO 이벤트 데이터에 여정 및 캠페인 메타데이터를 연결하는 분류를 포함합니다. |

{style="table-layout:auto"}

## 데이터 보기 만들기

연결이 만들어지면 하나 이상의 연결을 만들 수 있습니다 [데이터 보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ko-KR) cja에서 사용할 수 있는 원하는 차원 및 지표를 구성하려면 다음을 수행하십시오.

>[!NOTE]
>
>AJO와 CJA 간의 데이터 불일치는 일반적으로 1~2% 미만입니다. 최근 2시간 이내에 수집된 데이터의 경우 더 큰 불일치가 발생할 수 있습니다. 오늘을 제외한 날짜 범위를 사용하여 처리 시간을 포함한 불일치를 완화할 수 있습니다.

### 차원 구성

데이터 보기에서 다음 차원을 만들어 결정 관리에서 비슷한 차원과 대략적인 패리티를 달성할 수 있습니다. 차원 사용자 정의 옵션에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

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

데이터 보기에서 다음 지표를 만들어 결정 관리에서 유사한 지표와 대략적인 패리티를 달성할 수 있습니다. 지표 사용자 정의 옵션에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

| 지표 | 설명 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- | --- |
| 이벤트 유형(예: 특정 이벤트를 참조하는 이름 변경) `Feedback` 대상 `message.feedback`) [1] | 특정 유형의 이벤트 양 | `eventType` | 구성 요소 유형: 지표<br/>**[!UICONTROL 포함 제외 값 설정&#x200B;]**: 설정<br/>**[!UICONTROL 일치]**: [!UICONTROL 모든 기준이 충족되는 경우]<br/>**[!UICONTROL 기준&#x200B;]**:**[!UICONTROL &#x200B;다음과 같음&#x200B;]**`message.feedback` |
| 결정 옵션 점수 | 단일 범위 컨텍스트에서 결정 옵션에 대한 계산된 값입니다. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | 구성 요소 유형: 지표 |
| 대체 결정 옵션 점수 | 단일 범위 컨텍스트에서 대체 결정 옵션에 대한 계산된 값입니다. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | 구성 요소 유형: 지표 |
| 오퍼 해제 | 다른 직접적인 상호 작용 없이 무시되거나 거부된 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.display` | 구성 요소 유형: 지표 |
| 오퍼 표시 | 프로필에 표시되는 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.display` | 구성 요소 유형: 지표 |
| 오퍼 상호 작용 | 프로필에 표시되는 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.interact` | 구성 요소 유형: 지표 |
| 오퍼 보내기 | 프로필로 보낸 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.send` | 구성 요소 유형: 지표 |
| 오퍼 트리거 | 클라이언트 SDK에서 표시하도록 선택한 오퍼 수입니다. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 구성 요소 유형: 지표 |
| 오퍼 구독 취소 | 프로필에서 요청한 오퍼 수가 향후에 표시되지 않습니다. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 구성 요소 유형: 지표 |

{style="table-layout:auto"}
[1] 사용 가능한 다양한 이벤트 유형에 대해 여러 지표를 정의할 수 있습니다. 자세한 내용은 [제외 값 구성 요소 설정 포함](/help/data-views/component-settings/include-exclude-values.md) 추가 정보.
