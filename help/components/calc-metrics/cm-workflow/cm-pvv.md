---
description: 간단한 "방문당 페이지 보기 수" 지표를 만드는 방법을 표시합니다.
title: 간단한 "방문자 수당 페이지 보기 수" 지표 작성
feature: Calculated Metrics
exl-id: 46c83a1f-cb2d-4d5d-af4f-e1d2e4566743
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 100%

---

# 간단한 &quot;방문자 수당 페이지 보기 수&quot; 지표 작성

간단한 &quot;방문당 페이지 보기 횟수&quot; 지표를 만드는 방법을 표시합니다.

UI 구성 요소에 대한 자세한 설명은 [지표 작성](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

다음은 간단한 &quot;방문당 페이지 보기 수&quot; 지표를 만드는 방법입니다.

1. 계산된 지표 빌더로 이동합니다.
1. 지표의 이름을 &quot;방문당 페이지 보기 수&quot; 또는 이와 유사하게 지정합니다.
1. 사용자에게 친근한 **[!UICONTROL 설명]**&#x200B;을 지정하여 용도를 알 수 있도록 합니다.
1. 올바른 **[!UICONTROL 공식]**&#x200B;을 선택합니다. 이 경우에는 십진수입니다.
1. 보고서를 표시할 소수점 이하 자리수를 결정합니다.
1. 지표 극성을 설정합니다. 이 지표의 경우, 증가 트렌드가 좋은 (녹색) 것입니다.
1. **[!UICONTROL 태그]**&#x200B;를 추가하여 지표를 정리합니다.
1. 이 지표의 경우, 먼저 페이지 보기 수를 캔버스로 드래그한 다음 그 아래의 방문 수를 드래그합니다(파란색 선이 나타날 때까지 기다렸다가 놓음).
1. 나누기 연산자를 선택합니다. (나누기는 기본 연산자입니다.)
1. 이제 지표를 만들면 오른쪽 상단에서 해당 지표의 **[!UICONTROL 미리보기]**&#x200B;를 볼 수 있습니다.
1. **[!UICONTROL 저장을 클릭합니다]**.
1. **[!UICONTROL 요약]** 공식은 지표 정의를 변경할 때마다 업데이트된다는 점을 참고하십시오.
1. 이제 필터 관리자와 유사한 [계산된 지표 관리자](/help/components/calc-metrics/cm-workflow/cm-manager.md)가 자동으로 표시됩니다. 지표를 공유, 승인, (재)태깅, 이름 변경 또는 삭제할 수 있도록 해 줍니다.
