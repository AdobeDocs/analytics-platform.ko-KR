---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 21bcc23b37372fc96347228b8b40fa970bb09bb5
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 92%

---

# 현재 Adobe Customer Journey Analytics 릴리스 정보 (2023년 8월)

**최근 업데이트**: 2023년 8월 9일

이 릴리스 정보는 2023년 8월 9일부터 9월 13일까지의 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Report Builder 개선 사항** | <ul><li>통합 문서 탭에서 예약된 작업을 다운로드한 다음 제목을 지정하고 저장하고 공유할 수 있습니다. [자세히 알아보기](/help/report-builder/schedule-reportbuilder.md)</li><li>차원으로 시작 날짜를 사용하면 데이터 블록의 시작 날짜를 데이터 블록 출력에 차원으로 표시할 수 있습니다. [자세히 알아보기](/help/report-builder/create-a-data-block.md) </li></ul> | 해당 사항 없음 | 2023년 8월 17일 |
| **통화 전환** | 고객 여정에서 여러 통화를 지원하는 기능이 추가되고 있습니다. 데이터 보기 설정에서 통화를 다른 통화로 변환할 수 있습니다. [자세히 알아보기](/help/data-views/component-settings/format.md) | 해당 사항 없음 | 2023년 8월 31일 |
| **Analytics 소스 커넥터에서 A4T 분류 지원** | Adobe Target 활동 및 경험 이벤트에 대한 분류 데이터를 쉽게 결합하기 위해 상관 관계 ID를 추가하고 있습니다. | 해당 사항 없음 | 2023년 8월 31일 |
| **보고 활동 관리자** | 각 연결에 대한 보고 사용량에 대해 세부적인 가시성을 제공하여 관리자가 최대 보고 시간 동안 용량 문제를 쉽게 진단한 후 해결할 수 있도록 지원합니다. | 해당 사항 없음 | 2023년 9월 6일 |
| **Customer Journey Analytics 데이터 보기에 대한 PowerBI 및 Tableau 액세스** | Adobe Customer Journey Analytics SQL 커넥터를 통해 SQL은 Customer Journey Analytics에서 정의한 데이터 보기에 액세스할 수 있습니다. Power BI, Tableau 또는 기타 비즈니스 인텔리전스와 시각화 도구에 익숙한 데이터 엔지니어 및 분석가는 이제 Customer Journey Analytics 사용자가 Analysis Workspace 프로젝트에 사용하는 동일한 데이터 보기를 기반으로 보고서와 대시보드를 만들 수 있습니다. [자세히 알아보기](/help/data-views/sql-connector.md) | 해당 사항 없음 | 2023년 9월 13일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-309141; AN-319198; AN-324576; AN-324939; AN-325138; AN-325554

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **Customer Journey Analytics에서 데이터를 처리하는 방법 변경** | 2023년 6월 22일 | 최근 Customer Journey Analytics에서 데이터를 처리하는 방법이 변경되었습니다.<ul><li>타임스탬프가 24시간 미만인 모든 이벤트 데이터가 스트리밍됩니다.</li><li>타임스탬프가 24시간 이상 지난 모든 이벤트 데이터(최신 데이터와 동일한 배치에 있는 경우 포함)는 채우기로 간주되며 낮은 우선 순위로 수집됩니다.</li></ul> |

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
