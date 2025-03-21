---
title: 컨텐츠 분석 보고
description: 콘텐츠 분석에 대한 보고 방법
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: dbbdfac312b1b7cbb6d8b6ce38a63f6d2bc18420
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 0%

---

# 컨텐츠 분석 보고 개요

{{draft-aca}}

{{release-limited-testing}}

[Analysis Workspace](/help/analysis-workspace/home.md) 내에서 Content Analytics에 대해 보고하고, 분석을 수행하고, 통찰력을 얻습니다. 특정 Workspace [template](#template)을(를) 사용할 수 있으므로 관련 콘텐츠 인사이트를 사용하여 미리 채워진 Workspace 프로젝트에 즉시 액세스할 수 있습니다.

처음부터 Content Analytics에 대한 보고를 시작하려면:

1. [Workspace에서 새 프로젝트를 만들거나](/help/analysis-workspace/build-workspace-project/create-projects.md) [기존 프로젝트를 엽니다](/help/analysis-workspace/build-workspace-project/open-projects.md).
1. Content Analytics 보고를 위해 [데이터 보기를 선택](/help/analysis-workspace/c-panels/panels.md#data-view)했는지 확인하십시오. Content Analytics 보고는 Content Analytics에 대해 [구성](/help/content-analytics/config/configuration.md)된 데이터 보기에만 사용할 수 있습니다.
1. 캔버스에서 ![테이블](/help/assets/icons/Table.svg) [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) 시각화를 드래그합니다.
1. [특정 Content Analytics 구성 요소](components.md) 및 기타 일반 [구성 요소](/help/components/overview.md)(예: 필터, 날짜 범위, 주석)을 사용하여 Content Analytics 인사이트를 구축하십시오.

## 축소판

프로젝트에서 사용하는 Content Analytics 특정 차원을 기반으로 에셋 및 차원에 대한 썸네일이 표시됩니다.

![콘텐츠 분석 썸네일](../assets/aca-thumbnails.png)

기본적으로 관련 Content Analytics 차원에 대한 썸네일이 표시됩니다. Content Analytics 차원에 대한 썸네일 표시를 구성하려면 다음 작업을 수행하십시오.

* Content Analytics 차원의 머리글 행 위로 마우스를 가져갑니다. 예: **[!UICONTROL 자산 이름]** 또는 **[!UICONTROL 경험 ID]**.
* ![설정](/help/assets/icons/Setting.svg)을 선택합니다.
* **[!UICONTROL 행 설정]** 팝업에서 **[!UICONTROL 설정]** 아래의 **[!UICONTROL 축소판 표시]**&#x200B;를 선택하거나 선택 취소합니다.


## 미리 보기

썸네일을 표시하는 Content Analytics 차원 행의 경우 미리 보기 팝업 창을 열 수 있습니다.

다음 세부 정보를 사용하여 미리보기를 열려면 다음을 수행합니다.

* ![InfoOutline](/help/assets/icons/InfoOutline.svg) 선택. 다음 세부 정보가 표시됩니다.

  | 경험 미리보기 | 에셋 미리보기 |
  |---|---|
  | ![Content Analytics 경험 미리 보기](../assets/aca-experience-preview.png) | ![Content Analytics 자산 미리 보기](../assets/aca-asset-preview.png) |
  | **[!UICONTROL 경험 이름]** | **[!UICONTROL 에셋 이름]** |
  | **[!UICONTROL 노출 횟수(항상)]**: 경험에 대한 노출 횟수. | **[!UICONTROL 노출 횟수(항상)]**: 에셋의 노출 횟수. |
  | **[!UICONTROL Assets]**: 이 경험에 포함된 에셋 수입니다. <br/>자산을 검사하려면 ![분류](/help/assets/icons/Breakdown.svg) **[!UICONTROL 분류]**&#x200B;를 선택하십시오. | **[!UICONTROL 경험]**: 이 자산이 표시되는 경험 수입니다. <br/>자산을 검사하려면 ![분류](/help/assets/icons/Breakdown.svg) **[!UICONTROL 분류]**&#x200B;를 선택하십시오. |
  | **[!UICONTROL 첫 노출]**: 경험의 첫 노출 날짜입니다. | **[!UICONTROL 첫 노출]**: 에셋의 첫 노출 날짜입니다. |
  | **[!UICONTROL 가장 최근 노출]**: 경험의 가장 최근 노출 날짜입니다. | **[!UICONTROL 가장 최근 노출]**: 에셋의 가장 최근 노출 날짜입니다. |
  | **[!UICONTROL 경험 특성]**: 경험의 [특성](/help/content-analytics/report/components.md#experience-attributes). | **[!UICONTROL 자산 특성]**: 자산의 [특성](/help/content-analytics/report/components.md#asset-attributes). |


## 템플릿

콘텐츠 분석 [템플릿](/help/analysis-workspace/templates/use-templates.md)을(를) 사용하여 가장 성과가 좋은 콘텐츠 및 콘텐츠 특성을 확인할 수 있습니다. 템플릿은 [웹 채널 및 참여 사용 사례](/help/analysis-workspace/templates/use-templates.md#web-engagement)의 일부이며 콘텐츠가 세분화된 수준에서 어떻게 수행되는지 자세히 설명합니다. 개별 에셋의 성능 또는 특정 속성을 볼 수 있습니다.

배운 내용에 따라 여러 가지 작업을 수행할 수 있습니다. 홈 페이지에서 성과가 좋은 에셋을 홍보하는 것과 같이 성과가 좋은 속성을 포함하도록 특정 세그먼트에 대한 콘텐츠를 개인화하거나 부실 상태가 되기 시작한 콘텐츠를 회전합니다.

템플릿을 사용하려면 다음 작업을 수행하십시오.

1. 메인 메뉴에서 **[!UICONTROL Workspace]**&#x200B;을(를) 선택합니다.
1. Content Analytics용으로 구성된 데이터 보기를 선택했는지 확인합니다.
1. **[!UICONTROL 콘텐츠 분석]** 템플릿을 찾거나 선택하려면 필터(**[!UICONTROL 채널]**&#x200B;의 경우 **[!UICONTROL 웹]**, **[!UICONTROL 사용 사례]**의 경우 **[!UICONTROL 참여]**)를 검색하거나 사용하십시오.
1. **[!UICONTROL 템플릿 사용]**&#x200B;을 선택합니다.
1. **[!UICONTROL 템플릿 설정]** 대화 상자의 **[!UICONTROL 전환 지표 선택]** 대화 상자에서 지표를 선택합니다. 예: **[!UICONTROL 자산 CTR]**.
1. **[!UICONTROL 계속]**&#x200B;을 선택하세요.

**[!UICONTROL Content Analytics 개요]** 프로젝트가 [Analysis Workspace](/help/analysis-workspace/home.md)에서 열립니다. 프로젝트는 4개의 [패널](/help/analysis-workspace/c-panels/panels.md)로 구성되어 있으며, 각 패널은 특정 질문에 답하기 위해 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) 및 [시각화](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)를 제공합니다.

* **성과가 가장 좋은 콘텐츠는 무엇입니까?**
이 패널을 통해 어떤 경험이 참여와 전환을 유도하는지, 해당 경험에서 어떤 에셋이 있는지를 이해할 수 있습니다. 경험은 특정 시간에 캡처되는 전체 웹 페이지입니다. 경험에는 텍스트 및 여러 개의 개별 이미지 자산이 모두 포함될 수 있습니다. 에셋은 개별 이미지입니다.

  패널은 다음 시각화로 구성됩니다.

   * **경험**

      * **경험 CTR**: [요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md) 시각화(경험 CTR 표시)
      * **상위 전환 경험**: 선택한 전환 지표에 따라 상위 전환 경험을 표시하는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) 시각화입니다.
      * **가장 성과가 좋은 경험**: 가장 성과가 좋은 경험에 대한 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)([축소판](#thumbnails) 및 [미리 보기](#previews) 포함).

   * **자산**

      * **자산 CTR**
자산 CTR을 표시하는 [요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md) 시각화.
      * **자산 변환 중 상위**
선택한 전환 지표를 기반으로 상위 전환 자산을 보여 주는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) 시각화입니다.
      * **성과가 가장 높은 자산**
성과가 가장 높은 자산의 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)([썸네일](#thumbnails) 및 [미리 보기](#previews) 포함).
      * **Assets - 보기와 전환 비교.**
자산 보기와 자산 전환의 산포도를 보여 주는 [산포도](/help/analysis-workspace/visualizations/scatterplot.md) 시각화입니다.

* **전환에 기여하는 자산 특성은 무엇입니까?**
Content Analytics은 AI 및 GenAI를 사용하여 주제, 장면, 전경색 등과 같은 모든 에셋 메타데이터를 자동으로 할당합니다. 속성은 에셋 또는 경험의 내용을 설명하는 AI가 할당한 메타데이터 태그입니다. 예: <code>전경색: 빨강</code> 은(는) 자동으로 할당된 속성입니다. 시각화를 통해 전환에 가장 많이 기여하는 에셋의 속성을 식별할 수 있습니다.

  패널은 다음 시각화로 구성됩니다.

   * **자산 특성 변환 중 상위**
선택한 전환 지표에 따라 전환되는 상위 에셋 특성을 표시하는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md)입니다.
   * **자산 특성을 30일 이전과 비교하여 가장 많이 전환함**
선택한 전환 지표를 기준으로 이전 30일과 비교한 상위 전환 자산 특성을 표시하는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) 시각화입니다.
   * **자산 특성 데이터 상위 변환**
선택한 전환 지표를 기반으로 상위 전환 특성을 표시하는 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). 테이블에서 행을 선택하여 속성 트렌드 시각화를 업데이트합니다.
   * **특성 트렌드**
선택한 상위 전환 에셋 특성에 대한 특성 트렌드를 보여 주는 [line](/help/analysis-workspace/visualizations/line.md) 시각화입니다.
   * **자산 전경색**
단일 자산 특성 범주(전경색)의 항목 성능을 비교하는 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)의 예입니다. 이 자산 속성을 다른 자산 속성 범주 차원으로 바꿀 수 있습니다.

* **전환에 기여하는 경험 특성은 무엇입니까?**
자산 속성은 이미지의 시각적 품질에 중점을 두는 반면 경험 속성은 페이지 텍스트에 중점을 둡니다. 아래 시각화를 통해 전환에 기여하는 경험 속성을 살펴볼 수 있습니다. 이러한 속성은 AI 및 GenAI 모델을 사용하여 자동으로 지정됩니다.

  패널은 다음 시각화로 구성됩니다.

   * **경험 특성을 가장 많이 변환**
선택한 전환 지표를 기반으로 최고 전환 경험 특성을 표시하는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) 시각화입니다.
   * **경험 특성을 30일 이전과 비교하여 가장 많이 전환함**
선택한 전환 지표를 기반으로 이전 30일과 비교한 상위 전환 경험 특성을 표시하는 [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) 시각화입니다.
   * **경험 특성 데이터 변환 중 상위**
선택한 전환 지표를 기반으로 최상위 전환 경험을 표시하는 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). 테이블에서 행을 선택하여 라인 시각화를 업데이트합니다.
   * **줄**
선택한 상위 전환 경험 특성의 트렌드를 표시하는 [line](/help/analysis-workspace/visualizations/line.md) 시각화입니다.
   * **경험 키워드**
선택한 전환 지표를 기반으로 최상위 경험 키워드를 표시하는 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).

* **내 사이트에 자산이 표시되는 위치**
사이트에서 가장 많이 본 에셋이 표시되는 위치를 자세히 설명하는 하나의 자유 형식 테이블로 구성된 패널입니다.

  패널은 다음 하나의 시각화로 구성됩니다.

   * **가장 많이 본 에셋은 어디에 표시됩니까?**
모든 에셋을 차원별로 분류하여 해당 이미지가 표시되는 위치를 더 잘 이해할 수 있습니다.

     예제 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)([썸네일](#thumbnails) 및 [미리 보기](#previews) 포함)에서는 [!UICONTROL 자산 ID] 대신 **[!UICONTROL 자산 인식 ID]**&#x200B;이(가) 사용됩니다. 경우에 따라 완전히 동일한 이미지가 다른 이미지 URL로 사이트에서 복제될 수 있습니다. [!UICONTROL 자산 인식 ID] 특성을 사용하면 이러한 중복을 단일 ID로 그룹화할 수 있습니다.

     페이지에서 자산을 변경할 수 있으므로 각 자산은 **[!UICONTROL 경험 ID]**(으)로 분류되어 자산이 표시된 해당 페이지의 버전을 식별합니다. [!UICONTROL 경험 ID]을(를) 사이트의 자산 위치를 이해하는 데 도움이 되는 다른 차원으로 바꿀 수 있습니다. 예: [!UICONTROL 페이지 이름], [!UICONTROL 페이지 URL] 또는 [!UICONTROL 사이트 섹션].

     [!UICONTROL 자산 인식 ID]을(를) [!UICONTROL 자산 ID]&#x200B;(으)로 변경하여 특정 이미지 URL이 참조되는 위치에 대한 레코드를 가져올 수도 있습니다.


>[!MORELIKETHIS]
>
>[콘텐츠 분석 구성 요소](components.md)
>[템플릿 사용](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
