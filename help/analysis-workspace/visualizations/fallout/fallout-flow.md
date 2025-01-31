---
description: 폴아웃 보고서 및 시각화에 대해 알아봅니다.
title: 폴아웃 보고서 및 시각화 정보
feature: Visualizations
exl-id: c4338821-64ac-4345-828a-15af18a95ea6
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 30%

---

# 폴아웃 개요 {#fallout-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_fallout_button"
>title="폴아웃"
>abstract="방문자가 원하는 체크포인트로 진행하는 방법을 보여 주는 시각화를 만듭니다."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_이 문서에서는_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;에 폴아웃 시각화를 설명합니다._<br/>_이 문서의_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 버전에 대한 [폴아웃](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow)을 참조하세요._

>[!ENDSHADEBOX]

![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL 폴아웃]** 시각화는 사용자가 페이지의 사전 정의된 순서를 떠나고(폴아웃) 계속 따라가는(폴스루) 위치를 보여 줍니다.


>[!BEGINSHADEBOX]

데모 비디오가 필요하면 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [폴아웃 시각화 보고서 만들기](https://video.tv.adobe.com/v/345883/?quality=12&learn=on){target="_blank"}를 참조하십시오.

{{videoaa}}

>[!ENDSHADEBOX]


폴아웃 시각화를 통해 다음과 같은 작업을 수행할 수 있습니다.

* 동일한 보고서에서 서로 다른 두 개의 필터를 나란히 놓고 비교
* 단계 절차(터치포인트)를 드래그 앤 드롭하고 다시 정렬합니다.
* 서로 다른 차원 및 지표의 값을 혼합하고 일치시킵니다.
* 다차원 폴아웃 보고서를 만듭니다.
* 폴아웃 직후 고객이 이동하는 위치를 식별합니다.

폴아웃은 시퀀스에서 각 단계 또는 터치포인트 간 전환 및 폴아웃 비율을 보여 줍니다.

예를 들어 구매 프로세스 동안 개인의 폴아웃 지점을 추적할 수 있습니다. 시작 터치포인트와 완료 터치포인트를 선택하고, 중간 터치포인트를 추가하여 간단하게 웹 사이트 탐색 경로를 만들어 보십시오. 다차원 폴아웃을 수행할 수도 있습니다.

## 폴아웃, 플로우 및 여정 캔버스 시각화 중 선택

폴아웃 시각화는 [흐름 시각화](/help/analysis-workspace/visualizations/c-flow/flow.md) 및 [여정 캔버스 시각화](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)와 유사합니다.

### 차이점 이해

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 폴아웃 사용 시기

폴아웃과 [여정 캔버스](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) 시각화 모두 분석에 유용합니다.

* 사이트의 특정 프로세스를 통한 전환율 (예: 구매 또는 등록 프로세스)
* 일반적이고 광범위한 트래픽 흐름: 홈 페이지를 방문한 사람 중 이 흐름은 검색을 수행한 사람 수를 보여줍니다. 그리고 나서 그들 중 얼마나 많은 사람들이 결국 특정한 물건을 보았죠.
* 사이트에 있는 이벤트 간의 상관 관계. 상관 관계는 개인정보 처리방침을 본 방문자 중 제품을 구매한 비율을 보여 줍니다.

폴아웃 시각화는 다음에 가장 적합합니다.

* 사전 정의된 여정 시퀀스, 단일 진입점 및 경로를 가진 페이지를 포함하는 폴아웃 분석. (여러 진입점 및 경로가 있는 여정의 경우 여정 캔버스 사용)

* 동일한 보고서에서 서로 다른 두 필터의 병렬 비교를 수행해야 하는 여정.

[위의 표](#understand-the-differences)를 사용하여 여정 캔버스, 폴아웃 및 플로우 시각화 간의 차이점을 이해합니다.

>[!MORELIKETHIS]
>
>[폴아웃 시각화 구성](configuring-fallout.md)



