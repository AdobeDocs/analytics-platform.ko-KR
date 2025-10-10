---
title: 파생된 필드를 사용하여 LLM 및 AI 생성 트래픽에 대해 보고합니다
description: 파생 필드를 기반으로 사용하여 Workspace에서 LLM 및 AI 생성 트래픽에 대해 보고하는 방법을 이해합니다.
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 8862bfdf873c4c3c5e795f3b299040b3dc253647
workflow-type: tm+mt
source-wordcount: '1275'
ht-degree: 1%

---


# LLM 및 AI 생성 트래픽에 대한 보고서

이 사용 사례 문서에서는 Customer Journey Analytics 파생 필드 기능을 LLM(대형 언어 모델) 및 AI 생성 트래픽에 대한 보고의 기반으로 사용하는 방법에 대해 알아봅니다.

>[!NOTE]
>
>[검색 방법](#detection-methods), [검색 서명](#detection-signatures) 및 [구현 전략](#implementation)의 효과는 특정 데이터 수집 방법, Experience Platform 데이터 세트 적용 범위 및 Customer Journey Analytics 구현에 따라 다릅니다. 결과는 기술 환경, 데이터 거버넌스 정책 및 구현 접근 방식에 따라 달라질 수 있습니다. Experience Edge을 사용할 때는 원시 사용자 에이전트 문자열을 기록할지 또는 장치 정보를 수집할지 선택해야 합니다.
>

## 검색 방법

LLM 및 AI 생성 트래픽을 탐지하려면 다음을 구별합니다.

* **LLM 크롤러**: RAG(Augmented Generation) 교육 및 검색을 위해 데이터를 수집합니다.
* **AI 에이전트**: 사람 대신 작업을 수행하는 인터페이스로 작동합니다. AI 에이전트는 웹 분석 추적 메서드를 우회하는 API를 통해 상호 작용하는 것을 선호합니다. 그럼에도 불구하고 여전히 웹 사이트를 통해 AI가 생성한 트래픽의 상당 부분을 분석할 수 있습니다.

LLM 및 AI 생성 트래픽을 식별하고 모니터링하는 세 가지 일반적인 코어 감지 방법은 다음과 같습니다.

* **사용자 에이전트 식별**: 서버에 대한 요청이 있으면 HTTP 사용자 에이전트 헤더가 추출되어 알려진 AI 크롤러 및 에이전트 패턴에 대해 분석됩니다. 이 서버측 메서드는 HTTP 헤더에 액세스해야 하며 데이터 수집 계층에서 구현된 경우 가장 효과적입니다.
* **레퍼러 분류**: HTTP 레퍼러 헤더에 현재 요청에 연결된 이전 웹 페이지의 URL이 포함되어 있습니다. 이 헤더는 사용자가 ChatGPT 또는 Perplexity와 같은 웹 인터페이스에서 사이트를 클릭스루할 때 표시됩니다.
* **쿼리 매개 변수 검색**: AI 서비스는 URL 매개 변수(특히 UTM 매개 변수)를 링크에 추가할 수 있습니다. 이러한 매개 변수는 URL에서 유지되며 표준 분석 구현을 통해 감지할 수 있으므로 이러한 URL 매개 변수는 클라이언트측 추적 시나리오에서도 중요한 표시기가 됩니다.


다음 표는 다양한 LLM 및 AI 상호 작용 시나리오에 대해 감지 방법을 사용할 수 있는 방법을 보여 줍니다.

| 시나리오 | 사용자 에이전트 식별 | 레퍼러 분류 | 쿼리 매개변수 감지 |
|---|---|---|---|
| **모델 교육** | 서버측 로깅이 구현될 때 에이전트(`GPTBot`, `ClaudeBot` 등)를 식별할 수 있습니다. | 분류를 할 수 없습니다. AI 크롤러는 교육 중에 레퍼러를 생성하지 않습니다. | 발견은 불가능합니다. AI 크롤러는 교육 중에 매개 변수를 추가하지 않습니다. |
| **에이전트 탐색** | 서버측 로깅이 헤더를 캡처할 때 에이전트(`ChatGPT-User`, `claude-web`)를 식별할 수 있습니다. | 에이전트가 레퍼러 보존이 포함된 AI 인터페이스에서 탐색하는 경우 분류할 수 있습니다. | AI 서비스가 추적 매개 변수를 추가하면 감지도 가능해질 수 있습니다. |
| 쿼리에 응답할 **RAG(검색 증강 생성)를 검색합니다** | 에이전트(`OAI-SearchBot`, `PerplexityBot`)는 서버측 로깅으로 식별할 수 있습니다. | RAG 작업은 종종 레퍼러 메커니즘을 무시하므로 일반적으로 분류를 수행할 수 없습니다. | AI 제공자가 구체적으로 구현하지 않으면 탐지가 거의 불가능하다. |
| **사용자가 클릭스루** | 에이전트를 식별할 수 없습니다. AI 에이전트는 일반 사용자 에이전트로 표시됩니다. | 사용자가 AI 인터페이스([chatgpt.com](https://chatgpt.com), [claude.ai](https://claude.ai) 등)에서 링크를 클릭하면 분류가 가능합니다. | AI 서비스가 아웃바운드 링크에 UTM 매개 변수를 추가하면 검색이 가능합니다. |
| **트래픽 가시성 조건** | 에이전트 식별을 위해 서버측 로깅을 Customer Journey Analytics 또는 서버측 태깅과 통합해야 합니다. | 분류는 AI 플랫폼 레퍼러 정책 및 적절한 HTTP 헤더 전송에 따라 다릅니다. | 검색을 위해서는 리디렉션 및 적절한 URL 매개 변수 수집을 통한 매개 변수 보존이 필요합니다. |

### 과제

LLM 및 AI 에이전트는 디지털 속성과 상호 작용할 때 복잡하고 진화하는 동작을 보여 줍니다. 이러한 기술은 플랫폼과 버전 간에 일관되지 않게 작동합니다. 이러한 불일치는 데이터 전문가에게 고유한 문제를 만듭니다. 행동 패턴은 크게 다르며 사용되는 특정 AI 플랫폼, 버전 및 상호 작용 모드에 따라 다릅니다. 이러한 운영 다양성은 표준 분석 프레임워크 내에서 LLM 및 AI 생성 트래픽을 추적하고 분류하는 노력을 복잡하게 합니다. 이러한 상호 작용의 복잡한 특성은 신속한 진화와 함께 데이터 무결성을 유지하기 위해 미묘한 탐지 및 분류 방법이 필요합니다.

* **부분 데이터 수집**: 일부 최신 AI 에이전트는 제한된 JavaScript을 실행하므로 클라이언트측 구현에 대한 분석 데이터가 불완전합니다. 그 결과 일부 상호 작용은 추적되지만 다른 상호 작용은 누락됩니다.
* **세션 데이터가 일치하지 않음**: AI 에이전트가 세션 또는 페이지 유형에 따라 JavaScript을 다르게 실행할 수 있습니다. 이러한 실행 차이는 클라이언트측 구현을 위해 Customer Journey Analytics에서 조각화된 사용자 여정을 만듭니다.
* **검색 문제**: 부분 추적을 사용하면 특정 접점이 분석에 표시되지 않을 수 있으므로 검색을 신뢰할 수 없게 됩니다.


## 검색 서명

2025년 8월 현재, 검출 방식별로 다음과 같은 특정 신호를 확인할 수 있다.

### 사용자 에이전트 식별

<table>
<thead>
<tr>
<th>크롤러</th>
<th>사용자 에이전트 문자열</th>
<th>목적/행동</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>GPTBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; GPTBot/1.1; +<a href="https://openai.com/gptbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/gptbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">ChatGPT 및 언어 모델 교육을 위한 OpenAI의 기본 웹 크롤러</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/1.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">ChatGPT가 사용자 대신 웹 사이트를 탐색할 때 사용됩니다(레거시).</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User v2</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/2.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">온디맨드 가져오기 및 응답형 조회에 대한 ChatGPT의 업데이트된 버전</a></td>
</tr>
<tr>
<td><strong>OAI-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; OAI-SearchBot/1.0; +<a href="https://openai.com/searchbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/searchbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">콘텐츠 검색을 위한 ChatGPT의 검색 중심 크롤러</a></td>
</tr>
<tr>
<td><strong>클로드봇</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ClaudeBot/1.0; +claudebot@anthropic.com</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">클라우드 AI 비서 교육 및 업데이트를 위한 인류 크롤러</a></td>
</tr>
<tr>
<td><strong>Claud-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-User/1.0; +Claude-User@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Claude AI 사용자는 개인이 Claude에 질문을 할 때 Cl을 사용하여 웹 사이트에 액세스 할 수 있습니다 ...</a></td>
</tr>
<tr>
<td><strong>Claude-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-SearchBot/1.0; +Claude-SearchBot@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">온라인 콘텐츠를 분석하여 Claude AI 사용자의 검색 결과 품질을 개선하기 위해 웹을 탐색합니다.</a></td>
</tr>
<tr>
<td><strong>PlexityBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; PerplexityBot/1.0; +<a href="https://www.perplexity.ai/perplexitybot" target="_blank" rel="noopener nofollow noreferrer">https://perplexity.ai/perplexitybot</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">실시간 웹 데이터 인덱싱을 위한 Perplestity.ai 크롤러</a></td>
</tr>
<tr>
<td><strong>곤란-사용자</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Perplexity-User/1.0; +<a href="https://www.perplexity.ai/useragent" target="_blank" rel="noopener nofollow noreferrer">https://www.perplexity.ai/useragent</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">사용자가 복잡성 인용 을 클릭하면 페이지가 로드됩니다(robots.txt 무시)</a></td>
</tr>
<tr>
<td><strong>Google 확장</strong></td>
<td><code>Mozilla/5.0 (compatible; Google-Extended/1.0; +<a href="https://support.google.com/webmasters/answer/182072" target="_blank" rel="noopener nofollow noreferrer">http://www.google.com/bot.html</a>)</code></td>
<td><a href="https://blog.google/technology/ai/an-update-on-web-publisher-controls/" target="_blank" rel="noopener nofollow noreferrer">표준 Googlebot과 별도의 Gemini용 Google AI 중심 크롤러</a></td>
</tr>
<tr>
<td><strong>BingBot</strong></td>
<td><code>Mozilla/5.0 (compatible; BingBot/1.0; +<a href="http://www.bing.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bing.com/bot.html</a>)</code></td>
<td>Bing 검색 및 Bing 채팅(Copilot)을 지원하는 Microsoft 크롤러</td>
</tr>
<tr>
<td><strong>DuckAssisteBot</strong></td>
<td><code>Mozilla/5.0 (compatible; DuckAssistBot/1.0; +<a href="https://duckduckgo.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.duckduckgo.com/bot.html</a>)</code></td>
<td><a href="https://duckduckgo.com/duckduckgo-help-pages/results/duckassistbot" target="_blank" rel="noopener nofollow noreferrer">DuckDuckGo의 개인 AI 답변 기능인 DuckAssist에 대한 콘텐츠를 스크랩합니다</a></td>
</tr>
<tr>
<td><strong>YouBot</strong></td>
<td><code>Mozilla/5.0 (compatible; YouBot (+<a href="http://www.you.com" target="_blank" rel="noopener nofollow noreferrer">http://www.you.com</a>))</code></td>
<td>Crawler behind You.com의 AI 검색 및 브라우저 도우미</td>
</tr>
<tr>
<td><strong>meta-externalagent</strong></td>
<td><code>Mozilla/5.0 (compatible; meta-externalagent/1.1 (+<a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers" target="_blank" rel="noopener nofollow noreferrer">https://developers.facebook.com/docs/sharing/webmasters/crawler</a>))</code></td>
<td><a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers#identify-2" target="_blank" rel="noopener nofollow noreferrer">LLM 교육 또는 세부 조정을 위한 Meta의 데이터 수집 보트</a></td>
</tr>
<tr>
<td><strong>Amazonbot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/600.2.5 (KHTML, like Gecko) Version/8.0.2 Safari/600.2.5 (Amazonbot/0.1; +<a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">https://developer.amazon.com/support/amazonbot</a>)</code></td>
<td><a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">검색 및 AI 애플리케이션용 Amazon 크롤러</a></td>
</tr>
<tr>
<td><strong>Applebot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_5) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/13.1.1 Safari/605.1.15 (Applebot/0.1; +<a href="https://support.apple.com/kb/HT6619" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/go/applebot</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Spotlight, Siri 및 Safari용 Apple 크롤러</a></td>
</tr>
<tr>
<td><strong>Applebot-Extended</strong></td>
<td><code>Mozilla/5.0 (compatible; Applebot-Extended/1.0; +<a href="https://www.apple.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/bot.html</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">향후 AI 모델을 위한 Apple의 AI 중심 크롤러(옵트인)</a></td>
</tr>
<tr>
<td><strong>바이트스파이더</strong></td>
<td><code>Mozilla/5.0 (compatible; Bytespider/1.0; +<a href="https://www.bytedance.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bytedance.com/bot.html</a>)</code></td>
<td>TikTok 및 기타 서비스를 위한 ByteDance의 AI 데이터 수집기</td>
</tr>
<tr>
<td><strong>MistralAI-User</strong></td>
<td><code>Mozilla/5.0 (compatible; MistralAI-User/1.0; +<a href="https://mistral.ai/bot" target="_blank" rel="noopener nofollow noreferrer">https://mistral.ai/bot</a>)</code></td>
<td><a href="https://docs.mistral.ai/robots/" target="_blank" rel="noopener nofollow noreferrer">미스트랄의 '르 챗' 비서 리얼-타임 인용 페처</a></td>
</tr>
<tr>
<td><strong>코헤아이</strong></td>
<td><code>Mozilla/5.0 (compatible; cohere-ai/1.0; +<a href="http://www.cohere.ai/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.cohere.ai/bot.html</a>)</code></td>
<td>Cohere의 언어 모델에 대한 텍스트 데이터 수집</td>
</tr>
</tbody>
</table>


### 레퍼러 분류

<table>
<thead>
<tr>
<th><strong>소스</strong></th>
<th><strong>리퍼러</strong></th>
<th><strong>트래픽 유형</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td>chatgpt.com</td>
<td>ChatGPT 인터페이스에서 직접 트래픽</td>
</tr>
<tr>
<td>클로드</td>
<td>claude.ai</td>
<td>Anthropic의 Claude 인터페이스에서 트래픽</td>
</tr>
<tr>
<td>Google 제미니</td>
<td>gemini.google.com</td>
<td>Google AI 어시스턴트의 트래픽</td>
</tr>
<tr>
<td>Microsoft Copilot</td>
<td>copilot.microsoft.com</td>
<td>Microsoft AI 어시스턴트의 트래픽</td>
</tr>
<tr>
<td>Microsoft Copilot</td>
<td>m365.cloud.Microsoft</td>
<td>Microsoft의 AI 어시스턴트 트래픽(Microsoft 365 클라우드 서비스)</td>
</tr>
<tr >
<td>곤란 AI</td>
<td>perplexity.ai</td>
<td>인용이 있는 AI 검색의 트래픽</td>
</tr>
<tr>
<td>META AI</td>
<td>meta.ai</td>
<td>Meta AI 어시스턴트의 트래픽</td>
</tr>
</tbody>
</table>

### 쿼리 매개변수 감지

<table>
<thead>
<tr>
<th><strong>LLM 서비스</strong></th>
<th>예제 URL</th>
<th><strong>쿼리 매개 변수</strong></th>
<th><strong>값 예</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td ><a href="https://www.yoursite.com/product?utm_source=chatgpt.com" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/product?utm_source=chatgpt.com</a></td>
<td>utm_source</td>
<td>chatgpt.com</td>
</tr>
<tr>
<td>곤란</td>
<td><a href="https://www.yoursite.com/article?utm_source=perplexity" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/article?utm_source=perplexity</a></td>
<td>utm_source</td>
<td>곤란</td>
</tr>
</tbody>
</table>


## 구현

[파생 필드](/help/connections/overview.md), [세그먼트](/help/data-views/data-views.md) 및 [작업 영역 프로젝트](/help/analysis-workspace/home.md)의 특정 설정 및 구성을 통해 일반적인 Customer Journey Analytics 설정([연결](#derived-fields), [데이터 보기](#segments) 및 [작업 영역 프로젝트](#workspace-project)) 내에서 LLM 및 AI가 생성한 트래픽을 보고할 수 있습니다.


### 파생 필드

검출 방법 및 검출 신호를 구성하기 위해서, 도출된 필드들을 기초로 한다. 예를 들어 [사용자 에이전트 식별](#user-agent-identification), [쿼리 매개 변수 감지](#query-parameter-detection) 및 [레퍼러 분류](#referrer-classification)에 대해 파생 필드를 정의합니다.

#### LLM/AI 사용자 에이전트 식별

[Case When](/help/data-views/derived-fields/derived-fields.md#case-when) 파생 필드 함수를 사용하여 LLM/AI 사용자 에이전트를 식별하는 파생 필드를 정의합니다.

![LLM/AI 사용자 에이전트 식별](assets/aitraffic-useragents.png){zoomable="yes"}


#### LLM/AI 쿼리 매개 변수 감지

[URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse) 및 [분류](/help/data-views/derived-fields/derived-fields.md#classify) 파생 필드 함수를 사용하여 쿼리 매개 변수를 검색하는 파생 필드를 정의합니다.

![LLM/AI UTM 매개 변수 검색](assets/aitraffic-utmparams.png){zoomable="yes"}


#### LLM/AI 레퍼러 분류

[URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse) 및 [분류](/help/data-views/derived-fields/derived-fields.md#classify) 파생 필드 함수를 사용하여 레퍼러를 분류하는 파생 필드를 정의합니다.

(assets/aitraffic-referrers.png











































































































































































































































































































































































































){zoomable="yes"}


### 세그먼트

LLM 및 AI 생성 트래픽과 관련된 이벤트, 세션 또는 사람을 식별하는 데 도움이 되는 전용 세그먼트를 설정합니다. 예를 들어 이전에 만든 파생 필드를 사용하여 LLM 및 AI 생성 트래픽을 식별하는 세그먼트를 정의합니다.

![LLM 및 AI 생성 트래픽 세그먼트](assets/aitraffic-segment.png){zoomable="yes"}


### Workspace 프로젝트

파생된 필드와 세그먼트를 사용하여 LLM 및 AI가 생성한 트래픽을 보고하고 분석합니다. 예를 들어 아래에 주석이 있는 프로젝트를 참조하십시오.

![LLM 및 AI가 생성한 트래픽 Workspace 프로젝트](assets/aitraffic-workspace.png){zoomable="yes"}



>[!MORELIKETHIS]
>
>이 사용 사례 문서는 블로그 문서 [Adobe Customer Journey Analytics에서 LLM 및 AI 생성 트래픽 추적 및 분석](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/tracking-and-analyzing-llm-and-ai-generated-traffic-in-adobe/ba-p/771967)을 기반으로 합니다.
>
>
