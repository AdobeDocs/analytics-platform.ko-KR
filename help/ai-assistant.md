---
description: Customer Journey Analytics 설명서에 대한 질문을 하는 방법
title: Adobe Customer Journey Analytics용 AI 어시스턴트
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 20b578a6269aeaf54f6296b1f4337937887ecf05
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 2%

---


# Adobe Customer Journey Analytics용 AI 어시스턴트

AI 비서는 실무자가 빠른 속도로 작업을 수행할 수 있는 대화식 경험이다. 개념을 이해하거나 문제를 해결하거나 정보를 검색하는 것이 과제인지 여부. AI 비서도 전문가가 아닌 일반인이 전문가 업무를 수행할 수 있도록 해 전반적인 업무 품질을 높인다.

Customer Journey Analytics의 AI 도우미는 Adobe Experience League 설명서에 대해 교육되었습니다. 질문을 받으면 빠른 학습이 가능한 유익한 답변으로 AI 비서가 응답한다.

초보 사용자는 AI Assistant를 사용하여 Customer Journey Analytics 개념을 학습하고 익숙하지 않은 제품 및 기능을 온보딩할 수 있습니다. 숙련된 사용자는 AI Assistant를 사용하여 보다 고급 사용 사례나 팁 및 요령을 제시할 수 있습니다.

개념 질문의 몇 가지 예는 다음과 같습니다.

* 일괄 처리와 스트리밍 수집 간의 차이점은 무엇입니까?
* Customer Journey Analytics의 가장 좋은 용도는 무엇입니까?
* 데이터 보기를 설정하려면 어떻게 합니까?

Adobe Target 및 Adobe Creative Cloud Suite와 같은 다른 Adobe 제품에 대한 질문과 같이 Customer Journey Analytics 범위를 벗어나는 질문은 대답할 수 없습니다.

Customer Journey Analytics을 위한 AI Assistant는 모든 제품 계층에서 사용할 수 있습니다.

## 제품 지식 {#knowledge}

제품 지식 검색 모델은 Customer Journey Analytics 교육을 받습니다. 데이터 분석과 같은 다른 기능은 나중에 롤아웃됩니다.

| 제품 지식 | 예 |
| --- | --- |
| 뾰족한 학습 | <ul><li>Adobe Analytics과 Customer Journey Analytics의 차이점은 무엇입니까?</li><li>계산된 지표를 만들려면 어떻게 합니까?</li></ul> |
| 검색 열기 | <ul><li>Workspace 프로젝트를 내보내려면 어떻게 해야 합니까?</li><li>중복 Workspace 구성 요소를 찾으려면 어떻게 해야 합니까?</li></ul> |
| 문제 해결 | <ul><li>데이터가 CJA로 전송되려면 얼마나 걸립니까?</li><li>Customer Journey Analytics 연결에서 파생된 필드는 몇 개까지 사용할 수 있습니까?</li></ul> |

## 기능 액세스

다음 매개 변수는 AI Assistant 기능에 대한 액세스를 제어합니다.

* **솔루션 액세스**: AI 도우미는 Customer Journey Analytics에서 사용할 수 있지만 Adobe Analytics에서는 사용할 수 없습니다. Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP 및 추가 Experience Platform 앱에서도 사용할 수 있습니다.

* **계약 액세스**: AI Assistant를 사용할 수 없는 경우 조직의 관리자 또는 Adobe 계정 담당자에게 문의하십시오. 조직에서 AI Assistant를 사용하려면 먼저 특정 GenAI 관련 법률 조항에 동의해야 합니다.

* **권한**: [!UICONTROL Adobe Admin Console]에서 [!UICONTROL 보고 도구] **[!UICONTROL AI Assistant: 제품 기술 자료]** 권한이 이 도구에 대한 액세스를 결정합니다. [제품 프로필 관리자](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)는 [!UICONTROL Admin Console]에서 다음 단계를 따라야 합니다.
   1. **[!UICONTROL Admin Console]** > **[!UICONTROL 제품 및 서비스]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 제품 프로필]**(으)로 이동
   1. [!UICONTROL AI 길잡이: 제품 기술 자료]에 액세스할 수 있는 제품 프로필의 제목을 선택합니다.
   1. 특정 제품 프로필에서 **[!UICONTROL 권한]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 보고 도구]**&#x200B;를 편집하려면 ![편집](/help/assets/icons/Edit.svg)을 선택하세요.
   1. ![AddCircle](/help/assets/icons/AddCircle.svg)을(를) 선택하여 **[!UICONTROL 포함된 권한 항목]**&#x200B;에 **AI 길잡이: 제품 지식**&#x200B;을(를) 추가합니다.

      ![권한 추가](assets/ai-assistant-permissions.png).

   1. **[!UICONTROL 저장]**&#x200B;을 선택하여 권한을 저장합니다.

자세한 내용은 [액세스 제어](/help/technotes/access-control.md#access-control)를 참조하십시오.

## Customer Journey Analytics UI에서 AI 지원에 액세스

1. AI Assistant를 실행하려면 Customer Journey Analytics UI에 있는 페이지의 상단 헤더에서 AI Assistant 아이콘을 선택합니다.

   ![AI 길잡이 아이콘](assets/ai-asst1.png)

   AI Assistant를 처음 사용하는 경우 Assistant 사용에 대한 일부 약관과 함께 면책조항이 나타납니다.

1. 제공된 상자에서 AI Assistant의 특정 자연어 질문을 합니다.

   ![질문 상자](assets/ai-asst2.png)

1. (선택 사항) 소스를 표시하려면 **[!UICONTROL 소스 표시]**&#x200B;를 클릭하면 답변을 알려 주는 설명서 소스가 표시됩니다.

1. (선택 사항) 주어진 답변의 유용성에 대해 엄지손가락을 치켜거나 아래로 향하게 하여 투표할 수도 있습니다.

1. (선택 사항) 적절하지 않거나 해로운 콘텐츠에 대해 답변을 표시할 수 있습니다.
