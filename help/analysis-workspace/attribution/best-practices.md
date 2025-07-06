---
title: 속성 모범 사례
description: 모범 사례를 이해하고 사용할 속성 모델을 결정합니다.
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: 1b6e1d432bfe4b0574b8ee68bcfa940941f3c36f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 66%

---

# 속성 모범 사례

조직에 적합한 속성 모델을 선택하는 것은 여러 고려 사항에 따라 다릅니다. 이 문서에서는 방법론과 몇 가지 일반적인 모범 사례에 대해 알아봅니다.

* [탐색적 분석](#exploratory-analysis)
* [규칙 기반 속성](#rule-base-attribution)
* [알고리즘 속성 사용](#use-algorithmic-attribution)

## 탐색적 분석

>[!NOTE]
>이 분석은 속성 모델을 선택하기 전에 먼저 수행되어야 합니다.

이 단계는 먼저 고객 행동을 이해하고 전환 지표를 정의하는 절차로 구성됩니다. 전환 지표를 기반으로 [데이터 피드](https://experienceleague.adobe.com/ko/docs/analytics/export/analytics-data-feed/data-feed-overview)&#x200B;(원시 데이터용) 또는 Analysis Workspace와 같은 도구를 통해

* 전환하기 전에 다른 마케팅 채널을 터치하고 있는 고객의 수와
* 이러한 행동의 비율/분포를 보다 쉽게 이해할 수 있습니다.

예를 들어 고객의 50%가 전환하기 전에 세 개의 채널을 터치한다면 이들 세 개의 채널 사이에 인터랙션이 있습니까?
그런 다음 상위 및 하위 단계 분석을 수행하여 이해를 확장할 수 있습니다.

### 상위 단계 분석

상위 단계 분석 채널은 브랜드 또는 제품 인지도를 창출하기 위해 사용됩니다. 예를 들어 대부분의 TV 광고의 목표는 브랜드 인지도입니다. 사람들은 시간이 지남에 따라 TV 광고를 잊게 되므로 [시간 감소 속성 모델](/help/analysis-workspace/attribution/models.md)을 사용할 수 있습니다.

### 하위 단계 분석

하위 단계 분석에서는 사람들이 이미 귀하의 브랜드를 알고 있고 귀하는 사람들이 전환하기를 원한다고 가정합니다. 이메일, 푸시 알림 또는 Facebook 광고를 사용합니다.

## 규칙 기반 속성

이 단계의 목적은 가설을 확인하는 것입니다.

**예 1**

가설: &quot;*첫 번째 터치 채널이 마지막 터치 채널보다 전환에 더 많은 영향을 미칩니다.*&quot;

이 경우 [역 J자형 속성 모델](/help/analysis-workspace/attribution/models.md)을 사용하여 이 가설을 테스트합니다. 이 모델은 첫 번째 터치 포인트에 60%의 크레딧을 제공합니다.

**예 2**

가설이 *이라고 가정해 보십시오.&quot;특정 업계(예: 여행 업계)에서는 고객이 제품을 구매하기 전에 많은 조사를 하기 때문에 속성 기간이 30일이 아니라 60일 또는 90일이라고 가정합니다.*&quot;

이 경우 [전환 확인 기간](https://experienceleague.adobe.com/ko/docs/analytics/analyze/analysis-workspace/attribution/models)을 90일로 변경할 수 있습니다.

## 알고리즘 속성 사용

모든 질문에 만족스러운 답변을 제공하는 기여도 모델이 아직 없는 경우 [알고리즘 기여도](/help/analysis-workspace/attribution/algorithmic.md)를 사용할 수 있습니다. 많은 수의 가능한 가설과 조합을 검증하는 것은 매우 어렵기 때문에, 알고리즘 속성은 기본 제공 알고리즘을 사용하여 차원 항목에 크레딧을 할당합니다.

## 기타 고려 사항

* Analysis Workspace에 의존하지 않고 데이터 과학자의 서비스를 사용해야 할 수도 있습니다.
* Adobe 데이터 피드에서와 같이 원시 데이터를 사용할 수 있습니다.
* 예를 들어 노출 데이터를 고려하려는 경우 [Customer Journey Analytics](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview) 사용을 고려해 보십시오.
