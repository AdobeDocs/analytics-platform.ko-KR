---
title: 데이터 피드의 배열 및 맵의 하위 컨테이너 구성 요소
description: Customer Journey Analytics 데이터 피드가 배열 및 맵 필드에서 하위 컨테이너 구성 요소를 내보내는 방법과 데이터 웨어하우스에서 쿼리하는 방법에 대해 알아봅니다.
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
source-git-commit: 93107a7cf46e5d71bcb5c588eb7395fd1b88d150
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 1%
---
# 데이터 피드의 하위 컨테이너 구성 요소

{{release-limited-testing}}

하위 컨테이너 구성 요소는 XDM 스키마의 배열 또는 맵 내의 필드를 기반으로 하는 차원 및 지표입니다. 이를 통해 구매의 개별 제품과 같이 이벤트 수준보다 더 세분화된 수준에서 데이터를 분석할 수 있습니다. 세그먼트에서 이 데이터를 사용하는 방법에 대한 자세한 내용은 [하위 이벤트](/help/components/segments/sub-event.md)를 참조하세요.

다음 정보를 사용하여 배열 및 맵 필드의 하위 컨테이너 구성 요소가 Customer Journey Analytics 데이터 피드에 표시되는 방식을 이해합니다.

## 하위 컨테이너 구성 요소 이해

### XDM 스키마의 하위 컨테이너 구성 요소

XDM 스키마에서 배열의 각 요소(문자열 배열 또는 개체 배열)는 하위 컨테이너입니다. [데이터 피드의 필드 매핑](#map-fields-in-data-feeds)에 설명된 대로 맵 필드의 각 항목은 하위 컨테이너이기도 합니다. 하위 컨테이너 내의 필드를 기반으로 하는 차원 및 지표는 하위 컨테이너 구성 요소입니다.

Adobe Experience Platform에서 XDM 스키마 내의 하위 컨테이너를 보려면 [!UICONTROL **스키마**]&#x200B;를 선택한 다음 하위 컨테이너가 포함된 이벤트를 확장합니다.

다음 예제에서 `Product list items`은(는) 다양한 하위 컨테이너 구성 요소를 포함하는 개체 배열입니다.

개체 배열 및 하위 컨테이너 구성 요소가 포함된 ![XDM 스키마](assets/df-sub-event-schema.png)

### Analysis Workspace과 데이터 피드 간의 하위 컨테이너 차이점

하위 컨테이너 구성 요소는 Analysis Workspace과 Customer Journey Analytics의 데이터 피드 간에 다르게 표시됩니다.

| 위치 | 하위 컨테이너 구성 요소 표시 방법 |
| --- | --- |
| **Analysis Workspace(Customer Journey Analytics)** | 표시되는 계층과 별도로 개별 구성 요소로 선택할 수 있습니다. |
| **데이터 피드(Customer Journey Analytics)** | 계층이 그대로 있는 그룹으로 표시됩니다. |

### Adobe Analytics과 Customer Journey Analytics의 하위 컨테이너 차이점

하위 컨테이너 데이터(예: 단일 구매 이벤트의 여러 제품 세부 사항)는 Customer Journey Analytics 데이터 피드와 Adobe Analytics 데이터 피드에 다르게 표시됩니다. 다음 표에서는 각 제품이 하위 컨테이너 데이터를 나타내는 방식을 비교합니다.

| 제품 | 데이터 피드에 하위 컨테이너 데이터가 표시되는 방법 | 예: 제품 목록 |
| --- | --- | --- |
| **Adobe Analytics** | 단일 열에서 구분된 문자열로 병합되었습니다. | 제품 목록에는 단일 문자열로 그룹화된 여러 제품이 포함되어 있습니다.<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 하위 컨테이너 구성 요소는 XDM 스키마에 정의된 계층 구조를 유지합니다. 동일한 열에 그룹화되면 상위 이벤트와 형제 하위 컨테이너에 대한 관계형 계층 구조가 표시됩니다. | 제품 목록은 XDM 스키마에 배열로 정의된 계층 구조를 유지합니다.<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### 하위 컨테이너 예: 구매 이벤트의 제품

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

이 이벤트에는 `productListItems` 배열의 각 개체에 대해 하나씩 두 개의 하위 컨테이너가 포함되어 있습니다. 다음 표는 이벤트에 속하는 필드와 해당 하위 컨테이너에 속하는 필드를 보여줍니다.

| 레벨 | 필드 | 필드에 설명된 내용 |
| --- | --- | --- |
| **이벤트** | `eventType`, `timestamp`, `commerce.purchases.value` | 전체로서의 구매. 각 필드에는 이벤트에 대해 하나의 값이 있습니다. **주문** 지표는 포함된 제품의 수에 관계없이 이 이벤트에 대해 `1`을(를) 계산합니다. |
| **하위 컨테이너** | 각 `productListItems` 개체의 `SKU`, `name`, `quantity`, `priceTotal` | 구매의 개별 제품. 각 필드에는 제품당 하나의 값이 있습니다. 예를 들어, 무선 드릴의 경우 `quantity`이(가) `1`이고, 드릴 배터리 팩의 경우 `2`입니다. |

{style="table-layout:auto"}

>[!NOTE]
>
>하위 컨테이너에는 이벤트와 함께 전송된 데이터만 포함됩니다. Customer Journey Analytics은 장바구니 추가 또는 체크아웃과 같은 이전 이벤트에서 장바구니 콘텐츠를 재구성하지 않습니다. 제품이 구매 이벤트의 하위 컨테이너로 표시되려면 구현에서 해당 구매 이벤트의 `productListItems`에 제품을 포함해야 합니다.

## 데이터 피드에 하위 컨테이너 구성 요소 추가

데이터 피드에 하위 컨테이너 구성 요소를 추가하면 동일한 하위 컨테이너에서 다른 구성 요소를 추가하라는 대화 상자가 표시됩니다.

![관련 하위 컨테이너 구성 요소를 추가하라는 대화 상자](assets/data-feeds-add-subevent.png)

동일한 하위 컨테이너의 필드는 캔버스에 플랫 항목이 아닌 축소 가능한 중첩 그룹으로 표시됩니다.

![하위 컨테이너 그룹](assets/data-feeds-subevent-added.png)

이 그룹은 기본 데이터 구조를 반영합니다.

데이터 피드 출력에서 이러한 모든 구성 요소는 단일 열에 중첩된 배열로 표시됩니다.

하위 컨테이너 구성 요소를 포함한 구성 요소를 데이터 피드에 추가하는 방법에 대한 자세한 내용은 [데이터 피드 만들기](/help/components/exports/cja-data-feeds/create-feed.md)를 참조하십시오.

## 데이터 피드 출력의 하위 컨테이너 데이터 쿼리

하위 컨테이너 데이터 [은(는) Customer Journey Analytics 데이터 피드에서 다르게 표시되므로](#sub-container-differences-between-adobe-analytics-and-customer-journey-analytics)에 사용하는 쿼리와 Adobe Analytics 데이터 피드에 사용하는 쿼리가 다릅니다.

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

## 데이터 피드에서 맵 필드 사용

XDM 스키마 저장소 키-값 쌍의 필드를 매핑합니다. 데이터 피드는 다른 [하위 컨테이너 데이터](#query-sub-container-data-in-data-feed-output)와 같은 방식으로 각 맵을 개체 배열로 내보냅니다. 각 개체에는 맵 키와 해당 값이 별도의 필드로 포함되어 있습니다.

출력의 필드 이름은 `key` 또는 `value`과 같이 고정된 이름이 아닌 데이터 피드에 대해 구성하는 구성 요소 ID에서 가져옵니다. 이 섹션의 예제에서는 샘플 구성 요소 ID를 사용합니다.

<!-- Confirm with Nate before publishing: how the outer array column is named in the output (for example, `survey_responses`). -->

### 단순 맵

단순 맵은 자체 스키마에서 만들 수 있는 맵 유형입니다. 각 키는 문자열이고, 각 값은 문자열 또는 정수입니다.

예를 들어 설문 조사 맵은 각 질문을 키로 저장하고 응답은 값으로 저장합니다.

```json
{
  "_yourtenant": {
    "surveyResponses": {
      "How did you hear about us?": "Search engine",
      "How likely are you to recommend us?": 9
    }
  }
}
```

데이터 피드 출력에서 `survey_question` 및 `survey_answer`은(는) 키와 값의 구성 요소 ID입니다.

```json
{
  "survey_responses": [
    { "survey_question": "How did you hear about us?", "survey_answer": "Search engine" },
    { "survey_question": "How likely are you to recommend us?", "survey_answer": 9 }
  ]
}
```

### ID 맵

[`identityMap`](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/field-groups/profile/identitymap) 필드의 각 ID를 하나의 개체로 내보냅니다. 개체에는 식별자, 인증된 상태 및 기본 플래그와 함께 ID 네임스페이스(키)가 포함되어 있습니다. 네임스페이스는 해당 네임스페이스의 각 ID에 대해 반복됩니다.

데이터 보기에 차원으로 존재하며 데이터 피드에 추가한 ID 맵 속성만 내보내집니다.

```json
{
  "identity_map": [
    { "identity_namespace": "ECID", "identity_id": "83290187457380573620940587193016478103", "authenticated_state": "ambiguous", "is_primary": true },
    { "identity_namespace": "CRMID", "identity_id": "C-1048576", "authenticated_state": "authenticated", "is_primary": false }
  ]
}
```

### 중첩된 맵

`segmentMembership`과(와) 같은 일부 Adobe 정의 필드는 맵 맵입니다. 데이터 피드는 이를 단일 배열로 병합하고 첫 번째 수준 키와 두 번째 수준 키를 각 개체에서 별도의 필드로 사용합니다. 첫 번째 수준 키는 적용되는 각 개체에서 반복되므로 데이터나 관계가 손실되지 않습니다.

예를 들어 `segment_namespace` 및 `segment_id`은(는) 첫 번째 수준 키 및 두 번째 수준 키의 구성 요소 ID입니다.

```json
{
  "segment_membership": [
    { "segment_namespace": "ups", "segment_id": "04a81716-43d6-4e7a-a49c-f1d8b3129ba9", "status": "realized" },
    { "segment_namespace": "ups", "segment_id": "53cba6b2-a23b-454a-8069-fc41308f1c0f", "status": "exited" }
  ]
}
```








