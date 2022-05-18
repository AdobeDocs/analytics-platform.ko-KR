---
description: AEP Attribution AI이 CJA에서 작업 공간과 통합되는 방법을 확인하십시오.
title: CJA와 Attribution AI 통합
role: Admin
solution: Customer Journey Analytics
source-git-commit: 5302d9213b66c327b59c3f4476fbf204f1078392
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 4%

---

# CJA와 Attribution AI 통합

>[!NOTE]
>
>이 페이지는 현재 개발 중입니다.

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en)Adobe Experience Platform Intelligent Services의 일부로, 지정된 결과에 대한 고객 상호 작용의 영향과 점진적 효과를 계산하는 다중 채널 알고리즘 속성 서비스입니다. 마케터는 Attribution AI을 통해 고객 여정의 각 단계에서 개별 고객과의 상호 작용이 미치는 영향을 파악하여 마케팅 및 광고 비용을 측정하고 최적화할 수 있습니다.

Attribution AI은 두 가지 점수 카테고리를 지원합니다. 알고리즘 및 규칙 기반. 알고리즘 점수에는 증분 및 영향을 받는 점수가 포함됩니다. 규칙 기반 점수는 첫 번째 터치, 마지막 터치, 선형, U자형 및 시간 감소가 포함됩니다. Attribution AI은 3개의 Experience Platform 스키마를 지원합니다. 경험 이벤트, Adobe Analytics 및 소비자 경험 이벤트입니다.

Attribution AI은 Attribution AI이 데이터에 대해 모델을 실행한 다음 CJA가 이러한 모델의 출력을 데이터 세트로 가져온 다음 나머지 CJA 데이터 세트와 통합할 수 있는 정도로 Customer Journey Analytics(CJA)와 통합됩니다. 그런 다음 Attribution AI 지원 데이터 세트를 CJA의 데이터 보기 및 보고에서 활용할 수 있습니다.

## 워크플로

일부 단계는 CJA에서 출력을 사용하기 전에 Adobe Experience Platform에서 수행됩니다.

### 1단계: Attribution AI 점수 다운로드

설명된 대로 Adobe Experience Platform에서 Attribution AI 점수를 다운로드합니다 [여기](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).

### 2단계: Attribution AI 인스턴스 만들기

설명된 대로 Experience Platform에서 데이터를 선택 및 매핑하고, 이벤트를 정의하고, 데이터를 교육하여 Attribution AI 인스턴스를 생성합니다 [여기](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### 3단계: Attribution AI 데이터 세트에 CJA 연결 설정

CJA에서 이제 다음을 수행할 수 있습니다 [하나 이상의 연결 만들기](/help/connections/create-connection.md) Attribution AI에 대해 계측된 데이터 세트 Experience Platform. 이러한 데이터 세트에는 다음과 같이 &quot;Attribution AI 점수&quot; 접두사가 있습니다.

![AAI 점수](assets/aai-scores.png)

### 4단계: 이러한 연결을 기반으로 데이터 보기 만들기

CJA에서,

## Attribution AI과 Attribution IQ 간의 차이점

따라서 언제 Attribution AI 데이터와 [Attribution IQ](/help/analysis-workspace/attribution/overview.md): 기본 CJA 기능 이 표에서는 기능의 몇 가지 차이점을 보여 줍니다.

| 기능 | Attribution AI | Attribution IQ |
| --- | --- | --- |
| 분수 기여도 분석 | 예 | 아니요 |
| 사용자가 모델을 조정할 수 있습니다 | 아니요 | 예 |
| 여러 채널에 기여도 분석이 수행됩니다(참고: AAI는 CJA와 동일한 결합된 데이터를 사용하지 않습니다.) | 예 | 예 |
| 증분 및 영향을 받는 점수 포함 | 예 | 아니요 |
| ML 모델링 | 예 | 예 |
| 예측을 사용하여 ML 모델링 | 예 | 아니요 |

{style=&quot;table-layout:auto&quot;}
