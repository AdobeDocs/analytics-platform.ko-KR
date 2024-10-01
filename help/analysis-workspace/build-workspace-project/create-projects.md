---
description: Analysis Workspace에서 기본 프로젝트를 만드는 방법 알아보기
title: 프로젝트 만들기
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 40%

---

# 프로젝트 만들기 {#create-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_countrepeatinstances"
>title="반복 인스턴스 계산"
>abstract="보고서에서 반복 인스턴스가 계산되는지 여부를 지정합니다.<br/><br/>참고: 이 설정은 플로우 또는 폴아웃 시각화에 적용되지 않습니다."

<!-- markdownlint-enable MD034 -->


Analysis Workspace의 [프로젝트](/help/analysis-workspace/build-workspace-project/freeform-overview.md)을(를) 사용하면 비즈니스 크리티컬 분석을 만들고 볼 수 있습니다.  이러한 분석은 조직 내부 또는 외부의 이해 당사자와 공유할 수 있습니다.

1. Customer Journey Analytics에서 **[!UICONTROL Workspace]**&#x200B;을(를) 선택합니다.

1. 왼쪽 패널에서 **[!UICONTROL 프로젝트]**&#x200B;를 선택한 다음 **[!UICONTROL 프로젝트 만들기]**&#x200B;를 선택합니다.

1. 브라우저를 사용하여 Workspace 프로젝트를 만들려면 **빈 Workspace 프로젝트**&#x200B;를 선택하십시오.

   모바일 앱을 사용하여 다른 관련자와 공유할 수 있는 모바일 스코어카드 프로젝트를 만드는 방법에 대한 자세한 내용은 [빈 모바일 스코어카드](/help/mobile-app/curator.md)를 참조하십시오. 안내식 분석 프로젝트를 만드는 데 사용할 수 있는 다양한 옵션에 대한 자세한 내용은 [안내식 분석](/help/guided-analysis/overview.md)을 참조하세요.

1. [!UICONTROL **만들기**]&#x200B;를 선택합니다.


빈 Workspace 프로젝트를 만들었으므로 이제 [Analysis Workspace](/help/analysis-workspace/home.md) 사용자 인터페이스를 잘 알고 있는지 확인하십시오. 프로젝트를 빌드할 수 있습니다. 방법은 다음과 같습니다.

![예제 프로젝트](assets/example-project.png)

* 프로젝트에 [패널](/help/analysis-workspace/c-panels/panels.md)을(를) 추가합니다. 예: {0➊}.**[!DNL Example Panel]**

* 패널에 [시각화](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)를 추가합니다. 예:
   * **[!DNL Line Graph]** [줄](/help/analysis-workspace/visualizations/line.md) ➋ 시각화
   * **[!DNL Countries]** [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ➌ 시각화
* [구성 요소](/help/components/overview.md)를 시각화에 추가하십시오. 예:
   * **[!DNL Store Country]** [차원{2➍}](/help/components/dimensions/overview.md)
   * **[!DNL People]** [지표{2➎}](/help/components/apply-create-metrics.md)
   * **[!DNL Avg Order Value]** [계산된 지표{2➏}](/help/components/calc-metrics/calc-metr-overview.md)
   * **[!DNL Mobile App Sessions]** [필터{2➐}](/help/components/filters/filters-overview.md)
   * **[!DNL Last Month]** [날짜 범위{2➑}](/help/components/date-ranges/overview.md)
   * **[!DNL Example]** [주석{2➒}](/help/components/annotations/overview.md)


## 프로젝트 정보 및 설정 {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_repeatinstances"
>title="반복 인스턴스 계산"
>abstract="보고서에서 반복 인스턴스가 계산되는지 여부를 지정합니다.<br/>참고: 이 설정은 플로우 또는 폴아웃 시각화에 적용되지 않습니다."

<!-- markdownlint-enable MD034 -->


프로젝트 설정은 현재 활성화된 프로젝트에 대한 프로젝트 수준 정보를 제공합니다.

![프로젝트 정보 및 설정 창](./assets/projectinfo.png)

설정에는 다음이 포함됩니다.

| 설정 | 설명 |
|---|---|
| 프로젝트 이름 | 프로젝트에 지정된 이름. 이름을 더블 클릭하여 편집할 수 있습니다. |
| 소유자 | 프로젝트 소유자 이름 |
| 마지막 수정 | 프로젝트의 마지막 수정 날짜. |
| 태그 | 더 쉬운 분류를 위해 프로젝트에 적용된 모든 태그를 나열합니다. |
| 설명 | 설명은 프로젝트의 목적을 명확히 하는 데 유용합니다. 설명을 더블 클릭하여 편집할 수 있습니다. |
| 반복 인스턴스 계산 | 보고서에서 반복 인스턴스가 계산되는지 여부를 지정합니다. 참고: 이 설정은 플로우 또는 폴아웃 시각화에 적용되지 않습니다. |
| 주석 표시 | 이 프로젝트에 대한 주석을 표시할지 여부를 지정합니다. |
| [프로젝트 색상 팔레트](/help/analysis-workspace/build-workspace-project/color-palettes.md) | 색맹 사용자에 최적화된 비맞춤형 팔레트에서 선택하거나 맞춤형 팔레트를 지정하여 Workspace에서 사용되는 범주별 색상 팔레트를 변경할 수 있습니다. 이 기능은 대부분의 시각화를 포함하여 작업 영역의 많은 사항에 영향을 줍니다. |
| [보기 밀도](/help/analysis-workspace/build-workspace-project/view-density.md) | 자유 형식 테이블 및 집단 테이블에서 왼쪽 패널의 수직 안쪽 여백을 줄여 화면에서 더 많은 데이터를 볼 수 있습니다. |



