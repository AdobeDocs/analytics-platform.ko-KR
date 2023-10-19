---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 328b95efb7ed9ff597b95979ecdeceaa8db92bb4
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 97%

---

# 현재 Adobe Customer Journey Analytics 릴리스 정보 (2023년 10월)

**마지막 업데이트**: 2023년 10월 19일

이번 릴리스 정보에는 2023년 10월 4일부터 2023년 10월 24일까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **조회 및 프로필 데이터 세트에 대한 행 수 지표** | 이러한 지표는 이전에는 이벤트 데이터 세트에만 사용할 수 있었습니다. | 2023년 10월 16일 |
| **클라우드로 전체 테이블 내보내기** | Customer Journey Analytics 전체 테이블 내보내기를 사용하면 수백만 개의 Workspace 행을 클라우드 대상으로 내보낼 수 있습니다. <p>전체 테이블 내보내기 기능은 연결된 테이블에서 최대 5개의 분류, 5개의 지표, 필터 및 계산된 지표를 모두 지원하며 Workspace 내에서 디자인된 데이터 테이블을 일회성 또는 예약된 게재로 제공합니다. 이는 현재 Data Warehouse에서 사용할 수 없지만 자주 요청되는 새로운 기능을 다수 포함하는 Adobe Analytics의 Data Warehouse 보고서에 대한 개선 사항입니다.</p><p> 클라우드 내보내기 옵션에는 다음과 같은 사항이 포함됩니다.</p><ul><li>Adobe Experience Platform 데이터 랜딩 영역</li><li>Amazon S3 Role ARN</li><li>Google Cloud 플랫폼</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>자세한 내용은 [클라우드로 Customer Journey Analytics 보고서 내보내기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html)를 참조하십시오. | 2023년 10월 4일 | 2023년 10월 19일 |
| **구성 요소 관리 시 새로운 열 사용 가능** | 이제 구성 요소 관리 시 [계산된 지표 관리자](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html) 및 [필터 관리자](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html) 에서 새로운 열을 사용할 수 있습니다.<ul><li>다음에서 사용</li><li>마지막 사용</li></ul>이 정보는 구성 요소가 조직의 사용자에게 유용한지, 어디에서 사용되는지, 삭제 또는 수정이 필요한지를 결정하는 데 도움이 됩니다. 이 정보와 함께 데이터 사전을 사용하면 조직에서 구성 요소가 사용되는 방식을 지속적으로 추적하고 보다 명확하게 파악할 수 있습니다. | 2023년 9월 23일 | 2023년 10월 4일 |
| **Adobe Analytics 프로젝트 및 포함된 모든 구성 요소를 Customer Journey Analytics로 마이그레이션** | 이제 Adobe Analytics 프로젝트를 Customer Journey Analytics로 마이그레이션할 수 있습니다. 이 프로세스는 Adobe Analytics에서 Customer Journey Analytics로의 전환을 간소화합니다. <p>프로젝트를 Customer Journey Analytics로 마이그레이션하면 자산이 Adobe Analytics 보고서 세트에서 Customer Journey Analytics 데이터 보기로 매핑됩니다.</p> <p>Adobe Analytics 인터페이스에서 Customer Journey Analytics로 프로젝트를 마이그레이션합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)</p> | 해당 사항 없음 | 2023년 10월 9일 |
| **Adobe Product Analytics: 시리즈 표시/숨기기** | 시각화에서 시리즈의 가시성을 제어하려면 차트 범례 또는 테이블 행을 클릭하십시오. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=ko) | 해당 사항 없음 | 2023년 10월 4일 |
| **Adobe Product Analytics의 주석** | 이제 안내식 분석이 Customer Journey Analytics에서 생성된 주석을 조회하는 기능을 지원합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=ko) | 해당 사항 없음 | 2023년 10월 4일 |
| **보고 활동 관리자** | 보고 활동 관리자를 사용하면 조직에서의 각 연결에 대한 보고 용량을 확인할 수 있습니다. 이는 관리자에게 보고 사용량에 대해 상세한 가시성을 제공하며 최대 보고 시간 동안 발생할 수 있는 용량 문제를 쉽게 진단하고 해결할 수 있도록 해 줍니다. 보고 활동 관리자의 주요 기능은 다음과 같습니다.<ul><li>현재 보고 요청 취소 (안내식 분석 및 전체 테이블 내보내기 요청 포함)</li><li>정의된 기간 동안 후속 요청 제한</li></ul>현재 요청을 취소하는 것 외에도 관리자는 이제 정의된 기간 동안 요청을 제한할 수 있습니다. 관리자는 요청, 프로젝트 또는 사용자별로 요청을 제한할 수 있습니다. [자세히 알아보기](/help/reporting-activity-manager/reporting-activity-overview.md) | 2023년 10월 17일 | 2023년 10월 24일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-325940; AN-326468; AN-328301; AN-328640; AN-329370

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 | 해당 사항 없음 | 해당 사항 없음 |

{style="table-layout:auto"}

## 서비스 종료(EOL) 알림

| EOL 제품 또는 기능 | 추가 또는 업데이트 일자 | 설명 |
| --- | --- | --- |
| **Adobe I/O OAuth 서버 간 자격 증명으로 마이그레이션** | 2023년 5월 11일 | Adobe I/O JWT 자격 증명을 사용하는 Adobe Analytics API, Customer Journey Analytics API 및 Livestream 고객은 **2025년 1월 1일**&#x200B;까지 Adobe I/O OAuth 서버 간 자격 증명으로 마이그레이션해야 합니다. 2024년 5월 1일부터는 Adobe I/O를 사용하여 새 JWT 자격 증명을 만들 수 없습니다. JWT를 사용하는 고객은 OAuth 서버 간 자격 증명을 새로 만들거나 기존 JWT 자격 증명을 OAuth 서버 간 자격 증명으로 마이그레이션해야 합니다. 또한 고객은 새 OAuth 서버 간 자격 증명을 사용하려면 클라이언트 애플리케이션을 업데이트해야 합니다. <ul><li>[서비스 계정(JWT) 자격 증명에서 마이그레이션](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[새 OAuth 서버 간 자격 증명 사용](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## 관련 리소스

* [2023년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2023.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko)
* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
