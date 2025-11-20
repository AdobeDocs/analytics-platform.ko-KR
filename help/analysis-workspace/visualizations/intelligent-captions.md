---
description: 인텔리전트 캡션을 사용하여 시각화 내에서 추세를 표면화하기 위한 자연어 인사이트를 생성하는 방법에 대해 알아봅니다.
title: 지능형 캡션
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 100%

---

# 인텔리전트 캡션 {#intelligent-captions}

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions"
>title="인텔리전트 캡션"
>abstract="이 시각화에 대한 데이터를 보다 쉽게 이해하고 해석할 수 있도록 자연어 형식으로 인사이트를 생성합니다."


인텔리전트 캡션 기능은 고급 생성형 AI를 사용하여 자연어로 가장 자주 사용되는 Workspace 시각화에 대한 주요 인사이트를 제공합니다.

인텔리전트 캡션은 다음을 대상으로 합니다.

* 다른 사용자와 공유할 스토리가 필요한 분석가. 분석가는 사용자에게 컨텍스트를 제공하기 위해 이러한 인사이트가 필요합니다.
* 빠르게 높은 수준의 핵심 정보를 발견하고 싶어하는 비즈니스 사용자.

>[!BEGINSHADEBOX]

데모 비디오를 보려면 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [인텔리전트 캡션](https://video.tv.adobe.com/v/3443145/?captions=kor&quality=12&learn=on){target="_blank"}을 확인하십시오.

>[!ENDSHADEBOX]


## 인텔리전트 캡션 실행 {#launch}

시각화를 위한 자동 생성 인텔리전트 캡션을 시작하려면 시각화 오른쪽 상단에 있는 ![인텔리전트 캡션](/help/assets/icons/AI.svg)을 선택합니다. 이러한 선택을 통해 자연어 인사이트가 생성됩니다.

![제품 조회수 추세에 대한 인텔리전트 캡션을 보여 주는 분석 창을 실행합니다. ](assets/intelligent-captions.gif)


주의 사항:

* 캡션을 성공적으로 생성하려면 최소 3개의 데이터 포인트가 필요합니다. 그렇지 않으면 **[!UICONTROL 분석할 데이터가 충분하지 않습니다]**&#x200B;와 같은 오류가 발생할 수 있습니다.

* 캡션은 시각화를 실행하는 테이블에서 기본적으로 선택된 데이터가 변경될 때마다 생성됩니다.

* 연관된 자유 형식 테이블에 여러 개의 지표가 있는 경우, 캡션은 첫 번째 지표나 사용자가 현재 선택한 지표에만 생성됩니다. 그러나 라인 및 영역 시각화의 여러 지표에 대한 캡션을 생성할 수 있습니다.

* 특정 지점에서 프로젝트를 저장한 다음 나중에 다시 로드하면 캡션이 새로운 데이터로 자동 업데이트됩니다. 프로젝트에서 내보낸 예약된 프로젝트와 PDF 파일에도 동일하게 적용됩니다.


## 시각화 {#visualizations}

인텔리전트 캡션은 다음 시각화에서 지원됩니다.

* [라인](line.md)(여러 라인 포함)
* [막대](bar.md)
* [가로 막대](horizontal-bar.md)
* [영역](area.md)(여러 영역 라인 포함)
* [도넛](donut.md)
* [폴아웃](fallout/fallout-flow.md)
* [플로우](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## 액션

인텔리전트 캡션에서 다음 액션을 수행할 수 있습니다.

### 클립보드에 복사 {#copy}

캡션을 클립보드에 복사하여 PowerPoint 또는 다른 도구에 붙여넣을 수 있습니다. 개별 캡션을 하나씩 복사하거나 확장된 캡션 보기에서 모든 캡션을 한 번에 복사할 수 있습니다.

* 캡션을 복사하려면 캡션 대화 상자 오른쪽 상단에 있는 ![캡션을 클립보드에 복사](/help/assets/icons/Copy.svg)를 선택합니다.

### 모든 인텔리전트 캡션 또는 개별 인텔리전트 캡션 표시  {#show-all-or-individual}

확장된 보기에서 모든 인텔리전트 캡션을 한 번에 표시하거나 개별 인텔리전트 캡션을 하나씩 보도록 표시할 수도 있습니다.

* 모든 인텔리전트 캡션을 표시하려면 ![모든 인텔리전트 캡션 표시](/help/assets/icons/Maximize.svg)를 선택합니다.
* 개별 인텔리전트 캡션을 하나씩 표시하려면 ![개별 인텔리전트 캡션 표시](/help/assets/icons/Minimize.svg)를 선택합니다.

### 디스플레이 편집 {#edit}

특정 인사이트 카테고리를 숨기거나 표시하는 등 캡션 표시를 편집할 수 있습니다.

1. 인텔리전트 캡션 대화 상자에서 ![인텔리전트 캡션의 가시성 편집](/help/assets/icons/EditInLight.svg)을 선택합니다.

1. ![가시성 전환](/help/assets/icons/Visibility.svg)을 전환하여 특정 인사이트를 표시하거나(예: **[!UICONTROL 최소]**), ![가시성 전환](/help/assets/icons/VisibilityOff.svg)을 전환하여 특정 인사이트를 숨깁니다(예: **[!UICONTROL 스파이크]**).

   ![인텔리전트 캡션 편집](assets/edit-intelligent-captions.png)

1. **[!UICONTROL 적용]**&#x200B;을 선택합니다.


### 피드백 제공

생성된 인텔리전트 캡션에 대한 피드백을 제공할 수 있습니다(피드백은 확장된 캡션 보기에서만 제공 가능).

1. 인텔리전트 캡션 대화 상자에서 ![기타 액션](/help/assets/icons/More.svg)을 선택합니다.

1. ![양호한 응답](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL 양호한 응답]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL 잘못된 응답]** 또는 ![플래그](/help/assets/icons/Flag.svg) **[!UICONTROL 보고서]**&#x200B;를 선택합니다.

1. **[!UICONTROL 피드백을 보내 주셔서 감사합니다.]** 대화 상자에서 피드백을 입력하고 **[!UICONTROL 제출]**&#x200B;을 선택하여 피드백을 제출합니다.

### 내보내기 {#export}

프로젝트가 생성된 인텔리전트 캡션과 함께 저장되면 PDF의 일부로 인텔리전트 캡션을 내보낼 수 있습니다.

### 끄기 {#toggle}

인텔리전트 캡션을 표시하지 않으려면 해당 기능을 해제하면 됩니다.

1. [시각화 환경 설정](/help/analysis-workspace/user-preferences.md#visualizations-preferences)으로 이동합니다.
1. **[!UICONTROL 인텔리전트 캡션 표시]** 선택을 해제합니다.

   ![인텔리전트 캡션 표시 선택을 해제하는 옵션을 보여 주는 라인 시각화 옵션.](assets/toggle-captions.png)

1. 환경 설정을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.


## 모바일 스코어카드의 인텔리전트 캡션

인텔리전트 캡션은 Customer Journey Analytics [모바일 스코어카드](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)에서도 사용할 수 있습니다.

## 기능 액세스

다음 매개변수는 인텔리전트 캡션에 대한 액세스를 제어합니다.

* **솔루션 액세스**: 인텔리전트 캡션 기능은 Customer Journey Analytics에서는 사용할 수 있지만 Adobe Analytics에서는 사용할 수 없습니다.

* **계약적 액세스**: 인텔리전트 캡션을 사용할 수 없는 경우, 조직의 관리자나 Adobe 계정 담당자(관리자)에게 문의하십시오. 조직 내에서 인텔리전트 캡션을 사용하려면 먼저 특정 생성형 AI 관련 법적 약관에 동의해야 합니다.

* **권한**: [!UICONTROL Adobe Admin Console]에서 [!UICONTROL 보고 도구] **[!UICONTROL 인텔리전트 캡션]** 권한은 액세스를 결정합니다. [제품 프로필 관리자](https://helpx.adobe.com/kr/enterprise/using/manage-product-profiles.html)는 [!UICONTROL Admin Console]의 다음 단계를 따라야 합니다.
   1. **[!UICONTROL Admin Console]** > **[!UICONTROL 제품 및 서비스]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 제품 프로필]**&#x200B;로 이동합니다.
   1. 인텔리전트 캡션에 대한 액세스를 제공하려는 제품 프로필의 제목을 선택합니다.
   1. 특정 제품 프로필에서 **[!UICONTROL 권한]**&#x200B;을 선택합니다.
   1. ![편집](/help/assets/icons/Edit.svg)을 선택하여 **[!UICONTROL 보고 도구]**&#x200B;를 편집합니다.
   1. ![AddCircle](/help/assets/icons/AddCircle.svg)을 선택하여 **[!UICONTROL 포함된 권한 항목]**&#x200B;에 **인텔리전트 캡션**&#x200B;을 추가합니다.

      ![권한 추가](./assets/intelligent-captions-permissions.png)

   1. 권한을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

자세한 내용은 [액세스 제어](/help/technotes/access-control.md#access-control)를 참조하십시오.
