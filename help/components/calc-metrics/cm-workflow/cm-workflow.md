---
description: 계산된 지표를 만드는 방법을 알아봅니다.
title: 계산된 지표 만들기
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 18%

---

# 계산된 지표 만들기

기본적으로 관리자만 계산된 지표를 만들 수 있습니다. 사용자에게 계산된 지표를 볼 수 있는 권한이 있습니다. 이는 사용자가 다른 구성 요소(예: 세그먼트, 주석 등)를 보는 것과 유사합니다.

그러나 관리자는 **[!UICONTROL Admin Console]**&#x200B;을 통해 **[!UICONTROL CJA Workspace 액세스에 대한 권한 편집]**&#x200B;에서 **[!UICONTROL 보고 도구]**&#x200B;에 대한 [계산된 지표 만들기](/help/technotes/access-control.md#user-level-access) 권한을 사용자에게 부여할 수 있습니다.


다음 방법으로 계산된 지표를 만들 수 있습니다.

![지표를 만드는 방법](assets/create-metric.png)

* **A**. 주 인터페이스에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택하고 **[!UICONTROL 계산된 지표]**&#x200B;을(를) 선택합니다. ![계산된 지표](/help/assets/icons/AddCircle.svg) 관리자[!UICONTROL **[!UICONTROL 에서 &#x200B;]**]AddCircle[추가](/help/components/calc-metrics/cm-workflow/cm-manager.md)를 선택합니다.
* **B**. Workspace 프로젝트의 구성 요소 왼쪽 패널에서 ![이벤트](/help/assets/icons/Add.svg) ![지표](/help/assets/icons/Event.svg)의 **추가**&#x200B;를 선택합니다.
* **C**. Workspace 프로젝트의 지표 열 헤더에 있는 컨텍스트 메뉴에서 **[!UICONTROL 선택 항목에서 지표 만들기]**&#x200B;를 선택합니다. 하위 메뉴에서 함수를 선택하거나 **[!UICONTROL 계산된 지표 빌더에서 열기]**&#x200B;를 선택할 수 있습니다. <br/>함수를 선택하면 계산된 지표가 프로젝트 전용 지표로 정의됩니다. 나중에 이 지표를 편집할 때 [구성 요소 정보](/help/components/use-components-in-workspace.md#component-info) 팝업을 통해 [계산된 지표 빌더](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)에 알림이 표시됩니다.
* **D**. Workspace 프로젝트의 메뉴에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택하고 **[!UICONTROL 지표 만들기]**&#x200B;를 선택합니다.
* **E**. Workspace 프로젝트에서 바로 가기 **[!UICONTROL shift+cmd+c]**(macOS) 또는 **[!UICONTROL shift+ctrl+c]**(Windows)을 사용합니다.

새 계산된 지표를 정의하려면 [계산된 지표 빌더](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)를 사용합니다.


## 워크플로

계산된 지표를 만들기 전에 다음 워크플로를 신중하게 고려하십시오.

| 워크플로 작업 | 설명 |
| --- | --- |
| 계산된 지표 계획 | 특히 공식적으로 승인될 지표의 경우, 널리 사용될 계산된 지표와 그 정의 방법을 대략적으로 설명하는 것이 좋습니다. |
| [빌드](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) 계산된 지표 | [!DNL Customer Journey Analytics] 구성 요소에서 사용할 계산 및 고급 계산된 지표를 작성하고 편집합니다. |
| [태그](cm-tagging.md) 계산된 지표 | 편리한 구성 및 공유를 위해 계산된 지표에 태그를 지정합니다. 단순 및 고급 검색 및 조직에 대해 태그를 계획하고 할당하는 방법을 참조하십시오. |
| [승인](cm-approving.md) 계산된 지표 | 계산된 지표를 승인하여 표준으로 지정합니다. |
| 계산된 지표 사용 | 프로젝트에서 계산된 지표를 사용합니다. |
| [계산된 지표 공유](cm-sharing.md) | 계산된 지표를 다른 개인, 그룹 또는 조직과 공유합니다. |
| [계산된 지표 &#x200B;](cm-filter.md)개 필터링 | 태그, 소유자 및 기타 필터(모두, 내 세그먼트, 나와 공유, 즐겨찾기 및 승인됨 표시)로 계산된 지표를 필터링합니다. |
| 계산된 지표를 [즐겨찾기](cm-finding.md)(으)로 표시 | 지표를 즐겨찾기로 표시하는 것은 쉽게 사용할 수 있게 구성하는 또 다른 방법입니다. |

