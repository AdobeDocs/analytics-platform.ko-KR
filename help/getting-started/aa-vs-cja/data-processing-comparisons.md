---
title: Adobe Analytics 및 CJA 보고 기능에서 데이터 처리 비교
description: 다양한 보고 기능에 대한 데이터 처리 차이점 이해
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 23%

---

# Adobe Analytics 및 CJA 보고 기능에서 데이터 처리 비교

다양한 보고 기능에 대한 데이터 처리 차이점을 이해하면 사용 가능한 지표와 지표가 다를 수 있는 이유를 이해하는 데 도움이 될 수 있습니다.

예를 들어 Adobe Analytics에서 지표로 &quot;방문 횟수&quot;는 데이터 처리 시간에 정의되고 CJA의 지표로 &quot;세션&quot;은 보고서 시간에 계산되므로 두 지표는 CJA 데이터 보기 내의 세션 정의에 사용되는 규칙에 따라 다를 수 있습니다.

또한 방문 횟수 및 세션 을 Analytics 소스 커넥터에서 만든 데이터 세트에서 사용할 수 없으므로 비교를 수행하려면 쿼리 논리에 세션을 정의해야 합니다.

## 용어 {#terms}

아래 표에서는 Adobe Analytics 및 CJA에 적용되는 다양한 유형의 처리 로직에 대한 용어를 정의합니다.

| 용어 | 정의 | 참고 |
| --- | --- | --- |
| 처리 시간 논리 | 데이터가 처리 중일 때 보고 및 분석 목적으로 저장되기 전에 수행되는 로직입니다. | 이 논리는 &#39;기존 데이터에 결합됨&#39;이며 일반적으로 쉽게 변경할 수 없습니다. |
| 보고서 시간 논리 | 보고서 실행 시 수행되는 논리. | 이 논리는 비파괴적으로 보고서 런타임 시 미래 및 이전 데이터에 적용할 수 있습니다. |
| 히트 수준 논리 | 행 단위로 적용된 논리. | 예: 처리 규칙, VISTA, 특정 마케팅 채널 규칙. |
| 방문 수준 논리 | 방문 수준에서 적용된 논리. | 예: 방문 및 세션 정의. |
| 방문자 수준 논리 | 방문자 수준에서 적용된 논리. | 예: 교차 장치/교차 채널 방문자 결합. |
| 세그먼트(필터) 논리 | 히트/방문/방문자(이벤트/세션/개인) 세그먼트(필터) 규칙 평가. | 예: 빨간 신발을 사신 분들입니다. |
| 계산된 지표 | 세그먼트와 필터를 포함한 복잡한 공식을 기반으로 할 수 있는 고객이 생성한 사용자 지정 지표 평가입니다. | 예: 빨간색 신발을 구입한 사람 수. |
| 속성 논리 | 속성을 계산하는 논리. | 예: eVar 지속성. |

{style=&quot;table-layout:auto&quot;}

시간이 지나면서 Adobe Analytics 및 이제 Customer Journey Analytics은 보고서 런타임 시 방문 및 방문자 수준 데이터 논리를 수행할 수 있도록 함으로써 유연성을 개선했습니다.

## 데이터 처리 유형 {#types}

Adobe Analytics 및 CJA에 대해 수행되는 데이터 처리 단계 및 이러한 단계의 타이밍 은 Analytics 기능에서 Analytics 기능으로 달라집니다. 아래 표는 각 Analytics 기능에 대한 데이터 처리 유형과 데이터 처리가 적용되는 시기에 대한 요약을 제공합니다.

| Analytics 기능 | 처리 시간에 적용됨 | 보고서 시간에 적용됨 | 사용할 수 없음 | 참고 |
| --- | --- | --- | --- | --- |
| [코어 AA](https://experienceleague.adobe.com/docs/analytics.html?lang=kr) 보고<br/>(보고서 처리 시간이 있는 Attribution IQ 또는 가상 보고서 세트 포함 안 됨) | <ul><li>[처리 규칙](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=ko)</li><li>[VISTA 규칙](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>히트 수준 [마케팅 채널 규칙](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=ko)</li><li>방문 수준 마케팅 채널 규칙(참고 참조)</li><li>방문 정의</li><li>속성 논리</li></ul> | <ul><li>세그먼트 논리</li><li>계산된 지표</li></ul> | <ul><li>교차 디바이스 분석 (참고 참조)</li></ul> | <ul><li>CDA를 사용하려면 보고서 처리 시간이 있는 가상 보고서 세트를 사용해야 합니다.</li><li>방문 수준 마케팅 채널 규칙에는 다음이 포함됩니다. **방문의 첫 페이지임**, **마지막 터치 채널 무시**, 및 **마케팅 채널 만료**. (자세한 내용은 [설명서](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ko))</li></ul> |
| 코어 AA [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=en) | <ul><li>처리 규칙</li><li>VISTA 규칙</li><li>히트 수준 마케팅 채널 규칙</li><li>방문 수준 마케팅 채널 규칙</li><li>방문 정의</li><li>속성 논리</li></ul> | <ul><li>세그먼트 논리</li></ul> | <ul><li>계산된 지표</li><li>크로스 디바이스 분석</li></ul> |  |
| 코어 AA [데이터 피드](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) | <ul><li>처리 규칙</li><li>VISTA 규칙</li><li>히트 수준 마케팅 채널 규칙</li><li>방문 수준 마케팅 채널 규칙</li><li>방문 정의(visitnum 필드)</li><li>속성 논리(사후 열)</li></ul> |  | <ul><li>세그먼트 논리</li><li>계산된 지표</li><li>크로스 디바이스 분석</li></ul> | <ul><li>데이터 피드의 특정 마케팅 채널 관련 열에 대한 ID 매핑은 데이터 피드에 포함되지 않습니다. (자세한 내용은 [데이터 피드 설명서](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ko-KR))</li></ul> |
| 코어 AA [실시간 스트리밍](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> 처리 규칙</li><li>VISTA 규칙</li><ul> |  | <ul><li>히트 수준 마케팅 채널 규칙</li><li>방문 수준 마케팅 채널 규칙</li><li>방문 논리</li><li>속성 논리</li><li>세그먼트 논리</li><li>계산된 지표</li><li>크로스 디바이스 분석</li></ul> |  |
| 코어 AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=ko-KR) | <ul><li>처리 규칙</li><li>VISTA 규칙</li><li>방문 정의(참고 참조)</li><li>교차 디바이스 분석 (참고 참조)</li></ul> | <ul><li>히트 수준 마케팅 채널 규칙(참고 참조)</li><li>방문 수준 마케팅 채널 규칙(참고 참조) 속성 논리</li><li>세그먼트 논리</li><li>계산된 지표</li></ul> |  | <ul><li>CDA를 사용하려면 보고서 처리 시간이 있는 가상 보고서 세트를 사용해야 합니다.</li><li>핵심 분석의 Attribution IQ은 보고서 시간에 완전히 파생된 마케팅 채널(즉, 파생된 mid 값)을 사용합니다.</li><li>Attribution IQ은 보고서 시간 처리 VRS에 사용되는 경우를 제외하고 처리 시간 방문 정의를 사용합니다.</li></ul> |
| 핵심 AA 가상 보고서 세트 및 [보고서 처리 시간](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ko-KR) (VRS RTP) | <ul><li>처리 규칙</li><li>VISTA 규칙</li><li>[크로스 디바이스 분석](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ko-KR)</li></ul> | <ul><li>방문 정의</li><li>속성 논리</li><li>세그먼트 논리</li><li>계산된 지표</li><li>기타 VRS RTP 설정</li></ul> | <ul><li>히트 수준 마케팅 채널 규칙</li><li>방문 수준 마케팅 채널 규칙</li></ul> | <ul><li>VRS RTP 를 참조하십시오 [설명서](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en).</li></ul> |
| [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR)AEP data lake의 기반 데이터 세트 | <ul><li>처리 규칙</li><li>VISTA 규칙</li><li>히트 수준 마케팅 채널 규칙</li><li>필드 기반 결합(참고 참조)</li></ul> |  | <ul><li>[방문 수준 마케팅 채널 규칙](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>방문 논리</li><li>속성 논리</li><li>필터 논리</li></ul> | <ul><li>고유한 필터 논리 및 계산된 지표를 적용해야 합니다</li><li>필드 기반 결합은 Analytics 소스 커넥터에서 만든 데이터 세트 외에 별도의 결합된 데이터 세트를 만듭니다.</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en) 보고 | <ul><li>처리 규칙</li><li>VISTA 규칙</li><li>히트 수준 [마케팅 채널 규칙](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>[연결 설정](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ko)</li><li>필드 기반 결합(참고 참조)</li></ul> | <ul><li>세션 정의</li><li>[데이터 보기 설정](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ko)</li><li>속성 논리</li><li>계산된 지표</li><li>필터 논리</li></ul> | <ul><li>방문 수준 마케팅 채널 규칙</li></ul> | <ul><li>필드 기반 결합을 사용하려면 결합된 데이터 세트를 사용해야 합니다.</li></ul> |

{style=&quot;table-layout:auto&quot;}
