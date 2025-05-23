---
description: Customer Journey Analytics 설명서의 데이터 분석 질문 방법
title: Customer Journey Analytics의 Data Insights 에이전트를 사용하여 데이터 시각화
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: 730464719f05026eae141c8e6cc656fb0fe4f819
workflow-type: tm+mt
source-wordcount: '1961'
ht-degree: 35%

---

# Customer Journey Analytics에서 Data Insights Agent을 사용하여 데이터 시각화

>[!AVAILABILITY]
>
>이 문서에 설명된 기능은 2025년 5월 28일에 시작되는 단계적 릴리스의 일부로 모든 적격 고객이 사용할 수 있으며, 현재 환경에서는 아직 사용할 수 없습니다. 기능이 일반적으로 제공되면 이 메모는 제거됩니다. Customer Journey Analytics 릴리스 프로세스에 대한 자세한 내용은 [Customer Journey Analytics 기능 릴리스](/help/release-notes/releases.md)를 참조하십시오.

>[!AVAILABILITY]
>
>Data Insights Agent은 제한된 기간 동안 적격 고객이 사용할 수 있습니다. Data Insights Agent에 대한 액세스는 2025년 11월 30일에 종료됩니다. 중단 없이 Data Insights Agent을 계속 사용하려면 Adobe 계정 담당자에게 연락하여 Data Insights Agent 라이선스에 대해 자세히 알아보십시오.

Customer Journey Analytics의 AI Assistant에서 액세스할 수 있는 Data Insights Agent은 데이터에 대한 질문에 빠르고 효율적으로 답변할 수 있는 생성 AI 대화 에이전트입니다. 데이터 보기의 구성 요소와 실제 데이터를 사용하여 Analysis Workspace에서 관련 시각화를 구축합니다.

Data Insights Agent을 사용하여 Analysis Workspace의 데이터 중심 질문에 답변하면 Analysis Workspace에서 시각화를 수동으로 구축하고 데이터 보기 구성 요소에 익숙해지는 데 드는 시간을 크게 절약할 수 있습니다.

![AI 어시스턴트 내의 Data Insights 에이전트](assets/cja-ai-asst-da.gif)

## 범위 내 및 범위 외 기능

| 기능 | 범위 내 | 범위를 벗어남 |
| --- | --- | --- |
| **시각화 유형** | <ul><li>라인</li><li>다중 라인</li><li>자유 형식 테이블</li><li>막대</li><li>도넛</li><li>요약 숫자</li></ul> | <ul><li>플로우</li><li>폴아웃</li><li>코호트 테이블</li><li>영역, 스택 영역</li><li>스택 막대</li><li>글머리 기호</li><li>콤보</li><li>히스토그램</li><li>가로 막대, 스택 가로 막대</li><li>주요 지표 요약</li><li>분산</li><li>요약 변경</li><li>텍스트</li><li>트리맵</li><li>벤</li></ul> |
| **Workspace 작업 및 에이전트 기능** | <ul><li>시각화 작성 및 업데이트<p>자유 형식 테이블과 관련 시각화(라인, 막대, 도넛 등)를 생성합니다.<p>예를 들어, *2월부터 5월까지 SKU의 이익은 무엇입니까?*</p></li><li>후속 질문<p>이전 프롬프트에서 컨텍스트에 있는 프롬프트에 응답합니다. 예:</p> <ul><li>프롬프트 1: *3월의 트렌드 이벤트.*</li><li>프롬프트 2: *대신 3월부터 4월까지의 데이터를 보여 주십시오*</li></ul> </li><li>범위를 벗어난 프롬프트 감지<p>*이 프로젝트 내보내기*&#x200B;와 같이 범위를 벗어난 프롬프트를 제출하는 경우 Data Insights Agent은 질문이 범위를 벗어났음을 알리는 방식으로 응답합니다.</p></li></ul> | <ul><li>공유</li><li>내보내기</li><li>다운로드</li><li>사용자 환경 설정 관리</li><li>데이터 보기 관리</li><li>Analytics 대시보드 앱</li><li>속성</li><li>인라인 요약 또는 응답<p>Data Insights Agent은 사용자 프롬프트의 요약 답변으로 채팅 레일에서 인라인으로 응답할 수 없습니다. 범위를 벗어나는 프롬프트의 예로는 *마지막 프롬프트에서 인사이트에 대한 요약을 제공합니다* 및 *선 시각화에서 하이라이트를 요약합니다*.</p></li></ul> |
| **질문 명료화** | Data Insights Agent이 답변할 수 있는 충분한 컨텍스트가 없는 질문을 하거나 너무 일반적인 질문을 하는 경우 Data Insights Agent은 명확한 질문이나 제안된 옵션으로 응답합니다. <p>구성 요소 관련 질문의 예는 다음 명확화 질문입니다.</p><ul><li>지표: *어떤 “수익” 지표를 말씀하시는 겁니까?*</li><li>차원: *아래 “지역” 중 어느 지역에 집중하고 싶으십니까?*</li><li>세그먼트: *어떤 “계정” 세그먼트를 적용하고 싶으십니까?*</li><li>날짜 범위: *“지난 달”이란 지난 한 달을 의미하는 것입니까, 아니면 지난 30일을 의미하는 겁니까?*</li></ul><p>다음 명확화 질문은 차원 항목과 관련된 질문의 예입니다.</p> <ul><li>어떤 &quot;가게 이름&quot;을 말씀하시는 건가요? (예: 매장 #5274, 매장 #2949 등)</li></ul> | 질문 명료화는 구성 요소와 차원 항목으로 제한됩니다. Data Insights Agent에서는 데이터 보기, 시각화, 데이터 세부기간, 비교 및 범위와 같은 항목을 명확하게 할 수 없습니다. 명확한 질문을 사용할 수 없는 경우, 에이전트는 사용자가 요청할 가능성이 가장 큰 질문을 기본값으로 설정합니다. 예기치 않은 시각화 또는 데이터 세부기간을 반환하는 경우 후속 질문을 하거나 시각화 및 데이터를 조정할 수 있습니다. |
| **데이터 확인 및 수정** | 생성된 자유 형식 테이블 조회 및 데이터 시각화를 통해 데이터 검증성 및 정확성을 확인할 수 있다. <p>예를 들어 Data Insights Agent에 *지난 달의 트렌드 주문*&#x200B;을(를) 요청하면 새로 생성된 패널, 데이터 시각화 및 자유 형식 테이블에서 올바른 지표(&quot;주문&quot;) 및 날짜 범위(&quot;지난 달&quot;)가 선택되었는지 확인할 수 있습니다. | Data Insights Agent은 추가된 구성 요소 또는 시각화를 알려 주지 않습니다.</p> |
| **피드백 메커니즘** | <ul><li>좋아요</li><li>싫어요</li><li>플래그</li></ul> |  |


## Customer Journey Analytics에서 Data Insights Agent에 대한 액세스 관리

다음 매개 변수는 Customer Journey Analytics에서 Data Insights Agent에 대한 액세스를 제어합니다.

* **솔루션 액세스**: Data Insights Agent은 2025년 11월 30일까지 제한된 액세스 프로그램의 일부로 모든 Customer Journey Analytics 고객이 사용할 수 있습니다. Adobe Analytics에서는 사용할 수 없습니다.

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
      >데이터 보기를 활성화할 때 다음 사항을 고려하십시오.
      >* IMS 조직당 최대 50개의 데이터 보기를 활성화할 수 있습니다. 주어진 조직에 대해 모든 제품 프로필에서 50개 이상의 데이터 보기를 활성화하면 Data Insights Agent에서 가장 많이 사용되는 50개의 데이터 보기를 사용합니다.
      >* Data Insights Agent은 포함된 데이터 보기를 Admin Console에서 활성화한 같은 날 중에 참조할 수 있습니다.

   1. 활성화하려는 데이터 보기를 검색하거나 스크롤한 다음 각 데이터 보기 이름 옆에 있는 더하기 아이콘 ![AddCircle](/help/assets/icons/AddCircle.svg)을 선택합니다.

      추가한 각 데이터 보기는 **[!UICONTROL 포함된 권한 항목]** 열에 표시됩니다.

      ![권한 추가](assets/ai-assistant-permissions-dataviews.png).

   1. 권한을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

  액세스 제어에 대한 자세한 내용은 [액세스 제어](/help/technotes/access-control.md#access-control)를 참조하십시오.

## AI Assistant에서 Data Insights Agent 액세스

1. [experience.adobe.com](https://experience.adobe.com/)으로 이동하여 Adobe ID로 로그인합니다.

2. Experience Cloud 홈에서 **Customer Journey Analytics**&#x200B;를 선택합니다.

3. 프로젝트 페이지 상단 배너에서 **[!UICONTROL 빈 프로젝트]**&#x200B;를 선택하여 새로운 빈 프로젝트를 엽니다.

4. 패널에 대해 선택한 데이터 보기가 [Customer Journey Analytics에서 Data Insights Agent에 대한 액세스 관리](#manage-access-to-data-insights-agent-in-customer-journey-analytics)에 설명된 대로 Data Insights Agent에서 사용할 수 있도록 설정된 데이터 보기인지 확인하십시오.

5. 페이지 오른쪽 상단에 있는 AI 어시스턴트 채팅 아이콘을 선택합니다.

   채팅 아이콘이 보이지 않으면 관리자에게 문의하여 Admin Console에서 다음 기능을 활성화합니다.

   * 보고 도구: **[!UICONTROL AI 길잡이: 제품 지식]**

   * 데이터 보기 도구: **[!UICONTROL Data Insights Agent]**

   자세한 내용은 [Customer Journey Analytics에서 Data Insights Agent 액세스 관리](#manage-access-to-data-insights-agent-in-customer-journey-analytics)를 참조하십시오.

   ![AI 어시스턴트 아이콘](/help/assets/ai-asst-icon.png)

6. 페이지 하단의 **[!UICONTROL Customer Journey Analytics에 대해 묻기]** 대화 상자에서 Data Insights Agent을 사용하여 데이터 시각화 질문을 합니다.

   자세한 내용은 다음 예제를 참조하십시오.

### 예제 1

예를 들어 귀하의 비즈니스가 7월에 받은 주문에 관심이 있다고 가정해 보겠습니다.

**프롬프트:** *“7월의 트렌드 주문”*&#x200B;을 입력합니다.

![AI 프롬프트](/help/assets/ai-asst-prompt1.png)

**응답:** Data Insights Agent은 데이터 보기에서 지표 및 구성 요소를 포함한 데이터를 확인하여 통찰력을 수집합니다. 프롬프트를 데이터 범위 내에서 올바른 차원과 지표로 변환합니다.

보시다시피, 7월 주문을 표시하기 위해 자동으로 선 그래프와 자유 형식 테이블을 생성했습니다.

![프롬프트에 대한 답변 - 선 그래프와 자유 형식 테이블](/help/assets/ai-asst-result.png)

### 예제 2

다음으로, 지역별로 수익을 비교하려고 합니다.

**프롬프트:** 프롬프트 창에 *“지역별 수익 표시”*&#x200B;를 입력합니다.

**응답:** Data Insights Agent은 &quot;지역&quot;별로 &quot;고객 지역&quot;을 의미한다는 것을 지능적으로 이해합니다. 지역별 수익을 가장 잘 보여 주는 막대형 차트를 생성합니다.

![막대 그래프](/help/assets/ai-asst-result2.png)

### 예제 3

다음으로 지역별 매출을 이해하는 것 외에도 지역별 수익 데이터를 확인할 수 있습니다. 이전 프롬프트를 반복하는 대신 Data Insights Agent에 최신 시각화 및 자유 형식 테이블을 업데이트하도록 요청할 수 있습니다.

**프롬프트:** 프롬프트 창에 *“수익 추가”*&#x200B;를 입력합니다.

**응답:** **[!UICONTROL 막대]** 그래프는 여전히 가장 간결한 답변을 제공하지만 수익 지표는 자유 형식 테이블에 열로 추가되었습니다.

![막대 그래프](/help/assets/ai-asst-result4.png)

### 예제 4

마지막으로 제품 카테고리별 매출을 살펴보겠습니다.

**프롬프트:** 프롬프트 창에 *“제품 카테고리별 수익 비율”*&#x200B;을 입력합니다.

**응답:** Data Insights Agent은 질문에 답변할 수 있도록 가장 적절한 시각화(이 경우 **[!UICONTROL 도넛]** 시각화)를 선택합니다.

![도넛](/help/assets/ai-asst-result3.png)

## 데이터 시각화 프롬프트 예시

다음은 일반적인 프롬프트 및 Data Insights Agent에서 이러한 프롬프트에 응답하는 데 사용한 시각화의 몇 가지 예입니다.

| 예시 프롬프트 | 예상 시각화 |
| --- | --- |
| [월별] 이익 보기 | 라인<p>기본적으로 특정 시간 범위 내의 트렌드나 지표를 요청하면 라인 시각화가 반환됩니다. |
| [월별] 트렌드 주문 | 라인 |
| [월별] 지역별 수익 보기 | 막대 |
| 제품 카테고리별 매출 점유율 | 도넛 |
| 1월부터 5월까지 일별 주문 | 막대 |
| 3월부터 6월까지 성별 주문 보기 | 막대 |
| 2월부터 5월까지 SKU 전체의 수익은 얼마입니까? | 막대 |
| [월별] 매장명별 매출 | 막대 |
| [월별] 수익이 가장 높았던 상위 10개 SKU는 무엇입니까? | 막대 |
| 연간 월별 구매 비율 | 도넛 |
| [월별] 총 이익 | 요약 숫자<p>특정 시간 범위에 걸친 지표의 “전체”를 요청하면 요약 숫자 시각화가 반환되어야 합니다. |


## 프롬프트 모범 사례

Data Insights Agent은 각 사용자 프롬프트에서 제공하는 컨텍스트를 처리하고 자유 형식 테이블에서 가장 적절한 시각화 및 구성 요소로 지능적으로 응답하려고 합니다.

응답은 프롬프트에 사용된 특정 단어와 구문에 따라 달라질 수 있으며, 언어의 미세한 변화는 다른 결과를 초래할 수 있습니다.

최상의 결과를 얻으려면 다음 지침을 고려해야 합니다.

* **구체적으로 지정:** 응답 범위를 좁히려면 정확한 용어를 포함하십시오. 다음은 특정 프롬프트의 예입니다. &quot;Last month&#39;s sales in California&quot;

* **명확한 지표, 차원 및 세그먼트 사용:** 특정 지표(예: &quot;매출&quot;), 차원(예: &quot;웹 사이트 이름&quot;), 세그먼트(예: &quot;iPhone 사용자&quot;) 및 날짜 범위(예: &quot;최근 3개월&quot;)를 추가하면 Data Insights Agent이 올바른 데이터에 집중할 수 있습니다.

* **직접 질문하기:** 직접 질문을 표현하면 Data Insights Agent에서 명확하고 관련성 있는 통찰력을 쉽게 제공할 수 있습니다. 다음은 &quot;올해 제품 범주별 평균 매출은 무엇입니까?&quot;라는 질문을 즉석에서 던진 예입니다.

예상할 수 있는 응답 유형과 함께 Data Insights Agent을 사용하여 프롬프트에 사용할 수 있는 다음 예시 용어 표를 검토하십시오.

이러한 예제는 특정 단어나 구조가 데이터 Insight 에이전트의 출력에 어떤 영향을 미칠 수 있는지 파악하여 보다 정확하고 중요한 통찰력을 보장하는 데 도움이 되도록 설계되었습니다. Data Insights Agent은 생성 AI를 사용하므로 시각화 또는 선택한 데이터가 유사한 프롬프트에 따라 약간 다를 수 있습니다.

| 원하는 결과 | 예시 용어 및 구문 |
| --- | --- |
| 요약 숫자 시각화 | <ul><li>합계</li></ul> |
| 구성 요소 비교 | <ul><li>비교</li><li>및</li><li>대비</li><li>주별</li><li>월별</li><li>분기별</li><li>전년 대비</li></ul> |
| 도넛 시각화 | <ul><li>비율</li><li>점유율</li><li>분포</li><li>백분율</li><li>기여도</li><li>부분</li><li>부분</li></ul> |
| 라인 시각화 | <ul><li>트렌드</li><li>[시간 범위]의 [지표]</li></ul> |
| 막대 시각화 | <ul><li>[차원]별 [지표]</li></ul> |

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

