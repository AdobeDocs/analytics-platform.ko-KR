---
title: Adobe Journey Optimizer 통합
description: Adobe Journey Optimizer에서 생성된 데이터를 가져와 Customer Journey Analytics 내의 Analysis Workspace를 사용하여 분석합니다.
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 979564d0249abadd454ce43aba9aeae2c78a44f0
workflow-type: ht
source-wordcount: '3020'
ht-degree: 100%

---

# Journey Optimizer 통합

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
| [!UICONTROL AJO 엔티티 데이터 세트] | [!UICONTROL AJO 엔티티 레코드 스키마] | [!UICONTROL 조회] | [!UICONTROL 기타] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![Status Green](assets/../../connections/assets/status-green.svg) 켜짐 | ![Status Gray](assets/../../connections/assets/status-gray.svg) 꺼짐 |
| [!UICONTROL 여정 단계 이벤트] | [!UICONTROL Journey Orchestration용 여정 단계 이벤트 스키마] | [!UICONTROL 이벤트] | [!UICONTROL 기타] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![Status Green](assets/../../connections/assets/status-green.svg) 켜짐 | ![Status Gray](assets/../../connections/assets/status-gray.svg) 꺼짐 |
| [!UICONTROL AJO 이메일 추적 경험 이벤트 데이터 세트] | [!UICONTROL AJO 이메일 추적 경험 이벤트 스키마] | [!UICONTROL 이벤트] | [!UICONTROL 기타] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status Green](assets/../../connections/assets/status-green.svg) 켜짐 | ![Status Gray](assets/../../connections/assets/status-gray.svg) 꺼짐 |
| [!UICONTROL AJO 메시지 피드백 이벤트 데이터 세트] | [!UICONTROL AJO 메시지 피드백 이벤트 스키마] | [!UICONTROL 이벤트] | [!UICONTROL 기타] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status Green](assets/../../connections/assets/status-green.svg) 켜짐 | ![Status Gray](assets/../../connections/assets/status-gray.svg) 꺼짐 |
| [!UICONTROL AJO 푸시 추적 경험 이벤트 데이터 세트] | [!UICONTROL AJO 푸시 추적 경험 이벤트 스키마] | [!UICONTROL 이벤트] | [!UICONTROL 기타] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![Status Green](assets/../../connections/assets/status-green.svg) 켜짐 | ![Status Gray](assets/../../connections/assets/status-gray.svg) 꺼짐 |


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
   - 자동 추가된 일부 지표 또는 차원은 파생 필드 기반입니다. 이들 파생 필드는 이 통합 기능을 위해 특별히 생성된 것입니다. 예를 들어 [!UICONTROL 랜딩 페이지 클릭수(AJO)] 지표는 [!UICONTROL 랜딩 페이지 클릭수] 파생 필드 기반입니다.
   - 일부 지표 또는 차원은 추가적인 구성을 갖고 있습니다. 예를 들어 [!UICONTROL 스팸 불만 사항(AJO)]에는 [!UICONTROL 포맷] 및 [!UICONTROL 제외 값 포함] 설정이 적용되어 있습니다.
   - 자동으로 추가된 모든 지표와 차원에는 `:`*`name_of_metric_or_dimension`*이라고 지정된 컨텍스트 레이블이 있습니다. 예를 들어 [!UICONTROL 랜딩 페이지 클릭수(AJO)] 지표에는 `:Landing page clicks (AJO)`라는 이름의 컨텍스트 레이블이 있습니다.

- **[!UICONTROL 설정]** 탭에는 특정한 구성 값이 적용되어 있지 않습니다

>[!IMPORTANT]
>
>연결 및 데이터 보기에 대해 자동 구성된 값을 수정하면 자동 구성된 Customer Journey Analytics 통합을 사용하는 Journey Optimizer 보고에 영향을 줍니다.


## Journey Optimizer와 함께 사용할 데이터 보기 수동 구성

다음 섹션에서는 Journey Optimizer에서 생성된 데이터를 수동으로 사용하여 Customer Journey Analytics에서 고급 분석을 수행하는 방법을 설명합니다. [자동 구성 옵션](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer)이 요구 사항을 충족하는 경우에는 이 수동 구성이 필요하지 않습니다.

### Journey Optimizer의 데이터를 Experience Platform에 전송

Adobe Experience Platform은 Journey Optimizer와 Customer Journey Analytics 사이를 연결하는 중앙 데이터 소스의 역할을 합니다. Journey Optimizer 데이터를 Experience Platform에 데이터 세트로 전송하는 방법에 대한 절차는 Journey Optimizer 사용 안내서의 [데이터 세트 시작](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/data-management/datasets/get-started-datasets)을 참조하십시오.

### 연결 만들기

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


### 데이터 보기 구성

연결을 만든 다음에는 하나 이상의 [데이터 보기](/help/data-views/create-dataview.md)를 만들어 Customer Journey Analytics에서 사용할 수 있는 차원 및 지표를 구성할 수 있습니다.

>[!NOTE]
>
>Journey Optimizer와 Customer Journey Analytics 간의 데이터 불일치는 일반적으로 1~2% 미만입니다. 최근 2시간 이내에 수집된 데이터의 경우 더 큰 불일치가 발생할 수 있습니다. 오늘을 제외한 날짜 범위를 사용하여 처리 시간을 포함한 불일치를 완화할 수 있습니다.


#### 차원 구성

데이터 보기에서 다음 차원을 만들어 Journey Optimizer에 있는 유사한 차원과 거의 정확한 동등성을 달성할 수 있습니다. 차원 사용자 정의 옵션에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

| 차원 | 설명 | 데이터 세트 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- | --- | --- |
| 액션 실행 오류 (AJO) | 여정 런타임이 액션을 실행하지 못하게 하는 오류 조건입니다. | 여정 단계 이벤트 | `_experience.journeyOrchestration.`<br/>`stepEvents.actionExecutionError ` | 구성 요소 유형: 차원 |
| 액션 레이블 (AJO) | 최종 사용자가 상호 작용한 요소의 고객 생성 표시 이름입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.decisioning.`<br/>`propositionAction.label` | 구성 요소 유형: 차원 |
| 배치 ID (AJO) | 예약된 여정 또는 캠페인 액션에 대해 각각의 새 일괄 처리 인스턴스를 호출할 때 생성되는 GUID입니다. 예를 들어 예약된 여정 또는 캠페인 액션이 오전 8시와 오전 10시에 실행되는 경우에 두 개의 서로 다른 batchInstanceID가 있게 됩니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | ` _experience.customerJourneyManagement.`<br/>`messageExecution.batchInstanceID` | 구성 요소 유형: 차원 |
| 배치 인스턴스 타임스탬프 (AJO) | 배치 인스턴스의 타임스탬프입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 차원(파생 필드) |
| 캠페인 ID (AJO) | 캠페인의 ID입니다. | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.entities.`<br/>`campaign.campaignID` | 구성 요소 유형: 차원 |
| 캠페인 이름 (AJO) | 캠페인 이름입니다. | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.entities.`<br/>`campaign.name` | 구성 요소 유형: 차원 |
| 캠페인 버전 ID (AJO) | 캠페인의 버전 ID입니다. | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`entities.campaign.campaignVersionID` | 구성 요소 유형: 차원 |
| 채널 (AJO) | 이 데이터를 연관시켜야 하는 채널입니다. | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.channel._id` | 구성 요소 유형: 차원 |
| 상관관계 ID (AJO) | 상관관계 ID입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.decisioning.propositions.`<br/>`scopeDetails.correlationID` | 구성 요소 유형: 차원 |
| 결정 정책 ID (AJO) | 이 제안에 포함할 항목을 결정할 때 사용되는 결정 정책의 ID입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 차원(파생 필드) |
| 이메일 수신자 도메인 (AJO) | 이메일 주소의 도메인 | AJO 푸시 추적 경험 이벤트 데이터 세트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`emailChannelContext.address` | 구성 요소 유형: 차원 |
| 이메일 제목 (AJO) | 이메일 제목, 개인화되지 않음 | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.entities.`<br/>`channelDetails.email.subject` | 구성 요소 유형: 차원 |
| Event ID (AJO) | 시계열 이벤트에 대한 고유 식별자입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_id` | 구성 요소 유형: 차원(파생 필드) |
| 종료 기준 ID (AJO) | 여정을 종료해야 하는지 결정하는 데 사용되는 종료 기준의 ID입니다. | 여정 단계 이벤트 | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaID` | 구성 요소 유형: 차원 |
| 종료 기준 이름 (AJO) | 종료 기준의 이름입니다. | 여정 단계 이벤트 | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaName` | 구성 요소 유형: 차원 |
| 실험 ID (AJO) | 실험의 ID입니다. | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | 구성 요소 유형: 차원 |
| 실험 이름 (AJO) | 실험 이름입니다. | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.entities.`<br/>`experiment.experimentName` | 구성 요소 유형: 차원 컨텍스트 레이블: 실험 |
| 가져오기 오류 (AJO) | 여정 런타임이 가져오기를 실행하지 못하게 하는 오류 조건입니다. | 여정 단계 이벤트 | `_experience.journeyOrchestration.`<br/>`stepEvents.fetchError` | 구성 요소 유형: 차원 |
| 전송 시간이 최적화되어 있음 (AJO) | 메시지 실행 SendTimeOptimized가 있음 | AJO 푸시 추적 경험 이벤트 데이터 세트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageProfile.isSendTimeOptimized` | 구성 요소 유형: 차원 |
| 테스트 여정임 (AJO) | 테스트 여정 실행의 이벤트 부분임 | 여정 단계 이벤트 | `_experience.journeyOrchestration.`<br/>`stepEvents.inTest` | 구성 요소 유형: 차원 |
| 테스트 메시지임 (AJO) | 테스트 실행으로 메시지가 전송됨 | AJO 푸시 추적 경험 이벤트 데이터 세트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageProfile.isTestExecution` | 구성 요소 유형: 차원 |
| 항목 ID (AJO) | 항목의 ID입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.decisioning.`<br/>`propositions.items.id` | 구성 요소 유형: 차원 |
| 항목 이름 (AJO) | 항목 이름입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.decisioning.`<br/>`propositions.items.name` | 구성 요소 유형: 차원 |
| 여정 액션 ID | MessageExecution이 트리거되는 여정 액션 ID입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageExecution.journeyActionID` | 구성 요소 유형: 차원 |
| 여정 액션 노드 이름 (AJO) | 여정의 액션 노드 이름입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트, AJO 엔티티 데이터 세트 | 파생 필드 | 구성 요소 유형: 차원(파생 필드) |
| 여정 이벤트 노드 이름 (AJO) | 이 값은 여정에서 세그먼트 또는 외부 이벤트가 발생할 때마다 설정됩니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트, AJO 엔티티 데이터 세트 | 파생 필드 | 구성 요소 유형: 차원(파생 필드) |
| 여정 ID (AJO) | 여정의 ID입니다. | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyID` | 구성 요소 유형: 차원 |
| 여정 이름 (AJO) | 여정의 이름입니다. | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyName` | 구성 요소 유형: 차원 |
| 여정 이름 및 버전 (AJO) | 여정의 이름 및 버전입니다. | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNameAndVersion` | 구성 요소 유형: 차원 |
| 여정 버전 ID (AJO) | 여정의 버전 ID입니다. | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.entities.`<br/>`journey.journeyVersionID` | 구성 요소 유형: 차원 |
| 랜딩 페이지 ID (AJO) | 랜딩 페이지의 고유 식별자입니다. | AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.landingpage.landingPageID` | 구성 요소 유형: 차원 |
| 랜딩 페이지 소스 (AJO) | 랜딩 페이지의 소스입니다. | AJO 이메일 추적 경험 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 차원(파생 필드) |
| 링크 URL (AJO) | 사용자가 클릭한 URL입니다. | AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | 구성 요소 유형: 차원 |

{style="table-layout:auto"}

#### 지표 구성

데이터 보기에서 다음 지표를 만들어 Journey Optimizer에 있는 유사한 지표와 거의 정확한 동등성을 달성할 수 있습니다. 지표 사용자 정의 옵션에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

| 지표 | 설명 | 데이터 세트 | 스키마 요소 | 구성 요소 설정 |
| --- | --- | --- | --- | --- |
| 앱 설치 (AJO) | 앱 설치 수 | AJO 푸시 추적 경험 이벤트 데이터 세트 | `application.installs.value` | 구성 요소 유형: 지표 |
| 앱 실행 (AJO) | 모바일 애플리케이션 실행 횟수 | AJO 푸시 추적 경험 이벤트 데이터 세트 | `application.launches.value` | 구성 요소 유형: 지표 |
| 아웃바운드 채널에 대한 바운스 (AJO) | 아웃바운드 채널을 통해 반송된 총 메시지 개수 | AJO 메시지 피드백 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표 |
| 클릭 수 (AJO) | 모든 채널의 총 클릭 수 | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 이메일 추적 경험 이벤트 데이터 세트, AJO 메시지 피드백 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 지표(파생 필드) |
| 대체 제안의 수 (AJO) | 대체 제안의 수. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.decisioning.propositions.items.`<br/>`itemSelection.selectionDetail.selectionType` | 구성 요소 유형: 지표 |
| 오퍼의 수 (AJO) | 오퍼의 수. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | ` _experience.decisioning.`<br/>`propositions.items.id` | 구성 요소 유형: 지표 |
| 중복 제거 지표 (AJO) | 중복 제거 지표 | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_id` | 구성 요소 유형: 지표 |
| 게재됨 (AJO) | 게재된 총 메시지 개수입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 지표(파생 필드) |
| 취소됨 (AJO) | 최종 사용자가 메시지를 닫기 위해 선택한 작업에 관계없이 Adobe SDK에서 인앱 메시지를 닫을 때마다 계산됩니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | 구성 요소 유형: 지표 |
| 디스플레이 (AJO) | 이 카운트는 AJO 메시지를 표시합니다. 여기에는 이메일 열기, 웹 디스플레이 및 인앱 디스플레이가 포함됩니다. 모바일 플랫폼은 SMS 및 푸시 메시지 표시를 보고하지 않으므로 카운트되지 않습니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 이메일 추적 경험 이벤트 데이터 세트, AJO 메시지 피드백 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 지표(파생 필드) |
| 이메일 열람 수 (AJO) | 총 이메일 열람 수 | AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 구성 요소 유형: 지표 |
| 인바운드 클릭 수 (AJO) | 인바운드 채널의 총 클릭 수 | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.decisioning.`<br/>`propositionEventType.interact` | 구성 요소 유형: 지표 |
| 인바운드 취소 (AJO) | 인바운드 채널의 총 취소 수 | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | 구성 요소 유형: 지표 |
| 인바운드 노출 횟수 (AJO) | 인바운드 채널의 총 노출 횟수 | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.decisioning.`<br/>`propositionEventType.display` | 구성 요소 유형: 지표 |
| 여정 종료 (AJO) | 현재 단계가 여정의 인스턴스를 종료하는 것으로 이어지면 참입니다. 이는 지정된 프로필에 대한 여정의 마지막 단계가 정상적으로 실행되었음을 의미합니다. | 여정 단계 이벤트 | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | 구성 요소 유형: 지표 |
| 여정 진입 (AJO) | 단계 이벤트가 프로필에 대한 여정 진입 이벤트인 경우 참입니다. | 여정 단계 이벤트 | 파생 필드 | 구성 요소 유형: 지표(파생 필드) |
| 여정 종료 (AJO) | 현재 단계가 여정의 인스턴스를 종료하는 것으로 이어지면 참입니다. 이는 지정된 프로필에 대한 여정의 마지막 단계가 정상적으로 실행되었음을 의미합니다. | 여정 단계 이벤트 | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | 구성 요소 유형: 지표 |
| 여정 실패 (AJO) | 실행이 완료된 단계의 현재 상태를 제공합니다. 가능한 값: `Transitions`(다음 단계는 이벤트 전환 시 발생함), `EndStep`(이 여정 인스턴스의 마지막 단계가 실행됨), `Error`(이 단계에서 오류 조건이 발생하여 현재 여정 인스턴스가 종료됨), `TimedOut`(현재 단계가 가져오기 또는 액션에서 시간 초과로 인해 종료됨). | 여정 단계 이벤트 | `_experience.journeyOrchestration.`<br/>`stepEvents.stepStatus` | 구성 요소 유형: 지표 |
| 랜딩 페이지 클릭 수 (AJO) | 랜딩 페이지의 총 클릭 수입니다. | AJO 이메일 추적 경험 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 지표(파생 필드) |
| 랜딩 페이지 전환 (AJO) | 랜딩 페이지의 총 전환 수입니다. | AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 구성 요소 유형: 지표 |
| 랜딩 페이지 조회수 (AJO) | 랜딩 페이지의 총 조회수입니다. | AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 구성 요소 유형: 지표 |
| 노드 진입 (AJO) | 단계 이벤트가 프로필에 대한 노드 진입 이벤트인 경우 참입니다. | 여정 단계 이벤트 | 파생 필드 | 구성 요소 유형: 지표(파생 필드) |
| 아웃바운드 클릭 수 (AJO) | 아웃바운드 채널의 총 클릭 수 | AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 구성 요소 유형: 지표 |
| 아웃바운드 오류 (AJO) | 아웃바운드 채널의 총 오류 메시지 수 | AJO 메시지 피드백 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표 |
| 아웃바운드 제외 (AJO) | 아웃바운드 채널의 총 제외 이벤트 수 | AJO 메시지 피드백 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표 |
| 아웃바운드 전송 횟수 (AJO) | 아웃바운드 채널을 통해 전송된 총 메시지 개수 | AJO 메시지 피드백 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 구성 요소 유형: 지표 |
| 푸시 사용자 정의 작업 (AJO) | 푸시 인터랙션의 총 사용자 정의 작업 수입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `eventType` | 구성 요소 유형: 지표 |
| 푸시 인터랙션 (AJO) | 직접 푸시 메시지 상호 작용으로 인해 모바일 애플리케이션이 실행된 횟수 | AJO 푸시 추적 경험 이벤트 데이터 세트 | `application.launches.value` | 구성 요소 유형: 지표 |
| 전송 (AJO) | 모든 채널의 전송된 총 메시지 수 | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 지표(파생 필드) |
| SMS 인바운드 메시지 (AJO) | SMS 수신 응답입니다. 예를 들어 정지, 시작, 구독 등이 있습니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | 구성 요소 유형: 지표 |
| 스팸 고객 불만 (AJO) | 총 스팸 고객 불만 수 | AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 구성 요소 유형: 지표 |
| 구독 목록 추가 (AJO) | 구독 목록에 추가된 총 횟수입니다. | AJO 이메일 추적 경험 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 지표(파생 필드) |
| 구독 목록 제거 (AJO) | 구독 목록에서 제거된 총 횟수입니다. | AJO 이메일 추적 경험 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 지표(파생 필드) |
| 타기팅됨 (AJO) | 제안이 개인에게 타기팅된 횟수입니다. 이는 제안이 개인에게 표시되도록 고려된 횟수입니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | 파생 필드 | 구성 요소 유형: 지표(파생 필드) |
| 트리거됨 (AJO) | Adobe SDK에서 표시하도록 제안이 선택되었습니다. 다른 요인으로 인해 실제로 표시되지 않을 수도 있습니다. | AJO 푸시 추적 경험 이벤트 데이터 세트, 여정 단계 이벤트, AJO 메시지 피드백 이벤트 데이터 세트, AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 구성 요소 유형: 지표 |
| 실험의 고유 방문자 (AJO) | 실험의 고유 방문자 수 | AJO 엔티티 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | 구성 요소 유형: 지표 |
| 구독 취소 (AJO) | 총 구독 취소 수 | AJO 이메일 추적 경험 이벤트 데이터 세트 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 구성 요소 유형: 지표 |

{style="table-layout:auto"}
