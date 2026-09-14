---
title: 대화 통찰력 구현
description: Conversation Insights용 에이전트 애플리케이션 또는 서비스를 계측하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '2257'
ht-degree: 6%
---
# 대화 통찰력 구현

대화 데이터를 XDM 경험 이벤트로 생성하고 이러한 대화 경험 이벤트가 데이터 세트로 Adobe Experience Platform에 표시되도록 하려면 Conversation Insights를 사용하도록 에이전트 애플리케이션 또는 서비스를 계측하십시오.

이 문서에서는 필요한 구현 단계에 대해 설명합니다.

>[!PREREQUISITES]
>
>* 데이터를 수집하려면 Experience Platform 환경(조직 및 샌드박스)을 사용할 수 있어야 합니다.
>* 실험 에이전트 및 대화 필드 그룹에 대해 Adobe 조직을 활성화해야 합니다.
>

## 스키마 및 데이터 세트

기본 대화 이벤트(프롬프트, 응답, 피드백)를 위한 데이터 세트를 구성합니다. 이러한 데이터 세트는 동일한 스키마(예: 일반 대화 통찰력 스키마) 또는 개별 스키마를 기반으로 할 수 있습니다.
프롬프트, 응답 및 피드백에 대해 별도의 데이터 세트를 정의하거나 데이터를 데이터 세트로 결합할 수 있습니다. 예를 들어, 프롬프트 및 응답에는 한 데이터 세트를 사용하고 피드백에는 다른 데이터 세트를 사용합니다. 또는 모든 대화 이벤트에 단일 데이터 세트를 사용합니다.

프롬프트, 응답 및 피드백 데이터 세트에 사용되는 스키마는 XDM 경험 이벤트 기본 스키마를 필수 필드 그룹으로 확장해야 합니다. 추가 필드 그룹으로 XDM 경험 이벤트 기본 스키마를 확장할 수 있습니다.

### 에이전트 정보 필드 그룹

**[!UICONTROL 에이전트 정보]** 필드 그룹은 필수 필드 그룹이며 `agenticExperience` 개체를 사용합니다.

+++ 세부 사항

| 필드 경로(점 표기법) | 유형 | 예제 값 | 참고 |
|---|---|---|---|
| `conciergeID` | 문자열 | `"concierge-abc123"` | **새로 만들기.** Concierge의 고유 식별자입니다. |
| `name` | 문자열 | `"Brand Concierge"` | 에이전트 세트를 결합한 Concierge 이름입니다. |
| `version` | 문자열 | `"1.0.0"` | 에이전트 세트를 결합한 Concierge 버전입니다. |
| `environment` | 문자열 | `"prod"` | 이 이벤트가 시작된 환경(개발, 단계, 프로덕션) |
| `mode` | 문자열 | `"release"` | 에이전트의 상태 모드(테스트, 미리보기, 릴리스) |
| `agents[]` | 배열 | 아래 에이전트 개체 참조 | 사용된 에이전트 배열 |
| `agents[].agentID` | 문자열 | `"agent-001"` | **새로 만들기.** 아래 `skills[].agentID`에서 참조한 에이전트의 고유 식별자입니다. |
| `agents[].name` | 문자열 | `"Chatbot Assistant"` | 에이전트 이름 |
| `agents[].version` | 문자열 | `"2.1.3"` | 에이전트 버전 |
| `agents[].score` | 숫자 | `0.92` | 반환된 값의 에이전트 신뢰도 점수 |
| `agents[].skills[]` | 배열 | 아래 스킬 오브젝트 참조 | **사용하지 않음** — `agentID`을(를) 통해 기술 호출 및 각 에이전트를 연결하는 순서가 지정된 전체 목록을 소유하고 있는 아래 최상위 수준 `skills[]` 배열을 대신 사용합니다. |
| `agents[].skills[].name` | 문자열 | `"Intent Recognition"` | 스킬 이름(사용되지 않는 배열) |
| `agents[].skills[].version` | 문자열 | `"1.0.0"` | 스킬 버전(사용되지 않는 배열) |
| `agents[].skills[].score` | 숫자 | `0.95` | 스킬 신뢰도 점수(0-1)(더 이상 사용되지 않는 배열) |
| `agents[].skills[].parameters[]` | 배열 | 아래 매개 변수 참조 | 스킬로 전송된 매개 변수(키-값 쌍)(더 이상 사용되지 않는 배열) |
| `agents[].skills[].parameters[].key` | 문자열 | `"language"` | 매개 변수 키 |
| `agents[].skills[].parameters[].value` | 문자열 | `"en-US"` | 매개 변수 값 |
| `skills[]` | 배열 | 아래 스킬 호출 개체 를 참조하십시오 | **새로운 기능, 실험적 기능** 모든 에이전트에서 이 경험에 대한 전체 주문 스킬 호출 목록입니다. 더 이상 사용되지 않는 에이전트당 `agents[].skills[]` 배열을 바꿉니다. |
| `skills[].skillID` | 문자열 | `"skill-intent-recognition"` | 호출된 스킬 정의 식별자 |
| `skills[].skillInvocationID` | 문자열 | `"inv-9f2a-001"` | 게재와 일관적인 개별 스킬 호출에 대한 고유 식별자입니다. 스킬 배열 다운스트림 병합 시 중복 제거 키 |
| `skills[].name` | 문자열 | `"Intent Recognition"` | 호출된 스킬 이름 |
| `skills[].version` | 문자열 | `"1.0.0"` | 호출된 스킬 버전 |
| `skills[].agentID` | 문자열 | `"agent-001"` | `agents[].agentID`과(와) 관련된 이 스킬을 호출한 에이전트의 식별자입니다. 하위 에이전트가 동시에 실행되므로 에이전트 내에서 기술을 주문하는 데 사용하는 주요 소비자 그룹화 |
| `skills[].invocationSource` | 문자열 | `"main"` | 기본 에이전트 루프(`main`)에 의해 호출되는지 또는 하위 에이전트(`subagent`)에 의해 호출되는지 여부 |
| `skills[].score` | 숫자 | `0.95` | 스킬 일치로 인한 점수 |
| `skills[].failed` | 부울 | `false` | 스킬 실행이 실패했음을 나타내는 플래그 |
| `skills[].errorReason` | 문자열 | `"timeout"` | `failed`이(가) true인 경우 스킬이 실패한 원인 |
| `skills[].sequenceNumber` | 정수 | `1` | 단일 에이전트 실행 내에서 이 스킬 호출의 인덱스를 단조롭게 증가(하위 에이전트가 동시에 실행되므로 전환되지 않음). 소비자는 타임브레이커로 `agentID`, `sequenceNumber`, `timestamp`씩 주문합니다. 선택 사항입니다 |
| `skills[].timestamp` | 문자열(날짜-시간) | `"2026-09-11T00:03:15Z"` | 스킬이 호출된 시간, ISO 8601 UTC. `sequenceNumber` 이후에 사용되는 순서 지정 키입니다. 제작자는 항상 이 항목을 채워야 합니다. |
| `skills[].skillSource` | 문자열 | `"inline"` | 기술 정의가 런타임으로 배달되는 방법: `inline`(컨텍스트에 인라인으로 로드됨) 또는 `deferred`(온디맨드로 로드됨) |
| `skills[].executionContext` | 문자열 | `"inline"` | 호출 에이전트를 기준으로 스킬을 실행하는 경우: `inline` 또는 `forked`(포크된 하위 에이전트 컨텍스트에서 실행) |
| `skills[].reasoning.narration` | 문자열 | `"Recognized an intent to verify a geography fact"` | 이 스킬이 호출된 이유에 대한 자연어 설명 |
| `skills[].parameters[]` | 배열 | 아래 매개 변수 참조 | 스킬에 전달된 매개 변수 |
| `skills[].parameters[].key` | 문자열 | `"language"` | 매개 변수 키 |
| `skills[].parameters[].value` | 문자열 | `"en-US"` | 매개 변수 값 |

+++

에이전트 정보 필드 그룹에 데이터를 전달하는 이벤트를 구현하려면 다음을 확인해야 합니다.

* 에이전트 구성

  * 각 에이전트에는 고유한 agentID, 이름 및 버전 조합이 있습니다.
  * 에이전트 점수가 `0.0`에서 `1.0` 사이에 표준화되었습니다.
  * 기술 호출로 에이전트를 참조하려면 `agentID`을(를) 사용하십시오.

* 스킬 호출

  * 각 에이전트 아래에 기술을 중첩하지 않고 모든 에이전트에서 스킬 호출당 하나의 항목만 내보냅니다.
  * 다운스트림 혼합을 통해 중복 재게재된 이벤트를 제거할 수 있도록 skillInvocationID를 채웁니다.
  * 소비자를 적절히 주문하십시오. `agentID`별로 그룹화한 다음 `sequenceNumber`별로 정렬하여 `timestamp`(으)로 돌아갑니다. 하위 에이전트가 동시에 실행될 수 있으므로 순서 지정이 필요합니다.
  * `invocationSource` 및 `executionContext`을(를) 사용하여 기본 및 하위 에이전트 기술과 인라인 및 포크된 실행을 구별합니다.
  * 더 이상 사용되지 않는 `agents[].skills[]` 배열을 사용하지 마십시오. 과거에 배열을 사용한 적이 있는 경우에는 배열을 읽기 전용 개체로 취급합니다.

* 스킬 매개변수

  * 매개 변수는 Adobe XDM 키-값 데이터 유형을 사용하고, 언어 설정, 임계값, 모델 구성에 일반적인 매개 변수 유형을 사용합니다. 예, `"key":"language", "value":"en-US"`.

+++ 에이전트 정보 필드 그룹의 사용 예 

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffe",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"agent.interaction",
  "identityMap":{
    "ECID":[
      {
        "id": "12345678901234567890123456789012345678",
        "primary": true
      }
    ]
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      {
        "agentID":"agent-001",
        "name":"Chatbot Assistant",
        "version":"2.1.3",
        "score":0.92
      },
      {
        "agentID":"agent-002",
        "name":"Voice Assistant",
        "version":"3.0.0",
        "score":0.88
      }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline",
        "reasoning":{
          "narration":"Recognized an intent to verify a geography fact"
        },
        "parameters":[
          { "key":"language", "value":"en-US" },
          { "key":"confidenceThreshold", "value":"0.8" }
        ]
      },
      {
        "skillID":"skill-faq-retrieval",
        "skillInvocationID":"inv-9f2a-002",
        "name":"FAQ Retrieval",
        "version":"1.2.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.89,
        "failed":false,
        "sequenceNumber":2,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"inline",
        "executionContext":"forked",
        "parameters":[
          { "key":"maxResults", "value":"5" }
        ]
      },
      {
        "skillID":"skill-speech-recognition",
        "skillInvocationID":"inv-9f2a-003",
        "name":"Speech Recognition",
        "version":"2.0.1",
        "agentID":"agent-002",
        "invocationSource":"main",
        "score":0.91,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"deferred",
        "executionContext":"inline",
        "parameters":[
          { "key":"languageModel", "value":"general" },
          { "key":"noiseSuppression", "value":"true" }
        ]
      }
    ]
  }
}
```

+++


### 대화 이벤트 필드 그룹

**[!UICONTROL 대화 이벤트]** 필드 그룹은 필수 필드 그룹이며 `conversation` 개체를 사용합니다.

대화 개체는 다음에 대한 데이터를 캡처합니다.

#### 대화

고유한 `conversationID`이(가) 대화를 식별합니다. 예: `conversationID = "conv-001"`. 스키마에서도 `conversationName`을(를) 지원합니다. 사용자가 읽을 수 있는 이름으로, 대화의 전체 컨텍스트를 설명합니다(예: `France Geography Q&A`).

`conversationID`을(를) 사용하면 관련된 모든 회전 이벤트를 동일한 대화 경험으로 그룹화할 수 있습니다.

#### 회전

차례는 대화 내의 상호 작용 주기 중 하나입니다.

`turnID` 고유한 `turnID`이(가) 회전을 식별합니다. 예:

`conversationID = "conv-001"`
`turnID = "turn-001"`

같은 `conversationID` 및 `turnID`을(를) 사용하여 해당 전환과 연결된 프롬프트, 응답 및 피드백을 상호 연관시킵니다. 이러한 상관 관계는 별도로 제공되거나 다른 데이터 세트로 끝나는 레코드 간에 작동합니다.


#### 프롬프트

프롬프트는 에이전트에 제출된 입력입니다. 대부분의 고객 시나리오에서 이 입력은 사용자의 질문, 요청, 지침 또는 메시지입니다.

프롬프트에서 다음 표현을 사용합니다. `conversation.prompt`

중요한 프롬프트 필드는 다음과 같습니다.

| 필드 | 의미 |
|---|---|
| `prompt.source` | 프롬프트를 만든 사람 또는 무엇, 일반적으로 최종 사용자. |
| `prompt.raw[]` | 하나 이상의 원시 콘텐츠 세그먼트. |
| `prompt.raw[].text` | 실제 프롬프트 텍스트 또는 콘텐츠입니다. |
| `prompt.raw[].purpose` | 콘텐츠의 목적(예: 사용자 입력 또는 링크) |

프롬프트에 여러 원시 세그먼트가 포함될 수 있습니다. 예를 들어 사용자가 텍스트를 입력하고 URL을 포함합니다.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`


#### 응답

응답은 에이전트나 다른 응답 당사자가 반환하는 컨텐츠입니다.

`conversation.response` 고유한 `responseID`은(는) 응답을 나타냅니다.

중요 응답 필드는 다음과 같습니다.

| 필드 | 의미 |
|---|---|
| `response.source` | 반응을 일으킨 사람 또는 그 사람. |
| `response.raw[]` | 하나 이상의 응답 콘텐츠 세그먼트 |
| `response.raw[].text` | 응답 텍스트 또는 콘텐츠입니다. |
| `response.raw[].purpose` | 콘텐츠 세그먼트의 목적. |

문서화된 소스 유형은 다음과 같습니다.

| 소스 | 의미 |
|---|----|
| `bot` | 자동화된 에이전트 응답. |
| `canned` | 사전 정의되거나 템플릿화된 응답. |
| `concierge` | 인간 에이전트 응답. |
| `end-user` | 해당되는 경우 사용자 생성 콘텐츠. |

#### 피드백

피드백은 상호 작용에 대한 사용자의 명시적인 평가 또는 반응이다.

피드백 구조에는 `conversation.feedback`이(가) 포함됩니다.

예:

* `feedback.raw[].text: "Great help"`
* feedback.rating.score: 1
* feedback.rating.classification: &quot;엄지손가락 위로&quot;
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`

문서화된 등급 점수 범위는 `-1.0`에서 `1.0`까지입니다.

`eventType = "conversation.feedback"`을(를) 사용하여 피드백 이벤트를 피드백 전용 이벤트로 표시할 수 있습니다.

피드백이 특정 차례대로 적용되는 경우 대화 믹서기가 해당 피드백을 관련 상호 작용과 연결할 수 있도록 적절한 `conversationID` 및 `turnID`을(를) 유지하십시오.


#### 신호

신호는 대화 내용에 대한 구조화된 분석적 관찰입니다. 신호 추출 서비스는 신호를 추출합니다.

신호에는 다음 필드가 있습니다.

| 필드 | 의미 |
|---|----|
| `scope` | 신호를 파생시키는 데 사용되는 입력 범위(예: 대화 또는 최신 대화). |
| `name` | 제목, 의도, 색조 또는 감정 등 신호 식별자. 제품 정의 신호 이름도 지원됩니다. |
| `type` | 값 유형은 문자열, 숫자 또는 부울입니다. |
| `values[]` | 신호와 연결된 하나 이상의 값. |
| `stringValue` | 의도, 톤 또는 제목과 같은 문자열 신호 값입니다. |
| `numberValue` | 감정 점수와 같은 숫자 신호 값입니다. |
| `booleanValue` | true/false 신호 값. |
| `confidence` | 신호 값에 대한 선택적 생산자 신뢰도(일반적으로 0과 1 사이). |
| `qualifiers[]` | 신호 값에 컨텍스트를 추가하는 선택적 설명자입니다. |
| `metadata[]` | 선택적 생성자 정의 키/값 메타데이터. |


신호 추출 서비스가 신호 데이터 집합에 대한 `signals` 개체를 채웁니다.

이전 `signals[].attributes.{subjects,intents,tones,sentiment}` 컨테이너는 사용되지 않습니다.

#### 대화

대화 개체에 대한 자세한 내용은 아래를 참조하십시오.

+++ 세부 사항 

| 필드 경로(점 표기법) | 유형 | 예제 값 | 참고 |
|---|---|---|---|
| `conversationID` | 문자열 | `"conv-001"` | 여러 회전을 함께 그룹화합니다 |
| `conversationName` | 문자열 | `"France Geography Q&A"` | **새로 만들기.** 전체 컨텍스트를 나타내는 대화에 지정된 이름 |
| `turnID` | 문자열 | `"turn-001"` | 이 차례에 대한 고유 ID |
| `prompt.source` | 문자열 | `"end-user"` | 프롬프트 Source, 기타 옵션에는 캐시된 값, 빈 값 등이 포함될 수 있습니다. |
| `prompt.raw[]` | 배열 | 아래 원시 개체 참조 | 원시 프롬프트 데이터 |
| `prompt.raw[].text` | 문자열 | `"What is the capital of France?"` | 실제 텍스트 컨텐츠 |
| `prompt.raw[].purpose` | 문자열 | `"User Input"` | 이 텍스트 세그먼트의 목적 |
| `response.source` | 문자열 | `"bot"` | 응답의 Source |
| `response.raw[]` | 배열 | 아래 원시 개체 참조 | 원시 응답 데이터 |
| `response.raw[].text` | 문자열 | `"The capital of France is Paris."` | 응답 텍스트 콘텐츠 |
| `response.raw[].purpose` | 문자열 | `"main"` | 응답 세그먼트의 목적상, 다른 옵션에는 링크, 사진 등이 포함될 수 있습니다. |
| `feedback.source` | 문자열 | `"end-user"` | 피드백 Source |
| `feedback.raw[]` | 배열 | 아래 원시 개체 참조 | 원시 피드백 데이터 |
| `feedback.raw[].text` | 문자열 | `"Great help"` | 피드백 텍스트 |
| `feedback.raw[].purpose` | 문자열 | `"free-form text"` | 피드백 세그먼트의 목적, 다른 옵션에는 스크린샷, 미디어 등이 포함될 수 있습니다. |
| `feedback.rating.score` | 숫자 | `1` | -1.0에서 1.0까지의 수치 평가 점수 |
| `feedback.rating.classification` | 문자열 | `"Thumbs Up"` | 등급 분류 |
| `feedback.rating.reasons[]` | 배열 | `["Accurate", "Quick response"]` | 등급 이유 배열 |
| `signals[]` | 배열 | 아래 신호 개체 참조 | 이 이벤트와 그동안의 대화를 기반으로 파생된 신호입니다. 각 항목은 자체 범위가 있는 단일 명명된 신호입니다 |
| `signals[].scope` | 문자열 | `"turn"` | 이 신호 집합이 파생되는 입력 범위(전환, 대화 누락, 마지막 N회 전환, 피드백) |
| `signals[].attributes` | 오브젝트 | 아래 속성을 참조하십시오. | **사용되지 않습니다.** 신호 속성에 대한 컨테이너입니다. 각 속성은 값 또는 값이 포함된 객체입니다. 이는 신호를 생성하는 데 사용되는 ML/에이전트 정보의 모집단을 지원할 필요가 예상됨에 따른 것이다. |
| `signals[].attributes.subjects` | 오브젝트 | 아래 제목 참조 | **사용되지 않습니다.** 주제 컨테이너 |
| `signals[].attributes.subjects.values[]` | 배열 | 아래 제목 값을 참조하십시오 | **사용되지 않습니다.** 제목 값 배열 |
| `signals[].attributes.subjects.values[].phrase` | 문자열 | `"product pricing"` | **사용되지 않습니다.** 선택한 범위의 입력에서 추출된 구문 또는 키워드입니다. |
| `signals[].attributes.subjects.values[].qualifiers[]` | 배열 | `["important", "urgent"]` | **사용되지 않습니다.** 구문에 대한 한정자 목록 |
| `signals[].attributes.intents` | 오브젝트 | 아래 의도 참조 | **사용되지 않습니다.** 의도 컨테이너 |
| `signals[].attributes.intents.values[]` | 배열 | `["make a purchase", "learn more"]` | **사용되지 않습니다.** 범위 입력에서 파생된 의도 |
| `signals[].attributes.tones` | 오브젝트 | 아래 색조 참조 | **사용되지 않습니다.** 톤 컨테이너 |
| `signals[].attributes.tones.values[]` | 배열 | `["thrilled", "contemplative"]` | **사용되지 않습니다.** 범위 입력에서 파생된 톤 |
| `signals[].attributes.sentiment` | 오브젝트 | 아래 감정 참조 | **사용되지 않습니다.** 감정 컨테이너 |
| `signals[].attributes.sentiment.value` | 숫자 | `0.71` | **사용되지 않습니다.** 감정을 나타내는 -1(음수)에서 1(양수)까지의 점수 |
| `signals[].name` | 문자열 | `"sentiment"` | **새로 만들기**(더 이상 사용되지 않는 `attributes` 컨테이너를 대체). 이 신호에 대한 식별자(예: &quot;주제&quot;, &quot;의도&quot;, &quot;색조&quot;, &quot;감정&quot; 또는 생성자가 정의한 이름) - 생성자는 스키마를 변경하지 않고 새 신호 유형을 추가할 수 있습니다 |
| `signals[].type` | 문자열 | `"number"` | **새로 만들기.** 이 신호 값의 데이터 형식(`string`, `number` 또는 `boolean`) - 소비자에게 `values[]`의 각 항목에 입력된 값 필드가 채워져 있는지 알려줍니다. |
| `signals[].values[]` | 배열 | 아래 값 개체 참조 | 이 신호에 대한 하나 이상의 값 |
| `signals[].values[].stringValue` | 문자열 | `"curious"` | `type`이(가) &quot;string&quot;인 경우 채워집니다. 인텐트, 색조 또는 추출된 구문과 같은 범주형 값 |
| `signals[].values[].numberValue` | 숫자 | `0.71` | `type`이(가) &quot;숫자&quot;일 때 채워집니다(예: 감정 점수가 -1에서 1까지 또는 강도). |
| `signals[].values[].booleanValue` | 부울 | `true` | `type`이(가) &quot;부울&quot;일 때 채워짐 - true/false 플래그 |
| `signals[].values[].confidence` | 숫자 | `0.9` | **새로 만들기.** 생성자가 이 값에 할당하는 신뢰도(0-1) |
| `signals[].values[].qualifiers[]` | 배열 | `["important", "urgent"]` | 이 값에 대한 추가 설명자. 키워드와 유사하지만 더 의미 있음 |
| `signals[].values[].metadata[]` | 배열 | 아래 매개 변수 참조 | **새로 만들기.** 키/값 쌍(예: 신호를 생성한 ML/에이전트에 대한 컨텍스트)으로서 이 값에 대한 생성자 정의 메타데이터 |

+++




### 추가 필드 그룹

프롬프트, 응답 및 피드백 데이터 세트에 사용하는 스키마에 선택적 필드 그룹을 추가할 수 있습니다. 예:

* **웹 세부 정보** 필드 그룹입니다. 대화가 포함된 웹 페이지의 세부 정보를 캡처합니다.
* **Commerce 세부 정보** 필드 그룹. 대화의 일부로 언급된 권장 제품의 제품 세부 정보를 캡처합니다.



고객은 소스 대화 이벤트를 생성할 책임이 있습니다. Adobe 플랫폼은 후속적으로 신호 추출 및 데이터 블렌딩을 수행합니다. 고객은 신호 추출 또는 혼합 서비스를 구현할 필요가 없습니다.

이 문서에서는 대화 통찰력 MVP 입력 요구 사항 및 현재 에이전트 스키마 업데이트에 대해 설명합니다. 여기에는 Conversation Insights 1.0 기능 또는 이후 릴리스 요구 사항이 포함되지 않습니다.

### 이벤트 유형

각 대화 이벤트에 대해 `eventType`(문자열)에 대해 다음 값 중 하나를 설정해야 합니다.

| 값 | 설명 |
|---|---|
| `conversation turn` | 대화에 대한 프롬프트 및 응답 완료 |
| `conversation recommendation` | 대화 기반 추천 |
| `conversation feedback` | 피드백 전용 이벤트 |


### Source 유형

이벤트의 각 `prompt`, `response` 또는 `feedback` 개체에 대해 `source`에 대해 다음 값 중 하나를 설정해야 합니다.

| 값 | 설명 |
|---|---|
| `end-user` | 사람 사용자 입력 |
| `bot` | 자동화된 에이전트 응답 |
| `canned` | 사전 정의/템플릿 응답 |
| `concierge` | 인간 에이전트 응답 |

### 목적 유형(원시 텍스트)

`prompt`, `response` 또는 `feedback` 개체에 있는 `raw` 개체의 모든 요소에 대해 `purpose` 특성에 대해 다음 값 중 하나를 설정해야 합니다.

| 값 | 설명 |
|---|---|
| `User Input` | 기본 사용자 입력 |
| `main` | 주요 응답 콘텐츠 |
| `advertisement` | 프로모션 콘텐츠 |
| `citation` | 참조/소스 링크 |
| `link` | 외부 링크 |
| `image` | 이미지 참조 |
| `enum picker` | 구조화된 피드백 선택 |


### 예

다양한 시나리오에서 대화 이벤트 필드 그룹의 사용 예는 아래를 참조하십시오.

+++ 세부 사항 

>[!BEGINTABS]

>[!TAB 이벤트 전환]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What is the capital of France? This link says it is Lyon.", "purpose": "User Input" },
        { "text": "https://wrong.geography.com/france", "purpose": "link" }
      ]
    }
  }
}
```

>[!TAB 응답 이벤트 예]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffd",
  "timestamp":"2026-09-11T00:03:16Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "The capital of France is Paris.", "purpose": "main" },
        { "text": "Would you like to plan a trip to Paris?", "purpose": "advertisement" },
        { "text": "https://en.wikipedia.org/wiki/France", "purpose": "citation" }
      ]
    }
  }
}
```

>[!TAB 피드백 이벤트 예]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffb",
  "timestamp":"2026-09-12T00:03:15Z",
  "eventType":"conversation.feedback",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "feedback": {
      "source": "end-user",
      "raw": [
        { "text": "Great help", "purpose": "text box" }
      ],
      "rating": {
        "score": 1,
        "classification": "Thumbs Up",
        "reasons": ["Accurate", "Quick response"]
      }
    }
  }
}
```

>[!TAB 제품 권장 사항 이벤트 예]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffa",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.recommendation",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-xyz789",
    "name":"Product Concierge",
    "version":"1.0.0",
    "environment":"prod",
    "mode":"release",
    "agents":[
      { "agentID":"agent-010", "name":"Product Advisor", "version":"1.0.0", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "turnID": "int-099",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What product do you recommend for a new user trying to create a poster?", "purpose": "User Input" }
      ]
    },
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "To create a poster, we would recommend Adobe Express - https://express.adobe.com.", "purpose": "main" },
        { "text": "https://express.adobe.com", "purpose": "link" }
      ]
    }
  },
  "productListItems": [
    { "SKU": "express" }
  ]
}
```

>[!ENDTABS]

+++

## 데이터 수집

대화 통찰력에 대해 다음 데이터 수집 전략을 사용하십시오.


### 이벤트 유형

에이전트 애플리케이션 또는 서비스에서 가능한 한 빨리 이벤트를 보냅니다. 앱 또는 서비스가 이벤트 발생 시 사용할 수 있는 정보를 사용하여 프롬프트를 전송하기 전에 응답을 기다리지 않는지 확인하십시오.

이 권장 사항은 다음을 의미합니다.

* 프롬프트, 응답 및 피드백 오브젝트는 독립적으로 채워지며 단일 이벤트의 일부로 강제되지 않아야 합니다.
* 데이터 세트 간에 동일한 `conversationID` 및 `turnID`을(를) 가진 여러 이벤트가 필요합니다.

### 이벤트 상관 관계

에이전트 애플리케이션 또는 서비스는 모든 관련 이벤트에 대해 안정적인 식별자를 유지해야 합니다.

| 필드 경로 | 설명 |
|---|---|
| `conversation.conversationID` | 전체 대화에 대한 고유 식별자. |
| `conversation.turnID` | 대화 내의 개별 차례에 대한 고유 식별자. |
| `_id` | 경험 이벤트 레코드 식별자. |
| `timestamp` | 이벤트가 발생한 시간입니다. |
| `eventType` | 대화 이벤트의 유형을 식별합니다. |

* 동일한 대화에 속하는 모든 이벤트에 동일한 `conversationID`을(를) 사용해야 합니다.

* 프롬프트, 응답 및 같은 순서와 연결된 모든 피드백에 동일한 `turnID`을(를) 사용해야 합니다. 프롬프트, 응답 및 피드백 데이터 세트에 동일한 `turnID`을(를) 가진 여러 이벤트가 있을 수 있습니다.

에이전트 애플리케이션 또는 서비스는 재시도 또는 재게재 중 안정적인 ID를 생성합니다. 이를 통해 다운스트림 처리를 통해 이벤트를 올바르게 연결하고 의도하지 않은 중복 이벤트를 방지할 수 있습니다.

## 신호 추출

신호 추출은 데이터 수집 후에 발생합니다. 에이전트 애플리케이션 또는 서비스가 추가 신호를 채우지 않습니다.

+++ 신호가 있는 선반가공 이벤트 예

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id":"12345678901234567890123456789012345678", "primary":true }
    ]
  },
  "web":{
    "webPageDetails":{ "URL":"https://www.adobe.com", "name":"Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline"
      }
    ]
  },
  "conversation":{
    "conversationID":"conv-001",
    "conversationName":"France Geography Q&A",
    "turnID":"int-001",
    "signals":[
      {
        "scope":"turn",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"capital of France", "confidence":0.93, "qualifiers":["geographical","factual-question"] },
          { "stringValue":"Lyon", "confidence":0.87, "qualifiers":["incorrect","misinformation"] }
        ]
      },
      {
        "scope":"turn",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"seek-information" },
          { "stringValue":"verify-facts" }
        ]
      },
      {
        "scope":"turn",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"curious" },
          { "stringValue":"uncertain" }
        ]
      },
      {
        "scope":"turn",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.1 }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"unreliable source", "qualifiers":["external-link","potentially-misleading"] },
          { "stringValue":"geography knowledge", "qualifiers":["educational","basic-facts"] }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"fact-checking" },
          { "stringValue":"learn-correct-information" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"questioning" },
          { "stringValue":"seeking-clarification" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.3 }
        ]
      }
    ],
    "prompt":{
      "source":"end-user",
      "raw":[
        { "text":"What is the capital of France? This link says it is Lyon.", "purpose":"User Input" },
        { "text":"https://wrong.geography.com/france", "purpose":"link" }
      ]
    }
  }
}
```

+++

## 데이터 혼합

대화 블렌더 서비스는 프롬프트, 응답, 피드백 및 신호 이벤트 데이터 세트의 이벤트를 전용 블렌드 대화 이벤트 데이터 세트에 병합합니다. 해당 데이터 세트는 Customer Journey Analytics에서 연결의 일부로 사용됩니다. 해당 데이터 세트 내의 구성 요소는 대화 통찰력 구성에 대해 지정한 데이터 보기에 추가됩니다.
