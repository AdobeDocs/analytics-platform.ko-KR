---
title: 데이터 피드에서 파생된 필드 사용
description: 데이터 피드에서 파생 필드를 사용하는 방법을 알아봅니다.
hide: true
feature: Components
source-git-commit: a9f53472d57a3a26004bd5ca583a43134bbdba7e
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# 데이터 피드에서 파생 필드 사용

{{release-limited-testing}}

[파생 필드](/help/data-views/derived-fields/derived-fields.md)를 사용하여 데이터 피드 데이터에 대한 데이터 변환을 수행할 수 있습니다.

많은 파생 필드 함수는 값 바꾸기, 필드 결합 또는 필드의 데이터 형식 변환과 같이 SQL을 사용하여 적용할 수 있는 변환을 수행하므로, 선택하는 방법은 경우에 따라 기본 설정의 문제가 됩니다.

## 파생 필드와 SQL 비교

다음 표에서는 파생 필드 또는 SQL 사용의 장점과 단점을 비교합니다.

| 메서드 | 장점 | 단점 |
| --- | --- | --- |
| **파생 필드** | <ul><li>파생 필드가 표준 차원 및 지표와 함께 데이터 피드 스키마의 구성 요소로 포함되므로 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다.</li><li>일부 변형, 특히 범위 설정에 따라 달라지거나 URL을 구문 분석하는 변형은 SQL에서 복제하기 어렵습니다.</li></ul> | 데이터 피드 전달 성능에 영향을 줄 수 있는 처리 오버헤드를 추가합니다.<!--Under a future usage-based pricing model, this could also add cost.--> |
| **SQL** | <ul><li>파생 필드에 적용되는 함수 및 연산자 제한에 의해 제한되지 않습니다.</li><li>는 데이터 피드 전달 성능에 영향을 주지 않습니다.</li></ul> | <ul><li>논리는 Analysis Workspace에 적용되지 않으므로 별도로 복제해야 합니다.</li><li>일부 변형, 특히 범위 설정에 따라 달라지거나 URL을 구문 분석하는 변형은 복제하기 어렵거나 비현실적입니다.</li></ul> |

{style="table-layout:auto"}

## 파생 필드 함수

다음 표에서는 각 파생 필드 함수, 파생 필드나 SQL에 가장 적합한지 여부 및 사용하기 전에 고려해야 할 사항에 대해 설명합니다.

| 파생 필드 함수 | SQL을 사용하여 복제하는 데 어려움 | 최적(파생 필드 또는 SQL) | 고려 사항 |
| --- | --- | --- | --- |
| [**사례**](/help/data-views/derived-fields/derived-fields.md#casewhen)<br/>&#x200B;하나 이상의 필드에서 조건을 기준으로 조건을 적용한 다음 일치하는 조건을 기준으로 출력 값을 설정합니다. | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. 이 기능은 마케팅 채널 분류와 같이 많은 규칙이 관련되어 있을 때 특히 유용합니다. |
| [**분류**](/help/data-views/derived-fields/derived-fields.md#classify)<br/>&#x200B;새 파생 필드의 해당 값으로 대체되는 값 집합을 정의합니다. | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| [**연결**](/help/data-views/derived-fields/derived-fields.md#concatenate)<br/>&#x200B;정의된 구분 기호(예: 페이지 이름 및 마케팅 채널)를 사용하여 필드 값을 새로운 파생된 단일 필드로 결합합니다. | 간편한 중재 | 둘 중 하나 | 자유 형식 테이블에 여러 차원 열을 추가하는 기능을 미러링합니다. 이 기능은 전체 테이블 내보내기로 제한됩니다. 파생 필드를 사용하면 데이터 피드에서 유사한 출력을 사용할 수 있습니다. |
| [**날짜 계산**](/help/data-views/derived-fields/derived-fields.md#datemath)<br/>&#x200B;이벤트, 세션 또는 개인의 범위를 사용하여 두 날짜 또는 날짜-시간 필드(예: 예약 날짜와 체크인 날짜 사이의 일 수) 간의 차이를 반환합니다. | 어려움 | 파생 필드 | SQL에서 복제하는 것은 복잡합니다. 이 함수는 범위 설정에 따라 다릅니다. 자세한 내용은 [함수의 범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요. |
| [**중복 제거**](/help/data-views/derived-fields/derived-fields.md#dedup)<br/>&#x200B;개인 또는 세션 범위를 사용하여 값을 여러 번 카운트하지 않도록 합니다(예: 예약 확인 ID 중복 제거). | 어려움 | 파생 필드 | 이 함수는 범위 설정에 따라 다릅니다. 자세한 내용은 [함수의 범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요. |
| [**깊이**](/help/data-views/derived-fields/derived-fields.md#depth)<br/>&#x200B;표준 이벤트 깊이 차원(예: 내부 검색 깊이)과 유사한 필드의 깊이를 반환합니다. | 어려움 | 파생 필드 | 세션을 범위로 사용하며, 구성할 수 없습니다. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> 세션이 피드 전달 경계에 걸쳐 있을 때 카운터가 작동하는 방식이 여전히 엔지니어링 상태에서 확인되고 있습니다. 이 함수는 범위 설정에 따라 다릅니다. 자세한 내용은 [함수의 범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요. |
| [**찾기 및 바꾸기**](/help/data-views/derived-fields/derived-fields.md#find-and-replace)<br/>&#x200B;선택한 필드에서 모든 값을 찾아 다른 값으로 바꿉니다. | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| [**조회**](/help/data-views/derived-fields/derived-fields.md#lookup)<br/>&#x200B;일치하는 키를 사용하여 조회 데이터 집합에서 값을 검색하고 새 파생 필드에 반환합니다. | 간편한 중재 | 둘 중 하나 | 조회 테이블이 이미 있으면 SQL이 작동합니다. |
| [**소문자**](/help/data-views/derived-fields/derived-fields.md#lowercase)<br/>&#x200B;필드의 값을 소문자로 변환합니다. | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| [**계산**](/help/data-views/derived-fields/derived-fields.md#math)<br/>&#x200B;기본 수학 연산자(더하기, 빼기, 곱하기, 나누기 또는 거듭제곱하기)를 적중 단위로 평가되는 숫자 필드에 적용합니다. | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| [**필드 병합**](/help/data-views/derived-fields/derived-fields.md#merge)<br/>&#x200B;두 개 이상의 필드 중 첫 번째 필드에 값이 있는지 확인하고, 값이 없으면 다음 필드를 사용하는 등의 작업을 수행합니다. | 간편한 중재 | 둘 중 하나 | 없음 |
| [**다음 또는 이전**](/help/data-views/derived-fields/derived-fields.md#next-previous)<br/>&#x200B;사용자 또는 세션 범위를 사용하여 방문 또는 이벤트 테이블 필드의 다음 또는 이전 값을 확인합니다. | 어려움 | 파생 필드 | 이 함수는 범위 설정에 따라 다릅니다. 자세한 내용은 [함수의 범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요. |
| [**정규 표현식**](/help/data-views/derived-fields/derived-fields.md#regex-replace)<br/>&#x200B;정규 표현식을 사용하여 필드의 값을 바꿉니다. | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| [**분할**](/help/data-views/derived-fields/derived-fields.md#split)<br/>&#x200B;필드의 값을 새로운 파생 필드로 분할합니다(예: 구분된 목록을 배열로 변환). | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| [**요약**](/help/data-views/derived-fields/derived-fields.md#summarize)<br/>&#x200B;집계 함수(예: 합계, 개수 또는 가장 일반적인 함수)를 이벤트, 세션 또는 개인 범위가 있는 필드에 적용합니다. | 어려움 | 파생 필드 | 이 함수는 범위 설정에 따라 다릅니다. 자세한 내용은 [함수의 범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요. |
| [**트리밍**](/help/data-views/derived-fields/derived-fields.md#trim)<br/>&#x200B;필드 값의 시작 또는 끝에서 공백, 특수 문자 또는 문자 집합을 트리밍합니다. | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| [**Typecast**](/help/data-views/derived-fields/derived-fields.md#typecast)<br/>&#x200B;추가적인 변환에 사용할 수 있도록 필드의 데이터 형식을 변경합니다. | 간편한 중재 | 둘 중 하나 | SQL에서 재현할 수 있지만 파생된 필드를 사용하면 Analysis Workspace 및 데이터 피드 출력 모두에서 동일한 논리가 일관되게 적용됩니다. |
| [**URL 구문 분석**](/help/data-views/derived-fields/derived-fields.md#urlparse)<br/>&#x200B;프로토콜, 호스트, 경로, 쿼리 문자열 매개 변수 또는 해시 값을 포함하여 URL의 일부를 구문 분석합니다. | 어려움 | 파생 필드 | SQL에서 동일한 구성 요소를 추출하려면 사용자 지정 문자열 구문 분석이 필요합니다. |

{style="table-layout:auto"}

### 함수의 범위 설정이 데이터 피드에 미치는 영향 {#scope-settings}

[!UICONTROL **날짜 계산**], [!UICONTROL **중복 제거**], [!UICONTROL **다음 또는 이전**] 및 [!UICONTROL **요약**]&#x200B;은(는) 이벤트, 세션 또는 개인의 [!UICONTROL **범위**] 설정에 따라 다릅니다(사용 가능한 옵션은 함수에 따라 다름). [!UICONTROL **Depth**]&#x200B;에는 구성 가능한 범위 필드가 없지만 기본적으로 세션에 연결되어 있습니다. 표준 이벤트 깊이 차원과 비슷합니다. 범위가 있는 모든 필드는 해당 범위 내의 모든 행에 동일한 값을 쓰고 해당 값은 전환 확인 날짜 범위 내의 데이터에 따라 다릅니다.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

전환 확인 날짜 범위는 각 데이터 피드 배달과 함께 앞으로 이동하므로 이미 발생한 이벤트에 대해서도 나중에 배달할 때 동일한 필드가 다른 값을 반환할 수 있습니다.

범위 크기에 따라 위험 증가: 개인 내역은 피드 실행 내에 자연 시간 경계가 없으므로 개인 범위는 세션 범위보다 더 많은 위험을 내포합니다.

## 파생 필드 함수 템플릿

[파생 필드 함수 템플릿](/help/data-views/derived-fields/derived-fields.md#templates)을 사용하면 마케팅 채널 구축, 봇 검색 또는 URL에서 UTM 매개 변수 추출과 같은 특정 사용 사례에 대한 파생 필드를 빠르게 만들 수 있습니다. 템플릿은 미리 작성된 규칙 체인으로 작성되므로 SQL에서 동일한 논리를 처음부터 재현하는 것보다 항상 하나를 사용하는 것이 좋습니다.

템플릿에 범위 설정에 의존하는 함수가 포함된 경우 템플릿에는 해당 함수의 범위 주의 사항이 상속됩니다. [함수의 범위 설정이 데이터 피드에 미치는 영향](#scope-settings)을 참조하세요.

