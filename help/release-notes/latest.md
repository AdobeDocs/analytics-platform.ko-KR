---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0fdf95906e17b9e90fa6ba652aa8e53f695279a4
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 76%

---

# 현재 CJA(Customer Journey Analytics) 릴리스 정보 (2023년 5월)

**마지막 업데이트**: 2023년 5월 31일

Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 주요 기능 및 업데이트

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer 데이터 보기** | CJA 관리자는 &quot;AJO 데이터 보기(Sandbox-name)&quot;라는 제목의 CJA의 일부 추가 데이터 보기에 액세스할 수 있습니다. 이러한 데이터 보기는 Adobe Journey Optimizer(AJO)의 보고서를 향상시키는 데 사용됩니다. 또한 CJA에서 AJO 활동을 더 깊이 분석하는 데 사용할 수도 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html) |  | 2023년 5월 25일 |
| **비프로덕션 샌드박스용 채우기** | 비프로덕션 샌드박스에서 Analytics 소스 커넥터 데이터 흐름을 생성할 때 비프로덕션 샌드박스의 채우기는 3개월로 제한됩니다. 프로덕션 샌드박스의 경우 13개월로 유지됩니다. | 해당 사항 없음 | 2023년 4월 26일 |
| **프로젝트 링크 공유 (로그인 불필요)** | 이제 Adobe Analytics에 액세스할 수 없는 사용자에게 Analysis Workspace 프로젝트에 대한 읽기 전용 링크를 공유할 수 있습니다. 여기에는 조직 외부의 사용자 또는 Adobe Analytics용으로 프로비저닝되지 않은 조직 내의 사용자와의 공유가 포함됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>이 기능은 기본적으로 활성화되어 있으며 시스템 관리자가 비활성화할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 2023년 5월 3일 | 2023년 6월 5일 |
| **Analytics 대시보드 앱(모바일 앱)에 대한 홈 화면 업데이트** | 새롭게 업데이트된 홈 화면에서는 모든 스코어카드를 하나의 통합된 스코어카드 목록에서 볼 수 있습니다. 한 번의 로그인으로 두 개 이상의 조직에 액세스할 수 있는 경우, 조직의 모든 스코어카드를 단일 목록에서 사용할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | 해당 사항 없음 | 2023년 5월 10일 |
| **파생 필드** | 이는 파생 필드의 초기 릴리스를 나타냅니다. 파생 필드를 사용하면 사용자 정의 가능한 규칙 빌더를 통해 즉석에서 (종종 복잡한) 데이터 조작을 정의할 수 있습니다. 데이터 보기에서 파생 필드를 구성 요소(지표 또는 차원)로 추가 정의한 다음 파생 필드를 작업 영역에서 구성 요소로 사용할 수 있습니다.<p>이 릴리스는 마케팅 채널 템플릿과 다음 기능을 지원합니다.</p><ul><li>연결</li><li>다음과 같은 경우</li><li>찾기 및 바꾸기</li><li>조회</li><li>URL 구문 분석</li></ul> <p>[자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 2023년 5월 10일 | 2023년 8월 2일 |
| **CJA용 Report Builder - 셀에서 데이터 보기 선택** | 이 기능을 사용하면 사용자가 셀에서 데이터 블록에 대한 데이터 보기를 선택할 수 있습니다. 이는 통합 문서를 만들고 데이터 구성이 유사한 여러 데이터 보기가 있고 서로 다른 데이터 보기에서 통합 문서를 여러 번 재사용하려는 경우에 유용합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 해당 사항 없음 | 2023년 5월 24일 |
| **Analysis Workspace의 구성 요소 정렬** | <p>이제 왼쪽 레일 또는 Analysis Workspace의 데이터 사전에서 구성 요소를 볼 때 새로운 정렬 옵션을 사용할 수 있습니다. 권장(가장 일반적으로 사용되는 구성 요소), 알파벳순 또는 범주(유형)별로 구성 요소를 정렬할 수 있습니다.</p><p>이전에는 구성 요소만 검색하거나 필터링만 할 수 있었습니다. [자세히 알아보기](/help/components/overview.md)</p> | 해당 사항 없음 | TBD |
| **자유 형식 테이블에서 동적 차원이 포함된 행 삭제** | 이제 Analysis Workspace의 자유 형식 테이블에서 x 아이콘을 사용하여 동적 차원이 포함된 특정 행을 신속하게 삭제할 수 있습니다. 이렇게 하면 &quot;항상 항목 제외&quot; 필터 규칙이 자동으로 적용됩니다.<p>이전에는 동적 차원이 포함된 행을 삭제하는 유일한 방법은 필터 대화 상자에서 수동으로 규칙을 만드는 것이었습니다. [자세히 알아보기](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 해당 사항 없음 | 2023년 5월 17일 |
| **패널 내에 시각화를 추가하는 새 버튼** | 이제 Analysis Workspace의 각 패널 하단에 새로운 버튼이 추가되어 시각화를 빠르게 추가할 수 있습니다. <p>이전에는 패널에 시각화를 추가하는 유일한 방법은 왼쪽 레일에서 시각화를 드래그하거나, 기존 시각화를 복제 또는 복사하거나, 빈 패널을 만드는 것이었습니다. [자세히 알아보기](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 해당 사항 없음 | 2023년 5월 17일 |
| **딥 링크 (모바일 앱)** | 사용자가 앱의 스코어카드 프로젝트로 바로 연결되는 스코어카드 링크를 보낼 수 있습니다. 이를 통해 프로젝트를 보다 쉽게 공유하고 기술 수준이 낮은 대상자의 참여를 높일 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) | 해당 사항 없음 | 2023년 5월 17일 |
| **지능형 캡션** | 의 자연어 요약으로 사용자를 위한 스토리텔링 강화 [!UICONTROL 라인] 시각화. [자세히 알아보기](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023년 5월 17일 | 2023년 6월 1일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-316412; AN-317105; AN-318122; AN-317353

## CJA 관리자를 위한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 | 해당 사항 없음 | 해당 사항 없음 |

## 서비스 종료(EOL) 알림 {#eol}

| EOL 제품 또는 기능 | 추가 또는 업데이트 일자 | 설명 |
| --- | --- | --- |
| **AdobeIO OAuth 서버 간 자격 증명으로 마이그레이션** | 2023년 5월 11일 | AdobeIO JWT 자격 증명을 사용하는 Adobe Analytics API, CJA API 및 라이브스트림 고객은 다음을 통해 AdobeIO OAuth 서버 간 자격 증명으로 마이그레이션해야 합니다. **2025년 1월 1일**. AdobeIO에서는 2024년 5월 1일부터 새 JWT 자격 증명을 만들 수 없습니다. JWT를 사용하는 고객은 새 OAuth 서버 간 자격 증명을 만들거나 기존 JWT 자격 증명을 OAuth 서버 간 자격 증명으로 마이그레이션해야 합니다. 또한 고객은 새 OAuth 서버 간 자격 증명을 사용하도록 클라이언트 애플리케이션을 업데이트해야 합니다. <ul><li>[서비스 계정(JWT) 자격 증명에서 마이그레이션](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[새 OAuth 서버 간 자격 증명 사용](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[FAQ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |

{style="table-layout:auto"}

## 관련 리소스

* [2023년 이전 CJA 릴리스 정보](/help/release-notes/2023.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=en)
* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
