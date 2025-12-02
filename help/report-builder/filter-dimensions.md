---
title: Report Builder에서 차원 필터링
description: Customer Journey Analytics용 Report Builder에서 차원 필터링을 사용하는 방법을 설명합니다
role: User
feature: Report Builder
type: Documentation
exl-id: 5730d5f3-de76-429f-81f5-ebe6b62a9480
solution: Customer Journey Analytics
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 33%

---


# 차원 필터링

기본적으로 테이블의 각 차원 항목은 해당 차원의 상위 10개 항목을 반환합니다.

각 차원에 대해 반환된 차원 항목을 변경하려면 다음을 수행합니다.

1. 데이터 블록의 셀을 선택합니다.

1. ![명령](/help/assets/icons/Edit.svg) 패널에서 **[!UICONTROL 편집]** **[!UICONTROL 데이터 블록 편집]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL 다음]**&#x200B;을 선택하여 **[!UICONTROL 차원]** 탭을 표시합니다.

1. 표에서 구성 요소 이름 옆에 있는 ![MoreSmall](/help/assets/icons/MoreSmall.svg)을 선택합니다.

   ![줄임표 아이콘 옵션](./assets/image27.png){zoomable="yes"}

1. 팝업 메뉴에서 **[!UICONTROL 필터 차원]**&#x200B;을 선택하여 **[!UICONTROL 필터 차원]** 창을 표시합니다.

1. **Type**(으)로 **가장 자주 사용하는 항목** 또는 **[!UICONTROL 특정]**&#x200B;을(를) 선택하십시오.

   ![필터 차원 창에서 선택한 특정 옵션입니다.](./assets/image28.png){zoomable="yes"}

1. 선택한 [필터 형식](#filter-type)을(를) 기반으로 적절한 옵션을 선택하십시오.

1. 필터를 추가하려면 **[!UICONTROL 적용]**&#x200B;을 선택하십시오.

1. Report Builder는 추가된 필터를 확인하는 알림을 표시합니다.

적용된 필터를 표시하려면 차원 위로 마우스를 가져갑니다. 필터가 적용된 차원에는 차원 이름 옆에 ![필터](/help/assets/icons/Filter.svg) 필터 아이콘이 표시됩니다.

## 필터 및 정렬 순서 변경

데이터 블록을 필터링하고 정렬하는 데 사용되는 지표 옆에 ![ArrowUp](/help/assets/icons/ArrowUp.svg) 또는 ![ArrowDown](/help/assets/icons/ArrowDown.svg)이(가) 나타납니다. 화살표 방향은 지표가 오름차순으로 정렬되는지 또는 내림차순으로 정렬되는지 여부를 나타냅니다.

정렬 순서를 변경하려면:

- 정렬 순서를 전환하려면 지표 옆에 있는 ![ArrowUp](/help/assets/icons/ArrowUp.svg) 또는 ![ArrowDown](/help/assets/icons/ArrowDown.svg)을 선택합니다.

데이터 블록을 필터링하고 정렬하는 데 사용되는 지표를 변경하려면:

1. 추가 옵션을 표시하려면 테이블 빌더에서 원하는 지표 구성 요소 위로 마우스를 가져갑니다.

2. 기본 지표로 ![ArrowDown](/help/assets/icons/ArrowDown.svg)을(를) 선택합니다.

   ![테이블 빌더 및 지표](./assets/image30.png){zoomable="yes"}



## 필터 유형

차원 항목을 필터링하는 방법에는 두 가지가 있습니다. [가장 자주 사용하는 항목](#most-popular) 및 [특정](#specific-filtering)

### **[!UICONTROL 최고 인기 항목]**

**[!UICONTROL 가장 자주 사용하는 항목]** 옵션을 사용하면 지표 값을 기반으로 차원 항목을 동적으로 필터링할 수 있습니다. 최고 인기 항목 은 지표 값을 기반으로 순위가 가장 높은 차원 항목을 반환합니다. 기본적으로 처음 10개의 차원 항목이 나열되며 데이터 블록에 추가된 첫 번째 지표를 기준으로 정렬됩니다.

![가장 자주 사용하는 옵션입니다.](./assets/image29.png){zoomable="yes"}


#### 페이지 및 행 옵션

**[!UICONTROL 페이지]** 및 **[!UICONTROL 행]** 필드를 사용하여 데이터를 순차적 그룹 또는 페이지로 나눕니다. 이 기능을 사용하면 최상위 값이 아닌 순위가 지정된 행 값을 보고서로 가져올 수 있습니다. 또한 50,000개의 행 제한을 초과하는 데이터를 가져올 때 특히 유용합니다.

페이지의 기본값은 `1`이고 행의 기본값은 `10`입니다. 이러한 기본값은 각 페이지에 10개의 데이터 행이 있음을 의미합니다. 페이지 1은 상위 10개 항목을 반환하고 페이지 2는 다음 10개 항목을 반환하는 식입니다.

아래 테이블에는 페이지 및 행 값과 결과 출력의 예가 나와 있습니다.

| 페이지 | 행 | 출력 |
|------|--------|----------------------|
| 1 | 10 | 상위 10개 항목 |
| 2 | 10 | 11~20번 항목 |
| 1 | 100 | 상위 100개 항목 |
| 2 | 100 | 101~200번 항목 |
| 2 | 50,000 | 50,001~100,000번 항목 |

아래 표에는 페이지 및 행의 최소값과 최대값이 나와 있습니다.

|       | 최소값 | 최대값 |
|-------|---------------:|---------------:|
| 시작 페이지 | 1 | 5,000만 |
| 행 수 | 1 | 50,000 |


#### “값 없음” 포함

Customer Journey Analytics에서 일부 차원은 *값 없음* 항목을 수집합니다. **[!UICONTROL 값 없음 포함]** 설정을 사용하면 보고서에서 이러한 값을 제외할 수 있습니다. 예를 들어 제품 SKU 키를 기반으로 하는 제품 이름 분류와 같은 분류를 만들 수 있습니다. 특정 제품 SKU가 특정 제품 이름 분류로 설정되지 않은 경우 해당 제품 이름 값이 *값 없음*(으)로 설정됩니다.

**[!UICONTROL 기본적으로 &quot;값 없음&quot;]**&#x200B;이 선택됩니다. 값이 없는 항목을 제외하려면 이 옵션을 선택 취소합니다.

#### 기준별 필터링

모든 기준이 충족되는지 또는 충족되는 기준이 있는지 여부에 따라 차원 항목을 필터링할 수 있습니다.

필터링 기준을 설정하려면 다음을 수행합니다.

1. 연산자 드롭다운 메뉴에서 연산자를 선택합니다. 기본적으로 **[!UICONTROL 구문 포함]**&#x200B;이(가) 선택되어 있습니다.

   ![연산자 목록입니다.](./assets/image31.png){zoomable="yes"}

1. 검색어를 입력하십시오.

1. ![추가](/help/assets/icons/Add.svg) **[!UICONTROL 행 추가]**&#x200B;를 선택하여 선택을 확인하고 다른 기준 항목을 추가합니다.

1. 기준 항목을 제거하려면 ![CrossSize75](/help/assets/icons/CrossSize75.svg)을(를) 선택하십시오.

최대 10개의 기준 항목을 포함할 수 있습니다.

### **[!UICONTROL 별]**

**[!UICONTROL 특정]** 옵션을 사용하면 각 차원에 대해 고정된 차원 항목 목록을 만들 수 있습니다. **[!UICONTROL 특정]** 필터링 유형을 사용하여 필터에 포함할 정확한 차원 항목을 지정합니다. 목록이나 셀 범위에서 항목을 선택할 수 있습니다.

![특정 옵션 및 선택한 항목입니다.](./assets/image32.png){zoomable="yes"}

#### 목록에서

1. **[!UICONTROL 목록에서]** 옵션을 선택하여 차원 항목을 검색하고 선택합니다.

   **목록에서** 옵션을 선택하면 **[!UICONTROL Dimension 항목]** 목록이 이벤트 수로 정렬된 차원 항목으로 채워집니다.

   ![목록에서 옵션 및 사용 가능한 항목입니다.](./assets/image33.png){zoomable="yes"}

1. 목록을 검색하려면 ![검색](/help/assets/icons/Search.svg) **[!UICONTROL _항목 추가_]**&#x200B;에 검색어를 입력하십시오.

1. 지난 90일 간의 데이터에 포함되지 않은 항목을 검색하려면 **[!UICONTROL 지난 6개월 동안의 항목 표시]**&#x200B;를 선택하여 검색을 확장합니다. 지난 6개월 동안의 데이터가 로드된 후 Report Builder은 링크를 **[!UICONTROL 지난 18개월 동안의 항목 표시]**(으)로 업데이트합니다.

1. **[!UICONTROL 선택한 항목]** 목록에서 항목을 삭제하려면 ![CrossSize75](/help/assets/icons/CrossSize75.svg)을(를) 선택하십시오.

1. **[!UICONTROL 선택한 항목]** 목록에서 항목을 이동하려면 항목을 드래그 앤 드롭하거나 ![MoreSmall](/help/assets/icons/MoreSmall.svg)을 선택하여 컨텍스트 메뉴를 표시하고 이동 옵션에서 선택하십시오.

1. **[!UICONTROL 적용]**&#x200B;을 선택합니다.

Report Builder는 적용한 특정 필터링을 표시하도록 목록을 업데이트합니다.

#### 셀 범위에서

**셀 범위에서** 옵션을 선택하여 일치시킬 차원 항목 목록이 포함된 셀 범위를 선택합니다.

![셀 범위 하나를 선택하는 From 셀 범위 옵션 및 필드입니다.](./assets/image37.png){zoomable="yes"}

셀 범위를 선택할 때 다음 제한 사항을 고려하십시오.

- 범위에는 하나 이상의 셀이 있어야 합니다.
- 범위는 50,000개 이상의 셀을 포함할 수 없습니다.
- 범위는 중단되지 않은 단일 행 또는 열에 있어야 합니다.

선택 항목에는 빈 셀이나 특정 차원 항목과 일치하지 않는 값이 있는 셀이 포함될 수 있습니다.


### 빠르게 차원 필터링

현재 필터가 적용되지 않은 차원을 필터링하려면 다음을 수행합니다.

1. 차원에 대해 ![V자형 화살표](/help/assets/icons/ChevronRight.svg)를 선택하십시오. 예를 들어 **[!UICONTROL 상호 작용 채널]**&#x200B;입니다.

1. 필터에 추가할 차원 항목을 두 번 선택합니다. 또는 하나 이상의 차원 항목을 선택하고 선택 항목을 ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]** 섹션으로 끌어서 놓습니다.

   ![차원 탭과 차원 목록입니다.](./assets/quickly-filter.png){zoomable="yes"}

