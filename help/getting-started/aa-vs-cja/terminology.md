---
title: Analytics 소스 커넥터를 통해 전달된 Analytics 데이터의 용어 비교
description: 일부 용어 차이점
solution: Customer Journey Analytics
source-git-commit: 287c75fd2b519f3d1d86209e0b0ab4ed7f761814
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 27%

---


# Analytics 소스 커넥터를 통해 전달된 Analytics 데이터의 용어 비교

Adobe Analytics, 데이터 피드, Analytics 소스 커넥터/데이터 레이크 및 CJA 간에는 일부 용어 차이가 있습니다. 이 주제는 이러한 차이점을 강조 표시하고 명확하게 하는 것을 목표로 합니다.

| 관련 용어 | Adobe Analytics | Adobe Analytics 데이터 피드 | Analytics 소스 커넥터/Data Lake | CJA | 참고 |
|---|---|---|---|---|---|
| <ul><li>히트 수</li><li>발생 횟수</li><li>레코드</li><li>이벤트</li></ul> | **발생 횟수** 지표<br><br>다음을 참조하십시오.<ul><li>[Adobe Analytics에 사용되는 용어](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=ko-KR)</li><li>[발생 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ko-KR)</li></ul> | 데이터 피드 파일에 있는 행(레코드)의 수입니다 | 데이터 집합에 있는 행(레코드) 수<br><br>다음을 참조하십시오.<ul><li>[Adobe Analytics 데이터와 CJA 데이터 비교](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=en)</li></ul> | **이벤트** 지표 | <ul><li>Adobe Analytics에서 &quot;히트&quot;와 &quot;발생&quot; 은 동의어입니다.</li><li>자세한 내용은 _사용자 지정 이벤트_ 아래의 제품에서 사용할 수 있습니다.</li><li>특정 데이터는 Analytics 소스 커넥터를 통해 AEP로 전송할 때 필터링됩니다. 자세한 내용은 [Adobe Analytics 데이터를 CJA 데이터와 비교](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=en) |
| <ul><li>고유 방문자 수</li><li>고유 장치</li><li>고유 쿠키</li></ul> | **고유 방문자 수** 지표<br><br>다음을 참조하십시오.<ul><li>[Adobe Analytics에 사용되는 용어](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>[고유 방문자 수](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html?lang=ko-KR)</li></ul> | 의 고유 값 **post\_visid\_high &amp; post\_visid\_low** 함께 연결합니다.<br><br>See:<ul><li>[데이터 피드를 사용한 일반 지표 계산](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=en)</li></ul> | 고유 개수 **endUserIDs.\_experience.aaid.id** | **사람** 지표, **endUserIDs.\_experience.aaid.id** 가 개인 ID로 선택됩니다. | <ul><li>Adobe Analytics의 &quot;방문자&quot;는 일반적으로 쿠키와 같은 &quot;장치 식별자&quot;와 연결됩니다. AAID는 ECID가 아니라 Adobe Analytics의 기본 장치 식별자입니다. 참조 - [AAID, ECID, AACUCUSTOMER 및 Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/aaid-ecid-adc.html?lang=en).</li><li>CJA에서는 &quot;방문자&quot;가 기본 지표가 아닙니다. 하지만 만약 당신이 **endUserIDs.\_experience.aaid.id** 개인 ID로서 CJA의 사람 지표는 Adobe Analytics의 고유 방문자 수와 거의 같습니다.</li></ul> |
| <ul><li>사람</li></ul> | **사람** 지표<br><br> 다음을 참조하십시오.<ul><li>[사람](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=en)</li></ul> | 사용할 수 없음 | 고유 개수 **_\&lt;path>_.stitchedId**(결합된 데이터 세트에서만 사용 가능) | **인물 지표** | <ul><li>CJA의 사람 지표는 개인 ID의 고유한 수입니다. CJA 연결에서 개인 ID로 선택하는 사항에 따라 사람 지표는 다른 의미일 수 있습니다.</ul></li> |
| <ul><li>방문 횟수</li><li>세션</li></ul> | **방문 횟수** 지표<br><br>다음을 참조하십시오.<ul><li>[Adobe Analytics에 사용되는 용어](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>[방문 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=en)</li><li>[보고서 처리 시간](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ko-KR)</ul></li> | 의 고유 값 **post\_visid\_high, post\_visid\_low, visit\_num &amp; visit\_start\_time\_gmt** 함께 연결합니다.<br><br>다음을 참조하십시오.<ul><li>[데이터 피드를 사용한 일반 지표 계산](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=en)</li></ul> | 사용할 수 없음 | **세션** 지표 | <ul><li>Adobe Analytics 가상 보고서 세트 및 CJA 데이터 보기의 보고서 처리 시간을 사용하면 방문(세션)의 개념을 구성할 수 있습니다. 따라서 적용된 정의에 따라 방문(세션) 카운트가 환경 간에 다를 수 있습니다. 참조 - [Adobe Analytics 및 CJA 보고 기능에서 데이터 처리 비교](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/data-processing-comparisons.html?lang=en) 및 [가상 보고서 세트, 데이터 보기, AEP 샌드박스 및 Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/vrs-dataview-sandbox-adc.html?lang=en). |
| <ul><li>사용자 정의 이벤트</li><li>성공 이벤트</li></ul> | 사용자 지정 이벤트 1-1000 | **post\_events\_list**<br><br>&#x200B;다음을 참조하십시오.<ul><li>[데이터 피드를 사용한 일반 지표 계산](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=en) | **\_experience.analytics .<ul>event1to100.event1 **through<br>** event901to1000.event1000 **</ul> | **\_experience.analytics .<ul>event1to100.event1 **through<br>** event901to1000.event1000 **</ul> | <ul><li>Adobe Analytics의 &quot;이벤트&quot;는 [성공 이벤트](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=en) (사용자 지정 이벤트) 이미지 요청에 설정된 값을 반환합니다(데이터 수집 서버 호출).</ul> |
| <ul><li>이벤트 중복 제거</li><li>지표 중복 제거</ul></li> | See:<ul><li>[이벤트 ID 직렬화](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en)</li></ul> | 다음 **post_events_list** 열에는 중복 제거된 이벤트 지표가 포함되어 있습니다.<br><br>See <ul><li>[데이터 열 참조](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en). </ul></li> | 사용할 수 없음 | 다음을 참조하십시오.<ul><li>[지표 중복 제거 구성 요소 설정](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=ko-KR) | <ul><li>Adobe Analytics의 이벤트/지표 중복 제거는 CJA와 약간 다릅니다. Adobe Analytics에서 데이터 중복 제거는 데이터 처리 시 발생합니다. CJA에서 중복 제거는 보고서 런타임 시 발생하므로 보다 유연하게 대처할 수 있습니다. 중복 제거된 지표는 Adobe Analytics과 CJA에서 약간 다를 수 있습니다.</li></ul> |
| <ul><li>인스턴스 지표</li></ul> | 다음을 참조하십시오.<ul><li>[인스턴스](https://experienceleague.adobe.com/docs/analytics/components/metrics/instances.html?lang=en) | pre&quot; 변수가 null(예: eVar1)이 아닌 횟수입니다. | mid 변수가 null이 아닌 횟수(예: **\_experience.analytics .<br>customDimensions.eVars.eVar1**). | **인스턴스** 지표 | <ul><li>인스턴스는 일반적으로 변수가 설정된 횟수를 확인하는 수단으로 prop 및 eVar 열과 연결됩니다. |