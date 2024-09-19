---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 81%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2024년 9월)

**마지막 업데이트**: 2024년 9월 11일

이번 릴리스 정보에는 2024년 9월 11일부터 10월 초까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **계산된 지표 관리자 및 필터 관리자 내 “다음에서 사용” 열의 추가 정보** | 계산된 지표 관리자 및 필터 관리자의 “다음에서 사용” 열에는 다음과 같은 새로운 보고 영역이 포함되어 있습니다.<ul><li>**Report Builder**: Report Builder에서 사용되는 계산된 지표 또는 필터의 수를 보여 줍니다.</li><li>**애드혹 구성 요소**: 프로젝트에서 사용되는 애드혹 계산된 지표 또는 애드혹 필터의 수를 보여 줍니다. 이러한 애드혹 계산된 지표 및 필터(“빠른 계산된 지표” 및 “빠른 필터”라고도 함)는 생성된 프로젝트에서만 사용할 수 있으므로 “다음에서 사용” 열의 “프로젝트” 보고 영역에서 별도로 보고됩니다.</li></ul>자세한 내용은 [계산된 지표 관리자](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) 및 [필터 관리자](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-components/cja-filters/manage-filters)를 참조하시기 바랍니다. |  | 2024년 9월 11일 |
| **경고** | Customer Journey Analytics의 경고를 사용하면 변경된 백분율이나 특정 데이터 포인트에 따라 알림을 받을 수 있습니다.<p>Customer Journey Analytics 패키지에 따라 예외 항목 임계값에 따라 트리거할 경고를 사용할 수도 있습니다. 이러한 경고(&quot;지능형 경고&quot;라고도 함)는 예외 항목 탐지 와 통합되어 가장 필요할 때 트리거되는 세분화된 제어를 제공합니다.</p><p>Customer Journey Analytics에서 경고를 사용하는 프로세스는 Adobe Analytics에서 경고를 사용하는 프로세스와 거의 동일합니다. 한 가지 주요 차이점은 시간별 경고는 Customer Journey Analytics에서 사용할 수 없다는 것입니다. 이러한 차이는 가져올 수 있는 다양한 이벤트 데이터에 대한 데이터 수집이 일반적으로 데이터 이벤트 시간보다 3~9시간 정도 지연된 이후에 완료되기 때문입니다.</p><p>Adobe Analytics의 Customer Journey Analytics에서 경고를 사용할 때의 차이점에 대한 자세한 내용은 [경고 기능 비교](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)를 참조하십시오.</p><p>경고에 대한 자세한 내용은 [경고 개요](/help/components/c-intelligent-alerts/intelligent-alerts.md)를 참조하세요. |  | 2024년 9월 13일 토요일 |
| **Adobe Analytics Source Connector 업데이트** | Analytics Source Connector는 Adobe에서 전적으로 관리하므로 데이터 세트 활동 페이지에는 배치에 대한 정보가 표시되지 않습니다. 수집한 레코드 주변의 지표를 확인하여 데이터 흐름을 모니터링할 수 있습니다. 자세한 내용은 [Analytics 데이터의 소스 연결을 만드는 방법](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)에 관한 안내서를 참조하십시오. |  | 지금 사용 가능 |
| **Usage Analytics** | 귀하의 조직에서 Customer Journey Analytics를 어떻게 사용할 수 있는지 확인해 보십시오. 이 기능을 활성화하면 조직 내에서 Analysis Workspace를 사용할 때 Adobe Experience Platform에 데이터를 수집하는 데이터 세트가 생성됩니다. 연결 및 데이터 보기도 자동으로 생성되므로 상위 프로젝트 유형, 가장 활동적인 사용자, 프로젝트에서 가장 많이 사용되는 구성 요소 등의 차원에 액세스할 수 있습니다. (참조할 설명서 링크) |  | 2024년 9월 18일 |
| **안내식 분석: Workspace에 임베드** | Analysis Workspace에서 여러 안내식 분석을 단일 보기로 결합합니다. (참조할 설명서 링크) | 2024년 9월 22일 | 2024년 10월 2일 |


## Customer Journey Analytics의 수정 사항

AN-352461; AN-355446: AN-355665

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 | | |

{style="table-layout:auto"}

## 관련 리소스

* [2024년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2024.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [스트리밍 미디어 컬렉션 추가 기능 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
