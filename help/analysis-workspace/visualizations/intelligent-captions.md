---
description: 지능형 캡션을 사용하여 시각화 내의 트렌드를 표시하는 자연어 인사이트를 생성합니다.
title: 인텔리전트 캡션
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 5d391a73fb30ebc8f443f5a88357c866df03ce96
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 19%

---

# 인텔리전트 캡션 {#intelligent-captions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_area"
>title="인텔리전트 캡션: 영역"
>abstract="이 시각화에 대한 데이터를 보다 쉽게 이해하고 해석할 수 있도록 자연어 형식으로 인사이트를 생성합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_bar"
>title="인텔리전트 캡션: 막대"
>abstract="이 시각화에 대한 데이터를 보다 쉽게 이해하고 해석할 수 있도록 자연어 형식으로 인사이트를 생성합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_donut"
>title="인텔리전트 캡션: 도넛"
>abstract="이 시각화에 대한 데이터를 보다 쉽게 이해하고 해석할 수 있도록 자연어 형식으로 인사이트를 생성합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_horizontalbar"
>title="인텔리전트 캡션: 수평 막대"
>abstract="이 시각화에 대한 데이터를 보다 쉽게 이해하고 해석할 수 있도록 자연어 형식으로 인사이트를 생성합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_line"
>title="인텔리전트 캡션: 라인"
>abstract="이 시각화에 대한 데이터를 보다 쉽게 이해하고 해석할 수 있도록 자연어 형식으로 인사이트를 생성합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_fallout"
>title="인텔리전트 캡션: 폴아웃"
>abstract="이 시각화에 대한 데이터를 보다 쉽게 이해하고 해석할 수 있도록 자연어 형식으로 인사이트를 생성합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_flow"
>title="인텔리전트 캡션: 플로우"
>abstract="이 시각화에 대한 데이터를 보다 쉽게 이해하고 해석할 수 있도록 자연어 형식으로 인사이트를 생성합니다."

<!-- markdownlint-enable MD034 -->

지능형 캡션 기능은 고급 생성 AI를 사용하여 자연어로 가장 자주 사용되는 Workspace 시각화에 대한 주요 통찰력을 제공합니다.

지능형 캡션은 다음 항목에 맞춰져 있습니다.

* 다른 사용자와 공유하기 위해 서술이 필요한 분석가. 분석가는 사용자에게 컨텍스트를 제공할 수 있도록 이러한 통찰력이 필요합니다.
* 높은 수준의 테이크아웃을 빠르게 찾고 싶은 비즈니스 사용자.

>[!BEGINSHADEBOX]

데모 비디오는 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [지능형 캡션](https://video.tv.adobe.com/v/3420131/?quality=12&learn=on){target="_blank"}을 참조하십시오.

>[!ENDSHADEBOX]

## 지능형 캡션 실행 {#launch}

시각화에 대해 자동 생성된 지능형 캡션을 시작하려면 시각화의 오른쪽 상단에서 ![지능형 캡션](/help/assets/icons/AI.svg)을(를) 선택합니다. 이 옵션을 선택하면 자연어 통찰력이 생성됩니다.

![제품 보기에 대한 지능형 캡션 트렌드를 표시하는 분석 시작 창. ](assets/intelligent-captions.gif)


주의 사항:

* 캡션을 성공적으로 생성하려면 최소 3개의 데이터 포인트가 필요합니다. 그렇지 않으면 **[!UICONTROL 분석할 데이터가 충분하지 않음]**&#x200B;과 같은 오류가 발생할 수 있습니다.

* 시각화를 구동하는 테이블에서 기본 선택 데이터가 변경될 때마다 캡션이 생성됩니다.

* 연결된 자유 형식 테이블에 여러 지표가 있는 경우 첫 번째 지표 또는 사용자가 현재 선택한 지표에 대해서만 캡션이 생성됩니다. 하지만 선 및 영역 시각화를 위한 여러 지표에 대해 캡션을 생성할 수 있습니다.

* 프로젝트를 특정 시점에 저장하고 나중에 다시 로드하는 경우 캡션이 새 데이터로 자동 업데이트됩니다. 프로젝트에서 내보낸 예약된 프로젝트 및 PDF 파일에도 적용됩니다.


## 시각화 {#visualizations}

지능형 캡션은 다음 시각화에서 지원됩니다.

* [줄](line.md)(여러 줄 포함)
* [막대](bar.md)
* [가로 막대형](horizontal-bar.md)
* [영역](area.md)(여러 영역 라인 포함)
* [도넛](donut.md)
* [폴아웃](fallout/fallout-flow.md)
* [흐름](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## 작업

지능형 캡션에 대해 다음 작업을 수행할 수 있습니다.

### 클립보드에 복사 {#copy}

캡션을 클립보드에 복사하고 PowerPoint 또는 다른 도구에 붙여 넣을 수 있습니다. 개별 캡션을 하나씩 보기에서 복사할 수도 있고 확장된 캡션 보기에서 모든 캡션을 한 번에 복사할 수도 있습니다.

* 캡션을 복사하려면 캡션 대화 상자의 오른쪽 맨 위에 있는 ![클립보드에 캡션 복사](/help/assets/icons/Copy.svg)를 선택합니다.

### 모든 또는 개별 지능형 캡션 표시  {#show-all-or-individual}

확장된 보기에서 모든 지능형 캡션을 한 번에 표시하거나 개별 지능형 캡션을 하나씩 표시할 수 있습니다.

* 모든 지능형 캡션을 표시하려면 ![모든 지능형 캡션 표시](/help/assets/icons/Maximize.svg)를 선택합니다.
* 개별 지능형 캡션을 하나씩 표시하려면 ![개별 지능형 캡션 표시](/help/assets/icons/Minimize.svg)를 선택합니다.

### 디스플레이 편집 {#edit}

특정 범주의 인사이트를 숨기거나 숨기는 것과 같은 캡션 표시를 편집할 수 있습니다.

1. 지능형 캡션 대화 상자에서 ![지능형 캡션의 가시성 편집](/help/assets/icons/EditInLight.svg)을 선택합니다.

1. ![가시성 전환](/help/assets/icons/Visibility.svg)을 전환하여 특정 통찰력(**[!UICONTROL Min]**)을 표시하거나 ![가시성 전환](/help/assets/icons/VisibilityOff.svg)을 전환하여 특정 통찰력(**[!UICONTROL Spike]**)을 숨깁니다.

   ![지능형 캡션 편집](assets/edit-intelligent-captions.png)

1. **[!UICONTROL 적용]**&#x200B;을 선택합니다.


### 피드백 제공

생성된 지능형 캡션에 대한 피드백을 제공할 수 있습니다(피드백은 확장된 캡션 보기에서만 제공될 수 있음).

1. 지능형 캡션 대화 상자에서 ![추가 작업](/help/assets/icons/More.svg)을 선택합니다.

1. ![좋은 응답](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL 좋은 응답]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL 잘못된 응답]** 또는 ![플래그](/help/assets/icons/Flag.svg) **[!UICONTROL 보고서]**&#x200B;를 선택하십시오.

1. **[!UICONTROL 피드백을 제공해주셔서 감사합니다]** 대화 상자에서 피드백을 제공하고 **[!UICONTROL 제출]**&#x200B;을 선택하여 피드백을 제출하십시오.

### 내보내기 {#export}

프로젝트가 지능형 캡션이 생성된 상태로 저장되는 한 지능형 캡션을 PDF의 일부로 내보낼 수 있습니다.

### 전환 해제 {#toggle}

지능형 캡션을 표시하지 않는 경우에는 기능을 끌 수 있습니다.

1. [시각화 환경 설정](/help/analysis-workspace/user-preferences.md#visualizations-preferences)(으)로 이동합니다.
1. **[!UICONTROL 지능형 캡션 표시]**&#x200B;를 선택 취소합니다.

   ![지능형 캡션 표시 선택 취소 옵션을 표시하는 선 시각화 옵션입니다.](assets/toggle-captions.png)

1. 환경 설정을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택하십시오.


## 모바일 스코어카드의 지능형 캡션

지능형 캡션은 Customer Journey Analytics [모바일 스코어카드](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)에서도 사용할 수 있습니다.

## 기능 액세스

다음 매개 변수는 지능형 캡션에 대한 액세스를 제어합니다.

* **솔루션 액세스**: 지능형 캡션 기능은 Customer Journey Analytics에서 사용할 수 있지만 Adobe Analytics에서는 사용할 수 없습니다.

* **계약 액세스**: 지능형 캡션을 사용할 수 없는 경우 조직의 관리자 또는 Adobe 계정 담당자(관리자)에게 문의하십시오. 조직에서 지능형 캡션을 사용하려면 먼저 특정 생성 AI 관련 법률 용어에 동의해야 합니다.

* **권한**: [!UICONTROL Adobe Admin Console]에서 [!UICONTROL 보고 도구] **[!UICONTROL 지능형 캡션]** 권한이 액세스를 결정합니다. [제품 프로필 관리자](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)는 [!UICONTROL Admin Console]에서 다음 단계를 따라야 합니다.
   1. **[!UICONTROL Admin Console]** > **[!UICONTROL 제품 및 서비스]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 제품 프로필]**&#x200B;로 이동합니다.
   1. 지능형 캡션에 대한 액세스를 제공할 제품 프로필의 제목을 선택합니다.
   1. 특정 제품 프로필에서 **[!UICONTROL 권한]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 보고 도구]**&#x200B;를 편집하려면 ![편집](/help/assets/icons/Edit.svg)을 선택하세요.
   1. **[!UICONTROL 포함된 권한 항목]**&#x200B;에 **지능형 캡션**&#x200B;을 추가하려면 ![AddCircle](/help/assets/icons/AddCircle.svg)을(를) 선택하십시오.

      ![권한 추가](./assets/intelligent-captions-permissions.png)

   1. **[!UICONTROL 저장]**&#x200B;을 선택하여 권한을 저장합니다.

자세한 내용은 [액세스 제어](/help/technotes/access-control.md#access-control)를 참조하십시오.
