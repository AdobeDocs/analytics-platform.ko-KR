---
description: 지표 유형 및 속성에 대해 알아보기
title: 지표 유형 및 속성
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 2d182004b12eb44f54ec9b4b5f63cb9072594aec
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 100%

---

# 지표 유형 및 속성

계산된 지표 정의에서 지표의 지표 유형과 [속성 모델](#attribution-models)을 구성할 수 있습니다.

1. 지표 구성 요소에서 ![설정](/help/assets/icons/Setting.svg)을 선택합니다.
1. 팝업 대화 상자에서:

   ![지표 유형 및 속성](assets/cm-type-alloc.png)

   * **[!UICONTROL 지표 유형]**&#x200B;을 지정합니다.

     | 지표 유형 | 정의 |
     |---|---|
     | **[!UICONTROL 표준]** | 공식이 하나의 표준 지표로 구성된 경우 계산되지 않은 지표에 해당하는 대응값과 동일한 데이터가 표시됩니다. 표준 지표는 각 개별 라인 항목별로 계산된 지표를 만드는 데 유용합니다. <p>예를 들어 ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 주문]** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 세션]**&#x200B;은 특정 라인 항목에 대한 주문을 가져와 해당 특정 라인 항목의 세션 수로 나눕니다. |
     | **[!UICONTROL 총 합계]** | 각 라인 항목에 있는 보고 기간에 대한 **[!UICONTROL 총 합계]**&#x200B;를 사용합니다. 수식에 단일 총 합계 지표가 포함된 경우 계산된 지표는 모든 라인 항목에 동일한 총 합계를 표시합니다. 총 합계 지표는 사이트 합계 데이터를 기준으로 비교하는 계산된 지표를 만들고자 할 때 유용합니다. <p>예를 들어 ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 주문]** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 총 세션]**&#x200B;은 특정 라인 항목에 대한 세션뿐만 아니라 모든 세션에 대한 주문 비율을 보여 줍니다. 이 예에서 계산된 지표의 ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 세션 지표]**&#x200B;에 대한 **[!UICONTROL 총 합계]**&#x200B;를 지정하면 자동으로 ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 총 세션]**&#x200B;으로 변환됩니다. |

   * **[!UICONTROL 속성]**&#x200B;을 지정합니다.

      1. 다음과 같은 작업을 수행할 수 있습니다.

         * **[!UICONTROL 비기본 속성 모델 사용]**&#x200B;을 비활성화하여 30일의 전환 확인 기간이 있는 마지막 터치의 기본 열 속성 모델을 사용합니다.
         * **[!UICONTROL 비기본 속성 모델 사용]**&#x200B;을 활성화합니다. **[!UICONTROL 열 속성 모델]** 대화 상자에서

            * 속성 모델에서 **[!UICONTROL 모델]**&#x200B;을 선택합니다.
            * **[!UICONTROL 전환 확인 기간]**&#x200B;을 선택합니다. **[!UICONTROL 사용자 정의 시간]**&#x200B;을 선택하면 **[!UICONTROL 분]** 단위에서 최대 **[!UICONTROL 분기]** 단위로 기간을 정의할 수 있습니다. 자세한 내용은 [전환 확인 기간](#lookback-window)을 참조하십시오.

      1. 비기본 속성 모델을 적용하려면 **[!UICONTROL 적용]**&#x200B;을 선택합니다. 취소하려면 취소를 선택합니다.

     비기본 속성 모델을 이미 정의한 경우 **[!UICONTROL 편집]**&#x200B;을 선택해 선택 항목을 수정합니다.

속성 모델과 전환 확인 기간 사용에 대한 예시는 [예제](#example)에서 확인하십시오.


## 속성 {#attribution}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="비기본 속성 모델 사용"
>abstract="선택한 지표에 기본이 아닌 속성 모델을 사용합니다."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="모델"
>abstract="지표에 대한 속성 모델을 선택합니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="마지막 터치"
>abstract="100%의 크레딧이 방문자가 본 마지막 차원 값으로 이동합니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="첫 번째 터치"
>abstract="100%의 크레딧이 방문자가 본 첫 번째 차원 값으로 이동합니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="선형"
>abstract="크레딧이 모든 차원 값에 고르게 분산됩니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="기여도"
>abstract="100%의 크레딧이 방문자가 본 모든 차원 값으로 이동합니다<br/>열 합계가 과대 평가됩니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="동일한 터치"
>abstract="전환과 동일한 이벤트에 발생하는 차원 값에만 크레딧이 제공됩니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="동일한 터치"
>abstract="전환과 동일한 이벤트에 발생하는 차원 값에만 크레딧이 제공됩니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U자형"
>abstract="첫 번째 차원 값이 40%의 크레딧, 마지막 차원 값이 40%의 크레딧을 차지하고 나머지 20%의 크레딧은 중간 차원 값에서 공유합니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J 곡선"
>abstract="마지막 차원 값이 60%의 크레딧, 첫 번째 차원 값이 20%의 크레딧을 차지하고 나머지 20%의 크레딧은 중간 차원 값에서 공유합니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J 곡선"
>abstract="마지막 차원 값이 60%의 크레딧, 첫 번째 차원 값이 20%의 크레딧을 차지하고 나머지 20%의 크레딧은 중간 차원 값에서 공유합니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="J의 역"
>abstract="첫 번째 차원 값이 60%의 크레딧, 마지막 차원 값이 20%의 크레딧을 차지하고 나머지 20%의 크레딧은 중간 차원 값에서 공유합니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="J의 역"
>abstract="첫 번째 차원 값이 60%의 크레딧, 마지막 차원 값이 20%의 크레딧을 차지하고 나머지 20%의 크레딧은 중간 차원 값에서 공유합니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="시간 감소"
>abstract="시간적으로 변환에 가장 가까운 차원 값에 가장 많은 크레딧이 제공됩니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="사용자 정의"
>abstract="고유한 위치 기반 속성 가중치를 정의합니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="사용자 정의"
>abstract="고유한 위치 기반 속성 가중치를 정의합니다."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="알고리즘"
>abstract="크레딧은 통계적 알고리즘에 따라 동적으로 결정합니다."



{{attribution-models-details}}


### 전환 확인 기간 {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="전환 확인 기간"
>abstract="이 설정은 각 변환에 적용될 데이터 속성의 기간을 결정합니다."

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### 속성 예제 {#attribution-example}

다음 예를 생각해 보십시오.

1. 9월 15일 방문자가 유료 검색 광고를 통해 사이트에 방문했다가 나갑니다.
1. 9월 18일 이 방문자가 친구로부터 받은 소셜 미디어 링크를 통해 다시 사이트에 방문합니다. 장바구니에 몇 개 항목을 추가하지만 구입하지는 않습니다.
1. 9월 24일 마케팅 팀이 장바구니에 있는 일부 항목에 대한 쿠폰이 포함된 이메일을 보냅니다. 쿠폰은 적용하지만 다른 쿠폰이 있는지 확인하기 위해 다른 몇 개 사이트를 방문합니다. 디스플레이 광고를 통해 다른 항목을 찾은 다음 최종적으로 $50에 구매합니다.

전환 확인 기간과 속성 모델에 따라 채널은 서로 다른 크레딧을 받습니다. 다음의 몇 가지 예를 살펴보겠습니다.

* **첫 번째 터치**&#x200B;와 **세션 전환 확인 기간**&#x200B;을 사용하는 속성은 세 번째 방문만 봅니다. 이메일과 디스플레이 사이에 이메일이 첫 번째였으며, 따라서 $50 구매에 대해 이메일이 100% 크레딧을 받습니다.

* **첫 번째 터치**&#x200B;와 **개인 전환 확인 기간**&#x200B;을 사용하는 속성은 세 번째 방문만 봅니다. 유료 검색이 첫 번째였으며, 따라서 $50 구매에 대해 유료 검색이 100% 크레딧을 받습니다.

* **선형**&#x200B;과 **세션 전환 확인 기간**을 사용하는 경우 크레딧이 이메일과 디스플레이 간에 나눠집니다. 이 두 채널 모두 각각 $25의 크레딧을 받습니다.
**선형**&#x200B;과 **개인 전환 확인 기간**&#x200B;을 사용하는 경우 크레딧은 유료 검색, 소셜, 이메일 및 디스플레이 간에 나눠집니다. 각 채널은 이 구매에 대해 $12.50 크레딧을 받습니다.

* **J자형**&#x200B;과 **개인 전환 확인 기간**&#x200B;을 사용하는 경우 크레딧은 유료 검색, 소셜, 이메일 및 디스플레이 간에 나눠집니다.

   * $30인 60% 크레딧이 디스플레이에 제공됩니다.
   * $10인 20% 크레딧이 유료 검색에 제공됩니다.
   * 나머지 20%는 소셜과 이메일 간에 나누어져 각각 $5가 제공됩니다.

* **시간 가치 하락**&#x200B;과 **개인 전환 확인 기간**&#x200B;을 사용하는 경우 크레딧은 유료 검색, 소셜, 이메일 및 디스플레이 간에 나눠집니다. 다음과 같이 기본 7일 반감기를 사용합니다.

   * 디스플레이 접점과 전환 간 0일 간격. `2^(-0/7) = 1`
   * 이메일 접점과 전환 간 0일 간격. `2^(-0/7) = 1`
   * 소셜 접점과 전환 간 6일 간격. `2^(-6/7) = 0.552`
   * 유료 검색 접점과 전환 간 9일 간격. `2^(-9/7) = 0.41`
   * 이러한 값을 표준화하면 다음과 같은 결과가 나옵니다.

      * 디스플레이: 33.8%, $16.88 받음
      * 이메일: 33.8%, $16.88 받음
      * 소셜: 18.6%, $9.32 받음
      * 유료 검색: 13.8%, $6.92 받음

크레딧이 여러 채널에 속하는 경우 일반적으로 정수가 있는 전환 이벤트는 분할됩니다. 예를 들어 두 채널이 선형 속성 모델을 사용하여 주문에 기여하는 경우 두 채널 모두 해당 주문의 0.5를 받습니다. 이러한 부분 지표는 모든 개인에게 집계된 다음 보고를 위해 가장 가까운 정수로 반올림됩니다.


>[!MORELIKETHIS]
>
>[속성 구성 요소 설정](/help/data-views/component-settings/attribution.md)
>[참여도 지표](participation-metric.md)
>

