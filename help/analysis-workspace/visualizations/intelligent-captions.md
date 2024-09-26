---
description: 지능형 캡션을 사용하여 시각화 내에서 트렌드를 빠르게 표시하기 위한 자연어 통찰력을 생성합니다.
title: 지능형 캡션
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 9d94d52b14a4f119193696c1e5fc6df9538f77cb
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 5%

---

# 지능형 캡션

지능형 캡션은 고급 머신 러닝 및 생성형 AI를 사용하여 Workspace 시각화에 대한 유용한 자연어 인사이트를 제공합니다. 초기 릴리스는 [Line](line.md) 시각화에 대해 자동 생성된 인사이트를 제공합니다. 다른 시각화 요소도 함께 제공됩니다.

지능형 캡션은 다음 항목에 맞춰져 있습니다.

* 다른 사용자와 공유하기 위해 내러티브가 필요한 분석가. 분석가는 사용자에게 컨텍스트를 제공할 수 있도록 이러한 통찰력이 필요합니다.
* 높은 수준의 테이크아웃을 빠르게 발견하고자 하는 비즈니스 사용자.

## 지능형 캡션 실행 {#launch}

선 시각화에 대해 자동 생성된 캡션을 시작하려면 시각화의 오른쪽 상단에 있는 **[!UICONTROL 지능형 캡션]** 아이콘을 클릭합니다.

![제품 보기에 대한 지능형 캡션 트렌드를 표시하는 분석 시작 창. ](assets/intell-caps-1.png)

이제 자연어 인사이트가 생성됩니다.

주의 사항

* 캡션을 성공적으로 생성하려면 최소 3개의 데이터 포인트가 필요합니다. 그렇지 않으면 **[!UICONTROL 분석할 데이터가 충분하지 않음]**&#x200B;과 같은 오류가 발생할 수 있습니다.

* 시각화를 구동하는 테이블에서 기본 선택 데이터가 변경될 때마다 캡션이 생성됩니다.

* 테이블에 여러 개의 지표가 있는 경우 첫 번째 지표 또는 사용자가 현재 선택한 지표에 대해서만 캡션이 생성됩니다.

* 프로젝트를 특정 시점에 저장하고 나중에 다시 로드하는 경우 캡션이 새 데이터로 자동 업데이트됩니다. 프로젝트에서 내보낸 예약된 프로젝트 및 PDF 파일에도 적용됩니다.

다음은 지능형 캡션의 예입니다.

![시즌, 최소, 최대, 스파이크 및 쇠퇴를 포함하여 선 시각화를 위한 지능형 캡션입니다.](assets/captions.png)

## 작업

지능형 캡션에 대해 다음 작업을 수행할 수 있습니다.

### 클립보드에 복사 {#copy}

캡션을 클립보드에 복사하고 PowerPoint 또는 다른 도구에 붙여 넣을 수 있습니다. 캡션 대화 상자의 오른쪽 맨 위에 있는 ![클립보드에 캡션 복사](/help/assets/icons/Copy.svg)를 선택합니다.

### 디스플레이 편집 {#edit}

특정 범주의 인사이트를 숨기거나 숨기는 것과 같은 캡션 표시를 편집할 수 있습니다.

1. 지능형 캡션 대화 상자에서 ![지능형 캡션 표시 편집](/help/assets/icons/EditInLight.svg)을 선택합니다.

1. 특정 인사이트(예: **[!UICONTROL Min]**)를 표시하려면 ![Visibility](/help/assets/icons/Visibility.svg)를 전환하고 특정 인사이트(예: **[!UICONTROL Spike]**)를 숨기려면 ![VisibilityOff](/help/assets/icons/VisibilityOff.svg)를 전환합니다.

   ![지능형 캡션 편집](assets/edit-intelligent-captions.png)

1. **[!UICONTROL 적용]**&#x200B;을 선택합니다.


### 피드백 제공

생성된 지능형 캡션에 대한 피드백을 제공할 수 있습니다.

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

* **계약 액세스**: 지능형 캡션을 사용할 수 없는 경우 조직의 관리자 또는 Adobe 계정 담당자에게 문의하십시오. 조직에서 지능형 캡션을 사용하려면 먼저 특정 GenAI 관련 법률 용어에 동의해야 합니다.

* **권한**: [!UICONTROL Adobe Admin Console]에서 [!UICONTROL 보고 도구] **[!UICONTROL 지능형 캡션]** 권한이 액세스를 결정합니다. [제품 프로필 관리자](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)는 [!UICONTROL Admin Console]에서 다음 단계를 따라야 합니다.
   1. **[!UICONTROL Admin Console]** > **[!UICONTROL 제품 및 서비스]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 제품 프로필]**&#x200B;로 이동합니다.
   1. 지능형 캡션에 대한 액세스를 제공할 제품 프로필의 제목을 선택합니다.
   1. 특정 제품 프로필에서 **[!UICONTROL 권한]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 보고 도구]**&#x200B;를 편집하려면 ![편집](/help/assets/icons/Edit.svg)을 선택하세요.
   1. **[!UICONTROL 포함된 권한 항목]**&#x200B;에 **지능형 캡션**&#x200B;을 추가하려면 ![AddCircle](/help/assets/icons/AddCircle.svg)을(를) 선택하십시오.

      ![권한 추가](./assets/intelligent-captions-permissions.png)

   1. **[!UICONTROL 저장]**&#x200B;을 선택하여 권한을 저장합니다.

자세한 내용은 [액세스 제어](/help/technotes/access-control.md#access-control)를 참조하십시오.
