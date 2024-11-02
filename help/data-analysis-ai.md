---
description: Customer Journey Analytics 설명서의 데이터 분석 질문에 대한 질문을 하는 방법
title: Customer Journey Analytics의 Data Analysis AI Assistant
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: e18d8facbd54ae65d158ce2c72f47709ef988f8f
workflow-type: tm+mt
source-wordcount: '1422'
ht-degree: 4%

---


# Customer Journey Analytics - Alpha의 Data Analysis AI Assistant

Data Analysis AI Assistant는 Customer Journey Analytics에서 Analysis Workspace 데이터에 대한 질문에 보다 빠르고 효율적으로 답변할 수 있도록 도와주는 지능형 컨텍스트 인식 대화 에이전트입니다.

Assistant는 다양한 유형의 지표 및 구성 요소를 포함하여 데이터 보기에서 모든 데이터를 살펴보며 프롬프트를 이 분석에 적합한 차원, 지표 및 날짜 범위로 변환합니다. 데이터 보기 구성 요소를 숙지한 다음, 이러한 구성 요소를 드래그하여 최상의 조합으로 놓아 질문에 답변해야 하는 대신, 질문을 AI Assistant에 입력하면 됩니다.

## Alpha 버전의 범위 내 기능과 범위 외 기능 비교

### 범위 내 기능

| 지원되는 기능 | 설명 |
| --- | --- |
| **시각화 작성 및 업데이트** | 자유 형식 테이블 및 관련 시각화(예: 선, 막대, 도넛 등)를 생성합니다.<p>예: *2월부터 5월까지 SKU에서 발생한 이익은 무엇입니까?* |
| **지원되는 시각화 유형** | <ul><li>라인</li><li>여러 줄</li><li>자유 형식</li><li>막대</li><li>도넛</li><li>요약 번호</li></ul> |
| **범위 외 프롬프트 감지** | &quot;이 프로젝트 내보내기&quot;와 같이 범위를 벗어난 프롬프트를 제출하는 경우 도우미는 질문이 범위를 벗어났음을 알리는 방식으로 응답합니다. |
| **명확한 질문** | AI Assistant가 답변할 수 있는 충분한 컨텍스트가 없는 질문을 하거나 너무 일반적인 경우 AI Assistant는 명확한 질문 및/또는 제안된 옵션으로 응답합니다. 예: <p>**구성 요소**<ul><li>지표: *어떤 &quot;매출&quot; 지표를 의미했습니까?*</li><li>Dimension: *아래 &quot;지역&quot; 중 어떤 것에 집중하시겠습니까?*</li><li>필터: *어떤 &quot;계정&quot; 필터를 적용하시겠습니까?*</li><li>날짜 범위: *지난 달, 마지막 전체 달 또는 마지막 30일을 의미합니까?*</li></ul>**Dimension 항목**: &quot;스토어 이름&quot;을 의미합니까? (예: 스토어 #5274, 스토어 #2949 등) |
| **다중 회전** | AI 어시스턴트는 이전 프롬프트의 컨텍스트에 따라 프롬프트에 응답하므로 사용자가 시각화를 업데이트하고 후속 질문을 할 수 있습니다. 예: *3월에서 4월까지의 데이터를 대신 표시합니다.* |
| **피드백** | <ul><li>엄지 손가락 위로</li><li>엄지 손가락 아래로</li><li>플래그</li></ul> |

### 범위를 벗어난 기능

| 지원되지 않는 기능 | 설명 |
| --- | --- |
| **온라인 요약 또는 응답** | AI Assistant는 사용자 프롬프트의 요약 답변으로 채팅 레일에서 인라인 응답할 수 없습니다.범위 외 프롬프트의 예:<ul><li>*마지막 프롬프트에서 인사이트에 대한 요약을 제공합니다.*</li><li>*선 시각화에서 강조 표시를 요약합니다.*</li></ul> |
| **명확한 질문** | 질문을 명확히 하는 것은 구성 요소 및 차원 항목으로 제한됩니다. AI Assistant는 데이터 보기, 시각화, 데이터 세부 기간, 비교, 범위 등을 명확히 할 수 없습니다. 질문을 명확히 하지 않으면 어시스턴트는 사용자가 가장 많이 묻는 질문으로 기본 설정됩니다. 예기치 않은 시각화 또는 데이터 세부 기간 수준을 반환하는 경우 다중 회전/업데이트 기능을 사용하여 시각화 및 데이터를 조정할 수 있습니다. |
| **Workspace 작업/기능** | AI 도우미는 시각화를 구축하고 업데이트하는 것 외에 Workspace에서 사용자에 대한 작업을 수행할 수 없습니다. 예를 들어, 다음과 같은 작업은 수행할 수 없습니다.<ul><li>상황별 작업 UI 버튼(차트, 새 패널, 새 테이블에 추가)</li><li>공유</li><li>내보내기</li><li>다운로드</li><li>사용자 환경 설정 관리</li><li>조정</li><li>데이터 보기 관리</li><li>Analytics 대시보드 앱</li><li>속성</li></ul> |
| **지원되지 않는 시각화 유형** | <ul><li>흐름</li><li>폴아웃</li><li>집단 테이블</li><li>영역, 스택 영역</li><li>스택 막대</li><li>글머리 기호</li><li>콤보</li><li>히스토그램</li><li>가로 막대, 스택 가로 막대</li><li>주요 지표 요약</li><li>분산</li><li>요약 변경</li><li>텍스트</li><li>트리맵</li><li>벤</li></ul> |
| **설명 가능성 및 검증 가능성** | AI 어시스턴트가 응답을 생성한 방법에 대한 투명 설명 또는 인용을 제공하고 답변이 올바른지 확인할 수 있는 방법을 제공합니다. |

## Customer Journey Analytics UI의 기능 액세스

[알파에 이 섹션이 균일 필요합니까?]

다음 매개 변수는 데이터 분석 AI Assistant 기능에 대한 액세스를 제어합니다.

* **솔루션 액세스**: Data Analysis AI Assistant는 Customer Journey Analytics Prime 및 Ultimate 고객이 사용할 수 있습니다. Adobe Analytics에서는 사용할 수 없습니다.

Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP 및 추가 Experience Platform 앱에서도 사용할 수 있습니다.

* **계약 액세스**: AI Assistant를 사용할 수 없는 경우 조직의 관리자 또는 Adobe 계정 담당자에게 문의하십시오. 조직에서 Data Analysis AI Assistant를 사용하려면 먼저 귀하가 특정 GenAI 관련 법률 조항에 동의해야 합니다.

* **권한**: [!UICONTROL Adobe Admin Console]에서 [!UICONTROL 보고 도구] **[!UICONTROL AI Assistant: Data Analysis]** 권한이 이 도구에 대한 액세스를 결정합니다. [제품 프로필 관리자](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)는 [!UICONTROL Admin Console]에서 다음 단계를 따라야 합니다.
   1. **[!UICONTROL Admin Console]** > **[!UICONTROL 제품 및 서비스]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 제품 프로필]**(으)로 이동
   1. [!UICONTROL AI 길잡이: 제품 기술 자료]에 액세스할 수 있는 제품 프로필의 제목을 선택합니다.
   1. 특정 제품 프로필에서 **[!UICONTROL 권한]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 보고 도구]**&#x200B;를 편집하려면 ![편집](/help/assets/icons/Edit.svg)을 선택하세요.
   1. ![AddCircle](/help/assets/icons/AddCircle.svg)을(를) 선택하여 **[!UICONTROL 포함된 권한 항목]**&#x200B;에 **AI 길잡이: 데이터 분석**&#x200B;을(를) 추가합니다.

      ![권한 추가](assets/ai-assistant-permissions.png).

   1. **[!UICONTROL 저장]**&#x200B;을 선택하여 권한을 저장합니다.

자세한 내용은 [액세스 제어](/help/technotes/access-control.md#access-control)를 참조하십시오.

## Data Analysis AI Assistant 액세스 및 사용

1. 이 링크로 이동하여 Labs IMS Org(단계)에서 Workspace을 열고 Adobe ID으로 로그인합니다.

1. 새 빈 프로젝트를 열려면 프로젝트 페이지 상단의 배너에서 **[!UICONTROL 빈 프로젝트]**&#x200B;를 클릭하십시오.

1. 오른쪽 상단에 있는 AI 비서 채팅 아이콘을 클릭합니다.

   ![AI 길잡이 아이콘](/help/assets/ai-asst-icon.png)

1. 하단의 **[!UICONTROL Customer Journey Analytics에 대해 묻기]** 대화 상자에서 AI 도우미에서 데이터 분석 질문을 합니다.

### 예제 1

예를 들어 7월에 받은 주문에 관심이 있다고 가정해 보겠습니다.

1. &quot;7월 주문 표시&quot;를 입력합니다.

   ![AI 프롬프트](/help/assets/ai-asst-prompt1.png)

1. 이제 AI Assistant는 지표 및 구성 요소를 포함하여 데이터 보기에서 데이터를 확인하여 통찰력을 수집합니다. 프롬프트를 올바른 차원/초, 지표/초 및 데이터 범위로 변환합니다.

   보시다시피 7월 주문을 보여주는 선 그래프와 자유 형식 테이블이 자동으로 생성되었습니다.

   ![프롬프트에 응답 - 선 그래프 및 자유 형식 테이블](/help/assets/ai-asst-result.png)

### 예제 2

다음으로, 지역별로 매출이 어떻게 비교되는지 확인하려고 합니다.

1. 프롬프트 창에서 &quot;지역별 매출 표시&quot;를 입력합니다.

2. AI는 &quot;지역&quot;에서 &quot;고객 지역&quot;을 의미한다는 것을 이해할 수 있을 만큼 스마트합니다. 지역별 매출을 가장 잘 보여주는 막대 차트를 생성합니다.

   ![막대 차트](/help/assets/ai-asst-result2.png)

### 예제 3

이제 제품 범주별 매출액을 살펴보자.

1. 프롬프트 창에서 &quot;제품 범주별 매출 표시&quot;를 입력합니다.

2. 다시 말하지만, Data Analysis AI Assistant는 가장 적절한 시각화(이 경우 **[!UICONTROL 도넛]** 시각화)를 선택하여 질문에 답합니다.

   ![도넛](/help/assets/ai-asst-result3.png)

### 예제 4

마지막으로, 가장 수익성이 높은 SKU와 마케팅 리소스를 어디에 투자해야 하는지 알고 싶을 수 있습니다.

1. 프롬프트 창에서 &quot;2월부터 5월까지 SKU에서 수익이 어떻게 됩니까?&quot;라고 묻습니다.

1. 간단한 **[!UICONTROL 막대]** 차트는 가장 간결한 답변을 제공합니다.

   ![막대 차트](/help/assets/ai-asst-result4.png)

## 데이터 분석 프롬프트 예

다음은 일반적인 프롬프트의 몇 가지 예와 AI Assistent가 이러한 프롬프트에 응답하는 데 사용하는 시각화입니다.

| 예제 프롬프트 | 예상 시각화 |
| --- | --- |
| [개월]에 이익 표시 | 라인<p>기본적으로 특정 시간 범위 내에서 트렌드 또는 지표를 요청하면 라인 시각화가 반환됩니다. |
| [개월]의 주문 트렌드 | 라인 |
| [개월]에 지역별 수입 표시 | 막대 |
| 제품 범주별 매출 점유율 | 도넛 |
| 요일(1월부터 5월까지)별 주문 | 막대 |
| 3월부터 6월까지 성별 주문 보기 | 막대 |
| 2월부터 5월까지 SKU의 수익 | 막대 |
| [월]의 저장소 이름별 수익 | 막대 |
| [월]에 수익별 상위 10개 SKU는 무엇입니까? | 막대 |
| 연간 월별 구매 비율 | 도넛 |
| [개월]의 총 이익 | 요약 번호<p>특정 시간 범위 동안 지표의 &quot;합계&quot;를 요청하려면 요약 번호 시각화를 반환해야 합니다. |


## 프롬프트 우수 사례

TBD

## Alpha 테스트 기대치 및 요청된 피드백

각 질문을 제기한 후 비서가 제공한 답변을 주의 깊게 검토합니다. 피드백을 제공하기 전에 생성된 시각화를 종합적으로 평가하는 것이 중요합니다.

응답 평가: 주어진 답변이 맞습니까?

어시스턴트가 채팅 레일 내에서 응답하는 경우: 텍스트 응답을 평가합니다.

* 시각화/차트가 표시되는 경우: 시각화를 평가합니다. 질문에 대한 적절한/예상 시각화입니까?

* 자유 형식 테이블이 표시되는 경우: 자유 형식 테이블을 평가합니다. 자유 형식 테이블 데이터가 올바릅니까? 요청한 위치에 데이터를 분류하고 있습니까? 적용된 필터가 요청했거나 예상한 필터입니까?

* 질문이 범위를 벗어났음을 나타내는 일반적인 오류 메시지가 표시되는 경우 메시지가 표시되는 경우 범위를 벗어난 메시지가 적절하다고 생각하는지 여부에 대한 피드백을 제공합니다. 당신의 신속성이 실제로 범위 내에 있었습니까?

모든 응답에 대해 응답을 기준으로 엄지 손가락을 위로 또는 아래로 내립니다.

엄지 손가락 위쪽/아래쪽 선택 다음에 관련 다중 선택 피드백 상자를 선택하십시오. 추가 피드백을 제공하려면 열기 텍스트 상자에 메모를 추가합니다.

## 질문 및 연락처

전자 메일 `taylorb@adobe.com`(PM)
Alpha Slack 채널에서 질문과 피드백 보내기: #aep-cja-ai-assistant-testers ???


