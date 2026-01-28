---
title: 자유 형식 테이블에 여러 차원 포함
description: 자유 형식 테이블에 여러 차원을 포함하는 방법을 알아봅니다
feature: Visualizations
role: User
source-git-commit: 696bd0db44949162307d8ce7d2debed351a76cd6
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 1%

---

# 자유 형식 테이블에 여러 차원 열 포함

{{release-limited-testing}}

자유 형식 테이블에 최대 5개의 차원 열을 포함할 수 있으므로 여러 차원 항목을 나란히 볼 수 있습니다. 차원 항목의 각 행은 연결된 단일 차원 항목처럼 작동합니다.

여러 차원 열이 있는 자유 형식 테이블에 필터, 정렬, 분류 등을 적용하여 보다 심층적이고 사용자 정의 분석을 만들 수 있습니다.

## 연결된 차원 항목

[자유 형식 테이블에 여러 차원 열을 추가](#add-multiple-dimension-columns)하면 각 차원 항목 행은 연결된 단일 차원 항목처럼 작동합니다. 이 기능을 사용하면 특정 차원 조합에 대한 지표 데이터를 볼 수 있습니다.

예를 들어, 차원 열이 _구/군/시_, _장치 유형_ 및 _날짜_&#x200B;이고 지표가 _이벤트_&#x200B;인 자유 형식 테이블을 생각해 보십시오. 이 테이블의 첫 번째 행에 있는 3개 차원 항목은 연결된 단일 차원 항목이 되어 그 달 30일에 휴대폰에서 뭄바이에서 발생한 2,056개의 이벤트가 있었음을 보여 줍니다.

| Dimension: 도시 | Dimension: 장치 유형 | Dimension: 날짜 | 지표: 이벤트 |
|---------|----------|---------|---------|
| 뭄바이 | 휴대폰 | 30 | 2,056 |
| 뉴욕 | 태블릿 | 31 | 1,761 |
| 방갈로르 | 데스크톱 | 1 | 1,666 |
| 델리 | 휴대폰 | 14 | 1,396 |

이 표가 Analysis Workspace에 표시되는 방식은 다음과 같습니다.

![다중 차원 예](assets/multi-dim-example.png)

## 여러 차원 열 추가

여러 차원 열을 한 번에 하나씩 또는 일괄적으로 추가할 수 있습니다.

1. Analysis Workspace에서 자유 형식 테이블을 만듭니다.

   자세한 내용은 [시각화 개요](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)에서 [패널에 시각화 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)를 참조하십시오.

1. 자유 형식 테이블에 차원을 추가합니다. 한 번에 하나씩 차원을 추가하거나 여러 차원을 한 번에 추가할 수 있습니다.

   * 차원을 한 번에 하나씩 자유 형식 테이블로 드래그합니다. 테이블에서 기존 차원 열의 왼쪽 또는 오른쪽에 추가 차원 열을 배치합니다. 새 열이 만들어질 파란색 세로 **[!UICONTROL 추가]** 줄이 표시됩니다.

     ![개별 차원 드래그](assets/dimensions-add-individually.png)

   * 구성 요소 메뉴에서 최대 5개의 차원을 선택하여 자유 형식 테이블로 드래그합니다. 차원은 사용자가 선택한 순서대로 왼쪽에서 오른쪽으로 표에 추가됩니다.

     여러 차원을 선택하려면 ***Command*** 키(Mac의 경우) 또는 ***Ctrl*** 키(Windows의 경우)를 길게 누릅니다.

     ![여러 차원 드래그](assets/dimensions-add-multiple.png)

1. 테이블의 각 행을 단일 차원 항목으로 봅니다. 자세한 내용은 [연결된 차원 항목](#concatenated-dimension-items)을 참조하십시오.

## 테이블 필터링 및 정렬

자유 형식 테이블의 열에 필터링 및 정렬을 적용할 수 있습니다. 자유 형식 테이블의 데이터는 차원이든 지표이든 열을 기준으로 정렬할 수 있습니다. 여러 열을 동시에 정렬할 수도 있습니다.

자세한 내용은 [자유 형식 테이블 필터링 및 정렬](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)을 참조하십시오.

## 여러 차원 열 및 분류

Analysis Workspace에서는 자유 형식 테이블 내에 여러 차원을 추가하는 다음과 같은 방법을 제공합니다.

* 여러 차원 열 포함(이 문서에 설명된 대로)

* [분류 추가](/help/components/dimensions/t-breakdown-fa.md)

이 두 가지 방법 모두 다른 차원에 대해 차원을 분석할 수 있도록 해줍니다. 그러나 중요한 차이점이 있으며, 두 방법 모두 한 표에서 사용하면 더욱 심층적인 분석이 가능합니다.

### 차원 열과 분류 간의 차이점

여러 차원 열을 사용하면 다음 작업을 수행할 수 있습니다.

* 차원 항목을 여러 차원의 고유한 데이터 행에 연결합니다.

* 차원 항목이 테이블의 각 차원 열에 적용되는 경우에만 연결된 행에 차원 항목을 포함합니다. 이렇게 하려면 열 필터를 사용하여 각 차원 열에서 **[!UICONTROL 값 없음 포함]** 설정을 선택 취소합니다.

  자세한 내용은 [여러 열을 기준으로 표 정렬(고급 정렬)](#sort-tables-by-multiple-columns-advanced-sorting)을 참조하십시오.

* 사용자 지정된 데이터를 더 많이 보려면 여러 차원 및 지표 열을 기준으로 데이터를 정렬하십시오.

  자세한 내용은 [여러 열을 기준으로 표 정렬(고급 정렬)](#sort-tables-by-multiple-columns-advanced-sorting)을 참조하세요.

분류를 사용하면 다음 작업을 수행할 수 있습니다.

* 자유 형식 테이블의 차원 항목을 보조 차원으로 분류합니다. 보조 차원에 대해 최대 400개의 차원 항목을 표시할 수 있습니다.

### 여러 차원 열이 있는 테이블에 분류를 추가합니다

여러 차원 열이 있는 테이블에 분류를 추가하면 분류는 추가한 행의 연결된 차원 항목(모든 차원 열에 있음)에 적용됩니다.

![다중 정렬 분류 예제](assets/dimensions-multiple-sort-breakdown.png)

또한 분류 내에 여러 차원 열을 추가할 수 있습니다. 분류 내의 각 차원 항목 행도 연결된 단일 차원 항목처럼 작동합니다.

<!-- Add a screenshot of a breakdown with multiple cllumns, then add this sentence: "For example, you can break down the first dimension item in this table by a new concatenated dimension item that shows..." -->

분류를 추가하는 방법에 대한 자세한 내용은 [차원 분류](/help/components/dimensions/t-breakdown-fa.md)를 참조하십시오.

## 여러 차원 열에 걸쳐 있는 차원 항목을 기반으로 세그먼트를 만듭니다

여러 차원 열에 걸쳐 있는 차원 항목을 기반으로 세그먼트를 만들면 각 차원 항목이 세그먼트 정의에 포함되고, And 연산자가 연결됩니다.

세그먼트 만들기에 대한 자세한 내용은 [세그먼트 만들기](/help/components/segments/seg-create.md)를 참조하십시오.

## 지원되지 않는 차원 {#unsupported}

다음 차원 조합은 지원되지 않으며, Analysis Workspace에서는 조합을 추가하지 않거나 추가된 후 오류 메시지를 표시합니다.

* 동일한 자유 형식 테이블에서 함께 사용되는 다른 [개체 배열](/help/use-cases/object-arrays.md)을 참조하는 필드의 여러 차원입니다.

  여러 차원이 동일한 개체 배열을 참조하는 경우 동일한 자유 형식 테이블에서 여러 차원을 함께 사용할 수 있습니다.

