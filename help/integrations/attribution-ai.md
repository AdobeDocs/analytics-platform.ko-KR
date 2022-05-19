---
description: AEP Attribution AI이 CJA에서 작업 공간과 통합되는 방법을 확인하십시오.
title: CJA와 Attribution AI 통합
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: 77b253390dafb27228995f339d138eb9f4fa2c56
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 3%

---

# CJA와 Attribution AI 통합

>[!NOTE]
>
>이 기능은 2022년 5월 25일에 릴리스됩니다.

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en)Adobe Experience Platform Intelligent Services의 일부로, 지정된 결과에 대한 고객 상호 작용의 영향과 점진적 효과를 계산하는 다중 채널 알고리즘 속성 서비스입니다. 마케터는 Attribution AI을 통해 고객 여정의 각 단계에서 개별 고객과의 상호 작용이 미치는 영향을 파악하여 마케팅 및 광고 비용을 측정하고 최적화할 수 있습니다.

Attribution AI은 두 가지 점수 카테고리를 지원합니다. 알고리즘 및 규칙 기반. 알고리즘 점수에는 증분 및 영향을 받는 점수가 포함됩니다.

* **영향을 받는 점수** 마케팅 채널에서 전환 크레딧의 100%를 나눕니다.
* **증분 점수** 먼저 마케팅 없이 달성했을 전환 기준을 고려합니다. 이 기준선은 기존 브랜드 인식, 충성도 및 입소문 등의 AI 관찰에 따라 달라집니다. 나머지 크레딧은 마케팅 채널 간에 나눠집니다.

규칙 기반 점수는 다음과 같습니다 [!UICONTROL 첫 번째 터치], [!UICONTROL 마지막 터치], [!UICONTROL 선형], [!UICONTROL U자형], 및 [!UICONTROL 시간 가치 하락]. Attribution AI은 3개의 Experience Platform 스키마를 지원합니다. 경험 이벤트, Adobe Analytics 및 소비자 경험 이벤트입니다.

Attribution AI은 Attribution AI이 데이터에 대해 모델을 실행한 다음 CJA가 이러한 모델의 출력을 데이터 세트로 가져온 다음 나머지 CJA 데이터 세트와 통합할 수 있는 정도로 Customer Journey Analytics(CJA)와 통합됩니다. 그런 다음 Attribution AI 지원 데이터 세트를 CJA의 데이터 보기 및 보고에서 활용할 수 있습니다.

## 워크플로

일부 단계는 CJA에서 출력을 사용하기 전에 Adobe Experience Platform에서 수행됩니다. 출력은 적용된 Attribution AI 모델이 있는 데이터 세트로 구성됩니다.

### 1단계: Attribution AI 점수 다운로드

설명된 대로 Adobe Experience Platform에서 Attribution AI 점수를 다운로드합니다 [여기](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).

### 2단계: Attribution AI 인스턴스 만들기

설명된 대로 Experience Platform에서 데이터를 선택 및 매핑하고, 이벤트를 정의하고, 데이터를 교육하여 Attribution AI 인스턴스를 생성합니다 [여기](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### 3단계: Attribution AI 데이터 세트에 CJA 연결 설정

CJA에서 이제 다음을 수행할 수 있습니다 [하나 이상의 연결 만들기](/help/connections/create-connection.md) Attribution AI에 대해 계측된 데이터 세트 Experience Platform. 이러한 데이터 세트에는 다음과 같이 &quot;Attribution AI 점수&quot; 접두사가 있습니다.

![AAI 점수](assets/aai-scores.png)

>[!IMPORTANT]
>
>연결에 프로필 및 조회 데이터 세트와 콜 센터 및 CRM 데이터를 추가할 수 있습니다. 그러나 Adobe은 동일한 연결에서 Attribution AI 점수가 있는 데이터 세트에 Adobe Analytics 데이터 세트를 추가하는 것을 권장하지 않습니다.


### 4단계: 이러한 연결을 기반으로 데이터 보기 만들기

CJA에서, [하나 이상의 데이터 보기 만들기](/help/data-views/create-dataview.md) 에는 Attribution AI XDM 필드가 포함되어 있습니다. 여기에 스크린샷을 찍으면 좋겠습니다.

### 5단계: CJA 작업 공간의 AAI 데이터 보고서

CJA Workspace 프로젝트에서 &quot;AAI 주문&quot;과 같은 지표와 &quot;AAI 캠페인 이름&quot; 또는 &quot;AAI 마케팅 채널&quot;과 같은 차원을 가져올 수 있습니다.

![AAI 차원](assets/aai-dims.png)

영향을 받는 점수와 증분 점수가 포함된 주문을 표시하는 AAI 데이터가 포함된 작업 공간 프로젝트를 확인할 수 있습니다.

![AAI 프로젝트](assets/aai-project.png)

![AAI 프로젝트](assets/aai-project2.png)


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
