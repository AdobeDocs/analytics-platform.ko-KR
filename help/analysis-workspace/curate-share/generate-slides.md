---
description: Workspace 보고서에서 pptx 형식의 프레젠테이션을 생성하는 방법을 알아봅니다.
keywords: Analysis Workspace
title: Workspace 보고서에서 프레젠테이션 생성
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 9e23382800326440ed2a583e80029c9f27bb2494
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 4%

---

# Data storytelling: Workspace 보고서에서 슬라이드 프레젠테이션 생성 {#generate-powerpoint}

[필요한 권한](#permission-requirements-to-generate-slides)이 있는 사용자는 Analysis Workspace 프로젝트에서 .pptx 프레젠테이션을 자동으로 생성할 수 있습니다. 이러한 슬라이드 프레젠테이션을 생성할 때 Customer Journey Analytics은 주요 인사이트를 식별하고 관련자가 사용할 수 있는 슬라이드로 변환하여 데이터에서 스토리를 자동으로 생성합니다.

이 기능을 사용하면 Workspace 프로젝트의 결과를 표시하는 데 필요한 시간과 노력을 줄일 수 있으며, 이를 통해 경영진 설명을 신속하게 작성하고 비즈니스 영향을 이해 당사자에게 전달할 수 있습니다.

이렇게 자동 생성된 데이터 스토리를 통해 분석가는 데이터 탐색에 집중할 수 있으며 Customer Journey Analytics은 관련자 소비를 위해 분석가가 발견한 내용을 선별하고 형식을 지정할 수 있습니다.

## 슬라이드 프레젠테이션의 데이터 스토리 이해

Analysis Workspace은 생성 AI를 사용하여 슬라이드 프레젠테이션 내에서 데이터 스토리를 생성합니다. 이러한 데이터 스토리는 추가 컨텍스트를 제공하고 중요한 하이라이트를 표시하며 다음 단계에 대한 아이디어를 제공하여 주어진 Workspace 프로젝트에 대한 분석을 보완합니다. 숨겨진 트렌드, 예외 항목, 기여 요인, 주요 요인

### 데이터 스토리에서 제공하는 추가 값

데이터 스토리는 다음과 같은 방법으로 주어진 Workspace 프로젝트에 대한 분석을 보완합니다.

* 추가 컨텍스트 제공

* 중요한 인사이트 강조 표시

* 숨겨진 트렌드, 예외 항목 및 기타 기여 요소 표시

* 주요 드라이버 식별

* 다음 단계에 대한 아이디어 제공

### 데이터 스토리를 형성하는 프로젝트 요소

Analysis Workspace은 다음 프로젝트 요소를 고려하여 데이터 스토리를 생성합니다.

* 차원 간 및 지표 간 관계

* 분석의 기초를 이루는 개별 요소: 차원, 지표, 필터, 자유 형식 테이블 구조, 시각화 및 패널

* 패널, 테이블 및 시각화에 지정된 이름

* 자유 형식 테이블에서 지표의 순서 지정(우선 순위 결정)

* 요약 번호 및 요약 텍스트(데이터 스토리에서 강조 표시해야 하는 지표를 결정하기 위한)

### 데이터 스토리의 프레젠테이션 요소

데이터 스토리는 요약 슬라이드, 세부 슬라이드 및 섹션 구분자로 구성됩니다.

**실행 요약:** 가장 높은 가치의 통찰력을 우선시하며 길이가 1~5문장 사이인 중요한 스토리를 만듭니다.

**세부 슬라이드:** Workspace 프로젝트의 테이블, 패널 또는 시각화와 관련된 통찰력을 생성합니다. 인사이트는 트렌드, 계절성, 예외 항목 및 상관 관계로 구성됩니다.

**섹션 분할자:** 적절하게 배치된 섹션 분할자와 명명된 섹션 분할자로 인사이트를 나눕니다.

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

1. 슬라이드 프레젠테이션의 기반으로 사용할 데이터가 포함된 Workspace 프로젝트로 이동합니다.

1. 페이지의 오른쪽 상단에서 **[!UICONTROL 슬라이드 생성]**&#x200B;을 선택합니다.

   슬라이드 생성 대화 상자가 표시됩니다.

   ![슬라이드 생성 대화 상자](assets/generate-slides.png)

1. 다음 정보를 지정합니다.

   | 옵션 | 설명 |
   |---------|----------|
   | **[!UICONTROL 표지 제목]** | 프레젠테이션의 제목을 지정합니다. 이 제목은 프레젠테이션의 제목 슬라이드에 표시됩니다. |
   | **[!UICONTROL 발표자 이름 포함]** | 발표자의 이름을 지정합니다. 이 이름은 프레젠테이션의 제목 슬라이드에 있으며 표지 제목 아래에 있습니다. |
   | 포함할 **[!UICONTROL 패널 및 시각화]** | 프레젠테이션에 포함할 패널 및 시각화를 선택합니다. 최대 50개의 시각화를 포함할 수 있습니다.<p>대부분의 패널 및 시각화가 지원됩니다. 지원되지 않는 패널 및 시각화에 대한 자세한 내용은 [지원되지 않는 프로젝트 요소 및 기능](#unsupported-project-elements-and-features)을 참조하십시오.</p> |
   | **[!UICONTROL 패널 및 시각화 설명]** | |
   | **[!UICONTROL 주석]** | |
   | **[!UICONTROL 구성 요소 강조]** | 프레젠테이션에서 강조할 시각화에서 최대 5개의 지표와 5개의 차원을 선택합니다.<p>강조를 적용하지 않으면 구성 요소는 다음과 같이 프레젠테이션에 표시됩니다.<ul><li>**지표 및 차원:** 기울임꼴</li><li>**Dimension 항목:** 큰따옴표</li></ul></p><p>강조를 적용하면 구성 요소가 프레젠테이션에 다음과 같이 표시됩니다.</p><ul><li>**지표 및 차원:** 기울임체 및 굵게</li><li>해당 차원이 강조된 경우 **Dimension 항목:** 굵게<p>차트에서 차원 항목이 강조 표시되면 색상도 차원 항목에 적용됩니다.</p></li></ul> |

1. (조건부) 슬라이드 프레젠테이션에 회사 테마가 필요하지 않은 경우 더 적은 단계로 슬라이드를 빠르게 생성하려면 **[!UICONTROL 기본 테마]**&#x200B;를 선택합니다.

   원하는 색상을 선택하여 프레젠테이션의 색상 테마를 선택하면 됩니다.

   ![기본 테마를 사용하여 슬라이드 생성](assets/generate-slides-default-theme.png)

1. (조건부) 슬라이드 프레젠테이션이 회사 테마와 일치해야 하는 경우 **[!UICONTROL 템플릿 업로드]**&#x200B;를 선택합니다. 이 옵션을 사용하려면 사용자 지정 템플릿을 업로드하고 사용자 지정 스타일을 적용해야 합니다.

   ![사용자 지정 템플릿으로 슬라이드 생성](assets/generate-slides-upload-template.png)

   사용자 지정 템플릿을 업로드하려면 다음 중 하나를 수행하십시오.

   * (권장) 빈 템플릿을 다운로드하고 수정합니다.

      1. 이 빈 템플릿을 다운로드합니다. <!--add link-->

      1. 빈 템플릿에 사용자 지정 스타일을 적용합니다.

      1. 마스터 레이아웃 이름을 변경하지 않고 템플릿을 다시 업로드합니다.

   * 사용자 지정 템플릿을 바로 업로드합니다.

      1. 파일 시스템에서 사용자 지정 템플릿을 드롭 영역으로 드래그합니다.

         또는

         **[!UICONTROL 찾아보기]**&#x200B;를 선택한 다음 파일 시스템에서 사용자 지정 템플릿을 찾아 선택합니다.

         업로드된 파일에 &quot;Title_Slide&quot;, &quot;Section_Divider&quot;, &quot;Title_Text&quot;, &quot;Title_Chart&quot;, &quot;Title_Two_Content_Mixed&quot;, &quot;Title_Three_Content_Mixed&quot; 이름이 있는 마스터 레이아웃이 있는지 확인합니다.

         최대 25MB의 .pptx 및 .potx 파일이 지원됩니다.

1. **[!UICONTROL PPT 내보내기]**&#x200B;를 선택합니다.

1. (권장) 다음 섹션 [이전에 생성된 프레젠테이션의 슬라이드 편집](#edit-slides-from-a-previously-generated-presentation)에 설명된 대로 .ppt 프레젠테이션을 검토 및 편집하고 필요한 변경을 수행합니다.

## 이전에 생성한 프레젠테이션의 슬라이드 편집


## 생성된 .pptx 프레젠테이션 다운로드



## 슬라이드 생성을 위한 권한 요구 사항

>[!AVAILABILITY]
>
>조직에서 Workspace 프로젝트에서 슬라이드 프레젠테이션을 생성할 수 있는 액세스 권한이 없는 경우 Adobe 계정 담당자에게 문의하여 라이선싱에 대한 자세한 내용을 확인하십시오.
>
>이 기능은 필요한 라이선스가 있는 조직의 모든 사용자에 대해 기본적으로 활성화됩니다.

조직에 슬라이드 생성 라이선스가 있는 제품 프로필 관리자는 필요한 경우 액세스를 비활성화할 수 있습니다.

[!UICONTROL Adobe Admin Console]에서 [!UICONTROL 보고 도구] **[!UICONTROL 데이터 storytelling]** 권한은 이 기능에 대한 액세스를 결정합니다. [제품 프로필 관리자](https://helpx.adobe.com/kr/enterprise/using/manage-product-profiles.html)가 액세스를 사용하지 않도록 설정하려면 [!UICONTROL Admin Console]에서 다음 단계를 따라야 합니다.
1. **[!UICONTROL Admin Console]** > **[!UICONTROL 제품 및 서비스]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 제품 프로필]**&#x200B;로 이동합니다.
1. [!UICONTROL Data storytelling]에 대한 액세스 권한을 제공할 제품 프로필의 제목을 선택합니다.
1. 특정 제품 프로필에서 **[!UICONTROL 권한]**&#x200B;을 선택합니다.
1. ![편집](/help/assets/icons/Edit.svg)을 선택하여 **[!UICONTROL 보고 도구]**&#x200B;를 편집합니다.
1. ![포함된 권한 항목](/help/assets/icons/RemoveCircle.svg)에서 **데이터 storytelling**&#x200B;을(를) 제거하려면 **[!UICONTROL AddCircle]**&#x200B;을(를) 선택하십시오.

   <!--add screenshot of permission in the admin console-->

1. 권한을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

자세한 내용은 [액세스 제어](/help/technotes/access-control.md#user-level-access)의 [사용자 수준 액세스](/help/technotes/access-control.md#access-control)를 참조하십시오.

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


