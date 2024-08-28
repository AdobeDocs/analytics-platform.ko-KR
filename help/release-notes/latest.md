---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b5877ff515147964c2d4fbd6eaa43a8a99f0fe0
workflow-type: ht
source-wordcount: '540'
ht-degree: 100%

---

# 현재 Adobe Customer Journey Analytics 릴리스 정보 (2024년 8월)

**마지막 업데이트**: 2024년 8월 14일

이번 릴리스 정보에는 2024년 8월 14일부터 9월까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **요약 수준 데이터 소스** | 개인 ID가 없는 시계열 데이터를 가져올 수 있습니다. 이 시계열 데이터를 사용하여 다음과 같은 다양한 사용 사례를 지원할 수 있습니다.<ul><li>이벤트 수준 데이터의 일부 또는 거의 유사한 높은 수준의 성과 지표를 제공합니다. 여기에는 날짜 및 단일 지표 값 등 간단한 항목이 포함되거나 광고 노출 횟수, 이메일 열기, 광고 비용, 매출 원가 등 여러 차원 항목 및 지표가 포함될 수 있습니다.</li><li>매시간 또는 매일 대상이나 목표를 업로드한 다음 이벤트 수준 지표에 대해 이들 대상 또는 목표를 배치합니다. 이는 조직의 대상 또는 목표 대비 지표의 추세가 어떻게 변화하는지를 시각화하는 데 도움이 됩니다.</li></ul><p>자세한 내용은 [요약 데이터](/help/data-views/summary-data.md)를 참조하십시오.</p> | 2024년 8월 13일 | 2024년 8월 21일 |
| **대상자가 Experience Platform의 새로운 “대상자” 섹션에 게시됨** | 이제 Customer Journey Analytics에서 게시된 대상자를 Adobe Experience Platform의 새로운 “대상자” 섹션에서 사용할 수 있습니다.<p>이전에는 Customer Journey Analytics에서 게시된 대상자를 Experience Platform의 “세그먼트” 섹션에서 사용할 수 있었습니다.</p><p>이 개선 사항은 다음과 같은 이점이 있습니다.</p><ul><li>대상자가 더 이상 1시간의 지연 없이 Experience Platform에 표시됩니다. 게시된 지 몇 초면 사용할 수 있습니다.</li><li>Experience Platform에서 대상자가 원래 게시된 애플리케이션을 표시하는 “원본” 열을 사용하여 대상자를 정렬할 수 있습니다.</li><li>Experience Platform의 필터링 및 정렬 옵션을 사용하여 해당 대상자를 보다 빨리 찾을 수 있습니다.</li></ul> <p>자세한 내용은 [대상자 만들기 및 게시](/help/components/audiences/publish.md) 문서의 [Experience Platform에서 Customer Journey Analytics 대상자 사용](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform)을 참조하십시오.</p> | 2024년 9월 | 2024년 9월 |
| **지능형 경고** | Customer Journey Analytics에서 지능형 경고를 사용하면 데이터에 비정상적인 이벤트 발생 시 즉시 알림을 받을 수 있습니다.<p>예외 항목 임계값, 백분율 변경 또는 특정 데이터 포인트를 기준으로 지능형 경고가 트리거되도록 설정할 수 있습니다. 경고는 예외 항목 탐지 기능과 통합하여 필요 시 트리거되는 세부적인 제어를 제공합니다.</p><p>Customer Journey Analytics에서 지능형 경고의 사용 프로세스는 Adobe Analytics에서 지능형 경고의 사용 프로세스와 거의 동일합니다. 한 가지 주요 차이점은 시간별 경고는 Customer Journey Analytics에서 사용할 수 없다는 것입니다. 이러한 차이는 가져올 수 있는 다양한 이벤트 데이터에 대한 데이터 수집이 일반적으로 데이터 이벤트 시간보다 3~9시간 정도 지연된 이후에 완료되기 때문입니다.</p><p>(업데이트된 설명서 링크)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | TBD |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-354359, AN-351646, AN-346873, AN-352504, AN-353755, AN-354199, AN-354268, AN-354791, AN-354598, AN-354462, AN-354547

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
