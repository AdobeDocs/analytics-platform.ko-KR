---
description: Customer Journey Analytics용 Analysis Workspace에서 빠른 필터 사용
title: 빠른 필터
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 2%

---

# 빠른 필터

빠른 필터를 사용하면 [필터 빌더](/help/components/filters/create-filters.md)에서 필터를 만들지 않고도 Workspace 프로젝트 내의 데이터를 빠르게 탐색할 수 있습니다.


+++ 다음 비디오에서는 빠른 필터를 사용하는 방법을 보여 줍니다.

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)


+++

빠른 필터를 사용하려면 다음 사항에 유의하십시오.

* 빠른 필터는 Workspace 프로젝트에서 직접 만들어집니다. 따라서 빠른 필터는 빠른 필터를 만드는 Workspace 프로젝트에만 적용됩니다. Workspace 프로젝트의 빠른 필터는 다른 프로젝트에서 사용할 수 없으며, 다른 사용자와 공유할 수 없습니다.
* 빠른 필터의 일부로 세 가지 조건만 지정할 수 있습니다.
* 빠른 필터는 중첩된 컨테이너 또는 순차적 조건을 지원하지 않습니다.
* 공유 Workspace 프로젝트 내에서 빠른 필터를 편집할 수 있습니다. 따라서 다른 사용자는 이러한 사용자와 공유한 Workspace 프로젝트에서 빠른 필터를 편집할 수 있습니다.

## 만들기

빠른 필터는 패널에 적용됩니다. Workspace 프로젝트의 모든 패널에 대해 하나 이상의 빠른 필터를 만들 수 있습니다. Analysis Workspace의 모든 사용자는 빠른 필터를 만들 수 있습니다.

빠른 필터를 만들려면 다음 작업을 수행하십시오.

* 패널 맨 위에서 ![FilterAdd](/help/assets/icons/FilterAdd.svg)을(를) 선택합니다. <br/>그런 다음 [빠른 필터 빌더](#quick-filter-builder)에서 필터를 직접 편집합니다.
* 구성 요소 패널의 구성 요소를 패널 헤더의 필터 드롭 영역으로 드래그합니다. 드롭한 후에는 필터 위로 마우스를 가져간 후 ![편집](/help/assets/icons/Edit.svg)을 선택하여 [빠른 필터 빌더](#quick-filter-builder)에서 필터를 편집합니다.

드래그 앤 드롭을 사용하여 빠른 필터를 만들 때는 다음 사항에 유의하십시오.

* 일부 구성 요소 유형은 지원되지 않습니다. 계산된 지표는 지원되지 않으며 필터를 빌드할 수 있는 차원 및 지표만 지원됩니다.
* 차원 및 지표 구성 요소의 경우 [빠른 필터 빌더](#quick-filter-builder)에서 `exists` 조건을 자동으로 만듭니다. 예를 들어 `City`을(를) 끌어서 놓으면 `City exists` 조건이 만들어집니다.
* 차원 값의 경우 [빠른 필터 빌더](#quick-filter-builder)에서 `equals` 조건을 자동으로 만듭니다. 예를 들어 `City` 차원에서 `amsterdam`을(를) 끌어서 놓으면 조건 `City equals amsterdam`이(가) 만들어집니다.
* `unspecified` 또는 `none`을(를) 끌어서 놓으면 [빠른 필터 빌더](#quick-filter-builder)에서 자동으로 `does not exist` 조건을 만듭니다.

만든 빠른 필터 가 패널 맨 위에 나타납니다. 빠른 필터에는 연한 파란색 얇은 왼쪽 막대가 있습니다. 빠른 필터가 [빠른 필터 빌더](#quick-filter-builder)를 사용하여 편집 모드에 있는 경우 빠른 필터의 배경은 연한 파란색입니다.

패널에서 만드는 빠른 필터의 결과는 패널에 포함된 모든 시각화에 (AND 논리 사용) 적용됩니다.


## 관리

빠른 필터를 관리하려면 특정 **[!UICONTROL 빠른 필터]** 위로 마우스를 가져갑니다.

* ![편집](/help/assets/icons/Edit.svg)을 선택하여 [빠른 필터 빌더](#quick-filter-builder)를 열고 빠른 필터를 편집합니다.
* 팝업을 열려면 ![InfoOutline](/help/assets/icons/InfoOutline.svg)을(를) 선택하십시오. 팝업에 필터에 대한 정보가 표시됩니다. **[!UICONTROL 모든 프로젝트에 사용할 수 있도록 설정하기 및 구성 요소 목록 추가하기]** 구성 요소 패널의 ![필터](/help/assets/icons/Segmentation.svg) **[!UICONTROL 필터]** 구성 요소 목록에 필터를 추가하기. 필터 이름을 지정하라는 **[!UICONTROL 빠른 필터 저장]** 대화 상자가 표시됩니다. 계속하려면 **[!UICONTROL 저장]**&#x200B;을 선택하세요. [!UICONTROL 빠른 필터]이(가) **[!UICONTROL 필터]**(으)로 바뀝니다. [빠른 필터 빌더](#quick-filter-builder)를 사용하여 더 이상 필터를 편집할 수 없습니다. 대신 [필터 빌더](filter-builder.md)를 사용하여 필터를 일반 필터로 편집해야 합니다.

## 빠른 필터 빌더

빠른 필터 빌더에 대한 예는 아래를 참조하십시오. 예제에서 빌더는 제목이 `Call Reason = Order Change AND Online Orders is greater than or equal 1`인 빠른 필터에 대해 열립니다. 맨 위에 있는 두 빠른 필터 모두 [!UICONTROL 평균 주문 가격 대시보드] 패널 및 [!UICONTROL 국가별 평균 주문 가격] 자유 형식 테이블과 같은 내의 모든 시각화에 적용됩니다.

![빠른 필터 빌더](assets/quick-filter-builder.png)

빠른 필터 빌더는 다음 영역과 단추로 구성됩니다.

### 머리글 영역

헤더 영역에 따라 빠른 필터의 이름, 유형 및 범위가 결정됩니다. 빠른 필터의 결과에 대한 시각화도 표시됩니다.

| 요소 | 설명 |
|---|---|
| **[!UICONTROL 이름]** | 빠른 필터 정의에서 이름이 자동으로 파생됩니다. |
| **[!UICONTROL 사람]** <br/>![확인 표시 원](/help/assets/icons/CheckmarkCircle.svg) ![경고](/help/assets/icons/Alert.svg) | 빠른 필터로 인한 데이터의 시각적 미리 보기. 막대 및 백분율은 전체 데이터 중 빠른 필터의 결과에 속하는 데이터의 양에 대한 통찰력을 제공합니다. 빨간색 ![경고](/help/assets/icons/Alert.svg)는 빠른 필터에서 데이터를 반환하지 않는다는 신호를 보냅니다. |
| **[!UICONTROL 포함]**<br/>**[!UICONTROL 제외]** | 패널의 데이터에서 빠른 필터의 결과를 포함할지 또는 제외할지 여부를 ![VDown](/help/assets/icons/ChevronDown.svg) 드롭다운에서 선택합니다. |
| **[!UICONTROL 이벤트]**<br/>**[!UICONTROL 세션]**<br/>**[!UICONTROL 사용자]** | ![V자형 화살표](/help/assets/icons/ChevronDown.svg) 드롭다운에서 빠른 필터의 범위를 선택합니다. |

### 조건 영역

조건 영역은 조건(최대 3개)을 지정합니다. 각 조건에 대해 다음을 지정할 수 있습니다.

| 요소 | 설명 |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL 지표]**<br/>**[!UICONTROL 날짜 범위]** | 드롭다운 ![V자형 화살표](/help/assets/icons/ChevronDown.svg)에서 차원, 지표 또는 날짜 범위에 대한 조건을 지정할지 여부를 선택합니다. |
| **[!UICONTROL *구성 요소&#x200B;*]** | 조건에 대한 구성 요소 필드. 구성 요소를 [!UICONTROL *추가*]&#x200B;하거나 목록에서 구성 요소를 선택하거나 구성 요소 패널에서 구성 요소를 끌어서 놓을 수 있습니다. 조건의 구성 요소 필드에는 유사한 구성 요소만 끌어 놓을 수 있습니다. 예를 들어 차원 조건의 구성 요소 패널에서만 차원 구성 요소를 삭제할 수 있습니다. <br/>끌어다 놓아 기존 구성 요소를 바꿀 수도 있습니다.<br/>구성 요소 필드에서 구성 요소를 삭제하려면 ![CrossSize75](/help/assets/icons/CrossSize75.svg)를 선택하십시오. |
| **[!UICONTROL *연산자&#x200B;*]** | 구성 요소에 대한 연산자입니다. 자세한 내용은 [연산자](operators.md)를 참조하십시오. 차원 및 지표에만 사용할 수 있습니다. |
| **[!UICONTROL *value *]** | 조건의 값입니다. 선택한 연산자에 따라 목록에서 값을 선택하거나 값을 입력할 수 있습니다. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | 빠른 필터에서 조건을 삭제하려면 선택합니다. |

### 버튼

| 버튼 | 설명 |
|---|---|
| **[!UICONTROL 및]**<br/>**[!UICONTROL 또는]** | 두 개 이상의 조건을 정의하는 경우에만 사용할 수 있습니다. 조건 사이의 ![V자형 화살표](/help/assets/icons/ChevronDown.svg) 드롭다운에서 선택합니다. 선택 항목에 따라 빠른 필터에 대한 부울 논리가 결정됩니다. 세 가지 조건이 있는 경우 논리를 혼합할 수 없습니다. 부울 논리는 **[!UICONTROL AND]** 또는 **[!UICONTROL OR]**&#x200B;입니다. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | 빠른 필터에 다른 조건을 추가합니다. 이 단추는 빠른 필터에 대해 하나 또는 두 개의 조건을 정의한 경우에만 사용할 수 있습니다. |
| **[!UICONTROL 적용]** | 변경 사항을 빠른 필터에 적용합니다. |
| **[!UICONTROL 빌더 열기]** | **[!UICONTROL 을(를) 확인하는 메시지가 표시됩니다. 계속하시겠습니까?]** 대화 상자. **[!UICONTROL 확인]**&#x200B;을 선택하면 [빠른 필터 빌더](#quick-filter-builder)에서 더 이상 필터를 수정할 수 없습니다. 빠른 필터의 이름이 **[!UICONTROL 필터]**(으)로 바뀌고 이제 짙은 파란색 얇은 왼쪽 막대가 표시됩니다.<br/>일반 [필터 빌더](filter-builder.md)가 열리고 **[!UICONTROL 이 필터를 모든 프로젝트에 사용할 수 있도록 설정하고 구성 요소 목록에 추가]**&#x200B;할 수 있는 옵션이 제공됩니다. <ul><li>이 옵션을 선택하고 **[!UICONTROL 적용]**&#x200B;을 선택하면 필터가 구성 요소 패널의 ![필터](/help/assets/icons/Segmentation.svg) **[!UICONTROL 필터]** 구성 요소 목록에 추가됩니다.</li><li>이 옵션을 선택하지 않고 **[!UICONTROL 적용]**&#x200B;을 선택하면 필터는 Workspace 프로젝트 전용 필터로 유지됩니다.</li></ul> |
| **[!UICONTROL 취소]** | 빠른 필터 만들기 또는 편집을 취소하려면 선택합니다. |

## 빠른 필터 및 필터

빠른 필터 는 이름이 정확히 입니다. 빠른 필터를 빠르게 인라인 만들고 편집하여 패널에서 즉시 효과를 볼 수 있습니다.

필터는 빠른 필터와 비교하여 다음과 같은 이점이 있습니다.

* 필터는 모든 Workspace 프로젝트에서 사용할 수 있습니다
* 필터는 중첩된 계층형 컨테이너와 시퀀스 필터 를 사용하여 보다 복잡한 절차를 지원합니다.


