---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e6b2df9ae90ef5663206e768b985749de38e263c
workflow-type: ht
source-wordcount: '691'
ht-degree: 100%

---

# 현재 Adobe Customer Journey Analytics 릴리스 정보 (2023년 7월)

**마지막 업데이트**: 2023년 7월 25일

Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics는 Customer Journey Analytics에서 교차 채널 데이터 및 인사이트와 상호 작용하는 새로운 방법입니다. 이러한 새로운 기능을 통해 제품 팀은 안내 분석 워크플로를 통해 제품 경험에 대한 데이터 및 인사이트를 자체 관리할 수 있습니다. 팀에서 수행할 수 있는 작업:<ul><li>시간 경과에 따른 사용자 참여 패턴 이해&#x200B;</li><li>제품 사용자 기반의 성장 및 유지 추적&#x200B;</li><li>제품의 마찰 영역 식별</li><li>기능 릴리스 및 최초 사용의 &#x200B; 영향 측정</li><li>제품을 사용하는 여정 동안 참여하고 육성할 의미 있는 사용자 세그먼트 탐색&#x200B;</li><li>분석가와의 심층 분석 및 공동 작업을 위해 Analysis Workspace와 연결</li></ul>Adobe Product Analytics는 Customer Journey Analytics의 유료 추가 기능입니다. 조직에서 이 기능을 사용하도록 프로비저닝하려면 Adobe 계정 팀에 문의하십시오. [자세히 알아보기](/help/guided-analysis/overview.md) | 해당 사항 없음 | 2023년 7월 17일 |
| **파생 필드** | 이는 파생 필드의 초기 릴리스를 나타냅니다. 파생 필드를 사용하면 사용자 정의 가능한 규칙 빌더를 통해 즉석에서 (종종 복잡한) 데이터 조작을 정의할 수 있습니다. 데이터 보기에서 파생 필드를 구성 요소(지표 또는 차원)로 추가 정의한 다음 파생 필드를 작업 영역에서 구성 요소로 사용할 수 있습니다.<p>이 릴리스는 마케팅 채널 템플릿과 다음 기능을 지원합니다.</p><ul><li>연결</li><li>다음과 같은 경우</li><li>찾기 및 바꾸기</li><li>조회</li><li>URL 구문 분석</li></ul> <p>[자세히 알아보기](/help/data-views/derived-fields/derived-fields.md)</p> | 2023년 5월 10일 | 2023년 8월 2일 |
| **프로필 및 조회 데이터에 대한 조회 지원이 확장됨** | 프로필 또는 조회 데이터 세트 내의 필드 조회로 데이터 세트를 추가하는 기능을 제공합니다. 이전에는 이벤트 데이터 세트만 지원되었습니다. [자세히 알아보기](/help/connections/create-connection.md) | 2023년 6월 21일 | 2023년 7월 12일 |
| **Report Builder 개선 사항** | <ul><li>여러 데이터 블록에 대해 셀에서 필터링합니다. 셀에서 여러 데이터 블록에 대한 필터를 변경할 수 있습니다. 미리 정의된 셀을 사용하여 여러 데이터 블록에 할당하고 셀에 정의된 필터를 기반으로 데이터를 업데이트합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=ko)</li><li>행 및 열 헤더를 표시하거나 숨깁니다. 데이터 블록 테이블 헤더 또는 행 및 열 헤더를 표시하거나 숨겨 보고서의 테이블 형식을 다시 지정하고 데이터 블록을 정렬할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=ko#build-the-data-block)</li></ul> | 해당 사항 없음 | 2023년 7월 19일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-317971, AN-319234, AN-320439, AN-320519, AN-321740, AN-322444, AN-323116

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
