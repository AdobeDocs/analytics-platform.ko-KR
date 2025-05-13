---
description: Customer Journey Analytics 설명서의 데이터 분석 관련 질문을 하는 방법
title: Customer Journey Analytics의 Data Insights 에이전트를 사용하여 데이터 시각화
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: f3f3b34c904c1aeba3fbd07218f323ccd81974d4
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 3%

---

# Customer Journey Analytics에서 Data Insights Agent을 사용하여 데이터 시각화

{{release-limited-testing}}

>[!AVAILABILITY]
>
>Data Insights Agent은 2025년 11월 30일까지 자격 있는 Customer Journey Analytics 고객이 사용할 수 있습니다. 해당 날짜 이후, Data Insights Agent을 계속 사용하려면 라이선스가 필요합니다. 라이선스 프로세스에 대한 지원은 Adobe 계정 팀에 문의하십시오.

Customer Journey Analytics의 AI Assistant에서 액세스할 수 있는 Data Insights Agent은 데이터에 대한 질문에 빠르고 효율적으로 답변할 수 있는 생성 AI 대화 에이전트입니다. 데이터 보기의 구성 요소를 사용하고 실제 데이터를 사용하여 Analysis Workspace에서 관련 시각화를 구축합니다.

Data Insights Agent을 사용하여 Analysis Workspace의 데이터 중심 질문에 답변하면 Analysis Workspace에서 시각화를 수동으로 구축하고 데이터 보기 구성 요소에 익숙해지는 데 드는 시간을 크게 절약할 수 있습니다.

![AI Assistant 내의 데이터 인사이트 에이전트](assets/cja-ai-asst-da.gif)

## 범위 내 및 범위 외 기능



### 범위 내 기능

| 지원되는 기능 | 설명 |
| --- | --- |
| **시각화 빌드 및 업데이트** | 자유 형식 테이블 및 관련 시각화(예: 선, 막대, 도넛 등)를 생성합니다.<p>예: *2월부터 5월까지 SKU에서 발생한 이익은 무엇입니까?* |
| **지원되는 시각화 유형** | <ul><li>라인</li><li>다중 라인</li><li>자유 형식 테이블</li><li>막대</li><li>도넛</li><li>요약 숫자</li></ul> |
| **범위를 벗어난 프롬프트 감지** | &quot;이 프로젝트 내보내기&quot;와 같이 범위를 벗어난 프롬프트를 제출하는 경우 Data Insights Agent은 질문이 범위를 벗어났음을 알리는 방식으로 응답합니다. |
| **명확한 질문** | Data Insights Agent이 답변할 수 있는 충분한 컨텍스트가 없는 질문을 하거나 너무 일반적인 질문을 하는 경우 Data Insights Agent은 명확한 질문이나 제안된 옵션으로 응답합니다. 예: <p>**구성 요소**<ul><li>지표: *어떤 &quot;매출&quot; 지표를 의미했습니까?*</li><li>Dimension: *아래 &quot;지역&quot; 중 어떤 것에 집중하시겠습니까?*</li><li>세그먼트: *어떤 &quot;계정&quot; 세그먼트를 적용하시겠습니까?*</li><li>날짜 범위: *지난 달, 마지막 전체 달 또는 마지막 30일을 의미합니까?*</li></ul>**Dimension 항목**: &quot;스토어 이름&quot;을 의미합니까? (예: 스토어 #5274, 스토어 #2949 등) |
| **다중 회전** | Data Insights Agent은 이전 프롬프트의 컨텍스트에 따라 프롬프트에 응답하므로 사용자가 시각화를 업데이트하고 후속 질문을 할 수 있습니다. 예: <ul><li>프롬프트 1: *3월의 트렌드 이벤트*</li><li>프롬프트 2: *대신 3월에서 4월까지의 데이터 표시*</li></ul> |
| **확인 가능** | 생성된 자유 형식 테이블 및 데이터 시각화를 통해 데이터 검증 가능성 및 정확성을 확인할 수 있다. 예를 들어, 사용자가 *지난 달 주문 트렌드*&#x200B;에 대해 묻는 경우, 새로 생성된 패널, 데이터 시각화 및 자유 형식 테이블에서 올바른 지표(&quot;주문&quot;) 및 날짜 범위(&quot;지난 달&quot;)가 선택되었는지 확인할 수 있습니다. |
| **피드백** | <ul><li>엄지 손가락 위로</li><li>엄지 손가락 아래로</li><li>플래그</li></ul> |

### 범위를 벗어난 기능

| 지원되지 않는 기능 | 설명 |
| --- | --- |
| **온라인 요약 또는 응답** | Data Insights Agent은 사용자 프롬프트의 요약 답변으로 채팅 레일에서 인라인으로 응답할 수 없습니다. 범위 외 프롬프트 예:<ul><li>*마지막 프롬프트에서 인사이트에 대한 요약을 제공합니다.*</li><li>*선 시각화에서 강조 표시를 요약합니다.*</li></ul> |
| **명확한 질문** | 질문을 명확히 하는 것은 구성 요소 및 차원 항목으로 제한됩니다. Data Insights Agent에서는 데이터 보기, 시각화, 데이터 세부기간, 비교 및 범위와 같은 항목을 명확하게 할 수 없습니다. 명확한 질문을 사용할 수 없는 경우 상담원은 사용자가 요청할 가능성이 가장 높은 질문을 기본값으로 설정합니다. 예기치 않은 시각화 또는 데이터 세부기간을 반환하는 경우 다중 전환/업데이트 기능을 사용하여 시각화 및 데이터를 조정할 수 있습니다. |
| **Workspace 작업/기능** | Data Insights Agent은 시각화를 구축하고 업데이트하는 것 외에 Workspace에서 사용자에 대한 작업을 수행할 수 없습니다. 예를 들어, 다음 작업을 수행할 수 없습니다.<ul><li>상황별 작업 UI 버튼(차트, 새 패널, 새 테이블에 추가)</li><li>공유</li><li>내보내기</li><li>다운로드</li><li>사용자 환경 설정 관리</li><li>조정</li><li>데이터 보기 관리</li><li>Analytics 대시보드 앱</li><li>속성</li></ul> |
| **지원되지 않는 시각화 유형** | <ul><li>플로우</li><li>폴아웃</li><li>집단 테이블</li><li>영역, 스택 영역</li><li>스택 막대</li><li>글머리 기호</li><li>콤보</li><li>히스토그램</li><li>가로 막대, 스택 가로 막대</li><li>주요 지표 요약</li><li>분산</li><li>요약 변경</li><li>텍스트</li><li>트리맵</li><li>벤</li></ul> |

## Customer Journey Analytics에서 Data Insights Agent에 대한 액세스 관리

다음 매개 변수는 Customer Journey Analytics에서 Data Insights Agent에 대한 액세스를 제어합니다.

* **솔루션 액세스**: Customer Journey Analytics Prime 및 Ultimate 고객이 Data Insights Agent을 사용할 수 있습니다. Adobe Analytics에서는 사용할 수 없습니다.

* **계약 액세스**: AI Assistant에서 Data Insights Agent을 사용할 수 없는 경우 조직의 관리자 또는 Adobe 계정 팀에 문의하십시오. 조직에서 Data Insights Agent을 사용하려면 먼저 생성 AI와 관련된 특정 법률 용어에 동의해야 합니다.

* **권한**: 사용자가 Data Insights Agent에 액세스하려면 [!UICONTROL Adobe Admin Console]에서 필요한 권한을 부여해야 합니다.

  권한을 부여하려면 [제품 프로필 관리자](https://helpx.adobe.com/kr/enterprise/using/manage-product-profiles.html)가 [!UICONTROL Admin Console]에서 다음 단계를 완료해야 합니다.
   1. **[!UICONTROL Admin Console]**&#x200B;에서 **[!UICONTROL 제품]** 탭을 선택하여 **[!UICONTROL 모든 제품 및 서비스]** 페이지를 봅니다.
   1. **[!UICONTROL Customer Journey Analytics]**&#x200B;을(를) 선택합니다.
   1. **[!UICONTROL 제품 프로필]** 탭에서 [!UICONTROL AI Assistant: 제품 기술 자료]에 대한 액세스 권한을 제공할 제품 프로필의 제목을 선택합니다.
   1. 특정 제품 프로필에서 **[!UICONTROL 권한]** 탭을 선택합니다.

      Admin Console의 ![사용 권한 탭](assets/ai-assistant-permissions-tab.png)

   1. 제공된 테이블의 **[!UICONTROL 보고 도구]** 행에서 편집 아이콘 ![편집](/help/assets/icons/Edit.svg)을 선택합니다.
   1. **[!UICONTROL AI Assistant: 제품 정보]**(으)로 스크롤하거나 검색한 다음 이 권한 옆에 있는 더하기 아이콘 ![AddCircle](/help/assets/icons/AddCircle.svg)을(를) 선택합니다.

      **[!UICONTROL AI Assistant: 제품 정보]** 권한이 **[!UICONTROL 포함된 권한 항목]** 열에 추가됩니다.

      ![권한 추가](assets/ai-assistant-permissions.png).

   1. **[!UICONTROL 데이터 보기 도구]** 탭을 선택한 다음 **[!UICONTROL Data Insights Agent]** 권한 옆에 있는 더하기 아이콘 ![AddCircle](/help/assets/icons/AddCircle.svg)을(를) 선택합니다.

      **[!UICONTROL Data Insights Agent]** 권한이 **[!UICONTROL 포함된 권한 항목]** 열에 추가되었습니다.

      ![권한 추가](assets/ai-assistant-permissions-dataviewtools.png).

   1. Data Insights Agent에 사용할 데이터 보기를 선택하려면 **[!UICONTROL 데이터 보기]** 탭을 선택하십시오.

      >[!IMPORTANT]
      >
      >Data Insights Agent은 포함된 데이터 보기를 Admin Console에서 활성화한 같은 날 중에 참조할 수 있습니다.

   1. 활성화하려는 데이터 보기를 검색하거나 스크롤한 다음 각 데이터 보기 이름 옆에 있는 더하기 아이콘 ![AddCircle](/help/assets/icons/AddCircle.svg)을 선택합니다.

      추가한 각 데이터 보기는 **[!UICONTROL 포함된 권한 항목]** 열에 표시됩니다.

      ![권한 추가](assets/ai-assistant-permissions-dataviews.png).

   1. 권한을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

  액세스 제어에 대한 자세한 내용은 [액세스 제어](/help/technotes/access-control.md#access-control)를 참조하십시오.

## AI Assistant에서 Data Insights Agent 액세스

1. [experience.adobe.com](https://experience.adobe.com/)&#x200B;(으)로 이동하여 Adobe ID으로 로그인합니다.

2. Experience Cloud 홈에서 **Customer Journey Analytics**&#x200B;을(를) 선택합니다.

3. 새 빈 프로젝트를 열려면 프로젝트 페이지 상단의 배너에서 **[!UICONTROL 빈 프로젝트]**&#x200B;을(를) 선택하십시오.

4. 패널에 대해 선택한 데이터 보기가 [Customer Journey Analytics에서 Data Insights Agent에 대한 액세스 관리](#manage-access-to-data-insights-agent-in-customer-journey-analytics)에 설명된 대로 Data Insights Agent에서 사용할 수 있도록 설정된 데이터 보기인지 확인하십시오.

5. 페이지의 오른쪽 상단 영역에서 AI Assistant 채팅 아이콘을 선택합니다.

   채팅 아이콘이 보이지 않는 경우 관리자에게 문의하여 Admin Console에서 다음 기능을 활성화하십시오.

   * 보고 도구: **[!UICONTROL AI 길잡이: 제품 지식]**

   * 데이터 보기 도구: **[!UICONTROL Data Insights Agent]**

   자세한 내용은 [Customer Journey Analytics에서 Data Insights Agent 액세스 관리](#manage-access-to-data-insights-agent-in-customer-journey-analytics)를 참조하십시오.

   ![AI 길잡이 아이콘](/help/assets/ai-asst-icon.png)

6. 페이지 하단의 **[!UICONTROL Customer Journey Analytics에 대해 묻기]** 대화 상자에서 Data Insights Agent을 사용하여 데이터 시각화 질문을 합니다.

   자세한 내용은 다음 예를 참조하십시오.

### 예제 1

예를 들어 7월에 받은 주문에 관심이 있다고 가정해 보겠습니다.

**프롬프트:** *&quot;7월의 트렌드 주문&quot;* 입력

![AI 프롬프트](/help/assets/ai-asst-prompt1.png)

**응답:** Data Insights Agent은 데이터 보기에서 지표 및 구성 요소를 포함한 데이터를 확인하여 통찰력을 수집합니다. 프롬프트가 데이터 범위 내에서 올바른 차원 및 지표로 변환됩니다.

보시다시피 7월 주문을 표시하기 위해 선 그래프와 자유 형식 테이블을 자동으로 생성했습니다.

![프롬프트에 응답 - 선 그래프 및 자유 형식 테이블](/help/assets/ai-asst-result.png)

### 예제 2

다음으로, 지역별로 매출이 어떻게 비교되는지 확인하려고 합니다.

**프롬프트:** 프롬프트 창에서 *&quot;지역별 매출액 표시&quot;*&#x200B;를 입력하십시오.

**응답:** Data Insights Agent은 &quot;지역&quot;별로 &quot;고객 지역&quot;을 의미한다는 것을 지능적으로 이해합니다. 지역별 매출을 가장 잘 보여주는 막대 차트를 생성합니다.

![막대 차트](/help/assets/ai-asst-result2.png)

### 예제 3

다음으로 지역별 매출을 이해하는 것 외에도 지역별 수익 데이터를 확인할 수 있습니다. 이전 프롬프트를 반복하는 대신 Data Insights Agent에 최신 시각화 및 자유 형식 테이블을 업데이트하도록 요청할 수 있습니다.

**프롬프트:** 프롬프트 창에서 *&quot;이익 추가&quot;를 입력하십시오.*

**응답:** **[!UICONTROL 막대]** 차트는 여전히 가장 간결한 답변을 제공하지만 이익 지표가 자유 형식 테이블의 열로 추가되었습니다.

![막대 차트](/help/assets/ai-asst-result4.png)

### 예제 4

마지막으로, 제품 범주별 매출액을 살펴보자.

**프롬프트:** 프롬프트 창에 *&quot;제품 범주별 매출액 비율&quot;을 입력하십시오.*

**응답:** Data Insights Agent은 질문에 답변할 수 있도록 가장 적절한 시각화(이 경우 **[!UICONTROL 도넛]** 시각화)를 선택합니다.

![도넛](/help/assets/ai-asst-result3.png)

## 예제 데이터 시각화 프롬프트

다음은 일반적인 프롬프트 및 Data Insights Agent에서 이러한 프롬프트에 응답하는 데 사용한 시각화의 몇 가지 예입니다.

| 예제 프롬프트 | 예상 시각화 |
| --- | --- |
| [개월]에 이익 표시 | 라인<p>기본적으로 특정 시간 범위 내에서 트렌드 또는 지표를 요청하면 라인 시각화가 반환됩니다. |
| [개월]의 주문 트렌드 | 라인 |
| [개월]에 지역별 수입 표시 | 막대 |
| 제품 범주별 매출 점유율 | 도넛 |
| 1월부터 5월까지 요일별 주문 | 막대 |
| 3월부터 6월까지 성별 주문 표시 | 막대 |
| 2월부터 5월까지 SKU의 이익은 얼마입니까 | 막대 |
| [월]의 저장소 이름별 수익 | 막대 |
| [월]에 수익별 상위 10개 SKU는 무엇입니까? | 막대 |
| 연간 월별 구매 비율 | 도넛 |
| [개월]의 총 이익 | 요약 번호<p>특정 시간 범위 동안 지표의 &quot;합계&quot;를 요청하려면 요약 번호 시각화를 반환해야 합니다. |


## 프롬프트 우수 사례

Data Insights Agent은 각 사용자 프롬프트에서 제공하는 컨텍스트를 처리하고 자유 형식 테이블에서 가장 적절한 시각화 및 구성 요소로 지능적으로 응답하려고 합니다.

프롬프트에 사용된 특정 단어와 구에 따라 응답이 다를 수 있으며, 언어가 약간 변경되면 다른 결과가 나타날 수 있습니다.

최상의 결과를 얻으려면 다음 지침을 고려하십시오.

* **구체적으로 지정:** 응답 범위를 좁히려면 정확한 용어를 포함하십시오. 다음은 특정 프롬프트의 예입니다. &quot;Last month&#39;s sales in California&quot;

* **명확한 지표, 차원 및 세그먼트 사용:** 특정 지표(예: &quot;매출&quot;), 차원(예: &quot;웹 사이트 이름&quot;), 세그먼트(예: &quot;iPhone 사용자&quot;) 및 날짜 범위(예: &quot;최근 3개월&quot;)를 추가하면 Data Insights Agent이 올바른 데이터에 집중할 수 있습니다.

* **직접 질문하기:** 직접 질문을 표현하면 Data Insights Agent에서 명확하고 관련성 있는 통찰력을 쉽게 제공할 수 있습니다. 다음은 &quot;올해 제품 범주별 평균 매출은 무엇입니까?&quot;라는 질문을 즉석에서 던진 예입니다.

예상할 수 있는 응답 유형과 함께 Data Insights Agent을 사용하여 프롬프트에 사용할 수 있는 다음 예시 용어 표를 검토하십시오.

이러한 예제는 특정 단어나 구조가 데이터 Insight 에이전트의 출력에 어떤 영향을 미칠 수 있는지 파악하여 보다 정확하고 중요한 통찰력을 보장하는 데 도움이 되도록 설계되었습니다. Data Insights Agent은 생성 AI를 사용하므로 시각화 또는 선택한 데이터가 유사한 프롬프트에 따라 약간 다를 수 있습니다.

| 원하는 결과 | 용어와 구 예시 |
| --- | --- |
| 요약 번호 시각화 | <ul><li>합계</li></ul> |
| 구성 요소 비교 | <ul><li>비교</li><li>및</li><li>대비</li><li>주별</li><li>월정액</li><li>사분기</li><li>해가 거듭되어</li></ul> |
| 도넛 시각화 | <ul><li>비율</li><li>공유</li><li>배포</li><li>백분율</li><li>기여도</li><li>부분</li><li>부분</li></ul> |
| 라인 시각화 | <ul><li>트렌드</li><li>[시간 범위]의 [지표]</li></ul> |
| 막대 시각화 | <ul><li>[Dimension]의 [지표]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->

