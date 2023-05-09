---
description: Adobe은 사용할 수 있는 다양한 계산된 지표를 제공합니다. 이 페이지에는 해당 지표와 의도한 사용 목록이 표시됩니다.
title: 기본 계산된 지표
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 66%

---

# 기본 계산된 지표

Customer Journey Analytics은 가장 일반적인 사용 사례를 다루는 다양한 계산된 지표를 제공합니다. 이러한 계산된 지표는 Analysis Workspace에서 기본적으로 사용할 수 있습니다.

다음은 Adobe에서 제공하는 각 계산된 지표의 목록이며, 그 의도한 함수와 이를 계산하는 데 사용되는 기본 공식이 있습니다.

>[!NOTE]
>
>이 페이지에 설명된 기본 계산된 지표 외에도 데이터 보기에 계산된 지표를 추가할 수도 있습니다.
>
>:
> * 에 설명된 대로 스트리밍 미디어에 대한 기본 계산된 지표를 추가합니다. [계산된 지표](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 에 설명된 대로 기존 지표에서 사용자 지정 계산된 지표를 만듭니다. [계산 및 고급 계산(파생) 지표](/help/components/calc-metrics/cm-adv-functions.md).



| 계산된 지표 이름 | 함수 | 공식 |
|---------|----------|---------|
| 바운스 비율 | 해당 페이지의 방문 수와 비교하여 정확히 한 번의 히트가 포함된 방문의 비율. 이를 통해 이탈률이 가장 높은 차원 항목을 파악하거나 시간 경과에 따른 사이트의 집계된 총 이탈률을 확인할 수 있습니다. | `[Bounces] / [Entries]` |
| 매출/방문자 | 사이트의 개별 방문자가 생성한 평균 매출. | `[Revenue] / [Unique Visitors]` |
| 주문 수/방문자 수 | 사이트의 개별 방문자가 생성한 평균 주문 또는 거래 횟수 | `[Orders] / [Unique Visitors]` |
| 수입/방문 횟수 | 사이트 1회 방문으로 생성된 평균 매출. | `[Revenue] / [Visits]` |
| 수입/주문 | 사이트에서 완료된 각 거래 또는 주문에 의해 생성된 평균 매출. | `[Revenue] / [Orders]` |
| 주문 수/방문 수 | 거래가 완료된 사이트 방문 비율. | `[Orders] / [Visits]` |
| 페이지 조회수/방문 수 | 사용자가 사이트를 한 번 방문하는 동안 본 평균 페이지 수. | `[Page Views] / [Visits]` |
| 방문 횟수/방문자 | 고유 방문자의 평균 사이트 조회 수. | `[Visits] / [Unique Visitors]` |
| 다시 로드 / 페이지 보기 횟수 | 페이지 다시 로드 또는 새로 고침으로 이어진 페이지 조회수의 비율. | `[Reloads] / [Page Views]` |
| 가중 바운스 비율 | 함수 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 지원 주문 | 채널 또는 소스가 고객의 구매 여정에 기여했지만 최종 구매로는 이어지지 않은 횟수. | `[Orders (Visit Participation)] - [Orders]` |
| 종료 비율 | 특정 페이지를 본 후 사이트를 떠나는 방문자의 비율. | `[Exits] / [Visits]` |
| 시작 비율 | 사이트의 총 세션 수와 비교하여 주어진 페이지에서 사이트에 들어온 방문자의 비율. | `[Entries] / [Visits]` |
| 사이트의 평균 시간 | 방문자가 사이트를 떠나거나 다른 곳으로 이동하기 전에 사이트를 이용한 평균 시간. | `[Average Time Spent on Site (Seconds)]` |
| 체류 시간/사용자(상태) | 평균 방문자가 사이트에 있는 동안 특정 주에서 보내는 시간 | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 사용자(모바일) | 모바일 앱을 사용하는 총 사용자 수 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 앱 사용자 | 모바일 앱을 사용하는 총 사용자 수 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 상태 보기 | 앱의 다른 상태 또는 화면에 대한 보기 수 | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| 작업 | 앱에서 수행된 총 작업 수 | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| 획득 링크 클릭 수 | 사용자가 사이트로 트래픽을 유도하도록 설계된 링크를 클릭한 횟수. | `[Campaign Click-throughs]` |
| 페이지 속도 | 한 컨텐츠가 생성하는 추가 페이지 보기 수입니다. 이를 통해 추가 참여를 유도하는 컨텐츠를 결정할 수 있습니다. | `[Page Views] / [Visits]` |
| 전환율 | 구매와 같이 원하는 작업을 수행한 방문자의 비율. | `[Orders] / [Visits]` |
| 평균 세션 길이(모바일) | 방문자가 단일 세션 동안 사이트를 이용하는 평균 시간. | 빈 |
| Experience Cloud ID 범위 | Experience Cloud ID를 보유한 방문자의 비율. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 콘텐츠 속도 | 새 콘텐츠가 제작되고 사이트에 게시되는 속도와 이러한 콘텐츠에서 사용자 참여가 발생하는 속도. | `[Page Views] / [Visits]` |
| ITP 2.1 고유 방문자 / 고유 방문자 수 | ITP 2.1 쿠키 제한의 영향을 받는 브라우저를 사용하는 고유 방문자, 즉 CNAME 구현을 사용하지 않는 고객의 비율. 이는 클라이언트측 JavaScript를 통해 쿠키를 설정하는 고객에게 적용됩니다. | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| 7일 후 재방문하는 고유 방문자/고유 방문자 | 7일 이상의 기간 후에 돌아오는 고유 방문자 비율. | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| 페이지 보기 수/고유 방문자 수 | 사이트의 각 고유 방문자가 조회한 평균 페이지 수. | `[Page Views] / [Unique Visitors]` |
| 방문 횟수 / 방문자 | 고유 방문자의 평균 사이트 조회 수 . | `[Visits] / [Unique Visitors]` |
| 예상 고유 방문자 수(ITP 2.1) | ITP 방문자(Safari 브라우저의 사용자)의 경우 고유 방문자 수를 2 이하로 나눕니다. 이 계산된 지표는 사용자가 클라이언트측 JavaScript를 사용하여 쿠키를 설정한다고 가정합니다(CNAME 구현을 사용하지 않음). 클라이언트측 JavaScript를 사용하여 쿠키를 설정하는 구현은 ITP 2.1부터 영향을 받았습니다. [지능형 추적 방지](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 자세한 내용 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| 페이지 조회수 / 예상되는 고유 방문자 (ITP 2.1) | 예상되는 고유 방문자(ITP 2.1)가 조회한 평균 페이지 수. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
