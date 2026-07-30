---
title: LLM Optimizer 통합
description: LLM Optimizer과 Customer Journey Analytics 통합
feature: Experience Platform Integration
role: User
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
source-git-commit: 3aa4e0c98e9a3e4163dad992e598638892fc88cd
workflow-type: tm+mt
source-wordcount: 2539
ht-degree: 2%

---


# LLM Optimizer 통합

[Adobe LLM Optimizer](https://experienceleague.adobe.com/ko/docs/llm-optimizer/using/home){target="_blank"}은(는) 생성 엔진 최적화를 위한 생성 AI 우선 애플리케이션으로, 브랜드가 AI 기반 검색 환경에서 가시성, 정확성 및 영향력을 향상시킬 수 있도록 설계되었습니다. LLM Optimizer은 AI가 생성한 답변의 브랜드 존재감에 대한 통찰력을 제공하고, 규범적인 콘텐츠 권장 사항을 제공하고, 최적화 수정 사항을 자동화합니다.

AI는 주요 검색 채널이 되었습니다. 채팅 GPT, Copilot, Copilot, 크롤링 및 브랜드 콘텐츠와 같은 LLM 에이전트.

>[!PREREQUISITES]
>
>LLM Optimizer 유료 서비스가 프로비저닝되어 있어야 하며 관리 커넥터를 통해 Experience Platform 구성에 연결되어 있어야 합니다.


>[!IMPORTANT]
>
>이 통합의 일부로, 미국에서 LLM Optimizer 데이터의 일부 임시 처리가 발생합니다. 데이터는 Customer Journey Analytics 계약에 구성된 대로 지정된 영역에 최종적으로 저장됩니다.


## 사용 사례

다음 두 가지 방법으로 Customer Journey Analytics과 LLM Optimizer을 통합할 수 있습니다.

* **인바운드 통합**: Customer Journey Analytics의 LLM Optimizer 데이터를 사용하여 기존 웹, 모바일 및 기타 유형의 데이터와 함께 LLM 기반 트래픽(보트 웹 크롤러, RAG 요청, 에이전트 활동)을 측정합니다. 예를 들어 다음 작업을 수행할 수 있습니다.

  * 기존 채널과 함께 에이전트 소스별로 LLM 기반 트래픽을 측정합니다.

  * LLM에서 많이 사용하지만 사람 전환에서 성과가 낮은 콘텐츠를 식별합니다.

  * 중요한 경로에서 LLM 에이전트 요청이 실패하는 위치를 감지합니다.

  * 페이지에 대한 LLM 보트 수요를 URL 및 호스트 수준에서 일치하는 웹 데이터의 해당 페이지 전환 및 매출과 비교합니다.

* **아웃바운드 통합**: ChatGPT 또는 Perplexity와 같은 중요한 트래픽을 보내는 LLM 소스에 대한 AI 가시성을 최적화할 수 있도록 Customer Journey Analytics 성능 데이터를 LLM Optimizer에 보냅니다. 예를 들어 다음 작업을 수행할 수 있습니다.

  * 계속 전환하거나 수익을 창출하는 방문자를 보내는 LLM 소스를 확인하십시오. Customer Journey Analytics은 봇 데이터 세트가 아니라 참조된 웹 트래픽에서 이 값을 측정합니다.
  * LLM 소스의 순위를 보내는 사람 방문자의 다운스트림 값으로 지정한 다음 가장 성과가 좋은 소스에 AI 가시성 작업을 집중하십시오.


## 인바운드 통합

LLM 트래픽은 두 가지 방법으로 사이트에 도달합니다. Customer Journey Analytics은 다른 데이터 소스에서 각 방식으로 측정합니다.

첫 번째 방법은 AI 답변을 읽은 다음 클릭하여 사이트를 방문하는 사람입니다. 이 방문은 웹 데이터의 나머지 부분을 수집하는 동일한 JavaScript을 실행합니다. 따라서 기존 Customer Journey Analytics 웹 데이터에는 사용자를 보낸 방문 및 참조 도메인이 포함됩니다(예: chatgpt.com). Customer Journey Analytics은 이러한 방문을 자체적으로 AI 트래픽으로 레이블 지정하지 않습니다. 이들을 식별하고 그룹화하려면 AI 참조 도메인과 일치하는 연결에 파생 필드를 만든 다음, 세그먼트를 작성하고 해당 필드에 대해 보고합니다. [파생 필드](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}를 참조하세요. 이 사람 트래픽에는 LLM Optimizer 데이터 세트가 필요하지 않습니다.

두 번째 방법은 페이지를 직접 요청하는 보트 또는 에이전트입니다. 여기에는 사용자가 AI 도우미에 프롬프트를 제출할 때 발생하는 AI 인덱스 및 라이브 가져오기를 빌드하는 웹 크롤러가 포함됩니다. 이러한 요청은 JavaScript을 실행하지 않으므로 기존 웹 데이터는 이러한 요청을 기록하지 않습니다. LLM Optimizer 데이터 세트는 CDN 계층에서 이 트래픽을 캡처합니다. 이 섹션의 나머지 부분에서는 해당 데이터 세트에 대해 설명합니다.

### Customer Journey Analytics에 데이터 세트 온보드

LLM Optimizer 관리 커넥터는 데이터를 요약 데이터 세트로 Experience Platform에 전달합니다. Customer Journey Analytics에서 측정하려면 두 가지 설정 단계를 직접 완료합니다.

1. LLM Optimizer 데이터 세트를 포함하는 연결을 만듭니다. [연결 만들기 또는 편집](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}을 참조하세요.
2. 해당 연결에 대한 데이터 보기를 만듭니다. 데이터 보기를 통해 Analysis Workspace에서 아래의 차원 및 지표를 사용할 수 있습니다. [데이터 보기 만들기 또는 편집](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}을 참조하세요.

데이터 세트:

* XDM 요약 지표 클래스를 기반으로 하는 [요약 데이터 세트](/help/data-views/summary-data.md)를 사용합니다.
* URL 및 호스트, 시간 및 요청 특성(예: 보트 유형, CDN 공급자 및 상태)별로 데이터를 버킷합니다.

>[!NOTE]
>
>LLM Optimizer 데이터 세트에는 집계된 데이터가 포함되어 있습니다. 사용자 식별자, 프롬프트 또는 응답과 같은 PII는 포함되지 않습니다.
>

요약 데이터 세트이므로 조회 데이터 세트로 처리하여 전체 URL 키의 이벤트 데이터 세트에 조인할 수 있습니다.

LLM Optimizer은 **CDN URL** 차원에서 이 키를 제공합니다. Customer Journey Analytics에서 웹 데이터를 저장하는 방법과 유사하게 호스트와 요청된 경로를 하나의 정규화된 전체 URL로 결합합니다. 가입 성공 여부는 사용자의 데이터 수집에 따라 다릅니다. 이벤트 데이터 세트에는 동등한 전체 URL 필드 또는 LLM Optimizer에서 제공하는 URL과 일치하도록 구문 분석하고 정규화할 수 있는 필드가 필요합니다. 양측이 동일한 전체 URL로 확인되면 LLM Optimizer 레코드는 웹 데이터의 해당 페이지와 일치합니다.

### 데이터 세트 정보

LLM Optimizer은 서버측에서 CDN 액세스 로그를 읽고 요청 당사자가 봇 또는 자동화된 에이전트인 레코드를 추출합니다. 데이터는 CDN 계층에서 가져오므로 LLM Optimizer은 JavaScript 태그를 실행하지 않는 봇의 요청을 캡처합니다. 표준 웹 분석 도구는 이 트래픽을 완전히 놓칩니다.

데이터 집합에서 **CDN 요청 요약** 필드 그룹을 사용합니다. 모든 필드는 `cdn` 개체 아래에 있으므로 아래 표의 필드 이름은 `cdn.url` 및 `cdn.botType`과 같은 `cdn.<name>` 형식을 사용합니다.

각 레코드는 호스트, URL 경로, 보트 유형, CDN 공급자, 상태 코드, 레퍼러, 전달된 호스트 및 1시간 동안 첫 번째 바이트까지의 시간의 한 조합을 설명합니다. 동일한 조합이 매시간 두 번 이상 표시되면 Customer Journey Analytics은 이러한 레코드를 한 행에 결합하여 요청 수를 늘립니다. **CDN 요청 개수** 지표를 사용하여 볼륨을 측정합니다. 행 수를 사용하지 마십시오.

### 차원

LLM Optimizer 데이터 세트를 포함하는 연결을 설정한 후에는 데이터 보기에서 구성 요소로 사용할 수 있는 차원은 다음과 같습니다. **Field** 열은 CDN 요청 요약 필드 그룹의 원본 필드를 표시합니다.

| 치수 | 필드 | 설명 |
|-----------|-------|-------------|
| CDN URL | `cdn.url` | 조인 키로 사용되는 요청에 대한 정규화된 전체 URL입니다. LLM Optimizer은 호스트와 요청된 경로를 단일 URL로 결합하고 Customer Journey Analytics이 웹 데이터에 저장하는 전체 URL 양식과 일치하도록 표준화합니다. 이 차원을 사용하여 LLM Optimizer 조회 데이터 세트를 동등한 전체 URL 필드가 있는 이벤트 데이터 세트에 조인합니다. 여기에는 호스트와 경로가 포함되지만 스키마는 포함되지 않습니다. |
| CDN URL 경로 | `cdn.path` | CDN에서 전달한, 에이전트가 요청한 원시 URL 경로 및 쿼리 문자열입니다. 스키마 또는 호스트를 포함하지 않습니다. 정규화된 조인 키가 아닌 요청된 정확한 경로가 필요한 경우 사용하십시오. |
| CDN 호스트 | `cdn.host` | 요청을 받은 호스트 이름(예: www.example.com)입니다. 이 호스트는 CDN URL 조인 키의 일부이기도 합니다. 조직에 동일한 CDN 계정에 여러 개의 하위 도메인이 있는 경우 데이터 세트에 여러 호스트가 포함될 수 있습니다. |
| CDN 보트 유형 | `cdn.botType` | LLM Optimizer의 요청 에이전트 분류. 값은 클래식 검색 웹 크롤러, AI 인덱스 웹 크롤러 및 AI 라이브 가져오기 에이전트를 포함합니다. 전체 분류법을 보려면 아래의 [보트 에이전트 범주](#bot-agent-categories)를 참조하십시오. |
| CDN 사용자 에이전트 | `cdn.userAgent` | CDN 로그의 원시 사용자 에이전트 문자열. 보트 분류 내에서 하위 유형을 구별하거나 LLM Optimizer에서 지정한 분류를 확인하는 데 유용합니다. |
| CDN HTTP 상태 | `cdn.status` | HTTP 응답 상태 코드. 봇이 요청한 콘텐츠를 수신했는지 여부를 나타냅니다. AI 트래픽에 대한 해석 지침은 아래의 [상태 코드](#status-codes)를 참조하십시오. |
| CDN 공급자 | `cdn.cdnProvider` | 요청을 처리한 CDN입니다. 값은 `akamai`, `byocdn-akamai`, `byocdn-fastly` 및 `byocdn-cloudfront`입니다. `byocdn-` 접두사는 다른 CDN 공급업체가 아닌 로그 수집 경로를 나타냅니다. 조직에 다른 CDN 구성 뒤에 호스트가 있는 경우 데이터 세트에는 여러 값이 포함될 수 있습니다. |
| CDN 레퍼러 | `cdn.referer` | CDN 로그의 HTTP Referer 헤더 값. 종종 보트 트래픽에 대해 비어 있습니다. 존재하는 경우 가져오기를 트리거한 AI 제품 또는 도메인을 나타낼 수 있습니다. 예: chat.openai.com. |
| CDN 전달 호스트 | `cdn.xForwardedHost` | X-Forwarded-Host 헤더 값(있는 경우). 요청이 원본에 도달하기 전에 역방향 프록시 또는 CDN 실드 레이어를 통과한 경우와 관련이 있습니다. |
| CDN 이벤트 날짜 | 레코드 타임스탬프에서 파생됨 | 이 레코드에 대한 시간별 배치 타임스탬프의 날짜 부분입니다. |
| CDN 이벤트 시간 | 레코드 타임스탬프에서 파생됨 | 이 레코드에 대한 시간별 배치 타임스탬프의 시간 부분. |

### 보트 에이전트 범주

**CDN 보트 유형** 차원은 에이전트를 세 가지 범주로 구성합니다. 각 범주는 다른 분석 질문에 답합니다.

기존 검색 엔진에 대한 **클래식 검색 웹 크롤러** 인덱스 컨텐츠입니다. 이 범주를 사용하여 콘텐츠가 기존 검색 엔진에 표시되는 정도를 측정합니다.

| 보트 유형 값 | 공급업체 | 설명 |
|---|---|---|
| `GoogleBot` | Google | Google의 주 검색 색인 웹 크롤러. Google Discover 및 Google News도 제공합니다. |
| `BingBot` | Microsoft | Bing의 검색 색인 웹 크롤러. 또한 Microsoft Copilot의 웹 접지 색인에 데이터를 제공합니다. |

**AI 색인 웹 크롤러** 크롤링 콘텐츠를 빌드하거나 업데이트하여 AI 제품의 교육 코퍼스 또는 검색 색인을 빌드합니다. 이러한 웹 크롤러는 라이브 사용자 요청에 응답하지 않고 모델의 기술 자료를 준비하고 있습니다. URL의 웹 크롤러 볼륨이 높으면 AI 공급업체는 해당 콘텐츠를 인덱싱할 가치가 있다고 간주합니다. URL에 웹 크롤러 볼륨이 낮지만 라이브 가져오기 볼륨이 높은 경우 모델은 새 콘텐츠를 가져오는 대신 캐시된 지식으로부터 가져옵니다.

| 보트 유형 값 | 공급업체 | 설명 |
|---|---|---|
| `GPTBot` | 오픈에이아이 | 모델 교육 데이터 및 지식 기반 구축을 위한 OpenAI의 주요 웹 크롤러. |
| `OAI-SearchBot` | 오픈에이아이 | OpenAI의 ChatGPT의 웹 검색 제품 웹 크롤러. GPTBot와 구별됩니다. 이 에이전트는 교육 코퍼스가 아닌 실시간 검색 인덱스를 작성합니다. |
| `ClaudeBot` | 인간 같 | 모델 교육 데이터에 대한 Anthropic의 주요 웹 크롤러. |
| `Claude-SearchBot` | 인간 같 | 클로드의 검색 색인에 대한 인류 웹 크롤러. ClaudeBot과 다릅니다. |
| `PerplexityBot` | 곤란 | Perplexity의 인덱스 웹 크롤러. 당혹감은 이 에이전트를 사용하여 답변 생성을 위한 코퍼스를 구축합니다. |

**AI 라이브 가져오기**&#x200B;는 실제 사용자가 AI 도우미에 프롬프트를 제출하고 도우미가 응답하기 전에 페이지를 라이브로 가져올 때 발생합니다. 이 범주를 사용하여 AI 도우미를 통해 도착하는 직접 사용자 수요를 측정합니다.

| 보트 유형 값 | 공급업체 | 설명 |
|---|---|---|
| `ChatGPT-User` | 오픈에이아이 | 한 사용자가 ChatGPT에 질문을 했습니다. ChatGPT는 이 URL을 가져와서 읽고 그 답변을 작성했습니다. |
| `ChatGPT Clients` | 오픈에이아이 | 라이브 가져오기를 수행하는 ChatGPT 모바일 앱(iOS 및 Android)입니다. 사용자 에이전트 문자열에는 앱 버전 및 장치가 포함됩니다. |
| `Claude-User` | 인간 같 | Claude를 사용하는 사용자 또는 애플리케이션이 이 URL을 실시간으로 가져옵니다. 사용자-에이전트 문자열은 특정 클로드 제품, 예를 들어, 클로드-코드를 식별할 수 있다. |
| `Perplexity-User` | 곤란 | 한 사용자가 당혹감을 감추지 못하고 질문을 던졌다. 당혹스러움이 이 URL을 가져와서 대답을 지연했습니다. |
| `Google-NotebookLM` | Google | 사용자가 Google NotebookLM을 열고 이 도메인을 소싱했습니다. NotebookLM은 소스 도메인 내에서 접근 가능한 모든 URL을 가져옵니다. |
| `Google-ai-mode` | Google | Google 검색의 AI 개요 기능은 검색 결과의 AI 생성 답변 패널에 포함하기 위해 이 URL을 가져왔습니다. |
| `Gemini-Deep-Research` | Google | 사용자가 Gemini 딥리서치 세션을 실행했습니다. 심층 조사(Deep Research)는 연구 보고서를 작성하기 위해 여러 소스에서 많은 순차적 가져오기를 수행합니다. |
| `GoogleAgent-URLContext` | Google | 사용자가 Gemini와 URL을 공유하고 해당 페이지에 대해 질문했습니다. Gemini는 특정 콘텐츠에 대한 질문에 답변하기 위해 URL을 라이브로 가져왔습니다. |
| `Amzn-User` | Amazon | Amazon Alexa 또는 Amazon AI 에이전트가 이 URL을 실시간으로 가져옵니다. 일반적으로 참조 및 설명서 콘텐츠에 나타납니다. |
| `MistralAI-User` | 미스트랄 | 미스트랄 기반 제품 또는 API 소비자의 라이브 가져오기. |

LLM Optimizer에서 사용자 에이전트를 인식된 패턴에 일치시킬 수 없는 경우 값 `Unknown`을(를) 할당합니다. **CDN 사용자 에이전트** 차원을 사용하여 어떤 에이전트가 이러한 요청을 했는지 식별할 수 있습니다.

### 상태 코드

이 데이터 세트의 HTTP 상태 코드는 AI 에이전트가 요청한 콘텐츠를 수신했는지 여부를 나타냅니다.

| 상태 | 이름 | 해석 |
|--------|------|----------------|
| 200 | 확인 | 봇이 전체 응답을 받았습니다. AI가 사용할 수 있는 콘텐츠가 제공되었습니다. |
| 304 | 수정되지 않음 | 봇은 콘텐츠가 변경되지 않았음을 확인하고 캐시된 버전을 사용합니다. 콘텐츠를 사용할 수 있습니다. |
| 301 | 영구적으로 이동됨 | 봇이 새 URL로 리디렉션되었습니다. 각 리디렉션에는 추가 왕복이 추가됩니다. 자주 크롤링의 높은 301 볼륨은 CDN 수준에서 URL을 해결해야 함을 의미합니다. |
| 302 | 찾음(임시 리디렉션) | 301과 동일한 지연 페널티입니다. 301과 달리 영구적인 움직임을 나타내지 않으므로 봇은 원본 URL을 계속 적중합니다. |
| 403 | 금지 | CDN 또는 원본이 보트를 차단했습니다. 예를 들어 robots.txt 규칙 또는 WAF 정책을 통해 의도적이거나, 너무 넓은 비율 제한을 통해 의도하지 않을 수 있습니다. AI 가져오기가 차단되면 해당 콘텐츠가 AI 답변에 표시되지 않습니다. |
| 404 | 찾을 수 없음 | URL이 존재하지 않습니다. AI 에이전트 유형의 높은 404 볼륨은 AI의 색인에 오래된 URL이 포함되어 있음을 나타냅니다. 410 상태를 사용하여 웹 크롤러가 색인에서 URL을 영구적으로 제거하도록 할 수 있습니다. |
| 429 | 요청이 너무 많음 | CDN이 보트를 제한했습니다. 라이브 가져오기 에이전트 유형에서 429개의 오류가 지속되면 AI 도우미에게 콘텐츠에 대한 질문을 하는 사용자가 불완전하거나 누락된 응답을 받게 됩니다. |
| 504 | 게이트웨이 시간 초과 | CDN이 원본이 응답하기를 기다리는 것을 중지했습니다. 콘텐츠가 AI에 도달하지 않았습니다. 페이지 시간이 초과되면 AI가 해당 콘텐츠에 액세스할 수 없으며 답변에 포함할 수 없습니다. 라이브 가져오기 에이전트 유형의 높은 504 볼륨은 직접적인 AI 가시성 위험입니다. |

### 지표

LLM Optimizer 데이터 세트를 포함하는 연결을 설정한 후에는 다음 지표를 데이터 보기의 구성 요소로 사용할 수 있습니다. **Field** 열은 CDN 요청 요약 필드 그룹의 원본 필드를 표시합니다.

| 지표 | 필드 | 설명 |
|--------|-------|-------------|
| CDN 요청 카운트 | `cdn.requests` | 모든 행의 요청 필드에서 합산된 CDN 요청의 총 개수입니다. 항상 이 지표를 사용하여 볼륨을 측정합니다. 행 수를 사용하지 마십시오. |
| CDN 오류 카운트 | `cdn.status`, `cdn.requests` | 4xx 또는 5xx HTTP 상태 코드를 반환하는 요청 개수입니다. |
| CDN 오류율 | CDN 오류 카운트에서 파생 | 총 요청 수로 계산되는 오류입니다. |
| CDN 첫 번째 바이트까지의 평균 시간 | `cdn.timeToFirstByte` | CDN이 응답의 첫 번째 바이트에 대한 요청을 받은 시점부터 경과된 평균 시간(밀리초)입니다. CDN 캐시 응답은 일반적으로 50ms 미만입니다. 원점에서 제공되는 응답은 일반적으로 300ms에서 700ms입니다. AI 라이브 가져오기 에이전트는 종종 시간이 초과되거나 원본 응답이 매우 느린 경우 훨씬 더 높은 값을 표시합니다. 라이브 가져오기 에이전트 유형의 높은 평균 값은 AI 가시성 위험으로 조사할 가치가 있습니다. |

### 데이터 세트 경계

이 데이터 세트는 CDN 액세스 로그의 봇 트래픽만 캡처합니다. 여기에는 다음 항목이 포함되어 있지 않습니다.

* **사용자 세션, 전환 또는 참여 데이터** AI 답변에서 클릭스루하는 사용자는 페이지에서 JavaScript을 실행하므로 방문이 이 데이터 세트에 있지 않고 기존 웹 데이터에 있습니다. 두 데이터 세트를 Customer Journey Analytics으로 가져와서 동일한 URL 및 호스트에 대해 비교할 수 있습니다.
* **ECID와 같은 개인 식별자.** 이 데이터 집합에서 개인 수준의 참가를 만들 수 없습니다. 조인은 URL 및 호스트 수준에서 작동합니다.
* **초 단위 시간 세부기간** 타임스탬프는 시간별입니다. 1시간 이내에 트래픽을 분 또는 초로 분류할 수 없습니다.
* **페이지 콘텐츠 또는 렌더링된 HTML.** 이 데이터 세트는 AI가 페이지에서 읽은 내용이 아니라 가져오기 사실과 결과를 기록합니다.
* **전환 데이터.** 이 데이터 세트는 AI 답변이 사용자를 사이트로 방문하게 했는지 또는 전환하게 했는지 여부를 알려주지 않습니다. 개인 기반 이벤트 데이터가 아닌 집계 CDN 요약 데이터를 보유하고 있으므로 요청을 개별 개인 또는 세션에 연결하지 않습니다.

## 아웃바운드 통합

결정될 예정입니다.


<!-- 

# LLM Optimizer integration

[Adobe LLM Optimizer](https://experienceleague.adobe.com/ko/docs/llm-optimizer/using/home){target="_blank"} is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. LLM Optimizer provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. LLM agents, such as ChatGPT, Claude, Copilot, and Perplexity, crawl and reference brand content. 

>[!PREREQUISITES]
>
>You must have an LLM Optimizer paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of LLM Optimizer data occurs in the United States. Data is ultimately stored in your designated region as configured in your Customer Journey Analytics contract.


## Use cases

You can benefit from the integration between Customer Journey Analytics and LLM Optimizer in two ways:

* **Inbound integration**: Use LLM Optimizer data in Customer Journey Analytics to measure LLM-driven traffic (bot crawlers, RAG requests, agent activity) alongside existing web, mobile, and other types of data. For example, to address the following use cases:
  
  * Measure LLM-driven traffic by agent source alongside traditional channels.
  
  * Identify content that is heavily consumed by LLMs but underperforms in human conversion.
  
  * Detect where LLM-agent requests fail across critical paths.

  * Correlate LLM activity with downstream business outcomes (revenue, conversions, engagement).
  
* **Outbound integration**: Use Customer Journey Analytics performance data inside LLM Optimizer so AI visibility can be optimized for real business outcomes. For example, to address the following use cases:

  * Evaluate how each LLM agent correlates with revenue, conversions, and engagement.
  * Identify which LLM agents are associated with stronger downstream performance. Which LLM agents are associated with higher engagement or conversion rates.


## Inbound integration

To ingest LLM Optimizer data into Customer Journey Analytics, use the LLM Optimizer datasets available in Experience Platform. The ingestion method:

* Uses [summary datasets](/help/data-views/summary-data.md) that are based on the XDM Summary Schema class.
* Buckets data by URL/host, time, and request characteristics such as bot type, CDN provider, and status.

>[!NOTE]
>
>The LLM Optimizer dataset contains aggregated data that does not contain any PII, such as user identifiers, prompts, or responses.
>

You use the LLM Optimizer dataset in a connection. Because the dataset is a summary dataset, you can use the dataset as a lookup dataset and potentially join to an event dataset on a full-URL key.

LLM Optimizer provides this key for you in the **CDN URL** dimension. The key combines the host and the requested path into a single normalized full URL, similar to how Customer Journey Analytics stores web data. This join-key field facilitates the join. The outcome depends on your Customer Journey Analytics implementation and whether your event dataset has a page URL field that matches the URL representation LLM Optimizer provides. When both sides resolve to the same full URL, the LLM Optimizer record matches the corresponding page in your web data.

### About the dataset

LLM Optimizer reads CDN access logs on the server side and extracts records where the requesting party is a bot or automated agent. Because the data comes from the CDN layer, LLM Optimizer captures requests from bots that do not execute any JavaScript tag. Standard web analytics tools miss this traffic entirely.

Each record describes one combination of host, URL path, bot type, CDN provider, status code, referrer, forwarded host, and time to first byte for one hour. When the same combination appears multiple times hourly, Customer Journey Analytics combines those records into one row and increases the request count. Use the **CDN Request Count** metric to measure volume. Do not use row count.

### Dimensions

The following dimensions are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Dimension | Description |
|-----------|-------------|
| CDN URL | The normalized full URL for the request, intended as the join key. LLM Optimizer combines the host and the requested path into a single URL and normalizes it to match the full-URL form that Customer Journey Analytics stores for web data. Use this dimension to join the LLM Optimizer lookup dataset to an event dataset that has an equivalent full-URL field. It includes the host and path, but not the scheme. |
| CDN URL Path | The raw URL path and query string that the agent requested, as delivered by the CDN. Does not include the scheme or host. Use this when you need the exact requested path rather than the normalized join key. |
| CDN Host | The hostname that received the request, for example, www.example.com. This host is also part of the CDN URL join key. A dataset can contain multiple hosts when an organization has multiple subdomains on the same CDN account. |
| CDN Bot Type | LLM Optimizer's classification of the requesting agent. Values cover classic search crawlers, AI index crawlers, and AI live-fetch agents. See the [Bot agent categories](#bot-agent-categories) below for the full taxonomy. |
| CDN User Agent | The raw user-agent string from the CDN log. Useful for distinguishing sub-types within a bot classification, or for validating the classification assigned by LLM Optimizer. |
| CDN HTTP Status | The HTTP response status code. Indicates whether the bot received the content it requested. See the [Status codes](#status-codes) below for interpretation guidance specific to AI traffic. |
| CDN Provider | Which CDN handled the request. Values are `akamai`, `byocdn-akamai`, `byocdn-fastly`, and b`yocdn-cloudfront`. The `byocdn-` prefix indicates the log collection pathway, not a different CDN vendor. A dataset can contain multiple values when an organization has hosts behind different CDN configurations. |
| CDN Referrer | The HTTP Referer header value from the CDN log. Often empty for bot traffic. When present, it can indicate which AI product or domain triggered the fetch. For example, chat.openai.com. |
| CDN Forwarded Host | The X-Forwarded-Host header value, if present. Relevant when the request passed through a reverse proxy or CDN shield layer before reaching the origin. |
| CDN Event Date | The date part of the hourly batch timestamp for this record. |
| CDN Event Hour | The hour part of the hourly batch timestamp for this record. |

### Bot agent categories

The **CDN Bot Type** dimension organizes agents into three categories. Each category answers a different analytical question.

**Classic search crawlers** index content for traditional search engines. Use this category to measure how visible your content is to traditional search engines.

| Bot type value | Vendor | Description |
|---|---|---|
| `GoogleBot` | Google | Google's main search index crawler. Also serves Google Discover and Google News. |
| `BingBot` | Microsoft | Bing's search index crawler. Also feeds Microsoft Copilot's web grounding index. |

**AI index crawlers** crawl content to build or update an AI product's training corpus or search index. These crawlers are preparing a model's knowledge base, not responding to a live user request. When a URL has high crawler volume, AI vendors consider that content worth indexing. When a URL has low crawler volume but high live-fetch volume, the model draws from cached knowledge rather than fetching fresh content.

| Bot type value | Vendor | Description |
|---|---|---|
| `GPTBot` | OpenAI | OpenAI's primary crawler for model training data and knowledge base construction. |
| `OAI-SearchBot` | OpenAI | OpenAI's crawler for ChatGPT's web search product. Distinct from GPTBot. This agent builds the real-time search index, not the training corpus. |
| `ClaudeBot` | Anthropic | Anthropic's primary crawler for model training data. |
| `Claude-SearchBot` | Anthropic | Anthropic's crawler for Claude's search and retrieval index. Distinct from ClaudeBot. |
| `PerplexityBot` | Perplexity | Perplexity's index crawler. Perplexity uses this agent to build the corpus for its answer generation. |

**AI live fetches** occur when a real user submits a prompt to an AI assistant and the assistant fetches the page live before responding. Use this category to measure direct user demand arriving through AI assistants.

| Bot type value | Vendor | Description |
|---|---|---|
| `ChatGPT-User` | OpenAI | A user asked ChatGPT a question. ChatGPT fetched this URL to read it and form its answer. |
| `ChatGPT Clients` | OpenAI | The ChatGPT mobile app (iOS and Android) doing a live fetch. The user-agent string includes the app version and device. |
| `Claude-User` | Anthropic | A user or application using Claude live-fetched this URL. The user-agent string may identify the specific Claude product, e.g., claude-code. |
| `Perplexity-User` | Perplexity | A user asked Perplexity a question. Perplexity fetched this URL to ground its answer. |
| `Google-NotebookLM` | Google | A user opened Google NotebookLM and sourced this domain. NotebookLM fetches every reachable URL within a sourced domain. |
| `Google-ai-mode` | Google | Google Search's AI Overviews feature fetched this URL to include it in an AI-generated answer panel in search results. |
| `Gemini-Deep-Research` | Google | A user ran a Gemini Deep Research session. Deep Research makes many sequential fetches across multiple sources to compile a research report. |
| `GoogleAgent-URLContext` | Google | A user shared a URL with Gemini and asked questions about that page. Gemini fetched the URL live to answer questions about that specific content. |
| `Amzn-User` | Amazon | An Amazon Alexa or Amazon AI agent live-fetched this URL. Typically appears on reference and documentation content. |
| `MistralAI-User` | Mistral | A live fetch from a Mistral-powered product or API consumer. |

When LLM Optimizer cannot match a user-agent to a recognized pattern, it assigns the value `Unknown`. You can use the **CDN User Agent** dimension to identify what agent made those requests.

### Status codes

HTTP status codes in this dataset indicate whether the AI agent received the content it requested.

| Status | Name | Interpretation |
|--------|------|----------------|
| 200 | OK | The bot received the full response. The content was available for the AI to use. |
| 304 | Not Modified | The bot confirmed the content has not changed and used its cached version. The content was available. |
| 301 | Moved Permanently | The bot was redirected to a new URL. Each redirect adds an extra round-trip. High 301 volume on frequently crawled URLs means the redirect should be resolved at the CDN level. |
| 302 | Found (Temporary Redirect) | Same latency penalty as 301. Unlike 301, it does not signal a permanent move, so bots will keep hitting the original URL. |
| 403 | Forbidden | The CDN or origin blocked the bot. This can be intentional, e.g., through robots.txt rules or WAF policy, or unintentional, e.g., through overly broad rate limits. When AI fetches are blocked, that content cannot appear in AI answers. |
| 404 | Not Found | The URL does not exist. High 404 volume on AI agent types indicates the AI's index contains stale URLs. Use the 410 status to tell crawlers to remove a URL from their index permanently. |
| 429 | Too Many Requests | The CDN rate-limited the bot. Sustained 429 errors on live-fetch agent types mean that users asking AI assistants questions about your content will receive incomplete or missing responses. |
| 504 | Gateway Timeout | The CDN stopped waiting for the origin to respond. The content did not reach the AI. When a page times out, the AI cannot access its content and cannot include it in an answer. High 504 volume on live-fetch agent types is a direct AI visibility risk. |

### Metrics

The following metrics are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Metric | Description |
|--------|-------------|
| CDN Request Count | The total count of CDN requests, summed from the requests field across all rows. Always use this metric to measure volume. Do not use row count. |
| CDN Error Count | The count of requests that returned a 4xx or 5xx HTTP status code. |
| CDN Error Rate | The error count as a percentage of total requests. |
| CDN Avg Time to First Byte | The average time in milliseconds from when the CDN received a request to the first byte of the response. CDN-cached responses are typically under 50ms. Responses served from the origin are typically 300ms to 700ms. AI live-fetch agents often show much higher values, which correspond to timed-out or very slow origin responses. High average values on live-fetch agent types are worth investigating as an AI visibility risk. |

### Dataset boundaries

This dataset captures only bot traffic from CDN access logs. It does not contain the following:

* **Human sessions, conversions, or engagement data.** Human sessions are in your existing web analytics dataset. To correlate AI demand with human outcomes, join the two datasets in CJA at the URL and host level.
* **Any person identifier such as ECID.** You cannot make a person-level join from this dataset. The join works at the URL and host level.
* **Sub-second time granularity.** The timestamp is hourly. You cannot break down traffic within an hour into minutes or seconds.
* **Page content or rendered HTML.** This dataset records the fact of the fetch and its outcome, not what the AI read from the page.
* **Conversion data.** Whether an AI answer led a user to visit the site or convert is not in this dataset. That analysis requires joining to human session data in CJA.

## Outbound integration

To be determined.

-->