---
title: 기본 함수
description: 계산된 지표 빌더를 사용하면 고급 계산된 지표에 통계 및 수학 함수를 적용할 수 있습니다.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 47c5fc27d994667933103f864a253e086050bbf8
workflow-type: tm+mt
source-wordcount: '1636'
ht-degree: 100%

---

# 기본 함수


[계산된 지표 빌더](cm-workflow/cm-build-metrics.md)를 사용하면 통계 및 수학 함수를 적용할 수 있습니다. 이 문서는 함수 및 그 정의를 알파벳 순서로 나열한 것입니다.

>[!NOTE]
>
>[!DNL metric]이 함수에서 인수로 식별되는 경우 지표의 다른 표현식도 허용됩니다. 예를 들어 [COLUMN MAXIMUM(지표)](#column-maximum)는 [COLUMN MAXIMUM(페이지 조회수 + 방문 수)](#column-maximum)도 허용합니다.



## 테이블 함수 대 행 함수

테이블 함수는 출력이 모든 테이블 행에 대해 동일한 함수입니다. 행 함수는 출력이 모든 테이블 행에 대해 다른 함수입니다.

해당 및 관련이 있는 경우 함수에 함수 유형이 주석으로 표시됩니다. [!BADGE 테이블]{type="Neutral"}[!BADGE 행]{type="Neutral"}

## include-zeros 매개변수는 무엇을 의미합니까?

계산에 0을 포함할지 여부를 알려 줍니다. 때로 0은 *아무것도 없다*&#x200B;는 뜻이지만, 경우에 따라서는 중요합니다.

예를 들어 매출 지표가 있고, 그 다음에 페이지 조회수 지표를 보고서에 추가하는 경우, 모두 0인 매출 행이 갑자기 더 많아집니다. 이러한 추가 지표가 수익 열에 있는 **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** 등 계산에 영향을 미치는 것을 원하지 않을 수도 있습니다. `include-zeros` 매개변수를 확인해야 합니다.

다른 시나리오는 관심 있는 지표가 두 개이며, 하나는 일부 행이 0이기 때문에 평균 또는 최솟값이 더 높은 경우입니다.  이 경우 매개변수에 0을 포함하지 않도록 선택할 수 있습니다



## 절댓값 {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="절댓값"
>abstract="숫자의 절댓값을 반환합니다. 숫자의 절댓값은 양의 값을 갖는 숫자입니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(지표)]**

[!BADGE 행]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| 지표 | 절댓값을 계산할 지표. |


## 열 최댓값 {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="열 최댓값"
>abstract="지표 열에 대한 차원 요소 세트에서 가장 큰 값을 반환합니다. MAXV는 차원 열 전체에 걸쳐 단일 열(지표) 내에서 수직으로 평가됩니다."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM(지표, include_zeros)]**

지표 열에 대한 차원 요소 세트에서 가장 큰 값을 반환합니다. MAXV는 차원 열 전체에 걸쳐 단일 열(지표) 내에서 수직으로 평가됩니다.

| 인수 | 설명 |
|---|---|
| 지표 | 하나 이상의 지표가 필요하지만 여러 개의 지표를 매개변수로 사용할 수 있습니다. |
| include_zeros | 계산에 0값을 포함할지 여부. |


## 열 최솟값 {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="열 최솟값"
>abstract="지표 열에 대한 차원 요소 세트에서 가장 작은 값을 반환합니다. MINV는 차원 열 전체에 걸쳐 단일 열(지표) 내에서 수직으로 평가됩니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM(지표, include_zeros)]**

지표 열에 대한 차원 요소 세트에서 가장 작은 값을 반환합니다. MINV는 차원 열 전체에 걸쳐 단일 열(지표) 내에서 수직으로 평가됩니다.

| 인수 | 설명 |
|---|---|
| 지표 | 하나 이상의 지표가 필요하지만 여러 개의 지표를 매개변수로 사용할 수 있습니다. |
| include_zeros | 계산에 0값을 포함할지 여부. |


## 열 합계 {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-sum"
>title="열 합계"
>abstract="열 내의 한 지표에 대한 모든 숫자 값을 추가합니다(차원의 요소들에 대해)."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN SUM(지표)]**

열 내의 한 지표에 대한 모든 숫자 값을 추가합니다(차원의 요소들에 대해).

| 인수 | 설명 |
|---|---|
| 지표 | 하나 이상의 지표가 필요하지만 여러 개의 지표를 매개변수로 사용할 수 있습니다. |


## 개수 {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="개수"
>abstract="열 내의 한 지표에 대한 0이 아닌 모든 숫자 값의 개수 또는 카운트를 반환합니다(한 차원 내에서 보고된 고유 요소의 수)."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(지표)]**

[!BADGE 테이블]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| 지표 | 카운트할 지표. |


## 지수 {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="지수"
>abstract="e를 주어진 숫자만큼 거듭제곱한 값을 반환합니다. 상수 e는 자연 로그의 밑인 2.71828182845904와 같습니다. 지수는 숫자의 자연 로그인 LN의 역함수입니다."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(지표)]**

[!BADGE 행]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| 지표 | 밑 e에 적용된 지수. |


## 평균 {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="평균"
>abstract="열에 있는 지표에 대한 산술 평균 또는 평균을 반환합니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(지표, include_zeros)]**

[!BADGE 테이블]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| 지표 | 평균을 계산할 지표. |
| include_zeros | 계산에 0값을 포함할지 여부. |


## 중간값 {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="중간값"
>abstract="열에 있는 지표에 대한 중간값을 반환합니다. 중간은 숫자 세트의 중간에 있는 숫자입니다. 즉, 이 값의 반은 중간값보다 크거나 같은 값이고 다른 반은 중간값보다 작거나 같습니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(지표, include_zeros)]**

[!BADGE 테이블]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| 지표 | 중간값을 계산할 지표. |
| include_zeros | 계산에 0값을 포함할지 여부. |


## 모듈로 {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-modulo"
>title="모듈로"
>abstract="유클리드 분할을 사용하여 x를 y로 나눈 후 나머지를 반환합니다. "

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

유클리드 분할을 사용하여 x를 y로 나눈 후 나머지를 반환합니다.

| 인수 | 설명 |
|---|---|
| metric_X | 분할하려는 첫 번째 지표. |
| metric_Y | 분할하려는 두 번째 지표. |

### 예

반환 값의 부호는 입력과 같습니다(또는 0임).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

항상 양수를 얻으려면 다음을 사용합니다

```
MODULO(MODULO(x,y)+y,y)
```

## 백분위수 {#percentile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-percentile"
>title="백분위수"
>abstract="0~100 사이의 값인 n번째 백분위수를 반환합니다. N &lt; 0이면 이 함수는 0을 사용합니다. N > 100이면 이 함수는 100을 반환합니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(지표, k, include_zeros)]**

[!BADGE 테이블]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| 지표 | 0에서 100까지 범위의 백분위수 값. |
| k | 상대적 순위를 정의하는 지표 열. |
| include_zeros | 계산에 0값을 포함할지 여부. |



## 거듭제곱 연산자 {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pow"
>title="거듭제곱 연산자"
>abstract="x를 y의 거듭제곱으로 반환합니다."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER OPERATOR(metric_X, metrix_Y)]**

x를 y의 거듭제곱으로 반환합니다.

| 인수 | 설명 |
|---|---|
| metric_X | metric_Y 거듭제곱으로 올리려는 지표. |
| metric_Y | metric_X를 높이려는 거듭제곱. |


## 사분위수 {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="사분위수"
>abstract="지표에 대한 값들의 사분위수를 반환합니다. 예를 들어 사분위수는 대부분의 매출을 파생시키는 상위 25%의 제품을 찾는 데 사용될 수 있습니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(지표, 사분위수, include_zeros)]**

[!BADGE 테이블]{type="Neutral"}[COLUMN MINIMUM](#column-minimum), [MEDIAN](#median), 및 [COLUMN MAXIMUM](#column-maximum)은 사분위수가 각각 `0`(영), `2` 및 `4`와 같을 때 [QUARTILE](#quartile)와 동일한 값을 반환합니다.

| 인수 | 설명 |
|---|---|
| 지표 | 사분위수 값을 계산할 지표. |
| 사분위수 | 반환할 사분위수 값을 나타냅니다. |
| include_zeros | 계산에 0값을 포함할지 여부. |


## 반올림 {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-round"
>title="반올림"
>abstract="*숫자* 매개변수가 없는 반올림은 *숫자* 매개변수가 0인 반올림과 같습니다. 즉 가장 가까운 정수로 반올림하는 것과 같습니다.  *숫자* 매개변수를 사용하면 ROUND는 *숫자* 자리를 소수점 이하 오른쪽에 반환합니다.  *숫자*&#x200B;가 음수이면 소수의 왼쪽에 0들을 반환합니다."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(지표, 숫자)]**

*숫자* 매개변수가 없는 반올림은 *숫자* 매개변수가 0인 반올림과 같습니다. 즉 가장 가까운 정수로 반올림하는 것과 같습니다.  *숫자* 매개변수를 사용하면 ROUND는 *숫자* 자리를 소수점 이하 오른쪽에 반환합니다.  *숫자*&#x200B;가 음수이면 소수의 왼쪽에 0들을 반환합니다.

| 인수 | 설명 |
|---|---|
| 지표 | 반올림할 지표. |
| 숫자 | 소수점 오른쪽에 몇 자리까지 반환할 것인가. (음수이면 소수점 왼쪽에 0이 반환됩니다). |

### 예

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## 행 수 {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-rows"
>title="행 수"
>abstract="주어진 열에 대해 행 수를 반환합니다(차원 내에 보고된 고유 요소 수). *고유 수 초과*&#x200B;는 1로 간주됩니다."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT()]**

주어진 열에 대해 행 수를 반환합니다(차원 내에 보고된 고유 요소 수). *고유 수 초과*&#x200B;는 1로 간주됩니다.


## 행 최댓값 {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-max"
>title="행 최댓값"
>abstract="각 행의 열 최댓값."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MAX(지표, include_zeros)]**

각 행의 열 최댓값.

| 인수 | 설명 |
|---|---|
| 지표 | 하나 이상의 지표가 필요하지만 여러 개의 지표를 매개변수로 사용할 수 있습니다. |
| include_zeros | 계산에 0값을 포함할지 여부. |


## 행 최솟값 {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-min"
>title="행 최솟값"
>abstract="각 행의 열 최솟값."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN(지표, include_zeros)]**

각 행의 열 최솟값.

| 인수 | 설명 |
|---|---|
| 지표 | 하나 이상의 지표가 필요하지만 여러 개의 지표를 매개변수로 사용할 수 있습니다. |
| include_zeros | 계산에 0값을 포함할지 여부. |



## 행 합계 {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-sum"
>title="행 합계"
>abstract="각 행의 열 합계."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM(지표, include_zeros)]**

각 행의 열 합계.

| 인수 | 설명 |
|---|---|
| 지표 | 하나 이상의 지표가 필요하지만 여러 개의 지표를 매개변수로 사용할 수 있습니다. |


## 제곱근 {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="제곱근"
>abstract="숫자의 양의 제곱근을 반환합니다. 숫자의 제곱근은 해당 숫자의 1/2 거듭제곱 값입니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL 제곱근(지표, include_zeros)]**

[!BADGE 행]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| 지표 | 제곱근을 계산할 지표. |


## 표준 편차 {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="표준 편차"
>abstract="데이터의 표본 집단을 기반으로, 표준 편차나, 분산의 제곱근을 반환합니다."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL 표준편차(지표, include_zeros)]**

[!BADGE 테이블]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| | 표준 편차를 계산할 지표. |
| include_zeros | 계산에 0값을 포함할지 여부. |


## 분산 {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="분산"
>abstract="데이터의 표본 집단을 기반으로 분산을 반환합니다."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(지표, include_zeros)]**

[!BADGE 테이블]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| 지표 | 분산 계산할 지표. |
| include_zeros | 계산에 0값을 포함할지 여부. |


VARIANCE 방정식은 다음과 같습니다.

![](assets/variance_eq.png){width="100"}

여기서 *x*&#x200B;는 샘플 평균 [MEAN(*지표*)](#mean)이고 *n*&#x200B;은 샘플의 크기입니다.


분산을 계산하려면 전체 숫자 열을 확인합니다. 그 숫자 목록에서 먼저 평균을 계산합니다. 평균을 계산한 다음 각 항목으로 이동하여 다음 작업을 수행합니다.

1. 숫자에서 평균을 뺍니다.

1. 계산 결과를 제곱합니다.

1. 그 값을 총계에 더합니다.

전체 열에 대해 반복하여 총계 값을 하나 얻습니다. 그 총계를 열의 항목 수(열 개수)로 나눕니다. 이렇게 해서 얻은 숫자가 열의 변량입니다. 이 값은 하나의 값이지만 숫자 열로 표시됩니다.

다음 3개 항목 열의 예:

| 열 |
|:---:|
| 1 |
| 2 |
| 3 |

이 열의 평균은 2입니다. 열의 분산은((1 - 2)<sup>2</sup> +(2 - 2)<sup>2</sup> +(3 - 2)<sup>2</sup>/3 = 2/3입니다.

<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->