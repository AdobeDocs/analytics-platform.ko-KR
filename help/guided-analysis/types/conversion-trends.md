---
title: 전환 트렌드 분석
description: 시간 경과에 따른 전환율 변화를 추적합니다.
feature: Adobe Product Analytics, Guided Analysis
keywords: 제품 분석
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!UICONTROL 전환 트렌드] 분석 {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_conversiontrends_button"
>title="전환 추세"
>abstract="시간 경과에 따른 전환율 변화를 추적합니다."

<!-- markdownlint-enable MD034 -->


![전환 트렌드](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL 전환 트렌드]** 분석에서는 시간 경과에 따른 전환율의 트렌드 시각화를 제공합니다. 가로축은 시간 간격인 반면, 세로축은 전환율을 나타냅니다.


>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)


## 사용 사례

이 분석의 사용 사례는 다음과 같습니다.

* **최적화 작업 추적**: [단계](funnel.md) 분석을 사용하여 개선하려는 주요 병목 현상을 식별한 후 이 분석을 사용하여 이러한 최적화가 시간에 따른 전환율에 미치는 영향을 추적할 수 있습니다.
* **A/B 테스트 평가**: 단계 컨텍스트에서 수행된 A/B 테스트 또는 실험의 효과를 평가합니다. 서로 다른 변형 간의 전환율을 비교하여 어떤 테스트가 더 높은 전환율을 제공하는지 쉽게 판단할 수 있으므로 어떤 변형을 영구적으로 구현할지 데이터 중심의 결정을 내릴 수 있습니다.
* **시간 경과에 따른 캠페인 평가**: 시간 경과에 따른 마케팅 캠페인의 효과를 측정합니다. 지정된 캠페인을 터치한 사용자에 중점을 둔 세그먼트를 만들고 전환율을 다른 캠페인과 비교할 수 있습니다. 또한 현재 전환율을 과거에 실행된 유사한 캠페인과 비교할 수도 있습니다.

## 인터페이스

안내식 분석 인터페이스에 대한 개요는 [인터페이스](../overview.md#interface)를 참조하십시오. 다음 설정은 이 분석과 관련이 있습니다.

### 쿼리 레일

쿼리 레일을 사용하면 다음 구성 요소를 구성할 수 있습니다.

* **[!UICONTROL 보기]**: 이 분석과 [단계](funnel.md) 간을 전환합니다.
* **[!UICONTROL 단계]**: 추적할 이벤트 터치포인트입니다. 차트의 각 막대는 단계를 나타냅니다. 최대 10개의 단계를 포함할 수 있습니다.
* **[!UICONTROL 다음 값으로 계산]**: 선택한 이벤트에 적용할 계산 메서드입니다. 옵션에는 [!UICONTROL 사용자] 및 [!UICONTROL 세션]이 포함됩니다.
* **[!UICONTROL 세그먼트]**: 단계를 비교할 세그먼트입니다. 선택한 각 세그먼트는 각 단계를 여러 개의 막대로 분할합니다. 각 색상은 다른 세그먼트를 나타냅니다. 최대 3개의 세그먼트를 포함할 수 있습니다.

### 차트 설정

[!UICONTROL 전환 트렌드] 분석에서는 차트 위의 메뉴에서 조정할 수 있는 다음과 같은 차트 설정을 제공합니다.

* **[!UICONTROL 차트 종류]**: 사용할 시각화 형식입니다. 옵션에는 [!UICONTROL 줄]이 포함됩니다.
* **[!UICONTROL 변환 대상]**: 단계별로 백분율 계산을 결정합니다. 옵션에는 [!UICONTROL 첫 번째 단계] 또는 [!UICONTROL 이전 단계]에서 전환 계산이 포함됩니다.

>[!NOTE]
>
>전환 트렌드 분석 테이블의 **평균** 열이 [단계 분석](funnel.md) 테이블의 **합계** 열과 다릅니다. 전자는 간격 열의 평균(예: 일일 전환율 평균)이고 후자는 전체 날짜 범위에서 집계된 계산입니다.

### 시간 비교

{{apply-time-comparison}}


### 날짜 범위

분석에 필요한 날짜 범위입니다. 이 설정에는 두 가지 구성 요소가 있습니다.

* **[!UICONTROL 간격]**: 트렌드 데이터를 보려는 날짜 세부 기간입니다. 유효한 옵션에는 시간별, 일별, 주별, 월별 및 분기별 이 포함됩니다. 동일한 날짜 범위에는 차트의 데이터 요소 수와 테이블의 열 수에 영향을 주는 서로 다른 간격이 있을 수 있습니다. 예를 들어 일별 세부기간을 사용하여 3일 동안의 분석을 보면 데이터 포인트가 세 개만 표시되는 반면, 시간별 세부기간을 사용하여 3일 동안의 분석에서는 데이터 포인트가 72개로 표시됩니다.
* **[!UICONTROL 날짜]**: 시작 및 종료 날짜입니다. 롤링 날짜 범위 사전 설정 및 이전에 저장된 사용자 지정 범위는 편의상 사용하거나, 달력 선택기를 사용하여 고정 날짜 범위를 선택할 수 있습니다.

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
