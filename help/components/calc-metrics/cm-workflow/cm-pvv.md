---
description: 간단한 계산된 지표를 작성하는 방법을 알아봅니다.
title: 간단한 계산된 지표 작성
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
TQID: https://experienceleague.adobe.com/hbiAmMoSUMm2Ggf5Vkxm484SzYETtgRRZAuaWvlS884
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 17%

---

# 간단한 계산된 지표 작성

다음 정보는 간단한 *방문당 페이지 보기 수* 지표를 만드는 방법을 설명합니다.

1. [지표 작성](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)에 설명된 대로 지표 작성을 시작합니다.
1. 지표 이름을 `Page Views per Session` 또는 이와 유사하게 지정합니다.
1. 지표에 지표가 사용되는 용도를 표시하려면 사용자에게 친숙한 **[!UICONTROL 설명]**&#x200B;을 지정하십시오.
1. 올바른 **[!UICONTROL 형식]**&#x200B;을(를) 선택하십시오. 이 예제에서는 **[!UICONTROL 십진수]**&#x200B;를 선택합니다.
1. 보고서를 표시할 소수점 이하 자리수를 결정합니다.
1. **[!UICONTROL 추세를]**(으)로 표시 드롭다운 메뉴에서 ▲ **[!UICONTROL 양호(녹색)]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL 태그]**&#x200B;를 추가하여 지표를 정리합니다.
1. 이 계산된 지표의 경우 먼저 **[!UICONTROL 지표]** 구성 요소에서 캔버스의 **[!UICONTROL 정의]** 섹션으로 **[!UICONTROL 페이지 보기 수]**&#x200B;를 끌어옵니다.
1. 그런 다음 **[!UICONTROL 지표]** 구성 요소에서 **[!UICONTROL 세션]**&#x200B;을 드래그하고 지표를 **[!UICONTROL 페이지 보기 수]** 아래에 놓습니다(지표를 놓기 전에 파란색 선이 나타날 때까지 대기).
1. 나누기 ![나누기](/help/assets/icons/Divide.svg) 연산자를 선택하십시오. (나누기는 기본 연산자입니다.)
1. 지표를 빌드하는 동안 지표의 **[!UICONTROL 미리 보기]**&#x200B;를 볼 수 있습니다.
1. **[!UICONTROL 제품 호환성]**&#x200B;은(는) 계산된 지표가 Customer Journey Analytics의 모든 곳에서 호환되는지 여부를 표시합니다(실험 제외).

   ![단순 계산된 지표](assets/simple-calculated-metric.png)
1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

   **[!UICONTROL 요약]** 공식은 지표 정의를 변경할 때마다 업데이트된다는 점을 참고하십시오.

1. (선택 사항) 지표를 공유, 승인, (재)태깅, 이름 변경 또는 삭제하려면 [계산된 지표 관리자](/help/components/calc-metrics/cm-workflow/cm-manager.md)(으)로 이동하십시오.

