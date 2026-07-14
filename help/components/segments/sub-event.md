---
title: 하위 이벤트 분석
description: 하위 이벤트 분석을 통해 고객 여정 분석에서 이벤트 내의 개별 제품 또는 다른 컨테이너를 필터링하여 제품 보고서에서 속성 출혈을 제거하는 방법에 대해 알아봅니다.
feature: Segmentation
hold: true
hide: true
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: c504a631398d14479c9a2b70d9ef43ac88e35704
workflow-type: tm+mt
source-wordcount: 565
ht-degree: 0%

---

# 하위 이벤트 분석

{{release-limited-testing}}

하위 이벤트 분석을 사용하면 이벤트 수준보다 더 세분화된 수준에서 이벤트 데이터를 분석할 수 있습니다. 전체 이벤트를 필터링하는 대신 이벤트 내의 개별 컨테이너에서 세그먼트화할 수 있습니다. 예:

- 동일한 순서로 구입한 다른 모든 제품을 포함하지 않고 특정 제품 카테고리로 세그먼트화
- 콘텐츠 분석 데이터 내의 특정 에셋 카테고리에 대해 세그먼트화하고 있습니까?
- Media Analytics 데이터 내의 특정 미디어 채널에서 세그먼트화합니다.


Customer Journey Analytics에서는 하위 이벤트 분석을 사용할 컨테이너를 데이터 보기 내에 정의합니다. 하위 이벤트 분석이 없으면 컨테이너 항목 속성에 대해 세그먼트화하면 이벤트 내의 모든 항목이 컨테이너 항목 속성과 일치하는 모든 이벤트가 반환됩니다. 그 결과가 잘못된 속성 및 부풀려진 매출 지표입니다. 하위 이벤트 분석에서는 필터를 이벤트 내의 개별 항목 행으로 범위를 지정하고 이러한 문제를 해결합니다.

하위 이벤트 분석에서 제외 논리는 컨테이너에 대한 표준 이벤트 수준 제외와 다르게 동작합니다. 컨테이너 내에서 항목 특성을 제외하면 세그먼트는 컨테이너 내에 **항목이 있지만**&#x200B;제외 기준과 일치하지 않는 이벤트를 반환합니다. 세그먼트는 항목이 없는 이벤트를 반환하지 않습니다.


## 예

전문 소송 범주의 매출액만 측정하려 합니다. 하위 이벤트 분석 없이, 전문 수트에 대한 세그먼트를 적용하면 전문 수트 카테고리가 있는 하나 이상의 제품이 포함된 모든 주문(이벤트)에 대한 모든 제품의 수익이 포함됩니다. 하위 이벤트 분석을 사용하면 필터를 제품 수준으로 확장하고 전문 슈트 카테고리의 제품에 대한 매출만 반환합니다.

또한 Professional Suits 범주를 제외한 다른 모든 범주의 온라인 매출을 측정하려고 합니다.

>[!BEGINTABS]

>[!TAB 이벤트 분석]

세그먼테이션 빌더에서 또는 **[!UICONTROL 빠른 세그먼트]**&#x200B;의 일부로 **[!UICONTROL 이벤트]** 컨테이너에 **[!UICONTROL Dimension]** **[!UICONTROL 제품 범주]** **[!UICONTROL 같음]** **[!UICONTROL 전문 수트]**&#x200B;를 **[!UICONTROL 포함]**&#x200B;하도록 지정합니다.

![제품 범주 전문가 모임에 대한 이벤트 수준의 세분화를 보여 주는 패널](./assets/product-category-segmentation-events.png)

따라서 최소 하나 이상의 **[!UICONTROL 전문 수트]** **[!UICONTROL product_category]**&#x200B;가 포함된 모든 주문이 고려되며, 이러한 주문의 다른 제품 매출은 **[!UICONTROL 매출]** 지표에 포함됩니다.카테고리에 대해 보고할 때, **[!UICONTROL 전문 수트]** **[!UICONTROL product_category]**&#x200B;와 함께 제품을 포함하는 주문의 일부인 **[!UICONTROL product_category]**&#x200B;의 다른 모든 값이 보고됩니다.

>[!TAB 하위 이벤트 분석]

세그먼테이션 빌더에서 또는 **[!UICONTROL 빠른 세그먼트]**&#x200B;의 일부로 **[!UICONTROL 제품]** 컨테이너에 **[!UICONTROL Dimension]** **[!UICONTROL 제품 범주]** **[!UICONTROL 같음]** **[!UICONTROL 전문 수트]**&#x200B;를 **[!UICONTROL 포함]**&#x200B;하도록 지정합니다.

![제품 범주 전문가 모임에 대한 하위 이벤트 수준의 세분화를 보여 주는 패널](./assets/product-category-segmentation-subevents.png)

따라서 최소 **[!UICONTROL 전문 수트]** **[!UICONTROL product_category]**&#x200B;가 포함된 모든 주문이 고려되며, **[!UICONTROL 전문 수트]** **[!UICONTROL product_category]**&#x200B;에 속하는 제품의 매출만 **[!UICONTROL 매출]** 지표에 포함됩니다.범주를 보고할 때 **[!UICONTROL 전문 수트]** **[!UICONTROL Rproduct_category]**&#x200B;만 보고됩니다.

>[!TAB 하위 이벤트 분석(제외)]

세그먼테이션 빌더에서 또는 **[!UICONTROL 빠른 세그먼트]**&#x200B;의 일부로 **[!UICONTROL 제품]** 컨테이너에 **[!UICONTROL Dimension]** **[!UICONTROL 제품 범주]** **[!UICONTROL 같음]** **[!UICONTROL 전문 수트]**&#x200B;를 **[!UICONTROL 제외]**&#x200B;하도록 지정합니다.

![제품 범주 남성을 제외하기 위한 하위 히트 수준의 세그먼테이션을 보여 주는 패널](./assets/product-category-segmentation-subevents-exclude.png)

제품 수준에서 제외하려면 하나 이상의 제품이 포함된 이벤트를 포함한 다음 하위 이벤트 수준의 제외가 해당 범위 내에서 적용됩니다. 이 제외는 전체 이벤트를 제외하는 이벤트 수준 제외와 다릅니다.

>[!ENDTABS]


<!-- 

AI generated content

title: Sub-Event Analysis in Customer Journey Analytics
description: Learn how to analyze data below the event level in Customer Journey Analytics using sub-event containers to segment individual items within event arrays.
feature: Filters, Segments
role: User, Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: e5aeaef3-57b4-4cce-b025-6dea43f9e14b
    internal-label: Admin
---

# Sub-event analysis

Sub-event analysis lets you segment and analyze data at a level below the individual event — for example, a specific product within a product list, or a single item within an array field. Without this capability, all data in arrays is automatically lifted to the event level, which causes attribution bleed, inflated counts, and inaccurate metrics.

**Example:** A customer purchases three items in a single order. Without sub-event analysis, a segment for *red shoes* would match the entire event, pulling in all three products. With sub-event analysis, the segment evaluates each item in the product list individually, returning only the red shoes row.

Sub-event analysis is built on *sub-event containers* — containers that an administrator configures in the data view. Once configured, these containers are available for use in the Segment builder and in certain visualizations.

## Configure sub-event containers (administrators)

Administrators configure sub-event containers from the **[!UICONTROL Containers]** tab in the data view builder. This tab appears before the **[!UICONTROL Components]** tab.

### System containers and custom containers

The **[!UICONTROL Containers]** tab has two sections:

| Section | Description |
|---|---|
| **[!UICONTROL System]** | The standard Person, Session, and Event containers. Administrators can rename a system container's display name but cannot otherwise modify it. |
| **[!UICONTROL Custom]** | Schema-based or component-based containers that you create from your data view's schema fields. These represent the sub-event level of your data — for example, `productListItems` in an e-commerce schema. |

The **[!UICONTROL Container type]** column shows whether each custom container is **[!UICONTROL Schema-based]** or **[!UICONTROL Component-based]**. Component-based containers only appear after you add the corresponding dimension or metric to the data view.

### Curate a container

Custom containers must be curated before they are available in the Segment builder. Curating a container is an explicit opt-in: only curated containers are valid for use in segments.

To curate a custom container, select the container in the **[!UICONTROL Custom]** table and enable it for segmentation.

>[!NOTE]
>
>A maximum of 100 custom containers can be curated per data view, across all Customer Journey Analytics SKUs. This limit may change in the future. Any auto-generated occurrence metrics from curated containers count toward the 5,000 component limit per data view.

### Container display names

The container's internal name is immutable after creation. Only the display name is editable. You can also add context labels and hide a container from reporting without removing it.

## Use sub-event containers in segments

Once an administrator has curated at least one sub-event container, it is available in the Segment builder as a new container option alongside Person, Session, and Event.

### Container auto-inference

When you drag a dimension that belongs to a sub-event container (for example, `productID`) into the Segment builder canvas, the builder automatically selects the most granular applicable sub-event container rather than defaulting to the Event container. This means the segment evaluates at the sub-event level without any additional configuration.

>[!NOTE]
>
>Container auto-inference applies when the dimension is exclusively part of one sub-event container. If a dimension appears in multiple containers, you must select the container manually.

### Mixed containers

When you add dimensions or metrics from different sub-event containers in a single segment rule, the builder uses the highest (least granular) container that covers all components. If all components share the same sub-event container, that shared container is used.

### Exclude logic

Exclusion at the sub-event level works differently from event-level exclusion. To exclude a specific sub-event condition, the system first includes events that contain a matching sub-event, then applies the exclusion within those events. This means the segment identifies *events that have the sub-event* and then removes the matching sub-event rows — rather than excluding all events where the sub-event does not exist.

This behavior is intentional but counterintuitive. Use explicit **[!UICONTROL Include]** and **[!UICONTROL Exclude]** containers when building sub-event exclusion logic to make the intent clear.

### Filter by container in the left rail

The Segment builder left rail includes a new option to filter the component list by container. Selecting a container shows only the dimensions and metrics that belong to that container, making it easier to build focused sub-event segment conditions.

This container filter is available in the Segment builder only. It is not currently available in other left rail panels.

## Auto-generated occurrence metrics

When an administrator curates a sub-event container, an **Occurrences** metric is automatically generated for that container. This metric counts the number of sub-event rows that match the container and appears in the left rail as a selectable metric when building segments.

These auto-generated metrics behave like the standard Person, Session, and Event count metrics:

- They cannot be duplicated or structurally modified.
- You can rename them, add context labels, and hide them from reporting.
- If you rename the curated container, the auto-generated metric name updates automatically — unless you have already manually renamed the metric.

## Histogram visualization

The Histogram is the only visualization that requires you to select a sub-event container explicitly. A container drop-down menu appears in the Histogram panel when sub-event containers are available in the data view, allowing you to scope the distribution to a specific container level.

No other panels or visualizations require changes to support sub-event containers.

-->
