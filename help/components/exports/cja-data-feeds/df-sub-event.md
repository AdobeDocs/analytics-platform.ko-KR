---
title: 데이터 피드의 하위 이벤트 및 개체 배열 이해
description: Customer Journey Analytics 데이터 피드가 스키마 배열에서 하위 이벤트를 내보내고 Workspace처럼 병합하지 않고 계층 구조를 유지하는 방법에 대해 알아봅니다.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: a4fdb1f8d49b42b6de21881e0c8392995124c1ea
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 2%
---
# 데이터 피드의 하위 이벤트

{{release-limited-testing}}

Customer Journey Analytics의 [하위 이벤트](/help/components/segments/sub-event.md)를 사용하면 이벤트 수준보다 더 세분화된 수준에서 이벤트 데이터를 분석할 수 있습니다.

Customer Journey Analytics 데이터 피드의 하위 이벤트로 작업하는 방법을 이해하려면 다음 정보를 사용하십시오.

## 하위 이벤트 이해

### XDM 스키마의 하위 이벤트

XDM 스키마에서 배열의 각 요소(문자열 배열 또는 개체 배열)는 하위 이벤트입니다.

Adobe Experience Platform의 XDM 스키마 내에서 하위 이벤트가 있는 이벤트를 보려면 [!UICONTROL **스키마**]&#x200B;를 선택한 다음 하위 이벤트가 포함된 이벤트를 확장합니다.

다음 예제에서 `Product list items`은(는) 다양한 하위 이벤트를 포함하는 개체 배열입니다.

개체 배열 및 하위 이벤트가 포함된 ![XDM 스키마](assets/df-sub-event-schema.png)

### 하위 이벤트 예: 구매 이벤트의 제품

고객이 무선 드릴 1개와 드릴 배터리 팩 2개를 한 번에 주문하여 두 제품을 구입합니다. 구현이 `productListItems` 개체 배열의 두 제품을 모두 포함하는 단일 구매 이벤트를 보냅니다.

```json
{
  "eventType": "commerce.purchases",
  "timestamp": "2026-09-16T14:32:07.512Z",
  "commerce": {
    "purchases": { "value": 1 }
  },
  "productListItems": [
    { "SKU": "CD-2000", "name": "Cordless Drill", "quantity": 1, "priceTotal": 129.99 },
    { "SKU": "BP-2000", "name": "Drill Battery Pack", "quantity": 2, "priceTotal": 39.98 }
  ]
}
```

이 이벤트에는 `productListItems` 배열의 각 개체에 대해 하나씩 두 개의 하위 이벤트가 포함되어 있습니다. 다음 표는 이벤트에 속하는 필드와 해당 하위 이벤트에 속하는 필드를 보여줍니다.

| 레벨 | 필드 | 필드에 설명된 내용 |
| --- | --- | --- |
| **이벤트** | `eventType`, `timestamp`, `commerce.purchases.value` | 전체로서의 구매. 각 필드에는 이벤트에 대해 하나의 값이 있습니다. **주문** 지표는 포함된 제품의 수에 관계없이 이 이벤트에 대해 `1`을(를) 계산합니다. |
| **하위 이벤트** | 각 `productListItems` 개체의 `SKU`, `name`, `quantity`, `priceTotal` | 구매의 개별 제품. 각 필드에는 제품당 하나의 값이 있습니다. 예를 들어, 무선 드릴의 경우 `quantity`이(가) `1`이고, 드릴 배터리 팩의 경우 `2`입니다. |

{style="table-layout:auto"}

>[!NOTE]
>
>하위 이벤트에는 이벤트와 함께 전송된 데이터만 포함됩니다. Customer Journey Analytics은 장바구니 추가 또는 체크아웃과 같은 이전 이벤트에서 장바구니 콘텐츠를 재구성하지 않습니다. 제품을 구매 이벤트의 하위 이벤트로 표시하려면 구현에서 해당 구매 이벤트의 `productListItems`에 제품을 포함해야 합니다.

## 데이터 피드에 하위 이벤트 데이터 추가

데이터 피드를 작성하는 동안 하위 이벤트인 열을 추가하려고 하면 피어 하위 이벤트를 추가하라는 대화 상자가 표시됩니다. 데이터 피드 출력에서 이러한 모든 이벤트는 단일 열에 나타납니다.

## 데이터 피드 출력에서 하위 이벤트 데이터 보기

### Analysis Workspace과 데이터 피드 간의 하위 이벤트 차이점

하위 이벤트는 Analysis Workspace과 Customer Journey Analytics의 데이터 피드 간에 다르게 표시됩니다.

| 위치 | 하위 이벤트 표시 방법 |
| --- | --- |
| **Analysis Workspace(Customer Journey Analytics)** | 표시되는 계층과 별도로 개별 구성 요소로 선택할 수 있습니다. |
| **데이터 피드(Customer Journey Analytics)** | 계층이 그대로 있는 그룹으로 표시됩니다. |

### Adobe Analytics과 Customer Journey Analytics의 하위 이벤트 차이점

하위 이벤트 데이터(예: 단일 구매 이벤트의 여러 제품 세부 사항)는 Customer Journey Analytics 데이터 피드와 Adobe Analytics 데이터 피드에 다르게 표시됩니다. 다음 표에서는 각 제품이 하위 이벤트 데이터를 나타내는 방식을 비교합니다.

| 제품 | 데이터 피드에 하위 이벤트 데이터가 표시되는 방법 | 예: 제품 목록 |
| --- | --- | --- |
| **Adobe Analytics** | 단일 열에서 구분된 문자열로 병합되었습니다. | 제품 목록에는 단일 문자열로 그룹화된 여러 제품이 포함되어 있습니다.<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 하위 이벤트는 XDM 스키마에 정의된 계층을 유지합니다. 동일한 열에 그룹화되면 상위 이벤트와 형제 하위 이벤트에 대한 관계형 계층 구조가 표시됩니다. | 제품 목록은 XDM 스키마에 배열로 정의된 계층 구조를 유지합니다.<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### Adobe Analytics과의 차이점

### Adobe Analytics 및 Customer Journey Analytics 데이터 피드 간의 출력 차이

하위 이벤트 데이터(예: 단일 구매 이벤트의 여러 제품 세부 사항)는 Customer Journey Analytics 데이터 피드와 Adobe Analytics 데이터 피드에 다르게 표시됩니다. 다음 표에서는 각 제품이 하위 이벤트 데이터를 나타내는 방식을 비교합니다.

| 제품 | 데이터 피드에 하위 이벤트 데이터가 표시되는 방법 | 예: 제품 목록 |
| --- | --- | --- |
| **Adobe Analytics** | 단일 열에서 구분된 문자열로 병합되었습니다. | 제품 목록에는 단일 문자열로 그룹화된 여러 제품이 포함되어 있습니다.<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 하위 이벤트는 XDM 스키마에 정의된 계층을 유지합니다. 동일한 열에 그룹화되면 상위 이벤트와 형제 하위 이벤트에 대한 관계형 계층 구조가 표시됩니다. | 제품 목록은 XDM 스키마에 배열로 정의된 계층 구조를 유지합니다.<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Analysis Workspace과 데이터 피드 출력 간 하위 이벤트의 차이점

하위 이벤트는 Analysis Workspace과 Customer Journey Analytics의 데이터 피드 간에 다르게 표시됩니다.

| 위치 | 하위 이벤트 표시 방법 |
| --- | --- |
| **Analysis Workspace** | 표시되는 계층과 별도로 개별 구성 요소로 선택할 수 있습니다. |
| **데이터 피드** | 계층이 그대로 있는 그룹으로 표시됩니다. |


## 데이터 피드 출력에서 하위 이벤트 데이터 보기

하위 이벤트 데이터(예: 단일 구매 이벤트의 여러 제품 세부 사항)는 Customer Journey Analytics 데이터 피드와 Adobe Analytics 데이터 피드에 다르게 표시됩니다. 다음 표에서는 각 제품이 하위 이벤트 데이터를 나타내는 방식을 비교합니다.

| 제품 | 데이터 피드에 하위 이벤트 데이터가 표시되는 방법 | 예: 제품 목록 |
| --- | --- | --- |
| **Adobe Analytics** | 단일 열에서 구분된 문자열로 병합되었습니다. | 제품 목록에는 단일 문자열로 그룹화된 여러 제품이 포함되어 있습니다.<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 하위 이벤트는 XDM 스키마에 정의된 계층을 유지합니다. 동일한 열에 그룹화되면 상위 이벤트와 형제 하위 이벤트에 대한 관계형 계층 구조가 표시됩니다. | 제품 목록은 XDM 스키마에 배열로 정의된 계층 구조를 유지합니다.<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## 데이터 피드 출력의 하위 이벤트 데이터 쿼리

하위 이벤트 데이터 [은(는) Customer Journey Analytics 데이터 피드에서 다르게 표시되므로](#view-sub-event-data-in-data-feed-output)에 사용하는 쿼리와 Adobe Analytics 데이터 피드에 사용하는 쿼리가 다릅니다.

다음 예는 특정 제품을 포함하는 이벤트를 찾는 방법을 보여줍니다. 이 예제에서는 Google BigQuery 구문을 사용합니다. Snowflake 및 Databricks 와 같은 다른 데이터 웨어하우스는 구문 차이가 적은 동일한 접근 방식을 지원합니다.

+++ Customer Journey Analytics 데이터 피드에서 제품 데이터 쿼리

Customer Journey Analytics 데이터 피드에서 동일한 두 제품이 `product_list_items` 열에 개체 배열로 나타납니다. 구분 기호 구문 분석이 필요하지 않습니다.

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill", "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack", "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

쿼리를 작성하는 방법은 이벤트당 하나의 행을 원하는지 아니면 일치하는 제품당 하나의 행을 원하는지에 따라 다릅니다.

**이벤트당 하나의 행 반환**

행 수를 변경하지 않고 이벤트를 필터링하려면 `EXISTS` 하위 쿼리 내에서 `UNNEST`을(를) 사용합니다.

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

이 쿼리는 배열에 일치하는 제품의 수에 관계없이 전체 `product_list_items` 배열이 그대로 유지되는 일치하는 각 이벤트에 대해 하나의 행을 반환합니다.

**일치하는 제품당 하나의 행 반환**

일치하는 각 제품에 대해 하나의 행을 반환하려면 `UNNEST`을(를) 외부 `FROM` 절로 이동하십시오.

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

일치하는 제품이 두 개 이상인 이벤트가 여러 행으로 나타나고 각 행에서 `row_id`과(와) 같은 이벤트 열이 반복됩니다. 제품 수준의 세부 사항이 필요한 경우에만 이 접근 방식을 사용하십시오. 결과에서 이벤트를 계산하려면 행을 계산하는 대신 `COUNT(DISTINCT row_id)`을(를) 사용하십시오.

이 접근 방식은 제품에만 적용되는 것이 아니라 XDM 스키마의 모든 배열 필드에 적용됩니다.

+++

+++ Adobe Analytics 데이터 피드에서 제품 데이터 쿼리

Adobe Analytics 데이터 피드에서 두 제품을 함께 구입한 이벤트가 `product_list` 열에 구분된 단일 문자열로 나타납니다.

```text
Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle
```

무선 드릴을 포함하는 이벤트를 찾으려면 이 문자열을 정규 표현식으로 구문 분석합니다.

```sql
SELECT hitid_high, hitid_low, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

+++






