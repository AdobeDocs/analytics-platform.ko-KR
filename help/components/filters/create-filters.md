---
title: 필터 만들기
description: 필터 만들기 사용자 인터페이스를 이해합니다.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 38%

---


# 필터 만들기

필터 빌더는 컨테이너 계층 논리, 규칙 및 연산자를 기준으로 지표 차원, 필터 및 이벤트를 필터 방문자로 드래그하여 놓을 수 있는 캔버스를 제공합니다. 이러한 통합 개발 도구를 사용하여 방문 횟수와 페이지 히트 수에 걸쳐 방문자 속성 및 작업을 식별하는 간단하거나 복잡한 필터를 작성하고 저장할 수 있습니다.

패널 상단의 필터 드롭 영역에 구성 요소 유형(차원, 차원 항목, 이벤트, 지표, 세그먼트, 세그먼트 템플릿, 날짜 범위)을 드롭하여 즉석 필터를 만들 수 있습니다.

구성 요소 유형은 필터로 자동 변환됩니다. Alternatively, you can click the &quot;+&quot; sign in the **[!UICONTROL Add Filter]** drop box.

주의 사항:

* You **cannot** drop the following component types into the filter zone: calculated metrics and dimensions/metrics from which you cannot build filters.
* 전체 차원 및 이벤트의 경우 Analysis Workspace은 &quot;존재함&quot; 히트 필터를 만듭니다. 예: &quot;eVar1이 있는 위치 히트&quot; 또는 &quot;event1이 있는 위치 히트&quot;.
* 필터 드롭 영역에 &quot;지정되지 않음&quot; 또는 &quot;없음&quot;이 놓이면 &quot;존재하지 않음&quot; 필터로 자동 변환되므로 올바로 처리됩니다.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>이렇게 만든 필터는 프로젝트 내부입니다.

다음 단계에 따라 이러한 필터를 공개(전역)하도록 선택할 수 있습니다.

1. 드롭 영역의 필터 위로 마우스를 가져간 다음 &quot;i&quot; 아이콘을 클릭합니다.
1. 표시되는 정보 패널에서 **[!UICONTROL 공개하기를 클릭합니다]**.

   ![](assets/segment-info.png)

## 필터를 적용하는 기타 방법

프로젝트에 필터를 적용하는 다른 몇 가지 방법이 있습니다.

| 작업 | 설명 |
|--- |--- |
| 선택 항목에서 필터 만들기 | 인라인 필터를 만듭니다. 행을 선택하고 선택 항목을 마우스 오른쪽 단추로 클릭한 다음 인라인 필터를 만듭니다. 이 필터는 열린 프로젝트에만 적용되며 CJA 필터로 저장되지 않습니다. 1. 행을 선택합니다. 2. 선택 항목을 마우스 오른쪽 단추로 클릭합니다. 3. Click *Create filter from selection*. |
| 구성 요소 > 새 필터 | 필터 빌더를 표시합니다. See [Filter Builder](https://docs.adobe.com/content/help/ko-KR/analytics/components/segmentation/segmentation-workflow/seg-build.html) for more information about filtering. |
| 공유 > 프로젝트 공유 또는 공유 > 프로젝트 데이터 조정 | In [Curate and Share](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), learn how filters that you apply to the project are available in shared analysis for the recipient. |
| 필터를 차원으로 사용 | 비디오: [Analysis Workspace에서 세그먼트를 차원으로 사용](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
