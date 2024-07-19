---
title: Customer Journey Analytics와 Adobe Journey Optimizer 통합
description: Adobe Journey Optimizer에서 생성된 데이터를 가져와 Customer Journey Analytics 내의 Analysis Workspace를 사용하여 분석합니다.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 13c3f99dba7725553c775df4492803f759ebead5
workflow-type: tm+mt
source-wordcount: '1541'
ht-degree: 100%

---

# Customer Journey Analytics와 Journey Optimizer 통합

[Adobe Journey Optimizer](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/get-started/get-started)를 사용하여 연관성 있고 상황에 맞는 개인화된 경험을 제공할 수 있습니다. 이를 사용하여 고객에게 고객 여정의 다음 단계를 안내할 수 있습니다.

Journey Optimizer에서 생성된 데이터를 구성해 Customer Journey Analytics에서 고급 분석을 수행할 수 있습니다. 이 통합은 자동 구성할 수 있습니다. 필요한 경우 연결 또는 데이터 보기에서 사용 가능한 데이터 세트, 차원 또는 지표를 추가로 수동 사용자 정의할 수 있습니다.

## Journey Optimizer 통합 자동 구성

{{release-limited-testing-section}}

Journey Optimizer는 보고 엔진으로 Customer Journey Analytics 사용을 지원합니다. Journey Optimizer 설명서에서 [새 보고 인터페이스 시작](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/channel-report/report-gs-cja)을 참조하시기 바랍니다.

Journey Optimizer용 Customer Journey Analytics 보고를 활성화하면 자동으로 특성 샌드박스에 대한 [연결](/help/connections/overview.md) 및 [데이터 보기](/help/data-views/data-views.md)가 생성됩니다.

### 연결

연결의 이름은 **[!UICONTROL AJO 활성화된 연결(*샌드박스 이름*)]**&#x200B;이며 구성 및 데이터세트에 대해 다음과 같은 기본 값을 가집니다.

| **연결 설정** | 값 |
|---|---| 
| [!UICONTROL 연결 이름] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL 연결 설명] | [!UICONTROL *연결을 설명해 주십시오.*] |
| [!UICONTROL 태그] | [!UICONTROL *태그 선택*] |


| **데이터 설정** | 값 |
|---|---| 
| [!UICONTROL 롤링 데이터 기간 활성화] | 활성화됨. [!UICONTROL 선택된 개월 수] `13`. |
| [!UICONTROL 샌드박스] | [!UICONTROL *샌드박스 이름*] (비활성화됨, 이 설정은 수정할 수 없음). |
| [!UICONTROL 일일 평균 이벤트 수] | 백만 개 미만(비활성화됨, 이 설정은 수정할 수 없음). |


| 데이터 세트 이름 | 스키마 | 데이터 세트 유형 | 데이터 소스 유형 | 개인 ID | 키 | 일치하는 키 | 새 데이터 가져오기 | 데이터 채우기 |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO 엔티티 데이터 세트] | [!UICONTROL AJO 엔티티 레코드 스키마] | [!UICONTROL 조회] | [!UICONTROL 기타] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![녹색 상태](assets/../../connections/assets/status-green.svg) 켜짐 | ![회색 상태](assets/../../connections/assets/status-gray.svg) 꺼짐 |
| [!UICONTROL 여정 단계 이벤트] | [!UICONTROL Journey Orchestration용 여정 단계 이벤트 스키마] | [!UICONTROL 이벤트] | [!UICONTROL 기타] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![녹색 상태](assets/../../connections/assets/status-green.svg) 켜짐 | ![회색 상태](assets/../../connections/assets/status-gray.svg) 꺼짐 |
| [!UICONTROL AJO 이메일 추적 경험 이벤트 데이터 세트] | [!UICONTROL AJO 이메일 추적 경험 이벤트 스키마] | [!UICONTROL 이벤트] | [!UICONTROL 기타] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![녹색 상태](assets/../../connections/assets/status-green.svg) 켜짐 | ![회색 상태](assets/../../connections/assets/status-gray.svg) 꺼짐 |
| [!UICONTROL AJO 이메일 추적 경험 이벤트 데이터 세트] | [!UICONTROL AJO 이메일 추적 경험 이벤트 스키마] | [!UICONTROL 이벤트] | [!UICONTROL 기타] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![녹색 상태](assets/../../connections/assets/status-green.svg) 켜짐 | ![회색 상태](assets/../../connections/assets/status-gray.svg) 꺼짐 |
| [!UICONTROL AJO 메시지 피드백 이벤트 데이터 세트] | [!UICONTROL AJO 메시지 피드백 이벤트 스키마] | [!UICONTROL 이벤트] | [!UICONTROL 기타] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![녹색 상태](assets/../../connections/assets/status-green.svg) 켜짐 | ![회색 상태](assets/../../connections/assets/status-gray.svg) 꺼짐 |
| [!UICONTROL AJO 푸시 추적 경험 이벤트 데이터 세트] | [!UICONTROL AJO 푸시 추적 경험 이벤트 스키마] | [!UICONTROL 이벤트] | [!UICONTROL 기타] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![녹색 상태](assets/../../connections/assets/status-green.svg) 켜짐 | ![회색 상태](assets/../../connections/assets/status-gray.svg) 꺼짐 |


### 데이터 보기

이 데이터 보기의 이름은 **AJO 활성화 데이터 보기(*샌드박스 이름*)**&#x200B;입니다.

- **[!UICONTROL 구성]** 탭에는 다음과 같은 값이 기본적으로 구성되어 있습니다.

  | 설정 | 값 |
  |---|---|
  | [!UICONTROL 연결] | AJO 지원 연결(*샌드박스 이름*) |
  | [!UICONTROL 이름] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL 외부 ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_`(이름에서 파생) |
  | [!UICONTROL 설명] | `undefined` |

  {style="table-layout:fixed"}

  | 호환성 | 값 |
  |---|---|
  | [!UICONTROL Adobe Journey Optimizer에서 기본 데이터 보기로 설정] | 활성화됨(기본값).<br/><br/>이 구성 옵션을 사용하면 수동 구성 없이도 Journey Optimizer와 사용할 데이터 보기를 지정할 수 있습니다. 이 구성 옵션을 활성화(이미 기본적으로 활성화되어 있지 않은 경우)하는 방법에 대한 자세한 내용은 [데이터 보기 만들기 또는 편집](/help/data-views/create-dataview.md)의 [호환성](/help/data-views/create-dataview.md#compatibility) 섹션을 참조하십시오. <br/><br/>옵션을 비활성화하면 기본 데이터 보기를 계속 변경해 둘 것인지 묻는 대화 상자가 나타납니다. **[!UICONTROL 계속]**&#x200B;을 선택하면 기본 데이터 보기로 다른 데이터 보기를 선택해야 합니다. 선택 사항을 확인하려면 **[!UICONTROL 확인]**&#x200B;을 선택합니다. 기본 데이터 보기 변경을 취소하려면 **[!UICONTROL 취소]**&#x200B;를 선택합니다. |

  | 컨테이너 | 값 |
  |---|---|
  | [!UICONTROL 개인 컨테이너 이름] | `Person` |
  | [!UICONTROL 세션 컨테이너 이름] | `Session` |
  | [!UICONTROL 이벤트 컨테이너 이름] | `Event` |

  | 캘린더 | 값 |
  |---|---|
  | [!UICONTROL 시간대] | 사용자의 위치에 맞는 시간대 |
  | [!UICONTROL 캘린더 유형] | 양력 |
  | [!UICONTROL 한 해의 첫 번째 달] | 1월 |
  | [!UICONTROL 한 주의 첫 번째 날] | 일요일 |


- **구성 요소** 탭에서:
   - 이름에 [!UICONTROL (AJO)]가 붙은 모든 지표와 차원은 이 자동 구성의 일부로 자동 추가됩니다.
   - 자동으로 추가된 일부 지표 또는 차원은 파생 필드 기반입니다. 이들 파생 필드는 이 통합 기능을 위해 특별히 생성된 것입니다. 예를 들어 [!UICONTROL 랜딩 페이지 클릭수(AJO)] 지표는 [!UICONTROL 랜딩 페이지 클릭수] 파생 필드 기반입니다.
   - 일부 지표 또는 차원은 추가적인 구성을 갖고 있습니다. 예를 들어 [!UICONTROL 스팸 불만 사항(AJO)]에는 [!UICONTROL 포맷] 및 [!UICONTROL 제외 값 포함] 설정이 적용되어 있습니다.
   - 자동으로 추가된 모든 지표와 차원에는 `:`*`name_of_metric_or_dimension`*이라고 지정된 컨텍스트 레이블이 있습니다. 예를 들어 [!UICONTROL 랜딩 페이지 클릭수(AJO)] 지표에는 `:Landing page clicks (AJO)`라는 이름의 컨텍스트 레이블이 있습니다.

- **[!UICONTROL 설정]** 탭에는 특정한 구성 값이 적용되어 있지 않습니다

>[!IMPORTANT]
>
>연결 및 데이터 보기에 대해 자동 구성된 값을 수정하면 자동 구성된 Customer Journey Analytics 통합을 사용하는 Journey Optimizer 보고에 영향을 줍니다.


## Journey Optimizer와 함께 사용할 데이터 보기 수동 구성

다음 섹션에서는 Journey Optimizer에서 생성된 데이터를 수동으로 사용하여 Customer Journey Analytics에서 고급 분석을 수행하는 방법을 설명합니다. [자동 구성 옵션](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer)이 요구 사항을 충족하는 경우에는 이 작업이 필요하지 않습니다.

### Journey Optimizer의 데이터를 Experience Platform에 전송

Adobe Experience Platform은 Journey Optimizer와 Customer Journey Analytics 사이를 연결하는 중앙 데이터 소스의 역할을 합니다. Journey Optimizer 데이터를 Experience Platform에 데이터 세트로 전송하는 방법에 대한 절차는 Journey Optimizer 사용 안내서의 [데이터 세트 시작](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/data-management/datasets/get-started-datasets)을 참조하십시오.

### Customer Journey Analytics에 연결 만들기

Journey Optimizer 데이터를 Adobe Experience Platform으로 가져온 다음에는 Journey Optimizer 데이터 세트를 기반으로 [연결을 만들](/help/connections/create-connection.md) 수 있습니다. 또는 기존 연결에 Journey Optimizer 데이터 세트를 추가할 수 있습니다.

다음 데이터 세트를 선택하고 구성합니다.

| 데이터 세트 | 데이터 세트 유형 | 연결 설정 | 설명 |
| --- | --- | --- | --- |
| AJO 메시지 피드백 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | &#39;[!UICONTROL 전송]&#39; 및 &#39;[!UICONTROL 바운스]&#39;와 같은 메시지 게재 이벤트를 포함합니다. |
| AJO 이메일 추적 경험 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | &#39;[!UICONTROL 열람수]&#39;, &#39;[!UICONTROL 클릭수]&#39; 및 &#39;[!UICONTROL 구독 취소]&#39;과 같은 이메일 추적 이벤트를 포함합니다. |
| AJO 푸시 추적 경험 이벤트 데이터 세트 | 이벤트 | 개인 ID: `IdentityMap` | &#39;[!UICONTROL 앱 실행]&#39;과 같은 푸시 추적 이벤트를 포함합니다. |
| 여정 단계 이벤트 | 이벤트 | 개인 ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | 여정의 각 노드에 참여한 프로필을 보여 주는 이벤트를 포함합니다. |
| AJO 엔티티 데이터 세트 | 조회 | 키: `_id`<br>일치하는 키: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 여정 및 캠페인 메타데이터를 모든 Journey Optimizer 이벤트 데이터에 연결하는 분류를 포함합니다. |

{style="table-layout:auto"}


### Journey Optimizer 차원 및 지표를 포함하도록 데이터 보기 구성

연결을 만든 다음에는 하나 이상의 [데이터 보기](/help/data-views/create-dataview.md)를 만들어 Customer Journey Analytics에서 사용할 수 있는 차원 및 지표를 구성할 수 있습니다.

>[!NOTE]
>
>Journey Optimizer와 Customer Journey Analytics 간의 데이터 불일치는 일반적으로 1~2% 미만입니다. 최근 2시간 이내에 수집된 데이터의 경우 더 큰 불일치가 발생할 수 있습니다. 오늘을 제외한 날짜 범위를 사용하여 처리 시간을 포함한 불일치를 완화할 수 있습니다.


#### 데이터 보기에서 차원 구성

데이터 보기에서 다음 차원을 만들어 Journey Optimizer에 있는 유사한 차원과 거의 정확한 동등성을 달성할 수 있습니다. 차원 사용자 정의 옵션에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

| 차원 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- |
| 여정 이름 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 구성 요소 유형: 차원 |
| 여정 이름 및 버전 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | 구성 요소 유형: 차원 |
| 여정 노드 이름 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeName` | 구성 요소 유형: 차원 |
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

#### 데이터 보기에서 지표 구성

데이터 보기에서 다음 지표를 만들어 Journey Optimizer에 있는 유사한 지표와 거의 정확한 동등성을 달성할 수 있습니다. 지표 사용자 정의 옵션에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

| 지표 | 설명 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- | --- |
| 바운스 | 즉시 바운스 및 게재 후 바운스를 모두 포함하는 바운스된 메시지 수입니다. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: 기준이 충족되는 경우<br>다음과 같음: `bounce`, 다음과 같음: `denylist` |
| 게재 후 바운스 | 일부 이메일 서비스는 게재된 이메일을 보고한 다음 나중에 바운스합니다. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | 구성 요소 유형: 지표<br>제외 값 포함: `async`와 같음 |
| 이메일 클릭 | 메시지 내 클릭 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: `click`와 같음 |
| 이메일 열림 | 열린 메시지 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: `open`와 같음 |
| 오류 | 오류가 발생한 메시지 수입니다. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: `error`와 같음 |
| 제외 | 제외된 메시지 수입니다. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: `exclude`와 같음 |
| 전송함 | 이메일 공급자가 수락한 메시지 수. | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표<br>제외 값 포함: `sent`와 같음 |
| 스팸 고객 불만 | 접수된 스팸 불만 사항 수. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: `spam_complaint`와 같음 |
| 구독 취소 | 구독 취소 수입니다. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 구성 요소 유형: 지표<br>제외 값 포함: `unsubscribe`와 같음 |
| 에지 전송 | 에지 네트워크에서 Web 또는 Mobile SDK에 메시지를 전송한 횟수입니다. | 스키마 문자열 요소 `_experience.decisioning.propositionEventType.send` 사용 | |
| 인바운드 표시 | 웹 또는 인앱 메시지가 사용자에게 표시된 횟수 | 스키마 문자열 요소 `_experience.decisioning.propositionEventType.display` 사용 | |
| 인바운드 클릭 | 웹 또는 인앱 메시지 클릭수 | 스키마 문자열 요소 `_experience.decisioning.propositionEventType.interact` 사용 | |
| 인앱 트리거 | 의사 결정 엔진에서 메시지를 표시해야 한다고 제안한 횟수입니다. Mobile SDK는 결정을 무시할 수 있으며 이에 따라 실제 표시 수가 줄어들 수 있습니다. | 스키마 문자열 요소 `_experience.decisioning.propositionEventType.trigger` 사용 | |
| 인앱 취소 | SDK에서 UI에서 인앱 메시지를 제거한 횟수 | 스키마 문자열 요소 `_experience.decisioning.propositionEventType.dismiss` 사용 | |

{style="table-layout:auto"}

#### Analysis Workspace에서 계산된 지표 구성

Journey Optimizer 데이터 세트에 대해 원하는 차원 및 지표를 구성했으면 해당 데이터에 대한 추가적인 인사이트를 위해 [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md)를 구성할 수도 있습니다. 이러한 계산된 지표는 데이터 보기 관리자에서 만들어진 위 지표를 기반으로 합니다.

| 계산된 지표 | 설명 | 공식 |
| --- | --- | --- |
| 메시지 전송 | 전송된 총 메시지 수. 성공 또는 실패한 메시지 포함. | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 게재된 메시지 | 고객에게 전달된 이메일 수. | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
