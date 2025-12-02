---
description: Analysis Workspace에서 빠른 세그먼트를 사용하는 방법을 알아봅니다.
title: 빠른 세그먼트
feature: Workspace Basics, Filters, Segments
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 84%

---

# 빠른 세그먼트

빠른 세그먼트를 사용하면 [세그먼트 빌더](/help/components/segments/seg-create.md)에서 세그먼트를 만들지 않고도 Workspace 프로젝트 내에서 데이터를 빠르게 탐색할 수 있습니다.



>[!BEGINSHADEBOX]

데모 비디오를 보려면 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace의 빠른 세그먼트](https://video.tv.adobe.com/v/345340/?captions=kor&quality=12&learn=on){target="_blank"}를 확인하십시오.

>[!ENDSHADEBOX]


빠른 세그먼트를 사용하려면 다음 사항에 유의해야 합니다.

* 빠른 세그먼트는 Workspace 프로젝트에서 직접 생성됩니다. 따라서 빠른 세그먼트는 빠른 세그먼트를 만든 Workspace 프로젝트에만 적용됩니다. Workspace 프로젝트의 빠른 세그먼트는 다른 프로젝트에서는 사용할 수 없으며 다른 사용자와 공유할 수 없습니다.
* 빠른 세그먼트에서는 세 가지 조건만 지정할 수 있습니다.
* 빠른 세그먼트는 중첩된 컨테이너나 순차적 조건을 지원하지 않습니다.
* 공유된 Workspace 프로젝트 내에서 빠른 세그먼트를 편집할 수 있습니다. 따라서 다른 사용자는 해당 사용자와 공유한 Workspace 프로젝트에서 빠른 세그먼트를 편집할 수 있습니다.

## 만들기

빠른 세그먼트는 패널에 적용됩니다. Workspace 프로젝트의 각 패널에 대해 하나 이상의 빠른 세그먼트를 만들 수 있습니다. Analysis Workspace의 모든 사용자는 빠른 세그먼트를 만들 수 있습니다.

빠른 세그먼트를 만드는 방법은 다음과 같습니다.

* 패널 상단에서 ![세그먼트 추가](/help/assets/icons/FilterAdd.svg)를 선택합니다. <br/>그런 다음 [빠른 세그먼트 빌더](#quick-segment-builder)에서 세그먼트를 직접 편집합니다.
* 구성 요소 패널에서 구성 요소를 패널 헤더의 세그먼트 드롭 영역으로 끌어다 놓습니다. 세그먼트를 끌어다 놓은 후 필터 위에 마우스를 가져다 대고 ![편집](/help/assets/icons/Edit.svg)을 선택하면 [빠른 세그먼트 빌더](#quick-segment-builder)에서 세그먼트를 편집할 수 있습니다.

드래그 앤 드롭으로 빠른 세그먼트를 생성할 때 다음 사항에 유의하십시오.

* 모든 구성 요소 유형이 지원되는 것은 아닙니다. 계산된 지표는 지원되지 않으며, 세그먼트를 작성할 수 있는 차원과 지표만 지원됩니다.
* 차원 및 지표 구성 요소의 경우 [빠른 세그먼트 빌더](#quick-segment-builder)가 자동으로 `exists` 조건을 생성합니다. 예를 들어 **[!UICONTROL City]**&#x200B;을(를) 끌어서 놓으면 **[!UICONTROL City]** **[!UICONTROL 존재함]** 조건이 만들어집니다.
* 차원 값의 경우 [빠른 세그먼트 빌더](#quick-segment-builder)에서 **[!UICONTROL equals]** 조건을 자동으로 만듭니다. 예를 들어 **[!UICONTROL City]** 차원 목록에서 **[!UICONTROL 암스테르담]**&#x200B;을(를) 끌어다 놓으면 **[!UICONTROL City]** **[!UICONTROL equals]** `Amsterdam` 조건이 만들어집니다.
* **[!UICONTROL 지정되지 않음]** 또는 **[!UICONTROL 없음]**&#x200B;을 끌어서 놓으면 [빠른 세그먼트 빌더](#quick-segment-builder)에서 자동으로 **[!UICONTROL 존재하지 않음]** 조건을 만듭니다.

만든 빠른 세그먼트는 패널 상단에 나타납니다. 빠른 세그먼트에는 연한 파란색의 얇은 왼쪽 막대가 있습니다. [빠른 세그먼트 빌더](#quick-segment-builder)를 사용하여 빠른 세그먼트를 편집 모드로 설정하면 빠른 세그먼트의 배경은 연한 파란색입니다.

패널에 생성된 빠른 세그먼트의 결과는 패널의 일부인 모든 시각화에 (AND 논리를 사용하여) 적용됩니다.


## 관리

빠른 세그먼트를 관리하려면 특정 **[!UICONTROL 빠른 세그먼트]** 위에 마우스를 가져다 댑니다.

* ![편집](/help/assets/icons/Edit.svg)을 선택하여 [빠른 세그먼트 빌더](#quick-segment-builder)를 열고 빠른 세그먼트를 편집합니다.
* 팝업을 열려면 ![InfoOutline](/help/assets/icons/InfoOutline.svg)을 선택합니다. 팝업에는 세그먼트에 대한 정보가 표시됩니다. **[!UICONTROL 모든 프로젝트에 사용 가능하게 하고 구성 요소 목록에 추가]**&#x200B;를 선택하여 구성 요소 패널에서 ![세그먼트](/help/assets/icons/Segmentation.svg) **[!UICONTROL 세그먼트]** 구성 요소 목록에 세그먼트를 추가할 수 있습니다. **[!UICONTROL 빠른 세그먼트 저장]** 대화 상자가 나타나서 세그먼트의 이름을 지정하라는 메시지가 표시됩니다. 계속하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다. [!UICONTROL 빠른 세그먼트]가 **[!UICONTROL 세그먼트]**&#x200B;로 변환됩니다. 더 이상 [빠른 세그먼트 빌더](#quick-segment-builder)를 사용하여 세그먼트를 편집할 수 없습니다. 대신, [세그먼트 빌더](seg-builder.md)를 사용하여 일반 세그먼트처럼 세그먼트를 편집해야 합니다.

## 빠른 세그먼트 빌더

빠른 세그먼트 빌더의 예는 아래와 같습니다. 이 예에서 빌더는 `Call Reason = Order Change AND Online Orders is greater than or equal 1`라는 제목의 빠른 세그먼트에 대해 열립니다. 상단의 빠른 세그먼트 두 개는 모두 [!UICONTROL 국가별 평균 주문 가격] 자유 형식 테이블 등 **[!UICONTROL 평균 주문 가격]** 대시보드 패널과 모든 시각화에 적용됩니다.

![빠른 세그먼트 빌더](assets/quick-filter-builder.png)

빠른 세그먼트 빌더는 다음과 같은 영역과 버튼으로 구성되어 있습니다.

### 헤더 영역

헤더 영역은 빠른 세그먼트의 이름, 유형 및 범위를 결정합니다. 빠른 세그먼트의 결과를 시각적으로 보여 줍니다.

| 요소 | 설명 |
|---|---|
| **[!UICONTROL 이름]** | 이름은 빠른 세그먼트 정의에서 자동으로 파생됩니다. |
| **[!UICONTROL 사용자]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![경고](/help/assets/icons/Alert.svg) | 빠른 세그먼트로 얻은 데이터의 시각적 미리보기. 막대와 백분율은 빠른 세그먼트의 결과에 포함된 전체 데이터의 비율이 얼마인지에 대한 인사이트를 제공합니다. ![경고](/help/assets/icons/AlertRed.svg)는 빠른 세그먼트가 데이터를 반환하지 않는다는 신호를 보냅니다. |
| **[!UICONTROL 포함]**<br/>**[!UICONTROL 제외]** | 패널의 데이터에 빠른 세그먼트의 결과를 포함할지 또는 제외할지 여부를 드롭다운 ![V자형 화살표](/help/assets/icons/ChevronDown.svg)에서 선택합니다. |
| **[!UICONTROL 이벤트]**<br/>**[!UICONTROL 세션]**<br/>**[!UICONTROL 개인]** | 드롭다운 메뉴 ![V자형 화살표](/help/assets/icons/ChevronDown.svg)에서 빠른 세그먼트의 범위를 선택합니다. |

### 조건 영역

조건 영역은 조건을 지정합니다(최대 3개). 각 조건에 대해 다음을 지정할 수 있습니다.

| 요소 | 설명 |
|---|---|
| **[!UICONTROL 차원]**<br/>**[!UICONTROL 지표]**<br/>**[!UICONTROL 날짜 범위]** | 드롭다운 메뉴 ![V자형 화살표](/help/assets/icons/ChevronDown.svg)에서 차원, 지표 또는 날짜 범위에 대한 조건을 지정할지 여부를 선택합니다. |
| **[!UICONTROL *구성 요소&#x200B;*]** | 조건에 대한 구성 요소 필드. 구성 요소를 [!UICONTROL *입력하여 추가*]&#x200B;하거나 목록에서 구성 요소를 선택하거나 구성 요소 패널에서 구성 요소를 드래그 앤 드롭할 수 있습니다. 조건의 구성 요소 필드에만 유사한 구성 요소를 놓을 수 있습니다. 예를 들어 차원 조건에만 구성 요소 패널의 차원 구성 요소를 놓을 수 있습니다. <br/>기존 구성 요소를 끌어다 놓아서 바꿀 수도 있습니다.<br/>![CrossSize75](/help/assets/icons/CrossSize75.svg)를 선택해 구성 요소 필드에서 구성 요소를 삭제합니다. |
| **[!UICONTROL *연산자&#x200B;*]** | 구성 요소의 연산자. 자세한 내용은 [연산자](seg-operators.md)를 참조하십시오. 차원 및 지표에만 사용할 수 있습니다. |
| **[!UICONTROL *값&#x200B;*]** | 조건에 대한 값. 선택한 연산자에 따라 목록에서 값을 선택하거나 값을 입력할 수 있습니다. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | 빠른 세그먼트에서 조건을 삭제하려면 선택합니다. |

### 버튼

| 버튼 | 설명 |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | 두 개 이상의 조건을 정의한 경우에만 사용할 수 있습니다. 조건 사이의 드롭다운 메뉴 ![V자형 화살표](/help/assets/icons/ChevronDown.svg)에서 선택합니다. 선택은 빠른 세그먼트에 대한 부울 논리를 결정합니다. 세 가지 조건이 있는 경우 논리를 섞을 수 없습니다. 부울 논리는 **[!UICONTROL AND]** 또는 **[!UICONTROL OR]**&#x200B;입니다. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | 빠른 세그먼트에 다른 조건을 추가합니다. 이 버튼은 빠른 세그먼트에 대해 하나 또는 두 개의 조건을 정의한 경우에만 사용할 수 있습니다. |
| **[!UICONTROL 적용]** | 빠른 세그먼트에 변경 사항을 적용합니다. |
| **[!UICONTROL 빌더 열기]** | **[!UICONTROL 확실합니까?]** 대화 상자의 확인 메시지가 표시됩니다. **[!UICONTROL 확인]**&#x200B;을 선택하면 더 이상 [빠른 세그먼트 빌더](#quick-segment-builder)의 세그먼트를 수정할 수 없습니다. 빠른 세그먼트의 이름이 **[!UICONTROL 세그먼트]**&#x200B;로 바뀌고 이제 왼쪽에 더 진한 파란색의 얇은 막대가 생겼습니다.<br/>일반 [세그먼트 빌더](seg-builder.md)는 **[!UICONTROL 모든 프로젝트에 이 세그먼트를 사용할 수 있도록 설정하고 구성 요소 목록에 추가]**&#x200B;하는 옵션과 함께 열립니다. <ul><li>이 옵션을 선택하고 **[!UICONTROL 적용]**&#x200B;을 선택하면 세그먼트가 구성 요소 패널의 ![세그먼트](/help/assets/icons/Segmentation.svg) **[!UICONTROL 세그먼트]** 구성 요소 목록에 추가됩니다.</li><li>이 옵션을 선택하지 않고 **[!UICONTROL 적용]**&#x200B;을 선택하면 세그먼트는 Workspace 프로젝트 전용 세그먼트로 유지됩니다.</li></ul> |
| **[!UICONTROL 취소]** | 빠른 세그먼트 생성 또는 편집을 취소하려면 선택합니다. |

## 빠른 세그먼트와 세그먼트

빠른 세그먼트는 이름에서 알 수 있듯이 빠른 세그먼트입니다. 빠른 세그먼트를 빠르게 인라인으로 만들고 편집한 후 패널에서 효과를 즉시 확인할 수 있습니다.

세그먼트는 빠른 세그먼트에 비해 다음과 같은 장점이 있습니다.

* 모든 Workspace 프로젝트에서 세그먼트를 사용할 수 있습니다.
* 세그먼트는 중첩된 계층형 [컨테이너](seg-builder.md#containers) 및 시퀀스([순차적 세그먼트](seg-sequential-build.md) 사용)를 사용하여 더 많은 복잡성을 지원합니다.


