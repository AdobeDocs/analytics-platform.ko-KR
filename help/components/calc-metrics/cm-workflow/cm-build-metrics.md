---
description: 계산된 지표 빌더는 차원, 지표, 세그먼트 및 함수를 드래그하여 놓음으로써 컨테이너 계층 논리, 규칙 및 연산자를 기준으로 사용자 정의 지표를 만들 수 있는 캔버스를 제공함을 알아봅니다.
title: 지표 빌드
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1613'
ht-degree: 100%

---

# 계산된 지표 빌드 {#build-metrics}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="제품 호환성"
>abstract="이 계산된 지표를 Customer Journey Analytics에서 사용할 수 있는 곳(예: Analysis Workspace, Report Builder 등)을 나타냅니다. 계산된 지표 중 일부는 실험에 사용할 수 없습니다."
>additional-url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="실험에서 계산된 지표 사용"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="외부 ID"
>abstract="외부 ID를 변경하면 비즈니스 인텔리전스 도구와 같은 외부 소스에 계산된 지표가 표시되는 방식에 영향을 미칠 수 있습니다."

Customer Journey Analytics는 차원, 지표, 세그먼트 및 함수를 끌어다 놓음으로써 컨테이너 계층 논리, 규칙 및 연산자를 기준으로 사용자 정의 지표를 만들 수 있는 캔버스를 제공합니다. 이러한 통합 개발 도구를 사용하여 간단하거나 복잡한 계산된 지표를 빌드하고 저장할 수 있습니다.

계산된 지표 빌더를 사용하여 계산된 지표를 만들거나 편집할 수 있습니다. 이렇게 생성되면 계산된 지표가 구성 요소 목록에서 사용 가능하며, 조직 전체의 프로젝트에서 사용할 수 있습니다. 또는 [지표](/help/components/apply-create-metrics.md)에서 [단일 프로젝트에 대한 계산된 지표 만들기](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)에 설명된 대로 계산된 지표가 생성된 프로젝트에 대해서만 사용할 수 있는 계산된 지표를 빠르게 만들 수 있습니다.

[계산된 지표 만들기](cm-workflow.md)는 새 계산된 지표 만들기에 사용할 수 있는 다양한 옵션을 설명해 줍니다.

## 계산된 지표 빌더의 영역

**[!UICONTROL 계산된 지표 빌더]** 대화 상자는 새 계산된 지표를 만들거나 기존의 계산된 지표를 편집하는 데 사용됩니다. 대화 상자의 제목은 **[!UICONTROL 새 계산된 지표]**&#x200B;이거나 [[!UICONTROL 계산된 지표] 관리자](/help/components/calc-metrics/cm-workflow/cm-manager.md)에서 지표를 만들거나 관리하는 **[!UICONTROL 계산된 지표 편집]**&#x200B;입니다.

>[!BEGINTABS]

>[!TAB 계산된 지표 빌더]

![다음 섹션에 설명된 필드와 옵션을 보여 주는 계산된 지표 세부 정보 창.](assets/calculated-metric-builder.png)

>[!TAB 계산된 지표 만들기 또는 편집]

![다음 섹션에 설명된 필드와 옵션을 보여 주는 계산된 지표 세부 정보 창.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. 다음 세부 정보를 지정합니다(![필수](/help/assets/icons/Required.svg)는 필수 입력 항목).

   | 요소 | 설명 |
   | --- | --- |
   | **[!UICONTROL 데이터 보기]** | 계산된 지표에 대한 데이터 보기를 선택할 수 있습니다. 정의한 계산된 지표는 선택한 데이터 보기에 따라 Workspace 프로젝트에서 사용할 수 있습니다. |
   | **[!UICONTROL 프로젝트 전용 지표]** | 단일 프로젝트에 대해 생성된 계산된 지표를 편집할 때, [단일 프로젝트에 대한 계산된 지표 만들기](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)에 설명된 대로 이 대화 상자의 맨 위에 정보 상자가 나타납니다. <p>이 계산된 지표를 모든 프로젝트에서 사용할 수 있도록 하려면 **[!UICONTROL 이 지표가 모든 프로젝트에 사용할 수 있도록 설정하기 및 구성 요소 목록 추가하기]** 옵션을 선택합니다.</p> |
   | **[!UICONTROL 제목]** ![필수](/help/assets/icons/Required.svg) | 계산된 지표의 이름을 지정합니다. 예: `Conversion Rate`. |
   | **[!UICONTROL 외부 ID]** ![필수](/help/assets/icons/Required.svg) | 외부 BI 도구와 BI 확장 기능을 사용할 때 계산된 지표의 이름. 값을 재정의하지 않는 한 `undefined_xxx`로 자동 정의됩니다. |
   | **[!UICONTROL 설명]** | 세그먼트에 대한 설명을 제공합니다. 예: `Calculated metric to define the conversion rate.` 계산된 지표에 대한 공식은 이미 [!UICONTROL 요약]에서 자동으로 사용할 수 있으므로 설명할 필요가 없습니다. |
   | **[!UICONTROL 포맷]** | 계산된 지표의 형식을 선택합니다. **[!UICONTROL 소수점]**, **[!UICONTROL 시간]**, **[!UICONTROL 백분율]**, **[!UICONTROL 통화]** 중에서 선택할 수 있습니다. |
   | **[!UICONTROL 소수점 이하 자리 수]** | 선택한 형식에 소수점 이하 자리 수를 지정합니다. 선택한 형식이 소수점, 통화, 백분율인 경우에만 활성화됩니다. |
   | **[!UICONTROL 증가 트렌드를 다음으로 표시]** | 계산된 지표의 상승 추세를 ▲ **[!UICONTROL 좋음(녹색)]**&#x200B;으로 표시할지 ▼ **[!UICONTROL 나쁨(빨간색)]**&#x200B;으로 표시할지 지정합니다. |
   | **[!UICONTROL 통화]** | 계산된 지표의 통화를 지정합니다. 형식이 통화로 선택된 경우에만 활성화됩니다. |
   | **[!UICONTROL 태그]** | 하나 이상의 태그를 만들거나 적용하여 계산된 지표를 구성합니다. 이름을 입력하여 선택할 수 있는 기존 태그를 찾습니다. 또는 **[!UICONTROL ENTER]** 키를 눌러 새 태그를 추가합니다. ![CrossSize75](/help/assets/icons/CrossSize75.svg)를 선택하여 태그를 제거합니다. |
   | **[!UICONTROL 미리보기]** | 미리보기는 지난 90일을 포함하며, 이를 통해 지표를 올바르게 정의했는지 측정할 수 있습니다. |
   | **[!UICONTROL 요약]** | 계산된 지표의 정의 요약을 표시합니다. <br/>예: ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 총 주문]** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 세션]**. |
   | **[!UICONTROL 정의]** ![필수](/help/assets/icons/Required.svg) | [정의 빌더](#definition-builder)를 사용하여 세그먼트를 정의합니다. |

1. 계산된 지표 정의가 올바른지 확인하려면 계산된 지표의 결과를 지속적으로 업데이트하는 **[!UICONTROL 미리보기]**&#x200B;를 사용합니다. **[!UICONTROL 미리보기]**&#x200B;는 지난 90일을 포함하며 계산된 지표의 정의를 지속적으로 평가합니다.

   **[!UICONTROL 제품 호환성]**&#x200B;은 계산된 지표를 실험에 사용할 수 있는지 여부를 나타냅니다. 가능한 값은 다음과 같습니다.
   * **[!UICONTROL Customer Journey Analytics의 모든 곳]**: 계산된 지표는 Customer Journey Analytics 전반에서 사용할 수 있습니다.
   * **[!UICONTROL Customer Journey Analytics의 모든 곳(실험 제외)]**: 계산된 지표는 실험 패널을 제외한 Customer Journey Analytics 전반에서 사용할 수 있습니다.

1. 다음을 선택합니다.
   * 계산된 지표를 저장하려면 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.
   * 계산된 지표 사본을 저장하려면 **[!UICONTROL 다른 이름으로 저장]**&#x200B;을 사용합니다.
   * 계산된 지표에 대한 변경 사항을 취소하거나 새 계산된 지표 생성을 취소하려면 **[!UICONTROL 지표]**&#x200B;를 선택합니다.


## 정의 빌더

정의 빌더를 사용하여 차원, 지표, 세그먼트 및 함수를 끌어다 놓아 컨테이너 계층 논리, 규칙 및 연산자를 기반으로 사용자 정의 지표를 만듭니다. 해당 구성에서는 표준 지표, Adobe 정의 지표, 계산된 지표, 세그먼트, 차원 및 함수를 사용할 수 있습니다. 이러한 모든 구성 요소는 계산된 지표 빌더의 구성 요소 패널에서 사용할 수 있습니다. 또한 정의에서 연산자와 컨테이너를 사용할 수 있습니다.

![계산된 지표 만들기](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

**[!UICONTROL 정의]** 영역에서는 지표만 단일 구성 요소로 정의됩니다. 다른 모든 구성 요소는 컨테이너, 자동 줄바꿈 지표 또는 다른 컨테이너로 정의됩니다. 자세한 내용은 [컨테이너](#containers)를 참조하십시오.

### 지표

지표 추가 방법:

* 구성 요소 패널에서 ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 지표]** 구성 요소를 **[!UICONTROL 지표, 차원, 차원 항목, 세그먼트 및/또는 함수를 여기에 드래그 앤 드롭]**&#x200B;으로 끌어다 놓습니다. 특정 구성 요소를 검색하려면 구성 요소 표시줄의 ![검색](/help/assets/icons/Search.svg)을 사용할 수 있습니다.

정의의 일부로 계산된 지표를 사용하면 계산된 지표가 확장됩니다.

지표 수정 방법:

1. ![정의](/help/assets/icons/Setting.svg) 영역에서 지표 구성 요소의 **[!UICONTROL 설정]**&#x200B;을 선택합니다.
1. 팝업 대화 상자에서 지표 유형과 속성 모델을 정의할 수 있습니다. [지표 유형 및 속성](m-metric-type-alloc.md)을 확인합니다.

지표 삭제 방법:

* 지표에서 ![닫기](/help/assets/icons/Close.svg)를 선택합니다.

### 연산자

연산자를 사용하면 구성 요소 또는 컨테이너 간의 연산자를 지정할 수 있습니다. 다음 사이에 연산자가 자동으로 나타납니다.

* 컨테이너에 두 개 이상의 지표
* 컨테이너에 두 개 이상의 컨테이너
* 컨테이너에 하나 이상의 지표와 하나 이상의 컨테이너.

다음 항목을 선택할 수 있습니다.

| 기호 | 연산자 |
|:---:|---|
| ![나누기](/help/assets/icons/Divide.svg) | 나누기 (기본값) |
| ![닫기](/help/assets/icons/Close.svg) | 곱하기 |
| ![제거](/help/assets/icons/Remove.svg) | 빼기 |
| ![추가](/help/assets/icons/Add.svg) | 추가 |

### 정적 숫자

계산된 지표 정의에 정적 숫자를 추가할 수 있습니다. 정적 숫자 추가 방법:

* 컨테이너 내에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 추가]**&#x200B;를 선택합니다.
* **[!UICONTROL 정적 숫자]**&#x200B;를 선택합니다. 정적 숫자 컨테이너가 나타납니다.
* [!UICONTROL *값을 추가하려면 클릭*]&#x200B;을 선택하고 값을 입력합니다.


### 컨테이너

계산된 지표 정의에 차원, 세그먼트 및 함수를 컨테이너로 추가합니다. 일반적인 컨테이너를 추가할 수도 있습니다. 컨테이너는 수학 표현식처럼 작동하고 작업 순서를 결정합니다. 컨테이너 내의 모든 항목은 다음 구성 요소나 컨테이너보다 먼저 처리됩니다.


#### 세그먼트 컨테이너

세그먼트 컨테이너의 개념을 사용하여 [세분화된 지표](metrics-with-segments.md)를 만들 수 있습니다. 세그먼트를 사용하거나 차원에서 만든 세그먼트를 사용하여 세그먼트 컨테이너를 구성할 수 있습니다.

* 차원에서 세그먼트 컨테이너를 추가하는 방법은 다음과 같습니다.

   1. 구성 요소 패널에서 ![차원](/help/assets/icons/Dimensions.svg) **[!UICONTROL 차원]** 구성 요소를 끌어다 **[!UICONTROL 지표, 차원, 차원 항목, 세그먼트 및/또는 함수를 여기에 드래그 앤 드롭]**&#x200B;에 놓습니다. 특정 구성 요소를 검색하려면 구성 요소 표시줄의 ![검색](/help/assets/icons/Search.svg)을 사용할 수 있습니다.
   1. **[!UICONTROL 차원에서 세그먼트 만들기]** 팝업에서 세그먼트에 대한 조건을 정의합니다. 연산자 목록에서 선택한 후 값을 선택하거나 값을 입력합니다. 예를 들어 **[!UICONTROL 월]**&#x200B;은 ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`와 **[!UICONTROL 같습니다]**.
   1. **[!UICONTROL 완료]**&#x200B;를 선택합니다. **[!UICONTROL 정의]**&#x200B;에 세그먼트 컨테이너가 추가됩니다.


* 세그먼트에서 세그먼트 컨테이너를 추가하기 위해 다음을 사용할 수 있습니다.

   * 구성 요소 패널에서 ![세분화](/help/assets/icons/Segmentation.svg) **[!UICONTROL 세그먼트]** 구성 요소를 끌어다 **[!UICONTROL 지표, 차원, 차원 항목, 세그먼트 및/또는 함수를 여기에 드래그 앤 드롭]**&#x200B;에 놓습니다. 특정 세그먼트를 검색하려면 구성 요소 표시줄의 ![검색](/help/assets/icons/Search.svg)을 사용할 수 있습니다.
세그먼트 이름을 사용하여 세그먼트 컨테이너가 자동으로 **[!UICONTROL 정의]**&#x200B;에 추가됩니다.

   * ![세분화](/help/assets/icons/Segmentation.svg) **[!UICONTROL 세그먼트]** 구성 요소를 구성 요소 패널에서 일반 컨테이너로 끌어다 놓습니다. 해당 컨테이너가 세그먼트 컨테이너로 수정됩니다.

   * 컨테이너 내에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 추가]**&#x200B;를 선택합니다.

      1. **[!UICONTROL 세그먼트]**&#x200B;를 선택합니다. **[!UICONTROL 정의]**&#x200B;에 세그먼트 컨테이너가 추가됩니다.
      1. 새 세그먼트 컨테이너에서의 [!UICONTROL *선택...*] 드롭다운 메뉴에서 세그먼트를 선택합니다.

  >[!TIP]
  >
  >컨테이너에 여러 개의 세그먼트를 추가할 수 있습니다.

  컨테이너 내의 세그먼트는 세그먼트 구성 요소의 이름을 따서 명명됩니다. 예: ![세분화](/help/assets/icons/Segmentation.svg) **[!UICONTROL 웹 세션]**. 세그먼트에 대한 더 자세한 내용이 포함된 팝업이 표시되도록 하려면 ![InfoOutline](/help/assets/icons/InfoOutline.svg)을 선택합니다. 팝업에서 ![편집](/help/assets/icons/Edit.svg)을 선택해 세그먼트 정의를 편집합니다.

컨테이너에서 세그먼트를 제거하는 방법은 다음과 같습니다.

* 세그먼트 이름 옆의 ![닫기](/help/assets/icons/Close.svg)를 선택합니다.

보다 자세한 내용과 예제는 [세분화된 지표](metrics-with-segments.md)를 참조하십시오.

#### 함수 컨테이너

함수 컨테이너를 추가하기 위해 다음을 사용할 수 있습니다.

* 드래그 앤 드롭:

   1. 구성 요소 패널에서 ![함수](/help/assets/icons/Effect.svg) **[!UICONTROL 함수]** 구성 요소를 끌어다 **[!UICONTROL 지표, 차원, 차원 항목, 세그먼트 및/또는 함수를 여기에 드래그 앤 드롭]**&#x200B;에 놓습니다. 특정 함수를 검색하려면 구성 요소 표시줄의 ![검색](/help/assets/icons/Search.svg)을 사용할 수 있습니다.
   1. 함수 이름을 사용하여 함수 컨테이너가 자동으로 **[!UICONTROL 정의]**&#x200B;에 추가됩니다.

* 컨테이너 내에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 추가]**&#x200B;를 선택합니다.

   1. **[!UICONTROL 함수]**&#x200B;를 선택합니다.
   1. 컨테이너의 [!UICONTROL *선택...*] 드롭다운 메뉴에서 함수를 선택합니다.

함수 컨테이너는 함수 구성 요소의 이름을 따서 명명됩니다. 예: ![함수](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(지표)]**. 함수에 대한 더 자세한 내용이 포함된 팝업이 표시되도록 하려면 ![InfoOutline](/help/assets/icons/InfoOutline.svg)을 선택합니다. 함수에 대한 자세한 내용은 **[!UICONTROL 자세히 알아보기]**&#x200B;를 참조하십시오.

계산된 지표를 만드는 데 사용할 수 있는 함수와 함수를 사용하는 방법에 대한 자세한 내용은 [함수 사용](cm-using-functions.md)을 참조하십시오.


#### 일반 컨테이너

일반 컨테이너 추가 방법:

* 컨테이너 내에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 추가]**&#x200B;를 선택합니다.
* **[!UICONTROL 컨테이너]**&#x200B;를 선택합니다. 새로운 빈 일반 컨테이너가 **[!UICONTROL 정의]**&#x200B;에 추가됩니다. 일반 컨테이너를 사용하여 계산된 지표 정의에 계층을 중첩하거나 만들 수 있습니다.


#### 컨테이너 삭제

컨테이너를 삭제하려면 컨테이너 수준에서 ![닫기](/help/assets/icons/Close.svg)를 선택합니다.

>[!MORELIKETHIS]
>
>[함수 사용](cm-using-functions.md)
>[세그먼트](/help/components/segments/seg-overview.md)
>
