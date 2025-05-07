---
title: 트렌드 분석
description: 시간 경과에 따른 사용자 참여를 측정합니다.
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: 제품 분석
role: User
source-git-commit: e42f04eaa06a761803e76b64a5a16674fb4af57d
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 92%

---

# [!UICONTROL 트렌드] 분석 {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_trends_button"
>title="트렌드"
>abstract="시간 경과에 따른 사용자 참여를 측정합니다."

<!-- markdownlint-enable MD034 -->

![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL 트렌드]** 분석은 시간 경과에 따른 제품 성과나 사용자 행동에 대한 귀중한 인사이트를 제공합니다. 본 보고서의 가로축은 시간 간격이고, 세로축은 원하는 이벤트를 측정합니다.


>[!VIDEO](https://video.tv.adobe.com/v/3423443/?quality=12&learn=on&captions=kor)

## 사용 사례

이 분석의 사용 사례는 다음과 같습니다.

* **제품 성과 평가**: 트렌드를 통해 특정 기간 동안 제품의 전반적인 성과를 평가할 수 있습니다. 사용자 참여도, 채택률, 전환율과 같은 지표를 분석하여 제품 성과가 개선되고 있는지, 정체되고 있는지 또는 감소하고 있는지 확인할 수 있습니다.
* **기능 채택**: 트렌드를 통해 사용자가 새로운 기능이나 출시하는 업데이트를 어떻게 채택하는지 파악할 수 있습니다. 어떤 기능이 인기가 있고 개선이 필요한지 확인할 수 있습니다. 이 정보를 통해 개발 노력의 우선순위를 정하기 위해 데이터 기반의 결정을 내릴 수 있습니다.
* **사용자 행동**: 트렌드는 시간 경과에 따른 사용자 행동에 대한 인사이트를 제공할 수 있습니다. 사용자가 수행하는 구체적인 행동을 살펴보면 사용자가 중단하는 패턴을 파악할 수 있습니다. 이 분석에서 얻은 인사이트를 [단계](funnel.md)와 결합하여 행동에 대한 더욱 심도 있는 인사이트를 얻을 수 있습니다.
* **A/B 테스트 및 실험**: 제품 내에서 A/B 테스트를 실행하면 트렌드를 사용하여 시간 경과에 따라 어떤 테스트가 가장 성공적인지 측정할 수 있습니다.

## 인터페이스

가이드 분석 인터페이스 개요는 [인터페이스](../overview.md#interface)에서 확인하십시오. 다음 설정은 이 분석에만 적용됩니다.

### 쿼리 레일

쿼리 레일을 사용하면 다음 구성 요소를 구성할 수 있습니다.

* **[!UICONTROL 보기]**: 이 분석과 [빈도](frequency.md)를 전환합니다.
* **[!UICONTROL 이벤트 및 지표]**: 측정하려는 이벤트나 지표. 각 선택 항목은 차트 시리즈와 테이블 행으로 표현됩니다. 이벤트와 지표는 쿼리에서 결합할 수 없습니다. 첫 번째 선택을 한 후에는 나머지 쿼리 선택 항목이 동일한 유형이어야 합니다. 최대 5개의 선택 항목을 포함할 수 있습니다.
* **[!UICONTROL 다음으로 계산됨]**: 선택한 이벤트에 적용할 계산 방법입니다. <ul><li>**[!UICONTROL 옵션]**&#x200B;에는 [!UICONTROL 사용자], [!UICONTROL 이벤트], [!UICONTROL 세션], [!UICONTROL 사용자 비율], [!UICONTROL 세션당 이벤트] 및 [!UICONTROL 사용자당 이벤트]가 포함됩니다.</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"} 추가 **[!UICONTROL B2B 옵션]**&#x200B;은(는) Customer Journey Analytics B2B edition에서 사용할 수 있습니다. [!UICONTROL 글로벌 계정], [!UICONTROL 계정], [!UICONTROL 구매 그룹], [!UICONTROL 기회], [!UICONTROL 글로벌 계정의 백분율], [!UICONTROL 계정의 백분율], [!UICONTROL 구매 그룹의 백분율], [!UICONTROL 기회의 백분율], [!UICONTROL 글로벌 계정당 이벤트], [!UICONTROL 계정당 이벤트], [!UICONTROL 구매 그룹당 이벤트] 및 [!UICONTROL 기회당 이벤트].</li></ul>옵션으로 계산된 내용은 이벤트 쿼리에만 적용되고 지표 쿼리에서는 제거됩니다.
* **[!UICONTROL 세그먼트]**: 측정하려는 세그먼트. 선택된 세그먼트마다 차트 시리즈와 테이블 행의 수가 두 배로 늘어납니다. 최대 5개의 세그먼트를 포함할 수 있습니다.
* **[!UICONTROL 분류 속성]**: 선택한 속성의 값을 기준으로 차트 시리즈와 테이블 행을 분류합니다. 단일 분류 속성이 지원됩니다. 테이블에는 상위 20개 값이 표에 표시되고, 차트에서 최대 10개의 값을 볼 수 있습니다. 차트에서 행을 숨기거나 표시하려면 ![숨기기 아이콘 표시](../assets/hide-in-chart.png) 아이콘을 토글합니다.

### 차트 설정

[!UICONTROL 트렌드] 분석에서는 다음과 같은 차트 설정을 제공하며, 차트 위의 메뉴에서 조정할 수 있습니다.

* **[!UICONTROL 차트 유형]**: 사용하고자 하는 시각화 유형. 옵션으로는 선, 막대, 스택 막대, 스택 영역이 있습니다.

### 오버레이

차트에 데이터를 추가합니다. 차트에 두 개 이상의 시리즈가 표시되어 있는 경우, 마우스를 올려 놓았을 때만 오버레이가 나타납니다.

* **[!UICONTROL 예외 항목 탐지]**: 트렌드 분석에 대해 [예외 항목 탐지](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)를 실행합니다. 이상치는 점으로 표시되며, 이 점으로 마우스를 가져가면 자세한 정보를 볼 수 있습니다.
* **[!UICONTROL 트렌드 라인 오버레이]**: 차트에 트렌드 라인을 추가하여 데이터의 패턴을 더욱 명확하게 묘사합니다.
   * [!UICONTROL 선형]: 직선 회귀선을 생성합니다. 꾸준한 속도로 증가하거나 감소하는 간단한 선형 데이터에 가장 적합합니다. 수식: `y = a + b * x`
   * [!UICONTROL 로그]: 곡선 회귀선을 생성합니다. 빠르게 증가하거나 감소한 후 수준이 높아지는 데이터에 가장 적합합니다. 수식: `y = a + b * log(x)`
   * [!UICONTROL 이동 평균]: 평균 세트를 기반으로 부드러운 트렌드 라인을 만듭니다. 롤링 평균이라고도 하는 이동 평균은 특정 수의 이전 데이터 포인트(선택 항목에 의해 결정됨)를 사용하고 평균을 계산하여 선의 한 지점으로 사용합니다. 예를 들어 7일 이동 평균 또는 4주 이동 평균이 있습니다. 사용 가능한 이동 평균 옵션은 선택한 간격 및 날짜 범위에 따라 달라집니다.

### 시간 비교

{{apply-time-comparison}}


### 날짜 범위

분석에 원하는 날짜 범위. 이 설정에는 두 가지 구성 요소가 있습니다.

* **[!UICONTROL 간격]**: 추세 데이터를 보려는 날짜별 세부 기간. 유효한 옵션으로는 시간별, 일별, 주별, 월별, 분기별이 있습니다. 동일한 날짜 범위는 차트의 데이터 포인트 수와 테이블의 열 수에 영향을 미치는 다양한 간격을 가질 수 있습니다. 예를 들어 일일 세분 기간으로 3일에 걸친 분석을 보면 데이터 포인트가 3개만 표시되는 반면, 시간별 세분 기간으로 3일에 걸친 분석에서는 72개의 데이터 포인트가 표시됩니다.
* **[!UICONTROL 날짜]**: 시작 및 종료 날짜. 순환 날짜 범위 사전 설정과 이전에 저장된 사용자 정의의 범위를 편리하게 사용할 수 있으며, 캘린더 선택기를 사용하여 고정된 날짜 범위를 선택할 수도 있습니다.


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->