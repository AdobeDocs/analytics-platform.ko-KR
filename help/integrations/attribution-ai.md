---
description: AEP Attribution AI이 CJA에서 작업 공간과 통합되는 방법을 확인하십시오.
title: CJA와 Attribution AI 통합
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: d165b3aaca9f99bb23bcbfbcfbca9d2e96b3cfcb
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 10%

---

# CJA와 Attribution AI 통합

>[!NOTE]
>
>이 기능은 2022년 5월 25일에 릴리스됩니다.

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en)Adobe Experience Platform Intelligent Services의 일부로, 지정된 결과에 대한 고객 상호 작용의 영향과 점진적 효과를 계산하는 다중 채널 알고리즘 속성 서비스입니다. 마케터는 Attribution AI을 통해 고객 여정의 각 단계에서 개별 고객과의 상호 작용이 미치는 영향을 파악하여 마케팅 및 광고 비용을 측정하고 최적화할 수 있습니다.

Attribution AI은 Attribution AI이 데이터에 대해 모델을 실행한 다음 CJA가 이러한 모델의 출력을 데이터 세트로 가져온 다음 나머지 CJA 데이터 세트와 통합할 수 있는 정도로 Customer Journey Analytics(CJA)와 통합됩니다. 그런 다음 Attribution AI 지원 데이터 세트를 CJA의 데이터 보기 및 보고에서 활용할 수 있습니다.

Attribution AI은 3개의 Experience Platform 스키마를 지원합니다. 경험 이벤트, Adobe Analytics 및 소비자 경험 이벤트입니다.

Attribution AI은 두 가지 점수 카테고리를 지원합니다. 알고리즘 및 규칙 기반.

## 알고리즘 점수

알고리즘 점수에는 증분 및 영향을 받는 점수가 포함됩니다.

* **[!UICONTROL 영향] 점수** 마케팅 채널에서 전환 크레딧의 100%를 나눕니다.
* **[!UICONTROL 증분] 점수** 먼저 마케팅 없이 달성했을 전환 기준을 고려합니다. 이 기준선은 기존 브랜드 인식, 충성도 및 입소문 등의 AI 관찰에 따라 달라집니다. 나머지 크레딧은 마케팅 채널 간에 나눠집니다.

## 규칙 기반 점수

규칙 기반 점수는 다음과 같습니다

* **[!UICONTROL 첫 번째 터치]** 속성 전환 확인 기간에서 맨 먼저 표시된 터치 포인트에 100% 크레딧을 제공합니다.
* **[!UICONTROL 마지막 터치]** 전환 전에 가장 최근에 발생하는 터치 포인트에 100% 크레딧을 제공합니다.
* **[!UICONTROL 선형]** 전환으로 이어지는 모든 표시되는 터치 포인트에 동일한 크레딧을 제공합니다.
* **[!UICONTROL U자형]** 첫 번째 상호 작용에 40% 크레딧을 제공하고, 마지막 상호 작용에 40% 크레딧을 제공하며, 나머지 20%를 그 사이의 모든 터치 포인트에 나눠줍니다. 터치 포인트가 하나인 전환의 경우 100% 크레딧이 제공됩니다. 터치 포인트가 두 개인 전환의 경우 두 터치 포인트에 50% 크레딧이 제공됩니다.
* **[!UICONTROL 시간 가치 하락]** 기본값이 7일인 사용자 지정 반감기 매개 변수를 사용하는 기하급수적 감소가 따릅니다. 각 채널의 가중치는 터치 포인트 시작과 최종 전환 사이에 경과된 시간에 따라 달라집니다. 크레딧을 결정하는 데 사용되는 공식은 `2^(-t/halflife)`이고, 여기서 `t`는 터치 포인트와 전환 사이의 시간입니다. 그러면 모든 터치 포인트가 100%로 표준화됩니다.

## 워크플로

일부 단계는 CJA에서 출력을 사용하기 전에 Adobe Experience Platform에서 수행됩니다. 출력은 적용된 Attribution AI 모델이 있는 데이터 세트로 구성됩니다.

### 1단계: Attribution AI 인스턴스 만들기

설명된 대로 Experience Platform에서 데이터를 선택 및 매핑하고, 이벤트를 정의하고, 데이터를 교육하여 Attribution AI 인스턴스를 생성합니다 [여기](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### 2단계: Attribution AI 데이터 세트에 CJA 연결 설정

CJA에서 이제 다음을 수행할 수 있습니다 [하나 이상의 연결 만들기](/help/connections/create-connection.md) Attribution AI에 대해 계측된 데이터 세트 Experience Platform. 이러한 데이터 세트에는 다음과 같이 &quot;Attribution AI 점수&quot; 접두사가 있습니다.

![AAI 점수](assets/aai-scores.png)

### 3단계: 이러한 연결을 기반으로 데이터 보기 만들기

CJA에서, [하나 이상의 데이터 보기 만들기](/help/data-views/create-dataview.md) 에는 Attribution AI XDM 필드가 포함되어 있습니다. 여기에 스크린샷을 찍으면 좋겠습니다.

### 4단계: CJA 작업 공간의 AAI 데이터 보고서

CJA Workspace 프로젝트에서 &quot;AAI 주문&quot;과 같은 지표와 &quot;AAI 캠페인 이름&quot; 또는 &quot;AAI 마케팅 채널&quot;과 같은 차원을 가져올 수 있습니다.

![AAI 차원](assets/aai-dims.png)

**영향을 받는 주문 및 증분 점수**

영향을 받는 점수와 증분 점수가 포함된 주문을 표시하는 AAI 데이터가 포함된 작업 공간 프로젝트를 확인할 수 있습니다. 임의의 차원으로 드릴다운하여 다음 방법으로 속성을 이해합니다. 캠페인, 제품 그룹, 사용자 세그먼트, 지역 등.

![AAI 프로젝트](assets/aai-project.png)

![AAI 프로젝트](assets/aai-project2.png)

**마케팅 성과**

다양한 속성 모델 간의 접점 속성 비교 및 대조:

![비교](assets/compare.png)

**채널 상호 작용**

채널 상호 작용을 이해하여 벤 다이어그램을 사용하여 다른 채널과 가장 효과적으로 사용할 수 있는 채널을 확인합니다.

![마케팅 채널 겹치기](assets/mc-overlap.png)

**전환으로 연결되는 상위 경로**

이 표에서는 터치포인트를 디자인하고 최적화하는 데 도움이 되는 전환(중복 제거됨)에 대한 상위 경로를 보여줍니다.

![상위 채널](assets/top-channels.png)

**리드 타임 전환**

여기서는 터치 포인트가 혼합되어 있을 때 전환으로 가는 리드 타임이 표시됩니다. 리드 타임 최적화에 도움이 됩니다.

![리드 타임](assets/lead-time.png)

## 새 CJA 지표

| 지표 | 설명 |
| --- | --- |
| [!UICONTROL 획득 비율] | 각 채널에 대해 터치한 전환 경로 중 시작 채널의 백분율입니다. |
| [!UICONTROL 플레이어 속도] | 각 채널에 대해 터치한 전환 경로 중 플레이어가 되는 채널의 백분율입니다. |
| [!UICONTROL 가까운 비율] | 각 채널에 대해 터치한 전환 경로 중 클로저가 되는 채널의 백분율입니다. |
| [!UICONTROL AAI 평균 주문까지의 일수] | 각 채널에 대해 주문 이후 평균 일 수입니다. |
| [!UICONTROL 판매 프로세스의 AAI 평균 총 일수] | 각 채널에 대해 터치한 전환 경로의 평균 총 일 수입니다. |
| [!UICONTROL 평균 주문에서 벗어난 터치] | 각 채널에 대해 평균은 순서에서 떨어져 있습니다. |

{style=&quot;table-layout:auto&quot;}

## Attribution AI과 Attribution IQ 간의 차이점

따라서 언제 Attribution AI 데이터와 [Attribution IQ](/help/analysis-workspace/attribution/overview.md): 기본 CJA 기능 이 표에서는 기능의 몇 가지 차이점을 보여 줍니다.

| 기능 | Attribution AI | Attribution IQ |
| --- | --- | --- |
| 분수 기여도 분석 | 예 | 아니요 |
| 사용자가 모델을 조정할 수 있습니다 | 예 | 예 |
| 여러 채널에 기여도 분석이 수행됩니다(참고: AAI는 CJA와 동일한 결합된 데이터를 사용하지 않습니다.) | 예 | 예 |
| 증분 및 영향을 받는 점수 포함 | 예 | 아니요 |
| ML 모델링 | 예 | 예 |
| 예측을 사용하여 ML 모델링 | 예 | 아니요 |

{style=&quot;table-layout:auto&quot;}
