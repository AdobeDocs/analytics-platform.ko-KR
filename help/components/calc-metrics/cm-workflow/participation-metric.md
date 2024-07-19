---
description: 계산된 지표 빌더를 사용하여 누구나 기여도 지표를 만들 수 있습니다.
title: 기여도 지표
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 5%

---

# 참여도 지표 빌드

이 문서에서는 참여 지표를 만드는 방법을 설명합니다. 기여도 지표는 차원에 대한 개별 값 (예: 페이지 보기 수, 마케팅 채널)이 특정 지표 (예: 주문)를 포함하는 세션에 기여하거나 참여하는 방법을 보여줍니다.

이 유형의 정보는 모든 콘텐츠 소유자에게 유용할 수 있습니다.

>[!NOTE]
>
>기여도와 같은 다른 속성 모델을 사용하는 지표는 관리자가 [데이터 보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html)의 일부로 만들 수도 있습니다. 자세한 내용은 [속성 구성 요소 설정](../../../data-views/component-settings/attribution.md)을 참조하십시오.<br/>아래 예제에서는 Workspace에서 계산된 지표 빌더에 액세스할 수 있는 모든 사용자가 기여도 지표를 만드는 방법을 보여 줍니다.


1. [지표 작성](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)에 설명된 대로 지표 작성을 시작합니다.
1. 계산된 지표 빌더에서 지표 이름을 `Participation` 또는 이와 유사하게 지정합니다.
1. 성공 이벤트(예: [!DNL Orders])가 포함된 지표를 [!UICONTROL 정의] 캔버스로 드래그합니다.
1. 지표에 대해 ![톱니바퀴](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)를 선택합니다.
1. 표시되는 팝업에서 **[!UICONTROL 기본값이 아닌 속성 모델 사용]**&#x200B;을 선택하여 해당 이벤트의 [속성 모델](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)을(를) **[!UICONTROL 참여]**&#x200B;에 정의하고 [!UICONTROL 전환 확인 기간]에 대해 **[!UICONTROL 세션]**&#x200B;을(를) 선택합니다. **[!UICONTROL 적용]**&#x200B;을 선택하여 확인하십시오.

   선택한 지표의 이름에 **(파티션|세션)**&#x200B;을(를) 추가하여 정의 상자에서 업데이트합니다.

   ![전환 확인 기간 동안 선택된 모델 및 세션으로 선택된 기여도를 표시하는 열 특성 모델 팝업](assets/participation-setup.png)



1. 지표를 저장하려면 [!UICONTROL **저장**]&#x200B;을 선택하십시오.
1. 보고서에서 계산된 지표를 사용합니다. 예를 들어 보고서에 계산된 [!DNL Orders (Session Participation)] 지표(5단계에서 정의됨)를 사용하여 주문이 포함된 세션에 기여한(또는 참여한) 고객 계층을 표시합니다.

   ![고객 계층 및 주문을 표시하는 자유 형식 테이블입니다.](assets/participation-pages-customer-tier.png)

1. (선택 사항) [계산된 지표 공유](/help/components/calc-metrics/cm-workflow/cm-sharing.md)에 설명된 대로 조직의 다른 사용자와 지표를 공유합니다.
