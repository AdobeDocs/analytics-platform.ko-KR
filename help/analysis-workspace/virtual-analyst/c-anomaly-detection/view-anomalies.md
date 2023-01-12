---
description: 표 또는 선 차트에서 예외 항목을 볼 수 있습니다.
title: Analysis Workspace에서 예외 항목 보기
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
source-git-commit: e62261d1d440c0a85e4cab95611c6e6272de6724
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 14%

---

# Analysis Workspace에서 예외 항목 보기

표 또는 선 차트에서 예외 항목을 볼 수 있습니다.

## 표에서 예외 항목 보기 {#section_869A87B92B574A38B017A980ED8A29C5}

시계열 자유 형식 테이블에서 예외 항목을 볼 수 있습니다.

1. 열 헤더에서 열 설정 아이콘을 선택한 다음, [!UICONTROL **예외 항목**] 옵션 목록에서 옵션이 선택됩니다. 자세한 내용은 [열 설정](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. 업데이트된 테이블을 보려면 설정 메뉴에서 를 클릭하십시오.

   ![](assets/anomaly_detected.png)

1. 예외 항목은 다음과 같이 표에 표시됩니다.

   A **짙은 회색 삼각형** 는 데이터 예외 항목이 탐지되는 각 행의 오른쪽 위 모서리에 나타납니다.

   색칠됨 **세로 선** 각 행에서 값은 예상되는 값을 나타냅니다. 색칠됨 **음영 영역** 각 행에서 실제 값이 표시됩니다. 라인(예상 값)이 음영 영역(실제 값)과 비교하는 방식을 통해 예외 항목이 있는지 여부를 결정합니다. (관찰은 [예외 항목 탐지에서 사용된 통계 기법](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md))

1. 행의 오른쪽 위 모서리에서 회색 삼각형을 선택하여 예외 항목에 대한 세부 사항을 확인합니다. 이것은 실제 값이 예상 값 위 또는 아래에 분기되는 범위(백분율)를 표시합니다.

## 선 차트에서 예외 항목 보기 {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

선 차트는 예외 항목을 볼 수 있는 유일한 시각화입니다.

선 차트에서 예외 항목을 보려면 다음을 수행하십시오.

1. 시각화 헤더에서 설정 아이콘을 선택한 다음, [!UICONTROL **예외 항목 표시**] 옵션 목록에서 옵션이 선택됩니다. 자세한 내용은 [라인](/help/analysis-workspace/visualizations/line.md).

1. (선택 사항) 신뢰 구간이 차트의 크기를 조정하도록 하려면 시각화 헤더에서 설정 아이콘을 선택한 다음, 옵션을 선택합니다. **[!UICONTROL 예외 항목을 Y축에 비율 조정 허용]**.

   이 옵션은 차트를 읽기 쉽게 만들 수 있으므로 기본적으로 선택되어 있지 않습니다.

1. 업데이트된 선 차트를 보려면 설정 메뉴 바깥쪽을 클릭합니다.

   ![](assets/anomaly_linechart.png)

   예외 항목은 다음과 같이 선 차트에 표시됩니다.

   A **흰색 점** 는 데이터 예외 항목이 탐지될 때마다 라인에 나타납니다. (관찰은 [예외 항목 탐지에서 사용된 통계 기법](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md))

   다음 **광음영 영역** 는 값이 있어야 하는 신뢰 구간 또는 예상 범위입니다. 이 예상 범위를 벗어나는 모든 값은 예외 항목입니다.

   라인 차트에 여러 개의 지표가 있는 경우 예외 항목만 표시되고 각 예외 항목을 마우스로 가리키면 해당 지표에 대한 신뢰 대역을 볼 수 있습니다.

   다음 **점선** 는 정확한 예상 값입니다.

1. 예외 항목(흰색 점)을 클릭하여 다음 정보를 확인합니다.

   * 예외 항목이 발생한 날짜

   * 예외 항목의 원시 값

   * 녹색 선으로 표시되는 예상 값보다 위 또는 아래 값의 백분율 값

