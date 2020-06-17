---
description: 'null'
title: Analysis Workspace 성능 최적화
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 98%

---


# Analysis Workspace 성능 최적화

>[!NOTE] Customer Journey Analytics의 Analysis Workspace 설명서를 보고 있습니다. 이 기능은 기존 Adobe Analytics의 [Analysis Workspace과 약간 다릅니다](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html). [추가 정보...](/help/getting-started/cja-aa.md)

특정 요소는 Analysis Workspace 내에 있는 프로젝트의 성능에 영향을 줄 수 있습니다. 최적의 방법으로 프로젝트를 계획 및 작성할 수 있도록 프로젝트 작성을 시작하기 전에 그러한 기여자가 무엇인지 알아두는 것이 중요합니다. 다음은 프로젝트 최적화에 대한 성과 및 우수 사례에 영향을 주는 요소 목록입니다. Analysis Workspace 성능은 Adobe의 최우선 순위 중 하나이며 매일 지속적으로 개선되고 있습니다.

## 세그먼트 로직의 복잡성

복잡한 세그먼트에는 프로젝트 성능에 대한 중요한 영향이 있을 수 있습니다. 세그먼트에 복잡성을 추가하는 요소(영향의 내림 순서로)에는 다음이 포함됩니다.

* 연산자 - &quot;포함&quot;, &quot;다음 중 1개 이상의 항목 포함&quot;, &quot;일치함&quot;, &quot;다음으로 시작&quot; 또는 &quot;다음으로 끝남&quot;
* 특히 차원 제한(Within/After)이 사용되는 경우 순차적 세분화
* 세그먼트에서 사용되는 차원 내 고유한 차원 항목의 수(예: Page에 10개의 고유 항목이 있는 Page = &#39;A&#39;는 Page에 100000개의 고유 항목이 있는 Page = &#39;A&#39;보다 빠릅니다.)
* 사용된 다양한 차원의 수(예: Page = &#39;Home&#39; 및 Page = &#39;Search results&#39;는 eVar 1 = &#39;red&#39; 및 eVar 2 = &#39;blue&#39;보다 빠릅니다.))
* 많은 OR 연산자(AND 대신)
* 범위가 다양한 중첩 컨테이너(예: &quot;방문자&quot; 내 &quot;방문&quot; 내의 &quot;히트&quot;)

**로직 복잡성에 대한 권장 사항**

일부 복잡성 요소를 방지할 수 없으면 세그먼트의 복잡성을 줄이는 기회에 대해 생각해보십시오. 일반적으로 세그먼트 기준을 더 특정적으로 만들수록 더 좋아집니다. 예:

* 컨테이너를 통해 세그먼트 상단에서 단일 컨테이너를 사용하는 것은 일련의 중첩 컨테이너보다 빠릅니다.
* 연산자의 경우 &quot;같음&quot;이 &quot;포함&quot;보다 빠르며 &quot;다음 중 1개 이상의 항목과 같음&quot;이 &quot;다음 중 1개 이상의 항목 포함&quot;보다 빠릅니다.
* 많은 기준을 사용하면 AND 연산자가 일련의 OR 연산자보다 빠릅니다. 또한 많은 OR 구문을 하나의 &quot;다음 중 1개 이상의 항목과 같음&quot; 구문으로 줄일 수 있는 기회를 찾으십시오.

또한 [분류](https://docs.adobe.com/content/help/ko-KR/analytics/components/classifications/c-classifications.html)를 사용하면 많은 값을 세그먼트를 생성할 수 있는 간결한 그룹으로 통합하는 데 도움이 될 수 있습니다. 분류 그룹에 대한 세그멘테이션을 사용하면 많은 OR 구문 또는 &quot;포함&quot; 기준을 포함하는 세그먼트에 대해 성능적인 이점이 있습니다.

## 요청한 데이터 범위

프로젝트 전체에서 요청한 데이터 범위는 Analysis Workspace 성능에 영향을 줍니다.

**데이터 범위에 대한 권장 사항**

가능하면 필요 이상의 데이터를 가져오지 마십시오.

날짜 범위(자주색 구성 요소)는 패널 날짜 범위를 재정의합니다. 따라서 다른 날짜 범위를 열(예: 지난 달, 지난 주 및 어제 열)로 사용하는 경우 패널 날짜 범위에서 열 날짜 범위를 모두 확장하지 않아도 됩니다. 자유 형식 테이블에서 사용된 날짜 범위가 이 패널을 재정의하므로 간단하게 어제로 설정할 수 있습니다. Analysis Workspace에서 날짜 범위 작업에 대한 자세한 내용은 [이 비디오](https://www.youtube.com/watch?v=ybmv6EBmhn0)에서 확인하십시오 .

비교하려는 특정 기간의 데이터를 가져오려면 [날짜 비교 선택 사항](/help/components/date-ranges/time-comparison.md)을 사용하십시오. 예를 들어, 최근 13개월간의 데이터로 패널을 설정하지 않고 작년 같은 달과 비교한 지난달의 데이터를 표시해야 하는 경우 기간 비교 선택 사항을 사용하여 전년 대비 성과를 표시하면 됩니다.

## 시각화 수

한 프로젝트에 포함된 그래프 시각화 수는 Analysis Workspace의 전체 응답성에 영향을 줍니다.

**시각화 개수에 대한 우수 사례**

프로젝트의 시각화 수를 줄입니다. Analysis Workspace는 추가한 각 비주얼에 대한 수많은 처리를 화면에 표시하지 않고 수행하므로, 필요한 경우 보고서 소비자에게 가장 중요한 시각화에 우선 순위를 두고 지원 비주얼을 별도의 세부 프로젝트로 구분합니다.

## 시각화의 복잡성(세그먼트, 지표, 필터)

프로젝트에 기본적으로 추가된 시각화 유형(예: 폴아웃 및 자유 형식 테이블)은 프로젝트 성능에 크게 영향을 주지 않습니다. 영향을 주는 것은 처리 시간에 추가되는 시각화의 복잡성입니다. 시각화에 복잡성을 추가하는 요소는 다음과 같습니다.

* 위에 언급된 대로 요청한 데이터 범위
* 적용된 세그먼트 수(예: 자유 형식 테이블의 행으로 사용된 세그먼트 수)
* 복잡한 세그먼트 사용
* 자유 형식 테이블의 정적 항목 행 또는 열
* 자유 형식 테이블의 행에 적용된 필터
* 포함된 지표 수, 특히 세그먼트를 사용하는 계산된 지표 수

**시각화 복잡성에 대한 우수 사례**

프로젝트가 원하는 대로 빠르게 로드되지 않은 경우, 가능하면 일부 세그먼트를 eVar 및 필터로 바꿔 보십시오.

비즈니스에 중요한 데이터 포인트에 대해 세그먼트와 계산된 지표를 계속해서 사용하는 경우, 이러한 데이터 포인트를 직접 캡처하도록 구현을 개선해 보십시오. Adobe Experience Platform Launch 및 Adobe의 처리 규칙과 같은 태그 관리자를 사용하면 구현을 빠르고 쉽게 변경할 수 있습니다. 복잡한 세그먼트를 간소화하는 방법에 대해 더 잘 이해하려면 위의 &#39;세그먼트 로직의 복잡성&#39;을 참조하십시오.

## 패널 수

패널 하나에 여러 개의 시각화가 포함될 수 있으므로, 패널 수가 Analysis Workspace의 전체 응답성에 영향을 줄 수도 있습니다.

**패널 개수에 대한 우수 사례**

프로젝트 하나에 모든 것을 추가하려고 하지 말고, 이해 당사자의 특정 목적이나 그룹을 지원하는 고유한 프로젝트를 만드십시오. 태그를 사용하여 프로젝트를 주요 테마로 구성하고 관련 프로젝트를 이해 당사자 그룹과 공유합니다.

더 많은 프로젝트 구성이 필요한 경우 프로젝트에 대한 [직접 연결](https://www.youtube.com/watch?v=6IOEewflG2U)을 선택할 수도 있습니다. 이해 당사자가 필요한 것을 쉽게 찾을 수 있도록 프로젝트의 내부 색인을 만드십시오.

작업 공간 하나에 많은 패널이 필요한 경우 저장 및 공유하기 전에 패널을 축소하십시오. 프로젝트가 로드되면 Analysis Workspace는 확장된 패널에 대한 내용만 로드합니다. 축소된 패널은 사용자가 확장할 때까지 로드되지 않습니다. 이 방법은 다음과 같은 두 가지 점에서 도움이 됩니다.

* 축소된 패널은 프로젝트의 전체 로드 시간을 줄여줍니다.
* 축소된 패널은 보고서 소비자를 위해 프로젝트를 논리적인 방식으로 구성하는 좋은 방법입니다.

## 보고서 세트 크기

보고서 세트 크기가 영향력이 큰 요인으로 보일 수 있지만, 실제로는 Adobe의 데이터 처리 방법으로 인해 프로젝트 성능에 미치는 영향은 미미합니다.

## Analysis Workspace를 동시에 액세스하는 사용자 수

사용자가 서로 다른 보고서 세트에 액세스하는 경우 Analysis Workspace나 특정 프로젝트에 동시에 액세스하는 사용자 수는 Analysis Workspace 성능에 상당한 영향을 주지 않습니다. 그러나 동시 사용자가 동일한 보고서 세트에 액세스하는 경우에는 성능에 영향을 주게 됩니다.

## Analysis Workspace의 일반 오류 메시지

Analysis Workspace와 상호 작용할 때 오류가 발생할 수 있습니다. 오류는 몇 가지 이유로 발생할 수 있으며 아래에 나열된 오류는 가장 일반적인 것입니다.

| 오류 메시지 | 왜 이 오류가 발생하는가? |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | 조직에서 특정 보고서 세트에 대해 너무 많은 동시 요청을 실행하려고 합니다. 이 오류에 기여하는 요소는 API 요청, 예약된 프로젝트, 예약된 보고서, 예약된 경고 및 보고 요청을 수행하는 동시 사용자입니다. 보고서 세트에 대한 요청 및 일정을 하루 전체에 더 고르게 분산하는 것이 좋습니다. |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe에서 해결해야 하는 문제가 발생했습니다. 고객 지원 요청을 통해 오류 코드를 제출하는 것이 좋습니다. |
| `The request is too complex.` | 보고 요청이 너무 커서 실행할 수 없습니다. 이 오류에 기여하는 요소는 요청의 크기로 인한 시간 초과, 세그먼트 또는 검색 필터에 일치하는 항목이 너무 많음, 포함된 지표가 너무 많음, 호환되지 않는 차원과 지표 조합 등입니다. 요청을 간소화하는 것이 좋습니다. |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | 검색 텍스트 기준을 좁히고 요청을 다시 시도하는 것이 좋습니다. |
| `This dimension does not currently support non-default attribution models.` | 테이블의 차원을 [기여도 분석 IQ](../attribution/overview.md)와 호환되는 차원으로 바꾸는 것이 좋습니다. |
| `Your request failed as a result of too many columns or pre-configured rows.` | 일부 열이나 행을 제거하거나 별도의 시각화로 분할하는 것이 좋습니다. |
