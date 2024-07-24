---
description: Analysis Workspace에서 지표를 사용하는 두 가지 방법이 있습니다.
title: 지표
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: cdab5d8b674527a1c3f950284daac65d0ab01900
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 18%

---

# 지표

지표를 사용하면 Analysis Workspace에서 데이터 포인트를 수량화할 수 있습니다. 이들은 일반적으로 시각화에서 열로 사용되며 차원에 연결됩니다.

## 지표 유형

Adobe는 Analysis Workspace에서 사용할 수 있는 여러 유형의 지표를 제공합니다.

* **표준 지표**: 표준 지표의 예로는 사람, 세션, 이벤트가 있습니다.

* **계산된 지표** ![계산된 지표 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): 표준 지표, 정적 숫자 또는 알고리즘 함수를 기반으로 하는 사용자 정의 지표입니다.

* **계산된 지표 템플릿**  <img src="./assets/adobe-logo.svg" width="18"> : 계산된 지표와 유사하게 동작하는 Adobe 정의 지표입니다. Workspace 프로젝트에서 있는 그대로 사용하거나 사본을 저장하여 해당 논리를 사용자 지정할 수 있습니다.


![왼쪽 창에서 지표를 강조 표시하는 Workspace 패널.](assets/cja-metrics.png)

지표가 승인되었는지 ![승인됨 아이콘](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)을 확인할 수 있습니다. 지표에 대한 자세한 내용을 보려면 지표 위로 마우스를 가져간 후 ![정보 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)을 선택하세요.


지표는 Analysis Workspace 내에서 유연하게 사용할 수 있습니다. 프로젝트의 날짜 기간 동안 지표가 트렌드를 표시되게 하려면 지표를 빈 자유 형식 테이블로 끌어서 놓습니다. 차원이 있을 때 지표를 드래그하여 각 차원 항목과 비교한 지표를 볼 수도 있습니다. 기존 지표 헤더 위로 지표를 드래그하면 지표가 대체되고 헤더 옆으로 지표를 드래그하면 두 지표를 나란히 볼 수 있습니다.

## Analysis Workspace에서 지표 사용

지표는 Analysis Workspace 내에서 다양한 방식으로 사용될 수 있습니다. Analysis Workspace에 지표 및 기타 유형의 구성 요소를 추가하는 방법에 대한 자세한 내용은 [Analysis Workspace에서 구성 요소 사용](/help/components/use-components-in-workspace.md)을 참조하십시오.

## 계산된 지표 만들기

계산된 지표를 사용하면 간단한 연산자나 통계 함수를 사용하여 지표가 서로 관련되는 방식을 쉽게 확인할 수 있습니다.

계산된 지표를 만드는 방법에는 몇 가지가 있습니다. 선택하는 방법은 계산된 지표를 모든 프로젝트의 구성 요소 목록에서 사용할 수 있는지 또는 지표를 만든 프로젝트에서만 사용할 수 있는지 여부를 결정합니다.

### 모든 프로젝트에 대해 계산된 지표 만들기

계산된 지표 빌더를 사용하여 계산된 지표를 만들 수 있습니다. 이러한 방식으로 생성되면 계산된 지표를 구성 요소 목록에서 사용할 수 있으며, 그런 다음 조직 전체의 프로젝트에서 사용할 수 있습니다.

계산된 지표 빌더에 액세스하는 방법에 대한 자세한 내용은 [지표 빌드](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)를 참조하십시오.

### 단일 프로젝트에 대해 계산된 지표 만들기

지표를 만든 프로젝트에서만 사용할 수 있는 빠르게 계산된 지표를 만들 수 있습니다.

단일 프로젝트에 대해 계산된 지표를 만들려면 다음 작업을 수행하십시오.

1. Analysis Workspace에서 계산된 지표를 만들 프로젝트를 엽니다.

1. 자유 형식 테이블에서 하나 이상의 머리글 열 셀을 마우스 오른쪽 단추로 클릭한 다음 **[!UICONTROL 선택 항목에서 지표 만들기]**&#x200B;를 선택합니다.

   ![선택 항목에서 만들기 강조 표시된 Workspace 패널](assets/create-metric-from-selection.png)

1. 이 프로젝트에 대해서만 계산된 지표를 만들려면 다음 옵션 중에서 선택하십시오.

   * [!UICONTROL **나누기**]

   * [!UICONTROL **빼기**]

   * [!UICONTROL **추가**]

   * [!UICONTROL **곱하기**]

   또는 계산된 지표 빌더를 열고 모든 프로젝트에 대한 계산된 지표를 만들려면 [!UICONTROL **계산된 지표 빌더에서 열기**]&#x200B;를 선택한 다음 [지표 빌드](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)를 계속합니다.

[계산된 지표: 구현 불가 지표](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=ko-KR) (3:42)

## 다양한 속성 모델과 지표 비교

한 가지 속성 모델을 다른 모델과 신속하고 간편하게 비교하려면 지표를 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL 속성 모델 비교]**&#x200B;를 선택하십시오.

![속성 모델 비교를 강조 표시하는 Workspace 패널](assets/compare-attribution.png)

이 단축키를 사용하면 지표를 드래그하여 두 번 구성하지 않고 한 가지 속성 모델을 다른 모델과 신속하고 간편하게 비교할 수 있습니다.
