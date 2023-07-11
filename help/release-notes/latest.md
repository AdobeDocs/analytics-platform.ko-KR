---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e9d2bfb4f4c4aa3ac96d0300e537376a1ef7821a
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 39%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2023년 7월)

**마지막 업데이트**: 2023년 7월 10일

Adobe Customer Journey Analytics 릴리스는 [연속 게재 모델](releases.md) 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | 제품 팀이 더 많은 데이터 중심의 제품 결정을 내릴 수 있도록 데이터 요구 사항을 신속하게 자체 제공할 수 있는 새로운 프로젝트 유형입니다. Customer Journey Analytics의 기존 연결 및 데이터 보기 워크플로 위에 구축됩니다. 구현 또는 구성 변경이 필요하지 않습니다. [자세히 알아보기](/help/guided-analysis/overview.md)<p>Product Analytics은 Customer Journey Analytics에 대한 유료 추가 기능입니다. 조직에서 이 기능을 사용하도록 프로비저닝하려면 Adobe 계정 팀에 문의하십시오. | 해당 사항 없음 | 2023년 7월 17일 |
| **파생 필드** | 이는 파생 필드의 초기 릴리스를 나타냅니다. 파생 필드를 사용하면 사용자 정의 가능한 규칙 빌더를 통해 즉석에서 (종종 복잡한) 데이터 조작을 정의할 수 있습니다. 또한 데이터 보기에서 파생 필드를 구성 요소(지표 또는 차원)로 정의한 다음 Workspace에서 파생 필드를 구성 요소로 사용할 수 있습니다.<p>이 릴리스는 마케팅 채널 템플릿과 다음 기능을 지원합니다.</p><ul><li>연결</li><li>다음과 같은 경우</li><li>찾기 및 바꾸기</li><li>조회</li><li>URL 구문 분석</li></ul> <p>[자세히 알아보기](/help/data-views/derived-fields/derived-fields.md)</p> | 2023년 5월 10일 | 2023년 8월 2일 |
| **프로필 및 조회 데이터에 대한 확장된 조회 지원** | 데이터 세트를 프로필 또는 조회 데이터 세트 내의 필드 조회로 추가하는 기능을 제공합니다. 이전에는 이벤트 데이터 세트만 지원되었습니다. [자세히 알아보기] | 2023년 6월 21일 | 2023년 7월 12일 |
| **Report Builder 개선 사항** | <ul><li>셀에서 여러 데이터 블록을 필터링합니다. 셀의 여러 데이터 블록에 대한 필터를 변경할 수 있습니다. 미리 정의된 셀을 사용하여 여러 데이터 블록에 할당하고 셀에 정의된 필터를 기반으로 데이터를 업데이트합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>행 및 열 머리글을 표시하거나 숨깁니다. 데이터 블록 표 머리글이나 행 및 열 머리글을 표시하거나 숨겨 표의 서식을 다시 지정하고 보고서의 데이터 블록을 정렬할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul> | 해당 사항 없음 | 2023년 7월 19일 |
| **Experience Edge 지역 조회** | Adobe Experience Edge는 모든 Experience Edge 사용자(Adobe Analytics, Customer Journey Analytics, Adobe Target, Adobe Medium Analytics, Adobe Experience Platform 등)에게 통합 지리 데이터를 제공하는 지역 조회 서비스를 추가하고 있습니다. | 해당 사항 없음 | 2023년 7월 26일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-317971; AN-319234; AN-320439; AN-320519; AN-321740; AN-322444; AN-323116

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **Customer Journey Analytics의 데이터 처리 방법 변경** | 2023년 6월 22일 | 최근에 Customer Journey Analytics에서 데이터를 처리하는 방법이 변경되었습니다.<ul><li>타임스탬프가 24시간 미만인 모든 이벤트 데이터가 스트리밍됩니다.</li><li>타임스탬프가 24시간 이상 지난 모든 이벤트 데이터(최신 데이터와 동일한 배치에 있는 경우에도)는 채우기로 간주되고 우선 순위가 낮은 상태로 수집됩니다.</li></ul> |

{style="table-layout:auto"}

## 서비스 종료(EOL) 알림

| EOL 제품 또는 기능 | 추가 또는 업데이트 일자 | 설명 |
| --- | --- | --- |
| **Adobe I/O OAuth 서버 간 자격 증명으로 마이그레이션** | 2023년 5월 11일 | AdobeIO JWT 자격 증명을 사용하는 Adobe Analytics API, Customer Journey Analytics API 및 라이브스트림 고객은 다음을 통해 AdobeIO OAuth 서버 간 자격 증명으로 마이그레이션해야 합니다. **2025년 1월 1일**. 2024년 5월 1일부터는 Adobe I/O를 사용하여 새 JWT 자격 증명을 만들 수 없습니다. JWT를 사용하는 고객은 OAuth 서버 간 자격 증명을 새로 만들거나 기존 JWT 자격 증명을 OAuth 서버 간 자격 증명으로 마이그레이션해야 합니다. 또한 고객은 새 OAuth 서버 간 자격 증명을 사용하려면 클라이언트 애플리케이션을 업데이트해야 합니다. <ul><li>[서비스 계정(JWT) 자격 증명에서 마이그레이션](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[새 OAuth 서버 간 자격 증명 사용](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## 관련 리소스

* [2023년 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2023.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
