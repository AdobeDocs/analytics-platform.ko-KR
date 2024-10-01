---
description: Analysis Workspace에서 지표를 사용하는 두 가지 방법이 있습니다.
title: 지표
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 20%

---

# 지표

지표를 사용하면 Analysis Workspace에서 데이터 포인트를 수량화할 수 있습니다. 이들은 일반적으로 시각화에서 열로 사용되며 차원에 연결됩니다.

## 지표 유형

Adobe는 Analysis Workspace에서 사용할 수 있는 여러 유형의 지표를 제공합니다.


* **표준 지표**: 표준 지표의 예로는 사람, 세션, 이벤트가 있습니다.

* **계산된 지표** ![계산기](/help/assets/icons/Calculator.svg): 표준 지표, 정적 숫자 또는 알고리즘 함수를 기반으로 하는 사용자 정의 지표입니다.

* **계산된 지표 템플릿** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : 계산된 지표와 유사하게 동작하는 Adobe 정의 지표입니다. Workspace 프로젝트에서 있는 그대로 사용하거나 사본을 저장하여 논리를 사용자 지정할 수 있습니다.

지표가 승인되었는지 ![승인됨 아이콘](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)을 확인할 수 있습니다. 지표에 대한 자세한 내용을 보려면 지표 위로 마우스를 가져간 후 ![정보 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)을 선택하세요. 자세한 내용은 [구성 요소 정보](use-components-in-workspace.md#component-info)를 참조하세요.



## Analysis Workspace에서 지표 사용

지표는 Analysis Workspace 내에서 유연하게 사용할 수 있습니다. 프로젝트의 날짜 기간 동안 지표가 트렌드를 표시되게 하려면 지표를 빈 자유 형식 테이블로 끌어서 놓습니다. 차원이 있을 때 지표를 드래그하여 각 차원 항목과 비교한 지표를 볼 수도 있습니다. 기존 지표 헤더 위로 지표를 드래그하면 지표가 대체되고 헤더 옆으로 지표를 드래그하면 두 지표를 나란히 볼 수 있습니다.

Analysis Workspace에 지표 및 기타 유형의 구성 요소를 추가하는 방법에 대한 자세한 내용은 [Analysis Workspace에서 구성 요소 사용](/help/components/use-components-in-workspace.md)을 참조하십시오.

## 계산된 지표

계산된 지표를 사용하면 간단한 연산자나 통계 함수를 사용하여 지표가 서로 관련되는 방식을 쉽게 구성할 수 있습니다. 자세한 내용은 [계산된 지표 개요](/help/components/calc-metrics/calc-metr-overview.md)를 참조하십시오.

<!--

There are several ways to create calculated metrics. See [Create calculated metrics]()

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, select **[!UICONTROL Create metric from selection]** from the context menu in a column header.

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


<!-- This video really shows an AA example using hits, etc.  Not suitable for CJA... >
+++ See the following video on how to create an implementation-less calculated metric from within Analysis Workspace.

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)


>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

+++

-->

## 다양한 속성 모델과 지표 비교

지표에 대한 속성 모델 하나를 다른 모델과 신속하고 간편하게 비교하려면 해당 지표의 컨텍스트 메뉴에서 **[!UICONTROL 속성 모델 비교]**&#x200B;를 선택하십시오.

![속성 모델 비교를 강조 표시하는 Workspace 패널](assets/compare-attribution.png)

이 바로 가기를 사용하면 속성 모델을 빠르고 쉽게 비교할 수 있습니다.
