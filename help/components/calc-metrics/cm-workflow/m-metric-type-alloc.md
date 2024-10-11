---
description: 지표 유형 및 속성에 대해 알아보기
title: 지표 유형 및 속성
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 39%

---

# 지표 유형 및 속성

계산된 지표 정의에서 지표에 대한 지표 유형 및 [속성 모델](#attribution-models)을(를) 구성할 수 있습니다.

1. 지표 구성 요소에서 ![설정](/help/assets/icons/Setting.svg)을 선택합니다.
1. 팝업 대화 상자에서:

   ![지표 유형 및 속성](assets/cm-type-alloc.png)

   * **[!UICONTROL 지표 유형]** 지정:

     | 지표 유형 | 정의 |
     |---|---|
     | **[!UICONTROL 표준]** | 공식이 단일 표준 지표로 구성된 경우 계산되지 않은 해당 지표와 동일한 데이터가 표시됩니다. 표준 지표는 각 개별 라인 항목에 고유한 계산된 지표를 만드는 데 유용합니다. <p>예를 들어, ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 주문]** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 세션]**&#x200B;은(는) 특정 라인 항목에 대한 주문을 가져와서 특정 라인 항목에 대한 세션 수로 나눕니다. |
     | **[!UICONTROL 총]** | 모든 라인 항목에서 보고 기간에 **[!UICONTROL 총계]**&#x200B;를 사용합니다. 공식이 단일 총계 지표로 구성된 경우 계산된 지표는 모든 라인 항목에 동일한 총계 수를 표시합니다. 총계 지표는 총계 데이터와 비교하는 계산된 지표를 만들려는 경우에 유용합니다. <p>예를 들어 ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 주문]** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 총 세션]**&#x200B;은 특정 라인 항목에 대한 세션뿐만 아니라 모든 세션에 대한 주문 비율을 표시합니다. 이 예에서는 계산된 지표에서 ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 세션]** 지표에 대해 **[!UICONTROL 총계]**&#x200B;를 지정합니다. 그러면 자동으로 ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 총 세션]**(으)로 바뀝니다. |

   * **[!UICONTROL 속성]**&#x200B;을 지정하십시오.

      1. 다음 중 하나를 수행할 수 있습니다.

         * 전환 확인 기간이 30일인 기본 열 속성 모델(마지막 터치)을 사용하려면 **[!UICONTROL 기본값이 아닌 속성 모델을 사용]**&#x200B;하십시오.
         * **[!UICONTROL 기본이 아닌 속성 모델 사용]**&#x200B;을 사용하도록 설정합니다. **[!UICONTROL 열 속성 모델]** 대화 상자에서

            * 속성 모델에서 **[!UICONTROL 모델]**&#x200B;을(를) 선택합니다.
            * **[!UICONTROL 전환 확인 기간]**&#x200B;을 선택하세요. **[!UICONTROL 사용자 지정 시간]**&#x200B;을(를) 선택하는 경우 최대 **[!UICONTROL 분기]**&#x200B;까지 **[!UICONTROL 분]**&#x200B;으로 기간을 정의할 수 있습니다. 자세한 내용은 [전환 확인 기간](#lookback-window)을 참조하세요.

      1. 기본이 아닌 속성 모델을 적용하려면 **[!UICONTROL 적용]**&#x200B;을 선택하십시오. 취소하려면 취소 를 선택합니다.

     기본값이 아닌 속성 모델을 이미 정의한 경우 **[!UICONTROL 편집]**&#x200B;을 선택하여 선택 사항을 수정합니다.

속성 모델 및 전환 확인 기간을 사용하는 방법에 대한 예는 [예](#example)를 참조하십시오.


## 속성 {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_nondefaultattributionmodel"
>title="비기본 속성 모델 사용"
>abstract="선택한 지표에 기본이 아닌 속성 모델을 사용합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attributionmodel"
>title="모델"
>abstract="지표에 대한 속성 모델을 선택합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_lasttouch"
>title="마지막 터치"
>abstract="100%의 크레딧이 방문자가 본 마지막 차원 값으로 이동합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_firsttouch"
>title="첫 번째 터치"
>abstract="100%의 크레딧이 방문자가 본 첫 번째 차원 값으로 이동합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_linear"
>title="선형"
>abstract="크레딧이 모든 차원 값에 고르게 분산됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_participation"
>title="기여도"
>abstract="100%의 크레딧이 방문자가 본 모든 차원 값으로 이동합니다<br/>열 합계가 과대 평가됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_sametouch"
>title="동일한 터치"
>abstract="전환과 동일한 이벤트에 발생하는 차원 값에만 크레딧이 제공됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_ushaped"
>title="U자형"
>abstract="첫 번째 차원 값이 40%의 크레딧, 마지막 차원 값이 40%의 크레딧을 차지하고 나머지 20%의 크레딧은 중간 차원 값에서 공유합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_jcurve"
>title="J 곡선"
>abstract="마지막 차원 값이 60%의 크레딧, 첫 번째 차원 값이 20%의 크레딧을 차지하고 나머지 20%의 크레딧은 중간 차원 값에서 공유합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_inversej"
>title="J의 역"
>abstract="첫 번째 차원 값이 60%의 크레딧, 마지막 차원 값이 20%의 크레딧을 차지하고 나머지 20%의 크레딧은 중간 차원 값에서 공유합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_timedecay"
>title="시간 감소"
>abstract="시간적으로 변환에 가장 가까운 차원 값에 가장 많은 크레딧이 제공됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_custom"
>title="사용자 정의"
>abstract="고유한 위치 기반 속성 가중치를 정의합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_algorithmic"
>title="알고리즘"
>abstract="크레딧은 통계적 알고리즘에 따라 동적으로 결정합니다."

<!-- markdownlint-enable MD034 -->


{{attribution-models-details}}


### 전환 확인 기간 {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_lookbackwindow"
>title="전환 확인 기간"
>abstract="이 설정은 각 변환에 적용될 데이터 속성의 기간을 결정합니다."

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### 속성 예 {#attribution-example}

다음 예를 생각해 보십시오.

1. 9월 15일, 한 사람이 유료 검색 광고를 통해 여러분의 사이트에 도착했다가 나갑니다.
1. 9월 18일, 해당 사용자는 친구로부터 받은 소셜 미디어 링크를 통해 다시 귀하의 사이트에 도착합니다. 장바구니에 몇 개 항목을 추가하지만 구입하지는 않습니다.
1. 9월 24일 마케팅 팀이 장바구니에 있는 일부 항목에 대한 쿠폰이 포함된 이메일을 보냅니다. 쿠폰은 적용하지만 다른 쿠폰이 있는지 확인하기 위해 다른 몇 개 사이트를 방문합니다. 디스플레이 광고를 통해 다른 항목을 찾은 다음 최종적으로 $50에 구매합니다.

전환 확인 기간과 속성 모델에 따라 채널은 서로 다른 크레딧을 받습니다. 다음은 몇 가지 예입니다.

* **첫 번째 터치**&#x200B;와 **세션 전환 확인 기간**&#x200B;을 사용하는 속성은 세 번째 방문만 봅니다. 이메일과 디스플레이 사이에 이메일이 첫 번째였으며, 따라서 $50 구매에 대해 이메일이 100% 크레딧을 받습니다.

* **첫 번째 터치**&#x200B;와 **개인 전환 확인 기간**&#x200B;을 사용하는 기여도 분석은 세 번의 방문을 모두 봅니다. 유료 검색이 첫 번째였으며, 따라서 $50 구매에 대해 유료 검색이 100% 크레딧을 받습니다.

* **선형** 및 **세션 전환 확인 기간**을 사용하면 크레딧이 전자 메일과 디스플레이 간에 나눠집니다. 이 두 채널 모두 각각 $25 크레딧을 받습니다.
**선형** 및 **개인 전환 확인 기간**&#x200B;을 사용하면 크레딧이 유료 검색, 소셜, 전자 메일 및 디스플레이 간에 나눠집니다. 각 채널은 이 구매에 대해 $12.50 크레딧을 받습니다.

* **J자형**&#x200B;과(와) **개인 전환 확인 기간**&#x200B;을(를) 사용하는 경우 크레딧은 유료 검색, 소셜, 이메일 및 디스플레이 간에 나눠집니다.

   * $30인 60% 크레딧이 디스플레이에 제공됩니다.
   * $10인 20% 크레딧이 유료 검색에 제공됩니다.
   * 나머지 20%는 소셜과 이메일 간에 나누어져 각각 5달러가 제공됩니다.

* **시간 감소**&#x200B;와 **개인 전환 확인 기간**&#x200B;을 사용하는 경우 크레딧은 유료 검색, 소셜, 이메일 및 디스플레이 간에 나눠집니다. 다음과 같이 기본 7일 반감기를 사용합니다.

   * 디스플레이 터치 포인트와 전환 간 0일 간격. `2^(-0/7) = 1`
   * 이메일 터치 포인트와 전환 간 0일 간격. `2^(-0/7) = 1`
   * 소셜 터치 포인트와 전환 간 6일 간격. `2^(-6/7) = 0.552`
   * 유료 검색 터치 포인트와 전환 간 9일 간격. `2^(-9/7) = 0.41`
   * 이러한 값을 표준화하면 다음과 같은 결과가 나옵니다.

      * 디스플레이: 33.8%, $16.88 받음
      * 이메일: 33.8%, $16.88 받음
      * 소셜: 18.6%, $9.32 받음
      * 유료 검색: 13.8%, $6.92 받음

일반적으로 정수가 있는 전환 이벤트는 크레딧이 둘 이상의 채널에 속하는 경우 나누어집니다. 예를 들어 두 채널이 선형 기여도 분석 모델을 사용하여 주문에 기여하는 경우 두 채널 모두 해당 주문의 0.5를 받습니다. 이러한 부분 지표는 모든 사람에 대해 집계한 후 보고를 위해 가장 가까운 정수로 반올림됩니다.


>[!MORELIKETHIS]
>
>[속성 구성 요소 설정](/help/data-views/component-settings/attribution.md)
>[기여도 지표](participation-metric.md)
>

