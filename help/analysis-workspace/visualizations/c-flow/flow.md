---
description: Analysis Workspace에서 플로우 시각화를 사용하는 방법에 대해 알아봅니다.
title: 플로우 개요
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 94%

---

# 플로우 개요 {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="플로우"
>abstract="하나의 체크포인트에서 다음 체크포인트로의 사용자 플로우를 표시하는 시각화를 만듭니다."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="플로우"
>abstract="하나의 터치포인트에서 다음 터치포인트로의 방문 또는 방문자 흐름을 분석합니다. 시작 및 종료에 사용할 구성 요소(지표, 차원 또는 항목)를 지정합니다. 필요한 경우 고급 설정을 정의하여 시각화를 더욱 세부적으로 구성할 수 있습니다."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_이 문서에서는_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;의 플로우 시각화에 대해 설명합니다._<br/>_이 문서의_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 버전은 [플로우](https://experienceleague.adobe.com/ko/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow)를 참조하십시오._

>[!ENDSHADEBOX]


![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 플로우]** 시각화는 고객이 웹 사이트 및 앱을 통과하는 경로를 보여 줍니다.

시각화를 사용하면 다음 작업을 할 수 있습니다.

* 웹 사이트나 애플리케이션 내의 고객 여정 시각화.
* 시작, 특정 차원 또는 종료와 같이, 지정된 체크포인트의 전후에 고객이 이동하는 위치 분석.
* 선택한 경로에서 특정 지점을 지정하여 세그먼트 생성.


>[!BEGINSHADEBOX]

데모 비디오를 보려면 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [플로우 시각화 만들기](https://video.tv.adobe.com/v/346063/?quality=12&learn=on){target="_blank"}를 확인하십시오.

{{videoaa}}

>[!ENDSHADEBOX]


## 차원 간 플로우

[차원 간 플로우](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)을 표시할 수 있습니다. 예를 들어 하나의 다이어그램에서 페이지와 차원을 결합할 수도 있습니다. 이 경우, 사용자의 플로우는 홈 페이지에서 &#39;남성&#39; 페이지로 이동한 다음 &#39;신발&#39; 부문으로 이동할 수 있습니다.

각 열에는 다른 차원이 표시될 수 있습니다. 차원을 드래그하여 드롭 영역에 놓아 해당 차원을 다이어그램에 추가합니다.

>[!MORELIKETHIS]
>
>[플로우 시각화 구성](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## 플로우, 폴아웃 또는 여정 캔버스 시각화 중에서 선택

플로우 시각화는 [폴아웃 시각화](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) 및 [여정 캔버스 시각화](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)와 유사하지만 중요한 차이점이 있습니다.

### 차이점 이해

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 플로우를 사용하는 경우

플로우 시각화는 다음과 같은 경우에 가장 적합합니다.

* 경로상의 바로 다음 터치포인트에 대한 탐색적, 애드혹 분석을 수행합니다. (여정 캔버스를 사용하여 사전 정의된 페이지 시퀀스가 있는 여정이나 최종 경로를 사용하는 여정에 사용합니다.)

* 여러 진입점과 경로가 있는 비선형 여정. (여정 캔버스를 사용하여 사전 정의된 페이지 시퀀스가 있는 여정에 사용합니다.)

[위의 테이블](#understand-the-differences)을 사용하여 플로우, 폴아웃 및 여정 캔버스의 차이점을 이해합니다.
