---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 6e94dcf003c26af5ce32544655477b1074b504b5
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 58%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2023년 9월)

**마지막 업데이트**: 2023년 9월 7일

이 릴리스 정보는 2023년 9월 13일부터 2023년 10월 3일까지의 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics 소스 커넥터에서 A4T 분류 지원** | 신규 지원 `correlationID` Adobe Analytics용 필드 | 다음 `_experience.decisioning.propositions.scopeDetails.correlationID` 이제 Adobe Analytics 소스 커넥터 스키마에서 필드를 사용할 수 있습니다. 이 필드는 A4T 분류 지원에 사용되며 2023년 9월부터 채워집니다. | | 해당 사항 없음 | 2023년 9월 12일 |
| **파생 필드에 대한 업데이트** | 파생 필드 기능에 대한 업데이트는 다음과 같습니다.<ul><li>다음 [!UICONTROL 조회] 함수 이름이 (으)로 변경되었습니다. [!UICONTROL 분류]CSV 데이터를 로드하는 추가 옵션이 있는 . **(2023년 9월 27일 릴리스)**</li><li>파생 필드를 정의할 때 추가 함수를 사용할 수 있습니다. [!UICONTROL 트림], [!UICONTROL 소문자] 및 [!UICONTROL 조회].</li><li>파생 필드 정의는 이제 의 필드도 지원합니다. [!UICONTROL 조회] 및 [!UICONTROL 프로필] 데이터 세트.</li></ul>[자세히 알아보기](/help/data-views/derived-fields/derived-fields.md) | 해당 사항 없음 | 2023년 9월 13일 |
| **Adobe Product Analytics의 새로운 기능** | <ul><li>**예외 항목 탐지**: 이벤트를 기록 트렌드에서 파생된 예상 값과 비교합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/usage.html)</li><li>**사용 빈도 보기 트렌드**: 사용 빈도별로 기능 채택을 측정합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html)</li><li>**사용자 환경 설정**: 색상 팔레트 및 숫자 포맷과 같은 다양한 사용자 환경 설정을 구성합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html)</li></ul> | 해당 사항 없음 | 2023년 9월 18일 |
| **Experience Edge 장치 조회** | Experience Platform 에지 네트워크를 통해 자동 장치 유형 데이터 수집을 활성화합니다. 이 Experience Edge 서비스는 다른 Experience Platform 앱과 함께 Customer Journey Analytics에 이점을 제공합니다. (참조할 설명서 링크) | 해당 사항 없음 | 2023년 9월 27일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-310972; AN-319509; AN-322245; AN-323411; AN-323719; AN-326101; AN-326125; AN-326888


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
