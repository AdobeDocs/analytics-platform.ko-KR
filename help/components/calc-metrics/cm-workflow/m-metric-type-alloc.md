---
description: 지표 유형 및 속성에 대해 알아봅니다.
title: 지표 유형 및 속성
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 98%

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

            * [속성 모델](#attribution-models)에서 **[!UICONTROL 모델]**&#x200B;을 선택합니다.
            * **[!UICONTROL 컨테이너]** 옵션에서 [컨테이너](#container)를 선택합니다.
            * **[!UICONTROL 전환 확인 기간]** 옵션에서 [전환 확인 기간](#lookback-window)을 선택합니다. **[!UICONTROL 사용자 정의 시간]**&#x200B;을 선택하면 **[!UICONTROL 분]** 단위에서 최대 **[!UICONTROL 분기]** 단위로 기간을 정의할 수 있습니다.

      1. 비기본 속성 모델을 적용하려면 **[!UICONTROL 적용]**&#x200B;을 선택합니다. 취소하려면 취소를 선택합니다.

     비기본 속성 모델을 이미 정의한 경우 **[!UICONTROL 편집]**&#x200B;을 선택해 선택 항목을 수정합니다.

속성 모델, 컨테이너와 전환 확인 기간 사용에 대한 예시는 [예제](#example)에서 확인하십시오.


## 속성 모델 {#attribution-models}

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


## 컨테이너 {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="컨테이너"
>abstract="원하는 기여도 범위를 설정하려면 컨테이너를 선택하십시오."

{{attribution-container}}


## 전환 확인 기간 {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="전환 확인 기간"
>abstract="이 설정은 각 변환에 적용될 데이터 속성의 기간을 결정합니다."

{{attribution-lookback-window}}




## 예

{{attribution-example}}

>[!MORELIKETHIS]
>
>[속성 구성 요소 설정](/help/data-views/component-settings/attribution.md)
>>[참여도 지표](participation-metric.md)
>

