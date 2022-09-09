---
title: Customer Journey Analytics에서 Google Analytics 데이터에 대한 보고
description: Customer Journey Analytics에서 Google Analytics 데이터에 대한 유용한 보고서 표시
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 35%

---

# Customer Journey Analytics에서 Google Analytics 데이터에 대한 보고

Customer Journey Analytics에서 사용할 수 있는 데이터가 있으면 다음 예에서는 해당 데이터에 대한 보고 시 유용한 시나리오를 제공합니다.

## 웹 데이터와 앱 데이터를 통합된 데이터 세트로 시각화

이 Venn 다이어그램은 웹 사이트의 사용자(Google Analytics 데이터 기반), 모바일 앱 사용자(Firebase 데이터 기반), 콜센터의 사용자를 중첩하여 보여 줍니다. 또한 성과가 가장 좋은 제품들을 웹뿐 아니라 모바일 앱에서도 볼 수 있습니다. 계산된 지표를 사용하여 두 가지 모두에서 총 매출도 얻을 수 있습니다. 통합된 매출을 살펴보면 최우수 제품에 대해 미처 파악하지 못했던 정보를 파악할 수 있습니다. 통합된 데이터 세트가 없었다면 &quot;트윌 캡&quot;이 우수한 성과를 보이는 제품이었다는 사실을 절대 몰랐을 것입니다.

![데이터 세트 결합](../assets/combined-datasets.png)

## 문의 전화의 이유 파악 및 문의 전화량 감소

지난 2개월 동안의 콜 센터 체류 시간의 트렌드를 표시하여 호출 볼륨을 결정할 수 있습니다. 다음 예는 지난 2개월 동안의 이 데이터 트렌드를 보여줍니다. 다음 예는 조직 비용에 영향을 줄 수 있는 증가 트렌드를 보여줍니다.

![통화 볼륨](../assets/call-volume.png)

&#39;호출 이유&#39; 차원을 사용하면 웹 경험을 향상시키는 방법에 힌트를 줄 수 있으므로 방문자가 처음부터 호출하지 못합니다. 위의 예에서는 &quot;Damage product&quot;의 평균 호출 시간이 호출당 거의 3분이라는 것을 보여주어, 조직에 고객 경험을 향상하고 콜 센터 비용을 절감하는 정확한 방법을 제공합니다.

콜 센터에 대한 대부분의 통화를 야기하는 제품과 그러한 호출을 한 고객 수를 확인할 수 있습니다. 거품도표는 2만 명이 4시간 30분 이상 소비한 뒤 남성용 쇼트 슬리브 티 제품 33개를 반환했다는 것을 보여준다.

![통화 이유](../assets/call-reason.png)

&#39;호출 이유&#39;의 차원 분류를 적용하는 예에서는 &quot;손상된 제품&quot; 차원 항목이 표시됩니다. 다음 단계는 품질 관리 부서에 문의하여 고객들이 왜 손상된 티셔츠를 받게 되었는지 알아보는 것입니다.

콜 센터까지 간 웹 사이트 페이지를 확인할 수 있습니다. 이 보고서를 통해 웹 사이트에서 최적의 경험이 어디 있는지 알 수 있고 제품 관리자가 이러한 문제를 해결할 수 있습니다. 다음 예제에서는 계산된 지표를 사용하여 데이터를 콜 센터 호출로 끝나는 세션으로만 필터링합니다. 또한 CJA의 &quot;기여도&quot; 모델을 사용합니다 [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html#cja-workspace).

다음 예는 &quot;장바구니&quot; 및 &quot;체크아웃 정보&quot; 페이지가 대부분의 호출을 유도하는 것을 보여줍니다.

![기여 페이지](../assets/contributing-pages.png)

집단 테이블을 사용하면 사용자가 웹 사이트를 방문한 후 일반적으로 콜 센터에 호출하는 데 걸리는 시간을 확인할 수 있습니다. 다음 예는 이 예제 데이터 세트에 대한 평균 시간이 3~4주 사이임을 나타냅니다.

![집단](../assets/cohort.png)

## 고급 마케팅 속성 사용

CJA에서는 크로스 채널 데이터에 정교한 속성 모델을 사용할 수 있습니다. 다음의 예에서는 Google Analytics 채널 그룹화 차원에 매출의 마지막 터치, 첫 번째 터치, U자형, 그리고 알고리즘 속성을 적용한 경우를 비교해 볼 수 있습니다.

![마케팅 기여도 분석](../assets/mktg-attribution.png)

계산된 지표를 사용하면 이러한 속성을 웹 매출과 모바일 앱 매출에 적용할 수 있으며 심지어 제품 반품을 제외할 수 있습니다. 그리고 결과적으로 각 마케팅 채널의 진정한 순 매출을 볼 수 있습니다.

![계산된 지표](../assets/calc-metric.png)

Attribution IQ을 사용하여 데이터를 필터링할 수도 있습니다. 예를 들어 두 개 이상의 디바이스를 사용하는 사용자 등 특정한 사용자 집합에 대해서만 속성을 볼 수 있습니다.

![필터](../assets/filter.png)

웹 및 앱 매출을 Google 광고 컨텐츠에 지정할 수도 있습니다. 이 데이터 세트의 예는 웹보다 온라인 Google Ads를 통해 제공되는 모바일 앱으로 인한 매출이 더 늘어났으며, 웹 및 앱 매출별로 광고를 정렬하면 가장 성과가 좋은 Google 광고가 무엇인지 다른 그림을 볼 수 있습니다.

![Google 광고](../assets/google-ad.png)

CJA에서 데이터 세트를 결합하면 이 예에서 온라인 광고가 모바일 앱에서 구매한 제품에 영향을 주는지 확인할 수 있습니다. 다음 시각화는 Google Ads의 모바일 앱 매출액이 웹과 비교하여 1만 4천 달러(1만 5천 달러)임을 보여줍니다.

![Google 광고 2](../assets/google-ad2.png)
