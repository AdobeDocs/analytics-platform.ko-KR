---
title: Analysis Workspace에서의 사용자 환경 설정 방법
description: 사용자를 위한 일반 프로젝트 환경을 설정할 수 있습니다.
feature: Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
role: User
source-git-commit: 827ab36b27eee1b0af46ff1c653f13b1accfe105
workflow-type: tm+mt
source-wordcount: '3632'
ht-degree: 100%

---

# 사용자 환경 설정

만든 모든 새 프로젝트 또는 패널에 대해 Analysis Workspace 및 관련 구성 요소의 사용자 설정이나 환경 설정을 관리할 수 있습니다. 기존 프로젝트 및 패널은 영향을 받지 않습니다.

## 환경 설정 업데이트

다음과 같은 방식으로 환경 설정을 업데이트할 수 있습니다.

- Workspace 메인 인터페이스에서 ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL 환경 설정 편집]**&#x200B;을 선택합니다.
- Workspace 프로젝트에서 작업할 때 메뉴에서 **[!UICONTROL 프로젝트]** > **[!UICONTROL 사용자 환경 설정]**&#x200B;을 선택합니다.
- 메인 Customer Journey Analytics 상단 막대에서 **[!UICONTROL 구성 요소]** > **[!UICONTROL 환경 설정]**(제품 관리자만 사용 가능)을 선택합니다.

## 환경 설정 구성

다음 환경 설정을 구성할 수 있습니다.

### 일반 환경 설정

일반 환경 설정은 브라우저의 Customer Journey Analytics 환경에 적용됩니다. 이러한 환경 설정에 액세스하는 방법에 대한 자세한 내용은 [환경 설정 업데이트](#update-preferences)를 참조하십시오.

| 환경 설정 | 옵션 |
| --- | --- |
| **[!UICONTROL 랜딩 페이지]** | Customer Journey Analytics에 액세스할 때 기본 페이지로 표시되는 페이지를 선택합니다. <ul><li>프로젝트 목록 (기본값)</li><li>빈 프로젝트</li><li>빈 트렌드 가이드 분석</li><li>목록에서 선택한 특정 프로젝트</li></ul> |
| **[!UICONTROL 팁]** | Analysis Workspace 오른쪽 아래 영역의 파란색 상자에 팁을 표시합니다. <p>이 옵션은 기본적으로 활성화되어 있습니다.</p> |
| **[!UICONTROL 왼쪽 패널 그룹에 표시되는 구성 요소]** | 왼쪽 패널의 구성 요소 메뉴에 표시할 각 구성 요소 그룹의 수를 선택합니다. <p>구성 요소 그룹에서 0을 선택하는 경우 왼쪽 레일에서 구성 요소 그룹에 더 이상 액세스할 수 없습니다.</p><p>기본적으로 다음 각 구성 요소 그룹에 대해 5개의 구성 요소가 표시됩니다.</p> <ul><li>차원</li><li>지표</li><li>필터</li><li>날짜 범위</li></ul> <p>Analysis Workspace의 구성 요소에 대한 자세한 내용은 [구성 요소 개요](/help/components/overview.md)를 참조하십시오.</p> |

### IMS 조직 환경 설정 {#ims-organization-preferences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="Workspace 사용자와의 공유만 허용"
>abstract="활성화되면 Analysis Workspace 프로젝트를 공유할 때 사용자가 **[!UICONTROL 모두와 공유]** 옵션을 더 이상 사용할 수 없습니다. 이전에 이 공유 옵션을 통해 프로젝트 액세스 권한을 부여받은 사람들이 더 이상 프로젝트에 액세스할 수 없습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="Experience Cloud 인증 필요"
>abstract="활성화되면 Analysis Workspace의 모두와 공유 옵션으로 프로젝트 액세스 권한을 부여받은 사용자는 자신의 Experience Cloud 자격 증명을 사용하여 인증해야 합니다."

<!-- markdownlint-enable MD034 -->


조직 내의 모든 사용자 및 프로젝트에 적용되는 회사 환경 설정을 업데이트할 수 있습니다. 이러한 환경 설정에 액세스하는 방법에 대한 자세한 내용은 [환경 설정 업데이트](#update-preferences)를 참조하십시오.

| 섹션 | 환경 설정 | 옵션 |
| --- | --- | --- |
| **프로젝트 공유** | | |
| | Workspace 사용자와의 공유만 허용 | 이 옵션이 활성화되면 **[!UICONTROL 공유]** 메뉴에서 조직의 사용자에게 **[!UICONTROL 모두와 공유]** 옵션이 표시되지 않습니다. 즉, [프로젝트 공유](/help/analysis-workspace/curate-share/share-projects.md)의 [모두와 프로젝트 공유(로그인 필요 없음)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link)에 설명된 대로 사용자는 조직에서 Analysis Workspace 계정이 없는 사람과 프로젝트를 공유할 수 없습니다.<br/>이 옵션은 Healthcare Shield 라이선스가 있는 고객을 제외하고 모든 조직에서 기본적으로 비활성화되어 있습니다(즉, 사용자가 조직 외부의 사람들과 프로젝트를 공유할 수 있음). <p>이 옵션을 활성화하거나 비활성화할 때 다음 사항을 고려하십시오.<ul><li>이 옵션을 활성화하면 이전에 [!UICONTROL 모두와 공유] 공유 옵션을 통해 프로젝트 액세스 권한을 부여받은 사람들이 더 이상 프로젝트에 액세스할 수 없습니다.</li><li>이 옵션을 활성화(Workspace 사용자와만 공유 허용)한 다음 나중에 비활성화(모두와 공유 허용)하더라도 이전에 [!UICONTROL 모두와 공유] 공유 옵션을 통해 프로젝트 액세스 권한을 부여받았던 사용자의 프로젝트 액세스 권한이 자동으로 회복되지 않습니다. 이 경우 [프로젝트 공유](/help/analysis-workspace/curate-share/share-projects.md)의 [모두와 프로젝트 공유(로그인 필요 없음)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link)에 설명된 대로 프로젝트를 공유한 사용자가 모두와 프로젝트를 공유&#x200B;**([!UICONTROL 공유]** > **[!UICONTROL 모두와 공유]**)할 때 사용할 수 있는 [!UICONTROL **링크 활성화됨**] 옵션을 활성화해야 합니다.</li><li>**Healthcare Shield 라이선스가 있는 고객:** 이 옵션이 기본적으로 활성화되어 있으며 비활성화할 수 없습니다. 사용자가 [!UICONTROL 모두와 공유] 공유 옵션을 사용할 수 있도록 이 옵션을 비활성화하려면 먼저 [!UICONTROL 모든 사람과 프로젝트 링크 공유] 권한([!UICONTROL 보고 도구] 아래에 위치)을 Adobe Admin Console에 추가해야 합니다. 권한을 추가한 후 이 옵션을 비활성화한 다음 그 결과로 표시되는 법적 고지 사항을 수락할 수 있습니다. 관리 콘솔에서 권한을 추가하는 방법에 대한 자세한 내용은 [Admin Console에서 제품 권한 관리](https://helpx.adobe.com/kr/enterprise/using/manage-permissions-and-roles.html)를 참조하십시오.</li></ul> |
| | Experience Cloud 인증 필요 | 활성화되면 Analysis Workspace의 모두와 공유 옵션으로 프로젝트 액세스 권한을 부여받은 사용자는 자신의 Experience Cloud 자격 증명을 사용하여 인증해야 합니다.<p>이 옵션이 활성화되면 사용자가 [!UICONTROL 모두와 공유] 공유 옵션을 사용하여 프로젝트를 공유할 때마다 공유 대화 상자에서 [!UICONTROL Experience Cloud 인증 필요] 옵션이 활성화되며, 프로젝트를 공유하는 사용자가 이를 비활성화할 수 없습니다. 사용자가 모두와 프로젝트를 공유할 수 있는 방법에 대한 내용은 [프로젝트 공유](/help/analysis-workspace/curate-share/share-projects.md)의 [모두와 프로젝트 공유(로그인 필요 없음)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link)을 참조하십시오. <p> <p>이 옵션을 활성화할 때 다음 사항을 고려하십시오. <ul><li>이 옵션을 활성화하면 이전에 [!UICONTROL 모두와 공유] 공유 옵션으로 공유되었고 [!UICONTROL Experience Cloud 인증 필요] 옵션이 활성화되지 않은 모든 프로젝트가 비활성화됩니다.<p>이 옵션을 활성화(Experience Cloud 인증 요구)한 다음 나중에 비활성화(링크가 있는 모두가 프로젝트에 액세스할 수 있도록 허용)하더라도 이전에 [!UICONTROL 모두와 공유] 공유 옵션으로 프로젝트 액세스 권한을 부여받은 사용자의 프로젝트 액세스 권한이 자동으로 회복되지 않습니다. 이 경우 [프로젝트 공유](/help/analysis-workspace/curate-share/share-projects.md)의 [모두와 프로젝트 공유(로그인 필요 없음)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link)에 설명된 대로 프로젝트를 공유한 사용자가 모두와 프로젝트를 공유할 때 사용할 수 있는 [!UICONTROL 링크 활성화됨] *옵션을 활성화해야 합니다&#x200B;**([!UICONTROL 공유]** > **[!UICONTROL 모두와 공유]** > **[!UICONTROL 링크 활성화됨]**).</li><li>이 옵션은 조직에 SSO가 구현된 경우에만 사용할 수 있습니다. 시스템 관리자가 조직에 대해 SSO를 활성화하는 방법에 대한 자세한 내용은 [ID 및 SSO(Single Sign-On) 설정](https://helpx.adobe.com/kr/enterprise/using/set-up-identity.html)을 참조하십시오.</p><p>조직에 SSO가 구성된 경우 콘솔에 자동 계정 만들기가 구현되어 있는지 확인합니다. 일반적으로 시스템 관리자는 [자동 계정 만들기 활성화](https://helpx.adobe.com/kr/enterprise/using/automatic-account-creation.html)에 설명된 대로 이를 설정합니다.</li><li>조직에서 Healthcare Shield 라이선스를 취득한 경우 이 옵션은 기본적으로 활성화되며 비활성화할 수 없습니다.</li></ul> |

{style="table-layout:auto"}

### 프로젝트 및 분석 환경 설정 {#project-and-analysis-preferences}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="카테고리형 팔레트"
>abstract="Analysis Workspace 및 가이드 분석의 많은 시각화에 적용됩니다. 각 색상은 고유한 카테고리형 값을 나타냅니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="분기형 팔레트"
>abstract="Analysis Workspace 및 사용자 증가 가이드 분석의 코호트 테이블에 적용됩니다. 이 팔레트는 양 극단과 중간의 기준선을 사용하여 숫자로 표시합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="순차적 팔레트"
>abstract="빈도 트렌드(누적 막대) 가이드 분석에 적용됩니다. 이 팔레트는 밝은 색상에서 어두운 색상까지 숫자로 표시합니다."

<!-- markdownlint-enable MD034 -->


모든 새로운 Analysis Workspace 프로젝트, 새로운 Analysis Workspace 패널 및 새로운 가이드 분석에 대해 이러한 환경 설정을 사용자 정의할 수 있습니다. 이러한 환경 설정에 액세스하는 방법에 대한 자세한 내용은 [환경 설정 업데이트](#update-preferences)를 참조하십시오.

[프로젝트 개요](/help/analysis-workspace/build-workspace-project/freeform-overview.md)의 설명에 따라 Analysis Workspace의 개별 프로젝트에 맞게 동일한 환경 설정 중 일부를 사용자 정의할 수도 있습니다.

| 섹션 | 환경 설정 | 옵션 |
| --- | --- | --- |
| **표시** | | |
|  | [보기 밀도](/help/analysis-workspace/build-workspace-project/view-density.md) | 자유 형식 테이블 및 코호트 테이블에서 왼쪽 패널 수직 안쪽 여백을 줄여 화면에 표시해야 할 콘텐츠 양을 선택합니다. <ul><li>콤팩트</li><li>편안함</li><li>확장됨 (기본값)</li></ul> |
| | [색상 팔레트](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Analysis Workspace 및 가이드 분석에서 사용되는 시각화 색상 팔레트를 선택합니다. <ul><li> 카테고리형 팔레트: Analysis Workspace 및 가이드 분석의 여러 시각화에 적용됩니다. 각 색상은 고유한 카테고리 값을 나타냅니다. Adobe에서 제공하는 옵션 중에서 선택하거나 쉼표로 구분된 16진수 값으로 정의된 맞춤형 팔레트를 입력합니다.</li><li> 다양한 팔레트: Analysis Workspace 및 사용자 성장 가이드 분석의 코호트 테이블에 적용됩니다. 이 팔레트는 두 개의 극단과 중간에 기준선이 있는 숫자 의미를 보유합니다.<li> 순차적 팔레트: 빈도 트렌드(스택 막대) 가이드 분석에 적용됩니다. 이 팔레트는 밝음부터 어두움까지의 숫자 의미를 보유합니다.</li></ul> |
| **데이터** | | |
|  | [데이터 보기](/help/analysis-workspace/c-panels/panels.md#data-view) | 테이블 및 시각화가 데이터를 도출하는 데이터를 선택합니다. <ul><li>가장 최근 (기본값)</li><li>목록에서 선택한 특정 데이터 보기</li></ul> |
|  | [캘린더](/help/analysis-workspace/c-panels/panels.md#calendar) | 다음 목록에서 선택: <ul><li>Adobe 제공 범위 (기본값은 이번 달)</li><li>[!UICONTROL 기본적으로 패널 캘린더를 기준으로 날짜 범위 구성 요소 만들기]를 활성화할 수 있습니다.</li></ul> |
|  | [패널 유형](/help/analysis-workspace/c-panels/panels.md#panel-types) | <ul><li>자유 형식 (기본값)</li><li>빈</li><li>빠른 인사이트</li></ul> |
|  | 인스턴스 계산 | [!UICONTROL 반복 인스턴스 계산]을 활성화하여 보고서에서 반복 인스턴스가 계산되는지 여부를 지정합니다. 예를 들어 활성화되면 동일한 페이지에 대한 여러 개의 연속 페이지 조회수가 여러 페이지 조회수로 처리됩니다. 비활성화되면 동일한 페이지에 대한 여러 개의 연속 페이지 조회수가 단일 페이지 조회수로 카운트됩니다. <p>**참고:** 이 설정은 특정 지표(예: 세션)에만 영향을 주고 흐름 또는 폴아웃 시각화에 적용되지 않습니다.</p> |
|  | 번호 형식 | <ul><li>1,000.00 (기본값)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | CSV 구분자 | <ul><li>쉼표 (기본값)</li><li>세미콜론</li><li>콜론</li><li>파이프</li><li>기간</li><li>공백</li><li>탭</li></ul> |
|  | 주석 표시 | 프로젝트에 주석을 표시할지 여부를 선택합니다. 주석에 대한 자세한 내용은 [주석 개요](/help/components/annotations/overview.md)를 참조하십시오. |


### 자유 형식 테이블 환경 설정 {#freeform-table-preferences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="예외 항목 표시"
>abstract="**[!UICONTROL 예외 항목 표시]**&#x200B;를 선택하면 시계열 자유 형식 테이블 시각화에 추가된 첫 번째 지표 열에서 예외 항목 탐지가 자동으로 실행됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="예측 표시"
>abstract="**[!UICONTROL 예측 표시]**&#x200B;를 선택하면 시계열 자유 형식 테이블 시각화에 추가된 첫 번째 지표 열이 자동으로 예측됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="기본 테이블 지표"
>abstract="자유 형식 테이블에 사용할 기본 지표를 선택하십시오. 선택한 데이터 보기에 선택한 기본 지표가 포함되어 있지 않으면 테이블은 자동으로 다른 기본 지표로 전환합니다."


<!-- markdownlint-enable MD034 -->



Analysis Workspace에서 만든 모든 새 프로젝트의 자유 형식 테이블 환경 설정을 사용자 정의할 수 있습니다. 이러한 환경 설정에 액세스하는 방법에 대한 자세한 내용은 [환경 설정 업데이트](#update-preferences)를 참조하십시오.

개별 프로젝트에 맞게 동일한 환경 설정 중 일부를 사용자 정의할 수도 있습니다.

사용 가능한 환경 설정에 대한 자세한 내용과 컨텍스트를 보려면 링크된 섹션 제목을 선택합니다.

| 섹션 | 환경 설정 | 옵션 |
| --- | --- | --- |
| **테이블** | | |
| | 테이블 유형 | <ul><li>자유 형식</li><li>테이블 빌더</li></ul> |
| | 기본 테이블 지표 | <ul><li>발생 횟수</li><li>고유 방문자 수</li><li>방문 횟수</li></ul> |
| | 기본 테이블 차원 | 분, 시간, 일, 주, 월, 분기 또는 연도 중에서 선택합니다. |
| | 날짜 정렬 | 이 옵션을 선택하여 각 열의 날짜가 같은 행에서 시작하도록 맞춥니다. |
| **[열](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | 머리글 텍스트 줄바꿈 | 자유 형식 테이블의 머리글 텍스트를 줄바꿈하여 머리글을 더 읽기 쉽게 하고 테이블을 더 공유하기 쉽게 할 수 있습니다. 이 기능은 .pdf 렌더링 및 긴 이름을 사용하는 지표에 유용합니다. 기본적으로 사용됩니다. |
| | 합계 표시 | 이 합계는 일반적으로 [!UICONTROL 총 합계]와 같거나 그 하위 집합입니다. [!UICONTROL 포함 내용 없음] 선택 사항을 포함하여 자유 형식 테이블 내에 적용된 테이블 필터를 반영합니다. |
| | 총계 표시 | 이 합계는 수집 된 모든 이벤트 수를 나타내며 ‘데이터 보기 합계’라고도 합니다. 필터가 패널 수준에서 또는 자유 형식 테이블 내에서 적용되면 이 합계는 필터 조건과 일치하는 모든 이벤트를 반영하도록 조정됩니다. [정적 행](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)이 있는 테이블 또는 분류에서는 총 합계가 지원되지 않습니다. |
| | 스파크라인 표시 | 차트 하단에 선 차트를 표시하거나 숨깁니다. 범례가 숨겨져 있으면 더 이상 시각적으로 선을 참조하지 않습니다. |
| | 숫자 | 셀에 지표에 대한 숫자 값을 표시할지 또는 숨길지를 결정합니다. 예를 들어 지표가 페이지 조회수이면 숫자 값은 행 항목에 대한 페이지 조회수입니다. |
| | 비율 | 셀에 지표에 대한 퍼센트 값을 표시할지 또는 숨길지를 결정합니다. 예를 들어 지표가 페이지 조회수이면 퍼센트 값은 행 항목에 대한 페이지 조회수를 해당 열에 대한 총 페이지 조회수로 나눈 수입니다.  참고: 정확하게 말하자면 100%보다 큰 백분율을 표시할 수 있습니다. 또한 열의 폭을 크게 늘릴 수 있도록 상한을 1,000%로 옮겼습니다. |
| | 예외 항목 표시 <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | 이 열의 값에 대해 예외 항목 탐지가 실행되는지 여부를 결정합니다. |
| | 예측 표시 | 만든 시계열 자유 형식 테이블의 첫 번째 지표 열에 대한 예측 값이 자동으로 표시되는지 여부를 결정합니다. |
| | 0을 값없음으로 해석 | 값이 0인 셀에 대해, 0을 표시할지 아니면 빈 셀을 표시할지를 결정합니다. 달의 각 날에 대한 데이터를 보고 일부 날은 아직 일어나지 않은 경우 유용합니다.  차후의 날짜에 대해 0을 표시하는 대신 빈 셀을 표시할 수 있습니다. 차트에 이 설정도 적용됩니다(즉, 이 설정을 선택한 경우 차트에 값이 0인 줄 또는 막대가 표시되지 않습니다). |
| | 배경 | 막대 그래프 및 조건부 서식을 포함하여, 셀에 모든 셀 서식을 표시할지 또는 숨길지를 결정합니다 <ul><li>막대 그래프</li> 열에 대한 합계와 상대적인 셀 값을 나타내는 수평 막대 그래프를 표시합니다. <li>조건부 서식</li>조건부 서식에 대한 자세한 내용은 [열 설정](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)의 “조건부 서식”을 참조하십시오.</ul> |
| | 셀 미리보기 | 각 셀이 현재 선택된 서식 선택 사항이 적용되면 어떻게 나타나는지 미리보기를 표시합니다. |
| **[행](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | 위치별 분류 | 분류를 항목 자체가 아닌 항목 위치로 유지하려면 이 옵션을 선택합니다. 분류에 대한 자세한 내용은 [차원 분류](/help/components/dimensions/t-breakdown-fa.md)를 참조하십시오. |
| | 백분율 계산 | <ul><li>열</li><li>행</li></ul> |
| | 열 합계 (정적 행만 해당) | <ul><li>행 합계 표시: 개별 라인 항목의 합계를 표시합니다. </li><li>총계 표시: 중복 제거된 행의 합계를 표시합니다.</li></ul> |

### 시각화 환경 설정 {#visalization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultflowcontainer"
>title="기본 컨테이너"
>abstract="[!UICONTROL 흐름] 시각화에 사용할 기본 컨테이너를 선택하십시오. 선택한 데이터 보기에 선택한 기본 컨테이너가 포함되어 있지 않으면 [!UICONTROL 흐름] 시각화는 자동으로 다른 기본 컨테이너로 전환합니다."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultfalloutcontainer"
>title="기본 컨테이너"
>abstract="[!UICONTROL 폴아웃] 시각화에 사용할 기본 컨테이너를 선택하십시오. 선택한 데이터 보기에 선택한 기본 컨테이너가 포함되어 있지 않으면 [!UICONTROL 폴아웃] 시각화는 자동으로 다른 기본 컨테이너로 전환합니다."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulthistogramcountingmethod"
>title="기본 계산 방법"
>abstract="[!UICONTROL 히스토그램] 시각화에 사용할 기본 계산 방법을 선택하십시오. 선택한 데이터 보기에 선택한 기본 계산 방법이 포함되어 있지 않으면 [!UICONTROL 히스토그램] 시각화는 자동으로 다른 기본 계산 방법으로 전환합니다."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultjourneycanvascontainer"
>title="기본 컨테이너"
>abstract="[!UICONTROL 여정 캔버스] 시각화에 사용할 기본 컨테이너를 선택하십시오. 선택한 데이터 보기에 선택한 기본 컨테이너가 포함되어 있지 않으면 [!UICONTROL 여정 캔버스] 시각화는 자동으로 다른 기본 컨테이너로 전환합니다."


Analysis Workspace에서 만든 모든 새 프로젝트의 시각화 환경 설정을 업데이트할 수 있습니다. 이러한 환경 설정에 액세스하는 방법에 대한 자세한 내용은 [환경 설정 업데이트](#update-preferences)를 참조하십시오.

개별 시각화에 맞게 동일한 환경 설정 중 일부를 사용자 정의할 수도 있습니다.

사용 가능한 환경 설정에 대한 자세한 내용과 컨텍스트를 보려면 링크된 섹션 제목을 선택합니다.

| 섹션 | 환경 설정 | 옵션 |
| --- | --- | --- |
| **일반 기본값** | | |
| | 백분율 | 모든 시각화 값을 백분율로 표시합니다. |
| | 범례 표시 | 모든 시각화에 대한 자세한 범례 텍스트를 숨길 수 있습니다. |
| | 최대 항목 수 제한 | 모든 시각화에 대한 X축의 항목 수를 줄입니다. 대규모 데이터 세트가 있는 경우 유용할 수 있습니다. |
| | 이중 축 표시 (해당되는 경우) | 지표가 두 개일 경우에만 적용됩니다. 왼쪽(한 지표에 대해)과 오른쪽(다른 지표에 대해)에 y축을 놓을 수 있습니다. 그려진 지표의 크기가 매우 다른 경우에 유용합니다. |
| | 표준화 (해당되는 경우) | 지표를 등분 비례에 강제 적용합니다. 그려진 지표의 크기가 매우 다른 경우에 유용합니다. |
| | Y축을 0에 고정 | 차트에 표시된 모든 값이 0보다 매우 큰 경우 차트 기본값에 따라 y축의 하단이 0이 아닌 값으로 지정됩니다. 이 상자를 선택하면 y축이 0이 됩니다(그리고 차트가 다시 그려짐). |
| | 예외 항목을 고정하여 Y축의 크기 조절 | 예외 항목 값을 사용하여 Y축의 크기를 조절합니다. |
| **[라인](/help/analysis-workspace/visualizations/line.md)** | | |
| | 백분율 | 라인 시각화 값을 백분율로 표시합니다. |
| | 범례 표시 | 라인 시각화에 대한 자세한 범례 텍스트를 숨길 수 있습니다. |
| | 최대 항목 수 제한 | 라인 시각화에서 X축의 항목 수를 줄입니다. 대규모 데이터 세트가 있는 경우 유용할 수 있습니다. |
| | 이중 축 표시 (해당되는 경우) | 지표가 두 개일 경우에만 적용됩니다. 왼쪽(한 지표에 대해)과 오른쪽(다른 지표에 대해)에 y축을 놓을 수 있습니다. 그려진 지표의 크기가 매우 다른 경우에 유용합니다. |
| | 표준화 (해당되는 경우) | 지표를 등분 비례에 강제 적용합니다. 그려진 지표의 크기가 매우 다른 경우에 유용합니다. |
| | X축 표시 | 선 차트에 X축을 표시합니다. |
| | Y축 표시 | 선 차트에 Y축을 표시합니다. |
| | Y축 고정 | 차트에 표시된 모든 값이 0보다 매우 큰 경우 차트 기본값에 따라 y축의 하단이 0이 아닌 값으로 지정됩니다. 이 상자를 선택하면 y축이 0이 됩니다(그리고 차트가 다시 그려짐). |
| | 예외 항목으로 Y축의 크기 조절 | 차트에 여러 개의 지표가 있을 경우에는 사용자는 마우스를 각 예외 항목의 위에 놓아 해당 지표에 대한 신뢰 대역을 확인해야 합니다. 예외 항목 탐지 신뢰 구간은 시각화를 읽기 쉽게 만들기 위해 Y축 크기를 자동으로 조절하지 않습니다. 이 옵션을 통해 신뢰 구간에서 시각화 크기를 조절할 수 있습니다. <p>자세한 내용은 [Analysis Workspace에서 예외 항목 보기](/help/analysis-workspace/c-anomaly-detection/view-anomalies.md)를 참조하십시오.</p> |
| | 예측을 Y축으로 확장하도록 허용 | 과거 값의 상한 및 하한을 벗어나는 예측 값이 있는 경우 y축은 이러한 예측 값에 맞게 자동으로 조정되지 않습니다. 이 옵션을 켜면 예측 값에 대한 y축의 크기가 적절하게 조정됩니다. |
| | 최소 표시 | 최소값 레이블을 오버레이하여 지표의 최저점을 빠르게 강조 표시합니다. 참고: 최소값은 차원 내의 전체 값 집합이 아니라 시각화에 표시되는 데이터 포인트에서 파생됩니다. |
| | 최대 표시 | 최대값 레이블을 오버레이하여 지표의 최고점을 빠르게 강조 표시합니다. 참고: 최대값은 차원 내의 전체 값 집합이 아니라 시각화에 표시되는 데이터 포인트에서 파생됩니다. |
| | 트렌드 라인 표시 | 라인 시리즈에 회귀 또는 이동 평균 추세선을 표시합니다. 트렌드 라인은 데이터의 명확한 패턴을 표현하는 데 도움이 됩니다. |
| **[코호트](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | 세부 기간 | 트렌드 시각화의 경우 시간 단위(일, 주, 월, 분기 또는 연도)를 변경할 수 있습니다. 이 변경 사항은 데이터 소스 테이블에도 적용됩니다. |
| | 백분율만 표시 | 숫자 값을 제거하고 백분율만 표시합니다. |
| | 백분율 반올림 | 백분율 값을 소수 값으로 표시하지 않고 가장 가까운 정수로 반올림합니다. |
| | 평균 백분율 행 표시 | 테이블의 맨 위에 새 행을 삽입한 다음 각 열 내의 값에 대한 평균을 추가합니다. |
| **[콤보 차트](/help/analysis-workspace/visualizations/combo-charts.md)** | | |
| | X축 표시 | 콤보 차트에 X축을 표시합니다. |
| | Y축 표시 | 콤보 차트에 Y축을 표시합니다. |
| | 선에 바벨 표시 | 콤보 차트의 라인에 바벨을 표시합니다. |
| **[주요 지표 요약](/help/analysis-workspace/visualizations/key-metric.md)** | | |
| | 요약 표시 유형 | <ul><li>백분율 변경 강조</li><li>숫자 값 강조</li></ul> |
| | 스파크라인 표시 | 차트 하단에 선 차트를 표시하거나 숨기는 방법. 범례가 숨겨져 있으면 더 이상 시각적으로 선을 참조하지 않습니다. |
| | 스파크라인에서 최대 및 최소 표시 | 기본 및 비교 선 차트에서 최소값 및 최대값 표시 또는 숨기기. |
| | 비교 보기 | 비교 데이터 표시. 숨겨진 경우 보기에서 비교 선 차트와 요약 변경 오브젝트가 모두 표시되지 않습니다. |
| | 숫자 값 옵션 | [!UICONTROL **주요 지표 요약**] 섹션에서 <ul><li>백분율 변경 표시</li><li>원시 차이 표시</li>기본 날짜 범위와 보조 날짜 범위의 총 지표 값 간의 원시 차이</ul> |
| **[폴아웃](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | 컨테이너 | **[!UICONTROL 세션]**&#x200B;과 **[!UICONTROL 개인]** 간을 전환하여 개인 경로를 분석할 수 있도록 합니다. 기본값은 **[!UICONTROL 개인]**&#x200B;입니다. 이 설정은 세션들에 대해 사용자 수준에서 사용자 참여를 이해하거나 분석을 단일 세션으로 제한하는 데 도움이 됩니다. <p>다음 옵션을 사용할 수 있습니다.</p> <ul><li>세션</li><li>개인</li></ul> |
| **[흐름](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | 컨테이너 | [!UICONTROL **흐름**] 섹션에서 <ul><li>세션</li><li>개인</li></ul> |
| | 줄 바꿈 레이블 | 대개 흐름 요소의 레이블은 화면 공간을 절약하기 위해 잘리지만 이 상자를 선택하여 전체 레이블을 표시할 수 있습니다. 기본값 = 선택 해제. |
| | 반복 인스턴스 포함 | 흐름 시각화는 차원의 인스턴스를 기반으로 합니다. 이 설정은 반복된 인스턴스(예: 페이지 다시 로드)를 포함하거나 제외하는 옵션을 제공합니다. 하지만 listVars, listProp, s.product, 머천다이징 eVar 등과 같이 여러 값을 갖는 차원을 포함하는 흐름 시각화에서는 반복을 제거할 수 없습니다. 기본값 = 선택 해제. |
| | 툴팁 표시 | 흐름 시각화에서 마우스로 개별 노드를 가리킬 때 노드 데이터를 포함하는 도구 설명이 표시되는지 여부를 결정합니다. |
| | 열 수 | 흐름 다이어그램에 사용할 열 수를 결정합니다. |
| | 열당 항목 확장됨 | 각 열에 원하는 항목 수입니다. |
| **스택형 차트** | | |
| | 100% 누적 | 스택 영역, 막대 스택 또는 가로 막대형 스택 시각화에 대한 이 설정은 차트를 “100% 스택”시각화로 전환합니다. <p>자세한 내용은 [막대 및 스택 막대](/help/analysis-workspace/visualizations/bar.md)를 참조하십시오.</p> |
| **[히스토그램](/help/analysis-workspace/visualizations/histogram.md)** | | |
| | 버킷 수 | 시각화에서 날짜 범위(버킷) 수를 선택합니다. 최대 버킷 수는 50개입니다. <p>자세한 내용은 [히스토그램](/help/analysis-workspace/visualizations/histogram.md)을 참조하십시오.</p> |
| | 계산 방법 | 다음 선택 사항 중 하나를 선택합니다. <ul><li>히트</li><li>세션</li><li>개인</li></ul> <p>예를 들어 페이지 조회수와 함께 사용될 때 사용자당 페이지 조회수, 방문 페이지 조회수 또는 이벤트당 페이지 조회수를 선택할 수 있습니다. 히트의 경우 “발생 횟수”는 자유형 테이블에서 Y축 지표로 사용됩니다.</p> |
| **[요약 변경](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | 값 | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>백분율 변경</li><li>원시 차이</li></ul> |
| | 백분율 | 요약 변경 시각화 값을 백분율로 표시합니다. |
| | 범례 표시 | 요약 변경 시각화에 대한 자세한 범례 텍스트를 숨길 수 있습니다. |
| **[요약 번호](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | 백분율 | 요약 번호 시각화 값을 백분율로 표시합니다. |
| | 범례 표시 | 요약 번호 시각화에 대한 자세한 범례 텍스트를 숨길 수 있습니다. |
| | 기준별 요약 값 | 최대, 최소, 평균, 중앙값 및 합계 중에서 선택합니다. |
| | 값 생략 | [!UICONTROL **요약 번호**] 섹션에서 |
| **[트리맵](/help/analysis-workspace/visualizations/treemap.md)** | | |
| | 백분율 | 트리맵 시각화 값을 백분율로 표시합니다. |
| | 최대 항목 수 제한 | 트리맵 시각화에서 X축의 항목 수를 줄입니다. 대규모 데이터 세트가 있는 경우 유용할 수 있습니다. |
| **[벤](/help/analysis-workspace/visualizations/venn.md)** | | |
| | 범례 표시 | 벤 시각화에 대한 자세한 범례 텍스트를 숨길 수 있습니다. |
| **[분산](/help/analysis-workspace/visualizations/scatterplot.md)** | | |
| | 백분율 | 분산 시각화 값을 백분율로 표시합니다. |
| | 범례 표시 | 분산 시각화에 대한 자세한 범례 텍스트를 숨길 수 있습니다. |
| | 최대 항목 수 제한 | 분산 시각화에서 X축의 항목 수를 줄입니다. 대규모 데이터 세트가 있는 경우 유용할 수 있습니다. |
| | Y축을 0에 고정 | 차트에 표시된 모든 값이 0보다 매우 큰 경우 차트 기본값에 따라 y축의 하단이 0이 아닌 값으로 지정됩니다. 이 상자를 선택하면 y축이 0이 됩니다(그리고 차트가 다시 그려짐). |

## 기본 환경 설정 복원

모든 사용자 환경 설정을 시스템 기본값으로 복원할 수 있습니다. 이는 회사 탭 아래의 관리자 환경 설정에 영향을 주지 않습니다.

이 작업은 실행 취소할 수 없습니다.

1. Customer Journey Analytics의 상단 메뉴에서 [!UICONTROL **구성 요소**] **>** [!UICONTROL **환경 설정**]&#x200B;을 선택합니다. 또는 Workspace 메뉴에서 **[!UICONTROL 프로젝트]** > **[!UICONTROL 사용자 설정]**&#x200B;을 선택합니다.

1. 오른쪽 상단에서 **[!UICONTROL 기본값 복원]**&#x200B;을 선택합니다.

1. **[!UICONTROL 시스템 기본 설정 복원]**&#x200B;에서 **[!UICONTROL 기본값 복원]**&#x200B;을 선택합니다.

## [!UICONTROL 어두운 테마]

Customer Journey Analytics 사용자 인터페이스에 어두운 배경을 사용하려는 경우 [!UICONTROL 어두운 테마]로 전환할 수 있습니다.

1. 오른쪽 상단에서 Experience Cloud 사용자 아이콘을 선택합니다.

   ![dark-theme](assets/dark-theme.png)

1. **[!UICONTROL 어두운 테마]**&#x200B;를 활성화합니다.

