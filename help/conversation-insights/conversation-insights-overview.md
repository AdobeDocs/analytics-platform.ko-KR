---
title: 대화 통찰력 개요
description: 대화 통찰력 값 및 용어에 대해 알아보고 대화 통찰력이 작동하는 방식을 알아봅니다.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 39d6847296cc385d501defda292b5b3cae98b46a
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 1%
---
# 대화 통찰력

대화 인사이트를 사용하면 고객에게 제공하는 에이전트 경험에서 대화를 분석할 수 있습니다. 이러한 에이전트 경험은 대형 언어 모델(LLM) 또는 사람의 대화를 기반으로 할 수 있습니다. 대화 통찰력 은 규모에 맞게 대화를 분석하고 전체 고객 여정 내에서 이러한 대화에 대한 컨텍스트를 제공합니다. 대화 인사이트를 통해 에이전트가 실제 사용자 결과에 미치는 영향을 이해할 수 있습니다.

대화 인사이트는 사용자가 겪을 수 있는 문제를 해결합니다. 예를 들어

* 고객이 여정 컨텍스트 내에서 에이전트(LLM 또는 인간)와 상호 작용할 때 발생하는 사항에 대한 insight을 가지고 있지 않습니다.
* 다음 내용을 이해할 수 없습니다.
  * 어떤 상담원이 고객에게 규모에 맞게 정보를 제공합니까?
  * 고객이 규모에 맞게 에이전트와 상호 작용하는 방법.
  * 이러한 상호 작용의 결과로 KPI에 미치는 전반적인 영향은 무엇입니까?
* 변화하는 사용자 환경 설정에 맞게 에이전트 환경을 만듭니다.

Conversation Insights 를 통해 다음을 이해할 수 있습니다.

* 에이전트에서 사용자에게 알리는 내용
* 사용자가 에이전트에게 요청하는 내용.
* 대화가 KPI에 미치는 영향

에이전트가 지침과 비교하여 어떤 성과를 거두고 있는지, 에이전트가 브랜드 지침을 얼마나 긴밀하게 준수하고 있는지, 에이전트 실행 비용이 결과에 의해 정당화되는지 여부를 확인할 수 있습니다.


## 개념

대화 인사이트의 높은 수준에서 [대화](#conversation)는 상관 관계가 있는 [회전](#turn)의 시퀀스입니다. 각 차례는 독립적으로 [프롬프트](#prompt), [응답](#response) 및 [피드백](#feedback) 이벤트를 전달할 수 있습니다. [신호](#signal)는 대화에서 파생된 구조화된 관찰이며, 혼합된 데이터 집합은 보고를 위해 소스 이벤트와 신호를 함께 가져옵니다.

대화 통찰력 은 두 가지 수준에서 에이전트 상호 작용을 분석합니다.

* [대화](#conversation) 수준: 사용자와 에이전트 간의 완전한 상호 작용이며, 여기에는 여러 번의 전환이 포함됩니다.
* [회전](#turn) 수준: 해당 대화 내의 사용자 메시지와 에이전트 응답으로 구성된 하나의 상호 작용 주기.

에이전트 애플리케이션 또는 서비스가 대화 관련 경험 이벤트를 Experience Platform으로 내보냅니다. 프롬프트, 응답 및 피드백 이벤트 데이터가 독립적으로 도착할 수 있습니다. 플랫폼 서비스는 이러한 이벤트를 상호 연관시켜 순환 수준 레코드로 혼합하고, 선택적으로 추출된 신호로 데이터를 보강하고, 결과 데이터를 Customer Journey Analytics 보고에 사용할 수 있도록 합니다.

### 대화

대화는 사용자와 에이전트 간의 완전한 상호 작용입니다. 하나 이상의 회전을 포함할 수 있습니다.

대화는 컨테이너 또는 그룹화 수준입니다. 이 컨테이너는 다음과 같은 질문에 유용합니다.

* 얼마나 많은 대화가 발생했습니까?
* 대화의 주제는 무엇이었습니까?
* 대화에서 감정은 어떻게 변경되었습니까?
* 어떤 대화가 결국 회심으로 이어졌을까?

구현 세부 정보는 [대화 인사이트 구현](./conversation-insights-implement.md) 설명서의 [대화](./conversation-insights-implement.md#conversation) 개체를 참조하십시오.

### 회전

차례는 대화 내의 상호 작용 주기 중 하나입니다.

전형적인 차례는 다음으로 구성됩니다.

* 사용자 프롬프트
* 에이전트 응답
* (선택 사항) 사용자 피드백

차례는 보고 목적으로 기본 분석 객체입니다. 대화 블렌더 서비스는 이용 가능한 프롬프트, 응답, 피드백 및 신호 정보를 턴레벨 레코드로 결합합니다.

구현 세부 정보는 [대화 인사이트 구현](./conversation-insights-implement.md) 설명서의 [회전](./conversation-insights-implement.md#turn) 개체를 참조하십시오.

### 프롬프트

프롬프트는 에이전트에 제출된 입력입니다. 대부분의 고객 시나리오에서 이 입력은 사용자의 질문, 요청, 지침 또는 메시지입니다.

프롬프트에 여러 원시 세그먼트가 포함될 수 있습니다. 예를 들어 사용자가 텍스트를 입력하고 URL을 포함합니다.

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`

프롬프트는 대화 통찰력이 다음과 같은 분석 정보를 가져올 수 있는 기본 입력입니다.

* 사용자의 의도
* 주제 또는 주제
* 사용자의 톤
* 사용자의 감정
* 기타 지원되는 신호

구현 세부 정보는 [대화 인사이트 구현](./conversation-insights-implement.md) 설명서의 [prompt](./conversation-insights-implement.md#prompt) 개체를 참조하십시오.

### 응답

응답은 에이전트나 다른 응답 당사자가 반환하는 컨텐츠입니다.

응답에는 종종 다른 유형의 콘텐츠가 포함됩니다. 예:

* 주요 대답
* 인용 또는 참조
* 링크
* 이미지
* 프로모션 콘텐츠

이러한 구분은 분석이 지원 링크, 인용, 광고 또는 기타 응답 구성 요소와 주요 답변을 분리해야 하므로 유용합니다.

구현 세부 정보는 [대화 인사이트 구현](./conversation-insights-implement.md) 설명서에서 [응답](./conversation-insights-implement.md#response) 개체를 참조하십시오.

### 피드백

피드백은 상호 작용에 대한 사용자의 명시적인 평가 또는 반응이다.

피드백에는 다음이 포함될 수 있습니다.

* 자유 형식 피드백 텍스트
* 수치 등급
* 등급 분류
* 등급에 대한 하나 이상의 이유

피드백이 반드시 프롬프트 또는 응답과 동시에 이용 가능하지는 않습니다. 사용자가 답변을 평가한 후 나중에 에이전트 애플리케이션 또는 서비스에서 피드백을 보낼 수 있습니다.

구현 세부 정보는 [대화 인사이트 구현](./conversation-insights-implement.md) 설명서에서 [피드백](./conversation-insights-implement.md#feedback) 개체를 참조하십시오.

### 신호

신호는 대화 내용에 대한 구조화된 분석적 관찰입니다. 신호 추출 서비스는 신호를 추출합니다.

구현 세부 정보는 [대화 인사이트 구현](./conversation-insights-implement.md) 설명서에서 [신호](./conversation-insights-implement.md#signal) 개체를 참조하십시오.


### 에이전트

에이전트 애플리케이션 또는 서비스를 식별하려면 각 대화 통찰력 이벤트(프롬프트, 응답, 피드백, 신호)에 대해 에이전트 정보가 필요합니다.

#### 스킬 호출

에이전트 경험 애플리케이션이 처리 중에 호출된 기능을 나타내는 기술 호출을 지원하는 경우 이러한 기술 호출을 에이전트 정보 필드 그룹의 일부로 추가할 수 있습니다.

구현 세부 정보는 [대화 인사이트 구현](./conversation-insights-implement.md) 설명서의 [에이전트 정보](./conversation-insights-implement.md#agentic-information-field-group) 필드 그룹을 참조하십시오.

## 작동 방식

Conversation Insights는 다음 세 가지 핵심 기능을 기반으로 구축됩니다.

* **데이터 수집**: LLM 및 에이전트가 작업을 얼마나 잘 수행하는지 사용자가 이해할 수 있도록 해줍니다. 필요한 모든 데이터 포인트를 수집하려면 데이터 수집이 필요합니다.
* **신호 추출 및 대화 혼합**: 구조화되지 않은 프롬프트 및 응답(회전이라고도 함)을 의도 및 감정과 같은 보고 가능한 데이터 포인트로 변환합니다. 따라서 사용자가 이러한 데이터 포인트에 대해 규모에 맞게 보고할 수 있습니다.
* **보고**: 에이전트의 효율성 및 ROI를 확인하려면 고객 여정 컨텍스트에서 규모에 맞게 대화를 분석하십시오.

데이터 수집, 신호 추출 및 대화 혼합의 전체 과정은 아래와 같다.

![대화 통찰력 작동 방식 그림](assets/conversation-insights.png){zoomable="yes"}

| | 설명 |
|---|---|
| 1 | 에이전트 응용 프로그램 또는 서비스를 사용하여 프롬프트 ![CommentText](/help/assets/icons2/CommentText.svg), 응답 ![CommentReply](/help/assets/icons2/CommentReply.svg) 및 피드백 ![Feedback](/help/assets/icons2/Feedback.svg) 데이터 세트가 포함된 이벤트를 만듭니다.<br/>에이전트 응용 프로그램 또는 서비스를 계측하는 방법에 대한 자세한 내용은 [구현 설명서](./conversation-insights-implement.md)를 참조하세요. |
| 2 | 신호 추출 서비스는 프롬프트 ![CommentText](/help/assets/icons2/CommentText.svg), 응답 ![CommentReply](/help/assets/icons2/CommentReply.svg) 및 피드백 데이터 세트 ![Feedback](/help/assets/icons2/Feedback.svg)에서 신호를 신호 이벤트 ![OnAir](/help/assets/icons/OnAir.svg)(으)로 추출하여 이러한 신호 이벤트를 새 데이터 세트에 저장합니다.<br>이 단계는 [대화 인사이트 구성](./conversation-insights-configure.md)의 정의의 일부로 구현됩니다. |
| 3 | 대화 블렌더 서비스는 프롬프트 ![CommentText](/help/assets/icons2/CommentText.svg), 응답 ![CommentReply](/help/assets/icons2/CommentReply.svg), 피드백 ![Feedback](/help/assets/icons2/Feedback.svg) 및 신호 ![OnAir](/help/assets/icons/OnAir.svg) 이벤트 데이터 세트의 이벤트를 혼합하고 혼합된 ![Merge](/help/assets/icons/Merge.svg)이벤트를 새 데이터 세트에 출력합니다.<br>이 단계는 [대화 인사이트 구성](./conversation-insights-configure.md)의 정의의 일부로 구현됩니다. |
| 4 | 혼합된 ![병합](/help/assets/icons/Merge.svg) 데이터 집합은 연결의 일부가 되며 혼합된 데이터 집합에 사용된 스키마에 정의된 구성 요소는 데이터 보기의 일부가 됩니다.<br>이 단계는 [대화 인사이트 구성](./conversation-insights-configure.md)의 정의의 일부로 구현됩니다. |

