---
title: Customer Journey Analytics와 Adobe Journey Optimizer 통합
description: Adobe Journey Optimizer에서 생성한 데이터를 가져와 Customer Journey Analytics 내에서 Analysis Workspace을 사용하여 분석합니다.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
source-git-commit: 2429c60cab701017702e3312770232aa329e303c
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 68%

---

# Adobe Journey Optimizer과 Adobe Customer Journey Analytics 통합

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html)를 사용하여 연관성 있고 상황에 맞는 개인화된 경험을 제공할 수 있습니다. 이를 사용하여 고객에게 고객 여정의 다음 단계를 안내할 수 있습니다.

다음 단계를 수행하여 Journey Optimizer에서 생성된 데이터를 가져와 Customer Journey Analytics에서 고급 분석을 수행할 수 있습니다.

## Journey Optimizer의 데이터를 Adobe Experience Platform에 전송

Adobe Experience Platform은 Journey Optimizer와 Customer Journey Analytics 사이를 연결하는 중앙 데이터 소스의 역할을 합니다. Journey Optimizer 데이터를 플랫폼에 데이터 세트로 전송하는 방법에 대한 절차는 Journey Optimizer 사용 안내서의 [데이터 세트 시작하기](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html)를 참조하십시오.

## Customer Journey Analytics에 연결 만들기

Journey Optimizer 데이터가 Adobe Experience Platform에 있으면 다음 작업을 수행할 수 있습니다 [연결 만들기](/help/connections/create-connection.md) Journey Optimizer 데이터 세트를 기반으로 합니다. 또는 기존 연결에 Journey Optimizer 데이터 세트를 추가할 수 있습니다.

다음 데이터 세트를 선택하고 구성합니다.

| 데이터 세트 | 데이터 세트 유형 | 연결 설정 | 설명 |
| --- | --- | --- | --- |
| AJO 메시지 피드백 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | 와 같은 메시지 게재 이벤트를 포함합니다.[!UICONTROL 전송 횟수]&#39; 및 &#39;[!UICONTROL 바운스]&#39;. |
| AJO 이메일 추적 경험 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | 와 같은 이메일 추적 이벤트 포함[!UICONTROL 열림]&#39;, &#39;[!UICONTROL 클릭수]&#39;, &#39;[!UICONTROL 구독 취소]&#39;. |
| AJO 푸시 추적 경험 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | 와 같은 푸시 추적 이벤트 포함[!UICONTROL 앱 실행]&#39;. |
| 여정 단계 이벤트 | 이벤트 | 개인 ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | 여정의 각 노드에 참여한 프로필을 표시하는 이벤트를 포함합니다. |
| AJO 엔티티 데이터 세트 | 조회 | 키: `_id`<br>일치하는 키: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 여정 및 캠페인 메타데이터를 모든 Adobe Journey Optimizer 이벤트 데이터에 연결하는 분류를 포함합니다. |

{style="table-layout:auto"}


## Journey Optimizer 차원 및 지표를 포함하도록 데이터 보기 구성

연결을 만든 다음에는 하나 이상의 [데이터 보기](/help/data-views/create-dataview.md)를 만들어 Customer Journey Analytics에서 사용할 수 있는 차원 및 지표를 구성할 수 있습니다.

>[!NOTE]
>
>Adobe Journey Optimizer과 Customer Journey Analytics 간의 데이터 불일치는 일반적으로 1~2% 미만입니다. 최근 2시간 이내에 수집된 데이터의 경우 더 큰 불일치가 발생할 수 있습니다. 오늘을 제외한 날짜 범위를 사용하여 처리 시간을 포함한 불일치를 완화할 수 있습니다.


### 데이터 보기에서 차원 구성

데이터 보기에서 다음 차원을 만들어 Journey Optimizer에 있는 유사한 차원과 거의 정확한 동등성을 달성할 수 있습니다. 차원 사용자 정의 옵션에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

| 차원 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- |
| 여정 이름 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 구성 요소 유형: 차원 |
| 여정 이름 및 버전 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | 구성 요소 유형: 차원 |
| 여정 노드 이름 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 구성 요소 유형: 차원 |
| 여정 노드 유형 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | 구성 요소 유형: 차원 |
| 캠페인 이름 | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | 구성 요소 유형: 차원 |
| 채널 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | 구성 요소 유형: 차원 |
| 푸시 제목 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | 구성 요소 유형: 차원 |
| 이메일 제목 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | 구성 요소 유형: 차원 |
| 링크 레이블 | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | 구성 요소 유형: 차원 |
| 실험 이름 | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | 구성 요소 유형: 차원<br>컨텍스트 레이블: 실험 |
| 처리 이름 | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | 구성 요소 유형: 차원<br>컨텍스트 레이블: 실험 변형 |
| 이메일 게재 실패 이유 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | 구성 요소 유형: 차원 |
| 이메일 게재 제외 이유 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | 구성 요소 유형: 차원 |
| 요소 레이블 | `_experience.decisioning.propositionAction.label` | 구성 요소 유형: 차원 |

{style="table-layout:auto"}

### 데이터 보기에서 지표 구성

데이터 보기에서 다음 지표를 만들어 Journey Optimizer에 있는 유사한 지표와 거의 정확한 동등성을 달성할 수 있습니다. 지표 사용자 정의 옵션에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

| 지표 | 설명 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- | --- |
| 반송 | 반송된 메시지 수, 즉시 반송 및 게재 후 반송을 모두 포함합니다. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: 기준이 충족되는 경우<br>다음과 같음: `bounce`, 다음과 같음: `denylist` |
| 게재 후 반송 | 일부 이메일 서비스는 게재된 이메일을 보고한 다음 나중에 반송합니다. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | 구성 요소 유형: 지표<br>제외 값 포함: `async`와 같음 |
| 이메일 클릭 | 메시지 내 클릭 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: `click`와 같음 |
| 이메일 열림 | 열린 메시지 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: `open`와 같음 |
| 오류 | 오류가 발생한 메시지 수. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: `error`와 같음 |
| 제외 | 제외된 메시지 수. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: `exclude`와 같음 |
| 전송함 | 이메일 공급자가 수락한 메시지 수. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: `sent`와 같음 |
| 스팸 고객 불만 | 접수된 스팸 불만 사항 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: `spam_complaint`와 같음 |
| 구독 취소 | 구독 취소 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: `unsubscribe`와 같음 |
| Edge 전송 횟수 | Edge 네트워크가 웹 또는 모바일 SDK에 메시지를 보내는 횟수 | 스키마 문자열 요소 사용 `_experience.decisioning.propositionEventType.send` |
| 인바운드 디스플레이 | 사용자에게 웹 또는 인앱 메시지가 표시되는 횟수 | 스키마 문자열 요소 사용 `_experience.decisioning.propositionEventType.display` |
| 인바운드 클릭수 | 웹 또는 인앱 메시지 클릭 수 | 스키마 문자열 요소 사용 `_experience.decisioning.propositionEventType.interact` |
| InApp 트리거 | 의사 결정 엔진이 메시지를 표시해야 하는 횟수. Mobile SDK는 실제 디스플레이 수를 줄이는 결정을 무시할 수 있습니다. | 스키마 문자열 요소 사용 `_experience.decisioning.propositionEventType.trigger` |
| InApp 취소 | SDK가 UI에서 인앱 메시지를 제거한 횟수 | 스키마 문자열 요소 사용 `_experience.decisioning.propositionEventType.dismiss` |

{style="table-layout:auto"}

### Analysis Workspace에서 계산된 지표 구성

Journey Optimizer 데이터 세트에 대해 원하는 차원 및 지표를 구성했으면 해당 데이터에 대한 추가적인 인사이트를 위해 [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md)를 구성할 수도 있습니다. 이러한 계산된 지표는 데이터 보기 관리자에서 생성된 위 지표를 기반으로 합니다.

| 계산된 지표 | 설명 | 공식 |
| --- | --- | --- |
| 메시지 전송 | 전송된 총 메시지 수. 성공 또는 실패한 메시지 포함. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 게재된 메시지 | 고객에게 전달된 이메일 수. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
