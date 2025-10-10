---
title: 오브젝트 배열 사용
description: Customer Journey Analytics이 데이터 계층에 대해 보고하는 방법을 알아봅니다.
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 61%

---

# 오브젝트 배열 사용

일부 플랫폼 스키마에 오브젝트 배열이 있을 수 있습니다. Adobe Customer Journey Analytics은 이벤트, 조회 및 프로필 데이터 내에서 개체 배열의 수집 및 보고를 지원합니다. 가장 일반적인 예 중 하나는 여러 제품이 포함된 장바구니입니다. 각 제품에는 이름, SKU, 범주, 가격, 수량 및 추적하려는 기타 모든 차원이 있습니다. 이러한 모든 패싯에는 별도의 요구 사항이 있지만 모두 동일한 히트에 적합해야 합니다.

이전 버전의 Adobe Analytics에서는 `products` 변수를 사용하여 이 기능을 제공했습니다. 제품의 패싯을 구분하기 위해 세미콜론(`;`)으로 구분된 연속 문자열이며, 제품 설명은 쉼표(`,`)로 구분했습니다. &quot;오브젝트 배열&quot;을 제한적으로 지원하는 유일한 변수였습니다. 목록 변수와 같은 다중 값 변수는 배열의 동등한 변수를 지원할 수 있지만, &quot;오브젝트 배열&quot;을 지원할 수는 없습니다. Customer Journey Analytics은 단일 데이터 행 내에서 임의의 세부 계층을 지원하여 이 개념을 확장했습니다. 이는 이전 버전의 Adobe Analytics에서 사용할 수 없는 기능입니다.

## 동일한 이벤트 예

다음 이벤트는 고객이 구매한 세탁기 및 건조기 구성을 나타내는 JSON 개체입니다.

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

데이터 보기를 만들 때 다음 차원과 지표를 사용할 수 있습니다(스키마를 기준).

* **차원:**
   * ID
   * product : SKU
   * product : name
   * product : order_id
   * product : warranty : coverage
   * prodcut : warranty : length
   * product : warranty : name
   * product : warranty : type
* **지표:**
   * product : orders
   * product : units
   * product : revenue
   * product : warranty
   * product : warranty : revenue

### 동일한 이벤트 예(보고 동작)

위의 이벤트만 사용하면 다음 표에서 일부 차원과 지표 조합이 있는 Workspace 보고서를 확인할 수 있습니다.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

Customer Journey Analytics은 표를 기반으로 개체의 차원과 지표를 선택적으로 살펴봅니다.

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

보증 수익만 보고하려면 프로젝트가 다음과 비슷합니다.

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

Customer Journey Analytics은 다음과 같은 이벤트 부분을 보고 보고서를 생성합니다.

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

건조기에 보증서가 포함되지 않았으므로 테이블에 건조기가 포함되지 않습니다.

차원과 지표를 모두 결합할 수 있으므로 다음 테이블에서 데이터에 어떻게 지정되지 않은 차원 항목이 있는지 확인할 수 있습니다.

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

제품 주문에 연결된 보증 이름이 없으므로 차원 항목 속성이 &#39;지정되지 않음&#39;으로 설정됩니다. 제품 보증 주문에도 동일한 상황이 적용됩니다.

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

연결된 이름이 없는 주문에 주의하십시오. 이는 &#39;지정되지 않음&#39; 차원 항목으로 인한 주문입니다.

### 지표 결합

Customer Journey Analytics은 이름이 비슷한 지표가 다른 객체 수준에 있는 경우 기본적으로 이 지표를 결합하지 않습니다.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

하지만 다음과 같이 원하는 지표를 결합하는 계산된 지표를 만들 수 있습니다.

계산된 지표 &quot;총 매출액&quot;: `[product : revenue] + [product : warranty : revenue]`

이 계산된 지표를 적용하면 원하는 결과가 표시됩니다.

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |



## 제한 사항

제한 사항은 Customer Journey Analytics에서 사용하고 Experience Platform의 스키마의 일부로 모델링되는 데이터의 배열에 적용됩니다. [실시간 고객 프로필 데이터 및 세분화를 위한 기본 보호](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-model-limits)에서 [데이터 모델 제한](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-size-limits) 및 [데이터 크기 제한](https://experienceleague.adobe.com/ko/docs/experience-platform/profile/guardrails)을 참조하십시오.

