---
title: Customer Journey Analytics의 데이터에 양자 지표 세션 재생 연결
description: 양자 지표 연결 세션은 "무엇을"의 "이유"를 더 잘 이해하기 위해 CJA 데이터로 재생됩니다.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 9563b13da52963eaf7b17050fb9a7cb3a47ef1ed
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 1%

---

# Customer Journey Analytics의 데이터에 양자 지표 세션 재생 연결

Quantum Metric 세션 재생과 CJA 데이터를 연결함으로써 고객은 &quot;내용&quot; 이면의 &quot;이유&quot;를 더 잘 이해할 수 있습니다.  Workspace을 사용하여 마찰이 있는 세션을 검색한 다음 하이퍼링크된 세션 ID를 클릭하여 Quantum 지표에서 세션 재생 을 탐색할 수 있습니다.  이 데이터를 사용하면 세션 내의 비헤이비어를 보고 소비자 마찰을 유도하는 요소를 더 잘 이해할 수 있습니다.  CJA과 연결된 세션 재생을 통해 경험에서 고객 행동에 대한 중요한 컨텍스트를 캡처할 수 있습니다.

## 전제 조건:

이 사용 사례에서는 나머지 구현과 함께 Quantum 지표의 세션 ID를 수집해야 합니다. 구현을 수정하는 방법을 알아보려면 [Customer Journey Analytics에서 Quantum Metric 세션 ID 수집](collect-session-id.md)을 참조하세요.

## 1단계: 세션 ID 차원을 수용하도록 Workspace 구성

Workspace에서 자유 형식 테이블을 만들고 세션 ID 값이 Quantum 지표에 직접 연결되도록 구성합니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하고 상단 메뉴에서 **[!UICONTROL Workspace]**&#x200B;을(를) 선택합니다.
1. 기존 프로젝트를 선택하거나 프로젝트를 만듭니다.
1. [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)을 만듭니다.
1. 세션 ID 차원을 Workspace 캔버스로 드래그합니다.
1. 차원 열 헤더를 마우스 오른쪽 단추로 클릭한 다음 **[!UICONTROL 모든 차원 항목에 대한 하이퍼링크 만들기]**&#x200B;를 선택합니다.
1. **[!UICONTROL 사용자 지정 URL 만들기]**&#x200B;를 선택합니다.
1. 다음 URL 구조를 붙여넣습니다.

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

이제 각 세션 ID를 클릭 가능한 링크로 지정할 수 있습니다. Analysis Workspace 차원 항목에 하이퍼링크를 추가하는 방법에 대한 자세한 내용은 [자유 형식 테이블에 하이퍼링크 만들기](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)를 참조하십시오.

## 2단계 Customer Journey Analytics에서 세션 보기

세션 재생을 탐색할 관심 있는 세그먼트를 찾으면 세션 ID 링크가 포함된 패널에 적용하고 세그먼트별로 필터링할 수 있습니다. 이 테이블은 해당 세그먼트의 모든 세션을 반환하며, 이러한 세션 중 하나를 클릭하여 양자 지표에서 자세히 탐색할 수 있습니다.

[https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay)에서 Quantum 지표 세션 재생에 대해 자세히 알아보세요. 추가 리소스는 Quantum Metric 고객 지원 담당자에게 문의하거나 Quantum Metric [고객 요청 포털](https://community.quantummetric.com/s/public-support-page)을 통해 요청을 제출하십시오.

