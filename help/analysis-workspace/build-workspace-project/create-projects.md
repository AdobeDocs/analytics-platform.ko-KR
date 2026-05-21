---
description: Analysis Workspace에서 기본 프로젝트를 만드는 방법을 알아봅니다.
title: 프로젝트 만들기
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
TQID: https://experienceleague.adobe.com/DWTWJ2Bd9iEPO2awiiOLcUzUGPc-clZul3dNFcyWvxk
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: fa6ac035-8403-478b-9ce1-3fe29d211fca
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 459
ht-degree: 96%

---

# 프로젝트 만들기 {#create-projects}


Analysis Workspace의 [프로젝트](/help/analysis-workspace/build-workspace-project/freeform-overview.md)를 사용하여 비즈니스에 중요한 분석을 만들고 볼 수 있습니다.  이러한 분석은 조직 내부 또는 외부의 관련자와 공유할 수 있습니다.

1. Customer Journey Analytics에서 **[!UICONTROL Workspace]**&#x200B;를 선택합니다.

1. 왼쪽 패널에서 **[!UICONTROL 프로젝트]**&#x200B;를 선택한 다음 **[!UICONTROL 프로젝트 만들기]**&#x200B;를 선택합니다.

1. **빈 Workspace 프로젝트**&#x200B;를 선택하여 브라우저를 통해 Workspace 프로젝트를 만듭니다.

   모바일 앱을 통해 다른 관련자와 공유할 수 있는 모바일 스코어카드 프로젝트를 만드는 방법에 대한 자세한 내용은 [빈 모바일 스코어카드](/help/mobile-app/curator.md)를 참조하십시오. 가이드 분석 프로젝트를 만들 수 있는 다양한 옵션에 대한 자세한 내용은 [가이드 분석](/help/guided-analysis/overview.md)을 참조하십시오.

1. [!UICONTROL **만들기**]&#x200B;를 선택합니다.


빈 Workspace 프로젝트를 만들고 나면 [Analysis Workspace](/help/analysis-workspace/home.md) 사용자 인터페이스를 잘 알고 있는지 확인합니다. 확인되면 프로젝트를 빌드할 수 있습니다. 이렇게 하려면 다음 작업을 수행하십시오.

![예제 프로젝트](assets/example-project.png)

* [패널](/help/analysis-workspace/c-panels/panels.md)를 프로젝트에 추가합니다. (예: **[!DNL Example Panel]** ➊).

* [시각화](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)를 패널에 추가합니다. 예:
   * **[!DNL Line Graph]** [라인](/help/analysis-workspace/visualizations/line.md) 시각화 ➋
   * **[!DNL Countries]** [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) 시각화➌
* [구성 요소](/help/components/overview.md)를 시각화에 추가합니다. 예:
   * **[!DNL Store Country]** [차원](/help/components/dimensions/overview.md) ➍
   * **[!DNL People]** [지표](/help/components/apply-create-metrics.md) ➎
   * **[!DNL Avg Order Value]** [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [세그먼트](/help/components/segments/seg-overview.md) ➐
   * **[!DNL Last Month]** [날짜 범위](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [주석](/help/components/annotations/overview.md) ➒


## 프로젝트 정보 및 설정 {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="반복 인스턴스 계산"
>abstract="보고서에서 반복 인스턴스가 계산되는지 여부를 지정합니다.<br/><br/>참고: 이 설정은 플로우 또는 폴아웃 시각화에 적용되지 않습니다."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="반복 인스턴스 계산"
>abstract="보고서에서 반복 인스턴스가 계산되는지 여부를 지정합니다.<br/>참고: 이 설정은 플로우 또는 폴아웃 시각화에 적용되지 않습니다."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="댓글 허용"
>abstract="이 기능을 활성화하면 Analysis Workspace의 프로젝트 오른쪽 레일에 댓글 영역이 제공됩니다."


프로젝트 설정에서는 현재 활성 상태인 프로젝트에 대한 프로젝트 수준의 정보를 제공합니다.

![프로젝트 정보 및 설정 창](./assets/projectinfo.png)

설정에는 다음이 포함됩니다.

| 설정 | 설명 |
|---|---|
| 프로젝트 이름 | 프로젝트에 지정된 이름입니다. 이름을 더블 클릭하여 편집할 수 있습니다. |
| 소유자 | 프로젝트 소유자 이름 |
| 마지막 수정 | 프로젝트의 마지막 수정 날짜. |
| 태그 | 더 쉬운 분류를 위해 프로젝트에 적용된 모든 태그를 나열합니다. |
| 설명 | 설명은 프로젝트의 목적을 명확하게 하는 데 유용합니다. 설명을 더블 클릭하여 편집할 수 있습니다. |
| 반복 인스턴스 계산 | 보고서에서 반복 인스턴스가 계산되는지 여부를 지정합니다. 참고: 이 설정은 흐름 또는 폴아웃 시각화에 적용되지 않습니다. |
| 주석 표시 | 이 프로젝트의 주석을 표시할지 여부를 지정합니다. |
| [프로젝트 색상 팔레트](/help/analysis-workspace/build-workspace-project/color-palettes.md) | 색맹 사용자에 최적화된 비맞춤형 팔레트에서 선택하거나 맞춤형 팔레트를 지정하여 Workspace에서 사용되는 카테고리별 색상 팔레트를 변경할 수 있습니다. 이 기능은 대부분의 시각화를 포함하여 작업 영역의 많은 사항에 영향을 줍니다. |
| [보기 밀도](/help/analysis-workspace/build-workspace-project/view-density.md) | 자유 형식 테이블 및 코호트 테이블에서 왼쪽 패널의 수직 안쪽 여백을 줄여 화면에서 더 많은 데이터를 볼 수 있습니다. |
| 댓글 허용 | 이 옵션이 활성화되면 Analysis Workspace의 프로젝트 오른쪽 레일에 댓글 영역이 제공됩니다. 자세한 내용은 [프로젝트에서 댓글 추가 및 관리](/help/analysis-workspace/build-workspace-project/comment-projects.md)를 참조하십시오. |



