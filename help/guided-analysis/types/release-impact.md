---
title: 릴리스 영향 분석
description: 릴리스 전후 동일한 기간 동안의 성과를 비교합니다.
feature: Adobe Product Analytics, Guided Analysis
keywords: 제품 분석
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '530'
ht-degree: 100%

---

# [!UICONTROL 릴리스 영향] 분석 {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_releaseimpact_button"
>title="릴리스 영향"
>abstract="릴리스 전후 동일한 기간 동안의 성과를 비교합니다."

<!-- markdownlint-enable MD034 -->

![릴리스](/help/assets/icons/Release.svg) **[!UICONTROL 릴리스 영향]** 분석은 특정 날짜 전후의 주요 지표를 비교한 것입니다. 본 보고서의 가로축은 시간 간격이고, 세로축은 원하는 주요 지표를 측정합니다. 차트 중앙의 세로 막대는 비교하려는 전후 날짜를 나타냅니다. 이 날짜는 일반적으로 제품 업데이트나 캠페인 출시 등 측정하려는 제품에 대한 주요 변경 사항을 나타냅니다.

>[!VIDEO](https://video.tv.adobe.com/v/3423452/?quality=12&learn=on&captions=kor)

## 사용 사례

이 분석의 사용 사례는 다음과 같습니다.

* **전반적인 성과 평가:** 참여도 측정과 같은 전반적인 주요 지표를 비교하면 특정 릴리스가 전반적으로 성공했는지 확인하는 데 도움이 될 수 있습니다.
* **모니터링**: 로드 시간이나 로그인 수와 같은 변경 사항이 있을 때 일정하게 유지될 것으로 예상되는 중요한 지표를 추적합니다. 이 분석을 사용하여 릴리스 전후를 비교하여 의도치 않은 결과가 발생하지 않았는지 확인합니다.
* **기능 채택**: 제품 업데이트가 특정 기능을 개선하는 데 중점을 두고 있는 경우, 이 분석을 사용하여 제품 업데이트 전후에 해당 기능의 사용량을 직접 비교할 수 있습니다.
* **버그 감지**: 릴리스 전후의 오류 수를 추적하면 고객 문제를 조기에 파악할 수 있습니다. 릴리스 직후 오류가 증가하는 것을 발견하면 엔지니어링 또는 개발 팀과 협력하여 문제를 식별하고 수정하여 고객에게 더 이상의 영향을 미치지 않도록 할 수 있습니다.

## 인터페이스

가이드 분석 인터페이스 개요는 [인터페이스](../overview.md#interface)에서 확인하십시오. 다음 설정은 이 분석에만 적용됩니다.

### 쿼리 레일

쿼리 레일을 사용하면 다음 구성 요소를 구성할 수 있습니다.

* **[!UICONTROL 보기]**: 이 분석과 [최초 사용 영향](first-use-impact.md) 간에 전환합니다.
* **[!UICONTROL 주요 지표]**: 사용자별로 측정하려는 이벤트. 선택된 각 주요 지표는 색상이 있는 선으로 표시됩니다. 이벤트를 나타내는 행이 테이블에 추가됩니다. 최대 3개의 이벤트를 포함할 수 있습니다.
* **[!UICONTROL 다음으로 계산됨]**: 선택한 이벤트에 적용할 계산 방법. 옵션에는 [!UICONTROL 사용자당 이벤트], [!UICONTROL 사용자 비율], [!UICONTROL 이벤트], [!UICONTROL 세션] 및 [!UICONTROL 사용자]가 있습니다.
* **[!UICONTROL 요소]**: 이전과 이후를 비교하려는 날짜.
* **[!UICONTROL 세그먼트]**: 측정하려는 세그먼트. 선택된 세그먼트는 세그먼트 기준과 일치하는 개인에게만 초점을 맞추기 위해 데이터를 필터링합니다.

### 차트 설정

[!UICONTROL 릴리스 영향] 분석에서는 다음과 같은 차트 설정을 제공하며, 차트 위의 메뉴에서 조정할 수 있습니다.

* **[!UICONTROL 차트 유형]**: 사용하고자 하는 시각화 유형. 옵션에는 [!UICONTROL 라인] 및 [!UICONTROL 막대]가 있습니다.

### 날짜 범위

영향 분석에서 날짜 선택은 다른 분석과 다르게 작동합니다. 보고서가 쿼리 레일에 지정된 날짜를 중심으로 진행되기 때문입니다. 다음 옵션을 사용할 수 있습니다.

* **[!UICONTROL 간격]**: 추세 데이터를 보려는 날짜별 세부 기간. 유효한 옵션으로는 [!UICONTROL 일별], [!UICONTROL 주별], [!UICONTROL 월별], [!UICONTROL 분기별]이 있습니다. 간격을 변경하면 기간 전후에 사용할 수 있는 옵션에 영향을 줍니다.
* **[!UICONTROL 기간 전후]**: 쿼리 레일에 지정된 날짜 전후를 분석하는 데 걸리는 시간. 사용 가능한 옵션은 [!UICONTROL 간격] 선택에 따라 다릅니다.


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
