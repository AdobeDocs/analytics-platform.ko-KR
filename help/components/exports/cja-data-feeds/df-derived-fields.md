---
title: 데이터 피드에 데이터 변환 적용
description: 구성 요소 설정, 파생 필드 또는 SQL을 사용하여 데이터 피드 데이터를 변환하는 다양한 방법에 대해 알아봅니다.
hide: true
feature: Components
source-git-commit: 082927c1d511ba0831beba08aaaac0e2d0d9fbf6
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 5%
---
# 데이터 피드에 데이터 변환 적용

{{release-limited-testing}}

다음 방법 중 하나를 사용하여 데이터 피드 데이터를 변환할 수 있습니다.

* [데이터 보기 구성 요소 설정](/help/data-views/component-settings/overview.md), 사용

* [파생 필드](/help/data-views/derived-fields/derived-fields.md)

* SQL

당신이 선택하는 방법은 때때로 선호의 문제이다. 다음 표에서는 트레이드오프를 비교합니다.

## 데이터 변환 방법 비교

다음 표는 각 방법의 장단점을 전반적으로 비교한 것이다.

| 메서드 | 장점 | 단점 |
| --- | --- | --- |
| **구성 요소 설정** | <ul><li>데이터 피드가 배달되기 전에 보고서 시간에 적용됩니다.</li><li>동일한 논리가 Analysis Workspace 및 데이터 피드 출력 모두에서 일관되게 적용됩니다.</li><li>계정의 제한된 파생 필드 중 하나를 사용하지 않습니다.</li><li>지속성 및 지표 중복 제거와 같은 일부 변환은 SQL에서 복제하기가 어렵고, 현재 파생된 필드에서는 지속성이 불가능합니다.</li></ul> | <ul><li>각 구성 요소가 지원하는 특정 설정 세트에만 사용할 수 있으며, 파생 필드를 사용하여 사용자 지정 논리를 작성하는 것만큼 유연하지는 않습니다.</li><li>설정이 데이터 피드 출력에 영향을 미치는지 여부는 몇 가지 설정에 대해 계속 확인되고 있습니다. 아래 표를 참조하십시오.</li></ul> |
| **파생 필드** | <ul><li>데이터 피드가 배달되기 전에 보고서 시간에 적용됩니다.</li><li>동일한 논리가 Analysis Workspace 및 데이터 피드 출력 모두에서 일관되게 적용됩니다.</li><li>체인 조건부 규칙과 같은 단일 구성 요소 설정보다 유연한 사용자 지정 로직을 지원합니다.</li><li>일부 변형, 특히 범위 설정에 따라 달라지거나 URL을 구문 분석하는 변형은 SQL에서 복제하기 어렵습니다.</li></ul> | <ul><li>데이터 피드 전달 성능에 영향을 줄 수 있는 처리 오버헤드를 추가합니다.<!--Under a future usage-based pricing model, this could also add cost.--></li><li>계정의 제한된 파생 필드 중 하나를 사용합니다. 구성 요소 설정이 동일한 작업을 수행할 수 있는 경우 대신 해당 작업을 선호합니다.</li></ul> |
| **SQL** | <ul><li>파생 필드에 적용되는 함수 및 연산자 제한에 의해 제한되지 않습니다.</li><li>는 데이터 피드 전달 성능에 영향을 주지 않습니다.</li></ul> | <ul><li>데이터 피드가 이미 전달된 후에 적용됩니다.</li><li>논리는 Analysis Workspace에 적용되지 않으므로 별도로 복제해야 합니다.</li><li>일부 변형, 특히 범위 설정에 따라 달라지거나, URL을 구문 분석하거나, 범위에서 중복 제거를 수행하거나 값을 유지하는 변형은 복제하기 어렵거나 비현실적입니다.</li></ul> |

{style="table-layout:auto"}

## 데이터 변환

다음 표에는 각 데이터 변환을 수행할 수 있는 방법(또는 방법), SQL에서 복제하는 것이 얼마나 어려운지, 사용할 방법을 보여 주는 특정 데이터 변환이 나와 있습니다. <!--A few transformations are still being confirmed with the engineering team and are marked as open questions — don't treat those as confirmed to affect data feed output until that's resolved.-->

| 변환 | 구성 요소 설정 | 파생 필드 | SQL의 어려움 | 최적 | 고려 사항 |
| --- | --- | --- | --- | --- | --- |
| **조건별 조건 논리 또는 필터 값 적용** | [포함/제외 값](/help/data-views/component-settings/include-exclude-values.md) | [다음의 경우](/help/data-views/derived-fields/derived-fields.md#casewhen) | 문자열에는 쉬움, 지표에는 보통에서 어려움 | 문자열에 대해 또는 지표에 대한 구성 요소 설정 | 세 가지 모두에서 비슷한 문자열 값의 경우 대개 선호도의 문제입니다. 지표의 경우 SQL에는 `COUNT`과(와) 결합된 `CASE` 문이 필요합니다. 이 문은 실행 가능하지만 더 복잡하므로 구성 요소 설정이 더 쉬운 경로입니다. |
| **성공 이벤트에 대한 특성 크레딧** | [속성](/help/data-views/component-settings/attribution.md) | 사용할 수 없음 | 적용할 수 없음 | 적용할 수 없음 | 데이터 피드의 지표에 적용되지 않습니다. SQL 또는 다른 방식으로 복제할 데이터 피드 동작이 없습니다. |
| **범위에 버킷 숫자 값** | [값 버킷팅](/help/data-views/component-settings/value-bucketing.md) | 사례 시기(수동) | 어려움 | 구성 요소 설정 | 구성 요소 설정(가장 쉬움)에서 파생 필드(보통, 수동 사례 사용)로, SQL(가장 복잡함)로 복잡성이 증가합니다. |
| **조회 스타일 매핑을 사용하여 값 분류** | 사용할 수 없음 | [분류](/help/data-views/derived-fields/derived-fields.md#classify) | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| **필드 값을 구분 기호와 결합** | 사용할 수 없음 | [연결](/help/data-views/derived-fields/derived-fields.md#concatenate) | 간편한 중재 | 둘 중 하나 | 자유 형식 테이블에 여러 차원 열을 추가하는 기능을 미러링합니다. 이 기능은 전체 테이블 내보내기로 제한됩니다. 파생 필드를 사용하면 데이터 피드에서 유사한 출력을 사용할 수 있습니다. |
| **필드의 데이터 형식 변환** | 사용할 수 없음 | [Typecast](/help/data-views/derived-fields/derived-fields.md#typecast) | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| **지표 발생 횟수(값과 인스턴스 비교)** | [비헤이비어](/help/data-views/component-settings/behavior.md) | 사용자 지정 수학 기반 해결 방법 | 간편한 중재 | 둘 중 하나 | 세 가지 접근 방식 모두 작동합니다. Customer Journey Analytics에서 기본적으로 이 작업을 수행할 수 있다면 그렇게 하지 않을 이유가 거의 없습니다. |
| **범위 내 값 중복 제거** | [지표 중복 제거](/help/data-views/component-settings/metric-deduplication.md) | [중복 제거](/help/data-views/derived-fields/derived-fields.md#dedup) | 어려움 | 구성 요소 설정 또는 파생 필드 | 범위 설정에 따라 다릅니다. [범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요. 구성 요소 설정과 파생 필드는 거의 동일하지만 제한된 파생 필드 중 하나를 사용하지 않으므로 구성 요소 설정을 선호합니다. |
| **세션 내에서 필드 깊이 확인** | 사용할 수 없음 | [깊이](/help/data-views/derived-fields/derived-fields.md#depth) | 어려움 | 파생 필드 | 세션을 범위로 사용하며, 구성할 수 없습니다. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> 세션이 피드 전달 경계에 걸쳐 있을 때 카운터가 작동하는 방식이 여전히 엔지니어링 상태에서 확인되고 있습니다. 범위 설정에 따라 다릅니다. [범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요. |
| **리터럴 값 찾기 및 바꾸기** | 사용할 수 없음 | [찾기 및 바꾸기](/help/data-views/derived-fields/derived-fields.md#find-and-replace) | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| **표시할 값 서식 지정** | [포맷](/help/data-views/component-settings/format.md) | 사용할 수 없음 | 어려움 | 구성 요소 설정 | 날짜-시간 서식이 데이터 피드 출력에 아직 반영되지 않았습니다. 현재 피드에 이 설정에 관계없이 표준 타임스탬프가 표시되지만, Adobe은 일반 가용성을 위해 이를 지원할 계획입니다. 지표의 숫자 형식(십진수, 통화, 퍼센트)이 데이터 피드 출력에 영향을 주는지 여부는 여전히 팀에서 확인 중입니다. |
| **요약 데이터 세트에서 차원 그룹화** | [요약 데이터 그룹](/help/data-views/component-settings/summary-data-group.md) | 사용할 수 없음 | 미결 질문 | 미결 질문 | 아직 팀과 논의되지 않았습니다. 확인될 때까지 데이터 피드 출력에 영향을 주지 마십시오. |
| **빈(&quot;값 없음&quot;) 필드 처리** | [값 옵션 없음](/help/data-views/component-settings/no-value-options.md) | 사용할 수 없음 | 미결 질문 | 미결 질문 | 빈 값이 null로 전송되는지 여부, &quot;값으로 처리&quot;가 기본 데이터를 변경하는지 여부 등 데이터 피드 출력에 영향을 미치는지 여부는 여전히 팀에서 검토 중입니다. |
| **조회 데이터 집합에서 값 조회** | 사용할 수 없음 | [조회](/help/data-views/derived-fields/derived-fields.md#lookup) | 간편한 중재 | 둘 중 하나 | 조회 테이블이 이미 있으면 SQL이 작동합니다. |
| **문자열의 소문자** | [비헤이비어](/help/data-views/component-settings/behavior.md) | [소문자](/help/data-views/derived-fields/derived-fields.md#lowercase) | 간편한 중재 | 구성 요소 설정 또는 파생 필드 | 둘 다 동일하지만 구성 요소 설정은 제한된 파생 필드 중 하나를 사용하지 않으므로 선호됩니다. |
| **여러 필드를 하나로 병합** | 사용할 수 없음 | [필드 병합](/help/data-views/derived-fields/derived-fields.md#merge) | 간편한 중재 | 둘 중 하나 | — |
| **URL을 해당 구성 요소로 구문 분석** | [하위 문자열](/help/data-views/component-settings/substring.md)(URL 구문 분석 메서드) | [URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#urlparse) | 어려움 | 구성 요소 설정 또는 파생 필드 | SQL에서 동일한 구성 요소를 추출하려면 사용자 지정 문자열 구문 분석이 필요합니다. <!-- Possible discrepancy: in the component settings meeting, Matt and Derek described all Substring methods, including URL parse, as roughly interchangeable across component setting, derived field, and SQL ("either one would work... maybe a preference"), which is a looser SQL-difficulty read than "Difficult." Flagged for Luke to reconcile; not changed without confirmation. --> |
| **숫자 필드에 대한 기본 계산을 수행합니다** | 사용할 수 없음 | [계산](/help/data-views/derived-fields/derived-fields.md#math) | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| **이벤트 간에 차원 값 유지** | [지속성](/help/data-views/component-settings/persistence.md) | 현재 사용할 수 없는 <!-- Derek: considering adding this to FDL and surfacing it in derived fields; not currently possible. --> | 어려움 | 구성 요소 설정 | SQL에서 이 논리를 복제하는 것보다 구성 요소 설정을 사용하는 것이 훨씬 쉽습니다. 범위 종속 파생 필드 함수와 같은 방식으로 전환 확인 날짜 범위와 상호 작용하는 것이 이미 확인되었습니다. [전환 확인 날짜 범위 이해](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range)를 참조하세요. |
| **정규 표현식을 사용하여 값 바꾸기** | [하위 문자열](/help/data-views/component-settings/substring.md)(Regex 메서드) | [정규식 바꾸기](/help/data-views/derived-fields/derived-fields.md#regex-replace) | 간편한 중재 | 둘 중 하나 | 세 가지 접근 방식은 모두 동일한 결과를 도출합니다. 이는 선호도의 문제입니다. |
| **세션에서 다음 또는 이전 값을 확인합니다** | 사용할 수 없음 | [다음 또는 이전](/help/data-views/derived-fields/derived-fields.md#next-previous) | 어려움 | 파생 필드 | 범위 설정에 따라 다릅니다. [범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요. |
| **두 날짜 사이의 차이점 반환** | 사용할 수 없음 | [날짜 계산](/help/data-views/derived-fields/derived-fields.md#datemath) | 어려움 | 파생 필드 | SQL에서 복제하는 것은 복잡합니다. 범위 설정에 따라 다릅니다. [범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요. |
| **이벤트, 프로필 또는 합계를 기준으로 지표 범위 지정** | [범위](/help/data-views/component-settings/scope.md) | 사용할 수 없음 | 미결 질문 | 미결 질문 | 아직 팀과 논의되지 않았습니다. 확인될 때까지 데이터 피드 출력에 영향을 주지 마십시오. |
| **구분된 값 분할** | [하위 문자열](/help/data-views/component-settings/substring.md)(구분 기호 또는 왼쪽/오른쪽 메서드에서) | [분할](/help/data-views/derived-fields/derived-fields.md#split) | 간편한 중재 | 둘 중 하나 | 세 가지 접근 방식은 모두 동일한 결과를 도출합니다. 이는 선호도의 문제입니다. |
| **범위 전체에 걸쳐 값 요약 또는 집계** | 사용할 수 없음 | [요약](/help/data-views/derived-fields/derived-fields.md#summarize) | 어려움 | 파생 필드 | 범위 설정에 따라 다릅니다. [범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요. |
| **문자열에서 문자 트리밍** | [하위 문자열](/help/data-views/component-settings/substring.md)(Trim 메서드) | [트리밍](/help/data-views/derived-fields/derived-fields.md#trim) | 간편한 중재 | 둘 중 하나 | 세 가지 접근 방식은 모두 동일한 결과를 도출합니다. 이는 선호도의 문제입니다. |

{style="table-layout:auto"}

### 범위 설정이 데이터 피드에 미치는 영향 {#scope-settings}

날짜 계산, 중복 제거, 다음 또는 이전 및 요약은 각각 이벤트, 세션 또는 개인의 [!UICONTROL **범위**] 설정에 따라 다릅니다(사용 가능한 옵션은 함수에 따라 다름). 깊이는 구성 가능한 범위 필드가 없지만 표준 이벤트 깊이 차원과 유사하게 기본적으로 세션에 연결되어 있습니다. 범위가 있는 모든 필드는 해당 범위 내의 모든 행에 동일한 값을 쓰고 해당 값은 전환 확인 날짜 범위 내의 데이터에 따라 다릅니다.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

[전환 확인 날짜 범위](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range)가 각 데이터 피드 배달과 함께 앞으로 이동하기 때문에 이미 발생한 이벤트의 경우에도 동일한 필드가 나중에 배달할 때 다른 값을 반환할 수 있습니다.

범위 크기에 따라 위험 증가: 개인 내역은 피드 실행 내에 자연 시간 경계가 없으므로 개인 범위는 세션 범위보다 더 많은 위험을 내포합니다.

## 파생 필드 함수 템플릿

[파생 필드 함수 템플릿](/help/data-views/derived-fields/derived-fields.md#templates)을 사용하면 마케팅 채널 구축, 봇 검색 또는 URL에서 UTM 매개 변수 추출과 같은 특정 사용 사례에 대한 파생 필드를 빠르게 만들 수 있습니다. 템플릿은 미리 작성된 규칙 체인으로 작성되므로 SQL에서 동일한 논리를 처음부터 재현하는 것보다 항상 하나를 사용하는 것이 좋습니다.

템플릿에 범위 설정에 의존하는 함수가 포함된 경우 템플릿에는 해당 함수의 범위 주의 사항이 상속됩니다. [범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요.
