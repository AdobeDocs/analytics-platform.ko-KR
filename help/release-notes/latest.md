---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: ed5b1a233dc0e4cbfe223fe71e6e1960efba0592
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Customer Journey Analytics (CJA) 릴리스 정보 (2022년 10월)

**마지막 업데이트**: 2022년 10월 13일

Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 제공 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 관련 리소스

* [2022년 이전 CJA 릴리스 정보](/help/release-notes/2022.md)

* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko-KR?lang=ko)

* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ko-KR)

* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko-KR)

## 주요 기능 및 업데이트

| 기능 | 설명 | [목표 일자](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **실험 패널** | 이 새로운 작업 영역 패널을 통해 CJA 사용자는 온라인, 오프라인, Adobe 솔루션, Adobe Journey Optimizer 및 BYO 데이터 등 모든 소스에서 A/B 실험의 상승도와 신뢰도를 평가할 수 있습니다. [자세히 알아보기](/help/analysis-workspace/c-panels/experimentation.md) | 2022년 10월 5일 |
| **[!UICONTROL 주요 지표 요약] 시각화** | [!UICONTROL 주요 지표 요약] 시각화를 통해 단일 기간 내에서 중요한 지표의 추세를 확인할 수 있습니다. 또한 두 기간에 걸쳐 지표의 성능을 비교할 수 있습니다. 자세히 알아보기 | 2022년 10월 5일부터 단계적으로 롤아웃 |
| **CJA의 날짜 필드 지원** | CJA에서 날짜 및 날짜-시간 필드를 보고할 수 있습니다. [자세히 알아보기](/help/data-views/data-views-usecases.md#date) | 2022년 10월 5일 |
| **모바일 앱: 사용자 정의 상세 보기** | 사용자 정의 상세 보기를 사용하면 대상자가 가장 중요한 것에 집중할 수 있도록 함으로써 대상자와 공유하는 정보에 대해 훨씬 더 정확하게 지정할 수 있습니다. 각 스코어카드 타일과 관련된 상세 보기의 레이아웃을 변경하고 텍스트를 추가하여 최종 사용자가 데이터에서 볼 수 있는 내용을 더 잘 설명할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=ko-KR) | 2022년 10월 5일 |
| **대/소문자를 구분하지 않는 다중 값 변수** | 대/소문자를 구분하지 않는 다중 값 변수의 경우 다음 변수에 저장된 값 `mvvar1` - `mvvar3` 은 더 이상 자동으로 소문자화되지 않습니다. 대신 Analytics 소스 커넥터를 통해 Adobe Experience Platform 및 CJA로 전달된 데이터는 페이지에서 전달된 원래 사례를 반영합니다. | 2022년 10월 24일 |

{style=&quot;table-layout:auto&quot;}

## CJA 관리자를 위한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **기본 랜딩 페이지** | 2023년 9월 29일 | 올해 초에 도입된 [새 랜딩 페이지](/help/getting-started/landing.md)는 **2023년 1월**&#x200B;에 모든 사용자의 기본 환경이 됩니다. 현재 페이지는 더 이상 사용되지 않으며 모든 사용자는 새 환경을 사용해야 합니다. |
| **개선된 IP-to-geolocation 매핑** | 2022년 9월 29일 | Adobe의 IP 조회 공급업체인 Digital Element는 IP-to-geolocation 매핑을 위해 새롭게 개선된 데이터 세트(NetAcuity Pulse)로 업그레이드하고 있습니다. Adobe Analytics는 이 새로운 데이터 세트의 채택을 **2023년 1월**&#x200B;로 연기했습니다. 새 데이터베이스는 이전 버전보다 더 정확합니다. 새 데이터베이스가 채택되면 일부 IP-to-geo 매핑이 변경 및 개선됩니다.<p> [!UICONTROL Analytics Source Connector]를 통해 제공되는 CJA 데이터도 자동으로 새 매핑을 활용합니다. |
| **[!UICONTROL 예외 항목 탐지] 자동 실행 조건** | 2022년 9월 29일 | 오늘, [!UICONTROL 예외 항목 탐지]가 시계열 자유 형식 테이블의 모든 열에서 자동 실행됩니다. 데이터를 분석에 사용할 수 있고 프로젝트를 더 빠르게 로드할 수 있도록 Adobe는 [!UICONTROL 예외 항목 탐지] 자동 실행 방식을 변경할 것입니다. **2022년 10월 26일**&#x200B;부터 예외 항목 탐지는 테이블의 첫 번째 지표 열에서만 자동 실행됩니다. 필요한 경우 다른 열에서 [!UICONTROL 예외 항목 탐지]를 실행하도록 열 설정을 구성할 수 있습니다. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
