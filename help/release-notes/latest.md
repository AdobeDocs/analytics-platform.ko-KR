---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fc1a5b1b0f01ace6207820e2421d1770f68c3583
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 50%

---

# Customer Journey Analytics(CJA) 릴리스 노트(2022년 10월)

**마지막 업데이트**: 2022년 10월 5일

Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 제공 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이러한 릴리스 정보를 정기적으로 확인하십시오.

## 관련 리소스

* [2022년 이전 CJA 릴리스 정보](/help/release-notes/2022.md)

* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko)

* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## 주요 기능

| 기능 | 설명 | [목표 날짜](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **실험 패널** | 이 새로운 작업 영역 패널을 통해 CJA 사용자는 온라인, 오프라인, Adobe 솔루션, Adobe Journey Optimizer 및 BYO 데이터 등 모든 소스에서 A/B 실험의 상승도와 신뢰도를 평가할 수 있습니다. [자세히 알아보기](/help/analysis-workspace/c-panels/experimentation.md) | 2022년 10월 5일 |
| **[!UICONTROL 주요 지표 요약] 시각화** | 다음 [!UICONTROL 주요 지표 요약] 시각화를 사용하면 단일 기간 내에서 중요한 지표가 어떻게 트렌드를 표시하는지 확인할 수 있습니다. 또한 두 기간에 걸쳐 지표의 성능을 비교할 수 있습니다. 자세히 알아보기 | 2022년 10월 5일부터 단계적 롤아웃 시작 |
| **CJA의 날짜 필드 지원** | CJA에서 날짜 및 날짜-시간 필드를 보고할 수 있습니다. [자세히 알아보기](/help/data-views/data-views-usecases.md#date) | 2022년 10월 5일 |
| **모바일 앱: 사용자 지정 세부 사항 보기** | 사용자 지정 세부 사항 보기를 사용하면 가장 중요한 사항에 집중할 수 있도록 하여 대상자와 공유하는 정보에 대해 더 많은 타겟팅할 수 있습니다. 각 스코어카드 타일과 연관된 세부 사항 보기의 레이아웃을 변경할 수 있으며 텍스트를 추가하여 최종 사용자가 데이터에 볼 수 있는 내용을 더 잘 설명할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=ko) | 2022년 10월 5일 |

{style=&quot;table-layout:auto&quot;}

## CJA 관리자를 위한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **기본 랜딩 페이지** | 2023년 9월 29일 | 다음 [새 랜딩 페이지](/help/getting-started/landing.md) 올해 초에 도입된 것은 **2023년 1월**. 현재 페이지는 더 이상 사용되지 않으며 모든 사용자가 새 경험을 사용해야 합니다. |
| **개선된 IP-to-geolocation 매핑** | 2022년 9월 29일 | Adobe의 IP 조회 공급업체인 Digital Element는 IP-to-geolocation 매핑을 위해 새롭게 개선된 데이터 세트(NetAcuity Pulse)로 업그레이드하고 있습니다. Adobe Analytics은 이 새 데이터 집합의 채택을 연기했습니다. **2023년 1월**. 새 데이터베이스는 이전 버전보다 더 정확합니다. 새 데이터베이스가 채택되면 일부 IP-to-geo 매핑이 변경 및 개선됩니다.<p> 를 통해 제공된 CJA 데이터 [!UICONTROL Analytics 소스 커넥터] 또한 새 매핑을 자동으로 이용할 수 있습니다. |
| **[!UICONTROL 예외 항목 탐지] 자동 실행 조건** | 2022년 9월 29일 | 오늘 [!UICONTROL 예외 항목 탐지] 시계열 자유 형식 테이블의 모든 열에서 자동 실행됩니다. 분석 및 프로젝트를 더 빨리 로드하는 데 데이터를 사용할 수 있도록 Adobe이 방법을 변경합니다 [!UICONTROL 예외 항목 탐지] 자동 실행. 시작 **2022년 10월 26일**, 예외 항목 탐지는 테이블의 첫 번째 지표 열에서만 자동으로 실행됩니다. 열 설정을 구성하여 실행할 수 있습니다 [!UICONTROL 예외 항목 탐지] 필요한 경우 다른 열에 추가합니다. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
