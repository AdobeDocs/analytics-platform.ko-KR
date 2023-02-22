---
title: AJO(Adobe Journey Optimizer)을 Customer Journey Analytics(CJA)와 통합
description: AJO에서 생성된 데이터를 가져오고 CJA 내에서 Analysis Workspace를 사용하여 가져온 데이터를 분석하십시오.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: 3a4dbe9a87f8e195a4daf78423d29d73f2be0f83
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 53%

---

# Customer Journey Analytics와 Adobe Journey Optimizer 통합

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html)를 사용하여 연관성 있고 상황에 맞는 개인화된 경험을 제공할 수 있습니다. 이를 사용하여 고객에게 고객 여정의 다음 단계를 안내할 수 있습니다.

다음 단계를 수행하여 Journey Optimizer에서 생성된 데이터를 가져와 Customer Journey Analytics에서 고급 분석을 수행할 수 있습니다.

## Journey Optimizer의 데이터를 Adobe Experience Platform에 전송

Adobe Experience Platform은 Journey Optimizer와 Customer Journey Analytics 사이를 연결하는 중앙 데이터 소스의 역할을 합니다. Journey Optimizer 데이터를 플랫폼에 데이터 세트로 전송하는 방법에 대한 절차는 Journey Optimizer 사용 안내서의 [데이터 세트 시작하기](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html)를 참조하십시오.

## Customer Journey Analytics에 연결 만들기

Journey Optimizer 데이터를 Adobe Experience Platform으로 가져온 다음에는 Journey Optimizer 데이터 세트를 기반으로 [연결을 만들](/help/connections/create-connection.md) 수 있습니다. 플랫폼으로 전송한 데이터 세트를 선택합니다.

## Journey Optimizer 차원 및 지표를 포함하도록 데이터 보기 구성

연결을 만든 다음에는 하나 이상의 [데이터 보기](/help/data-views/create-dataview.md)를 만들어 Customer Journey Analytics에서 사용할 수 있는 차원 및 지표를 구성할 수 있습니다.

>!![NOTE]
AJO와 CJA 간의 데이터 불일치는 일반적으로 1-2% 미만입니다. 지난 2시간 내에 수집된 데이터에 대해 더 큰 불일치가 발생할 수 있습니다. 오늘을 제외한 날짜 범위를 사용하여 처리 시간을 포함한 불일치를 완화할 수 있습니다.

### 데이터 보기에서 차원 구성

데이터 보기에서 다음 차원을 만들어 Journey Optimizer의 유사한 차원과 대략적인 패리티를 달성할 수 있습니다. 자세한 내용은 [구성 요소 설정](/help/data-views/component-settings/overview.md) 데이터 보기 관리자에서 차원 사용자 지정 옵션에 대한 세부 사항을 살펴보십시오.

| 차원 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- |
| 여정 이름 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 구성 요소 유형: Dimension |
| 여정 이름 및 버전 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | 구성 요소 유형: Dimension |
| 여정 노드 이름 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 구성 요소 유형: Dimension |
| 여정 노드 유형 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | 구성 요소 유형: Dimension |
| 캠페인 이름 | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | 구성 요소 유형: Dimension |
| Channel | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | 구성 요소 유형: Dimension |
| 푸시 제목 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | 구성 요소 유형: Dimension |
| 이메일 제목 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | 구성 요소 유형: Dimension |
| 링크 레이블 | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | 구성 요소 유형: Dimension |
| 실험 이름 | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | 구성 요소 유형: Dimension<br>컨텍스트 레이블: 실험 실험 실험 |
| 치료 이름 | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | 구성 요소 유형: Dimension<br>컨텍스트 레이블: 실험 변형 |
| 이메일 게재 실패 이유 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | 구성 요소 유형: Dimension |
| 전자 메일 게재 제외 이유 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | 구성 요소 유형: Dimension |

{style=&quot;table-layout:auto&quot;}

### 데이터 보기에서 지표 구성

데이터 보기에서 다음 지표를 만들어 Journey Optimizer에 있는 유사한 지표와 거의 정확한 동등성을 달성할 수 있습니다. 자세한 내용은 [구성 요소 설정](/help/data-views/component-settings/overview.md) 데이터 보기 관리자에서 지표 사용자 지정 옵션에 대한 세부 사항을 확인합니다.

| 지표 | 설명 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- | --- |
| 반송 | 반송된 메시지 수게재 후 즉시 바운스 수 및 바운스 수를 모두 포함합니다. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: 기준이 충족되는 경우<br>다음과 같음: `bounce`, 다음과 같음: `denylist` |
| 게재 후 바운스 수 | 일부 이메일 서비스는 이메일을 배달한 다음 나중에 전송합니다. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | 구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `async` |
| 이메일 클릭 수 | 메시지 내 클릭 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `click` |
| 이메일 열기 | 열린 메시지 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `open` |
| 오류 | 오류가 발생한 메시지 수. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `error` |
| 제외 | 제외된 메시지 수. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `exclude` |
| 전송함 | 이메일 공급자가 수락한 메시지 수입니다. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `sent` |
| 스팸 불만 | 접수된 스팸 불만 사항 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `spam_complaint` |
| 구독 취소 | 구독 취소 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `unsubscribe` |

{style=&quot;table-layout:auto&quot;}

### Analysis Workspace에서 계산된 지표 구성

Journey Optimizer 데이터 세트에 대해 원하는 차원 및 지표를 구성했으면 해당 데이터에 대한 추가적인 인사이트를 위해 [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md)를 구성할 수도 있습니다. 이러한 계산된 지표는 데이터 보기 관리자에서 생성된 위 지표를 기반으로 합니다.

| 계산된 지표 | 설명 | 공식 |
| --- | --- | --- |
| 보낸 메시지 | 보낸 총 메시지 수입니다. 성공 또는 실패한 메시지를 포함합니다. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 배달된 메시지 | 고객에게 배달되는 이메일 수입니다. | `[Sends] - [Bounces After Delivery]` |

{style=&quot;table-layout:auto&quot;}
