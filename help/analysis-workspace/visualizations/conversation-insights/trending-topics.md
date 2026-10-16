---
description: 트렌드 주제 시각화를 사용하여 대화의 트렌드 주제를 탐색할 수 있습니다.
title: 트렌딩 항목
feature: Visualizations
role: User
hide: true
source-git-commit: 65d4115d4c292cff7e074d37a91563d369072ba5
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%
---
# 트렌딩 항목

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="트렌딩 항목"
>abstract="발생 횟수 및 백분율과 함께 트렌드 주제에 대한 계층적 드릴다운 지원 분류를 보여 주는 시각화를 만들어 대화에서 중요한 테마를 식별하는 데 도움이 됩니다."

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="트렌딩 항목"
>abstract="선택한 등급 지표를 기반으로 트렌드 주제를 분석합니다. 최대 5개 수준 깊이로 드릴다운할 주제를 선택합니다. 특정 주제를 검색하고 주제를 다른 날짜 범위와 비교합니다."

![피드](/help/assets/icons/Feed.svg) **[!UICONTROL 트렌드 주제]** 시각화를 사용하면 대화 통찰력의 일부로 트렌드 주제를 탐색하고 분석할 수 있습니다.

특정 주제를 검색하고 각 수준에서 각 주제의 수 및 백분율을 다른 데이터 범위와 비교할 수 있습니다.

## 만들기 및 구성

트렌드 주제 시각화를 만들고 구성하려면 다음 작업을 수행하십시오.

1. ![피드](/help/assets/icons/Feed.svg) **[!UICONTROL 트렌드 주제]** 시각화를 추가합니다. [패널 내에 시각화 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)를 참조하십시오.

1. **[!UICONTROL 트렌드 항목]** 시각화 구성:

   1. **[!UICONTROL 순위 지표]**&#x200B;을(를) 선택하십시오. 예: **[!UICONTROL 대화]**.
   1. 필요한 경우 **[!UICONTROL 속성 설정]**&#x200B;을 선택하고 **[!UICONTROL 모델]**, **[!UICONTROL 컨테이너]** 및 **[!UICONTROL 전환 확인 기간]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 하위 항목 수준 제한]**&#x200B;에 대한 수준을 선택하십시오. 기본값은 **[!UICONTROL 수준 5]**&#x200B;입니다.

      >[!NOTE]
      >
      >**[!UICONTROL 하위 항목 수준 제한]**&#x200B;은(는) 시각화의 주제에 대해 드릴다운할 최대 수준 수를 정의합니다. 정의된 최대 수 내의 수준에서 사용할 수 있는 항목이 더 이상 없으면 ![DataUnavailable](/help/assets/icons/DataUnavailable.svg) **[!UICONTROL 항목이 없습니다]**.

1. **[!UICONTROL 빌드]**&#x200B;를 선택하여 시각화를 빌드합니다. 구성 값을 기본값으로 재설정하려면 **[!UICONTROL 재설정]**&#x200B;을 선택하십시오.

트렌드 항목 시각화를 다시 구성하려면 **[!UICONTROL 순위 지표: _순위 지표_ 옆에 있는 ![편집](/help/assets/icons/Edit.svg)을 선택합니다. | 하위 항목 수준: _x_]**.

## 사용

시각화를 사용하려면 다음을 수행하십시오.

* 하위 레벨의 항목에 대한 트렌드 하위 항목을 드릴하고 보려면 특정 레벨의 항목을 선택합니다.

* 항목을 다른 날짜 범위와 비교하려면 비교 대상에서 날짜 범위를 선택합니다. 사용자 지정 날짜 범위를 사용하려면 다음을 수행하십시오.
  * 드롭다운 메뉴에서 사용자 지정 날짜 범위 를 선택하고 새 날짜 범위 대화 상자에서 사용자 지정 날짜 범위를 정의하고 저장합니다.
  * 해당 사용자 지정 날짜 범위를 선택합니다.

* 현재 선택한 항목에 대한 선 그래프를 표시하려면 **[!UICONTROL 트렌드 항목]** 시각화에 [선](/help/analysis-workspace/visualizations/line.md) 시각화를 놓으십시오. **[!UICONTROL Line]** 시각화는 **[!UICONTROL 트렌드 항목]** 시각화에 자동으로 연결됩니다.

## 설정

다음 특정 [시각화 설정](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)을 사용할 수 있습니다.

| 설정 | 설명 |
|---|---|
| **[!UICONTROL 실제 값 표시]** | 항목에 대한 실제 값을 표시합니다. |
| **[!UICONTROL 표시 비율]** | 토피의 백분율을 표시합니다. |



