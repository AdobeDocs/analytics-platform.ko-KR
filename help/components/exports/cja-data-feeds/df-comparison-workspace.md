---
description: Customer Journey Analytics 및 Adobe Analytics에서 데이터 피드 기능을 비교하는 방법 알아보기
keywords: 클릭스트림, 데이터 피드, 데이터피드, 데이터 피드
title: Customer Journey Analytics 및 Adobe Analytics의 데이터 피드 기능 비교
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7f3fb46b9c1928f8b02ce2108b4e98b5cc8da766
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 0%
---
# 데이터 피드와 Analysis Workspace 간의 데이터 불일치 이해

{{release-limited-testing}}

데이터 피드 내보내기의 데이터가 항상 Analysis Workspace에 표시되는 데이터와 정확히 일치하는 것은 아닙니다. 이 페이지의 정보에서는 몇 가지 주요 이유를 설명합니다.

이러한 차이점 중 일부는 Workspace 데이터가 집계되기 때문에 Workspace 보고서에서만 보기 어려운 Workspace 행동에서 기인합니다. 데이터 피드는 이벤트 수준 데이터를 제공하므로 데이터 피드 출력을 Workspace 보고서와 비교할 때 이러한 동작이 명확해집니다.

## 처리 창(데이터 피드)과 보고 창(Analysis Workspace) 비교 {#processing-window}

각 데이터 피드 게재는 롤링 30일 처리 기간을 사용합니다. 처리 창은 데이터 피드 전달에서 이벤트를 분류하는 데 필요한 기록 컨텍스트를 제공합니다. 예를 포함하여 처리 창에 대한 자세한 내용은 [처리 창 이해](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window)를 참조하십시오.

그런 의미에서 처리 기간은 Analysis Workspace의 보고 기간(보고서에 대해 선택하는 날짜 범위)과 유사합니다. 하지만, 중요한 차이점이 있습니다.

| 주요 차이점 | 보고 기간(Analysis Workspace) | 처리 창(데이터 피드) |
|---------|---------|----------|
| **보고할 일정**<br/>&#x200B;보고서 또는 피드에 포함된 이벤트 | 보고 기간이 시작되는 달력의 첫째 날에 시작하여 보고 기간이 끝날 때 끝납니다.<p>예를 들어, 보고 기간이 10월 6일부터 11월 5일까지인 보고서에는 10월 1일부터 10월 5일까지의 이벤트도 포함됩니다. Workspace 데이터가 집계되기 때문에 이러한 추가 이벤트는 인식하기 어려울 수 있습니다.</p><!--SME CHECK: Confirm that every Workspace report includes events from the first day of the calendar month in which the reporting window starts (per Luke, Nov 5, 2026), including segment qualification for segments limited to the reporting window. Other docs (persistence.md Person Reporting Window row, analysis-workspace/attribution/models.md lookback window) don't describe this yet.--> | 처리 창과 같지 않습니다. <p>보고할 시간대는 빈도 창이며, 처리 기간 종료 시 1시간 또는 1일이 될 수 있습니다.</p> |
| **데이터 경계**<br/>&#x200B;창 외부의 데이터가 보고서 또는 피드에 포함되는지 또는 영향을 주는지 여부 | 유연성<p>보고 기간이 시작되는 달력의 첫째 날 이벤트는 보고 기간 전에 발생한 경우에도 Workspace 보고서에 포함됩니다. 자세한 내용은 위의 **보고할 일정**&#x200B;을(를) 참조하십시오.</p><p>보고 기간을 벗어나는 이벤트는 다음 요소 중 하나를 통해 Workspace 보고서의 데이터에도 영향을 줄 수 있습니다.</p><ul><li>**Dimension 지속성**: 세션, 사용자 지정 시간 또는 지표 [만료](/help/data-views/component-settings/persistence.md#expiration-settings)을(를) 사용할 때 보고 기간 이후에도 지속될 수 있습니다.</li><li>**세그먼트 선별**: 기본적으로 세그먼트는 보고 기간을 넘어 확장할 수 있습니다.<p>사용자는 세그먼트를 만들 때 보고 기간으로 세그먼트를 제한하도록 선택할 수 있습니다. 그런 경우에도 세그먼트 자격은 보고 기간이 시작되는 역월 첫째 날의 이벤트를 고려합니다.</p></li><li>**세션 계산**: 세션이 보고 기간을 초과할 수 있습니다. </li><li>**파생 필드 변환**: 컨테이너를 참조하는 파생 필드 함수는 보고 기간을 사용합니다.<!--SME CHECK: Confirm that Session- and Person-scoped derived field functions (Deduplicate, Next or Previous, Summarize, Date Math) are limited to the reporting window in Workspace, or whether Session scope can extend beyond it like session calculation. ALSO: In the Segment qualification bullet, add a link to the new docs about limiting a segment to the reporting window.--></li></ul> | 고정<p>빈도 창의 이벤트만 데이터 피드에 포함됩니다. 자세한 내용은 위의 **보고할 일정**&#x200B;을(를) 참조하십시오.</p><p>빈도 창 외부에 있지만 처리 창 내에 있는 이벤트는 데이터 피드의 데이터에 영향을 줄 수 있습니다. 일반적으로 처리 창 앞에 해당하는 이벤트는 처리할 수 없습니다. 처리 창은 다음 요소를 제한합니다.</p><ul><li>**Dimension 지속성**: 세션, 개인 보고 기간 또는 지표 [만료](/help/data-views/component-settings/persistence.md#expiration-settings)을(를) 사용할 때는 처리 기간 이상으로 유지할 수 없습니다. Workspace과 달리 전환 보기는 해당 월의 첫째 날까지 연장되지 않습니다. Workspace과 동일한 사용자 지정 시간 [만료](/help/data-views/component-settings/persistence.md#expiration-settings)을(를) 사용할 때 처리 기간(최대 90일) 넘게 지속될 수 있습니다. Workspace과 데이터 피드 모두에서 사용자 지정 시간 전환 확인은 해당 월의 첫 날까지 연장되지 않습니다.<p>**참고:** 현재 사용자 지정 시간 만료도 처리 기간으로 제한됩니다. 처리 기간을 초과하는 사용자 지정 시간에 대한 지원이 곧 제공됩니다.</p></li><li>**세그먼트 선별**: 항상 처리 기간으로 제한됩니다. Workspace과 달리 는 해당 월의 첫 번째 날까지 확장되지 않습니다.</li><li>**세션 계산**: 항상 처리 기간으로 제한됩니다.</li><li>**파생 필드 변환**: 컨테이너를 참조하는 파생 필드 함수는 데이터 피드 내보내기에서 처리 창을 사용합니다.</li></ul> |

>[!BEGINSHADEBOX]

**예**

아래 예는 보고 기간과 처리 기간 간의 차이로 인해 Workspace 보고서와 데이터 피드 게재 간에 데이터 불일치가 발생하는 방식을 보여 줍니다.

* **보고할 일정**: 사용자에게 차원 값을 설정하는 이벤트가 10월 1일에 있으며, 더 많은 이벤트는 10월 말에 있습니다. Workspace에는 매월 1일의 이벤트가 포함되므로 10월 6일에 시작되는 보고 기간이 있는 Workspace 보고서에는 10월 1일 이벤트가 포함됩니다. 10월 1일에 설정된 값은 보고 기간에 사용자의 이벤트까지 지속될 수도 있습니다. 10월 6일에 시작되는 처리 기간을 사용하는 데이터 피드 게재는 10월 1일 이벤트를 고려하지 않으므로 이 값이 게재에서 사용자의 이벤트에 지속되지 않습니다.

* **세그먼트 자격**: 45일 전에 개인 컨테이너를 사용하여 세그먼트에 대한 자격이 있는 사용자가 오늘 이벤트를 갖게 되었습니다. 세그먼트가 기본적으로 보고 기간을 초과할 수 있으므로 30일 보고 기간이 있는 Workspace 보고서에는 사용자의 이벤트가 포함됩니다. 세그먼트 자격이 30일 처리 기간으로 제한되므로 오늘의 데이터 피드 배달에는 이벤트가 포함되지 않습니다.

<!-- update the following graphic: ![Data differences between workspace and data feeds](assets/data-feed-data-differences.png) -->

>[!ENDSHADEBOX]

## 결합 재생

결합 재생이 실행될 때마다 내역 ID 데이터가 소급하여 업데이트됩니다.

데이터 피드 및 Analysis Workspace은 다음과 같이 결합 재생을 다르게 처리합니다.

* **데이터 피드**: 내보낼 때만 결합된 ID를 반영합니다. 재생 결과는 내보낸 파일에 소급하여 적용되지 않습니다.

* **Analysis Workspace**: 재생이 실행될 때마다 소급하여 업데이트된 최신 결합 데이터를 표시합니다. 각 재생 후 내역 데이터가 변경되므로 Workspace은 항상 최신 ID 확인을 반영합니다.

## 늦게 도착하는 이벤트

데이터 피드에서 이벤트는 데이터 피드 내보내기 창이 닫힌 후에 도착할 수 있습니다.

데이터 피드 및 Analysis Workspace은 다음과 같이 이전 이벤트와 관련하여 다르게 작동합니다.

* **데이터 피드**: 이벤트 타임스탬프를 기반으로 고정된 기간(각 게재의 시간 또는 일) 내의 데이터를 내보냅니다.

  각 게재를 처리하기 전에 Customer Journey Analytics은 사용자가 선택한 [처리 지연](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay)을 기다립니다. 처리 지연 중에 도착하는 이벤트는 게재에 포함됩니다. 처리가 시작된 후에 도착하는 이벤트는 데이터 피드 파일에 포함되지 않습니다.

* **Analysis Workspace**: 보고서 시간에 데이터를 처리하므로 이벤트가 수신된 시기에 관계없이 보고서에 포함됩니다.

## 데이터 일괄 처리

데이터가 긴 기간에 걸쳐 일괄적으로 제출되는 경우가 있습니다.

데이터 피드 및 Analysis Workspace은 다음과 같이 일괄 처리된 데이터에 대해 다르게 작동합니다.

* **데이터 피드**: 원래 타임스탬프를 기반으로 매일 또는 시간에 일괄 처리된 데이터를 배포합니다. 예를 들어 30일 동안의 데이터가 포함된 배치는 내보내기 30일에 걸쳐 분산되므로 단일 내보내기에서 작은 조각만 나타납니다.

* **Analysis Workspace**: 일괄 처리에 포함된 시간 범위와 관계없이 일괄 처리가 완전히 처리되는 즉시 모든 데이터를 표시합니다.

