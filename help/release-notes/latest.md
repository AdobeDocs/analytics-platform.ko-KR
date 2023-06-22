---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 68041d22c55d46d740307f2ad2b0cefa249a7e96
workflow-type: tm+mt
source-wordcount: '1426'
ht-degree: 69%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2023년 6월)

**마지막 업데이트**: 2023년 6월 22일

Adobe Customer Journey Analytics 릴리스는 [연속 게재 모델](releases.md) 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 릴리스 하이라이트 {#highlights}

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **지능형 캡션** | [!UICONTROL 라인] 시각화의 자연어 요약으로 사용자를 위한 스토리텔링을 풍부하게 합니다. [자세히 알아보기](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023년 5월 17일 | 2023년 6월 1일 |
| **프로젝트 링크 공유 (로그인 불필요)** | 이제 Adobe Analytics에 액세스할 수 없는 사용자에게 Analysis Workspace 프로젝트에 대한 읽기 전용 링크를 공유할 수 있습니다. 여기에는 조직 외부의 사용자 또는 Adobe Analytics용으로 프로비저닝되지 않은 조직 내의 사용자와의 공유가 포함됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>이 기능은 기본적으로 활성화되어 있으며 시스템 관리자가 비활성화할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023년 5월 3일 | 2023년 6월 6일 |
| **파생 필드** | 이는 파생 필드의 초기 릴리스를 나타냅니다. 파생 필드를 사용하면 사용자 정의 가능한 규칙 빌더를 통해 즉석에서 (종종 복잡한) 데이터 조작을 정의할 수 있습니다. 또한 데이터 보기에서 파생 필드를 구성 요소(지표 또는 차원)로 정의한 다음 Workspace에서 파생 필드를 구성 요소로 사용할 수 있습니다.<p>이 릴리스는 마케팅 채널 템플릿과 다음 기능을 지원합니다.</p><ul><li>연결</li><li>다음과 같은 경우</li><li>찾기 및 바꾸기</li><li>조회</li><li>URL 구문 분석</li></ul> <p>[자세히 알아보기](/help/data-views/derived-fields/derived-fields.md)</p> | 2023년 5월 10일 | 2023년 6월 14일 |
| **통화 전환 지원** | 통화 전환은 데이터 보기에서 지표 구성 요소 서식 지정의 일부로 지원됩니다. [자세히 알아보기](../data-views/component-settings/format.md#currency) | 2023년 6월 7일 | 2023년 6월 21일 |
| **Customer Journey Analytics 데이터 보기에 대한 PowerBI 및 Tableau 액세스** | Adobe Customer Journey Analytics SQL Connector를 사용하면 Customer Journey Analytics에서 정의한 데이터 보기에 SQL로 액세스할 수 있습니다. Power BI, 타블로 또는 기타 비즈니스 인텔리전스 및 시각화 도구에 더 익숙한 데이터 엔지니어와 분석가는 이제 Customer Journey Analytics 사용자가 Analysis Workspace 프로젝트에 사용하는 것과 동일한 데이터 보기를 기반으로 보고서와 대시보드를 만들 수 있습니다. [자세히 알아보기](/help/data-views/sql-connector.md) |  | 2023년 6월 30일 |
| **프로필 및 조회 데이터에 대한 조회 지원이 확장됨** | 조회 데이터 세트를 이벤트 데이터 세트와 프로필 및 조회 데이터 세트에도 추가할 수 있습니다. | 2023년 6월 28일 | 2023년 7월 12일 |
| **Experience Edge 지역 조회** | 데이터 스트림에 대해 Adobe Experience Edge 지역 조회가 활성화되면 Customer Journey Analytics에서 지리적 위치 데이터를 사용하여 보고서를 작성할 수 있습니다. |  | 2023년 7월 26일 |

{style="table-layout:auto"}

## 기타 새로운 기능 또는 업데이트 {#other-new}

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer 데이터 보기** | Customer Journey Analytics 관리자는 &quot;AJO 데이터 보기(샌드박스 이름)&quot;라는 제목의 Customer Journey Analytics에서 일부 추가 데이터 보기에 액세스할 수 있습니다. 이러한 데이터 보기는 Adobe Journey Optimizer의 보고서를 실행하는 데 사용됩니다. 또한 Customer Journey Analytics에서 Adobe Journey Optimizer 활동을 보다 심층적으로 분석하는 데 사용할 수도 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html) | | 2023년 5월 25일 |
| **비프로덕션 샌드박스용 채우기** | 비프로덕션 샌드박스에서 Analytics 소스 커넥터 데이터 흐름을 생성할 때 비프로덕션 샌드박스의 채우기는 3개월로 제한됩니다. 프로덕션 샌드박스의 경우 13개월로 유지됩니다. | 해당 사항 없음 | 2023년 4월 26일 |
| **프로젝트 링크 공유 (로그인 불필요)** | 이제 Adobe Analytics에 액세스할 수 없는 사용자에게 Analysis Workspace 프로젝트에 대한 읽기 전용 링크를 공유할 수 있습니다. 여기에는 조직 외부의 사용자 또는 Adobe Analytics용으로 프로비저닝되지 않은 조직 내의 사용자와의 공유가 포함됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>이 기능은 기본적으로 활성화되어 있으며 시스템 관리자가 비활성화할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 2023년 5월 3일 | 2023년 6월 6일 |
| **Analytics 대시보드 앱(모바일 앱)에 대한 홈 화면 업데이트** | 새롭게 업데이트된 홈 화면에서는 모든 스코어카드를 하나의 통합된 스코어카드 목록에서 볼 수 있습니다.  한 번의 로그인으로 두 개 이상의 조직에 액세스할 수 있는 경우, 조직의 모든 스코어카드를 단일 목록에서 사용할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | 해당 사항 없음 | 2023년 5월 10일 |
| **Customer Journey Analytics Report Builder - 셀에서 데이터 보기 선택** | 이 기능을 사용하면 사용자가 셀에서 데이터 블록에 대한 데이터 보기를 선택할 수 있습니다. 이는 통합 문서를 만들고 데이터 구성이 유사한 여러 데이터 보기가 있고 서로 다른 데이터 보기에서 통합 문서를 여러 번 재사용하려는 경우에 유용합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 해당 사항 없음 | 2023년 5월 24일 |
| **업데이트된 Customer Journey Analytics 학습 페이지** | 이제 Customer Journey Analytics 랜딩 페이지의 학습 탭에 Adobe Analytics에서 Customer Journey Analytics으로 전환에 초점을 맞춘 콘텐츠를 포함하여 Customer Journey Analytics과 관련된 콘텐츠가 포함됩니다.<p>학습 탭에서도 다음과 같은 추가 개선 사항을 사용할 수 있습니다.</p><ul><li>개선된 탐색 기능으로 단일 페이지에 더 많은 학습 콘텐츠를 표시하는 개선된 디자인</li><li>경험 수준(초급, 중급, 고급)에 따라 학습 콘텐츠를 맞춤 설정하는 기능</li></ul><p>이전에는 Customer Journey Analytics의 학습 탭에 Adobe Analytics의 학습 탭과 동일한 정보가 포함되었습니다.</p> [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | 해당 사항 없음 | 2023년 6월 30일 |
| **Analysis Workspace의 구성 요소 정렬** | <p>이제 왼쪽 레일 또는 Analysis Workspace의 데이터 사전에서 구성 요소를 볼 때 새로운 정렬 옵션을 사용할 수 있습니다. 권장(가장 일반적으로 사용되는 구성 요소), 알파벳순 또는 범주(유형)별로 구성 요소를 정렬할 수 있습니다.</p><p>이전에는 구성 요소만 검색하거나 필터링만 할 수 있었습니다. [자세히 알아보기](/help/components/overview.md)</p> | 해당 사항 없음 | 2023년 6월 7일 |
| **자유 형식 테이블에서 동적 차원이 포함된 행 삭제** | 이제 Analysis Workspace의 자유 형식 테이블에서 x 아이콘을 사용하여 동적 차원이 포함된 특정 행을 신속하게 삭제할 수 있습니다. 이렇게 하면 “항상 항목 제외” 필터 규칙이 자동으로 적용됩니다.<p>이전에는 동적 차원이 포함된 행을 삭제하는 유일한 방법은 필터 대화 상자에서 수동으로 규칙을 만드는 것이었습니다. [자세히 알아보기](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 해당 사항 없음 | 2023년 5월 17일 |
| **패널 내에 시각화를 추가하는 새 버튼** | 이제 Analysis Workspace의 각 패널 하단에 새로운 버튼이 추가되어 시각화를 빠르게 추가할 수 있습니다. <p>이전에는 패널에 시각화를 추가하는 유일한 방법은 왼쪽 레일에서 시각화를 드래그하거나, 기존 시각화를 복제 또는 복사하거나, 빈 패널을 만드는 것이었습니다. [자세히 알아보기](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 해당 사항 없음 | 2023년 5월 17일 |
| **딥 링크 (모바일 앱)** | 사용자가 앱의 스코어카드 프로젝트로 바로 연결되는 스코어카드 링크를 보낼 수 있습니다. 이를 통해 프로젝트를 보다 쉽게 공유하고 기술 수준이 낮은 대상자의 참여를 높일 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) | 해당 사항 없음 | 2023년 5월 17일 |
| **지능형 캡션** | [!UICONTROL 라인] 시각화의 자연어 요약으로 사용자를 위한 스토리텔링을 풍부하게 합니다. [자세히 알아보기](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023년 5월 17일 | 2023년 6월 1일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-318343; AN-319453

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| Customer Journey Analytics의 데이터 처리 방법 변경 | 2023년 6월 22일 | 최근에 Customer Journey Analytics에서 데이터를 처리하는 방법이 변경되었습니다.<p>**이전 방식:**<ul><li>라이브 데이터 또는 이벤트: Adobe Experience Platform에서 데이터를 사용할 수 있게 되면 90분 이내에 처리 및 수집됩니다. (배치 크기 > 5천만 행: 90분 이상.)</li><li>소규모 채우기 - 예: 천만 행의 조회 데이터 세트: 7일 이내<li>대규모 채우기 - 예: 5000억 행: 30일</li></ul>**새로운 방법(2023년 6월 현재)**<ul><li>타임스탬프가 24시간 미만인 모든 이벤트 데이터가 스트리밍됩니다.</li><li>타임스탬프가 24시간 이상 지난 모든 이벤트 데이터(최신 데이터와 동일한 배치에 있는 경우에도)는 채우기로 간주되고 우선 순위가 낮은 상태로 수집됩니다.</li></ul> |

## 서비스 종료(EOL) 알림 {#eol}

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
