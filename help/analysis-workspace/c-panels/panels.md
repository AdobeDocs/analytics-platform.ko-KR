---
description: 패널은 테이블 및 시각화 컬렉션입니다.
title: 패널 개요
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: ht
source-wordcount: '2129'
ht-degree: 100%

---

# 패널 개요

[!UICONTROL 패널]은 테이블 및 시각화 컬렉션입니다. Workspace의 왼쪽 상단 아이콘 또는 [빈 패널](/help/analysis-workspace/c-panels/blank-panel.md)에서 패널에 액세스할 수 있습니다. 패널은 기간, 데이터 보기 또는 분석 사용 사례에 따라 프로젝트를 구성하려는 경우에 유용합니다.

## 패널 유형

[!UICONTROL Customer Journey Analytics]을 위한 Analysis Workspace에서 다음 패널 유형을 사용할 수 있습니다.

| 패널 이름 | 설명 |
| --- | --- |
| [빈 패널](/help/analysis-workspace/c-panels/blank-panel.md) | 사용 가능한 패널 및 시각화 중에서 선택하여 분석을 시작합니다. |
| [속성](attribution.md) | 차원 및 전환 지표를 사용하여 여러 기여도 모델을 빠르게 비교하고 시각화합니다. |
| [실험](experimentation.md) | 다양한 사용자 경험, 마케팅 또는 메시징의 변화를 비교하여 어떤 것이 특정 결과를 도출하는 데 가장 적합한지 판단합니다. |
| [자유 형식](freeform-panel.md) | 무제한 비교 및 분석을 수행한 다음 시각화를 추가하여 풍부한 데이터 스토리를 전달합니다. |
| [미디어 평균 분당 시청 대상자](average-minute-audience-panel.md) | 특정 콘텐츠 또는 사용자 정의된 기간 전체에 대해 평균 분당 시청 대상자를 분석합니다. |
| [미디어 동시 뷰어](media-concurrent-viewers.md) | 최대 동시성 및 분류 및 비교 기능에 대한 세부 정보로 시간 경과에 따른 동시 뷰어를 분석합니다. |
| [미디어 재생 소요 시간](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | 재생 소요 시간 분석을 통해 최대 동시 시청이 발생하는 위치 또는 시청 감소가 발생하는 위치를 파악합니다. |
| [다음 또는 이전 항목](next-previous.md) | 사용자가 이동하는 다음 또는 이전 페이지를 표시합니다. |
| [빠른 인사이트](quickinsight.md) | 인사이트를 더 빨리 분석하고 발견하려면 자유 형식 테이블과 함께 제공되는 시각화를 신속하게 빌드합니다. |


[!UICONTROL 빠른 인사이트], [!UICONTROL 빈] 패널 및 [!UICONTROL 자유 형식] 패널은 분석을 시작하기에 좋은 위치이며 [!UICONTROL Attribution IQ]는 보다 고급 분석에 적합합니다. 캔버스 하단에서 ![AddCircle](/help/assets/icons/AddCircle.svg)을 사용할 수 있으므로 언제든지 빈 패널을 추가할 수 있습니다.

기본 시작 패널은 [!UICONTROL 자유 형식] 패널이지만 [빈 패널](/help/analysis-workspace/c-panels/blank-panel.md) 또는 [빠른 인사이트](/help/analysis-workspace/c-panels/quickinsight.md)도 기본값으로 설정할 수 있습니다. [프로젝트 및 분석 환경 설정](/help/analysis-workspace/user-preferences.md#projects--analyses-preferences)을 참조하십시오.


## 패널 만들기

패널을 만드는 방법:

* **[!UICONTROL 패널]** 왼쪽 패널의 패널을 캔버스에 드래그 앤 드롭합니다.
* [빈 패널](blank-panel.md)에서 패널을 선택합니다.
* Workspace에서 **[!UICONTROL 삽입]** 메뉴를 사용하고 패널을 선택합니다. 또는 [단축키](../build-workspace-project/fa-shortcut-keys.md)를 사용하여 패널을 삽입할 수 있습니다.

  ![패널 만들기](assets/create-panel.png)

다음과 같은 작업을 수행할 수 있습니다.

* 모든 패널 **내** ![AddCircle](/help/assets/icons/AddCircle.svg)을 선택하여 다른 시각화를 추가합니다. 시각화를 선택할 수 있는 팝업이 나타납니다.

  ![가능한 시각화를 보여 주는 팝업](assets/blank-panel.png)

  | 선택... | 다음을 만들려면... |
  |---|---|
  | ![테이블](/help/assets/icons/Table.svg) | [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![라인](/help/assets/icons/GraphTrend.svg) | [라인](/help/analysis-workspace/visualizations/line.md) |
  | ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [막대](/help/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [요약 숫자](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![텍스트](/help/assets/icons/Text.svg) | [텍스트](/help/analysis-workspace/visualizations/text.md) |
  | ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [폴아웃](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![워크플로](/help/assets/icons/GraphPathing.svg) | [플로우](/help/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![GraphAreaStacked](/help/assets/icons/GraphAreaStacked.svg) | [스택 영역](/help/analysis-workspace/visualizations/area.md) |
  | ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [코호트 테이블](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![GraphBullet](/help/assets/icons/GraphBullet.svg) | [글머리 기호](/help/analysis-workspace/visualizations/bullet-graph.md) |
  | ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [도넛](/help/analysis-workspace/visualizations/donut.md) |
  | ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![히스토그램](/help/assets/icons/Histogram.svg) | [히스토그램](/help/analysis-workspace/visualizations/histogram.md) |
  | ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [분산](/help/analysis-workspace/visualizations/scatterplot.md) |
  | ![유형](/help/assets/icons/TwoDots.svg) | [벤](/help/analysis-workspace/visualizations/venn.md) |
  | ![GraphTree](/help/assets/icons/GraphTree.svg) | [트리맵](/help/analysis-workspace/visualizations/treemap.md) |

* Workspace의 마지막 패널 **외부**&#x200B;에서 ![AddCircle](/help/assets/icons/AddCircle.svg)을 선택하여 다른 [빈 패널](blank-panel.md)을 추가합니다.


## 데이터 보기

각 패널은 [데이터 보기](/help/data-views/data-views.md)와 연결되고, 패널 오른쪽 상단의 드롭다운 메뉴에서 ![데이터](/help/assets/icons/Data.svg) **[!UICONTROL *데이터 보기 이름&#x200B;*]**으로 식별됩니다.

빈 Workspace 프로젝트를 만들면 초기 패널의 기본 데이터 보기는 Customer Journey Analytics에서 마지막으로 작업한 데이터 보기입니다.

새 패널을 만들면 기본 데이터 보기는 Workspace 프로젝트에서 마지막으로 작업한 패널의 데이터 보기를 기반으로 합니다.

>[!IMPORTANT]
>
>선택한 데이터 보기는 패널에서 시각화를 빌드할 수 있는 차원, 지표 및 세그먼트를 결정합니다.
>
>
>패널의 데이터 보기를 전환하면 해당 새 데이터 보기에서 일부 구성 요소를 사용하지 못할 수 있습니다. 전환되면 시각화가 제대로 렌더링되지 않을 수 있습니다. 다음과 같은 경고가 표시될 수 있습니다.
>
>* 이 패널에는 선택한 데이터 보기에서 활성화되지 않은 구성 요소가 포함됩니다. 데이터 보기를 변경하거나 데이터 보기에서 필수 구성 요소를 활성화하십시오.
>* 시각화를 렌더링할 수 없습니다. 열과 행을 확인하여 유효한 구성 요소가 포함되어 있는지 확인하십시오.
>

## 캘린더

패널 캘린더는 패널 내의 테이블 및 시각화에 대한 데이터 범위를 제어합니다.

>[!NOTE]
>
>![캘린더](/help/assets/icons/Calendar.svg) 날짜 범위 구성 요소가 시각화 또는 패널 내에서 (예: 세그먼트로) 사용되면 날짜 범위 구성 요소가 패널 캘린더보다 우선 적용됩니다.
>


![선택한 날짜 범위를 보여 주는 캘린더 창입니다.](assets/panel-calendar.png)

1. 시작 일자를 먼저 선택한 다음 종료 일자를 선택하여 날짜 범위를 선택합니다.
또는 [!UICONTROL *사전 설정 선택*] 드롭다운 메뉴에서 **[!UICONTROL 사전 설정]**&#x200B;을 선택할 수 있습니다.

1. 필요한 경우 **[!UICONTROL 고급 설정 표시]**&#x200B;를 선택하여 다음 작업을 수행하십시오.

   * 기본 `12:00 AM`(`0:00`) 및 `11:59 PM`(`23:59`)가 아닌 다른 **[!UICONTROL 시작 시간]** 및 **[!UICONTROL 종료 시간]**&#x200B;을 지정합니다. 종료 시간은 항상 59초를 포함합니다. 날짜 범위가 여러 날에 걸친 경우 시작 시간은 날짜 범위의 첫 번째 날에 적용되고 종료 시간은 날짜 범위의 마지막 날에 적용됩니다. **[!UICONTROL (시간 값 재설정)]**&#x200B;을 사용하여 시작 및 종료 시간을 기본값으로 재설정합니다.
   * **[!UICONTROL 패널 캘린더를 기준으로 날짜 범위 구성 요소 만들기]**. 비활성화되면 패널에 사용된 날짜 범위 구성 요소는 현재 시간을 기준으로 합니다. 활성화되면 패널에 사용된 날짜 범위 구성 요소는 패널 캘린더를 기준으로 합니다.
   * **[!UICONTROL 순환 날짜 사용]**. 활성화되면 현재 날짜와 시간이 경과함에 따라 **[!UICONTROL 지난 7일]**&#x200B;과 같은 사전 설정 날짜 범위가 동적으로 업데이트됩니다. 비활성화되면 해당 사전 설정이 적용되어 업데이트되지 않습니다.

     ![Rolling dates](assets/calendar-rolling.png)

     대괄호 안의 텍스트를 선택하여(예: **[!UICONTROL 고정된 시작 - 일별 롤링]**) 패널을 확장하고 **[!UICONTROL 시작]** 및 **[!UICONTROL 종료]**&#x200B;에 대한 세부 정보를 지정할 수 있습니다.

      1. **[!UICONTROL 시작]**, **[!UICONTROL 종료]** 또는 **[!UICONTROL 고정일]**&#x200B;을 선택합니다.
      1. **[!UICONTROL 시작]** 또는 **[!UICONTROL 종료]**&#x200B;를 선택한 경우 전체 표현식을 작성할 수 있습니다. 예: **[!UICONTROL 현재 연도]** **[!UICONTROL 종료]** **[!UICONTROL +]** `1` **[!UICONTROL 일]**. 표현식의 각 개별 부분에 적합한 값을 선택합니다.
         * 현재 값을 선택합니다. 예: **[!UICONTROL 현재 연도]**.
         * 추가 계산 값을 선택합니다. 예: **[!UICONTROL 더하기]**.
         * 추가 계산이 지정된 경우 값을 지정합니다. 예 `1`.
         * 추가 계산이 지정된 경우 계산에 사용할 기간을 선택합니다. 예: **[!UICONTROL 일]**.

     **[!UICONTROL 세부 정보 숨기기]**&#x200B;를 선택하여 순환 날짜 계산에 대한 세부 정보를 숨깁니다.

1. **[!UICONTROL 적용]**을 선택하여 캘린더를 호출한 패널에 날짜 범위를 적용합니다.
**[!UICONTROL 모든 패널에 적용]**&#x200B;을 선택하여 Workspace 프로젝트의 모든 패널에 날짜 범위를 적용합니다.


## 드롭 영역 {#dropzone}

패널 드롭 영역을 사용하면 패널 내의 모든 테이블 및 시각화에 세그먼트 및 드롭다운 세그먼트를 적용할 수 있습니다. 패널에 하나 이상의 세그먼트를 적용할 수 있습니다.

### 세그먼트

패널 세그먼트화를 시작하려면 왼쪽 패널에서 패널 드롭 영역으로 세그먼트를 끌어다 놓습니다. 패널에 세그먼트를 추가하려면 이 과정을 반복하십시오. 세그먼트는 패널 상단에 나란히 표시됩니다.

![왼쪽 패널에는 사용 가능한 지수와 패널 놓기 영역으로 드래그된 모바일 고객 지표가 표시됩니다.](assets/segment-filter.png)

#### 빠른 세그먼트

세그먼트가 아닌 구성 요소를 드롭 영역으로 직접 끌어와 빠른 세그먼트를 만들 수도 있으므로 [세그먼트 빌더](/help/components/filters/filter-builder.md)로 이동하는 데 드는 시간과 노력을 절약할 수 있습니다. 이러한 방식으로 생성된 세그먼트는 자동으로 이벤트 수준 세그먼트로 정의됩니다. 세그먼트 이름 옆의 ![편집](/help/assets/icons/Edit.svg)을 선택하여 이 정의를 빠르게 수정할 수 있습니다.


자세한 내용은 [빠른 세그먼트](/help/components/filters/quick-filters.md)를 참조하십시오.

![공개되어 드롭 영역에 드롭된 애드혹 세그먼트](assets/adhoc-segment-filter.png)

### 드롭다운 세그먼트

>[!BEGINSHADEBOX]

데모 비디오를 보려면 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [드롭다운 세그먼트](https://video.tv.adobe.com/v/30913?quality=12&learn=on&captions=kor){target="_blank"}를 확인하십시오.

{{videoaa}}

>[!ENDSHADEBOX]


#### 정적 드롭다운 세그먼트

정적 드롭다운 세그먼트를 통해 제어된 방식으로 데이터와 상호 작용할 수 있습니다. 예를 들어 태블릿, 휴대폰 또는 데스크탑 별로 패널을 분할할 수 있도록 모바일 디바이스 유형에 대한 드롭다운 세그먼트를 추가할 수 있습니다.

정적 드롭다운 세그먼트를 사용하여 여러 프로젝트를 하나로 통합할 수도 있습니다. 예를 들어 다른 국가 세그먼트가 적용된 동일한 프로젝트의 여러 버전이 있는 경우 모든 버전을 단일 프로젝트로 통합하고 국가 드롭다운 세그먼트를 추가할 수 있습니다.

![시장 채널 “직접” 세그먼트가 강조 표시된 정적 드롭다운 세그먼트입니다. ](assets/dropdown-filter-intro.png)

##### 정적 드롭다운 세그먼트 만들기

* 차원 항목을 사용하는 드롭다운 세그먼트의 경우 왼쪽 패널에서 단일 차원을 선택하여 ⇧(*Shift*) 키를 누른 상태에서 차원을 패널 드롭 영역에 놓습니다. 이 액션을 수행하면 해당 차원과 연결된 모든 차원 항목이 포함된 드롭다운 세그먼트가 생성됩니다.

  또는 차원과 연결된 특정 차원 항목만 드롭다운 세그먼트에 포함하려면 왼쪽 패널에서 원하는 차원 옆에 있는 오른쪽 화살표 아이콘을 선택합니다. 이 액션을 수행하면 사용 가능한 모든 차원 항목이 표시됩니다. ⇧+![Select](/help/assets/icons/Select.svg)(*Shift* + *선택*) 또는 ^+![선택](/help/assets/icons/Select.svg)(*제어* + *선택*)을 사용하여 이 목록에서 여러 차원 항목을 선택한 다음 ⇧ 키를 **누른 상태**&#x200B;에서 패널 드롭 영역에 놓습니다.

* 단일 구성 요소 유형을 사용하는 드롭다운 세그먼트(예: 차원, 세그먼트 또는 지표만 사용)의 경우 왼쪽 패널에서 ⇧+![선택](/help/assets/icons/Select.svg) 또는 ^+![선택](/help/assets/icons/Select.svg)을 사용하여 동일한 유형의 여러 항목을 선택합니다. 그런 다음 ⇧ 키를 **누른 상태**&#x200B;에서 항목을 패널 드롭 영역에 놓습니다.

  선택한 구성 요소로 단일 드롭다운 세그먼트가 생성됩니다.

* 구성 요소 유형을 혼합하여 사용하는 드롭다운 세그먼트(예: 지표 2개와 세그먼트 3개)의 경우 ⇧+![선택](/help/assets/icons/Select.svg) 또는 ^+![선택](/help/assets/icons/Select.svg)을 사용하여 여러 구성 요소를 선택합니다. ⇧ 키를 **누른 상태**&#x200B;에서 선택 항목을 패널 드롭 영역에 놓습니다. 이 컨텍스트에서는 모든 구성 요소 유형이 별도의 드롭다운 세그먼트로 처리됩니다. 예를 들어 선택 항목에 지표와 차원 항목을 모두 포함하면 두 개의 별도 드롭다운 세그먼트가 생성됩니다. 드롭다운 필터 하나에는 차원 항목이 포함되고 다른 드롭다운 세그먼트에는 지표가 포함됩니다.

드롭다운 세그먼트를 클릭하면 다음 컨텍스트 메뉴 옵션이 제공됩니다.

* **[!UICONTROL 드롭다운 삭제]**: 패널에서 드롭다운 세그먼트를 제거합니다.
* **[!UICONTROL 레이블 삭제]**: 드롭다운 세그먼트 위에 표시된 텍스트를 제거합니다. 레이블을 수정하려면 레이블 위로 마우스를 가져가 ![드롭다운 세그먼트 레이블 편집](/help/assets/icons/Edit.svg)을 선택합니다.
* **[!UICONTROL 레이블 추가]**: 프로젝트에 드롭다운 세그먼트를 추가하면 구성 요소 이름에 레이블이 자동으로 설정됩니다. 레이블을 삭제한 경우 이 옵션을 사용하여 다시 추가할 수 있습니다.
* **[!UICONTROL 선택 필수]**: 패널에 세그먼트가 설정되어 있어야 합니다.

##### 정적 드롭다운 세그먼트 사용

사용자는 다음 방법 중 하나로 드롭다운 세그먼트 메뉴를 사용하여 패널을 세그먼트화할 수 있습니다.

* 드롭다운 세그먼트에서 세그먼트를 선택하여 패널에 단일 세그먼트를 적용합니다.

* 드롭다운 세그먼트에서 두 개 이상의 세그먼트를 선택하여 패널에 여러 세그먼트를 적용합니다. 선택된 세그먼트를 포함하도록 패널이 세그먼트화됩니다.


#### 동적 드롭다운 세그먼트

동적 드롭다운 세그먼트를 사용하면 패널의 보고 범위 내의 데이터 및 기타 드롭다운 세그먼트의 값을 기반으로 사용 가능한 값을 결정할 수 있습니다. 예를 들어 국가 차원과 도시 차원을 사용하여 두 개의 동적 드롭다운을 만들 수 있습니다. **[!UICONTROL 국가]** 드롭다운 메뉴에서 국가를 선택하면 **[!UICONTROL 도시]** 드롭다운 메뉴가 해당 국가 내의 도시만 표시하도록 동적으로 조정됩니다.

이와 동일한 개념이 모든 차원에 적용됩니다. 즉, 패널의 날짜 범위 및 선택한 세그먼트 내에 나타나는 차원 항목만 표시됩니다. 정적 드롭다운 세그먼트에서 선택한 차원 항목은 동적 드롭다운 세그먼트에서 사용 가능한 값에 영향을 줍니다. 그러나 그 반대로는 그렇지 않습니다. 즉, 동적 드롭다운 세그먼트에서 선택한 차원 항목은 정적 드롭다운 세그먼트에서 사용 가능한 값에 영향을 주지 않습니다.

나중에 특정 차원 항목을 수집할 것으로 예상되는 경우 차원 항목을 수동으로 선택할 수 있습니다. 값이 포함되지 않도록 동적 드롭다운 세그먼트를 지워서 다른 동적 드롭다운 세그먼트에 더 많은 값이 포함되도록 할 수도 있습니다. 해당 패널의 모든 드롭다운 세그먼트에서 선택 항목을 지우려면 **[!UICONTROL 모두 재설정]**&#x200B;을 선택합니다.

동적 드롭다운 세그먼트를 만드는 방법:

* ⇧**를 누른 상태**&#x200B;에서 단일 차원을 패널 드롭 영역으로 끌어다 놓습니다.

참고: 지표, 세그먼트 또는 날짜 범위에는 동적 드롭다운 세그먼트를 사용할 수 없습니다.

동적 드롭다운 세그먼트를 클릭하면 정적 드롭다운 세그먼트와 동일한 컨텍스트 메뉴 옵션이 제공됩니다.


## 컨텍스트 메뉴

패널 헤더의 컨텍스트 메뉴를 통해(마우스 오른쪽 버튼으로 클릭) 패널의 추가 기능을 사용할 수 있습니다.

![패널 헤더에 대한 마우스 오른쪽 버튼 클릭 옵션입니다.](assets/right-click-menu.png)

다음 옵션을 사용할 수 있습니다.

| 옵션 | 설명 |
| --- | --- |
| **[!UICONTROL 복사된 패널 삽입]** | 복사한 패널을 프로젝트 내의 다른 위치 또는 다른 프로젝트에 붙여넣을 수 있습니다. |
| **[!UICONTROL 복사된 시각화 삽입]** | 복사한 시각화를 패널, 프로젝트 내 다른 위치 또는 다른 프로젝트에 붙여넣습니다. |
| **[!UICONTROL 모든 패널에 데이터 보기 적용]** | 이 패널의 데이터 보기를 프로젝트의 모든 다른 패널에 적용합니다. |
| **[!UICONTROL 패널 복사]** | 패널을 복사하여 프로젝트 내의 다른 위치 또는 다른 프로젝트에 삽입할 수 있습니다. |
| **[!UICONTROL 패널 복제]** | 현재 패널의 정확한 복제본을 만들어서 수정할 수 있습니다. |
| **[!UICONTROL 모든 패널 축소]** | 모든 프로젝트 패널을 축소합니다. |
| **[!UICONTROL 모든 패널 확장]** | 모든 프로젝트 패널을 확장합니다. |
| **[!UICONTROL 패널에서 모든 시각화 축소]** | 현재 패널의 모든 시각화를 축소합니다. |
| **[!UICONTROL 패널에서 모든 시각화 확장]** | 현재 패널의 모든 시각화를 확장합니다. |
| **[!UICONTROL 설명 편집]** | 패널에 대한 텍스트 설명을 추가(또는 편집)합니다. |
| **[!UICONTROL 패널 링크 가져오기]** | 프로젝트 내의 특정 패널로 사용자를 안내합니다. 링크를 선택하면 연결된 정확한 패널로 이동하기 전에 먼저 수신자가 로그인해야 합니다. |

## 구성

일부 패널(예: [!UICONTROL 속성], [!UICONTROL 실험], [!UICONTROL 미디어 평균 분당 시청 대상자] 등)에는 시각화를 빌드할 수 있는 구성 대화 상자가 있습니다. 패널 상단의 ![Edit](/help/assets/icons/Edit.svg)을 사용하여 구성에 액세스하고 이를 변경합니다.

![패널 구성](/help/analysis-workspace/c-panels/assets/configure-panel.png)
