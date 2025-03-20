---
description: 계산된 지표를 만드는 방법을 알아봅니다.
title: 계산된 지표 만들기
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: 261d4b5e18531f7971a894bc4cd571b764c625f1
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 2%

---

# 계산된 지표 만들기

기본적으로 관리자만 계산된 지표를 만들 수 있습니다. 사용자에게 계산된 지표를 볼 수 있는 권한이 있습니다. 이는 사용자가 다른 구성 요소(예: 필터, 주석 등)를 보는 것과 유사합니다.

그러나 관리자는 [Admin Console](/help/technotes/access-control.md#user-level-access)을 통해 **[!UICONTROL CJA Workspace 액세스에 대한 권한 편집]**&#x200B;에서 **[!UICONTROL 보고 도구]**&#x200B;에 대한 **[!UICONTROL 계산된 지표 만들기]** 권한을 사용자에게 부여할 수 있습니다.


다음 방법으로 계산된 지표를 만들 수 있습니다.

![필터를 만드는 방법](assets/create-metric.png)

* **A**. 주 인터페이스에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택하고 **[!UICONTROL 계산된 지표]**&#x200B;을(를) 선택합니다. [[!UICONTROL 계산된 지표] 관리자](/help/components/calc-metrics/cm-workflow/cm-manager.md)에서 ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL 추가]**]를 선택합니다.
* **B**. Workspace 프로젝트의 구성 요소 왼쪽 패널에서 ![이벤트](/help/assets/icons/Event.svg) **지표**&#x200B;의 ![추가](/help/assets/icons/Add.svg)를 선택합니다.
* **C**. Workspace 프로젝트의 지표 열 헤더에 있는 컨텍스트 메뉴에서 **[!UICONTROL 선택 항목에서 지표 만들기]**&#x200B;를 선택합니다. 하위 메뉴에서 함수를 선택하거나 **[!UICONTROL 계산된 지표 빌더에서 열기]**&#x200B;를 선택할 수 있습니다. <br/>함수를 선택하면 계산된 지표가 프로젝트 전용 지표로 정의됩니다. 나중에 이 지표를 편집할 때 [구성 요소 정보](/help/components/use-components-in-workspace.md#component-info) 팝업을 통해 [계산된 지표 빌더](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)에 알림이 표시됩니다.
* **일**. Workspace 프로젝트의 메뉴에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택하고 **[!UICONTROL 지표 만들기]**&#x200B;를 선택합니다.
* **E**. Workspace 프로젝트에서 바로 가기 **[!UICONTROL shift+cmd+c]**(macOS) 또는 **[!UICONTROL shift+ctrl+c]**(Windows)을 사용합니다.

새 계산된 지표를 정의하려면 [계산된 지표 빌더](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)를 사용합니다.

<!--

Learn about the steps to take for creating calculated metrics.

| Workflow Task | Description |
| --- | --- |
| Plan Calculated Metrics | Especially for metrics that are going to be officially "approved", it makes sense to outline which calculated metrics will be widely used and how they will be defined. |
| [Build](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) Calculated Metrics | Build and edit calculated and advanced calculated metrics for use in [!DNL Customer Journey Analytics] components. |
| [Tag](cm-tagging.md) Calculated Metrics | Tag calculated metrics for ease of organization and sharing. See how to plan and assign tags for simple and advanced searches and organization. |
| [Approve](cm-approving.md) Calculated Metrics | Approve calculated metrics to make them canonical. |
| Apply Calculated Metrics | You can apply metrics directly from a report, from the Metric Selector (to access it, click [!UICONTROL Show Metrics]). |
| Filter Calculated Metrics | In the Metric Selector, click [!UICONTROL Advanced Selection] and filter by tags, owners, and other filters (Show All, Mine, Shared With me, Favorites, and Approved.) |
| Mark Calculated Metrics as [Favorites](cm-finding.md) | Marking metrics as favorites is another way to organize them for ease of use.|

-->
