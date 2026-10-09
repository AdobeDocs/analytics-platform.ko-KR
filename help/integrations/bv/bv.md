---
title: 브랜드 가시성 통합
description: Customer Journey Analytics과 브랜드 가시성 통합
feature: Experience Platform Integration
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fb3ebdba335ce2dde30d37b8aff4e8f201dc5d9f
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%
---

# Adobe Brand Visibility 통합

[Adobe Brand Visibility](https://experienceleague.adobe.com/ko/docs/brand-visibility/using/home){target="_blank"}은(는) 생성 엔진 최적화를 위한 생성 AI 우선 애플리케이션으로, 브랜드가 AI 기반 검색 환경에서 가시성, 정확성 및 영향력을 향상시킬 수 있도록 설계되었습니다. 브랜드 가시성은 AI가 생성한 답변의 브랜드 존재감에 대한 통찰력을 제공하고, 규범적인 콘텐츠 권장 사항을 제공하고, 최적화 수정 사항을 자동화합니다.

AI는 주요 검색 채널이 되었습니다. ChatGPT, Copilot, Copilot, 크롤링 브랜드 콘텐츠, 과 같은 대형 언어 모델(LLM) 에이전트.

>[!NOTE]
>
>브랜드 가시성 유료 서비스가 프로비저닝되어 있고 관리 커넥터를 통해 Experience Platform 구성에 연결되어 있어야 합니다.


>[!IMPORTANT]
>
>이 통합의 일부로, 미국에서 브랜드 가시성 데이터의 일부 임시 처리가 발생합니다. 데이터는 Customer Journey Analytics 계약에 구성된 대로 지정된 영역에 최종적으로 저장됩니다.


## 사용 사례

다음 두 가지 방법으로 Customer Journey Analytics과 Brand Visibility 간의 통합을 통해 혜택을 얻을 수 있습니다.

* **인바운드 통합**: Customer Journey Analytics의 브랜드 가시성 데이터를 사용하여 기존 웹, 모바일 및 기타 유형의 데이터와 함께 LLM 기반 트래픽(보트 웹 크롤러, RAG 요청, 에이전트 활동)을 측정합니다. 예를 들어 다음 작업을 수행할 수 있습니다.

  * 기존 채널과 함께 에이전트 소스별로 LLM 기반 트래픽을 측정합니다.

  * LLM에서 많이 사용하지만 사람 전환에서 성과가 낮은 콘텐츠를 식별합니다.

  * 중요한 경로에서 LLM 에이전트 요청이 실패하는 위치를 감지합니다.

  * 페이지에 대한 LLM 보트 수요를 URL 및 호스트 수준에서 일치하는 웹 데이터의 해당 페이지 전환 및 매출과 비교합니다.

* **아웃바운드 통합**: ChatGPT 또는 Perplexity와 같은 중요한 트래픽을 보내는 LLM 소스에 대한 AI 가시성을 최적화할 수 있도록 Customer Journey Analytics 성능 데이터를 브랜드 가시성에 보냅니다. 예를 들어 다음 작업을 수행할 수 있습니다.

  * 계속 전환하거나 수익을 창출하는 방문자를 보내는 LLM 소스를 확인하십시오. Customer Journey Analytics은 봇 데이터 세트가 아니라 참조된 웹 트래픽에서 이 값을 측정합니다.
  * LLM 소스의 순위를 보내는 사람 방문자의 다운스트림 값으로 지정한 다음 가장 성과가 좋은 소스에 AI 가시성 작업을 집중하십시오.


## 인바운드 통합

LLM 트래픽은 두 가지 방법으로 사이트에 도달합니다. Customer Journey Analytics은 다른 데이터 소스에서 각 방식으로 측정합니다.

첫 번째 방법은 AI 답변을 읽은 다음 클릭하여 사이트를 방문하는 사람입니다. 이 방문은 웹 데이터의 나머지 부분을 수집하는 동일한 JavaScript을 실행합니다. 따라서 기존 Customer Journey Analytics 웹 데이터에는 사용자를 보낸 방문 및 참조 도메인이 포함됩니다(예: chatgpt.com). Customer Journey Analytics은 이러한 방문을 자체적으로 AI 트래픽으로 레이블 지정하지 않습니다. 이들을 식별하고 그룹화하려면 AI 참조 도메인과 일치하는 연결에 파생 필드를 만든 다음, 세그먼트를 작성하고 해당 필드에 대해 보고합니다. [파생 필드](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}를 참조하세요. 이 사람 트래픽에는 브랜드 가시성 데이터 세트가 필요하지 않습니다.

두 번째 방법은 페이지를 직접 요청하는 보트 또는 에이전트입니다. 여기에는 사용자가 AI 도우미에 프롬프트를 제출할 때 발생하는 AI 인덱스 및 라이브 가져오기를 빌드하는 웹 크롤러가 포함됩니다. 이러한 요청은 JavaScript을 실행하지 않으므로 기존 웹 데이터는 이러한 요청을 기록하지 않습니다. 브랜드 가시성 데이터 세트는 CDN 계층에서 이 트래픽을 캡처합니다. 이 섹션의 나머지 부분에서는 해당 데이터 세트에 대해 설명합니다.


### 데이터 세트 온보드

브랜드 가시성 관리 커넥터는 데이터를 요약 데이터 세트로 Experience Platform에 전달합니다. Customer Journey Analytics에서 측정하려면 두 가지 설정 단계를 직접 완료합니다.

1. 브랜드 가시성 데이터 세트를 포함하는 연결을 만듭니다.
2. 해당 연결에 대한 데이터 보기를 만듭니다. 데이터 보기를 통해 Analysis Workspace에서 아래의 차원 및 지표를 사용할 수 있습니다.

데이터 세트:

* XDM 요약 지표 클래스를 기반으로 하는 [요약 데이터 세트](/help/data-views/summary-data.md)를 사용합니다.
* URL 및 호스트, 시간 및 요청 특성(예: 보트 유형, CDN 공급자 및 상태)별로 데이터를 버킷합니다.

>[!NOTE]
>
>브랜드 가시성 데이터 세트에는 집계된 데이터가 포함되어 있습니다. 사용자 식별자, 프롬프트 또는 응답과 같은 PII는 포함되지 않습니다.
>

요약 데이터 세트이므로 조회 데이터 세트로 사용하고 전체 URL 키의 이벤트 데이터 세트에 조인할 수 있습니다.

브랜드 가시성이 **CDN URL** 차원에서 이 키를 제공합니다. Customer Journey Analytics에서 웹 데이터를 저장하는 방법과 유사하게 호스트와 요청된 경로를 하나의 정규화된 전체 URL로 결합합니다. 가입 성공 여부는 사용자의 데이터 수집에 따라 다릅니다. 이벤트 데이터 세트에는 동등한 전체 URL 필드 또는 브랜드 가시성이 제공하는 URL과 일치하도록 구문 분석하고 정규화할 수 있는 필드가 필요합니다. 양측이 동일한 전체 URL로 확인되면 브랜드 가시성 레코드는 웹 데이터의 해당 페이지와 일치합니다.

자세한 내용은 다음을 참조하십시오.

* [인바운드 통합 설정 및 구성](/help/integrations/bv/configure.md)
* [데이터 세트 참조](/help/integrations/bv/reference.md)

## 아웃바운드 통합

아웃바운드 통합에 대한 자세한 내용은 Adobe Brand Visibility 설명서의 [Customer Journey Analytics 통합](https://experienceleague.adobe.com/ko/docs/brand-visibility/using/resources/customer-journey-analytics-integration){target="_blank"}을 참조하십시오.
