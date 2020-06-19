---
title: 개체 배열 사용
description: CJA가 데이터 계층에 대해 보고하는 방법을 이해합니다.
translation-type: tm+mt
source-git-commit: 52fecf03cc503fa59101f6280c671e153e2129e9
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---


# 개체 배열 사용

일부 플랫폼 스키마에는 개체 배열이 있을 수 있습니다. 가장 일반적인 예 중 하나는 여러 제품을 포함하는 장바구니입니다. 각 제품에는 이름, SKU, 카테고리, 가격, 수량 및 추적하려는 기타 모든 차원이 있습니다. 이러한 모든 측면에는 별도의 요구 사항이 있지만 모두 동일한 히트에 적합해야 합니다.

이전 버전의 Adobe Analytics에서는 변수를 사용하여 이 작업을 `products` 수행했습니다. 쉼표(쉼표)를 구분 처리하는 반면, 제품의 패싯은 쉼표(`;`)로 구분하기 위해 세미콜론으로 구분된 연결된`,`문자열입니다. &quot;개체 배열&quot;을 제한적으로 지원하는 유일한 변수입니다. 목록 변수와 같은 다중 값 변수는 배열의 해당 변수를 지원할 수 있지만 &quot;개체 배열&quot;을 지원할 수는 없습니다. CJA는 이전 버전의 Adobe Analytics에서는 사용할 수 없는 기능인 단일 데이터 행 내에서 임의 깊은 계층을 지원하여 이 개념을 확장했습니다.

## 동일한 히트 예

다음 히트는 세탁기 및 건조기로 구성된 고객을 나타내는 JSON 개체입니다.

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

데이터 뷰를 만들 때 다음 차원과 지표를 사용할 수 있습니다(스키마를 기준으로).

* **차원:**
   * ID
   * product : SKU
   * product : name
   * product : order_id
   * product : 보증 : 보장
   * prodcut : 보증 : 길이
   * product : 보증 : name
   * product : 보증 : type
* **지표:**
   * product : 주문
   * product : 판매량
   * product : 수익
   * product : 보증
   * product : 보증 : 수익

### 동일한 히트 예(보고 동작)

다음 표에는 몇 가지 차원과 지표 조합이 있는 작업 공간 보고서가 나와 있습니다.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA는 테이블을 기준으로 객체의 차원과 지표를 선택적으로 봅니다.

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

CJA는 보고서를 생성하기 위해 히트의 이러한 부분을 확인합니다.

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

건조기에 보증서가 포함되지 않았기 때문에 테이블에 포함되지 않습니다.

어떤 차원이든 어떤 지표와 결합할 수 있으므로 다음 표는 데이터가 지정되지 않은 차원 값과 어떻게 일치하는지를 보여줍니다.

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

제품 주문은 연결된 보증 이름 없이 존재하므로 차원 값 속성은 &#39;지정되지 않음&#39;으로 설정됩니다. 제품 보증 주문에도 동일한 상황이 적용됩니다.

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

여기에 이름이 연결되어 있지 않은 주문에 주목하십시오. &#39;지정되지 않음&#39; 차원 값에 속하는 주문입니다.

### 지표 결합

CJA는 이름이 비슷한 지표를 다른 객체 수준에 있는 경우 기본적으로 결합하지 않습니다.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

하지만 원하는 지표를 결합하는 계산된 지표를 만들 수 있습니다.

계산된 지표 &quot;총 매출액&quot;: `[product : revenue] + [product : warranty : revenue]`

이 계산된 지표를 적용하면 원하는 결과가 표시됩니다.

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |

## 지속성 예

