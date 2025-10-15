---
description: Workspace 보고서에서 pptx 형식의 프레젠테이션을 생성하는 방법을 알아봅니다.
keywords: Analysis Workspace
title: Workspace 보고서에서 프레젠테이션 생성
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 680799fdf18703acbd0569e25b41e6ecbc154d62
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 3%

---

# Data storytelling: Workspace 보고서에서 슬라이드 프레젠테이션 생성 {#generate-powerpoint}

Analysis Workspace 프로젝트에서 .pptx 프레젠테이션을 자동으로 생성할 수 있습니다. Customer Journey Analytics은 프레젠테이션을 생성할 때 주요 인사이트를 자동으로 식별하고 관련자가 사용할 수 있는 슬라이드로 변환합니다.

이 기능을 사용하면 Workspace 프로젝트의 결과를 표시하는 데 필요한 시간과 노력을 줄일 수 있으며, 이를 통해 경영진 설명을 신속하게 작성하고 비즈니스 영향을 전달할 수 있습니다.

## Workspace 프로젝트를 기반으로 .pptx 프레젠테이션 생성

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="포함된 패널 및 시각화"
>abstract="프레젠테이션에 포함할 패널 및 시각화를 선택합니다. 최대 50개의 시각화를 포함할 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="강조된 구성 요소"
>abstract="프레젠테이션에서 강조할 시각화에서 최대 5개의 지표와 5개의 차원을 선택합니다. 선택하는 지표는 기울임꼴로 표시되고, 차원은 굵게 표시되며, 차원 항목은 대비색으로 표시됩니다."

<!-- markdownlint-enable MD034 -->

1. 프레젠테이션의 기반으로 사용할 데이터가 포함된 Workspace 프로젝트로 이동합니다.

1. 페이지의 오른쪽 상단에서 **[!UICONTROL 슬라이드 생성]**&#x200B;을 선택합니다.

1. 다음 정보를 지정합니다.

   | 옵션 | 설명 |
   |---------|----------|
   | **[!UICONTROL 표지 제목]** | 프레젠테이션의 제목을 지정합니다. 이 제목은 프레젠테이션의 제목 슬라이드에 표시됩니다. |
   | **[!UICONTROL 발표자 이름 포함]** | 발표자의 이름을 지정합니다. 이 이름은 프레젠테이션의 제목 슬라이드에 있으며 표지 제목 아래에 있습니다. |
   | 포함할 **[!UICONTROL 패널 및 시각화]** | 프레젠테이션에 포함할 패널 및 시각화를 선택합니다. 최대 50개의 시각화를 포함할 수 있습니다.<p>대부분의 패널 및 시각화가 지원됩니다. 지원되지 않는 패널 및 시각화에 대한 자세한 내용은 [지원되지 않는 프로젝트 요소 및 기능](#unsupported-project-elements-and-features)을 참조하십시오.</p> |
   | **[!UICONTROL 패널 및 시각화 설명]** | |
   | **[!UICONTROL 주석]** | |
   | **[!UICONTROL 구성 요소 강조]** | 프레젠테이션에서 강조할 시각화에서 최대 5개의 지표와 5개의 차원을 선택합니다.<p>강조를 적용하지 않으면 구성 요소는 다음과 같이 프레젠테이션에 표시됩니다.<ul><li>**지표 및 차원:** 기울임꼴</li><li>**Dimension 항목:** 큰따옴표</li></ul></p><p>강조를 적용하면 구성 요소가 프레젠테이션에 다음과 같이 표시됩니다.</p><ul><li>**지표 및 차원:** 기울임체 및 굵게</li><li>해당 차원이 강조된 경우 **Dimension 항목:** 굵게<p>차트에서 차원 항목이 강조 표시되면 색상도 차원 항목에 적용됩니다.</p></li></ul> |

(조건부) 기본 테마를 사용하여 슬라이드를 생성하려면 **[!UICONTROL 기본 테마]**&#x200B;를 선택합니다.

1. 기본 테마를 사용할지 또는 사용자 지정 템플릿을 업로드할지 여부를 선택합니다.

   * **[!UICONTROL 기본 테마]**:

   * **[!UICONTROL 템플릿 업로드]**:





## 이전에 생성한 프레젠테이션의 슬라이드 편집


## 생성된 .pptx 프레젠테이션 다운로드

## 지원되지 않는 프로젝트 요소 및 기능 {#unsupported}

슬라이드를 생성할 때 프로젝트에 사용되는 다음 Analysis Workspace 요소 및 기능은 지원되지 않습니다.

* 속성 패널

  구성 옵션이 표시되면 이 패널은 흐리게 표시됩니다.

  다른 모든 패널은 Workspace 프로젝트에서 생성된 슬라이드에 포함할 수 있습니다.

* 일부 시각화

  대부분의 시각화는 Workspace 프로젝트에서 생성된 슬라이드에 포함할 수 있습니다. 하지만 다음 시각화는 포함할 수 없으며 구성 옵션이 표시될 때 흐리게 표시됩니다.

   * 코호트 테이블

   * 여정 캔버스

   * 글머리 기호

   * 콤보

   * 분산

   * 트리맵

* 분류

* 안내식 분석


