---
title: Customer Journey Analytics의 Google Analytics 데이터에 대한 보고서
description: Customer Journey Analytics의 Google Analytics 데이터에 대한 유용한 보고서를 표시합니다.
translation-type: tm+mt
source-git-commit: a4e95424ee304869e76a0532b7240290a3f13418
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---


# Customer Journey Analytics의 Google Analytics 데이터에 대한 보고서

이제 [Google Analytics 데이터를 Experience Platform 및 Customer Journey Analytics(CJA)](/help/use-cases/ga-to-cja.md)에 인제스트한 경우 해당 데이터에 대한 보고를 위한 유용한 시나리오를 보여줍니다.

## 웹 데이터와 앱 데이터를 통합 데이터 세트로 시각화

이 벤 다이어그램은 웹 사이트(Google Analytics 데이터)와 모바일 앱(Firebase 데이터)과 콜 센터의 사용자 오버랩을 보여줍니다. 또한 웹 뿐만 아니라 모바일 앱에서도 최고의 성능을 갖춘 제품을 볼 수 있습니다. 계산된 지표를 사용하여 두 가지 모두에서 총 매출을 얻을 수도 있습니다. 결합된 매출액을 볼 때 상위 제품이 서로 다른 스토리를 전달하는 방법을 살펴볼 수 있습니다. 데이터 세트를 결합하지 않으면 &quot;Twill Cap&quot;이 매우 강력한 수행자였다는 것을 결코 알 수 없습니다.

![](assets/combined-datasets.png)

## 호출 이유 식별 및 통화 볼륨 감소

많은 전화를 받았는지 확인하기 위해 지난 2개월 동안 콜센터 체류 시간을 트렌드에 표시할 수 있습니다. 증가하는 트렌드를 보는 것은 쉽다. 걱정스러운 것은, 콜 센터 직원이 매번 통화하는 전화비에 비용이 들므로. 이것은 당신의 수익에 확실히 영향을 줄 수 있다.

콜센터에 전화를 걸게 하는 주요 이유를 살펴보자. &quot;신용 카드 거부됨&quot;, &quot;신용 카드 제거&quot; 및 &quot;손상된 제품&quot;이 가장 큰 이유라는 것을 주목하십시오. 이것은 이미 온라인 경험을 개선할 수 있는 방법을 힌트할 수 있다. 또한 이러한 통화 이유를 트렌드에 표시하고 전체 스파이크에 가장 많은 기여를 한 이유를 확인할 수 있습니다. &quot;손상된 제품&quot;이 있는 고객이 전화당 3분 이상 시간을 보낸 것을 보니 흥미롭습니다.

![](assets/call-volume.png)

콜센터에 전화를 대부분의 걸게 하는 제품과 얼마나 많은 고객이 전화했는지 자세히 살펴보겠습니다. 거품형 차트는 2만명이 &#39;남성용 반팔 티티&#39; 제품 33개 중 3개 품목을 &quot;4시간 30분&quot;에 해당했다는 것을 보여준다.

이러한 통찰력을 분석해서 &quot;호출 이유&quot; 차원으로 드래그하여 제품을 반환한 이유를 확인할 수 있습니다. 보시다시피 이 제품이 많은 전화를 받는 이유는 &quot;손상된 제품&quot; 때문입니다. 다음 단계는 품질 관리부에 연락하여 고객이 손상된 T-셔츠를 입고 있는 이유를 확인하는 것입니다.

![](assets/call-reason.png)

이제 어느 웹 사이트 페이지가 콜센터에서 들어오는 전화를 유도했는지 살펴보겠습니다. 이렇게 하면 성과가 낮은 경험이 웹 사이트에서 어디에 있는지 파악하고 제품 관리자가 이러한 문제를 해결할 수 있습니다.

우리는 이것을 한다

* 계산된 지표를 사용하여 데이터를 콜 센터 호출로 끝난 세션으로만 필터링합니다.
* CJA의 [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#cja-workspace)에서 &quot;기여도&quot; 모델 사용

호출로 끝나는 세션에 가장 자주 참여하는 페이지를 손쉽게 확인할 수 있습니다. &quot;장바구니&quot; 및 &quot;체크아웃 정보&quot; 페이지가 대부분의 호출을 유도함을 볼 수 있습니다. firebase 모바일 앱 데이터도 포함되었으므로 페이지 오류와 호출을 생성하는 앱 충돌도 확인할 수 있습니다. 탁월한 웹 및 모바일 앱 경험을 제공하려는 경우 이는 매우 중요한 데이터 포인트입니다.

![](assets/contributing-pages.png)

마지막으로 Analysis Workspace의 집단 테이블을 사용하면 웹 사이트를 방문한 후 일반적으로 콜센터에 전화를 거는 데 걸리는 시간을 확인할 수 있습니다. 여기서 평균 시간은 3주에서 4주 사이입니다.

![](assets/cohort.png)

## 고급 마케팅 기여도 분석 사용

CJA를 사용하면 크로스채널 데이터에 정교한 어트리뷰션 모델을 사용할 수 있습니다. 다음 예에서는 매출을 Google Analytics 채널 그룹화 차원에 마지막 터치, 첫 번째 터치, u자 모양 및 알고리즘 속성 적용을 적용하는 비교표를 볼 수 있습니다.

![](assets/mktg-attribution.png)

계산된 지표를 사용하여 웹 매출액, 모바일 앱 매출액에 해당 속성을 적용하고 제품 수익률을 제거할 수 있습니다. 따라서 각 마케팅 채널에 대한 실제 순 매출을 확인할 수 있습니다.

![](assets/calc-metric.png)

또한 Attribution IQ을 사용하면 데이터를 손쉽게 필터링할 수 있습니다. 둘 이상의 장치를 사용하는 사용자 등 특정 사용자 세트에만 속성을 볼 수 있습니다.

![](assets/filter.png)

마지막으로, 웹 및 앱 매출액을 Google 광고 컨텐트에 연결할 수도 있습니다. 웹 광고보다 Adobe 온라인 Google Ads를 기반으로 하는 모바일 앱에서 더 많은 매출을 얻을 수 있습니다. 웹 및 앱 매출액을 기준으로 광고를 정렬하면 최고의 성과를 내는 Google 광고가 어떠했는지를 아주 다르게 알 수 있습니다.

![](assets/google-ad.png)

CJA가 없으면 온라인 광고가 모바일 앱에서 구입한 제품에 영향을 줄 수 있음을 알 수 없었습니다. 이제 Google Ads의 모바일 앱 수익은 웹에 비해 1,400~5,000달러 더 많은 수익을 내고 있습니다.

![](assets/google-ad2.png)