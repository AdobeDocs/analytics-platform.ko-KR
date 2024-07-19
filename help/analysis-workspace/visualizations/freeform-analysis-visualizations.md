---
description: Analysis Workspace에서 데이터를 시각적으로 표현합니다.
keywords: Analysis Workspace
title: 시각화 개요
feature: Visualizations
exl-id: ca9e0561-7a54-487a-9fdc-3bcf34f9bdb1
role: User
source-git-commit: c22f2d81eddbf9ee2fb3600fd5b727fb838de740
workflow-type: tm+mt
source-wordcount: '1326'
ht-degree: 80%

---

# 시각화 개요

작업 영역에서는 막대 차트, 도넛 차트, 히스토그램, 라인 차트, 맵, 산점도 등과 같은 데이터를 시각적으로 나타낼 수 있도록 해 주는 다양한 시각화를 제공합니다. Customer Journey Analytics를 사용하는 경우 대부분의 시각화 유형이 익숙할 것입니다. 그렇지만 Analysis Workspace에서는 시각화 설정을 비롯하여 대화형 기능이 포함된 여러 개의 고유한 새 시각화 유형을 제공합니다.

## 시각화 유형

Analysis Workspace에서 다음 시각화 유형을 사용할 수 있습니다.

| 시각화 이름 | 설명 |
| --- | --- | 
| [영역](/help/analysis-workspace/visualizations/area.md)<p>![영역 아이콘](assets/Smock_GraphArea_18_N.svg)</p> | 선 그래프와 비슷하지만 선 아래에 색칠된 영역이 있습니다. 여러 개의 지표가 있고 두 개 이상 지표의 교차 지점으로 표시되는 영역을 시각화하려는 경우 영역 그래프를 사용하십시오. |
| [막대](/help/analysis-workspace/visualizations/bar.md) <p>![막대 아이콘](assets/Smock_GraphBarVertical_18_N.svg)</p> | 하나 이상 지표에서 다양한 값을 나타내는 세로 막대를 표시합니다. |
| [글머리 기호 그래프](/help/analysis-workspace/visualizations/bullet-graph.md) <p>![글머리 기호 아이콘](assets/Smock_GraphBullet_18_N.svg)</p> | 중요한 값이 다른 성능 범위(목표)에 대해 비교되거나 측정되는 방식을 표시합니다. |
| [집단 테이블](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)<p>![집단 테이블 아이콘](assets/Smock_TextNumbered_18_N.svg)</p> | *`cohort`*&#x200B;는 지정된 기간 동안 공통적인 특성을 공유하는 사람들의 그룹입니다. 집단 분석은 유지, 이탈 또는 지연 시간 분석에 유용합니다. |
| [도넛](/help/analysis-workspace/visualizations/donut.md) <p>![도넛 아이콘](assets/Smock_GraphDonut_18_N.svg)</p> | 파이 차트와 유사하게 이 시각화는 데이터를 전체의 일부 또는 필터로 표시합니다. |
| [폴아웃](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)<p>![폴아웃 아이콘](assets/Smock_ConversionFunnel_18_N.svg)</p> | 폴아웃 보고서는 사용자가 페이지의 사전 정의된 순서를 떠나고(폴아웃) 계속 따라가는(폴스루) 위치를 보여줍니다. 최종 또는 정확한 시퀀스로 설정할 수 있습니다. |
| [플로우](/help/analysis-workspace/visualizations/c-flow/flow.md)<p>![흐름 아이콘](assets/flow-icon.png)</p> | 웹 사이트와 앱을 통해 정확한 고객 경로를 보여 줍니다. |
| [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)<p>![자유 형식 테이블 아이콘](assets/Smock_ViewTable_18_N.svg)</p> | 자유 형식 테이블은 데이터 테이블일 뿐만 아니라 대화형 시각화이기도 합니다. 작업 영역에서의 데이터 분석을 위한 기초입니다. |
| [히스토그램](/help/analysis-workspace/visualizations/histogram.md)<p>![막대 그래프 아이콘](assets/Smock_GraphHistogram_18_N.svg)</p> | 히스토그램은 지표 볼륨을 기반으로 사용자, 방문 또는 이벤트를 버킷으로 버킷팅합니다. |
| [가로 막대형](/help/analysis-workspace/visualizations/horizontal-bar.md)<p>![가로 막대 아이콘](assets//Smock_GraphBarHorizontal_18_N.svg)</p> | 하나 이상 지표에서 다양한 값을 나타내는 가로 막대를 표시합니다. |
| [라인](/help/analysis-workspace/visualizations/line.md)<p>![줄 아이콘](assets/Smock_GraphTrend_18_N.svg)</p> | 일정 기간 동안 값이 어떻게 변하는지를 보여 주기 위해 라인을 사용하여 지표를 나타냅니다. 꺾은선형 차트는 x축을 따라 시간을 사용합니다. |
| [산포도](/help/analysis-workspace/visualizations/scatterplot.md) <p>![산포도 아이콘](assets/Smock_GraphScatter_18_N.svg)</p> | 차원 항목과 최대 3개 지표 간의 관계를 표시합니다. |
| [요약 번호](/help/analysis-workspace/visualizations/summary-number-change.md)<p>![요약 번호 아이콘](assets/summary-number-icon.png)</p> | 선택한 셀을 1개의 큰 숫자로 표시합니다. |
| [요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md)<p>![요약 변경 아이콘](assets/summary-change-icon.png)</p> | 선택한 셀 사이의 변화를 1개의 큰 숫자/퍼센트로 표시합니다. |
| [텍스트](/help/analysis-workspace/visualizations/text.md)<p>![산포도 아이콘](assets/Smock_Text_18_N.svg)</p> | 사용자 정의 텍스트를 Analysis Workspace에 추가할 수 있게 합니다. 패널/시각화 설명을 활용하는 것 외에도 여러분의 분석 및 통찰력에 추가 컨텍스트를 추가하는 데 유용합니다. |
| [트리맵](/help/analysis-workspace/visualizations/treemap.md)<p>![트리맵 아이콘](assets/Smock_GraphTree_18_N.svg)</p> | 계층형 (트리 구조) 데이터를 중첩된 직사각형 세트로 표시합니다. |
| [벤](/help/analysis-workspace/visualizations/venn.md)<p>![벤 아이콘](assets/venn-icon.png)</p> | 원을 사용하여 최대 3개 필터의 지표 겹침을 나타냅니다. |

## 패널에 시각화 추가

1. 시각화를 추가할 Analysis Workspace 프로젝트를 엽니다.

1. 시각화를 추가하려면 다음 방법 중 하나를 사용하십시오.

   * 왼쪽 레일에서 **시각화** 아이콘 <!-- add icon -->을(를) 선택한 다음 시각화를 추가할 패널로 드래그합니다.

     ![시각화 패널](assets/viz-rail.png)

   * 시각화를 추가할 패널에서 **더하기** 아이콘을 선택한 다음 추가할 시각화를 나타내는 아이콘을 선택합니다. 각 시각화의 아이콘 위로 마우스를 가져가 이름을 확인합니다.

     ![시각화 추가 단추](assets/visualization-add-to-panel.png)

   * [빈 패널](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=ko-KR)을 추가한 다음 추가할 시각화를 선택하십시오.

     ![빈 패널](assets/blank_panel.png)

   * Analysis Workspace 프로젝트에서 기존 패널을 마우스 오른쪽 단추로 클릭한 다음 [!UICONTROL **시각화 복제**] 또는 [!UICONTROL **시각화 복사**]&#x200B;를 선택합니다.

## 시각화 설정 맞춤화

개별 시각화 또는 만든 모든 시각화에 대한 시각화 설정을 사용자 정의할 수 있습니다.

### 단일 시각화에 대한 시각화 설정 사용자 정의

개별 시각화에 대한 [!UICONTROL 시각화 설정]에 액세스하는 경우:

1. Analysis Workspace에서 사용자 정의할 시각화 설정 위로 마우스를 가져갑니다.

1. 톱니바퀴 아이콘을 클릭합니다.

   각 시각화 유형에는 사용자 정의할 수 있는 고유 설정이 있습니다. 사용 가능한 설정에 대한 자세한 내용은 [설정](#settings)을 참조하십시오.

### 만든 모든 시각화에 대한 시각화 설정 사용자 정의

생성한 모든 시각화에 대한 설정을 사용자 정의할 수 있습니다. 자세한 내용은 [사용자 환경 설정](/help/analysis-workspace/user-preferences.md)을 참조하십시오.

## 설정 {#settings}

각 시각화에는 관리할 수 있는 자체 설정이 있습니다. 시각화 설정에 액세스하려면 설정 아이콘 ![열 설정](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)을 선택하세요.

<img src="./assets/viz-settings-line.png" alt="시각화 설정" width="50%" />

| 설정 | 설명 |
| --- | --- |
| 시각화 유형 | 데이터를 묘사하는 데 사용되는 시각 자료 유형을 변경합니다. |
| 세부 기간 | 트렌드 시각화의 경우 이 드롭다운에서 시간 단위(일, 주, 월 등)를 이 드롭다운 목록에서 다음을 수행합니다. 이 변경 사항은 데이터 소스 테이블에도 적용됩니다. |
| 백분율 | 값을 백분율로 표시합니다. |
| 100% 누적 | 스택 영역, 막대 스택 또는 가로 막대형 스택 시각화에 대한 이 설정은 차트를 “100% 스택”시각화로 전환합니다. 예: ![누적 100% 옵션 보기를 표시하는 막대 차트](assets/stacked_100_percent.png) |
| 범례 표시 | 요약 번호/요약 변경 시각화에 대한 자세한 범례 텍스트를 숨길 수 있습니다. |
| 최대 항목 수 제한 | 시각화에 표시되는 항목 수를 제한할 수 있습니다. |
| Y축 0에 연결 | 차트에 표시된 모든 값이 0보다 매우 큰 경우, 차트 기본값에 따라 y축의 하단이 0이 아닌 값으로 지정됩니다. 이 상자를 선택하면 y축이 0이 됩니다(그리고 차트가 다시 그려짐). |
| 표준화 | 지표를 등분 비례에 강제 적용합니다. 그려진 지표의 크기가 매우 다른 경우에 유용합니다. |
| 이중 축 표시 | 지표가 두 개일 경우에만 적용됩니다. 왼쪽(한 지표에 대해)과 오른쪽(다른 지표에 대해)에 y축을 놓을 수 있습니다. 그려진 지표의 크기가 매우 다른 경우에 유용합니다. |
| 예외 항목 표시 | 예외 항목 탐지를 표시하여 선 그래프 및 자유 형식 테이블을 향상시킵니다. 선 시각화의 예외 항목 탐지에는 예상 값(파선)과 예상 범위(음영 처리된 띠)가 포함됩니다. |
| 예측 표시 | 예측 값을 표시하여 선 그래프 및 자유 형식 테이블을 개선합니다. |

## 범례 {#legend}

시각화 범례를 사용하면 소스 테이블의 날짜를 시각화에 그려진 시리즈와 연결할 수 있습니다. 범례는 대화형입니다. 범례 항목을 클릭하여 시각화에서 시리즈를 표시하거나 숨길 수 있습니다. 시각화되는 데이터를 단순화하려는 경우 유용합니다.

또한 시각적 오브젝트를 보다 쉽게 사용할 수 있도록 범례 레이블의 이름을 바꿀 수 있습니다. 참고: 트리맵, 글머리 기호, 요약 변경 사항 또는 숫자, 텍스트, 자유 형식, 히스토그램, 집단 또는 플로우 시각화에는 범례 편집이 적용되지 **않습니다**.

범례 레이블을 편집하려면 다음 작업을 수행하십시오.

1. 범례 레이블 중 하나를 마우스 오른쪽 버튼으로 클릭합니다.
1. **[!UICONTROL 레이블 편집을 클릭합니다]**.

   ![범례 레이블 및 레이블 편집 옵션입니다.](assets/edit-label.png)

1. 새 레이블 텍스트를 입력합니다.
1. **[!UICONTROL Enter]**&#x200B;를 눌러 저장합니다.

## 마우스 오른쪽 버튼 클릭 메뉴 {#right-click}

시각화 헤더를 마우스 오른쪽 버튼으로 클릭하면 시각화를 위한 추가 기능을 사용할 수 있습니다. 설정은 시각화에 따라 다릅니다. 사용 가능한 일부 설정은 다음과 같습니다.

![마우스 오른쪽 단추 클릭 옵션이 표시된 추가 시각화 설정입니다. 옵션은 다음 섹션에 설명되어 있습니다.](assets/right-click.png)

| 설정 | 설명 |
| --- | --- |
| 복사한 패널/시각화 삽입 | 복사한 패널 또는 시각화를 프로젝트 내의 다른 위치 또는 완전히 다른 프로젝트에 붙여넣을 (“삽입”) 수 있습니다. |
| 시각화 복사 | 시각화를 마우스 오른쪽 버튼으로 클릭하고 복사하여 프로젝트 내의 다른 위치 또는 완전히 다른 프로젝트에 삽입할 수 있습니다. |
| [프로젝트 데이터 다운로드](/help/analysis-workspace/export/download-send.md) | 선택한 차원에 대해 최대 50,000개의 차원 항목을 CSV로 다운로드합니다. |
| [프로젝트 데이터 다운로드](/help/analysis-workspace/export/download-send.md) | 시각화 데이터 소스를 CSV로 다운로드합니다. |
| 중복 시각화 | 현재 시각화의 수정할 수 있는 정확한 중복을 만듭니다. |
| 설명 편집 | 시각화에 대한 텍스트 설명을 추가 (또는 편집)합니다. |
| 시각화 링크 가져오기 | 프로젝트 내의 특정 시각화로 사용자를 안내할 수 있습니다. 링크를 클릭하면 연결된 정확한 시각화로 이동하기 전에 먼저 수신자가 로그인해야 합니다. |
| 시작 | (플로우, 벤, 히스토그램에서 작동) 현재 시각화에 대한 구성을 삭제하여 처음부터 다시 구성할 수 있습니다. |

## 시각화 만들기 아이콘 {#quick-viz}

어떤 시각화를 선택할지 확실하지 않은 경우 테이블 행에서 **[!UICONTROL 시각화 만들기]** 아이콘을 클릭합니다(마우스 오버 시 사용 가능). 이는 시각화를 추가하는 가장 빠른 방법입니다. 이 아이콘을 클릭하면 Analysis Workspace가 기존 학습을 토대로 사용자 데이터에 가장 적합한 시각화를 추정합니다. 예를 들어 1개의 행을 선택한 경우 추세선 그래프가 생성됩니다. 3개의 필터 행을 선택한 경우 벤 다이어그램이 생성됩니다.

![빠른 시각화](assets/quick-viz.png)
