---
description: 간단한 계산된 지표를 작성하는 방법을 알아봅니다.
title: 간단한 계산된 지표 작성
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 1b6e1d432bfe4b0574b8ee68bcfa940941f3c36f
workflow-type: tm+mt
source-wordcount: '223'
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

