---
title: 구성 요소 개요
description: CJA가 제공하는 구성 요소와 보고 시 그러한 구성 요소를 사용할 수 있는 방법을 알아봅니다.
translation-type: tm+mt
source-git-commit: c1699c4319b3b840d8420f3ffa1a4bd1c1d9a4d4
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 57%

---


# 구성 요소 개요

구성 요소는 보고서에서 사용하거나 보고 기능을 보완하는 Customer Journey Analytics의 기능입니다. 다음 단계를 사용하여 이러한 구성 요소를 관리할 수 있습니다.

1. Adobe ID 자격 증명을 사용하여 [analytics.adobe.com](https://analytics.adobe.com)에 로그인합니다.
2. 헤더 메뉴에서 [!UICONTROL 구성 요소] > [!UICONTROL 구성 요소]로 이동합니다.

다음 구성 요소를 관리할 수 있습니다.

* [**필터**](filters/filters-overview.md): 데이터의 일부를 제외하여 공통 차원 항목에 주력
* [**계산된 지표**](calc-metrics/calc-metr-overview.md): 보고에 사용할 새 구성 요소로 지표 및 공식 사용
* [**날짜 범위**](date-ranges/overview.md): Analysis Workspace에서 제공하는 날짜 범위 사용자 지정 및 세분화
* [**프로젝트**](/help/analysis-workspace/home.md): Analysis Workspace에서 프로젝트 구성 및 유지 관리

## Analysis Workspace 구성 요소

Analysis Workspace의 구성 요소는 프로젝트로 드래그하여 놓을 수 있는 지표, 차원, 세그먼트 및 시간 세부기간으로 구성됩니다. 사용자 지정 날짜 범위와 같은 만든 사용자 지정 구성 요소는 이러한 패널에 추가됩니다.

구성 요소 패널에 액세스하려면 왼쪽 레일에서 **[!UICONTROL 구성 요소]** 아이콘을 클릭하십시오. 왼쪽 레일 아이콘이나 [핫키](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)를 사용하여 패널(빈 패널, [자유 형식 패널](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [빠른 인사이트](/help/analysis-workspace/c-panels/quickinsight.md) 또는 [기여도 IQ](/help/analysis-workspace/c-panels/attribution.md) 패널), [시각화](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) 및 구성 요소 간을 전환할 수 있습니다.

![](assets/components.png)

프로젝트에서의 구성 요소 사용에 대한 자세한 내용은 [프로젝트 만들기](/help/analysis-workspace/home.md)를 참조하십시오.

## 구성 요소 작업

다양한 방법으로(개별적으로 또는 두 개 이상을 선택하여) 구성 요소를 관리할 수 있습니다. 구성 요소를 마우스 오른쪽 단추로 클릭하거나 구성 요소 목록의 맨 위에서 **[!UICONTROL 작업]**&#x200B;을 클릭하십시오.

>[!NOTE]
>
>시간 구성 요소에는 이 작업이 적용되지 않습니다.

| 구성 요소 작업 | 설명 |
|--- |--- |
| 태그 | 구성 요소에 태그를 적용하여 구성 요소를 구성하거나 관리합니다. 그러면 각 구성 요소 관리자에 Analytics > 구성 요소 > 세그먼트 또는 Analytics > 구성 요소 > 프로젝트와 같이 표시됩니다. |
| 즐겨찾기 | 구성 요소를 즐겨찾기 목록에 추가합니다. 그러면 각 구성 요소 관리자에 Analytics > 구성 요소 > 세그먼트 또는 Analytics > 구성 요소 > 프로젝트와 같이 표시됩니다. |
| 승인 | 정형화되도록 구성 요소를 승인합니다. 그러면 각 구성 요소 관리자에 Analytics > 구성 요소 > 세그먼트 또는 Analytics > 구성 요소 > 프로젝트와 같이 표시됩니다. |
| 공유 | 세그먼트에만 적용됩니다. |
| 삭제 | 세그먼트에만 적용됩니다. |

지표, 세그먼트 및 날짜 만들기에 대한 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## 구성 요소 액세스 권한

관리자는 보고 시 사용자에게 노출되는 구성 요소를 [Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en#manage-users-and-products)을 통해 관리할 수 있습니다. 다음 표는 이러한 구성 요소 액세스 권한이 어떻게 작동하는지 보여줍니다.

| 조정 유형 | 관리자는 | 관리자가 아닌 프로젝트 소유자(또는 역할 편집)는 | 관리자가 아닌 복제 역할 |
| --- | --- | --- | --- |
| **데이터 보기에서 &quot;숨겨진&quot; 구성 요소** | 보고에 사용할 수 있는 모든 데이터 보기 구성 요소(숨겨진 구성 요소는 &quot;모두 표시&quot; 클릭 필요) | 보고에 사용할 수 없음 | 보고에 사용할 수 없음 |
| **데이터 보기에서 추가 또는 제거된 구성 요소** | 데이터 보기에 추가된 구성 요소만(숨김 또는 숨김 안). 관리자는 데이터 보기로 정의되지 않은 필드 또는 구성 요소에 대해 보고할 수 없습니다. | 데이터 보기에 추가된 구성 요소나 사용자가 소유하거나 사용자와 공유한 구성 요소만 해당됩니다. 숨겨진 구성 요소는 사용할 수 없습니다(예: VRS 조정). | DV에 추가된 구성 요소만 숨겨지지 않으며 프로젝트 큐레이션에 포함되어 있습니다. |
| **프로젝트에서 조정된 구성 요소** | 보고에 사용할 수 있는 모든 데이터 보기 구성 요소(숨겨진 구성 요소는 &quot;모두 표시&quot; 클릭 필요) | 숨기지 않은 모든 데이터 보기 구성 요소(&quot;모두 표시&quot; 클릭 필요) | 선별된 구성 요소뿐만 아니라 사용자와 소유 또는 공유된 모든 구성 요소만 |
| **숨겨진 구성 요소가 있는 데이터 보기를 사용하여 조정된 프로젝트** | 보고에 사용할 수 있는 모든 데이터 구성 요소(숨겨진 구성 요소와 큐레이트가 없는 구성 요소는 &quot;모두 표시&quot;를 클릭해야 함) | 선별되지 않은 모든 프로젝트 구성 요소, 숨기지 않은 모든 데이터 보기 구성 요소 및 사용자가 소유하거나 사용자와 공유한 모든 구성 요소 | 선별된 구성 요소 및 사용자가 소유하거나 사용자와 공유한 모든 구성 요소 |

