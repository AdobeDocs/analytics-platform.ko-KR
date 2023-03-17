---
description: Adobe은 사용할 수 있는 다양한 계산된 지표를 제공합니다. 이 페이지에는 이러한 지표와 그 사용 용도가 나열됩니다.
title: 기본 계산된 지표
feature: Calculated Metrics
source-git-commit: 5d6942af4ac3f999c5e7fd7d6ba74a5fe7a26a9d
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 4%

---

# 기본 계산된 지표

Customer Journey Analytics은 가장 일반적인 사용 사례를 처리할 수 있도록 다양한 계산된 지표를 제공합니다. 이러한 계산된 지표는 Analysis Workspace에서 기본적으로 사용할 수 있습니다.

다음은 Adobe에서 제공하는 각 계산된 지표의 목록이며, 해당 의도된 함수와 이를 계산하는 데 사용되는 기본 공식이 포함되어 있습니다.

>[!NOTE]
>
>이 페이지에 설명된 기본 계산된 지표 외에 계산된 지표를 보고서 세트에 추가할 수도 있습니다.
>
>:
> * 에 설명된 대로 스트리밍 미디어에 대한 기본 계산된 지표를 추가합니다. [계산된 지표](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 에 설명된 대로 기존 지표에서 사용자 정의 계산된 지표를 만듭니다. [계산 및 고급 계산(파생) 지표](/help/components/calc-metrics/cm-adv-functions.md).



| 계산된 지표 이름 | 함수 | 공식 |
|---------|----------|---------|
| 바운스 비율 | 해당 페이지의 방문 수와 비교하여 정확히 하나의 히트가 포함된 방문의 비율입니다. 바운스 비율이 가장 높은 차원 항목을 이해하거나 시간에 따른 사이트의 총 바운스 비율 집계를 확인하는 데 도움이 될 수 있습니다. | `[Bounces] / [Entries]` |
| 매출 / 방문자 | 사이트에 대한 각 개별 방문자가 생성한 평균 매출액입니다. | `[Revenue] / [Unique Visitors]` |
| 주문 수/방문자 수 | 사이트에 대한 각 개별 방문자가 생성한 평균 주문 또는 트랜잭션 수 | `[Orders] / [Unique Visitors]` |
| 매출 / 방문 횟수 | 사이트에 대한 단일 방문으로 생성된 평균 매출액입니다. | `[Revenue] / [Visits]` |
| 매출 / 주문 | 사이트에서 완료된 각 거래 또는 주문으로 생성된 평균 매출액. | `[Revenue] / [Orders]` |
| 주문 수/방문 수 | 완료된 트랜잭션을 초래하는 사이트 방문 비율입니다. | `[Orders] / [Visits]` |
| 페이지 조회수/방문 수 | 사용자가 사이트를 한 번 방문하는 동안 보는 평균 페이지 수입니다. | `[Page Views] / [Visits]` |
| 방문 횟수 / 방문자 | 고유 방문자가 사이트를 방문하는 평균 횟수입니다. | `[Visits] / [Unique Visitors]` |
| 다시 로드 / 페이지 보기 | 페이지를 다시 로드하거나 새로 고친 페이지 보기 횟수의 비율입니다. | `[Reloads] / [Page Views]` |
| 가중 바운스 비율 | 함수 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 지원 주문 | 채널 또는 소스가 구매에 대한 고객의 여정에 기여했지만 최종 구매로 이어지지 않은 횟수입니다. | `[Orders (Visit Participation)] - [Orders]` |
| 종료 비율 | 특정 페이지를 본 후 사이트를 나가는 방문자의 비율입니다. | `[Exits] / [Visits]` |
| 시작 비율 | 사이트의 총 세션 수와 비교하여 주어진 페이지에서 사이트에 들어간 방문자의 비율입니다. | `[Entries] / [Visits]` |
| 사이트의 평균 시간 | 방문자가 사이트를 떠나거나 떠나기 전에 사이트에서 보낸 평균 시간입니다. | `[Average Time Spent on Site (Seconds)]` |
| 체류 시간/사용자(상태) | 평균 방문자가 사이트에 있는 동안 특정 상태에서 보내는 시간 | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 사용자(모바일) | 모바일 앱의 총 사용자 수 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 앱 사용자 | 모바일 앱의 총 사용자 수 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 상태 보기 | 앱의 다양한 상태 또는 화면에 대한 보기 수 | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| 작업 | 앱에서 수행한 총 작업 수 | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| 획득 링크 클릭 수 | 사이트로 트래픽을 유도하기 위해 고안된 링크를 사람들이 클릭하는 횟수입니다. | `[Campaign Click-throughs]` |
| 페이지 속도 | 콘텐츠 조각이 생성하는 추가 페이지 보기 수입니다. 이를 통해 추가 참여를 유도하는 콘텐츠를 확인할 수 있습니다. | `[Page Views] / [Visits]` |
| 전환율 | 구매와 같이 원하는 조치를 취한 방문자의 비율입니다. | `[Orders] / [Visits]` |
| 평균 세션 길이(모바일) | 방문자가 단일 세션 동안 사이트에서 보낸 평균 시간입니다. | 빈 |
| Experience Cloud ID 범위 | Experience Cloud ID가 있는 방문자의 비율입니다. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 콘텐츠 속도 | 사이트에서 새 콘텐츠를 만들고 게시하는 속도와 사용자 참여를 생성하는 속도입니다. | `[Page Views] / [Visits]` |
| ITP 2.1 고유 방문자 수 / 고유 방문자 수 | ITP 2.1 쿠키 제한 사항의 영향을 받는 브라우저를 사용하는 고유 방문자의 비율입니다. 즉, 고객이 CNAME 구현을 사용하지 않는 경우입니다. (클라이언트측 JavaScript를 통해 쿠키를 설정하는 고객에게 적용됩니다.) | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| 고유 방문자 수/7일 후 재방문하는 고유 방문자 수 | 7일 이상의 기간이 지난 후 재방문하는 고유 방문자의 비율입니다. | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| 페이지 조회수 / 고유 방문자 | 사이트에 대한 각 고유 방문자에 대해 본 평균 페이지 수입니다. | `[Page Views] / [Unique Visitors]` |
| 방문 횟수 / 방문자 수 | 고유 방문자가 사이트에 대해 수행하는 평균 방문 횟수입니다. | `[Visits] / [Unique Visitors]` |
| 예상 고유 방문자 수(ITP 2.1) | ITP 방문자(Safari 브라우저의 사용자)의 경우 고유 방문자 수를 2 이하로 나눕니다. 이 계산된 지표는 사용자가 클라이언트측 JavaScript를 사용하여 쿠키를 설정했다고 가정합니다(CNAME 구현을 사용하지 않음). 클라이언트측 JavaScript를 사용하여 쿠키를 설정하는 구현은 ITP 2.1부터 영향을 받았습니다. 다음을 참조하십시오 [지능형 추적 방지](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 을 참조하십시오. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| 페이지 보기 수 / 예상 고유 방문자 수(ITP 2.1) | 예상 고유 방문자 수(ITP 2.1)에 대해 본 평균 페이지 수입니다. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}