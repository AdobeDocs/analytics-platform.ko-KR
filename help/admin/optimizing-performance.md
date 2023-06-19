---
description: CJA 및 작업 공간 성능 및 적용할 수 있는 최적화에 영향을 주는 요소
title: CJA 및 Analysis Workspace 성능 최적화
feature: FAQ
exl-id: ad00e476-6f19-462b-ba53-d72ddd949802
source-git-commit: 3adf4f4eaa8455b19248e4756f802367dc7cdbae
workflow-type: tm+mt
source-wordcount: '1950'
ht-degree: 76%

---

# CJA 최적화 및 [!UICONTROL Analysis Workspace] 성능

다양한 요소가 Analysis Workspace 내의 프로젝트 성과뿐만 아니라 전체 CJA 성과에 영향을 줄 수 있습니다. 작업 영역에서 다음과 같은 오류 메시지가 표시될 수 있습니다

`This query is too complex. Please review best practices for building Analysis Workspace queries.`

이 우수 사례에서는 이 오류를 일으킬 수 있는 요인과 보고서/프로젝트를 간소화하는 방법에 대해 설명합니다.

## 쿼리 요소 {#query}

다음은 전체 CJA 성능에 영향을 주는 가장 일반적인 쿼리 요소입니다.

| 요소 | 정의 | 영향을 주는 요소 | 최적화 |
| --- | --- | --- | --- |
| **자유 형식 행 및 열 수** | 모든 테이블의 행과 열을 곱하여 계산한 프로젝트의 총 자유 형식 테이블 셀 수입니다. 숨겨진 데이터 소스를 제외합니다. 지침은 4,000개입니다. |  | 테이블의 열 수를 가장 관련성이 높은 데이터 포인트로만 줄입니다. 표시된 행 수를 조정하거나 표 필터를 적용하거나 필터를 적용하여 테이블의 행 수를 줄입니다. |
| **사용된 구성 요소** | 프로젝트에서 사용되는 총 구성 요소 수입니다. 지침은 100개입니다. | 사용된 구성 요소 수는 성능에 직접적인 영향을 주지 않습니다. 그러나, 이러한 구성 요소의 복잡성에 따라 프로젝트의 성과가 달라집니다. 아래의 &quot;추가 요소&quot; 섹션에서 최적화를 참조하십시오. |
| **가장 긴 날짜 범위** | 이 요소에서는 프로젝트에 사용되는 가장 긴 날짜 범위를 표시합니다. 지침은 1년입니다. |  | 가능하면 필요 이상의 데이터를 가져오지 마십시오. 패널 달력의 범위를 분석 관련 날짜로 좁히거나 자유 형식 테이블에서 날짜 범위 구성 요소(자주색 구성 요소)를 사용합니다. 테이블에 사용된 날짜 범위는 패널 날짜 범위를 덮어씁니다. 예를 들어 지난 달, 지난 주 및 어제를 테이블 열에 추가하여 해당하는 특정 데이터 범위를 요청할 수 있습니다. Analysis Workspace에서 날짜 범위 작업에 대한 자세한 내용은 [이 비디오](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html?lang=ko-KR)에서 확인하십시오. <br><br>프로젝트에서 사용되는 연도별 비교 횟수도 최소화합니다. 연도별 비교가 계산되면 관심 월들 사이의 전체 13개월 데이터를 살펴봅니다. 패널 날짜 범위를 지난 13개월로 변경하는 것과 동일한 효과가 있습니다. |
| **필터 복잡성** | 복잡한 필터에는 프로젝트 성능에 대한 중요한 영향이 있을 수 있습니다. | 필터에 복잡성을 추가하는 요소(영향의 내림 순서로)에는 다음이 포함됩니다. <ul><li>연산자 - “포함”, “다음 중 하나 이상의 항목 포함”, “일치함”, “다음으로 시작” 또는 “다음으로 끝남” </li><li>특히 차원 제한(Within/After)이 사용되는 경우 순차적 필터링 </li><li>필터에서 사용되는 차원 내 고유한 차원 항목의 수(예: Page에 10개의 고유 항목이 있는 Page = &#39;A&#39;는 Page에 100000개의 고유 항목이 있는 Page = &#39;A&#39;보다 빠릅니다.) </li><li>사용된 다양한 차원의 수 (예: Page = &#39;Home&#39; 및 Page = &#39;Search results&#39;는 eVar 1 = &#39;red&#39; 및 eVar 2 = &#39;blue&#39;보다 빠릅니다.))</li><li>많은 OR 연산자 (AND 대신)</li><li>범위가 다양한 중첩 컨테이너(예: &quot;개인&quot; 내 &quot;세션&quot; 내의 &quot;이벤트&quot;)</li></ul> | 일부 복잡성 요소를 방지할 수 없으면 필터의 복잡성을 줄이는 기회를 찾습니다. 일반적으로 필터 기준을 더 특정적으로 만들수록 더 좋아집니다. 예:<ul><li>컨테이너를 사용하면 필터 맨 위에 있는 단일 컨테이너를 사용하는 것이 일련의 중첩 컨테이너보다 빠릅니다.</li><li>연산자의 경우 &quot;같음&quot;이 &quot;포함&quot;보다 빠르며 &quot;다음 중 1개 이상의 항목과 같음&quot;이 &quot;다음 중 1개 이상의 항목 포함&quot;보다 빠릅니다.</li><li>많은 기준을 사용하면 AND 연산자가 일련의 OR 연산자보다 빠릅니다.</li></ul> 많은 OR 구문을 하나의 &quot;다음 중 하나 이상의 항목과 같음&quot; 구문으로 줄일 수 있는 기회도 찾습니다.<br> |
| **시각화 복잡성** (필터, 지표, 필터) | 프로젝트에 기본적으로 추가된 시각화 유형 (예: 폴아웃 및 자유 형식 테이블)은 프로젝트 성능에 크게 영향을 주지 않습니다. 시각화의 복잡성으로 인해 처리 시간이 늘어납니다. | 시각화에 복잡성을 추가하는 요소는 다음과 같습니다.<ul><li>요청한 데이터 범위</li><li>적용된 필터 수(예: 자유 형식 테이블의 행으로 사용된 필터 수)</li><li>복잡한 필터 사용</li><li>[자유 형식 테이블의 정적 항목 행 또는 열](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)</li><li>자유 형식 테이블의 행에 적용된 필터</li><li>포함된 지표 수, 특히 필터를 사용하는 계산된 지표 수</li></ul> |
| **데이터 센터 용량** | 귀하와 다른 고객이 Adobe 데이터 센터 내에서 공유하는 보고 용량입니다. | 용량은 조직 및 데이터 센터 내의 다른 조직에서 수행한 동시 쿼리 수의 영향을 받습니다. | 귀하의 조직은 정해진 용량을 받을 자격이 있으며 시스템이 경부하 상태인 경우 Adobe는 귀하에게 부여된 허용량 이상으로 더 많은 용량을 귀하에게 이동시킵니다. |
| **동시 쿼리 수** | 조직에서 동시에 요청하는 쿼리 수입니다. 각 조직은 최소 5개의 동시 쿼리를 받을 수 있습니다. 보고서에 시간이 오래 걸리는 경우는 일반적으로 다른 보고서와 함께 큐에 있기 때문입니다. 즉, 조직에서 특정 데이터 보기에 대해 많은 동시 요청을 실행하려고 합니다. | 쿼리는 API 요청, 보고 UI(Analysis Workspace, Report Builder 등), 예약된 프로젝트, 예약된 경고 및 보고를 요청하는 동시 사용자로부터 비롯될 수 있습니다. | 데이터 보기에 대한 요청 및 일정을 하루 전체에 더 고르게 분산합니다. 또한 가능하면 사용량이 적은 시간으로 요청을 이동합니다. 월요일 아침, 화요일 아침 그리고 매월 1일이 가장 많이 보고되는 시간입니다. |
| **연결 크기** | 연결에 수집된 데이터의 양입니다. |  | CJA의 전반적인 환경을 개선하기 위해 수행할 수 있는 구현 개선 사항이 있는지 확인하려면 구현 팀이나 CJA 전문가와 상의하십시오. |
| **차원 설정의 복잡성** | 매우 복잡한 차원은 프로젝트 성능, 특히 복잡한 사용자 정의 필드를 기반으로 하는 차원 또는 지표에 중요한 영향을 미칠 수 있습니다. |  | 사용자 지정 필드의 수를 줄이거나 별도의 차원을 만듭니다. |
| **고유 값이 많은 Dimension** | 높은 카디널리티 차원이라고도 하는 이러한 차원은 보고 성능에 영향을 줄 수 있습니다. | 다음을 참조하십시오 [높은 카디널리티 차원](/help/components/dimensions/high-cardinality.md) | 다음을 참조하십시오 [높은 카디널리티 차원](/help/components/dimensions/high-cardinality.md) |

## Analysis Workspace의 [!UICONTROL 도움말] > [!UICONTROL 성능]

다양한 요소가 Analysis Workspace 내에 있는 프로젝트의 성능에 영향을 줄 수 있습니다. 최적의 방법으로 프로젝트를 계획 및 작성할 수 있도록 프로젝트 작성을 시작하기 전에 그러한 기여자가 무엇인지 알아두는 것이 중요합니다. 이 섹션에는 Analysis Workspace에서 최고의 성능을 보장하기 위해 수행할 수 있는 최적화와 성능에 영향을 주는 요소의 목록이 포함되어 있습니다.

**Analysis Workspace > [!UICONTROL 도움말] > [!UICONTROL 성능]**&#x200B;에서 네트워크, 브라우저, 프로젝트 요소 등 프로젝트의 성능에 영향을 주는 요소를 참조할 수 있습니다. 가장 정확한 결과를 위해 성능 페이지를 열기 전에 프로젝트를 모두 로드하도록 허용합니다.

* 현재 프로젝트 열에는 현재 프로젝트 및 사용자 환경의 결과가 표시됩니다.
* 지침 열에는 각 요소에 대한 Adobe에서 권장하는 각 요소의 임계값이 표시됩니다.

성능 내용을 **CSV로 다운로드**&#x200B;하여 Adobe 고객 지원 또는 내부 IT 팀과 쉽게 공유할 수도 있습니다.

>[!NOTE]
>
>변경 내용이 요소에 적용되므로 모달을 열 때마다 성능 페이지의 정보가 달라집니다. 또한 Adobe에서는 더 많은 데이터를 사용할 수 있는 대로 제공하는 지침을 계속 세분화할 예정입니다.

![](assets/performance-modal.png)

### 네트워크 요소

[!UICONTROL 도움말] > [!UICONTROL 성능] 네트워크 요소에 포함되는 항목:

| 요소 | 정의 | 영향을 주는 요소 | 최적화 |
| --- | --- | --- | --- |
| **Adobe에 연결** | 성능 페이지가 열릴 때 Adobe에서 10개의 테스트 호출을 보냅니다. 이는 Adobe로 보내는 호출이 성공하는 비율을 나타냅니다. | 로컬 네트워크 문제 또는 Adobe 문제가 이 요소에 영향을 줍니다. | 알려진 서비스 문제가 있는지 확인하려면 status.adobe.com을 점검합니다. 그런 다음 로컬 네트워크 연결을 확인합니다. |
| **인터넷 대역폭** | Google Chrome에서만 사용할 수 있습니다. 브라우저가 예상하는 현재 위치의 대역폭입니다. 지침은 2.0MB/s입니다. | 로컬 네트워크 연결이 이 요소에 영향을 줍니다. | 로컬 네트워크 연결을 확인합니다. |
| **인터넷 지연 시간** | 성능 페이지가 열릴 때 Adobe에서 10개의 테스트 호출을 보냅니다. 이는 각 요청이 Adobe로 이동하고 반환되는 데 평균적으로 걸리는 시간을 나타냅니다. 즉, 현재 위치와 Adobe 사이의 인터넷 속도 측정입니다. 지침은 1초 미만입니다. | 로컬 네트워크 문제, 열려 있는 많은 브라우저 탭 또는 Adobe 문제가 이 요소에 영향을 줍니다. | 알려진 서비스 문제가 있는지 확인하려면 status.adobe.com을 점검합니다. 그런 다음, 로컬 네트워크 연결을 확인하고 사용하지 않는 탭을 닫습니다. |

### 브라우저 요소

[!UICONTROL 도움말] > [!UICONTROL 성능] 브라우저 요소에 포함되는 항목:

| 요소 | 정의 | 영향을 주는 요소 | 최적화 |
| --- | --- | --- | --- |
| **연산 속도** | 컴퓨터에서 처리 테스트를 수행하는 속도입니다. 지침은 750ms 미만입니다. | 하드웨어는 물론, 동시 실행 프로그램도 이 요소에 영향을 줍니다. | 컴퓨터의 작업 관리자(PC) 또는 활동 상태 보기(Mac)를 열어 프로그램을 닫을 수 있는지 확인합니다. 그런 다음, 사용하지 않는 브라우저 탭 또는 기타 프로그램을 닫습니다. <br><br>이러한 작업이 도움이 되지 않는 경우 IT 팀에 하드웨어 세부 사항을 문의합니다. |
| **사용된 메모리** | Google Chrome에서만 사용할 수 있습니다. Google Chrome 브라우저의 모든 작업 영역 탭에서 총 4GB의 메모리를 공유합니다. 이는 현재 프로젝트에서 사용 중인 메모리 허용 비율을 나타냅니다. 지침은 작업 영역에서 메모리 오류 표시가 시작되는 지점인 3,500MB입니다. | 여러 탭에서 작업하거나 50,000개의 데이터 행을 다운로드하면 메모리 사용량이 증가합니다. | 메모리 오류가 발생하면 기타 작업 영역 탭을 닫거나 한 번에 50,000개 행 다운로드를 실행합니다. |
| **사용된 로컬 스토리지** | 브라우저에 사용할 수 있도록 컴퓨터에 로컬로 저장된 데이터입니다. 원본 (예: experience.adobe.com)마다 10MB가 허용됩니다. | Analysis Workspace에서는 자동 저장 (기존) 프로젝트, 사용자 설정 및 기능 플래그를 저장하는 등 여러 가지 기능에 로컬 저장소를 사용합니다. | Analysis Workspace 기능이 중단되지 않도록 experience.adobe.com 도메인의 로컬 저장소를 지웁니다. |
| **렌더링 속도** | FPS는 브라우저에서 화면에 페이지를 그리는 횟수인 초당 프레임을 의미합니다. 일반적으로 사람의 눈으로는 24 FPS를 관찰할 수 있습니다. FPS가 이보다 낮으면 작업 영역에서 렌더링 문제가 발생합니다. | FPS는 한 번에 많은 Workspace 프로젝트의 멀티태스킹과 보고 있는 프로젝트의 크기에 영향을 받습니다. 컴퓨터에서 실행 중인 스트리밍, 백그라운드 스캐너 등과 같은 기타 프로그램이 영향을 받을 수 있습니다. 하드웨어도 이 요소에 영향을 줍니다. | 컴퓨터의 작업 관리자(PC) 또는 활동 상태 보기(Mac)를 열어 프로그램을 닫을 수 있는지 확인합니다. 그런 다음, 사용하지 않는 브라우저 탭 또는 기타 프로그램을 닫습니다. <br><br>이러한 작업이 도움이 되지 않는 경우 IT 팀에 하드웨어 세부 사항을 문의합니다. |

### 프로젝트 요소

[!UICONTROL 도움말] > [!UICONTROL 성능] 프로젝트 요소에 포함되는 항목:

| 요소 | 정의 | 최적화 |
| --- | --- | --- |
| **쿼리 개수** | 프로젝트에 표시되는 데이터를 검색하도록 Adobe에 적용되는 총 쿼리 (요청) 개수입니다. 쿼리에는 테이블에 대한 등급 요청, 예외 항목 탐지, 스파크라인, 왼쪽 레일에 표시된 구성 요소 등이 포함됩니다. 축소된 패널 및 시각화를 제외합니다. 지침은 100개입니다. | 특정 목적 또는 관련자 그룹에 도움이 되는 여러 프로젝트로 데이터를 분할하여 프로젝트를 최대한 간소화합니다. 태그를 사용하여 프로젝트를 테마로 분류하고, 관련자들이 필요한 내용을 더 손쉽게 찾을 수 있도록 [직접 연결](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=ko-KR)을 사용하여 내부 목차를 만듭니다. |
| **확장된 패널 (총 패널 중)** | 프로젝트의 총 패널 수 중 확장된 패널 수입니다. 지침은 5개입니다. | 프로젝트를 단순화하는 단계를 수행한 후 로드 시 볼 필요가 없는 프로젝트의 패널을 축소합니다. 프로젝트를 열면 확장된 패널만 처리됩니다. 축소된 패널은 사용자가 확장할 때까지 처리되지 않습니다. |
| **확장된 시각화 (총 시각화 중)** | 숨겨진 데이터 소스를 포함하여 프로젝트의 총계 중 확장된 테이블 및 시각화의 수입니다. 지침은 15개입니다. | 프로젝트를 단순화하는 단계를 수행한 후 로드 시 볼 필요가 없는 프로젝트의 시각화를 축소합니다. 필요한 경우 보고서의 소비자에게 가장 중요한 비주얼을 우선순위화하고 지원 비주얼을 별도의 더욱 상세한 패널 또는 프로젝트로 분류합니다. |
| **자유 형식 셀 수** | 위의 &quot;쿼리 요소&quot; 표를 참조하십시오. |  |
| **사용된 구성 요소** | 위의 &quot;쿼리 요소&quot; 표를 참조하십시오. |  |
| **가장 긴 날짜 범위** | 위의 &quot;쿼리 요소&quot; 표를 참조하십시오. |  |