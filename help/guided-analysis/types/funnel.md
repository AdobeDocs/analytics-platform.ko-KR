---
title: 단계 분석
description: 단계 간 전환율을 비교합니다.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: 제품 분석
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 3%

---

# [!UICONTROL 단계] 분석 {#funnel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_funnel_button"
>title="단계"
>abstract="단계 간 전환율을 비교합니다."

<!-- markdownlint-enable MD034 -->

![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Funnel ]**분석은 제품에 중요한 사용자 여정을 시각적으로 표시합니다. 가로축은 사용자가 통과해야 하는 각 단계를 나타냅니다. 세로 축은 각 단계에서 사용자 또는 세션의 백분율을 나타냅니다. 모든 단계는 최종 순서로 수행되어야 하지만 보고 기간 내에서 언제든지 발생할 수 있습니다.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?quality=12&learn=on){width="90%"}

## 사용 사례

이 분석의 사용 사례는 다음과 같습니다.

* **전환 분석**: 소매 체크아웃, 계정 등록, 구독 흐름 또는 제품 경험에 포함된 다른 중요한 여정과 같은 단계 각 단계의 전환을 분석할 수 있습니다. 한 단계에서 다음 단계로 진행되는 사용자 수를 추적하면 전환율이 일반적이지 않거나 원치 않는 병목 현상을 식별할 수 있습니다. 이 정보는 즉각적인 결과를 위해 제품 여정을 개선할 수 있는 위치를 이해하는 데 유용합니다.
* **실험 분석**: A/B 실험이 실행되고 있는 선택적 단계 또는 단계가 있는 단계 전체에 걸쳐 전환율을 비교할 수 있습니다. 이 정보를 통해 전환율이 가장 높은 단계의 변형을 파악하여 해당 경로를 따라 더 많은 사용자를 유도할 수 있습니다.
* **온보딩 최적화**: 주요 이벤트에 대한 사용자 동작을 검사하여 제품의 온보딩 프로세스를 최적화합니다. 사용자가 어려움을 겪거나 완료하지 못하는 단계를 식별할 수 있습니다.
* **기능 채택 및 참여**: 사용자가 제품의 특정 기능과 상호 작용하는 방법을 이해합니다. 기능 관련 단계를 통해 사용자 진행 상태를 분석하면 채택률을 확인하고 사용자가 특정 기능을 제대로 사용하지 않을 수 있는 영역을 식별할 수 있습니다. 그런 다음 이 정보를 사용하여 기능 개선에 주력하여 채택률을 높일 수 있습니다.
* **마케팅 채널 효율성**: 마케팅 채널의 효과를 측정합니다. 유료 검색, 디스플레이, 자연어 검색 또는 직접 등 다양한 마케팅 채널과 상호 작용한 사용자에게 중점을 둔 세그먼트를 만들 수 있습니다. 그런 다음 해당 여정을 비교하여 최상의 제품 결과로 이어지는 채널을 확인할 수 있습니다.

## 인터페이스

안내식 분석 인터페이스에 대한 개요는 [인터페이스](../overview.md#interface)를 참조하십시오. 다음 설정은 이 분석과 관련이 있습니다.

### 쿼리 레일

쿼리 레일을 사용하면 다음 구성 요소를 구성할 수 있습니다.

* **[!UICONTROL 보기]**: 이 분석과 [전환 트렌드](conversion-trends.md) 간을 전환합니다.
* **[!UICONTROL 단계]**: 추적할 이벤트 터치포인트입니다. 차트의 각 막대는 단계를 나타냅니다. 최대 10개의 단계를 포함할 수 있습니다.
   * [!UICONTROL 비교]: 각 단계에서는 단일 단계 단계에서 여러 이벤트를 비교하는 옵션을 제공하여 &quot;분기된 단계&quot;를 만듭니다. 이 기능을 사용하면 두 개의 별도 해석을 생성하지 않고도 두 여정의 마찰을 나란히 비교할 수 있습니다. 단계 옵션이 있거나 A/B 실험이 단계 내에서 실행되고 있는 경우에 유용합니다. 단계 비교 방법에 대한 비디오를 보려면 Customer Journey Analytics 자습서의 [단계](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel)를 참조하십시오.
* **[!UICONTROL 다음으로 계산]**: 단계에 적용할 범위입니다. 옵션에는 [!UICONTROL 세션] 및 [!UICONTROL 사용자]가 있습니다.
   * [!UICONTROL 세션]: 모든 단계는 같은 세션 내에서 계산되어야 합니다.
   * [!UICONTROL 사용자]: 모든 단계는 선택한 보고 기간 내에서 계산되어야 합니다.
* **[!UICONTROL 세그먼트]**: 단계를 비교할 세그먼트입니다. 선택한 각 세그먼트는 각 단계를 여러 개의 막대로 분할합니다. 각 색상은 다른 세그먼트를 나타냅니다. 최대 3개의 세그먼트를 포함할 수 있습니다.

### 차트 설정

[!UICONTROL 단계] 분석에서는 차트 위의 메뉴에서 조정할 수 있는 다음과 같은 차트 설정을 제공합니다.

* **[!UICONTROL 차트 종류]**: 사용할 시각화 형식입니다. 옵션에는 [!UICONTROL 단계]가 포함됩니다.
* **[!UICONTROL 변환 대상]**: 단계별로 백분율 계산을 결정합니다. 옵션에는 [!UICONTROL 첫 번째 단계] 또는 [!UICONTROL 이전 단계]에서 전환 계산이 포함됩니다.

### 시간 비교

{{apply-time-comparison}}



### 날짜 범위

분석에 필요한 날짜 범위입니다. 이 설정에는 두 가지 구성 요소가 있습니다.

* **[!UICONTROL 간격]**: 트렌드 데이터를 보려는 날짜 세부 기간입니다. 이 설정은 [단계](funnel.md)와 같이 트렌드가 없는 분석에는 영향을 주지 않습니다.
* **[!UICONTROL 날짜]**: 시작 및 종료 날짜입니다. 롤링 날짜 범위 사전 설정 및 이전에 저장된 사용자 지정 범위는 편의상 사용하거나, 달력 선택기를 사용하여 고정 날짜 범위를 선택할 수 있습니다.

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
