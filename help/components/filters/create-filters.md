---
title: 필터 만들기
description: 필터 만들기 사용자 인터페이스를 이해합니다.
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
source-git-commit: b907e62bfabd8cb42dc89d551d7b5285cb61298e
workflow-type: ht
source-wordcount: '368'
ht-degree: 100%

---

# 필터 만들기

필터 빌더는 컨테이너 계층 논리, 규칙 및 연산자를 기준으로 지표 차원, 필터 및 이벤트를 필터 방문자로 드래그하여 놓을 수 있는 캔버스를 제공합니다. 이러한 통합 개발 도구를 사용하여 방문 횟수와 페이지 히트 수에 걸쳐 방문자 속성 및 작업을 식별하는 간단하거나 복잡한 필터를 작성하고 저장할 수 있습니다.

구성 요소 유형(차원, 차원 항목, 이벤트, 지표, 필터, 필터 템플릿, 날짜 범위)을 패널 위쪽에 필터 드롭 영역으로 드래그하여 인스턴스 필터를 생성할 수 있습니다.

구성 요소 유형은 자동으로 필터로 변환됩니다. 또는 **[!UICONTROL 필터 추가]** 드롭박스에서 &quot;+&quot; 기호를 클릭할 수도 있습니다.

주의 사항:

* 다음 구성 요소 유형을 필터 영역으로 끌어 놓을 수 **없음**: 필터를 빌드할 수 없는 계산된 지표 및 차원/지표.
* 전체 차원 및 이벤트에 대해 Analysis Workspace는 &quot;존재함&quot; 히트 필터를 만듭니다. 예: &quot;eVar1이 있는 위치 히트&quot; 또는 &quot;event1이 있는 위치 히트&quot;.
* 필터를 놓는 영역에 &quot;지정되지 않음&quot; 또는 &quot;없음&quot;을 놓으면 올바로 처리되도록 자동으로 &quot;존재하지 않음&quot; 필터로 변환됩니다.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>이러한 방식으로 생성된 필터는 프로젝트 내부에서 사용됩니다.

다음 단계를 수행하여 이러한 필터를 공개(전역)로 지정하도록 선택할 수 있습니다.

1. 드롭 영역의 필터 위에 커서를 놓고 &quot;i&quot; 아이콘을 클릭합니다.
1. 표시되는 정보 패널에서 **[!UICONTROL 공개하기]**&#x200B;를 클릭합니다.

   ![](assets/segment-info.png)

## 필터를 적용하는 다른 방법

자유 형식 프로젝트에 필터를 적용하는 몇 가지 다른 방법이 있습니다.

| 작업 | 설명 |
|--- |--- |
| 선택 내용에서 필터 생성 | 인라인 필터를 만듭니다. 이 필터는 열려 있는 프로젝트에만 적용되며, CJA 필터로 저장되지는 않습니다.<p> 1. 필터에 포함할 테이블 행을 선택합니다. 2. 선택 항목을 마우스 오른쪽 버튼으로 클릭합니다.  3. *선택 항목에서 필터 만들기*&#x200B;를 클릭합니다. |
| 구성 요소 > 새 필터 | 필터 빌더를 표시합니다. 필터링에 대한 자세한 내용은 [필터 빌더](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=ko-KR)를 참조하십시오. |
| 공유 > 프로젝트 공유 또는 공유 > 프로젝트 데이터 조정 | [조정 및 공유](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=ko-KR#concept_4A9726927E7C44AFA260E2BB2721AFC6)에서, 수신자를 위한 공유 분석에서 프로젝트에 적용하는 필터를 어떻게 사용할 수 있는지 알아봅니다. |
| 필터를 차원으로 사용 | 비디오: Analysis Workspace에서 필터를 차원으로 사용 |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
