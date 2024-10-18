---
title: 기본 함수
description: 계산된 지표 빌더를 사용하면 고급 계산된 지표에 통계 및 수학 함수를 적용할 수 있습니다.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 1a84fc71eb29ceabf3a3c5c3e333b78b882ea966
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 29%

---

# 기본 함수


[계산된 지표 빌더](cm-workflow/cm-build-metrics.md)를 사용하면 통계 및 수학 함수를 적용할 수 있습니다. 이 문서에서는 함수 및 해당 정의의 알파벳 목록을 문서화합니다.

>[!NOTE]
>
>[!DNL metric]이 함수에서 인수로 식별되는 경우 지표의 다른 표현식도 허용됩니다. 예를 들어 [열 최대값(지표)](#column-maximum)은(는) [열 최대값(페이지 보기 횟수 + 방문 횟수)](#column-maximum)도 허용합니다.



## 테이블 함수 대 행 함수

테이블 함수는 출력이 모든 테이블 행에 대해 동일한 함수입니다. 행 함수는 출력이 모든 테이블 행에 대해 다른 함수입니다.

적용 가능하고 관련된 경우 함수에는 [!BADGE 테이블] 형식의 주석이 추가됩니다.{type="Neutral"}[!BADGE 행]{type="Neutral"}

## include-zeros 매개변수는 무엇을 의미합니까?

계산에 0을 포함할지 여부를 알려 줍니다. 때로는 0이 *없음*&#x200B;을 의미하지만 때로는 중요합니다.

예를 들어, 매출 지표가 있고, 그 다음 페이지 보기 지표를 보고서에 추가하는 경우, 모두 0인 매출 행이 갑자기 더 많아집니다. 추가 지표가 **[평균](cm-functions.md#mean)**, **[행 최소값](cm-functions.md#row-min)**, **[사분위수](cm-functions.md#quartile)** 및 수익 열에 있는 더 많은 계산에 영향을 주지 않도록 하려는 것일 수 있습니다. 이 경우 `include-zeros` 매개 변수를 확인합니다.

대체 시나리오는 두 개의 관심 지표가 있고 행 중 일부가 0이므로 한 개의 지표가 더 높은 평균 또는 최소값을 갖는 것입니다.  이 경우 0을 포함하도록 매개 변수를 확인하지 않도록 선택할 수 있습니다



## 절대값

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 절대값(지표)]**

[!BADGE 행]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| metric | 절대값을 계산할 지표입니다. |


## 열 최대값

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 열 최대값(지표, include_zeros)]**

지표 열에 대한 차원 요소 세트에서 가장 큰 값을 반환합니다. MAXV는 차원 열 전체에 걸쳐 단일 열(지표) 내에서 수직으로 평가됩니다.

| 인수 | 설명 |
|---|---|
| metric | 지표가 하나 이상 필요하지만 원하는 수의 지표를 매개 변수로 사용할 수 있습니다. |
| include_zeros | 계산에 0 값을 포함할지 여부입니다. |


## 열 최소값

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 열 최소값(지표, include_zeros)]**

지표 열에 대한 차원 요소 세트에서 가장 작은 값을 반환합니다. MINV는 차원 열 전체에 걸쳐 단일 열(지표) 내에서 수직으로 평가됩니다.

| 인수 | 설명 |
|---|---|
| metric | 지표가 하나 이상 필요하지만 원하는 수의 지표를 매개 변수로 사용할 수 있습니다. |
| include_zeros | 계산에 0 값을 포함할지 여부입니다. |


## 열 합계

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 열 합계(지표)]**

열 내의 한 지표에 대한 모든 숫자 값을 추가합니다(차원의 요소들에 대해).

| 인수 | 설명 |
|---|---|
| metric | 지표가 하나 이상 필요하지만 원하는 수의 지표를 매개 변수로 사용할 수 있습니다. |


## 계수

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(지표)]**

[!BADGE Table]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| metric | 계산할 지표입니다. |


## 지수

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 지수(지표)]**

[!BADGE 행]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| metric | 기본 e에 적용된 지수. |


## 평균

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 평균(지표, include_zeros)]**

[!BADGE Table]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| metric | 평균을 계산할 지표입니다. |
| include_zeros | 계산에 0 값을 포함할지 여부입니다. |


## 중간값

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 중간값(지표, include_zeros)]**

[!BADGE Table]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| metric | 중간값을 계산할 지표입니다. |
| include_zeros | 계산에 0 값을 포함할지 여부입니다. |


## 모듈로

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 모듈로(metric_X, metric_Y)]**

유클리드 분할을 사용하여 x를 y로 나눈 후 나머지를 반환합니다.

| 인수 | 설명 |
|---|---|
| metric_X | 분할하려는 첫 번째 지표입니다. |
| metric_Y | 분할하려는 두 번째 지표입니다. |

### 예

반환 값의 부호는 입력과 같습니다(또는 영임).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

항상 양수를 얻으려면 다음을 사용하십시오

```
MODULO(MODULO(x,y)+y,y)
```

## 백분위수

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 백분위수(지표, k, include_zeros)]**

[!BADGE Table]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| metric | 0에서 100까지 범위의 백분위수 값. |
| k | 상대적 순위를 정의하는 지표 열. |
| include_zeros | 계산에 0 값을 포함할지 여부입니다. |



## 거듭제곱 연산자

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL POWER 연산자(metric_X, metrix_Y)]**

x를 y 제곱한 값으로 반환합니다.

| 인수 | 설명 |
|---|---|
| metric_X | metric_Y 파워로 높이려는 지표입니다. |
| metric_Y | metric_X 를 높이려는 전력입니다. |


## 사분위수

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 사분위수(지표, 사분위수, include_zeros)]**

[!BADGE Table]{type="Neutral"}[열 최소값](#column-minimum), [중간값](#median) 및 [열 최대값](#column-maximum)은(는) 사분위수가 각각 `0`(영), `2` 및 `4`과(와) 같은 경우 [사분위수](#quartile)과(와) 같은 값을 반환합니다.

| 인수 | 설명 |
|---|---|
| metric | 사분위수 값을 계산할 지표입니다. |
| 사분위수 | 반환할 사분위수 값을 나타냅니다. |
| include_zeros | 계산에 0 값을 포함할지 여부입니다. |


## 반올림

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(지표, 숫자)]**

*number* 매개 변수가 없는 반올림은 *number* 매개 변수가 0인 반올림과 동일합니다. 즉, 가장 가까운 정수로 반올림합니다.  *number* 매개 변수를 사용하면 ROUND는 소수 오른쪽에 있는 *number*&#x200B;자리를 반환합니다.  *number*&#x200B;이(가) 음수이면 소수의 왼쪽에 0을 반환합니다.

| 인수 | 설명 |
|---|---|
| metric | 반올림할 지표. |
| 숫자 | 반환할 소수 오른쪽에 있는 자릿수입니다. (음수이면 십진수의 왼쪽에 0이 반환됩니다.) |

### 예

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```


## 행 수

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 행 수()]**

주어진 열에 대해 행 수를 반환합니다(차원 내에 보고된 고유 요소 수). *고유 수 초과*&#x200B;은(는) 1로 계산됩니다.


## 행 최대값

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 행 MAX(지표, include_zeros)]**

각 행의 최대 열 수.

| 인수 | 설명 |
|---|---|
| metric | 지표가 하나 이상 필요하지만 원하는 수의 지표를 매개 변수로 사용할 수 있습니다. |
| include_zeros | 계산에 0 값을 포함할지 여부입니다. |

## 행 최소값

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 행 최소값(지표, include_zeros)]**

각 행의 최소 열 수.

| 인수 | 설명 |
|---|---|
| metric | 지표가 하나 이상 필요하지만 원하는 수의 지표를 매개 변수로 사용할 수 있습니다. |
| include_zeros | 계산에 0 값을 포함할지 여부입니다. |



## 행 합계

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 행 합계(지표, include_zeros)]**

각 행의 열 합계.

| 인수 | 설명 |
|---|---|
| metric | 지표가 하나 이상 필요하지만 원하는 수의 지표를 매개 변수로 사용할 수 있습니다. |


## 제곱근

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 제곱근(지표, include_zeros)]**

[!BADGE 행]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| metric | 제곱근을 계산할 지표입니다. |


## 표준 편차

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 표준 편차(지표, include_zeros)]**

[!BADGE Table]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| | 표준 편차를 계산할 지표입니다. |
| include_zeros | 계산에 0 값을 포함할지 여부입니다. |


## 변량

![효과](/help/assets/icons/Effect.svg) **[!UICONTROL 분산(지표, include_zeros)]**

[!BADGE Table]{type="Neutral"}

| 인수 | 설명 |
|---|---|
| metric | 분산을 계산할 지표입니다. |
| include_zeros | 계산에 0 값을 포함할지 여부입니다. |


VARIANCE 방정식은 다음과 같습니다.

![](assets/variance_eq.png){width="100"}

여기서 *x*&#x200B;은(는) 샘플 평균이고 [MEAN(*metric*)](#mean)이며 *n*&#x200B;은(는) 샘플 크기입니다.


분산을 계산하기 위해 전체 숫자 열을 살펴봅니다. 그 숫자 목록에서 먼저 평균을 계산합니다. 평균을 구하면 각 항목으로 이동하여 다음을 수행합니다.

1. 숫자에서 평균을 뺍니다.

1. 계산 결과를 제곱합니다.

1. 그 값을 총계에 더합니다.

전체 열을 반복하면 하나의 합계가 생깁니다. 그 총계를 열의 항목 수(열 개수)로 나눕니다. 이렇게 해서 얻은 숫자가 열의 변량입니다. 이 값은 하나의 값이지만 숫자 열로 표시됩니다.

다음 세 항목 열의 예에서

| 열 |
|:---:|
| 1 |
| 2 |
| 3 |

이 열의 평균은 2입니다. 열의 변량은 ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3입니다.




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