---
title: 구성 요소 설정
description: 데이터 보기 구성 요소에 대한 핵심 설정 보기.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: f3bd60d6a371a16e606d9af60e3359d8128a3c9f
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 90%

---

# 구성 요소 설정 {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="구성 요소 설정"
>abstract="구성 요소와 관련된 이름, 설명 및 기타 설정을 조회하고 구성합니다. 보고에서 관리자가 아닌 사용자에게 이 구성 요소를 표시하지 않으려면 이 체크박스를 선택하십시오. 관리자는 Workspace 프로젝트에서 **[!UICONTROL 모든 구성 요소 표시]**&#x200B;를 선택하여 구성 요소에 액세스할 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="컨텍스트 레이블"
>abstract="컨텍스트 레이블을 제거하면 구성 요소가 필요한 특정 패널이나 보고서에 영향을 미칠 수 있습니다."

<!-- markdownlint-enable MD034 -->


다음 정보는 데이터 보기 구성 요소에서 사용하는 설정에 대해 설명합니다.

![Component settings described in this section](../assets/component-settings.png)

| 설정 | 설명/사용 사례 |
| --- | --- |
| [!UICONTROL 구성 요소 유형] | 필수. 구성 요소를 지표에서 차원으로 변경하거나 그 반대로 변경할 수 있습니다. 이 드롭다운 선택 사항을 변경하면 구성 요소는 각 포함된 구성 요소 영역으로 전환됩니다. |
| [!UICONTROL 구성 요소 이름] | 필수. Analysis Workspace에 표시되는 이름을 지정할 수 있습니다. 구성 요소의 이름을 변경하여 데이터 보기에 특정된 이름을 지정할 수 있습니다. |
| [!UICONTROL 설명] | 선택 사항이지만 권장됨. 다른 사용자에게 구성 요소에 대한 정보를 제공합니다. |
| [!UICONTROL 태그] | 선택 사항. Analysis Workspace UI에서 보다 쉽게 검색/필터링할 수 있도록 사용자 정의 태그 또는 즉시 사용 가능한 태그로 구성 요소에 태그를 지정할 수 있습니다. |
| [!UICONTROL 컨텍스트 레이블] | 선택 사항. 구성 요소에 적용할 수 있는 시스템 정의 레이블의 드롭다운 메뉴. <p>다음과 같은 상황에서 이들 레이블이 필요할 수 있습니다.</p> <ul><li>Analysis Workspace 프로젝트의 [실험 패널](/help/analysis-workspace/c-panels/experimentation.md)을 사용하여 실험 보고에 사용할 수 있는 구성 요소 집합을 정의합니다.<p>자세한 내용은 [Journey Optimizer와 통합](/help/integrations/ajo.md#data-view) 및 [Target 보고](/help/integrations/at.md)를 참조하십시오.</p></li><li>Analysis Workspace 프로젝트에서 맵 시각화에 사용할 수 있는 구성 요소 세트를 정의합니다.<p>자세한 내용은 [맵](/help/analysis-workspace/visualizations/map.md#add-context-labels-in-data-views)에서 [데이터 보기에 컨텍스트 레이블 추가](/help/analysis-workspace/visualizations/map.md)를 참조하십시오.</p><p>**참고:** 맵 시각화는 릴리스의 제한된 테스트 단계에 있으므로 사용자 환경에서 아직 사용하지 못할 수 있습니다.</p></li><li>Adobe에서 제공하는 템플릿을 사용하는 경우. 기본적으로 Adobe에서 제공하는 일부 템플릿은 데이터 보기에 없는 구성 요소를 포함하고 있으므로 작동하지 않습니다.<p>누락된 각 구성 요소에 대해 일치하는 컨텍스트 레이블을 데이터 보기에서 사용할 수 있습니다. 이미 데이터 보기에 있는 구성 요소에 일치하는 컨텍스트 레이블을 추가하거나, 데이터 보기에 새 구성 요소를 추가하고 여기에 컨텍스트 레이블을 추가해야 합니다.</p><p>자세한 내용은 [템플릿 만들기 및 관리](/help/analysis-workspace/templates/create-templates.md) 문서에서 [지정된 템플릿의 데이터 보기에 누락된 구성 요소 추가](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template)를 참조하십시오.</p> |
| [!UICONTROL 스키마 필드 이름] | 스키마 필드의 이름. |
| [!UICONTROL 데이터 세트 유형] | 필수. 구성 요소의 원본 데이터 세트 유형(이벤트, 조회 또는 프로필)을 표시하는 편집 불가능한 필드입니다. |
| [!UICONTROL 데이터 세트] | 구성 요소의 원본 데이터 세트를 표시하는 편집 불가능한 필드입니다. 이 필드에는 여러 개의 데이터 세트가 포함될 수 있습니다. |
| [!UICONTROL 스키마 유형] | 구성 요소의 데이터 유형을 표시하는 편집 불가능한 필드입니다. Platform에서 지원되는 모든 스키마 필드 유형을 사용할 수 있지만 Customer Journey Analytics에서 모든 필드 유형이 지원되는 것은 아닙니다. 지원되는 데이터 유형은 `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String`, `Boolean`입니다. 현재 조회 데이터 세트에서 `String` 스키마 데이터 유형만 허용됩니다. |
| [!UICONTROL 구성 요소 ID] | 필수. [Customer Journey Analytics API](https://adobe.io/cja-apis/docs)는 이 필드를 사용하여 구성 요소를 참조합니다. 데이터 보기의 각 구성 요소는 고유해야 합니다. Adobe는 각 구성 요소의 ID를 자동으로 생성합니다. 그러나 편집 아이콘을 클릭하고 구성 요소 ID를 수정할 수 있습니다. 이 구성 요소 ID를 변경하면 이 구성 요소가 포함된 기존의 모든 Workspace 프로젝트가 중단됩니다. 각 구성 요소는 단일 데이터 보기에서 고유 ID가 필요하지만 다른 데이터 보기에서는 동일한 구성 요소 ID를 사용할 수 있습니다. 다른 데이터 보기에서 동일한 구성 요소 ID를 사용하는 경우 Workspace 프로젝트는 데이터 보기 간에 호환될 수 있습니다. <br/>프로필 및 조회 기반 구성 요소의 경우 구성 요소 ID에 데이터 세트 ID를 기반으로 하는 ID 접두사가 있습니다(예: `642b28fcc1f0ee1c074265a0.person.name.firstName`). Workspace 프로젝트에서 `person.name.firstName`과 같은 프로필 또는 조회 기반 구성 요소를 재사용하고 이 구성 요소를 다른 데이터 보기에서 구성하려면 데이터 보기 전체에서 구성 요소 ID의 이름을 고유하게 바꾸어야 합니다(예: `myUniqueID.person.name.firstName`). |
| [!UICONTROL 경로] | 필수. 구성 요소의 원본 스키마 경로를 표시하는 편집 불가능한 필드입니다. |
| [!UICONTROL 데이터 사용 레이블] | Adobe Experience Platform에서 이 구성 요소에 할당된 데이터 사용 레이블. [자세히 알아보기](/help/data-views/data-governance.md). |
| [!UICONTROL 보고에서 구성 요소 숨기기] | 관리자가 아닌 경우 데이터 보기에서 구성 요소를 큐레이션할 수 있습니다. 관리자는 여전히 Analysis Workspace 프로젝트에서 [!UICONTROL 모든 구성 요소 표시]를 클릭하여 액세스할 수 있습니다. |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

데모 비디오를 보려면 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [구성 요소 유형 설정](https://video.tv.adobe.com/v/3412938/?quality=12&learn=on&captions=kor){target="_blank"}을 확인하십시오.

>[!ENDSHADEBOX]


