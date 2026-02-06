---
title: 시각화
description: Customer Journey Analytics의 다양한 BI 도구에서 BI 확장에 대한 시각화 사용 사례
solution: Customer Journey Analytics
feature: Data Views
role: User
exl-id: a357facb-d536-4c81-847c-a6f0d3f041e7
source-git-commit: 20ead546897ad517840f95a5ec4dcd7f830afe8c
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 24%

---

# 시각화


Customer Journey Analytics에서 사용할 수 있는 시각화를 BI 도구의 사용 가능한 시각화를 사용하여 유사하게 만드는 방법을 이해하려고 합니다.

+++ Customer Journey Analytics

Customer Journey Analytics에는 다양한 시각화가 있습니다. 가능한 모든 시각화에 대한 소개와 개요는 [시각화](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)를 참조하십시오.

+++

+++ BI 도구

>[!BEGINTABS]

>[!TAB Power BI 데스크톱]

## 비교

대부분의 Customer Journey Analytics 시각화의 경우 Power BI Desktop은 동등한 경험을 제공합니다. 아래 표를 참조하십시오.

| 아이콘 | Customer Journey Analytics 시각화 | Power BI 데스크탑 시각화 |
| :---: | --- | ---|
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [영역](/help/analysis-workspace/visualizations/area.md) | [영역 차트, 누적 영역 차트 및 100% 영역 차트](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#area-charts-basic-layered-and-stacked) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [막대](/help/analysis-workspace/visualizations/bar.md) | [클러스터형 열 차트](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [스택 막대](/help/analysis-workspace/visualizations/bar.md) | [누적 세로 막대형 차트 및 100% 누적 세로 막대형 차트](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [글머리 기호](/help/analysis-workspace/visualizations/bullet-graph.md) |  |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [코호트 테이블](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![콤보](/help/assets/icons/ComboChart.svg) | [콤보](/help/analysis-workspace/visualizations/combo-charts.md) | [선 및 누적 세로 막대형 차트 및 선 및 묶은 세로 막대형 차트](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#combo-charts) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [도넛](/help/analysis-workspace/visualizations/donut.md) | [도넛 차트](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#doughnut-charts) |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [폴아웃](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [Funnel](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#funnel-charts). |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [플로우](/help/analysis-workspace/visualizations/c-flow/flow.md) | 분해 나무요? |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [테이블](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#tables) 및 [매트릭스](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#matrix) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [히스토그램](/help/analysis-workspace/visualizations/histogram.md) |  |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) | [클러스터형 막대형 차트](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [스택 가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) | [누적 막대 차트 및 100% 누적 막대 차트](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![Branch3](/help/assets/icons/Branch3.svg) | [여정 캔버스](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | [분해 트리](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#decomposition-tree) |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [주요 지표 요약](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [라인](/help/analysis-workspace/visualizations/line.md) | [선 차트](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#line-charts) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [산포도](/help/analysis-workspace/visualizations/scatterplot.md) | [분산형 차트](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#scatter) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [섹션 헤더](/help/analysis-workspace/visualizations/section-header.md) | [텍스트 상자](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md) | [카드](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![123](/help/assets/icons/123.svg)</p> | [요약 번호](/help/analysis-workspace/visualizations/summary-number-change.md) | [카드](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![텍스트](/help/assets/icons/Text.svg) | [텍스트](/help/analysis-workspace/visualizations/text.md) | [텍스트 상자](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [트리맵](/help/analysis-workspace/visualizations/treemap.md)<p> | [트리맵](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#treemaps) |
| ![유형](/help/assets/icons/TwoDots.svg) | [벤](/help/analysis-workspace/visualizations/venn.md) | |


## 드릴다운

Power BI은 특정 시각화에 대한 자세한 내용을 살펴보기 위해 [드릴 모드](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill)를 지원합니다. 아래 예에서는 제품 범주에 대한 구매 매출을 분석합니다. 제품 카테고리를 나타내는 막대의 상황에 맞는 메뉴에서 **[!UICONTROL 드릴다운]**&#x200B;을 선택할 수 있습니다.

![Power BI 드릴다운](../assets/uc15-powerbi-drilldown.png)

드릴다운은 선택한 제품 범주 내의 제품에 대한 구매 매출로 시각화를 업데이트합니다.

![Power BI 드릴업](../assets/uc15-powerbi-drillup.png)

드릴다운을 수행하면 `WHERE` 절을 사용하는 다음 SQL 쿼리가 생성됩니다.

```sql
select "_"."product_category" as "c25",
    "_"."product_name" as "c26",
    "_"."a0" as "a0"
from 
(
    select "_"."product_category",
        "_"."product_name",
        "_"."a0"
    from 
    (
        select "_"."product_category",
            "_"."product_name",
            "_"."a0"
        from 
        (
            select "rows"."product_category" as "product_category",
                "rows"."product_name" as "product_name",
                sum("rows"."purchase_revenue") as "a0"
            from 
            (
                select "_"."product_category",
                    "_"."product_name",
                    "_"."purchase_revenue"
                from "public"."cc_data_view" "_"
                where ("_"."daterange" >= date '2023-01-01' and "_"."product_category" = 'Fishing') and "_"."daterange" < date '2024-01-01'
            ) "rows"
            group by "product_category",
                "product_name"
        ) "_"
        where not "_"."a0" is null
    ) "_"
) "_"
order by "_"."product_category",
        "_"."product_name"
limit 1001
```

>[!TAB 타블로 데스크톱]

## 비교

대부분의 Customer Journey Analytics 시각화를 위해 Tableau Desktop은 이와 동등한 경험을 제공합니다. 아래 표를 참조하십시오.

| 아이콘 | Customer Journey Analytics 시각화 | Power BI 데스크탑 시각화 |
| :---: | --- | ---|
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [영역](/help/analysis-workspace/visualizations/area.md) | [영역 차트](https://help.tableau.com/current/pro/desktop/en-us/qs_area_charts.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [막대](/help/analysis-workspace/visualizations/bar.md) | [막대 차트](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [스택 막대](/help/analysis-workspace/visualizations/bar.md) |  |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [글머리 기호](/help/analysis-workspace/visualizations/bullet-graph.md) | [글머리 기호 그래프](https://help.tableau.com/current/pro/desktop/en-us/qs_bullet_graphs.htm) |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [코호트 테이블](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![콤보](/help/assets/icons/ComboChart.svg) | [콤보](/help/analysis-workspace/visualizations/combo-charts.md) | [조합 차트](https://help.tableau.com/current/pro/desktop/en-us/qs_combo_charts.htm) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [도넛](/help/analysis-workspace/visualizations/donut.md) | |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [폴아웃](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [플로우](/help/analysis-workspace/visualizations/c-flow/flow.md) |  |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [텍스트 테이블](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_text.htm) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [히스토그램](/help/analysis-workspace/visualizations/histogram.md) | [히스토그램](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_histogram.htm) |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) | [막대 차트](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [스택 가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) | [막대 차트](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![Branch3](/help/assets/icons/Branch3.svg) | [여정 캔버스](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [주요 지표 요약](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [라인](/help/analysis-workspace/visualizations/line.md) | [선 차트](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_line.htm) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [산포도](/help/analysis-workspace/visualizations/scatterplot.md) | [산포도](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_scatter.htm) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [섹션 헤더](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![123](/help/assets/icons/123.svg)</p> | [요약 번호](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![텍스트](/help/assets/icons/Text.svg) | [텍스트](/help/analysis-workspace/visualizations/text.md) | |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [트리맵](/help/analysis-workspace/visualizations/treemap.md)<p> | [트리맵](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_treemap.htm) |
| ![유형](/help/assets/icons/TwoDots.svg) | [벤](/help/analysis-workspace/visualizations/venn.md) | |


## 드릴다운

Tableau는 [계층](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill)에서 [드릴 모드](https://help.tableau.com/current/pro/desktop/en-us/qs_hierarchies.htm)를 지원합니다. 아래 예제에서는 **[!UICONTROL 테이블]**&#x200B;에서 **[!UICONTROL 제품 이름]** 필드를 선택하고 **[!UICONTROL 제품 범주]** 위로 끌어서 놓으면 계층을 만듭니다. 그런 다음 제품 카테고리를 나타내는 막대의 컨텍스트 메뉴에서 **[!UICONTROL + 드릴다운]**&#x200B;을 선택할 수 있습니다.

![타블로 드릴다운](../assets/uc15-tableau-drilldown.png)

드릴다운은 선택한 제품 범주 내의 제품에 대한 구매 매출로 시각화를 업데이트합니다.

![타블로 드릴업](../assets/uc15-tableau-drillup.png)

드릴다운을 수행하면 GROUP BY 절을 사용하는 다음 SQL 쿼리가 생성됩니다.

```sql
SELECT CAST("cc_data_view"."product_category" AS TEXT) AS "product_category",
  CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1,
  2
```

쿼리가 결과를 선택한 제품 범주로 제한하지 **않습니다**. 시각화만 선택한 제품 범주를 표시합니다.

![타블로 드릴업](../assets/uc15-tableau-drillup2.png)

또는 한 개의 시각화가 다른 시각화에서 선택한 결과인 드릴다운 대시보드를 만들 수 있습니다. 아래 예제에서는 **[!UICONTROL 제품 범주]** 시각화를 필터로 사용하여 **[!UICONTROL 제품 이름]** 테이블을 업데이트합니다. 이 시각화 필터는 클라이언트 전용이며 추가 SQL 쿼리를 생성하지 않습니다.

![타블로 시각화 필터](../assets/uc15-tableau-visualizationfilter.png)


>[!TAB 조회자]

## 비교

대부분의 Customer Journey Analytics 시각화의 경우 Looker에서는 동등한 경험을 제공합니다. 아래 표를 참조하십시오.

| 아이콘 | Customer Journey Analytics 시각화 | Power BI 데스크탑 시각화 |
| :---: | --- | ---|
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [영역](/help/analysis-workspace/visualizations/area.md) | [영역 차트](https://cloud.google.com/looker/docs/area-options) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [막대](/help/analysis-workspace/visualizations/bar.md) | [막대 차트](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [스택 막대](/help/analysis-workspace/visualizations/bar.md) | [막대 차트](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [글머리 기호](/help/analysis-workspace/visualizations/bullet-graph.md) | [글머리 기호 그래프](https://cloud.google.com/looker/docs/bullet-chart) |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [코호트 테이블](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![콤보](/help/assets/icons/ComboChart.svg) | [콤보](/help/analysis-workspace/visualizations/combo-charts.md) | [시각화 사용자 지정](https://cloud.google.com/looker/docs/creating-visualizations#customizing_visualizations_with_chart_settings) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [도넛](/help/analysis-workspace/visualizations/donut.md) | [도넛](https://cloud.google.com/looker/docs/donut-multiples-options) |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [폴아웃](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [단계](https://cloud.google.com/looker/docs/funnel-options) |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [플로우](/help/analysis-workspace/visualizations/c-flow/flow.md) | [Sankey](https://cloud.google.com/looker/docs/sankey) |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [테이블](https://cloud.google.com/looker/docs/table-options) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [히스토그램](/help/analysis-workspace/visualizations/histogram.md) | |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) | [막대 차트](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [스택 가로 막대](/help/analysis-workspace/visualizations/horizontal-bar.md) | [막대 차트](https://cloud.google.com/looker/docs/bar-options) |
| ![Branch3](/help/assets/icons/Branch3.svg) | [여정 캔버스](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) |  |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [주요 지표 요약](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [라인](/help/analysis-workspace/visualizations/line.md) | [선 차트](https://cloud.google.com/looker/docs/line-options) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [산포도](/help/analysis-workspace/visualizations/scatterplot.md) | [산포도](https://cloud.google.com/looker/docs/scatter-options) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [섹션 헤더](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md) | [단일 값](https://cloud.google.com/looker/docs/single-value-options) |
| ![123](/help/assets/icons/123.svg)</p> | [요약 번호](/help/analysis-workspace/visualizations/summary-number-change.md) | [단일 값](https://cloud.google.com/looker/docs/single-value-options) |
| ![텍스트](/help/assets/icons/Text.svg) | [텍스트](/help/analysis-workspace/visualizations/text.md) | [단일 값](https://cloud.google.com/looker/docs/single-value-options) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [트리맵](/help/analysis-workspace/visualizations/treemap.md) | [트리맵](https://cloud.google.com/looker/docs/treemap) |
| ![Type](/help/assets/icons/TwoDots.svg) | [벤 다이어그램](/help/analysis-workspace/visualizations/venn.md) | [벤 다이어그램](https://cloud.google.com/looker/docs/venn) |

>[!TAB Jupyter 전자 필기장]

상태 기반 인터페이스인 **matplotlib.pyplot**&#x200B;의 시각화 기능을 matplotlib과 비교하는 것은 이 문서의 목적을 벗어납니다. 영감과 [matplotlib.pyplot](https://matplotlib.org/3.5.3/api/_as_gen/matplotlib.pyplot.html) 설명서는 위의 예를 참조하십시오.


>[!TAB 자습서]

R의 데이터 시각화 패키지인 **ggplot2**&#x200B;의 시각화 기능을 비교하는 것은 이 문서의 목적을 벗어납니다. 영감과 [ggplot2](https://ggplot2.tidyverse.org/articles/ggplot2.html) 설명서는 위의 예를 참조하십시오.

>[!ENDTABS]

+++
