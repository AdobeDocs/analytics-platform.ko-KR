---
description: 주문 추진에 도움이 되는 마케팅 채널을 보여 주는 지표를 만드는 방법을 설명합니다.
title: 보다 복잡한 계산된 지표 작성
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
TQID: https://experienceleague.adobe.com/T5hA3-IeRUfDR53RL6TnJUslUI7XxRSZN2KpPKAz7k0
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 3%

---

# 보다 복잡한 계산된 지표 작성

이 문서에서는 계산된 지표의 보다 복잡한 예제를 설명합니다. 이 계산된 지표는 주문 제작에 도움이 되는 마케팅 채널을 보여 줍니다. 이 유형의 계산된 지표는 모든 차원 또는 성공 이벤트에 적용할 수 있습니다.

1. [지표 작성](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)에 설명된 대로 계산된 지표를 작성합니다.

1. 계산된 지표 빌더에서 지표 이름을 `Assisted Online Orders` 또는 이와 유사하게 지정합니다.

1. **[!UICONTROL 지표]** 구성 요소에서 **[!UICONTROL 온라인 주문]** 지표를 선택하고 지표를 **[!UICONTROL 정의]** 영역으로 끌어서 놓습니다.

   1. 지표에 대해 ![설정](/help/assets/icons/Setting.svg)을(를) 선택합니다.
   1. **[!UICONTROL 비기본 속성 모델 사용]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 열 속성 모델]**&#x200B;에서 속성 모델을 조정합니다.
      1. **[!UICONTROL 모델]**&#x200B;에 대해 **[!UICONTROL 사용자 지정]**&#x200B;을(를) 선택하십시오. **[!UICONTROL Starter]**&#x200B;을(를) `0`(으)로, **[!UICONTROL Player]**&#x200B;을(를) `100`(으)로, **[!UICONTROL Closer]**&#x200B;을(를) `0`(으)로 설정합니다.
      1. **[!UICONTROL 컨테이너]**&#x200B;에 대해 **[!UICONTROL 방문자]**&#x200B;을(를) 선택하십시오.
      1. **[!UICONTROL 전환 확인 기간]**&#x200B;에 대해 **[!UICONTROL 30일]**&#x200B;을(를) 선택하십시오.

      1. **[!UICONTROL 적용]**&#x200B;을 선택합니다.

      ![열 속성 모델](assets/complex-calculated-metric.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택하여 계산된 지표를 저장합니다.

계산된 지표를 사용하려면 다음을 수행하십시오.

1. Analysis Workspace에서 **[!UICONTROL 마케팅 채널]** 차원, **[!UICONTROL 온라인 주문]** 및 새 **[!UICONTROL 온라인 주문 지원]** 지표를 사용하여 자유 형식 테이블을 만듭니다.

   ![마케팅 채널 지원 온라인 주문](assets/marketing-channel-assists.png)

1. (선택 사항) [계산된 지표 공유](/help/components/calc-metrics/cm-workflow/cm-sharing.md)에 설명된 대로 조직의 다른 사용자와 지표를 공유합니다.

이는 주문 제작에 도움이 되는 마케팅 채널을 쉽게 알 수 있는 방법입니다. 또는 자유 형식 테이블에서 지표를 선택하고 컨텍스트 메뉴에서 속성 모델을 테이블에서 직접 조정할 수 있습니다.
