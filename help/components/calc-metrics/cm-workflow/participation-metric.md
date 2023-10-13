---
description: 계산된 지표 빌더를 사용하여 누구나 기여도 지표를 만들 수 있습니다.
title: 기여도 지표
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d95d324350a2f8aa77032e7cac1c924d161d47ce
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 17%

---

# “참여도” 지표 작성

이 문서에서는 선택한 차원(예: 페이지 보기 수, 마케팅 채널, 앱 버전)에 대한 개별 값이 주문이 포함된 세션에 어떻게 기여했는지(또는 참여했는지) 보여 주는 지표를 만드는 방법을 설명합니다.

이 유형의 정보는 모든 콘텐츠 소유자에게 유용할 수 있습니다.

>[!NOTE]
>
>기여도와 같은 다른 속성 모델을 사용하는 지표는 관리자가 의 일부로 만들 수도 있습니다. [데이터 보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). 아래 예제는 작업 영역에서 계산된 지표 빌더에 액세스할 수 있는 모든 사용자가 이러한 지표를 만드는 방법을 보여 줍니다.

1. 에 설명된 대로 지표 작성을 시작합니다. [지표 작성](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. 계산된 지표 빌더에서 지표의 이름을 &quot;기여도&quot; 또는 이와 유사하게 지정합니다
1. 성공 이벤트 &quot;주문&quot;을 정의 캔버스로 드래그합니다.
1. 선택 ![톱니바퀴](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) 대상: [!DNL Orders] 지표.
1. 표시되는 팝업에서 을 선택합니다. **[!UICONTROL 기본이 아닌 속성 모델 사용]** 을(를) 정의하려면 [속성 모델](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) 에 대한 해당 이벤트 **[!UICONTROL 기여도]** 및 선택 **[!UICONTROL 세션]** 대상: [!UICONTROL 전환 확인 기간]. 선택 **[!UICONTROL 적용]** 확인할 수 있습니다.

   정의 상자에서 ![이벤트](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **주문 수** 이(가) (으)로 업데이트되었습니다. ![이벤트](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **주문(파티션|세션)**.

   ![](assets/participation-setup.png)



1. 선택 [!UICONTROL **저장**] 지표를 저장합니다.
1. 보고서에서 계산된 지표를 사용합니다. 계산된 지표 아래에 있는 은 주문이 포함된 세션에 기여한 (또는 참여한) 고객 계층을 표시하는 보고서에 사용됩니다.

   ![](assets/participation-pages-customer-tier.png)

1. (선택 사항) 의 설명에 따라 조직의 다른 사용자와 지표를 공유합니다 [계산된 지표 공유](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
