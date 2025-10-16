---
title: 타임라인 분석
description: 시간 경과에 따른 사용자 수준 세션 이벤트를 관찰하여 경험 패턴을 찾습니다.
feature: Adobe Product Analytics, Guided Analysis
keywords: 제품 분석
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 100%

---

# [!UICONTROL 타임라인] 분석 {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_timeline_button"
>title="타임라인"
>abstract="시간 경과에 따른 사용자 수준 세션 이벤트를 관찰합니다."

<!-- markdownlint-enable MD034 -->

![타임라인](/help/assets/icons/Timeline.svg) **[!UICONTROL 타임라인]** 분석을 사용하면 시간 경과에 따른 사용자 수준 세션 이벤트를 관찰하여 경험 패턴을 찾고 더 나은 사용자 스토리를 전달할 수 있습니다. 왼쪽 레일에서 속성 값과 세그먼트별로 스트림을 필터링할 수 있습니다. 오른쪽 레일을 사용하면 필터 조건에 맞는 사용자를 무작위로 나열한 목록에서 선택할 수 있습니다. 중앙 영역에는 타임스탬프, 속성 값, 기간으로 구성된 세션별 선택된 사용자의 스트림이 표시됩니다. 해당 세션의 마지막 이벤트에 대한 기간은 제공되지 않습니다.


>[!NOTE]
>
>[!UICONTROL 타임라인] 분석을 위해서는 **[!UICONTROL 개인 ID]** 표준 구성 요소가 [데이터 보기](/help/data-views/component-reference.md#optional)에서 사용 가능해야 합니다. 데이터 보기에 개인 ID를 포함하면 Customer Journey Analytics 관리자가 관리하므로 조직은 이 데이터에 액세스할 수 있는 사용자에 대한 완전한 개인정보 보호 제어가 가능합니다.
><br/>데이터 보기에 [!UICONTROL 개인 ID] 구성 요소가 추가되지 않은 경우 다음 메시지가 표시됩니다.
>
>* **관리자**: *이 분석에는 PersonID 속성이 필요합니다. 데이터 보기에 개인 ID를 추가하십시오.*
>* **관리자가 아닌 사용자**: *이 분석에는 PersonID 속성이 필요합니다. Customer Journey Analytics 관리자에게 문의하여 데이터 보기에 개인 ID를 추가하십시오.*

>[!VIDEO](https://video.tv.adobe.com/v/3435774/?captions=kor&quality=12&learn=on)



## 사용 사례

이 분석의 사용 사례는 다음과 같습니다.

* **마찰 탐색**: [단계 분석](funnel.md)에서 급격한 하락을 발견하면 해당 사용자 세그먼트를 만들고 이 분석에 세그먼트를 적용하여 잠재적 원인을 조사할 수 있습니다.
* **오류 행동**: 사용자에게 제품 오류가 발생하면 해당 오류가 나타나기 전이나 후에 사용자가 무엇을 했는지 알아볼 수 있습니다.
* **데이터 수집 검증**: 데이터 관리자는 이 분석을 자신의 개인 ID로 필터링하여 조직의 구현이 예상대로 작동하는지 검증할 수 있습니다.

## 인터페이스

가이드 분석 인터페이스 개요는 [인터페이스](../overview.md#interface)에서 확인하십시오. 다음 설정은 이 분석에만 적용됩니다.

### 쿼리 레일

쿼리 레일을 사용하면 다음 구성 요소를 구성할 수 있습니다.

* **[!UICONTROL 차원]**: 스트리밍된 값을 보려는 차원. 중앙의 스트림은 선택한 차원에 대한 값을 보여 줍니다. 필터를 적용하여 스트림을 더 관련성 있는 데이터로 좁힐 수도 있습니다. 필터에 유효한 연산자로는 [!UICONTROL 다음과 같음], [!UICONTROL 다음과 같지 않음], [!UICONTROL 다음으로 시작], [!UICONTROL 다음으로 끝남], [!UICONTROL 다음 포함], [!UICONTROL 다음을 포함하지 않음], [!UICONTROL 있음], [!UICONTROL 없음]이 있습니다.
* **[!UICONTROL 세그먼트]**: 분석하려는 세그먼트. 선택된 세그먼트는 세그먼트 기준과 일치하는 개인에게만 초점을 맞추기 위해 데이터를 필터링합니다. 분석 범위를 특정 개인 ID로 좁히려면 오른쪽 패널에서 해당 개인 ID로 필터링할 수 있습니다. 이 분석은 세그먼트 하나에 지원됩니다.

### 차트 설정

[!UICONTROL 타임라인] 분석에서는 다음과 같은 차트 설정을 제공하며, 차트 위의 메뉴에서 조정할 수 있습니다.

* **[!UICONTROL 다음으로 표시]**: 원하는 속성 값을 표시합니다.
   * [!UICONTROL 모두 표시]: 세션의 모든 속성 값을 표시합니다.
   * [!UICONTROL 강조]: 쿼리 필터와 일치하는 세션의 속성 값을 시각적으로 강조 표시합니다.
   * [!UICONTROL 보기 전용]: 쿼리 필터와 일치하는 세션의 속성 값만 표시합니다.

### 날짜 범위

분석에 원하는 날짜 범위. 이 설정에는 두 가지 구성 요소가 있습니다.

* **[!UICONTROL 간격]**: 추세 데이터를 보려는 날짜별 세부 기간. 이 설정은 타임라인과 같이 추세가 없는 분석에는 영향을 미치지 않습니다.
* **[!UICONTROL 날짜]**: 시작 및 종료 날짜. 순환 날짜 범위 사전 설정과 이전에 저장된 사용자 정의의 범위를 편리하게 사용할 수 있으며, 캘린더 선택기를 사용하여 고정된 날짜 범위를 선택할 수도 있습니다.


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
