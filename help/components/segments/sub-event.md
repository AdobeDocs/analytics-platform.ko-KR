---
title: 하위 이벤트 분석
description: 하위 이벤트 분석을 통해 고객 여정 분석에서 이벤트 내의 개별 제품 또는 다른 컨테이너를 필터링하여 제품 보고서에서 속성 출혈을 제거하는 방법에 대해 알아봅니다.
feature: Segmentation
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: 3fcb9c403ace295c1a7e62c21d8bb444a4f9c011
workflow-type: tm+mt
source-wordcount: 636
ht-degree: 9%

---

# 하위 이벤트 분석

{{release-limited-testing}}

하위 이벤트 분석을 사용하면 이벤트 수준보다 더 세분화된 수준에서 이벤트 데이터를 분석할 수 있습니다. 전체 이벤트를 필터링하는 대신 이벤트 내의 개별 컨테이너에서 세그먼트화할 수 있습니다. 예:

* 동일한 순서로 구매한 다른 모든 제품을 포함하지 않고 특정 제품 카테고리로 세그먼트화.
* 콘텐츠 분석 데이터 내의 특정 에셋 카테고리에 대한 세그먼트화.
* Media Analytics 데이터 내의 특정 미디어 채널에서 세그먼트화합니다.

Customer Journey Analytics에서는 하위 이벤트 분석을 사용할 컨테이너를 데이터 보기 내에 정의합니다. 하위 이벤트 분석을 사용하지 않으면 컨테이너 항목 속성에 대한 세그먼트화는 정의한 모든 이벤트, 세션, 사용자, (글로벌) 계정 [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, 구매 그룹 [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, 기회 [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 또는 기타 [컨테이너](/help/data-views/create-dataview.md#containers-1)를 반환합니다. 그 결과가 잘못된 속성 및 부풀려진 매출 지표입니다. 하위 이벤트 분석에서는 필터를 이벤트 내의 개별 컨테이너 행으로 범위를 지정하고 이러한 문제를 해결합니다.

하위 이벤트 분석에서 제외 논리는 컨테이너에 대한 표준 이벤트 수준 제외와 다르게 동작합니다. 컨테이너 내에서 항목 특성을 제외하면 세그먼트는 컨테이너 내에 **항목이 있지만**&#x200B;제외 기준과 일치하지 않는 이벤트를 반환합니다. 세그먼트는 항목이 없는 이벤트를 전혀 반환하지 않습니다.


## 예

전문 소송 범주의 매출액만 측정하려 합니다. 하위 이벤트 분석 없이, 전문 수트에 대한 세그먼트를 적용하면 전문 수트 카테고리가 있는 하나 이상의 제품이 포함된 모든 주문(이벤트)에 대한 모든 제품의 수익이 포함됩니다. 하위 이벤트 분석을 사용하면 필터를 제품 수준으로 확장하고 전문 슈트 카테고리의 제품에 대한 매출만 반환합니다.

또한 Professional Suits 범주를 제외한 다른 모든 범주의 온라인 매출을 측정하려고 합니다.

>[!BEGINTABS]

>[!TAB 이벤트 분석]

세그먼테이션 빌더에서 또는 **[!UICONTROL 빠른 세그먼트]**&#x200B;의 일부로 **[!UICONTROL 이벤트]** 컨테이너에 **[!UICONTROL Dimension]** **[!UICONTROL 제품 범주]** **[!UICONTROL 같음]** **[!UICONTROL 전문 수트]**&#x200B;를 **[!UICONTROL 포함]**&#x200B;하도록 지정합니다.

![제품 범주 전문가 모임에 대한 이벤트 수준의 세분화를 보여 주는 패널](./assets/product-category-segmentation-events.png)

따라서 최소 하나 이상의 **[!UICONTROL 전문 수트]** **[!UICONTROL product_category]**&#x200B;가 포함된 모든 주문이 고려되며, 이러한 주문의 다른 제품 매출은 **[!UICONTROL 매출]** 지표에 포함됩니다.
카테고리에 대해 보고할 때 **[!UICONTROL 전문 수트]** **[!UICONTROL product_category]**&#x200B;와 함께 제품을 포함하는 주문의 일부인 **[!UICONTROL product_category]**&#x200B;의 다른 모든 값이 보고됩니다.

>[!TAB 하위 이벤트 분석]

제품에 대한 하위 이벤트 분석을 위해 데이터 보기에서 **[!UICONTROL 제품 세부 정보]** [사용자 지정 컨테이너](/help/data-views/create-dataview.md#containers)를 정의했습니다.

![제품 세부 정보 컨테이너](assets/product-details-container.png)

세그먼테이션 빌더에서 또는 **[!UICONTROL 빠른 세그먼트]**&#x200B;의 일부로 **[!UICONTROL 제품 세부 정보]** 컨테이너에 **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]**&#x200B;을(를) **[!UICONTROL 포함]**&#x200B;하도록 지정합니다.

![제품 범주 전문가 모임에 대한 하위 이벤트 수준의 세분화를 보여 주는 패널](./assets/product-category-segmentation-subevents.png)

따라서 최소 **[!UICONTROL 전문 수트]** **[!UICONTROL product_category]**&#x200B;가 포함된 모든 주문이 고려되며, **[!UICONTROL 전문 수트]** **[!UICONTROL product_category]**&#x200B;에 속하는 제품의 매출만 **[!UICONTROL 매출]** 지표에 포함됩니다.
범주를 보고할 때 **[!UICONTROL 전문 수트]** **[!UICONTROL product_category]**&#x200B;만 보고됩니다.

>[!TAB 하위 이벤트 분석(제외)]

제품에 대한 하위 이벤트 분석을 위해 데이터 보기에서 **[!UICONTROL 제품 세부 정보]** [사용자 지정 컨테이너](/help/data-views/create-dataview.md#containers)를 정의했습니다.

![제품 세부 정보 컨테이너](assets/product-details-container.png)

세그먼테이션 빌더에서 또는 **[!UICONTROL 빠른 세그먼트]**&#x200B;의 일부로 **[!UICONTROL 제품 세부 정보]** 컨테이너에 **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL equals]** **[!UICONTROL Professional Suits]**&#x200B;을(를) **[!UICONTROL 제외]**&#x200B;하도록 지정합니다.

![제품 범주 남성을 제외하기 위한 하위 히트 수준의 세그먼테이션을 보여 주는 패널](./assets/product-category-segmentation-subevents-exclude.png)

제품 수준에서 제외하려면 하나 이상의 제품이 포함된 이벤트를 포함한 다음 하위 이벤트 수준의 제외가 해당 범위 내에서 적용됩니다. 이 제외는 전체 이벤트를 제외하는 이벤트 수준 제외와 다릅니다.

>[!ENDTABS]
