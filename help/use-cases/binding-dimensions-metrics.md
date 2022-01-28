---
title: CJA에서 결합 차원 및 지표 사용
description: 복잡한 지속성 분석을 위해 속성 차원을 객체 배열에 추가합니다.
source-git-commit: b93809c9af02227295c9dd66565f04675236c393
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---


# CJA에서 결합 차원 및 지표 사용

Customer Journey Analytics은 차원 값이 설정된 히트 이후에 차원 값을 유지하는 몇 가지 방법을 제공합니다. Adobe 오퍼이 제공하는 지속성 메서드 중 하나를 바인딩이라고 합니다. 이전 버전의 Adobe Analytics에서는 이 개념을 머천다이징이라고 했습니다.

최상위 이벤트 데이터로 바인딩 차원을 사용할 수 있지만, 이 개념은 [개체 배열](object-arrays.md). 특정 이벤트의 모든 속성에 차원을 적용하지 않고 객체 배열의 한 부분에 차원을 지정할 수 있습니다. 예를 들어 전체 이벤트에 해당 검색어를 바인딩하지 않고 장바구니 개체 배열의 한 제품에 검색어를 지정할 수 있습니다.

## 예제 2: 결합 지표를 사용하여 검색어를 제품 구매에 연결

Adobe Analytics에서 가장 일반적인 머천다이징 방법 중 하나는 검색어를 제품에 바인딩하여 각 검색어가 적절한 제품에 대한 크레딧을 받도록 하는 것이었습니다. 다음 고객 여정을 고려하십시오.

1. 방문자가 사이트에 도달하여 &quot;권투 글러브&quot;를 검색합니다.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
               "color": "Red",
               "price": "25.69"
           },
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Professional gloves",
               "color": "Blue",
               "price": "224.99"
           }
       ]
   }
   ```

1. 그들은 좋아하는 장갑을 찾아서 장바구니에 넣는다.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           }
       ]
   }
   ```

1. 그러면 방문자가 &quot;테니스 라켓&quot;을 검색합니다.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Women's open racket",
               "price": "49.99"
           },
           {
               "name": "Extreme racket",
               "price": "134.99"
           }
       ]
   }
   ```

1. 그들은 그들이 좋아하는 라켓을 찾아서 수레에 추가한다.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           }
       ]
   }
   ```

1. 방문자는 세 번째로 &quot;shoes&quot;를 검색합니다.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
               "color": "Grey",
               "price": "54.95"
           },
           {
               "name": "Tennis shoes",
               "color": "White",
               "price": "42.59"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. 그들은 좋아하는 신발을 찾아 카트에 추가한다.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. 방문자는 체크아웃 프로세스를 진행하여 이 세 항목을 구매합니다.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

검색어에 기존 할당 모델을 사용하는 경우 세 제품 모두 매출을 단일 검색어에만 기여합니다. 예를 들어 검색어 차원과 함께 첫 번째 할당을 사용한 경우:

| search_term | 매출 |
| --- | --- |
| 권투 장갑 | US$204.97 |

검색어 차원과 함께 마지막 할당을 사용한 경우 세 제품 모두 매출을 단일 검색어에 기여합니다.

| search_term | 매출 |
| --- | --- |
| 신발 | US$204.97 |

이 예에는 한 명의 방문자만 포함되지만, 다른 항목을 검색하는 많은 방문자가 검색어를 다른 제품에 잘못 지정할 수 있으므로 실제로 가장 적합한 검색 결과를 판별하기 어렵습니다.

Adobe은 바인딩 차원을 사용하여 바인딩된 차원 항목을 메모합니다. 후속 이벤트에서 동일한 바인딩 값이 표시되면 원하는 지표를 그 값에 지정할 수 있도록 차원 항목을 가져옵니다. 이 예제에서는 search_term에 대한 결합 차원을 제품 이름으로 설정할 수 있습니다.

![바인딩 차원](assets/binding-dimension.png)

데이터 보기 관리자에서 이 차원을 설정하면 바인딩 차원이 개체 배열에 있으므로 바인딩 지표도 설정해야 합니다. 바인딩 지표는 바인딩 차원에 대한 트리거 역할을 하므로 결합 지표가 있는 이벤트에만 바인딩합니다. 이 예제 구현에서 검색 결과 페이지에는 항상 검색어 차원과 검색 지표가 포함되어 있습니다. 검색 지표가 있을 때마다 제품 이름에 검색어를 바인딩할 수 있습니다.

![지표 바인딩](assets/binding-metric.png)

검색어 차원을 이 지속성 모델로 설정하면 다음 논리가 실행됩니다.

* search_term이 이벤트에 있으면 제품 이름이 있는지 확인합니다.
* 제품 이름이 없으면 아무 작업도 수행하지 마십시오.
* 제품 이름이 있는 경우 검색 지표가 있는지 확인합니다.
* 검색 지표가 없는 경우에는 아무 작업도 하지 않습니다.
* 검색 지표가 있는 경우 모든 제품 이름에 검색어를 바인딩합니다. 해당 이벤트의 제품 이름과 동일한 수준에서 작동하는 것입니다. 이 예에서는 product.search_term으로 처리됩니다.
* 후속 이벤트에서 동일한 제품 이름이 표시되면 바인딩된 검색어도 함께 존재합니다.

Analysis Workspace에서 결과 보고서는 다음과 비슷합니다.

| search_term | 매출 |
| --- | --- |
| 권투 장갑 | US$89.99 |
| 테니스 라켓 | US$34.99 |
| 신발 | US$79.99 |
