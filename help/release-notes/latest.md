---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f961bf0a615199de931a98f14d8b640890df7a2b
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 66%

---

# 현재 Customer Journey Analytics(CJA) 릴리스 노트(2022년 9월)

**마지막 업데이트**: 2022년 9월 9일

>[!NOTE]
>
>이 페이지에는 출시 전 콘텐츠가 포함되어 있으며 변경될 수 있습니다.

## 관련 리소스

* [2022년 이전 CJA 릴리스 노트](/help/release-notes/2022.md)

* [년 Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=kr)

* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=kr)

* [Adobe Experience Cloud 릴리스 노트](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko)

## 주요 기능

| 기능 | 설명 | [목표 날짜](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Analytics 소스 커넥터에 대한 교차 영역 지원** | 이제 모든 지역(미국, 영국 또는 싱가포르)에서 보고서 세트를 수집할 수 있습니다. 단, 이러한 보고서 세트는 소스 연결이 생성되는 Experience Platform Sandbox 인스턴스와 동일한 조직에 매핑되어야 합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko-kr) | 2022년 8월 24일 |
| **첫 번째 세션 보고** | 특정 세션이 사용자의 첫 번째 세션인지 알아봅니다. [자세히 알아보기](/help/data-views/data-views-usecases.md) | 2022년 8월 24일 |
| **CJA용 실험 패널** | 이 새로운 작업 공간 패널을 사용하면 CJA 사용자가 온라인, 오프라인, Adobe 솔루션, Adobe Journey Optimizer 및 BYO(Bring-your-Own) 데이터에서 모든 소스 - 온라인, 오프라인에서 모든 A/B 실험의 향상도와 신뢰도를 평가할 수 있습니다. [자세히 알아보기](/help/analysis-workspace/c-panels/experimentation.md) | [제한된 릴리스](/help/release-notes/releases.md) 2022년 9월 14일부터 |
| **작업 공간의 콤보 차트 시각화** | 콤보 차트를 사용하면 Workspace 내에서 지표를 보다 쉽고 직관적으로 비교할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/combo-charts.html?lang=en) | 2022년 9월 14일 |

{style=&quot;table-layout:auto&quot;}

## 수정 사항

AN-298412

## CJA 관리자를 위한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **개선된 IP-to-geolocation 매핑** | 2022년 9월 9일 | Adobe의 IP 조회 공급업체인 Digital Element는 IP-to-geolocation 매핑을 위해 새롭게 개선된 데이터 세트(NetAcuity Pulse)로 업그레이드하고 있습니다. Adobe Analytics에서 이 새 데이터 세트를 채택합니다 **2022년 10월 5일**. 새 데이터베이스는 이전 버전보다 더 정확합니다. 새 데이터베이스가 채택되면 일부 IP-to-geo 매핑이 변경 및 개선됩니다.<p> Analytics Source Connector를 통해 제공되는 CJA 데이터도 자동으로 새 매핑을 활용합니다. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
