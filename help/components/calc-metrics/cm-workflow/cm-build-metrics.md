---
description: 계산된 지표 빌더는 차원, 지표, 필터 및 함수를 드래그하여 놓음으로써 컨테이너 계층 논리, 규칙 및 연산자를 기준으로 사용자 지정 지표를 만들 수 있는 캔버스를 제공합니다. 이러한 통합 개발 도구를 사용하여 간단한 계산된 지표나 복잡한 고급 계산된 지표를 빌드하고 저장할 수 있습니다.
title: 계산된 지표 작성
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: 37209097327ffb142068b5df184c07c7c8021442
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 계산된 지표 작성 {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_productcompatibility"
>title="제품 호환성"
>abstract="이 계산된 지표를 Customer Journey Analytics에서 사용할 수 있는 곳(예: Analysis Workspace, Report Builder 등)을 나타냅니다. 계산된 지표 중 일부는 실험에 사용할 수 없습니다."
>additional-url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="실험에서 계산된 지표 사용"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_externalid"
>title="외부 ID"
>abstract="외부 ID를 변경하면 비즈니스 인텔리전스 도구와 같은 외부 소스에 계산된 지표가 표시되는 방식에 영향을 미칠 수 있습니다."

<!-- markdownlint-enable MD034 -->


**[!UICONTROL 계산된 지표 빌더]** 대화 상자를 사용하여 새 계산된 지표를 만들거나 기존 계산된 지표를 편집합니다. 대화 상자의 제목은 [[!UICONTROL 계산된 지표] 관리자](/help/components/calc-metrics/cm-workflow/cm-manager.md)에서 만들거나 관리하는 지표에 대해 **[!UICONTROL 새 계산된 지표]** 또는 **[!UICONTROL 계산된 지표 편집]**&#x200B;입니다.

>[!BEGINTABS]

>[!TAB 계산된 지표 빌더]

![다음 섹션에 설명된 필드와 옵션을 표시하는 계산된 지표 세부 정보 창](assets/calculated-metric-builder.png)

>[!TAB 계산된 지표 만들기 또는 편집]

![다음 섹션에 설명된 필드와 옵션을 표시하는 계산된 지표 세부 정보 창](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. 다음 세부 정보를 지정합니다(![필수](/help/assets/icons/Required.svg)는 필수 입력 항목).

   | 요소 | 설명 |
   | --- | --- |
   | **[!UICONTROL 데이터 보기]** | 계산된 지표에 대한 데이터 보기를 선택할 수 있습니다.  정의한 계산된 지표는 선택한 데이터 보기에 따라 Workspace 프로젝트에서 사용할 수 있습니다. |
   | **[!UICONTROL 프로젝트 전용 지표]** | 지표를 만든 프로젝트에서만 볼 수 있고 지표가 구성 요소 목록에 추가되지 않는다는 것을 설명하는 정보 상자입니다. **[!UICONTROL 이 지표를 모든 프로젝트에 사용할 수 있도록 설정하고 구성 요소 목록에 추가]**&#x200B;하여 해당 설정을 변경합니다. 이 정보 상자는 **[!UICONTROL 선택 항목에서 지표 만들기]**&#x200B;를 사용하여 Workspace에서 지표를 만들고 함수(예: **[!UICONTROL 평균]** 또는 **[!UICONTROL 중간값]**)를 선택한 경우에만 표시됩니다. 나중에 [구성 요소 정보](/help/components/use-components-in-workspace.md#component-info)를 사용하여 만들어진 지표를 편집합니다. |
   | **[!UICONTROL 제목]** ![필수](/help/assets/icons/Required.svg) | 계산된 지표의 이름을 지정합니다(예: `Conversion Rate`). |
   | **[!UICONTROL 외부 ID]** ![필수](/help/assets/icons/Required.svg) | 외부 BI 도구 및 BI 확장 기능을 사용할 때 계산된 지표의 이름입니다. 값을 재정의하지 않으면 값이 `undefined_xxx`(으)로 자동 정의됩니다. |
   | **[!UICONTROL 설명]** | 필터에 대한 설명을 입력하십시오(예: `Calculated metric to define the conversion rate.`). [!UICONTROL 요약]에서 공식을 이미 자동으로 사용할 수 있으므로 계산된 지표에 대한 수식을 설명할 필요가 없습니다. |
   | **[!UICONTROL 포맷]** | 계산된 지표의 형식을 선택하십시오. **[!UICONTROL 십진수]**, **[!UICONTROL 시간]**, **[!UICONTROL 백분율]** 및 **[!UICONTROL 통화]** 중에서 선택할 수 있습니다. |
   | **[!UICONTROL 소수점 이하 자리 수]** | 선택한 형식에 대한 소수점 이하 자리 수를 지정합니다. 선택한 형식이 십진수, 통화 및 백분율인 경우에만 활성화됩니다. |
   | **[!UICONTROL 증가 트렌드를 다음으로 표시]** | 계산된 지표의 증가 트렌드를 ▲ **[!UICONTROL 양호(녹색)]** 또는 ▼ **[!UICONTROL 불량(빨간색)]**&#x200B;으로 표시할지 여부를 지정합니다. |
   | **[!UICONTROL 통화]** | 계산된 지표의 통화를 지정합니다. 선택한 포맷이 통화인 경우에만 활성화됩니다. |
   | **[!UICONTROL 태그]** | 하나 이상의 태그를 생성하거나 적용하여 계산된 지표를 구성합니다. 이름을 입력하여 선택할 수 있는 기존 태그를 찾습니다. 또는 **[!UICONTROL Enter]**&#x200B;를 눌러 새 태그를 추가하십시오. ![CrossSize75](/help/assets/icons/CrossSize75.svg)를 선택하여 태그를 제거합니다. |
   | **[!UICONTROL 미리보기]** | 미리보기는 지난 90일을 포함하며 지표를 올바르게 정의했는지 여부를 측정하는 방법입니다. |
   | **[!UICONTROL 요약]** | 계산된 지표 정의의 요약을 표시합니다. <br/>예: ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 총 주문 수]** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 세션]**. |
   | **[!UICONTROL 정의]** ![필수](/help/assets/icons/Required.svg) | [정의 빌더](#definition-builder)를 사용하여 필터를 정의합니다. |

1. 계산된 지표 정의가 올바른지 확인하려면 계산된 지표 결과의 지속적으로 업데이트된 **[!UICONTROL 미리 보기]**&#x200B;를 사용하십시오. **[!UICONTROL 미리 보기]**&#x200B;은(는) 지난 90일을 처리하고 계산된 지표의 정의를 계속 평가합니다.

   **[!UICONTROL 제품 호환성]**&#x200B;은(는) 계산된 지표를 실험에 사용할 수 있는지 여부를 나타냅니다. 가능한 값:
   * **[!UICONTROL Customer Journey Analytics의 모든 곳]**: 계산된 지표는 모든 Customer Journey Analytics 전체에서 사용할 수 있습니다.
   * **[!UICONTROL Customer Journey Analytics의 모든 곳(실험 제외)]**: 계산된 지표는 실험 패널을 제외하고 모든 Customer Journey Analytics 전체에서 사용할 수 있습니다.

1. 선택:
   * 계산된 지표를 저장하려면 **[!UICONTROL 저장]**&#x200B;하세요.
   * 계산된 지표의 복사본을 저장하려면 **[!UICONTROL 다른 이름으로 저장]**&#x200B;하세요.
   * 계산된 지표에 대한 변경 내용을 취소하거나 새 계산된 지표 만들기를 취소하려면 **[!UICONTROL 취소]**&#x200B;하십시오.


## 정의 빌더

정의 빌더를 사용하여 차원, 지표, 필터 및 함수를 드래그하여 놓음으로써 컨테이너 계층 논리, 규칙 및 연산자를 기준으로 사용자 정의 지표를 만들 수 있습니다. 해당 구성에서는 표준 지표, Adobe 정의 지표, 계산된 지표, 필터, 차원 및 함수를 사용할 수 있습니다. 이러한 모든 구성 요소는 계산된 지표 빌더의 구성 요소 패널에서 사용할 수 있습니다. 또한 정의에서 연산자와 컨테이너를 사용할 수 있습니다.

![계산된 지표 만들기](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

지표만 **[!UICONTROL 정의]** 영역에서 단일 구성 요소로 정의됩니다. 다른 모든 구성 요소는 컨테이너, 래핑 지표 또는 기타 컨테이너로 정의됩니다. 자세한 내용은 [컨테이너](#containers)를 참조하십시오.

### 지표

지표를 추가하려면:

* 구성 요소 패널의 ![이벤트](/help/assets/icons/Event.svg) **[!UICONTROL 지표]** 구성 요소를 **[!UICONTROL 여기에 지표, 차원 항목, 필터 및/또는 함수를 끌어다 놓기]**&#x200B;합니다. 구성 요소 모음에서 ![검색](/help/assets/icons/Search.svg)을 사용하여 특정 구성 요소를 검색할 수 있습니다.

계산된 지표를 정의의 일부로 사용하면 계산된 지표가 확장됩니다.

지표를 수정하려면 다음을 수행합니다.

1. **[!UICONTROL 정의]** 영역의 지표 구성 요소에서 ![설정](/help/assets/icons/Setting.svg)을 선택합니다.
1. 팝업 대화 상자에서 지표 유형 및 속성 모델을 정의할 수 있습니다. [지표 유형 및 속성](m-metric-type-alloc.md)을 참조하세요.

지표를 삭제하려면 다음을 수행하십시오.

* 지표에서 ![닫기](/help/assets/icons/Close.svg)를 선택합니다.

### 연산자

연산자를 사용하면 구성 요소나 컨테이너 간에 연산자를 지정할 수 있습니다. 다음 사이에 연산자가 자동으로 표시됩니다.

* 컨테이너에 있는 두 개 이상의 지표
* 컨테이너에 있는 둘 이상의 컨테이너,
* 컨테이너 내에 하나 이상의 지표 및 하나 이상의 컨테이너가 있습니다.

다음 항목을 선택할 수 있습니다.

| 기호 | 연산자 |
|:---:|---|
| ![나누기](/help/assets/icons/Divide.svg) | 나누기(기본값) |
| ![닫기](/help/assets/icons/Close.svg) | 곱하기 |
| ![제거](/help/assets/icons/Remove.svg) | 빼기 |
| ![추가](/help/assets/icons/Add.svg) | 이벤트가 복제되지 않도록 하면서 현재 이벤트 변수에 |

### 정적 수

계산된 지표 정의에 정수를 추가할 수 있습니다. 정적 수를 추가하려면 다음을 수행합니다.

* 컨테이너 내에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**&#x200B;을(를) 선택합니다.
* **[!UICONTROL 정적 숫자]**&#x200B;을(를) 선택하십시오. 정적 숫자 컨테이너가 나타납니다.
* 값을 추가하려면 [!UICONTROL *클릭*]&#x200B;을 선택하고 값을 입력하십시오.


### 컨테이너

차원, 필터 및 함수를 계산된 지표 정의에 컨테이너로 추가합니다. 일반 컨테이너를 추가할 수도 있습니다. 컨테이너는 수학 표현식처럼 작동하고 작업 순서를 결정합니다. 컨테이너 내의 모든 항목은 다음 구성 요소 또는 컨테이너 전에 처리됩니다.


#### 필터 컨테이너

필터 컨테이너의 개념을 사용하여 [필터링된 지표](metrics-with-segments.md)을(를) 만듭니다. 필터를 사용하거나 차원에서 만든 필터를 사용하여 필터 컨테이너를 구성할 수 있습니다.

* 차원에서 필터 컨테이너를 추가하려면 다음을 수행합니다.

   1. 구성 요소 패널에서 ![Dimension](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimension]** 구성 요소를 **[!UICONTROL 여기에 지표, 차원 항목, 필터 및/또는 함수를 드래그하여 놓으십시오]**. 구성 요소 모음에서 ![검색](/help/assets/icons/Search.svg)을 사용하여 특정 구성 요소를 검색할 수 있습니다.
   1. **[!UICONTROL Dimension에서 필터 만들기]** 팝업에서 필터 조건을 정의합니다. 연산자 목록에서 를 선택하고 값을 선택하거나 값을 입력합니다. 예를 들어 **[!UICONTROL Month]** **[!UICONTROL equals]** ![V자형 화살표](/help/assets/icons/ChevronDown.svg) `Sep 2024`입니다.
   1. **[!UICONTROL 완료]**&#x200B;를 선택합니다. 필터 컨테이너가 **[!UICONTROL 정의]**&#x200B;에 추가됩니다.


* 필터에서 필터 컨테이너를 추가하려면 다음을 사용할 수 있습니다.

   * 구성 요소 패널의 ![세그먼테이션](/help/assets/icons/Segmentation.svg) **[!UICONTROL 필터]** 구성 요소를 **[!UICONTROL 여기에 지표, 차원 항목, 필터 및/또는 함수를 끌어다 놓기]**&#x200B;합니다. 구성 요소 막대에서 ![검색](/help/assets/icons/Search.svg)을 사용하여 특정 필터를 검색할 수 있습니다.
필터 이름을 사용하여 필터 컨테이너를 **[!UICONTROL 정의]**&#x200B;에 자동으로 추가합니다.

   * 구성 요소 패널의 ![세그먼테이션](/help/assets/icons/Segmentation.svg) **[!UICONTROL 필터]** 구성 요소를 일반 컨테이너로 끌어서 놓습니다. 컨테이너가 필터 컨테이너로 수정됩니다.

   * 컨테이너 내에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**&#x200B;을(를) 선택합니다.

      1. **[!UICONTROL 필터]**&#x200B;를 선택하십시오. 필터 컨테이너가 **[!UICONTROL 정의]**&#x200B;에 추가됩니다.
      1. 새 필터 컨테이너의 [!UICONTROL *선택..*] 드롭다운 메뉴에서 필터를 선택합니다.

  >[!TIP]
  >
  >한 컨테이너에 필터를 두 개 이상 추가할 수 있습니다.

  컨테이너의 필터 이름은 필터 구성 요소의 이름을 따서 지정합니다. 예: ![세그먼테이션](/help/assets/icons/Segmentation.svg) **[!UICONTROL 웹 세션]**. 필터에 대한 세부 정보가 포함된 팝업을 표시하려면 ![InfoOutline](/help/assets/icons/InfoOutline.svg)을(를) 선택하십시오. 팝업에서 ![편집](/help/assets/icons/Edit.svg)을 선택하여 필터 정의를 편집합니다.

컨테이너에서 필터를 제거하려면 다음 작업을 수행하십시오.

* 필터 이름 옆에 있는 ![닫기](/help/assets/icons/Close.svg)를 선택합니다.

자세한 내용과 예제는 [필터링된 지표](metrics-with-segments.md)를 참조하세요.

#### 함수 컨테이너

함수 컨테이너를 추가하려면 다음을 사용할 수 있습니다.

* 드래그 앤 드롭:

   1. 구성 요소 패널에서 ![함수](/help/assets/icons/Effect.svg) **[!UICONTROL 함수]** 구성 요소를 **[!UICONTROL 여기에 지표, 차원 항목, 필터 및/또는 함수를 드래그하여 놓으십시오]**. 구성 요소 모음에서 ![검색](/help/assets/icons/Search.svg)을 사용하여 특정 함수를 검색할 수 있습니다.
   1. 함수 이름을 사용하여 함수 컨테이너를 **[!UICONTROL 정의]**&#x200B;에 자동으로 추가합니다.

* 컨테이너 내에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**&#x200B;을(를) 선택합니다.

   1. **[!UICONTROL 함수]**&#x200B;을(를) 선택하십시오.
   1. 컨테이너의 [!UICONTROL *선택...*] 드롭다운 메뉴에서 함수를 선택합니다.

함수 컨테이너의 이름은 함수 구성 요소의 이름을 따서 지정합니다. 예를 들어 ![함수](/help/assets/icons/Effect.svg) **[!UICONTROL 제곱근(지표)]**&#x200B;입니다. ![InfoOutline](/help/assets/icons/InfoOutline.svg)을(를) 선택하여 기능에 대한 세부 정보가 포함된 팝업을 표시합니다. 함수에 대한 자세한 내용을 보려면 **[!UICONTROL 자세히 알아보기]**&#x200B;를 선택하십시오.

함수 사용 방법과 계산된 지표를 만드는 데 사용할 수 있는 함수에 대한 자세한 내용은 [함수 사용](cm-using-functions.md)을 참조하세요.


#### 일반 컨테이너

일반 컨테이너를 추가하려면 다음 작업을 수행하십시오.

* 컨테이너 내에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** 선택
* **[!UICONTROL 컨테이너]**&#x200B;를 선택합니다. 새 빈 제네릭 컨테이너가 **[!UICONTROL 정의]**&#x200B;에 추가됩니다. 일반 컨테이너를 사용하여 계산된 지표 정의에 계층을 중첩하거나 생성할 수 있습니다.


#### 컨테이너 삭제

컨테이너를 삭제하려면 컨테이너 수준에서 ![닫기](/help/assets/icons/Close.svg)를 선택합니다.

>[!MORELIKETHIS]
>
>[함수 사용](cm-using-functions.md)
>[필터](/help/components/filters/filters-overview.md)
>

