---
title: 릴리스 영향 분석
description: 릴리스 전후 동일한 기간 동안의 성능을 비교합니다.
feature: Adobe Product Analytics, Guided Analysis
keywords: 제품 분석
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 10%

---

# [!UICONTROL 릴리스 영향] 분석 {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_releaseimpact_button"
>title="릴리스 영향"
>abstract="릴리스 전후 동일한 기간 동안의 성능을 비교합니다."

<!-- markdownlint-enable MD034 -->

![릴리스](/help/assets/icons/Release.svg) **[!UICONTROL 릴리스 영향]** 분석은 지정된 날짜 전후에 주요 지표가 수행되는 방식을 비교합니다. 이 보고서의 가로축은 시간 간격인 반면 세로축은 원하는 주요 지표를 측정합니다. 차트 중간에 있는 세로 막대는 이전 날짜와 이후 날짜를 비교하려는 날짜를 나타냅니다. 이 날짜는 일반적으로 제품 업데이트 또는 캠페인 시작과 같이 측정하려는 제품에 대한 주목할 만한 변경 사항을 나타냅니다.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?quality=12&learn=on)

## 사용 사례

이 분석의 사용 사례는 다음과 같습니다.

* **전체 성능 평가:** 참여 측정과 같은 전반적인 주요 지표를 비교하면 해당 릴리스가 전체적으로 성공했는지 확인하는 데 도움이 됩니다.
* **모니터링**: 로드 시간이나 로그인 수와 같은 변경 사항이 있을 때 고정된 상태를 유지할 것으로 예상되는 중요한 지표를 추적합니다. 이 분석을 사용하여 릴리스 전후의 결과를 비교하여 의도하지 않은 결과가 발생하지 않았는지 확인하십시오.
* **기능 채택**: 제품 업데이트가 특정 기능을 개선하는 데 중점을 둔 경우 이 분석을 사용하여 제품 업데이트 전후의 해당 기능 사용을 직접 비교할 수 있습니다.
* **버그 감지**: 릴리스 전후의 오류 수를 추적하면 고객 문제를 조기에 파악할 수 있습니다. 릴리스 직후 오류가 증가하는 것을 발견하면 엔지니어링 또는 개발 팀과 협력하여 문제를 식별하고 수정하여 고객에게 더 이상의 영향을 미치지 않도록 할 수 있습니다.

## 인터페이스

안내식 분석 인터페이스에 대한 개요는 [인터페이스](../overview.md#interface)를 참조하십시오. 다음 설정은 이 분석과 관련이 있습니다.

### 쿼리 레일

쿼리 레일을 사용하면 다음 구성 요소를 구성할 수 있습니다.

* **[!UICONTROL 보기]**: 이 분석과 [첫 번째 사용 영향](first-use-impact.md) 간을 전환합니다.
* **[!UICONTROL 주요 지표]**: 사용자별로 측정할 이벤트입니다. 선택한 각 키 표시기는 색칠된 선으로 표시됩니다. 이벤트를 나타내는 행이 테이블에 추가됩니다. 최대 3개의 이벤트를 포함할 수 있습니다.
* **[!UICONTROL 다음으로 계산됨]**: 선택한 이벤트에 적용할 계산 방법입니다. 옵션에는 [!UICONTROL 사용자당 이벤트], [!UICONTROL 사용자 비율], [!UICONTROL 이벤트], [!UICONTROL 세션] 및 [!UICONTROL 사용자]가 있습니다.
* **[!UICONTROL 요소]**: 이전 날짜와 이후 비교하려는 날짜입니다.
* **[!UICONTROL 세그먼트]**: 측정할 세그먼트입니다. 선택한 세그먼트는 데이터를 필터링하여 세그먼트 기준과 일치하는 개인에게만 집중시킵니다.

### 차트 설정

[!UICONTROL 릴리스 영향] 분석에서는 차트 위의 메뉴에서 조정할 수 있는 다음과 같은 차트 설정을 제공합니다.

* **[!UICONTROL 차트 종류]**: 사용할 시각화 형식입니다. 옵션에는 [!UICONTROL 줄] 및 [!UICONTROL 막대]가 있습니다.

### 날짜 범위

보고서가 쿼리 레일에 지정된 날짜를 기준으로 회전하므로 영향 분석의 날짜 선택은 다른 분석과 다르게 작동합니다. 다음 옵션을 사용할 수 있습니다.

* **[!UICONTROL 간격]**: 트렌드 데이터를 보려는 날짜 세부 기간입니다. 유효한 옵션에는 [!UICONTROL 일별], [!UICONTROL 주별], [!UICONTROL 월별] 및 [!UICONTROL 분기별]이 있습니다. 간격을 변경하면 이전 및 이후 기간에 사용할 수 있는 옵션에 영향을 줍니다.
* **[!UICONTROL 이전 및 이후 기간]**: 쿼리 레일에 지정된 날짜 이전 및 이후에 분석할 시간입니다. 사용 가능한 옵션은 [!UICONTROL 간격] 선택에 따라 다릅니다.


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
