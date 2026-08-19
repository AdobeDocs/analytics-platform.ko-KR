---
description: Customer Journey Analytics 및 Adobe Analytics에서 데이터 피드 기능을 비교하는 방법 알아보기
keywords: 클릭스트림, 데이터 피드, 데이터피드, 데이터 피드
title: Customer Journey Analytics 및 Adobe Analytics의 데이터 피드 기능 비교
feature: Components
hide: true
source-git-commit: 7fe885e928c495a2518038645ec841229d1f1852
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 0%

---

# 데이터 피드와 Analysis Workspace 간의 데이터 불일치 이해

{{release-limited-testing}}

데이터 피드 내보내기의 데이터가 항상 Analysis Workspace에 표시되는 데이터와 정확히 일치하는 것은 아닙니다. 이 페이지의 정보에서는 몇 가지 주요 이유를 설명합니다.

## 전환 확인 날짜 범위(데이터 피드)와 보고 날짜 범위(Analysis Workspace)

데이터 피드의 전환 확인 날짜 범위는 데이터 피드 배달에 적합한 이벤트를 찾을 때 Customer Journey Analytics이 표시되는 전환 확인 시간을 결정합니다. 예제를 포함하여 전환 확인 날짜 범위에 대한 자세한 내용은 [전환 확인 날짜 범위 이해](/help/components/exports/cja-data-feeds/create-feed.md#understand-the-lookback-date-range)를 참조하십시오.

그러한 의미에서 전환 확인 날짜 범위는 Analysis Workspace의 보고 날짜 범위와 유사합니다. 하지만, 중요한 차이점이 있습니다.

| 주요 차이점 | 보고 날짜 범위(Analysis Workspace) | 전환 확인 날짜 범위(데이터 피드) |
|---------|---------|----------|
| **데이터 경계**<br/>&#x200B;데이터가 보고서 또는 피드에 포함되는지 여부 | 유연성<p>보고 날짜 범위를 벗어나는 이벤트는 이벤트가 다음 요인 중 하나에 의해 영향을 받는 경우 여전히 Workspace 보고서에 포함될 수 있습니다.</p><ul><li>**Dimension 지속성**: 세션, 사용자 지정 시간 또는 지표 [만료](/help/data-views/component-settings/persistence.md#expiration-settings)을(를) 사용할 때 보고 날짜 범위 이상으로 지속될 수 있습니다. 개인 보고 기간 [만료](/help/data-views/component-settings/persistence.md#expiration-settings)을(를) 사용할 때의 보고 날짜 범위와 동일합니다. 데이터가 집계됩니다.</li><li>**세그먼트 선별**: 기본적으로 세그먼트는 보고 날짜 범위 이상으로 확장할 수 있습니다.<p>사용자는 세그먼트를 만들 때 보고 날짜 범위로 세그먼트를 제한하도록 선택할 수 있습니다.<!--add link to new docs--></p></li><li>**세션 계산**: 세션이 보고 날짜 범위 이상으로 확장될 수 있습니다. </li><li>**파생 필드 변환**</li></ul> | 고정<p>전환 확인 날짜 범위를 벗어나는 이벤트는 다음 요인의 영향을 받는지 여부에 관계없이 데이터 피드에 포함되지 않습니다.</p></p><ul><li>**Dimension 지속성**: [만료 설정](/help/data-views/component-settings/persistence.md#expiration-settings)에 관계없이 전환 확인 날짜 범위 이상으로 유지할 수 없습니다. 데이터가 집계되지 않습니다.</li><li>**세그먼트 자격**: 항상 전환 확인 날짜 범위로 제한됩니다.</li><li>**세션 계산**: 항상 전환 확인 날짜 범위로 제한됩니다.</li><li>**파생 필드 변환**: 컨테이너를 참조하는 파생 필드 함수는 데이터 피드 내보내기에서 전환 확인 날짜 범위를 사용합니다.</li></ul><p>전환 확인 날짜 범위 구성에 대한 자세한 내용은 [데이터 피드 만들기](/help/components/exports/cja-data-feeds/create-feed.md#create-and-configure-a-data-feed)를 참조하십시오.</p> |
| **보고 기간**<br/>&#x200B;보고할 시간대입니다 | 보고 기간(보고할 시간대)과 동일합니다. | 보고할 시간대와 동일하지 않습니다. <p>보고할 시간대는 빈도 창이며, 이 기간은 1시간 또는 하루일 수 있습니다.</p> |

>[!BEGINSHADEBOX]

**예**

아래 예제는 보고 날짜 범위와 전환 확인 날짜 범위 간의 차이로 인해 Workspace 보고서와 데이터 피드 게재 간에 데이터가 어떻게 불일치하는지 보여 줍니다.

이벤트 A는 85일 전에 발생했으며 90일 지속성 설정(예: 캠페인 클릭 속성 창)이 있는 차원에 있습니다. 이벤트는 Analysis Workspace 보고서에 포함되며 데이터 피드 전달에는 포함되지 않습니다.

![작업 영역과 데이터 피드 간의 데이터 차이점](assets/data-feed-data-differences.png)


>[!ENDSHADEBOX]

## 결합 재생

결합 재생이 실행될 때마다 내역 ID 데이터가 소급하여 업데이트됩니다.

데이터 피드 및 Analysis Workspace은 다음과 같이 결합 재생을 다르게 처리합니다.

* **데이터 피드**: 내보낼 때만 결합된 ID를 반영합니다. 재생 결과는 내보낸 파일에 소급하여 적용되지 않습니다.

* **Analysis Workspace**: 재생이 실행될 때마다 소급하여 업데이트된 최신 결합 데이터를 표시합니다. 각 재생 후 내역 데이터가 변경되므로 Workspace은 항상 최신 ID 확인을 반영합니다.

## 늦게 도착하는 이벤트

데이터 피드에서 이벤트는 데이터 피드 내보내기 창이 닫힌 후에 도착할 수 있습니다.

데이터 피드 및 Analysis Workspace은 다음과 같이 이전 이벤트와 관련하여 다르게 작동합니다.

* **데이터 피드**: 이벤트가 수신되는 시점을 기준으로 고정 기간 내의 데이터를 내보냅니다.

  창이 닫힌 후에 도착하는 이벤트는 내보내기에 포함되지 않을 수 있습니다. 선택한 [전환 확인 날짜 범위](#lookback-date-range-data-feeds-vs-reporting-date-range-analysis-workspace)의 영향을 받습니다.

* **Analysis Workspace**: 보고서 시간에 데이터를 처리하므로 이벤트가 수신된 시기에 관계없이 보고서에 포함됩니다.

## 데이터 일괄 처리

데이터가 긴 기간에 걸쳐 일괄적으로 제출되는 경우가 있습니다.

데이터 피드 및 Analysis Workspace은 다음과 같이 일괄 처리된 데이터에 대해 다르게 작동합니다.

* **데이터 피드**: 원래 타임스탬프를 기반으로 매일 또는 시간에 일괄 처리된 데이터를 배포합니다. 예를 들어 30일 동안의 데이터가 포함된 배치는 내보내기 30일에 걸쳐 분산되므로 단일 내보내기에서 작은 조각만 나타납니다.

* **Analysis Workspace**: 일괄 처리에 포함된 시간 범위와 관계없이 일괄 처리가 완전히 처리되는 즉시 모든 데이터를 표시합니다.

