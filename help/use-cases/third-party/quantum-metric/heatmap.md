---
title: Customer Journey Analytics과 함께 Quantum Metric Heatmap 사용
description: Quantum 지표 히트맵 데이터를 사용하여 페이지 수준 참여를 더 잘 이해하고 소비자 행동을 기반으로 페이지를 최적화합니다.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: a0f82948895f3eac86cf00df1dec8abc2f723fc2
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Customer Journey Analytics과 함께 Quantum Metric Heatmap 사용

CJA 데이터에 Quantum 지표 히트매핑을 연결하면 페이지 수준 참여를 더 잘 이해하고 소비자 행동을 기반으로 페이지를 최적화할 수 있습니다. Workspace을 사용하여 소비자 사용자 흐름을 이해하고 소비자가 한 페이지에서 다음 페이지로 이동하는 경로를 확인할 수 있습니다. 그런 다음 하이퍼링크가 설정된 페이지 URL을 클릭하여 사용자가 콘텐츠에 어떻게 참여하는지를 시각적으로 열 매핑할 수 있습니다.

이 테이블은 해당 세그먼트의 모든 세션을 반환하며, 이러한 세션 중 하나를 클릭하여 QM에서 더 자세히 탐색할 수 있습니다.  https://www.quantummetric.com/platform/session-replay에서 Quantum Metric 세션 재생에 대해 자세히 알아보십시오.

## 사전 요구 사항

이 사용 사례에서는 나머지 구현과 함께 Quantum 지표의 세션 ID를 수집해야 합니다. 구현을 수정하는 방법을 알아보려면 [Customer Journey Analytics에서 Quantum Metric 세션 ID 수집](collect-session-id.md)을 참조하세요.

Quantum 지표의 히트맵 기능에 액세스하려면 Quantum 지표의 **UX Ops** 패키지에 대한 권한이 있어야 합니다.

## Workspace에서 자유 형식 테이블을 만들고 세션 ID 값이 Quantum 지표에 직접 연결되도록 구성합니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하고 상단 메뉴에서 **[!UICONTROL Workspace]**&#x200B;을(를) 선택합니다.
1. 기존 프로젝트를 선택하거나 프로젝트를 만듭니다.
1. [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)을 만듭니다.
1. 페이지 URL 차원을 Workspace 캔버스로 드래그합니다.
1. 차원 열 헤더를 마우스 오른쪽 단추로 클릭한 다음 **[!UICONTROL 모든 차원 항목에 대한 하이퍼링크 만들기]**&#x200B;를 선택합니다.
1. **[!UICONTROL 사용자 지정 URL 만들기]**&#x200B;를 선택합니다.
1. 다음 URL 구조를 붙여넣습니다.

   ```
   $value?qm-visible=true
   ```

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

1. 만들기 를 클릭한 다음 링크 중 하나를 테스트하여 QM 확장자가 팝업된 상태로 URL에서 열리는지 확인합니다. 참고 - 별도의 탭에서 열리므로 작업을 잃지 않습니다.


## Customer Journey Analytics 내의 링크를 클릭하여 Heatmap 보기

열 매핑을 탐색할 페이지가 발견되면 URL이 포함된 패널에 적용할 수 있습니다. 이 표에서는 해당 페이지의 히트맵, 스크롤 깊이 및 상호 작용을 위한 키 영역을 탐색할 수 있는 URL을 반환합니다.  Quantum Metric Heatmap에 대해 자세히 알아보십시오. https://www.quantummetric.com/platform/interaction-heatmaps


