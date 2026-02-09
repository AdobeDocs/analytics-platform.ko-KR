---
title: 기본 함수
description: 기본적인 계산된 지표 함수에 대해 알아보십시오.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: e2e87bc3d9f26b01f250d88b924c730fe4edac7b
workflow-type: tm+mt
source-wordcount: '3608'
ht-degree: 50%

---

# 기본 함수


[계산된 지표 빌더](cm-workflow/cm-build-metrics.md)를 사용하면 통계 및 수학 함수를 적용할 수 있습니다. 이 문서는 함수 및 그 정의를 알파벳 순서로 나열한 것입니다.

>[!NOTE]
>
>[!DNL metric]이 함수에서 인수로 식별되는 경우 지표의 다른 표현식도 허용됩니다. 예를 들어 [COLUMN MAXIMUM(지표)](#column-maximum)는 [COLUMN MAXIMUM(페이지 조회수 + 방문 수)](#column-maximum)도 허용합니다.



## 테이블 함수 대 행 함수

테이블 함수는 테이블의 모든 행에 대해 출력이 동일한 함수입니다. 행 함수는 테이블의 모든 행에 대해 출력이 다른 함수입니다.

해당 및 관련이 있는 경우 함수에 함수 유형이 주석([!BADGE 테이블]{type="Neutral"} 또는 [!BADGE 행]{type="Neutral"})으로 표시됩니다.

## include-zeros 매개변수는 무엇을 의미합니까?

계산에 0을 포함할지 여부를 알려 줍니다. 때로 0은 *아무것도 없다*&#x200B;는 뜻이지만 경우에 따라서는 중요합니다.

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

[!BADGE 행]{type="Neutral"} 숫자의 절댓값을 반환합니다. 숫자의 절댓값은 양의 값을 갖는 숫자입니다.

| 인수 | 설명 |
|---|---|
| 지표 | 절댓값을 계산할 지표. |

**사용 사례**: 매출 델타나 백분율 변경과 같이 음수 값을 생성할 수 있는 지표를 분석할 때 모든 결과가 양수인지 확인하십시오. 이는 방향에 상관 없이 변화의 크기에 초점을 맞추는 데 도움이 된다.

**계산된 지표 빌더에서**: **절대값** 함수에서 지표나 식을 래핑합니다(예: **절대값**(현재 수익 - 이전 수익). 이렇게 하면 음수 차이가 양수 값으로 변환됩니다.

>[!TIP]
>
>성능 증가 또는 감소 여부에 관계없이 두 기간 또는 세그먼트 간의 절대 차이를 측정하는 데 사용합니다.
>

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

**사용 사례**: 방문 횟수가 가장 많은 날 또는 매출액이 가장 많은 제품과 같이 분류 내에서 가장 높은 값을 식별합니다. 이렇게 하면 카테고리 간에 최고 성능을 강조하는 데 도움이 됩니다.

**계산된 지표 빌더에서**: **일** 또는 *제품*&#x200B;별로 분류할 때 *매출* 또는 *방문 횟수*&#x200B;와 같은 지표에 *열 최대값*&#x200B;을 적용합니다. 이 함수는 각 행에 대해 해당 열에서 가장 큰 값을 반환합니다.

>[!TIP]
>
>[IF](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if)&#x200B;(**Revenue** = *열 최대값&#x200B;**(Revenue*), 1, 0)과 같은 &#x200B;** IF** 문을 사용하여 분류에서 가장 성과가 좋은 항목을 강조 표시합니다.
>

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

**사용 사례**: 전환율이 가장 낮은 캠페인 또는 매출이 가장 낮은 요일과 같이, 분류 내에서 성과가 가장 낮은 값을 식별합니다. 이렇게 하면 성과가 낮은 세그먼트를 빠르게 표시할 수 있습니다.

**계산된 지표 빌더에서**: **Campaign** 또는 *일* 단위로 분류할 때 *매출* 또는 *전환율*&#x200B;과(와) 같은 지표에 *열 최소값*&#x200B;을(를) 적용합니다. 이 함수는 각 행에 대해 해당 열에서 가장 작은 값을 반환합니다.

>[!TIP]
>
>[IF](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if)&#x200B;(**Revenue** = *열 최소값&#x200B;**(Revenue*), 1, 0)과 같은 &#x200B;** IF** 문을 사용하여 분류에서 성과가 가장 낮은 항목을 강조 표시하십시오.
>


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

**사용 사례**: 모든 제품에 대한 총 매출액 또는 모든 일에 대한 총 방문 수와 같이 분류 내에 있는 모든 값의 합계를 계산합니다. 이렇게 하면 개별 행 값과 비교하기 위해 전체 합계가 필요한 경우에 도움이 됩니다.

**계산된 지표 빌더에서**: **제품** 또는 *일*&#x200B;별로 분류하면서 *매출* 또는 *방문*&#x200B;과 같은 지표에 *열 합계*&#x200B;를 적용합니다. 이 함수는 각 행에 대해 해당 열에 있는 모든 값의 합계를 반환합니다.

>[!TIP]
>
>총 성능의 지분 또는 백분율을 계산하기 위해 전체 합계에 대한 참조가 필요한 경우 사용합니다.
>


## 개수 {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="개수"
>abstract="열 내의 한 지표에 대한 0이 아닌 모든 숫자 값의 개수 또는 카운트를 반환합니다(한 차원 내에서 보고된 고유 요소의 수)."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(지표)]**

[!BADGE 테이블]{type="Neutral"} 열 내의 한 지표에 대한 0이 아닌 모든 숫자 값의 개수 또는 카운트를 반환합니다(한 차원 내에서 보고된 고유 요소의 수).

| 인수 | 설명 |
|---|---|
| 지표 | 카운트할 지표. |

**사용 사례**: 날짜 범위의 일 수 또는 분류의 제품 수와 같이 계산에 포함된 데이터 요소의 수를 계산합니다. 이렇게 하면 집계된 값에 기여하는 항목 수를 알아야 할 때 도움이 됩니다.

**계산된 지표 빌더에서**: **방문** 또는 *매출*&#x200B;과 같은 지표에 *Count*&#x200B;을(를) 적용하여 현재 분류 또는 날짜 범위에 포함된 총 행 수(또는 데이터 포인트)를 반환합니다.

>[!TIP]
>
>**열 합계**&#x200B;와 함께 사용하여 평균을 수동으로 계산합니다(예: **열 합계**(*수입*) / **개수**(수입).
>

## 지수 {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="지수"
>abstract="e를 주어진 숫자만큼 거듭제곱한 값을 반환합니다. 상수 e는 자연 로그의 밑인 2.71828182845904와 같습니다. 지수는 숫자의 자연 로그인 LN의 역함수입니다."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(지표)]**

[!BADGE 행]{type="Neutral"} 주어진 숫자만큼 거듭제곱한 값을 반환합니다. 상수 e는 자연 로그의 밑인 2.71828182845904와 같습니다. 지수는 숫자의 자연 로그인 LN의 역함수입니다.

| 인수 | 설명 |
|---|---|
| 지표 | 밑 e에 적용된 지수. |

**사용 사례**: 값을 제곱하거나 지수 증가 계수를 적용하는 등 지정한 거듭제곱으로 숫자나 지표를 늘립니다. 이는 증가 트렌드를 모델링하거나 지표를 기하급수적으로 확장할 때 유용합니다.

**계산된 지표 빌더에서**: 지표와 거듭제곱 값으로 **Exponent**&#x200B;을(를) 사용합니다. 예: **Exponent**(*방문*, 2) *방문* 지표의 제곱을 지정합니다.

>[!TIP]
>
>성장 패턴을 비교할 때 고급 모델링을 위해 **로그**&#x200B;와 결합하거나 변수가 많은 데이터를 매끄럽게 만듭니다.
>


## 평균 {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="평균"
>abstract="열에 있는 지표에 대한 산술 평균 또는 평균을 반환합니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(지표, include_zeros)]**

[!BADGE 테이블]{type="Neutral"} 열에 있는 지표에 대한 산술 평균 또는 평균을 반환합니다.

| 인수 | 설명 |
|---|---|
| 지표 | 평균을 계산할 지표. |
| include_zeros | 계산에 0값을 포함할지 여부. |

**사용 사례**: 일일 평균 매출액 또는 캠페인당 평균 방문 수와 같은 값 집합의 산술 평균을 계산합니다. 이렇게 하면 데이터 세트 내의 개별 값을 비교하기 위한 기준선을 설정하는 데 도움이 됩니다.

**계산된 지표 빌더에서**: **매출** 또는 *방문 횟수*&#x200B;와 같은 지표에 *평균*&#x200B;을(를) 적용하여 선택한 분류 또는 날짜 범위의 모든 데이터 포인트에 대한 평균 값을 반환합니다.

>[!TIP]
>
>을(를) 사용하여 전반적인 성능 추세를 이해하거나 **표준 편차**&#x200B;와(과) 결합하여 평균에 대한 일관성을 측정합니다.
>

## 중간값 {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="중간값"
>abstract="열에 있는 지표에 대한 중간값을 반환합니다. 중간은 숫자 세트의 중간에 있는 숫자입니다. 즉, 이 값의 반은 중간값보다 크거나 같은 값이고 다른 반은 중간값보다 작거나 같습니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(지표, include_zeros)]**

[!BADGE 테이블]{type="Neutral"} 열에 있는 지표에 대한 중간값을 반환합니다. 중간은 숫자 세트의 중간에 있는 숫자입니다. 즉, 이 값의 반은 중간값보다 크거나 같은 값이고 다른 반은 중간값보다 작거나 같습니다.

| 인수 | 설명 |
|---|---|
| 지표 | 중간값을 계산할 지표. |
| include_zeros | 계산에 0값을 포함할지 여부. |

**사용 사례**: 일일 평균 매출액 또는 방문당 페이지 보기 수 중앙값과 같은 데이터 집합의 중간값을 식별합니다. 이는 이상값의 영향을 줄이고 데이터의 중심 경향을 보려는 경우에 유용합니다.

**계산된 지표 빌더에서**: 매출액 또는 페이지 보기 수와 같은 지표에 중간값을 적용하여 선택한 분류 또는 날짜 범위의 모든 데이터 포인트에서 중간값을 반환합니다.

>[!TIP]
>
>데이터에 평균을 왜곡할 수 있는 매우 높거나 낮은 내용이 포함되어 있는 경우 **평균** 대신 사용합니다.
>


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

**사용 사례**: 한 숫자를 다른 숫자로 나눈 후 나머지를 반환합니다. 이는 매 n일마다 식별하거나 시퀀스에서 캠페인을 수행하는 것과 같이, 순환 또는 반복 패턴에 유용할 수 있습니다.

**계산된 지표 빌더에서**: 두 개의 숫자 입력에 **모듈로**&#x200B;을 사용합니다. 예를 들어 **Modulo**(*일 번호*, 7)은 일 번호를 7로 나눈 후 나머지를 반환합니다. 이렇게 하면 주별로 데이터를 그룹화하는 데 도움이 될 수 있습니다.

>[!TIP]
>
>조건부 논리와 결합하여 반복 간격을 강조 표시하거나 반복 주기를 기반으로 데이터를 세그먼트화합니다.
>

### 추가 예

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

[!BADGE Table]{type="Neutral"} 0~100 사이의 값인 n번째 백분위수를 반환합니다. N &lt; 0이면 이 함수는 0을 사용합니다. N > 100이면 이 함수는 100을 반환합니다.

| 인수 | 설명 |
|---|---|
| 지표 | 0에서 100까지 범위의 백분위수 값. |
| k | 상대적 순위를 정의하는 지표 열. |
| include_zeros | 계산에 0값을 포함할지 여부. |

**사용 사례**: 일일 매출 또는 페이지 보기의 90번째 백분위수와 같이 지정된 비율의 데이터 포인트가 속하는 값을 식별합니다. 이는 분포를 측정하고 고성능 이상치를 감지하는 데 도움이 됩니다.

**계산된 지표 빌더에서**: **수입** 또는 *방문*&#x200B;과 같은 지표에 *백분위수*&#x200B;을(를) 적용하고 원하는 백분위수 값(예: **백분위수**(*수입*, 90))을 지정하십시오. 이 결과는 데이터 포인트의 90%가 아래로 떨어지는 임계값을 보여 줍니다.

>[!TIP]
>
>성과 벤치마크를 설정하거나 최상의 성과를 보이는 날짜, 캠페인 또는 제품을 필터링하는 데 사용합니다.
>

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

**사용 사례**: 값을 제곱하거나 지수 가중치를 적용하는 것과 같이 한 숫자 또는 지표를 다른 숫자의 거듭제곱으로 늘립니다. 이는 성장을 모델링하거나, 값을 확장하거나, 고급 수학 변환을 수행할 때 유용합니다.

**계산된 지표 빌더에서**: 두 숫자 값 또는 지표 사이에 **Power 연산자를 사용**&#x200B;합니다. 예를 들어 *Revenue* ^ 2는 *Revenue* 값을 두 번째 단위로 늘립니다.

>[!TIP]
>
>**Exponent** 함수와 유사하지만 수학 연산자로 표시되어 계산된 지표 내에서 보다 작은 수식을 허용합니다.
>

## 사분위수 {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="사분위수"
>abstract="지표에 대한 값들의 사분위수를 반환합니다. 예를 들어 사분위수는 대부분의 매출을 파생시키는 상위 25%의 제품을 찾는 데 사용될 수 있습니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(지표, 사분위수, include_zeros)]**

[!BADGE 테이블]{type="Neutral"} 지표에 대한 값들의 사분위수를 반환합니다. 예를 들어 사분위수는 대부분의 매출을 파생시키는 상위 25%의 제품을 찾는 데 사용될 수 있습니다. [COLUMN MINIMUM](#column-minimum), [MEDIAN](#median) 및 [COLUMN MAXIMUM](#column-maximum)은 사분위수가 각각 `0`(영), `2` 및 `4`와 같을 때 [QUARTILE](#quartile)와 동일한 값을 반환합니다.

| 인수 | 설명 |
|---|---|
| 지표 | 사분위수 값을 계산할 지표. |
| 사분위수 | 반환할 사분위수 값을 나타냅니다. |
| include_zeros | 계산에 0값을 포함할지 여부. |

**사용 사례**: 매출 또는 방문 횟수로 상위 25%를 식별하는 것과 같이 값이 배포되는 방식을 이해하도록 데이터 집합을 4등분 합니다. 이렇게 하면 성능을 보다 심층적인 비교를 위해 등급 그룹으로 세분화하는 데 도움이 됩니다.

**계산된 지표 빌더에서**: **매출** 또는 *방문 횟수*&#x200B;와 같은 지표에 *사분위수*&#x200B;을(를) 적용하고 반환할 사분위수(예: **사분위수**(*매출*, 3)를 지정하여 세 번째 사분위수에 대한 임계값을 찾거나 상위 25%)를 지정하십시오.

>[!TIP]
>
>을 사용하여 낮은 성과, 중간 성과 및 높은 성과의 캠페인 또는 제품과 같은 성과 계층으로 값을 그룹화합니다.
>

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

**사용 사례**: 지정한 소수 자릿수로 반올림하여 숫자 결과를 단순화합니다. 이 기능은 시각화를 더 깔끔하게 만들거나 계산된 지표를 보고서에서 더 쉽게 읽을 수 있도록 하는 데 유용합니다.

**계산된 지표 빌더에서**: 지표 또는 식에 **Round**&#x200B;을(를) 적용하고 소수점 이하 자릿수를 지정하십시오. 예: **Round**(*전환율*, 2)은 값을 소수점 두 자리로 반올림합니다.

>[!TIP]
>
>특히 백분율 또는 통화 값을 표시할 때 를 사용하여 보고서 간 지표 서식을 표준화할 수 있습니다.
>

### 추가 예

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

**사용 사례**: 보고서에 포함된 일 수, 캠페인 또는 제품 수와 같이 분류 또는 데이터 세트에서 반환된 총 행 수를 계산합니다. 이렇게 하면 분석에 기여하는 항목의 수를 이해하는 데 도움이 됩니다.

**계산된 지표 빌더에서**: **행 수**&#x200B;를 적용하여 현재 분류 또는 세그먼트에 있는 총 행 수를 반환합니다. 예를 들어 *Product*&#x200B;에서 *Revenue*&#x200B;을(를) 볼 때 **Row Count**&#x200B;은(는) 표시된 제품 수를 반환합니다.

>[!TIP]
>
>**열 합계**&#x200B;와 같은 다른 함수와 함께 사용하여 평균을 수동으로 계산합니다(예: **열 합계**(*수입*) / **행 수**()).
>

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

**사용 사례**: 특정 날짜나 세그먼트에 대해 가장 큰 값을 갖는 지표(예: *매출*, *주문* 또는 *방문 횟수*)를 확인하는 등 단일 행의 모든 지표에서 가장 높은 값을 식별합니다. 이렇게 하면 각 데이터 행 내에서 리드하는 지표를 강조 표시하는 데 도움이 됩니다.

**계산된 지표 빌더에서**: 계산된 지표에 여러 지표가 포함된 경우 **행 최대값**&#x200B;을 적용합니다. 예를 들어 **행 최대값**(*매출*, *주문*, *방문 횟수*)은 각 행에 대해 해당 지표 중 가장 큰 값을 반환합니다.

>[!TIP]
>
>를 사용하여 관련 지표를 나란히 비교하고 각 행 내에서 성능에 가장 많이 기여하는 지표를 식별합니다.
>

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

**사용 사례**: 특정 날짜나 세그먼트에 대해 가장 작은 값을 갖는 지표(예: *매출*, *주문* 또는 *방문 횟수*)를 찾는 것과 같이 단일 행의 모든 지표에서 가장 낮은 값을 식별합니다. 이렇게 하면 각 데이터 행 내에서 가장 성과가 낮은 지표를 찾을 수 있습니다.

**계산된 지표 빌더에서**: 여러 지표를 비교할 때 **행 최소값**&#x200B;을 적용합니다. 예를 들어 **행 최소값**(*매출*, *주문*, *방문*)은 각 행에 대한 지표 중 가장 작은 값을 반환합니다.

>[!TIP]
>
>행 최대값과 결합하여 성능 범위를 계산하거나 병렬 비교에서 성과가 낮은 지표를 강조 표시합니다.
>

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

**사용 사례**: *매출*&#x200B;과 *세금*&#x200B;을 합하여 총 거래 값을 계산하거나 서로 다른 원본의 *방문*&#x200B;을 결합하는 것과 같이 단일 행 내에 여러 지표 값을 추가합니다. 이렇게 하면 관련 지표를 하나의 합계로 통합하는 데 도움이 됩니다.

**계산된 지표 빌더에서**: **행 합계**&#x200B;를 적용하여 여러 지표를 결합합니다. 예를 들어 **행 합계**(*매출*, *세금*)는 분류의 각 행에 대해 이러한 두 지표를 추가합니다.

>[!TIP]
>
>결합된 합계를 만들거나 관련 성과 지표를 단일 계산된 지표로 그룹화하는 데 사용합니다.
>

## 제곱근 {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="제곱근"
>abstract="숫자의 양의 제곱근을 반환합니다. 숫자의 제곱근은 해당 숫자의 1/2 거듭제곱 값입니다."

<!-- markdownlint-enable MD034 -->


![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL 제곱근(지표, include_zeros)]**

[!BADGE Row]{type="Neutral"} 숫자의 양의 제곱근을 반환합니다. 숫자의 제곱근은 해당 숫자의 1/2 거듭제곱 값입니다.

| 인수 | 설명 |
|---|---|
| 지표 | 제곱근을 계산할 지표. |

**사용 사례**: 데이터 집합에서 표준 편차 또는 정규화 값을 계산할 때 분산 루트 찾기와 같이 숫자 또는 지표의 제곱근을 반환합니다. 이 기능은 고급 통계 또는 데이터 변환 계산에 유용합니다.

**계산된 지표 빌더에서**: 지표 또는 식에 **제곱근**&#x200B;을 적용합니다. 예: **제곱근**(Variance(*수익*))은 *수익*&#x200B;의 표준 편차를 반환합니다.

>[!TIP]
>
>지표의 크기를 비례적으로 조정해야 하거나 루트 값에 의존하는 다른 통계 함수를 지원해야 하는 경우에 사용합니다.
>

## 표준 편차 {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="표준 편차"
>abstract="데이터의 표본 집단을 기반으로 표준 편차나 분산의 제곱근을 반환합니다."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL 표준편차(지표, include_zeros)]**

[!BADGE 테이블]{type="Neutral"} 데이터의 표본 집단을 기반으로 표준 편차나 분산의 제곱근을 반환합니다.

| 인수 | 설명 |
|---|---|
| | 표준 편차를 계산할 지표. |
| include_zeros | 계산에 0값을 포함할지 여부. |

**사용 사례**: 일별 매출이나 방문 횟수가 시간에 따라 얼마나 일관되는지 평가하는 등 평균과 값이 얼마나 다른지 측정합니다. 이는 변동성, 안정성 또는 비정상적인 성과 변동을 식별하는 데 도움이 됩니다.

**계산된 지표 빌더에서**: **매출** 또는 *방문 횟수*&#x200B;와 같은 지표에 *표준 편차*&#x200B;를 적용하여 선택한 분류 또는 날짜 범위 내의 값 스프레드를 계산합니다. 예를 들어 **표준 편차**(*매출*)은 일별 매출이 평균에서 얼마나 벗어나는지를 보여줍니다.

>[!TIP]
>
>*평균*&#x200B;과 함께 사용하여 예외 항목을 감지하거나 캠페인, 제품 또는 세그먼트 간 성능의 일관성을 비교하십시오.
>

## 분산 {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="분산"
>abstract="데이터의 표본 집단을 기반으로 분산을 반환합니다."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(지표, include_zeros)]**

[!BADGE 테이블]{type="Neutral"} 데이터의 표본 집단을 기반으로 분산을 반환합니다.

| 인수 | 설명 |
|---|---|
| 지표 | 분산 계산할 지표. |
| include_zeros | 계산에 0값을 포함할지 여부. |

**사용 사례**: 일별 매출 또는 세션 기간이 시간에 따라 얼마나 달라지는지 분석하는 등 데이터 집합의 값이 평균에서 얼마나 멀리 퍼져있는지 측정합니다. 이는 성능의 일관성 또는 변동 정도를 정량화하는 데 도움이 된다.

**계산된 지표 빌더에서**: **매출** 또는 *방문당 체류 시간*&#x200B;과 같은 지표에 *분산*&#x200B;을 적용하여 평균과 평균 제곱 편차를 계산합니다. 예를 들어 **Variance**(*Revenue*)은 선택한 범위에 대해 평균과 다른 수익 값을 표시합니다.

>[!TIP]
>
>**표준 편차**&#x200B;와 함께 사용하면 데이터 가변성을 더 잘 이해하고 예측할 수 없는 성능의 영역을 식별할 수 있습니다.
>

VARIANCE 방정식은 다음과 같습니다.

![](assets/variance_eq.png){width="100"}

여기서 *x*&#x200B;는 샘플 평균 [MEAN(*지표*)](#mean)이고 *n*&#x200B;은 샘플의 크기입니다.


분산을 계산하려면 전체 숫자 열을 확인합니다. 그 숫자 목록에서 먼저 평균을 계산합니다. 평균을 계산한 다음 각 항목으로 이동하여 다음 작업을 수행합니다.

1. 숫자에서 평균을 뺍니다.

1. 계산 결과를 제곱합니다.

1. 그 값을 총계에 더합니다.

전체 열에 대해 반복하여 총계 값을 하나 얻습니다. 그 총계를 열의 항목 수(열 개수)로 나눕니다. 해당 숫자는 열의 변량입니다. 단일 번호입니다. 그러나 숫자 열로 표시됩니다.

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

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers-that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

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