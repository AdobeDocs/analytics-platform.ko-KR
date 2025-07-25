---
description: Analysis Workspace 성능과 적용할 수 있는 최적화에 영향을 주는 요소에서 insight을 얻을 수 있습니다
title: Analysis Workspace 성능 최적화
feature: Workspace Basics
role: User, Admin
exl-id: 226afef7-00da-4ac2-be4e-e19995621c61
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '2469'
ht-degree: 42%

---

# Analysis Workspace 성능 최적화

Analysis Workspace 내의 프로젝트 성능에 영향을 주는 요소는 다양합니다.  이러한 요소를 이해하려면 최적의 방법으로 프로젝트를 계획 및 빌드하는 데 도움이 됩니다.

insight을 Analysis Workspace의 성능으로 전환하려면 다음을 수행하십시오.

1. **[!UICONTROL 도움말] > [!UICONTROL 성능]**&#x200B;을 선택합니다.

   네트워크, 브라우저 및 프로젝트 요소를 포함하여 프로젝트 성능에 영향을 주는 요소를 표시하는 양식 대화 상자를 볼 수 있습니다. 가장 정확한 결과를 얻으려면 먼저 프로젝트를 로드할 수 있도록 하십시오.

   * **[!UICONTROL 현재 프로젝트]** 열에는 현재 프로젝트 및 사용자 환경에 대한 결과가 표시됩니다.
   * **[!UICONTROL 지침]** 열에는 각 요소에 대한 Adobe의 권장 임계값이 표시됩니다.

1. **[!UICONTROL CSV로 다운로드]**&#x200B;를 선택하여 성과 보고서를 다운로드하면 내부 조직 또는 Adobe 지원 팀과 보고서를 공유할 수 있습니다.

>[!NOTE]
>
>변경 내용이 요소에 적용되므로 모달을 열 때마다 성능 페이지의 정보가 달라집니다. 또한 Adobe에서는 더 많은 데이터를 사용할 수 있게 됨에 따라 제공되는 지침을 계속 세분화하고 있습니다.

![](assets/cja-performance.png)

## 네트워크 요소

네트워크 요인은 다음과 같습니다.

| 요소 | 정의 | 영향을 주는 요소 | 최적화 |
| --- | --- | --- | --- |
| Adobe에 연결 | 성능 페이지가 열릴 때 Adobe에서 10개의 테스트 호출을 보냅니다. 이러한 호출은 성공한 Adobe 호출의 비율을 나타냅니다. | 로컬 네트워크 문제 또는 Adobe 문제가 이 요소에 영향을 줍니다. | 알려진 서비스 문제가 있는지 확인하려면 status.adobe.com을 점검합니다. 그런 다음 로컬 네트워크 연결을 확인합니다. |
| 인터넷 대역폭 | Google Chrome에서만 사용할 수 있습니다. 브라우저에서 예상하는 현재 위치의 대역폭입니다. 지침은 2.0MB/s입니다. | 로컬 네트워크 연결이 이 요소에 영향을 줍니다. | 로컬 네트워크 연결을 확인합니다. |
| 인터넷 지연 시간 | 성능 페이지가 열릴 때 Adobe에서 10개의 테스트 호출을 보냅니다. 이러한 호출은 요청이 Adobe에 도달하여 돌아오는 데 평균적으로 걸리는 시간을 나타냅니다. 즉, 현재 위치와 Adobe 사이의 인터넷 속도 측정입니다. 지침은 1초 미만입니다. | 로컬 네트워크 문제, 열려 있는 많은 브라우저 탭 또는 Adobe 문제가 이 요소에 영향을 줍니다. | 알려진 서비스 문제가 있는지 확인하려면 status.adobe.com을 점검합니다. 그런 다음, 로컬 네트워크 연결을 확인하고 사용하지 않는 탭을 닫습니다. |

## 브라우저 요소

브라우저 요소는 다음과 같습니다.

| 요소 | 정의 | 영향을 주는 요소 | 최적화 |
| --- | --- | --- | --- |
| 연산 속도 | 컴퓨터에서 처리 테스트를 수행하는 속도입니다. 지침은 750밀리초 미만입니다. | 하드웨어는 물론 동시 실행 프로그램도 이 요소에 영향을 줍니다. | 컴퓨터의 작업 관리자(PC) 또는 활동 상태 보기(Mac)를 열어 프로그램을 닫을 수 있는지 결정합니다. 그런 다음, 사용하지 않는 브라우저 탭 또는 기타 프로그램을 닫습니다. <br><br>이러한 작업이 도움이 되지 않는 경우 IT 팀에 하드웨어 세부 사항을 문의합니다. |
| 사용된 메모리 | Google Chrome에서만 사용할 수 있습니다. Google Chrome 브라우저의 모든 작업 영역 탭에서 총 4GB의 메모리를 공유합니다. 사용된 이 메모리는 현재 프로젝트에서 사용한 메모리 허용 비율을 나타냅니다. 지침은 Workspace에서 메모리 오류 표시가 시작되는 지점인 3,500MB입니다. | 여러 탭에서 작업하거나 50000 데이터 행을 다운로드하면 메모리 사용량이 증가합니다. | 메모리 오류가 발생하면 기타 작업 영역 탭을 닫거나 한 번에 50,000개 행 다운로드를 실행합니다. |
| 사용된 로컬 스토리지 | 브라우저에서 사용할 수 있도록 컴퓨터에 로컬로 저장된 데이터입니다. 원본(예: experience.adobe.com)마다 10MB가 허용됩니다. | Analysis Workspace에서는 자동 저장(기존) 프로젝트, 사용자 설정 및 기능 플래그를 저장하는 등 여러 가지 기능에 로컬 저장소를 사용합니다. | Analysis Workspace 기능이 중단되지 않도록 experience.adobe.com 도메인의 로컬 저장소를 지웁니다. |
| 렌더링 속도 | FPS는 브라우저에서 화면에 페이지를 그리는 횟수인 초당 프레임을 의미합니다. 일반적으로 사람의 눈으로는 24 FPS를 관찰할 수 있습니다. FPS가 24 FPS보다 낮으면 Workspace에서 렌더링 문제가 발생합니다. | FPS는 한 번에 많은 Workspace 프로젝트의 멀티태스킹과 보고 있는 프로젝트의 크기에 영향을 받습니다. 컴퓨터에서 실행 중인 스트리밍, 백그라운드 스캐너 등과 같은 기타 프로그램이 영향을 받을 수 있습니다. 하드웨어도 이 요소에 영향을 줍니다. | 컴퓨터의 작업 관리자(PC) 또는 활동 상태 보기(Mac)를 열어 프로그램을 닫을 수 있는지 결정합니다. 그런 다음, 사용하지 않는 브라우저 탭 또는 기타 프로그램을 닫습니다. <br><br>이러한 작업이 도움이 되지 않는 경우 IT 팀에 하드웨어 세부 사항을 문의합니다. |

## 프로젝트 요소

프로젝트 요소에는 다음이 포함됩니다.

| 요소 | 정의 | 최적화 |
| --- | --- | --- |
| 요청 수 | 프로젝트에 표시되는 데이터를 검색하기 위해 Adobe에 대해 수행된 총 요청 수입니다. 쿼리에는 테이블에 대한 등급 요청, 예외 항목 탐지, 스파크라인, 왼쪽 레일에 표시된 구성 요소 등이 포함됩니다. 이 숫자는 축소된 패널 및 시각화를 제외합니다. 지침은 100개입니다. | 특정 목적 또는 관련자 그룹에 도움이 되는 여러 프로젝트로 데이터를 분할하여 프로젝트를 최대한 간소화합니다. 태그를 사용하여 프로젝트를 테마로 분류하고, 관련자들이 필요한 내용을 더 손쉽게 찾을 수 있도록 [직접 연결](https://experienceleague.adobe.com/ko/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links)을 사용하여 내부 목차를 만듭니다. |
| 확장된 패널(총 패널 중) | 프로젝트의 총 패널 수 중 확장된 패널 수입니다. 지침은 5개입니다. | 프로젝트를 단순화하는 단계를 수행한 후 로드 시 볼 필요가 없는 프로젝트의 패널을 축소합니다. 프로젝트를 열면 확장된 패널만 처리됩니다. 축소된 패널은 사용자가 확장할 때까지 처리되지 않습니다. |
| 확장된 시각화(총 시각화 중) | 숨겨진 데이터 소스를 포함하여 프로젝트의 총계 중 확장된 테이블 및 시각화의 수입니다. 지침은 15개입니다. | 프로젝트를 단순화하는 단계를 수행한 후 로드 시 볼 필요가 없는 프로젝트의 시각화를 축소합니다. 필요한 경우 보고서의 소비자에게 가장 중요한 비주얼을 우선순위화하고 지원 비주얼을 별도의 더욱 상세한 패널 또는 프로젝트로 분류합니다. |
| 자유 형식 셀 개수 | 모든 테이블의 행과 열을 곱하여 계산한 프로젝트의 총 자유 형식 테이블 셀 수입니다. 이 숫자는 숨겨진 데이터 소스를 제외합니다. 지침은 4,000개입니다. | 테이블의 열 수를 가장 관련성이 높은 데이터 포인트로만 줄입니다. 표시된 행 수를 조정하거나 테이블 필터를 적용하거나 세그먼트를 적용하여 테이블의 행 수를 줄입니다. |
| 사용 가능한 구성 요소 | 프로젝트의 모든 보고서 세트에 걸쳐 프로젝트의 왼쪽 레일에서 검색된 총 구성 요소 수입니다. 이 숫자는 왼쪽 레일이 로드되는 속도와 검색 결과가 반환되는 속도에 영향을 줍니다. 지침은 2,000개입니다. | 구성 요소 세트가 더욱 맞춤화되는 선별된 가상 보고서 세트를 만드는 방법은 제품 관리자에게 문의하십시오. |
| 사용된 구성 요소 | 프로젝트에서 사용되는 총 구성 요소 수입니다. 지침은 100개입니다. | 사용된 구성 요소 수는 성능에 직접적인 영향을 주지 않습니다. 그러나 이러한 구성 요소의 복잡성은 프로젝트 성능에 영향을 줍니다. 아래의 A[추가 요소](#additional-factors) 섹션에서 최적화를 참조하십시오. |
| 가장 긴 날짜 범위 | 이 요소에는 프로젝트에서 사용되는 가장 긴 날짜 범위가 표시됩니다. 지침은 1년입니다. | 가능하면 필요 이상의 데이터를 가져오지 마십시오. 패널 달력의 범위를 분석 관련 날짜로 좁힙니다. 또는 자유 형식 테이블에서 날짜 범위 구성 요소 (자주색 구성 요소)를 사용합니다. 테이블에 사용된 날짜 범위는 패널 날짜 범위를 덮어씁니다. 예를 들어 지난 달, 지난 주 및 어제를 테이블 열에 추가하여 해당하는 특정 데이터 범위를 요청할 수 있습니다. Analysis Workspace에서 날짜 범위 작업에 대한 자세한 내용은 [이 비디오](https://experienceleague.adobe.com/ko/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-date-ranges-and-comparisons-in-analysis-workspace)에서 확인하십시오. <br><br>프로젝트에서 사용되는 연도별 비교 횟수도 최소화합니다. 연도별 비교가 계산되면 비교는 관심 월 사이의 전체 13개월 데이터를 살펴봅니다. 이 비교는 패널 날짜 범위를 지난 13개월로 변경하는 것과 동일한 영향을 줍니다. |

## 요청 요소

요청 요소

다음 다이어그램과 용어를 사용하여 요청이 처리되는 방식과 처리 시간에 영향을 주는 다양한 요인에 대해 알아보십시오.

>[!NOTE]
>
>이러한 요소에 대한 권장 지침은 보고 요청에 대한 미디어의 복잡성 점수를 기반으로 합니다.


### 요청 처리 다이어그램

![요청 처리](assets/request-processing.png)

### 처리 조건 요청

| 요소 | 정의 | 최적화 |
| --- | --- | --- |
| [!UICONTROL **평균 요청 시간**] | 요청이 시작되는 시점부터 완료되는 시점까지 필요한 시간. 지침은 15초입니다. <p>위의 [요청 처리](#request-processing-diagram) 다이어그램에서 요청 시간은 **Analysis Workspace 요청이 시작됨**&#x200B;부터 **Analysis Workspace 요청 완료**&#x200B;까지의 전체 프로세스를 나타냅니다.</p> |  |
| [!UICONTROL **가장 긴 요청 시간**] | 요청이 시작되는 시점부터 완료되는 시점까지 필요한 시간. <p>위의 [요청 처리](#request-processing-diagram) 다이어그램에서 요청 시간은 **Analysis Workspace 요청이 시작됨**&#x200B;부터 **Analysis Workspace 요청 완료**&#x200B;까지의 전체 프로세스를 나타냅니다.</p> |  |
| [!UICONTROL **평균 조회 시간**] | Analysis Workspace은 모든 세그먼트에서 사용되는 문자열에 대한 해시만 저장하기 때문에 프로젝트를 처리할 때마다 해시를 적절한 값과 일치시키기 위해 **조회**&#x200B;가 수행됩니다. 지침은 2초 미만입니다.<p>이러한 조회는 해시와 잠재적으로 일치할 수 있는 값의 수에 따라 리소스를 많이 사용하는 프로세스일 수 있습니다. </p><p>위의 [요청 처리](#request-processing-diagram) 다이어그램에서 조회 시간은 **조회** 단계(**요청 엔진 처리** 단계 시)에 표시됩니다.</p> | 여기에서 요청이 느려지는 경우는 프로젝트에 문자열 세그먼트가 너무 많거나 일치하는 항목이 너무 많은 일반 값을 가진 문자열 때문일 수 있습니다. |
| [!UICONTROL **평균 큐 시간**] | 요청이 처리되기 전에 대기열에서 대기하는 총 시간입니다. 지침은 5초입니다.<p>위의 [요청 처리](#request-processing-diagram) 다이어그램에서 큐 시간은 **요청 엔진 큐** 단계 및 **서버 큐** 단계에 표시됩니다.</p> | 여기에서 요청이 느려지는 경우는 조직에서 동시에 실행되는 요청이 너무 많기 때문일 수 있습니다. 사용량이 적은 시간에 요청을 실행해 보십시오. |
| [!UICONTROL **평균 서버 처리 시간**] | 요청을 처리하는 데 소요되는 평균 시간입니다.<p>위의 [요청 처리](#request-processing-diagram) 다이어그램에서 평균 서버 처리 시간은 **서버 큐** 단계 및 **서버 처리** 단계에 표시됩니다. 지침은 10초입니다 | 여기에서 요청이 느려지는 경우 프로젝트에 지나치게 긴 날짜 범위나 복잡한 시각화가 있을 수 있습니다. 프로젝트 날짜 범위를 줄여 처리 시간을 줄여 보십시오. |
| [!UICONTROL **복잡성**] | 모든 요청이 동일한 처리 시간을 요구하는 것은 아닙니다. 요청 복잡성은 요청을 처리하는 데 필요한 시간에 대한 일반적인 아이디어를 제공하는 데 도움이 될 수 있습니다. 지침은 Medium 이하입니다. <p>가능한 값은 다음과 같습니다.</p> <ul><li>[!UICONTROL **낮음**]</li><li>[!UICONTROL **보통**]</li><li>[!UICONTROL **높음**]</li></ul>이 값은 다음 열의 값에 영향을 받습니다.<ul><li>[!UICONTROL **월 경계**]</li><li>[!UICONTROL **열**]</li><li>[!UICONTROL **세그먼트**]</li></ul> |  |
| [!UICONTROL **월 경계**] | 요청에 포함되는 월 수. 더 많은 월 경계는 요청의 복잡성을 가중시킵니다. 지침은 6개 이하입니다. | 여기에서 요청이 느려지는 경우는 프로젝트의 월 경계가 너무 크기 때문일 수 있습니다. 개월 수를 줄여 보세요. |
| [!UICONTROL **열**] | 요청에 포함된 지수와 분류 수. 열이 많으면 요청의 복잡성이 증가합니다. 지침은 10개 이하입니다. | 여기에서 요청이 느려지는 경우 프로젝트에 열이 너무 많기 때문일 수 있습니다. 열의 수를 줄여 보십시오. |
| [!UICONTROL **세그먼트**] | 요청에 적용된 세그먼트 수. 세그먼트가 많으면 요청의 복잡성이 가중됩니다. 지침은 5개 이하입니다. | 여기에서 요청이 느려지는 경우 프로젝트에 세그먼트가 너무 많기 때문일 수 있습니다. 세그먼트 수를 줄여 보십시오. |

## 추가 요소

도움말 > 성능에 포함되지 않은 추가 요소는 다음과 같습니다.

| 요소 | 정의 | 영향을 주는 요소 | 최적화 |
| --- | --- | --- | --- |
| 세그먼트 복잡도 | 복잡한 세그먼트에는 프로젝트 성능에 대한 중요한 영향이 있을 수 있습니다. | 세그먼트에 복잡성을 추가하는 요소(영향의 내림 순서로)에는 다음이 포함됩니다. <ul><li>**[!UICONTROL 포함]**, **[!UICONTROL 다음 중 하나 이상의 항목 포함]**, **[!UICONTROL 일치]**, **[!UICONTROL 다음으로 시작]** 또는 **[!UICONTROL 다음으로 끝남]**/ </li><li>특히 차원 제한(Within/After)이 사용되는 경우 순차적 세분화 </li><li>세그먼트에서 사용되는 차원 내 고유한 차원 항목의 수 (예: Page에 10개의 고유 항목이 있는 Page = &#39;A&#39;는 Page에 100000개의 고유 항목이 있는 Page = &#39;A&#39;보다 빠릅니다.) </li><li>사용되는 다양한 차원의 수 (예: Page = &#39;Home&#39; 및 Page = &#39;Search results&#39;는 eVar 1 = &#39;red&#39; 및 eVar 2 = &#39;blue&#39;보다 빠릅니다.)</li><li>많은 OR 연산자(AND 대신)</li><li>범위가 다양한 중첩 컨테이너(예: 방문자 내부 방문의 히트)</li></ul> | 일부 복잡성 요소를 방지할 수 없으면 세그먼트의 복잡성을 줄이는 기회를 찾습니다. 일반적으로 세그먼트 기준을 더 특정적으로 만들수록 더 좋아집니다. 예:<ul><li>컨테이너를 사용하면 일련의 중첩 컨테이너보다 세그먼트 맨 위에서 단일 컨테이너를 사용하는 것이 빠릅니다.</li><li>연산자의 경우 **[!UICONTROL equals]**&#x200B;이(가) **[!UICONTROL contains]**&#x200B;보다 빠르며 **[!UICONTROL equals]**&#x200B;이(가) **[!UICONTROL contains any of]**&#x200B;보다 빠릅니다.</li><li>많은 기준을 사용하면 AND 연산자가 일련의 OR 연산자보다 빠릅니다.</li></ul> 많은 OR 구문을 하나의 **[!UICONTROL 다음 중 하나 이상의]** 문으로 줄일 수 있는 기회를 찾으십시오. |
| 시각화 복잡성(세그먼트, 지표, 필터) | 시각화 유형(예: 폴아웃과 자유 형식 테이블)은 프로젝트 성능에 크게 영향을 주지 않습니다. 시각화의 복잡성으로 인해 처리 시간이 늘어납니다. | 시각화에 복잡성을 추가하는 요소는 다음과 같습니다.<ul><li>요청한 데이터 범위</li><li>적용된 세그먼트 수(예: 자유 형식 테이블의 행으로 사용된 세그먼트 수)</li><li>복잡한 세그먼트 사용</li><li>[자유 형식 테이블의 정적 항목 행 또는 열](https://experienceleague.adobe.com/ko/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows)</li><li>자유 형식 테이블의 행에 적용된 필터</li><li>포함된 지표 수, 특히 세그먼트를 사용하는 계산된 지표 수</li></ul> | 프로젝트가 원하는 대로 빠르게 로드되지 않은 경우, 가능하면 일부 세그먼트를 eVar 및 필터로 바꿔 보십시오.<br><br>비즈니스에 중요한 데이터 포인트에 대해 세그먼트와 계산된 지표를 계속해서 사용하는 경우, 이러한 데이터 포인트를 직접 캡처하도록 구현을 개선해 보십시오. Adobe Experience Platform 및 Adobe의 처리 규칙에 태그를 사용하면 구현을 빠르게 변경하고 쉽게 수행할 수 있습니다. |
| 보고서 세트 크기 | 보고서 세트에 수집된 데이터의 양입니다. | - | Adobe Analytics의 전반적인 환경을 개선하기 위해 수행할 수 있는 구현 개선 사항이 있는지 확인하려면 구현 팀이나 Adobe 전문가와 상의하십시오. |
| 동시 쿼리 | 조직에서 Adobe에 동시에 요청하는 쿼리 수입니다. 각 조직은 최소 5개의 동시 쿼리를 받을 수 있습니다. | 보고서가 오래 걸리는 경우 다른 보고서와 함께 큐에 있으므로 조직에서 특정 보고서 세트에 대해 많은 동시 요청을 실행하려고 합니다. 쿼리는 API 요청, 보고 UI(Analysis Workspace, Report Builder), 예약된 프로젝트, 예약된 보고서, 예약된 경고 및 보고 요청을 하는 동시 사용자로부터 비롯될 수 있습니다. | 보고서 세트에 대한 요청과 일정을 하루 전체에 더 고르게 분산시킵니다. 또한 가능하면 사용량이 적은 시간으로 요청을 이동합니다. 월요일 아침, 화요일 아침 그리고 매월 1일이 가장 많이 보고되는 시간입니다. |

## Analysis Workspace의 생산성 향상을 위한 팁


>[!BEGINSHADEBOX]

데모 비디오는 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [생산성 향상을 위한 팁](https://video.tv.adobe.com/v/33281?quality=12&learn=on&captions=kor){target="_blank"}을 참조하세요.

>[!ENDSHADEBOX]
