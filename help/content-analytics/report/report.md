---
title: Content Analytics 보고
description: 자유 형식 테이블, 막대 및 분산형 등의 시각화를 사용하여 Content Analytics에 대해 보고하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 8c4bd397aa2863c7365778cb545ec42d9b0f4528
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 47%

---


# Content Analytics 보고 개요

[Analysis Workspace](/help/analysis-workspace/home.md) 내의 [!DNL Content Analytics]에 대해 보고하고, 분석을 수행하고, 통찰력을 얻습니다. 특정 Workspace [템플릿](#template)을 사용할 수 있으므로 관련 콘텐츠 인사이트로 미리 채워진 Workspace 프로젝트에 즉시 액세스할 수 있습니다.

나만의 Content Analytics 보고서를 처음부터 만들려면 다음 단계를 수행하십시오.

1. Workspace에서 [새 프로젝트](/help/analysis-workspace/build-workspace-project/create-projects.md)을(를) 만들거나 [기존 프로젝트](/help/analysis-workspace/build-workspace-project/open-projects.md)을(를) 여십시오.
1. Content Analytics 보고를 위해 [데이터 보기](/help/analysis-workspace/c-panels/panels.md#data-view)를 선택해야 합니다. Content Analytics 보고는 Content Analytics에 대해 [구성된](/help/content-analytics/config/configuration.md) 데이터 보기에서만 사용할 수 있습니다.
1. ![테이블](/help/assets/icons/Table.svg) [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) 시각화를 캔버스로 드래그합니다.
1. [특정 Content Analytics 구성 요소](components.md)와 기타 일반 [구성 요소](/help/components/overview.md)(세그먼트, 날짜 범위, 주석 등)를 사용하여 Content Analytics 인사이트를 빌드합니다.
1. 프로젝트를 향상시키려면 다른 [시각화](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)를 사용하십시오.


## 썸네일

프로젝트에서 사용하는 Content Analytics 관련 차원에 따라 썸네일이 다음 시각화에 표시됩니다.

### 자유 형식 테이블

![Content Analytics 썸네일](../assets/aca-thumbnails.png)

기본적으로 썸네일은 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)에 표시됩니다. Content Analytics 차원에 대한 썸네일 표시를 구성하려면:

* Content Analytics 차원의 헤더 행 위에 마우스를 가져다 댑니다. 예: **[!UICONTROL 자산 ID]** 또는 **[!UICONTROL 경험 ID]**.
* ![설정](/help/assets/icons/Setting.svg)을 선택합니다.
* **[!UICONTROL 행 설정]** 팝업에서 **[!UICONTROL 설정]** 아래에서 **[!UICONTROL 썸네일 표시]**&#x200B;를 선택하거나 선택 취소합니다.


### 막대(스택) 및 가로 막대(스택)

{{release-limited-testing-section}}

막대 차트의 ![Content Analytics 썸네일](/help/content-analytics/assets/aca-bar-thumbnail.png)


축소판은 세로 또는 가로 축에 범례의 일부로 표시됩니다. [막대(스택)](/help/analysis-workspace/visualizations/bar.md) 및 [가로 막대(스택)](/help/analysis-workspace/visualizations/horizontal-bar.md)의 막대 위에 마우스를 올려 놓으면 썸네일이 표시됩니다.


### 분산

{{release-limited-testing-section}}

![산포에 대한 Content Analytics 썸네일](/help/content-analytics/assets/aca-scatter-thumbnail.png)

[분산](/help/analysis-workspace/visualizations/scatterplot.md)의 데이터 포인트 위로 마우스를 가져가면 썸네일이 표시됩니다.

## 미리보기

>[!AVAILABILITY]
>
>이 섹션에 설명된 막대 및 분산형 시각화는 제한된 테스트에 있으며 사용자 환경에서 사용할 수 없을 수 있습니다. 이 메모는 기능을 일반적으로 사용할 수 있는 경우 제거됩니다. Customer Journey Analytics 릴리스 프로세스에 대한 자세한 내용은 [Customer Journey Analytics 기능 릴리스](/help/release-notes/releases.md)를 참조하십시오.
>

미리 보기 팝업 창을 열 수 있습니다. 이렇게 하려면 다음 작업을 수행하십시오.

* [자유 형식 테이블](#freeform-table)에서 ![InfoOutline](/help/assets/icons/InfoOutline.svg)을(를) 선택하십시오.
* [막대](#bar-and-horizontal-bar) 또는 [가로 막대](#bar-and-horizontal-bar) 시각화의 특정 막대 또는 [분산](#scatter) 시각화의 데이터 포인트를 선택하십시오.


다음 세부 정보를 확인할 수 있습니다.

| 경험 미리보기 | 자산 미리보기 |
|---|---|
| ![Content Analytics 경험 미리보기](../assets/aca-experience-preview.png) | ![Content Analytics 자산 미리보기](../assets/aca-asset-preview.png) |
| 차원의 이름 (예: **[!UICONTROL 경험 ID])** | 자산 차원의 이름 (예: **[!UICONTROL 자산 ID])** |
| **[!UICONTROL 노출 횟수(전체 기간)]**: 해당 경험에 대한 노출 횟수 | **[!UICONTROL 노출 횟수(전체 시간)]**: 해당 자산에 대한 노출 횟수 |
| **[!UICONTROL 자산]**: 이 경험에 포함된 자산의 수 <br/>![분류](/help/assets/icons/Breakdown.svg) **[!UICONTROL 분류]**&#x200B;를 선택해 자산을 검사합니다. | **[!UICONTROL 경험 수]**: 이 자산이 표시된 경험의 수 <br/>![분류](/help/assets/icons/Breakdown.svg) **[!UICONTROL 분류]**&#x200B;를 선택해 자산을 검사합니다. |
| **[!UICONTROL 첫 번째 노출]**: 해당 경험의 첫 번째 노출 날짜 | **[!UICONTROL 첫 번째 노출]**: 해당 자산의 첫 번째 노출 날짜 |
| **[!UICONTROL 가장 최근 노출]**: 경험의 가장 최근 노출 날짜입니다. | **[!UICONTROL 가장 최근 노출]**: 해당 자산의 가장 최근 노출 날짜 |
| **[!UICONTROL 경험 속성]**: 해당 경험의 [속성](/help/content-analytics/report/components.md#experience-attributes) | **[!UICONTROL 자산 속성]**: 해당 자산의 [속성](/help/content-analytics/report/components.md#asset-attributes) |


## 템플릿

Content Analytics [template](/help/analysis-workspace/templates/use-templates.md)을(를) 사용하여 가장 성과가 좋은 콘텐츠와 콘텐츠 특성을 알아볼 수 있습니다. 템플릿은 [웹 채널 및 참여 사용 사례](/help/analysis-workspace/templates/use-templates.md#web-engagement)의 일부이며 콘텐츠가 세부적으로 어떻게 성과를 내는지 자세히 설명합니다. 개별 자산 또는 특정 속성의 성과를 살펴볼 수 있습니다.

학습한 내용을 바탕으로, 홈 페이지에서 성과가 좋은 자산을 홍보하거나, 성과가 좋은 속성을 포함하도록 특정 세그먼트에 맞춰 콘텐츠를 개인화하거나, 오래된 콘텐츠를 교체하는 등 다양한 작업을 수행할 수 있습니다.

템플릿 사용하려면:

1. 메인 메뉴에서 **[!UICONTROL Workspace]**&#x200B;를 선택합니다.
1. Content Analytics에 구성된 데이터 보기를 선택해야 합니다.
1. 세그먼트(**[!UICONTROL 채널]**&#x200B;의 경우 **[!UICONTROL 웹]**, **[!UICONTROL 사용 사례]**의 경우 **[!UICONTROL 참여도]**)를 검색하거나 사용하여 **[!UICONTROL Content Analytics]** 템플릿을 찾고 선택합니다.
1. **[!UICONTROL 템플릿 사용]**&#x200B;을 선택합니다.
1. **[!UICONTROL 템플릿 설정]**&#x200B;대화 상자의 **[!UICONTROL 전환 지표 선택]** 대화 상자에서 지표를 선택합니다. 예를 들어 **[!UICONTROL 자산 CTR]**.
1. **[!UICONTROL 계속]**&#x200B;을 선택합니다.

[Analysis Workspace](/help/analysis-workspace/home.md)에서 **[!UICONTROL Content Analytics 개요]** 프로젝트가 열립니다. 프로젝트는 4개의 [패널](/help/analysis-workspace/c-panels/panels.md)로 구성되어 있으며, 각 패널은 특정 질문에 답변할 수 있도록 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) 및 [시각화](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)를 제공합니다.

**[!UICONTROL 콘텐츠 채널]** 분류를 사용하여 관심 있는 콘텐츠 채널의 패널을 [분류](/help/analysis-workspace/c-panels/panels.md#break-down-a-panel)할 수 있습니다. **[!UICONTROL 웹]** 또는 **[!UICONTROL 모바일]**.

![Analysis Workspace 패널의 콘텐츠 채널 분류](/help/content-analytics/assets/aca-content-channel-selector.png)

네 개의 패널은 다음과 같습니다.

* **가장 잘 수행되는 콘텐츠는 무엇입니까?**
이 패널에서는 참여와 전환을 유도하는 경험과 자산을 식별합니다. 경험은 특정 시간에 캡처된 전체 웹 페이지 또는 모바일 앱 내에서 정의된 텍스트, 에셋 및 작업 호출의 조합입니다.

   * **경험**.

     >[!NOTE]
     >
     >이러한 시각화는 Content Analytics 구성에서 [경험을 포함](/help/content-analytics/config/guided.md#experience-capture-and-definition)하도록 시스템을 구성한 경우에만 템플릿에 표시됩니다.
     > 

      * **경험 CTR**: 경험 CTR을 표시하는 [요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md) 시각화.
      * **상위 전환 경험**: 선택한 전환 지표를 기반으로 상위 전환 경험을 보여 주는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) 시각화
      * **가장 성과가 좋은 경험**: 가장 성과가 좋은 경험에 대한 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)([축소판](#thumbnails) 및 [미리 보기](#previews) 포함).

   * **자산**

      * **자산 CTR**
자산 CTR을 표시하는 [요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md) 시각화.
      * **상위 변환 자산**
선택한 전환 지표를 기반으로 상위 전환 자산을 보여 주는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) 시각화입니다.
      * **가장 성과가 좋은 자산**
성과가 가장 높은 자산의 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)([썸네일](#thumbnails) 및 [미리 보기](#previews) 포함).
Assets - 전환과 비교한 보기입니다.
자산 보기와 자산 전환의 산포도를 보여 주는 [산포도](/help/analysis-workspace/visualizations/scatterplot.md) 시각화입니다.

* **어떤 자산 속성이 전환에 가장 큰 영향을 미칩니까?**
Content Analytics은 AI 및 GenAI를 사용하여 모든 에셋에 제목, 장면 및 전경색과 같은 메타데이터 및 속성을 자동으로 할당합니다.

   * **자산 특성을 변환하는 상위 항목**
선택한 전환 지표에 따라 전환되는 상위 에셋 특성을 표시하는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md)입니다.
   * **자산 특성을 30일 이전과 비교하여 가장 많이 변환하는 항목**
선택한 전환 지표를 기준으로 이전 30일과 비교한 상위 전환 자산 특성을 표시하는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) 시각화입니다.
   * **자산 특성 데이터를 변환하는 상위 항목**
선택한 전환 지표를 기반으로 상위 전환 특성을 표시하는 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). 테이블에서 행을 선택하여 속성 추세 시각화를 업데이트합니다.
   * **특성 트렌드**
선택한 상위 전환 자산 특성에 대한 특성 트렌드를 보여 주는 [line](/help/analysis-workspace/visualizations/line.md) 시각화입니다.
   * **자산 전경색**
단일 자산 특성 범주(전경색)의 항목 성능을 비교하는 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)의 예입니다. 이 자산 속성을 다른 자산 속성 카테고리 차원으로 대체할 수 있습니다.

* **어떤 경험 속성이 전환에 가장 큰 영향을 미칩니까?**

  >[!NOTE]
  >
  >이 패널은 Content Analytics 구성에 [경험을 포함](/help/content-analytics/config/guided.md#experience-capture-and-definition)한 경우에만 표시됩니다.
  > 

  자산 속성은 이미지의 시각적 품질에 중점을 두는 반면, 경험 속성은 페이지의 텍스트에 중점을 둡니다. 아래 시각화를 통해 전환에 기여하는 경험 속성을 살펴볼 수 있습니다. 이러한 속성은 AI 및 생성형 AI 모델을 사용하여 자동으로 할당됩니다.

  패널은 다음 시각화로 구성되어 있습니다.

   * **경험 특성을 변환하는 상위 항목**
선택한 전환 지표를 기반으로 최고 전환 경험 특성을 표시하는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) 시각화입니다.
이전 30일과 비교한 최고 전환 경험 속성
선택한 전환 지표를 기반으로 이전 30일과 비교한 상위 전환 경험 특성을 표시하는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) 시각화입니다.
   * **경험 특성 데이터 변환 중 상위**
선택한 전환 지표를 기반으로 최상위 전환 경험을 표시하는 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). 테이블에서 행을 선택하여 라인 시각화를 업데이트합니다.
   * **줄**
선택한 상위 전환 경험 특성의 트렌드를 표시하는 [line](/help/analysis-workspace/visualizations/line.md) 시각화입니다.
   * **경험 키워드**
선택한 전환 지표를 기반으로 최상위 경험 키워드를 표시하는 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).

* **자산은 내 사이트의 어디에 표시됩니까?**
이 자유 형식 테이블은 가장 많이 본 에셋이 표시되는 위치를 자세히 설명합니다. 이 분석을 사용하여 성과가 좋은 페이지를 식별하고 자산 배치를 최적화합니다.

   * **조회수가 가장 많은 자산은 어디에 표시됩니까?**
모든 에셋을 차원별로 분류하여 해당 이미지가 표시되는 위치를 더 잘 이해할 수 있습니다.

     예시에서 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)([썸네일](#thumbnails) 및 [미리보기](#previews) 포함)에서는 **[!UICONTROL 자산 인식 ID]**&#x200B;가 [!UICONTROL 자산 ID] 대신 사용됩니다. 때로는 동일한 이미지가 사이트에서 다른 이미지 URL과 중복될 수 있습니다. [!UICONTROL 자산 인식 ID] 속성은 이러한 중복 항목을 단일 ID로 그룹화하는 데 도움이 됩니다.

     에셋은 페이지에서 변경될 수 있으므로 시스템에서는 각 에셋을 **[!UICONTROL 경험 ID]**(으)로 분류하여 에셋이 표시된 페이지의 버전을 식별합니다. [!UICONTROL 경험 ID]를 사이트에서 자산의 위치를 파악하는 데 도움이 되는 다른 차원으로 대체할 수 있습니다. 예를 들어 [!UICONTROL 페이지 이름], [!UICONTROL 페이지 URL] 또는 [!UICONTROL 사이트 섹션]입니다.

     또한 [!UICONTROL 자산 인식 ID]를 [!UICONTROL 자산 ID]로 바꿔서 특정 이미지 URL이 참조되는 위치에 대한 기록을 얻을 수 있습니다.


>[!MORELIKETHIS]
>
>[Content Analytics 구성 요소](components.md)
>[템플릿 사용](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
