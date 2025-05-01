---
title: 요약 데이터 그룹 구성 요소 설정
description: 요약 데이터를 적절하게 보고할 수 있도록 데이터 세트에서 차원을 구성하는 방법에 대한 세부 정보.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 89%

---

# [!UICONTROL 요약 데이터 그룹] 구성 요소 설정 {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup"
>title="요약 데이터 그룹"
>abstract="요약 데이터 그룹은 그룹의 모든 차원을 연결하며 보고를 위해 요약 데이터 세트의 차원을 다른 차원과 결합하는 데 사용됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup_hideinreporting"
>title="보고에서 숨기기"
>abstract="이 옵션을 선택하면 해당 차원에 대해 **[!UICONTROL 보고에서 구성 요소 숨기기]**&#x200B;가 활성화되며 Analysis Workspace 및 기타 Customer Journey Analytics 보고 도구에서 구성 요소가 표시되지 않습니다."

<!-- markdownlint-enable MD034 -->



요약 데이터 그룹은 그룹의 모든 차원을 연결하며 보고를 위해 요약 데이터 세트의 차원을 다른 차원과 결합하는 데 사용됩니다.

![요약 데이터 그룹 구성 요소 설정](/help/data-views/assets/summary-data-group.png)

차원 그룹화를 생성하는 방법:

1. 차원을 선택합니다.
1. ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 요약 데이터 그룹]**&#x200B;을 선택합니다.
1. **[!UICONTROL 그룹화 만들기]**&#x200B;를 활성화합니다.
1. 첫 번째 단계에서 선택한 차원과 그룹화할 **[!UICONTROL Dimension]** 드롭다운 메뉴에서 차원을 선택합니다. 데이터 보기에 이미 추가한 차원만 드롭다운 메뉴에서 사용할 수 있습니다.
1. 원할 경우, **[!UICONTROL 보고에서 숨기기]**&#x200B;를 활성화하여 그룹화된 차원을 보고에서 숨깁니다. 이 옵션을 활성화하는 것은 그룹화된 차원에서 별도로 **[!UICONTROL 보고서에서 숨기기]**&#x200B;를 구성하는 것과 비슷합니다. 자세한 내용은 [구성 요소 설정](overview.md)을 참조하십시오.
1. 원할 경우, 그룹화에 차원을 추가하려면 ![추가](/help/assets/icons/Add.svg) **[!UICONTROL 그룹에 차원 추가]**&#x200B;를 선택합니다.<br/>요약 데이터 그룹은 10개로 제한되므로 최대 9개의 차원을 추가할 수 있습니다.

## 동일한 구성 요소 설정

차원을 그룹화할 때는 그룹의 일부인 각 차원에 대해 [!UICONTROL 하위 문자열], [!UICONTROL 비헤이비어], [!UICONTROL 포함 제외 값]의 설정이 동일한지 확인해야 합니다. 그렇지 않으면 그룹의 각 차원은 그룹화 전에 잠재적으로 다른 결과를 반환할 수 있습니다.
예:

1. `campaign_code`(요약 데이터의 일부) 및 `tracking_code`(이벤트 데이터의 일부)에 대한 요약 데이터 그룹을 생성했습니다.
1. [!UICONTROL 비헤이비어]를 `tracking_code` 차원에는 적용했지만 `campaign_code`에는 적용하지 않았습니다.

`tracking_code`의 값은 잠재적으로 `campaign_code`과 다르게 표시될 수 있습니다.

>[!IMPORTANT]
>
>차원을 한 차원에서만 그룹화하고, 여러 차원에서 그룹화하지 않도록 주의하십시오. 예를 들어 `tracking_code` 차원에 `campaign_name` 차원을 추가하여 그룹을 생성하는 경우, `campaign_name` 차원에 대한 그룹도 생성하지 마십시오.
>
