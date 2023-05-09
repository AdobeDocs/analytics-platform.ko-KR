---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1c00f3974293c9022365e69d6c1b38d79f52d872
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 32%

---

# 현재 CJA(Customer Journey Analytics) 릴리스 정보 (2023년 5월)

**마지막 업데이트**: 2023년 5월 8일

Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 주요 기능 및 업데이트

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **비프로덕션 샌드박스용 채우기** | 비프로덕션 샌드박스에서 Analytics 소스 커넥터 데이터 흐름을 생성할 때 비프로덕션 샌드박스의 채우기는 3개월로 제한됩니다. 프로덕션 샌드박스의 경우 13개월로 유지됩니다. | 해당 사항 없음 | 2023년 4월 26일 |
| **프로젝트 링크 공유 (로그인 불필요)** | 이제 Adobe Analytics에 액세스할 수 없는 사용자에게 Analysis Workspace 프로젝트에 대한 읽기 전용 링크를 공유할 수 있습니다. 여기에는 조직 외부의 사람 또는 Adobe Analytics에 대해 프로비저닝되지 않은 조직 내의 사람과의 공유가 포함됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>이 기능은 기본적으로 활성화되어 있으며 시스템 관리자가 비활성화할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023년 5월 3일 | 2023년 6월 |
| **Analytics 대시보드 앱(모바일 앱)에 대한 홈 화면이 업데이트되었습니다** | 새로 업데이트된 홈 화면에서 하나의 통합 스코어카드 목록에서 모든 스코어카드를 볼 수 있습니다.  한 번의 로그인으로 두 개 이상의 조직에 액세스할 수 있는 경우 조직의 모든 스코어카드를 단일 목록에서 사용할 수 있습니다. | 해당 사항 없음 | 2023년 5월 10일 |
| **파생 필드** | 이는 파생 필드의 초기 릴리스를 나타냅니다. 파생 필드를 사용하면 사용자 지정 가능한 규칙 빌더를 통해 빠르게 (종종 복잡한) 데이터 조작을 정의할 수 있습니다. 파생된 필드를 데이터 보기에서 구성 요소(지표 또는 차원)로 정의한 다음, 파생 필드를 Workspace에서 구성 요소로 사용할 수 있습니다.<p>이 릴리스는 마케팅 채널 템플릿과 다음 기능을 지원합니다.</p><ul><li>연결</li><li>다음과 같은 경우</li><li>찾기 및 바꾸기</li><li>조회</li><li>URL 구문 분석</li></ul> <p>[자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 2023년 5월 10일 | TBD |
| **CJA용 Report Builder - 셀에서 데이터 보기 선택** | 이 기능을 사용하면 셀에서 데이터 블록에 대한 데이터 보기를 선택할 수 있습니다. 이 기능은 통합 문서를 만들고 유사한 데이터 구성이 있는 여러 데이터 보기가 있는 경우 다른 데이터 보기로 통합 문서를 여러 번 다시 사용할 수 있는 경우에 유용합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 해당 사항 없음 | 2023년 5월 24일 |
| **Analysis Workspace에서 구성 요소 정렬** | <p>이제 왼쪽 레일이나 Analysis Workspace의 데이터 사전에서 구성 요소를 볼 때 새 정렬 옵션을 사용할 수 있습니다. 구성 요소를 권장(가장 일반적으로 사용되는 항목), 알파벳 또는 카테고리적(유형)별로 정렬할 수 있습니다.</p><p>이전에는 구성 요소를 검색하거나 필터링할 수만 있었습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=en)</p> | 해당 사항 없음 | 2023년 5월 10일 |
| **자유 형식 테이블에서 동적 차원이 포함된 행 삭제** | 이제 Analysis Workspace의 자유 형식 테이블에서 x 아이콘을 사용하여 동적 차원이 포함된 특정 행을 빠르게 삭제할 수 있습니다. 이 경우 &quot;다음과 같지 않음&quot; 필터 규칙이 자동으로 적용됩니다.<p>이전에는 동적 차원이 포함된 행을 삭제하는 유일한 방법은 필터 대화 상자에서 규칙을 수동으로 만드는 것이었습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=en)</p> | 해당 사항 없음 | 2023년 5월 10일 |
| **패널 내에 시각화를 추가하는 새 단추** | 이제 Analysis Workspace의 각 패널 하단에 새 단추를 사용할 수 있으므로 시각화를 빠르게 추가할 수 있습니다. <p>이전에는 시각화를 패널에 추가하는 유일한 방법은 왼쪽 레일에서 시각화를 드래그하거나 기존 시각화를 복제하거나 복사하거나 빈 패널을 만드는 것이었습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#quick-viz)</p> | 해당 사항 없음 | 2023년 5월 10일 |
| **딥 링크(모바일 앱)** | 사용자가 앱의 스코어카드 프로젝트로 바로 안내하는 스코어카드에 대한 링크를 전송할 수 있습니다. 따라서 프로젝트를 보다 쉽게 공유하고 기술적인 지식이 부족한 대상으로부터의 참여를 늘릴 수 있습니다. | 해당 사항 없음 | 2023년 5월 17일 |
| **지능형 캡션** | 라인 시각화의 자연어 요약 정보를 사용하여 사용자에게 스토리텔링을 보강합니다. | 2023년 5월 17일 | 2023년 6월 1일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-316412; AN-317105; AN-318122; AN-317353

## CJA 관리자를 위한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 | 해당 없음 | 해당 사항 없음 |

{style="table-layout:auto"}

## 관련 리소스

* [2023년 이전 CJA 릴리스 정보](/help/release-notes/2023.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko)
* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
