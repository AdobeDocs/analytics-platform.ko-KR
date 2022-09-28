---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d2aec8976d7d81c28a6b9b76c58fec0fc2c3b360
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 최신 CJA(Customer Journey Analytics) 릴리스 정보 (2022년 9월)

**마지막 업데이트**: 2022년 9월 14일

Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 제공 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이러한 릴리스 정보를 정기적으로 확인하십시오.

## 관련 리소스

* [2022년 이전 CJA 릴리스 정보](/help/release-notes/2022.md)

* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko)

* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## 주요 기능

| 기능 | 설명 | [목표 날짜](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Analytics 소스 커넥터에 대한 교차 영역 지원** | 이제 모든 지역(미국, 영국 또는 싱가포르)에서 보고서 세트를 수집할 수 있습니다. 단, 이러한 보고서 세트는 소스 연결이 생성되는 Experience Platform Sandbox 인스턴스와 동일한 조직에 매핑되어야 합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) | 2022년 8월 24일 |
| **첫 번째 세션 보고** | 특정 세션이 사용자의 첫 번째 세션인지 확인합니다. [자세히 알아보기](/help/data-views/data-views-usecases.md) | 2022년 8월 24일 |
| **CJA 실험 패널** | 이 새로운 작업 영역 패널을 통해 CJA 사용자는 온라인, 오프라인, Adobe 솔루션, Adobe Journey Optimizer 및 BYO(Bring Your Own) 데이터 등 모든 소스에서 A/B 실험의 상승도와 신뢰도를 평가할 수 있습니다. [자세히 알아보기](/help/analysis-workspace/c-panels/experimentation.md) | [제한된 릴리스](/help/release-notes/releases.md)(2022년 9월 14월부터 시작) |
| **작업 영역의 콤보 차트 시각화** | 콤보 차트를 사용하면 작업 영역 내에서 서로 다른 지표를 더욱 쉽고 직관적으로 비교할 수 있습니다. [자세히 알아보기](/help/analysis-workspace/visualizations/combo-charts.md) | 2022년 9월 14일 |
| **데이터 거버넌스 레이블 및 정책에 대한 CJA 지원** | CJA와 Adobe Experience Platform 개인정보 보호 레이블 및 정책 간의 통합을 자동화합니다. 플랫폼에서 사용하는 데이터 세트에서 생성된 데이터 레이블은 중요한 필드에서 지표 및/또는 차원을 생성하는 사용자를 중단 또는 경고하기 위해 CJA 데이터 보기에 표시됩니다. 또한 데이터를 CJA에서 내보낼 경우(Workspace 또는 Report Builder 보고, 내보내기, API 등을 통해) 보고서에 특정 방법으로 처리해야 하는 기밀 정보가 포함되어 있음을 사용자에게 통지하기 위해 경고 또는 레이블이 추가됩니다. [자세히 알아보기](/help/data-views/data-governance.md) | 2022년 9월 14일 |

{style=&quot;table-layout:auto&quot;}

## 수정 사항

AN-298412

## CJA 관리자를 위한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **개선된 IP-to-geolocation 매핑** | 2022년 9월 9일 | Adobe의 IP 조회 공급업체인 Digital Element는 IP-to-geolocation 매핑을 위해 새롭게 개선된 데이터 세트(NetAcuity Pulse)로 업그레이드하고 있습니다. Adobe Analytics는 **2022년 10월 5일**&#x200B;에 이 새로운 데이터 세트를 채택할 예정입니다. 새 데이터베이스는 이전 버전보다 더 정확합니다. 새 데이터베이스가 채택되면 일부 IP-to-geo 매핑이 변경 및 개선됩니다.<p> Analytics Source Connector를 통해 제공되는 CJA 데이터도 자동으로 새 매핑을 활용합니다. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
