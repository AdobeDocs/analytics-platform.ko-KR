---
description: 라인 시각화를 사용하여 트렌드(시간 기반) 데이터 세트를 나타냅니다.
title: 라인
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 4f163e32787a732526511aeda5f6c1e32becb490
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 94%

---


# 라인

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 계십니다. 이 기능은 [기존 Adobe Analytics의 Analysis Workspace](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html)와 약간 다릅니다. [추가 정보...](/help/getting-started/cja-aa.md)

라인 시각화는 일정 기간 동안 값이 어떻게 변하는지를 보여주기 위해 라인을 사용하여 지표를 나타냅니다. 라인 차트는 시간을 차원으로 사용하는 경우에만 사용할 수 있습니다.

![라인 시각화](assets/line-viz.png)

>[!IMPORTANT]
>
>[!UICONTROL 트렌드 라인 표시]와 같은 일부 라인 시각화 설정이 현재 제한된 테스트 중입니다. [추가 정보](https://docs.adobe.com/content/help/ko-KR/analytics/landing/an-releases.html)

사용 가능한 [**시각화 설정에**](freeform-analysis-visualizations.md) 액세스하려면 라인 시각화의 오른쪽 상단에 있는 톱니바퀴 아이콘을 클릭하십시오. 설정은 다음과 같이 분류됩니다.

* **일반**: 시각화 유형 간에 공통적인 설정
* **축**: 라인 시각화의 x축 또는 y축에 영향을 주는 설정
* **오버레이**: 라인 시각화에 표시된 시리즈에 추가적인 컨텍스트를 추가하기 위한 옵션

![시각화 설정](assets/viz-settings-modal.png)

## 세부기간 변경

[시각화 설정](freeform-analysis-visualizations.md)의 세부기간 드롭다운을 사용하면 트렌드 시각화(예: 선, 막대)를 일별에서 주별, 월별 등으로 변경할 수 있습니다. 세부기간은 데이터 소스 테이블에서도 업데이트됩니다.

## 최소 또는 최대 표시

**[!UICONTROL 시각화 설정]** > **[!UICONTROL 오버레이]** > **[!UICONTROL 최소/최대 표시]** 아래에서 최소값과 최대값 레이블을 오버레이하여 지표의 최고점과 최저점을 빠르게 강조 표시할 수 있습니다. 참고:최소/최대 값은 차원 내의 전체 값 세트가 아니라 시각화에서 표시되는 데이터 포인트에서 파생됩니다.

![최소/최대 표시](assets/min-max-labels.png)

## 트렌드 오버레이 표시

**[!UICONTROL 시각화 설정]** > **[!UICONTROL 오버레이]** > **[!UICONTROL 트렌드 표시]** 아래에서 회귀 트렌드 라인을 라인 시리즈에 추가할 수 있습니다. 트렌드 라인은 데이터의 명확한 패턴을 표현하는 데 도움이 됩니다.

![선형 트렌드 라인](assets/show-linear-trendline.png)

모든 모델은 보통최소제곱법(ordinary least squares)을 사용하여 맞춰집니다.

| 모델 | 설명 |
| --- | --- |
| 선형 | 단순한 선형 데이터 세트에 가장 잘 맞는 직선을 만들며, 데이터가 일정한 속도로 증가 또는 감소하는 경우 유용합니다. 수식: `y = a + b * x` |
| 로그 | 가장 잘 맞는 곡선을 만들며 데이터의 변경 속도가 빠르게 증가 또는 감소하다가 수평을 유지하는 경우 유용합니다. 로그 트렌드 라인은 음수 값과 양수 값을 사용할 수 있습니다. 수식: `y = a + b * log(x)` |
| 지수 | 곡선을 만들며 데이터가 지속적으로 증가하는 비율로 증가하거나 감소할 때 유용합니다. 데이터에 0이나 음수 값이 있는 경우에는 이 옵션을 사용하지 마십시오. 수식: `y = a + e^(b * x)` |
| 거듭제곱 | 곡선을 만들고 특정 비율로 증가하는 측정 값을 비교하는 데이터 세트에 유용합니다. 데이터에 0이나 음수 값이 있는 경우에는 이 옵션을 사용하지 마십시오. 수식: `y = a * x^b` |
| 이차 | 포물선(위 또는 아래로 오목)과 같은 모양의 데이터 세트에 가장 잘 맞습니다. 수식: `y = a + b * x + c * x^2` |
