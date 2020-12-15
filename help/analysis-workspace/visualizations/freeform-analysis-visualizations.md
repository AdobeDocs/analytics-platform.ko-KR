---
description: Analysis Workspace에서 시각화 및 시각화 설정에 대해 알아봅니다.
keywords: Analysis Workspace
title: 시각화 개요
translation-type: tm+mt
source-git-commit: 1759bbf965e6b8d07e5a25867b73c3242dc49005
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 95%

---


# 시각화 개요

작업 공간에서는 막대 차트, 도넛 차트, 히스토그램, 선 차트, 맵, 산점도 등과 같은 데이터를 시각적으로 나타낼 수 있도록 해주는 다양한 시각화를 제공합니다. 각 시각화에는 관리할 수 있는 자체 설정이 있습니다. 자세한 내용을 보려면 시각화의 이름을 클릭합니다.

비디오 자습서:[Analysis Workspace](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/visualization-types.html)의 시각화 유형(2:57)

| 시각화 이름 | 설명 |
| --- | --- |
| [영역](/help/analysis-workspace/visualizations/area.md) | 선 그래프처럼 표시되지만 선 아래에 색상이 있는 영역이 있습니다. 여러 개의 지표가 있고 두 개 이상 지표의 교차 지점으로 표시되는 영역을 시각화하려는 경우 영역 그래프를 사용하십시오. |
| [막대](/help/analysis-workspace/visualizations/bar.md) | 하나 이상 지표에서 다양한 값을 나타내는 세로 막대를 표시합니다. |
| [글머리 기호 그래프](/help/analysis-workspace/visualizations/bullet-graph.md) | 중요한 값이 다른 성능 범위(목표)에 대해 비교되거나 측정되는 방식을 표시합니다. |
| [집단 테이블](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 집단은 지정된 기간 동안 공통적인 특성을 공유하는 사람들의 그룹입니다. 집단 분석은 예를 들어 집단이 브랜드에 어떻게 참여하는지를 알려고 할 때 유용합니다. 트렌드 변경 사항을 쉽게 찾아 응답할 수 있습니다. |
| [도넛](/help/analysis-workspace/visualizations/donut.md) | 파이 차트와 유사하게 이 시각화는 데이터를 전체의 일부 또는 세그먼트로 표시합니다. |
| [폴아웃](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | 폴아웃 보고서는 방문자가 페이지의 사전 정의된 순서를 떠나고(폴아웃) 계속 따라가는(폴스루) 위치를 보여줍니다. |
| [흐름](/help/analysis-workspace/visualizations/c-flow/flow.md) | 웹사이트와 앱의 고객 경로를 보여줍니다. |
| [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | 자유 형식 테이블은 데이터 테이블일 뿐만 아니라 대화형 시각화이기도 합니다. |
| [히스토그램](/help/analysis-workspace/visualizations/histogram.md) | 히스토그램은 막대 그래프와 유사하지만 숫자들을 범위로 그룹화합니다(버킷). |
| [가로 막대형](/help/analysis-workspace/visualizations/horizontal-bar.md) | 하나 이상 지표에서 다양한 값을 나타내는 가로 막대를 표시합니다. |
| [라인](/help/analysis-workspace/visualizations/line.md) | 일정 기간 동안 값이 어떻게 변하는지를 보여주기 위해 라인을 사용하여 지표를 나타냅니다. 라인 차트는 시간을 차원으로 사용하는 경우에만 사용할 수 있습니다. |
| [산포도](/help/analysis-workspace/visualizations/scatterplot.md) | 차원 항목과 최대 3개 지표 간의 관계를 표시합니다. |
| [요약 번호](/help/analysis-workspace/visualizations/summary-number-change.md) | 선택한 셀에 따라 이 시각화는 합계와 요약을 표시합니다. |
| [요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md) | 선택한 셀에 따라 이 시각화는 셀을 서로 비교합니다. |
| [텍스트](/help/analysis-workspace/visualizations/text.md) | 사용자 정의 텍스트를 Analysis Workspace에 추가할 수 있게 합니다. |
| [트리맵](/help/analysis-workspace/visualizations/treemap.md) | 계층형(트리 구조) 데이터를 중첩된 직사각형 세트로 표시합니다. |
| [벤](/help/analysis-workspace/visualizations/venn.md) | 최대 3개의 세그먼트(구성 요소)와 1개의 지표를 드래그하여 벤 다이어그램을 작성할 수 있습니다. |

## 시각화 패널 {#section_DC07F032FBEF4046A40F7B95C28DA018}

시각화 패널을 표시하려면 왼쪽 레일에서 **[!UICONTROL 시각화]**&#x200B;를 클릭합니다.

![단계 결과](assets/visualizations.png)

Adobe Analytics를 사용하는 경우 대부분의 시각화 유형(예: 면적, 막대, 도넛 및 라인 차트)에 익숙할 것입니다. 그렇지만 Analysis Workspace에서는 시각화 설정을 비롯하여 대화형 기능이 포함된 여러 개의 고유한 새 시각화 유형을 제공합니다.

## 시각화 설정 {#section_D3BB5042A92245D8BF6BCF072C66624B}

[!UICONTROL 시각화 설정]에 액세스하려면 시각화를 [!UICONTROL 자유 형식 패널]로 드래그한 다음 [!UICONTROL 시각화 설정] 톱니바퀴 아이콘을 클릭합니다. 

>[!IMPORTANT]
>
>표시되는 시각화 설정은 시각화에 따라 다릅니다. 모든 설정이 모든 시각화에 적용되는 것은 아닙니다. 또한 일부 고급 설정은 [히스토그램 설정](/help/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477)과 같은 특정 시각화에 대해서&#x200B;**만** 표시됩니다.

![](assets/visualization_settings.png)

| 설정 | 설명 |
| --- | --- |
| 백분율 | 값을 백분율로 표시합니다. |
| 100% 누적 | 스택 영역 또는 스택 막대 또는 가로 막대형 스택 시각화에 대한 이 설정은 차트를 &quot;100% 누적&quot; 시각화로 바꿉니다. 예: ![](assets/stacked_100_percent.png) |
| 범례 표시 | 요약 번호/요약 변경 사항 시각화에 대한 필터 세부 사항 텍스트를 숨길 수 있습니다. |
| 최대 항목 수 제한 | 시각화에 표시되는 항목 수를 제한할 수 있습니다. |
| Y축 0에 연결 | 차트에 표시된 모든 값이 0보다 매우 큰 경우, 차트 기본값에 따라 y축의 하단이 0이 아닌 값으로 지정됩니다. 이 상자를 선택하면 y축이 0이 됩니다(그리고 차트가 다시 그려짐).  |
| 표준화 | 지표를 등분 비례에 강제 적용합니다. |
| 이중 축 표시 | 지표가 두 개일 경우에만 적용됩니다. 왼쪽(한 지표에 대해)과 오른쪽(다른 지표에 대해)에 y축을 놓을 수 있습니다.  |
| 예외 항목 표시 | 데이터 예외 항목을 표시하도록 선 그래프와 자유 형식 테이블을 개선합니다.  |

## 시각화 만들기 아이콘 {#section_9C11D9DEDC42413AA53E69A71A509DFC}

어떤 시각화를 선택해야 할지 모를 경우 테이블 행에서 **[!UICONTROL 시각화 만들기]** 아이콘을 클릭합니다. 이 아이콘은 테이블 행 위로 마우스를 가져가면 나타납니다. 이 아이콘을 클릭하면 기존 학습을 토대로 사용자 데이터에 가장 적합한 시각화가 추측됩니다. 예를 들어 최대 3개의 세그먼트를 선택한 경우 벤 다이어그램이 생성됩니다. 세그먼트가 4개 이상이면 막대 차트가 생성됩니다. 다른 유형의 데이터에서는 선 그래프가 생성될 수 있습니다.

![](assets/create-visual.png)

## 시각화/패널 메뉴를 마우스 오른쪽 단추로 클릭 {#section_05B7914D4C9E443F97E2BFFDEC70240C}

시각화 또는 패널 헤더 옆을 마우스 오른쪽 단추로 클릭하면 그래프와 관련된 설정에 액세스할 수 있습니다. 다음 설정 중 일부 또는 전체를 사용할 수 있게 됩니다. 

![](assets/right-click_menu.png)

| 설정 | 설명 |
| --- | --- |
| 복사한 시각화/패널 삽입 | 복사한 요소를 프로젝트 내의 다른 위치 또는 완전히 다른 프로젝트에 붙여넣을(&quot;삽입&quot;) 수 있습니다. |
| 시각화/패널 복사 | 시각화 또는 패널을 마우스 오른쪽 단추로 클릭하고 복사할 수 있습니다. |
| 중복 시각화/패널 | 현재 시각화의 수정할 수 있는 정확한 중복을 만듭니다. |
| 모든 패널 축소 | 모든 프로젝트 패널을 축소합니다. |
| 패널의 모든 시각화 축소 | 이 프로젝트 패널의 모든 시각화를 축소합니다. |
| 모든 패널 확장 | 모든 프로젝트 패널을 확장합니다. |
| 패널의 모든 시각화 확장 | 이 프로젝트 패널의 모든 시각화를 확장합니다. |
| 설명 편집 | 시각화/패널에 대한 텍스트 설명을 추가(또는 편집)합니다. 이 설명은 프로젝트 >  프로젝트 정보 및 설정에 표시됩니다 . |
| 패널 링크 가져오기 | 프로젝트 내의 특정 패널로 사용자를 안내할 수 있습니다. |
| 시각화 링크 가져오기 | 이 링크를 복사하고 공유하여 다른 사용자를 이 시각화로 직접 보낼 수 있습니다. 사용자는 로그인해야 합니다. |
| 시작 | (흐름, 벤, 히스토그램에 대해 작동하게 됨) 현재 시각화에 대한 구성이 삭제되고, 다시 구성할 수 있는 새 패널이 열립니다.  |

## 범례 레이블 편집 {#section_94F1988CB4B9434BA1D9C6034062C3DE}

시각 자료를 더욱 잘 소비하게 만들 수 있도록 시각화 범례(폴아웃, 영역, 스택 영역, 막대, 스택 막대, 도넛, 막대 그래프, 가로 막대, 스택 가로 막대, 라인, 분산형 및 벤)에서 시리즈 이름을 바꿀 수 있습니다.

트리맵, 글머리 기호, 요약 변경 사항 또는 숫자, 텍스트, 자유 형식, 막대 그래프, 집단 또는 플로우 시각화에는 범례 편집이 적용되지 **않습니다**.

라인 차트에서 범례 레이블을 편집하려면 다음을 수행하십시오.

1. 범례 레이블 중 하나를 마우스 오른쪽 단추로 클릭합니다.
1. **[!UICONTROL 레이블 편집을 클릭합니다]**.

   ![](assets/edit-label.png)

1. 새 레이블 텍스트를 입력합니다.
1. **[!UICONTROL Enter]**&#x200B;를 눌러 저장합니다.

다음은 이 항목의 [비디오에 대한 링크](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html)입니다.
