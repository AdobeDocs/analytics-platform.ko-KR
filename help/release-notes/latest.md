---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 2579a6bbf17836fdab519b01e09f253bfb3a7aeb
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 41%

---

# 현재 Customer Journey Analytics(CJA) 릴리스 노트(2023년 1월)

**마지막 업데이트**: 2023년 1월 13일

Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 제공 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 주요 기능 및 업데이트

| 기능 | 설명 | [롤아웃 시작](/help/release-notes/releases.md) | [일반 가용성](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Workspace의 폴더** | 폴더를 사용하면 보다 효과적으로 검색 및 액세스할 수 있도록 프로젝트를 구성하고 분류할 수 있습니다. 또한 공유 **[!UICONTROL 회사]** 폴더를 사용하면 관리자가 모든 Workspace 사용자와 컨텐츠를 쉽게 만들고 공유할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html) | 해당 사항 없음 | 2023년 1월 11일 |
| **기본 랜딩 페이지** | 다음 [새 랜딩 페이지](/help/getting-started/landing.md) 2022년 초에 도입된 새로운 기능은 **2023년 1월 11일**. 기존 랜딩 페이지는 더 이상 사용되지 않으며 모든 사용자가 새 경험을 사용해야 합니다. | 해당 사항 없음 | 2023년 1월 11일 |
| **프로젝트 관리자 페이지가 더 이상 사용되지 않음** | 새 랜딩 페이지가 릴리스되면 더 이상 **[!UICONTROL 프로젝트 관리자]** 아래에 나열된 **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 구성 요소]**. 새 랜딩 페이지에는 이전 프로젝트 관리자 페이지의 모든 기능 등이 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#deprecate-pm-page) | 해당 사항 없음 | 2023년 1월 11일 |
| **Report Builder의 통합 문서 예약** | Customer Journey Analytics에서 일정 간격으로 통합 문서를 전송하는 일정을 만들 수 있습니다. 이제 수신자는 정기적으로 통합 문서에 대한 최신 업데이트를 받을 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html) | 해당 사항 없음 | 2023년 1월 11일 |
| **새 프로젝트 자동 저장** | 이제 Analysis Workspace에서 새로 만든 프로젝트를 자동으로 저장합니다. 어떤 이유로든 새로 만든 프로젝트에 수동으로 저장하기 전에 예기치 않게 액세스할 수 없는 경우 이제 프로젝트의 복구 버전을 사용할 수 있습니다. 이전에는 프로젝트를 수동으로 저장한 후에만 프로젝트가 자동으로 저장되었습니다. [자세히 알아보기](/help/analysis-workspace/build-workspace-project/save-projects.md) | 해당 사항 없음 | 2023년 1월 11일 |
| **향상된 사용자 환경 설정** | 이제 사용자 수준( [!UICONTROL 구성 요소] > [!UICONTROL 기본 설정]). 사용자 환경 설정을 지정하면 선택 사항이 프로젝트, 테이블 및 시각화에 걸쳐 확장됩니다. 이제 환경 설정 페이지에는 다음과 같은 새 탭이 있습니다. 각 탭에는 다음과 같은 새 구성 옵션이 있습니다.<ul><li>자유 형식 테이블</li><li>시각화>/li></ul>. 또한 이제 더 많은 환경 설정을 **[!UICONTROL 일반]** 및 **[!UICONTROL 프로젝트]** 탭.<p>이전에는 이러한 환경 설정 중 다수는 개별 프로젝트, 표 및 시각화에 대해서만 구성할 수 있었습니다. [자세히 알아보기](/help/analysis-workspace/user-preferences.md) | 해당 사항 없음 | 2023년 1월 11일 |

{style=&quot;table-layout:auto&quot;}

## 수정 사항

AN-287349; AN-301684; AN-305491; AN-305769; AN-307912

## CJA 관리자를 위한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **개선된 IP-to-geolocation 매핑** | 2022년 9월 29일 | Adobe의 IP 조회 공급업체인 Digital Element는 IP-to-geolocation 매핑을 위해 새롭게 개선된 데이터 세트(NetAcuity Pulse)로 업그레이드하고 있습니다. Adobe Analytics은 이 새 데이터 집합의 채택을 연기했습니다. **2023년 1월 11일**. 새 데이터베이스는 이전 버전보다 더 정확합니다. 새 데이터베이스가 채택되면 일부 IP-to-geo 매핑이 변경 및 개선됩니다.<p> [!UICONTROL Analytics Source Connector]를 통해 제공되는 CJA 데이터도 자동으로 새 매핑을 활용합니다. |

{style=&quot;table-layout:auto&quot;}


## 관련 리소스

* [2022년 이전 CJA 릴리스 정보](/help/release-notes/2022.md)

* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko-KR)

* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ko-KR)

* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko-KR)

* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
