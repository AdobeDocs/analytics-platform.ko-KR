---
title: 활성 증가 분석
description: 신규, 유지, 복귀 또는 휴면 상태를 식별합니다.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: 제품 분석
role: User
source-git-commit: be617c59cd2fced0031fda1130b86e638bee8f68
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 92%

---

# [!UICONTROL 활성 증가] 분석 {#active-growth}

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="활성 증가"
>abstract="신규, 유지, 복귀 또는 휴면 상태를 식별합니다."



![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL 활성 증가]** 분석은 특정 기간 동안 사용자의 증가 및 확보에 대한 인사이트를 제공합니다. 가로축은 시간 간격이고, 세로축은 사용자 측정값입니다. 사용자는 4가지 카테고리로 구분됩니다.

* **[!UICONTROL 신규]**: 사용자는 현재 기간 동안 활동했지만 이전에는 활동하지 않았습니다. 차트 범례에서 _[!UICONTROL 신규 사용자]_&#x200B;를 마우스를 가져다 대 분석 결과가 얼마나 되돌아왔는지 확인할 수 있습니다. 전환 확인 범위는 선택한 날짜 범위 및 간격에 따라 동적으로 결정됩니다.
* **[!UICONTROL 재방문]**: 사용자는 현재 및 직전 기간 동안 활동했습니다.
* **[!UICONTROL 복귀]**: 사용자는 현재 기간에는 활동적이었지만 바로 이전 기간에는 활동적이지 않았으나, 예전에는 특정 시점에 활동적이었습니다. 차트 범례에서 _[!UICONTROL 복귀 사용자]_&#x200B;를 마우스를 가져다 대 분석 결과가 얼마나 되돌아왔는지 확인할 수 있습니다. 전환 확인 범위는 선택한 날짜 범위 및 간격에 따라 동적으로 결정됩니다.
* **[!UICONTROL 휴면]**: 사용자는 바로 이전 기간에는 활동적이었으나 현재 기간에는 활동적이지 않습니다. 휴면 사용자는 전체 활성 사용자 수에 포함되지 않습니다.

모든 활성 사용자(신규 사용자 + 재방문 사용자 + 복귀 사용자)는 가로축 위에 청록색 음영으로 표시되는 반면, 모든 휴면 사용자는 가로축 아래에 주황색으로 표시됩니다.


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?quality=12&learn=on)

## 사용 사례

이 분석의 사용 사례는 다음과 같습니다.

* **사용자 유지 및 이탈:** 사용자 유지율이 높거나 낮은 기간을 명확하게 시각화합니다. 이러한 높은 유지 기간 또는 낮은 유지 기간을 인식하면 높은 유지율을 장려하거나 이탈을 최소화하는 데 도움이 되는 제품 결정을 내리는 데 도움이 될 수 있습니다.
* **캠페인 평가**: 특정 캠페인을 보면 해당 캠페인이 얼마나 많은 트래픽을 생성했는지, 그리고 사용자 참여를 유지하는 데 얼마나 도움이 되었는지 이해하는 데 도움이 될 수 있습니다.
* **사용자 수명 주기 분석**: 사용자 수명 주기 전반에 걸친 활발한 사용자 증가를 분석하면 사용자 참여가 감소하는 특정 단계를 식별하는 데 도움이 될 수 있습니다. 예를 들어 온보딩 단계에 있는 개인의 휴면 사용자 비율이 높으면 사용성 문제나 더 나은 제품 내 안내가 필요하다는 것을 나타낼 수 있습니다.

## 인터페이스

가이드 분석 인터페이스 개요는 [인터페이스](../overview.md#interface)에서 확인하십시오. 다음 설정은 이 분석에만 적용됩니다.

### 쿼리 레일

쿼리 레일을 사용하면 다음 구성 요소를 구성할 수 있습니다.

* **[!UICONTROL 보기]**: 이 분석과 [순 성장](net-growth.md) 간을 전환합니다.
* **[!UICONTROL 이벤트]**: 측정하려는 이벤트. 이 분석은 사용자 기반이므로, 해당 기간 내에 이벤트와 한 번 상호 작용한 사용자는 활성 사용자로 간주됩니다. 쿼리에 하나의 이벤트를 포함할 수 있습니다.
* **[!UICONTROL 다음으로 계산됨]**: 선택한 이벤트에 적용할 계산 방법입니다. <ul><li>**[!UICONTROL 옵션]**&#x200B;에는 [!UICONTROL 사용자 수] 및 [!UICONTROL 사용자 비율]이 포함됩니다.</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 추가 **[!UICONTROL B2B 옵션]**&#x200B;은(는) Customer Journey Analytics B2B edition에서 사용할 수 있습니다. [!UICONTROL 글로벌 계정], [!UICONTROL 계정], [!UICONTROL 구매 그룹], [!UICONTROL 기회], [!UICONTROL 글로벌 계정의 백분율], [!UICONTROL 계정의 백분율], [!UICONTROL 구매 그룹의 백분율] 및 [!UICONTROL 기회의 백분율].</li></ul>
* **[!UICONTROL 세그먼트]**: 데이터를 세그먼트화할 세그먼트입니다. 쿼리에 하나의 세그먼트를 포함할 수 있습니다.

### 차트 설정

[!UICONTROL 활성 증가] 분석에서는 다음과 같은 차트 설정을 제공하며, 차트 위의 메뉴에서 조정할 수 있습니다.

* **[!UICONTROL 차트 유형]**: 사용하고자 하는 시각화 유형. 옵션으로는 [!UICONTROL 스택 막대] 및 [!UICONTROL 스택 영역]이 있습니다.

### 시간 비교

{{apply-time-comparison}}

### 날짜 범위

분석에 원하는 날짜 범위. 이 설정에는 두 가지 구성 요소가 있습니다.

* **[!UICONTROL 간격]**: 추세 데이터를 보려는 날짜별 세부 기간. 유효한 옵션으로는 시간별, 일별, 주별, 월별, 분기별이 있습니다. 동일한 날짜 범위는 차트의 데이터 포인트 수와 테이블의 열 수에 영향을 미치는 다양한 간격을 가질 수 있습니다. 예를 들어 일일 세분 기간으로 3일에 걸친 분석을 보면 데이터 포인트가 3개만 표시되는 반면, 시간별 세분 기간으로 3일에 걸친 분석에서는 72개의 데이터 포인트가 표시됩니다.
* **[!UICONTROL 날짜]**: 시작 및 종료 날짜. 순환 날짜 범위 사전 설정과 이전에 저장된 사용자 정의의 범위를 편리하게 사용할 수 있으며, 캘린더 선택기를 사용하여 고정된 날짜 범위를 선택할 수도 있습니다.

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
