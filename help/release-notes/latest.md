---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e71fe4bc1b854dcb904dfbfd770233cdadd5c8eb
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 39%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2024년 6월)

**마지막 업데이트**: 2024년 6월 12일 목요일

이 릴리스 정보는 2024년 6월 6일부터 2024년 7월의 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics용 AI 어시스턴트** | Customer Journey Analytics UI에서 자연어 질문을 하고 Customer Journey Analytics 문서를 기반으로 답변을 얻을 수 있습니다. [자세히 알아보기](/help/ai-assistant.md) | | 2024년 6월 6일 |
| **그래프 기반 결합: UIS 그래프 내보내기를 사용하여 결합** | 그래프 기반 결합을 통해 ID 그래프를 사용하여 다음과 같이 함으로써 고객 여정을 더 잘 볼 수 있습니다.<ul><li>단일 식별자를 반영하기 위해 ETL 데이터를 사용하지 않고 서로 다른 식별자로 데이터 세트를 결합합니다.</li><li>데이터 세트 간에 ID를 공유하여 단일 데이터 세트에 대한 기본 ID 또는 골든 ID의 범위를 개선합니다.</li><li>Adobe Real-Time CDP 및 Adobe 여정 최적화 도구에서 만든 프로필을 Adobe Customer Journey Analytics의 사용자와 맞춥니다.</li></ul>(참조할 설명서 링크) |  | 2024년 6월 28일 토요일 |
| **개인에서 계정으로의 B2B 스키마 변환** | B2B 데이터(계정, 기회, 마케팅 목록 및 캠페인 포함)에 대한 사용자 기반 조회를 지원하기 위해 이제 B2B 조회 데이터 세트의 변환을 제공합니다. 이 변환은 다음 클래스를 기반으로 B2B 조회 스키마에 대한 데이터가 있는 데이터 세트에만 사용할 수 있습니다.<ul><li>XDM 비즈니스 계정 사용자 관계</li><li>XDM 비즈니스 영업 기회 사용자 관계</li><li>XDM 비즈니스 마케팅 목록 멤버</li><li>XDM 비즈니스 캠페인 멤버</li></ul>[자세히 알아보기](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 2024년 6월 5일 |
| **파생 필드 - 수학 함수** | 데이터 보기 내에서 간단한 수학 연산자를 사용하여 사용자에 대한 질문에 답할 수 있습니다. 예를 들어 제품, 보증 및 배송 수익을 결합할 수 있습니다. <p>[자세히 알아보기](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p> | | 2024년 6월 5일 |
| **파생 필드 - 파생 필드 - 다음 또는 이전 함수** | 다음 또는 이전 값이 무엇인지 살펴볼 수 있습니다. 예를 들어 선택한 마케팅 채널 전에 어떤 이전 마케팅 채널과 상호 작용했습니까? 또는 페이지 사용자가 선택한 페이지의 이전 또는 이후에 상호 작용한 것은 무엇입니까? 매장 가기 전에 가장 인기 있는 채널 사용자는 누구와 상호 작용합니까? [자세히 알아보기](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous) | | 2024년 6월 12일 |
| **파생 필드 - 요약 함수** | 이벤트, 세션 및 사용자 수준에서 지표 또는 차원에 집계 유형 함수를 적용하는 기능을 제공합니다. (참조할 설명서 링크) | | 2024년 6월 26일 목요일 |
| **파생 필드 - 고급 중복 제거 기능** | 값의 반복적인 계산을 방지하는 데 도움이 됩니다. 사용자 또는 세션 수준에서 또는 차원의 고유한 값을 기준으로 적용할 수 있습니다. (참조할 설명서 링크) |  | 2024년 6월 26일 목요일 |
| **수집 우선 순위 지정 및 지연** | 이제 데이터가 24시간, 48시간 또는 7일되었는지 여부에 관계없이 이벤트 데이터를 90분(SLT) 내에 Customer Journey Analytics으로 수집할 수 있습니다. 이 기능은 귀사가 구매한 SKU 패키지에 따라 다릅니다.<ul><li>CJA 우선 순위 수집 Basic: 90분 이내의 24시간 된 데이터 SLT 처리(CJA Foundation 및 CJA Select에서 사용 가능)</li><li>CJA 우선 순위 수집 중간: 90분 이내의 72시간 된 데이터 SLT 처리(CJA Prime에서 사용 가능)</li><li>CJA 우선 순위 수집 고급: 90분 SLT 처리 내 1주 된 데이터(CJA Ultimate에서 사용 가능)</li></ul> |  | 2024년 6월 12일 |
| **내보내기 및 가져오기에 사용되는 계정 및 위치 공유** | 이제 사용자는 자신이 만든 계정과 위치를 조직의 모든 사용자가 사용할 수 있도록 할 수 있습니다. 계정 및 위치 소유자와 시스템 관리자만 계정 및 위치를 편집하고 삭제할 수 있습니다. 이전에는 계정 및 위치를 만든 사용자만 사용할 수 있었습니다. 이러한 설정은 사용자가 [클라우드 내보내기 계정을 구성](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)하고 [클라우드 내보내기 위치를 구성](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)할 때 사용할 수 있습니다. | 2024년 6월 12일 | 2024년 6월 18일 수요일 |
| **자유 형식 테이블의 드롭다운 메뉴에서 사용할 수 있는 경우 여러 필터를 선택합니다** | 여러 필터가 자유 형식 테이블에 드롭다운 메뉴로 추가된 경우 자유 형식 테이블 사용자는 이제 한 번에 두 개 이상의 필터를 선택할 수 있습니다. 자유 형식 테이블은 선택한 필터를 포함하도록 필터링됩니다. <p>이전에는 필터 드롭다운 메뉴에서 한 번에 하나의 필터만 선택할 수 있었습니다.</p><p>(참조할 설명서 링크)<!--For more information, see "Add filters to a project" in "Use components in Analysis Workspace."--> |  | 2024년 6월 19일 목요일 |
| **작업 영역 프로젝트의 목차** | 이제 프로젝트에 새 목차를 사용할 수 있습니다. 목차에서는 사용자가 프로젝트 내의 패널 및 시각화로 빠르게 이동할 수 있는 링크를 제공합니다. <p>목차는 주어진 사용자의 개별 프로젝트 또는 모든 프로젝트에 대해 활성화할 수 있습니다.</p><p>(참조할 설명서 링크)<!--For more information, see "Display the project table of contents" in "Create projects".--> |  | 2024년 6월 19일 목요일 |
| **자유 형식 테이블의 차원 항목에 대한 하이퍼링크 만들기** | 하나 이상의 차원 항목에 대한 하이퍼링크를 만들어 Analysis Workspace의 자유 형식 테이블 내에서 클릭할 수 있도록 할 수 있습니다. <p>URL 값이 있는 차원 항목에 대한 하이퍼링크를 만들거나, URL이 아닌 값이 있는 차원 항목에 대한 사용자 지정 URL을 만들 수 있습니다.</p><p>변수를 사용하여 여러 차원 항목에 대한 동적 사용자 지정 URL을 생성할 수 있습니다. 변수는 차원 항목의 값을 참조하거나 분류 차원을 참조할 수 있습니다.</p><p>(참조할 설명서 링크)<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | 2024년 6월 19일 목요일 |
| **대상자가 Experience Platform의 새로운 “대상자” 섹션에 게시됨** | 이제 Customer Journey Analytics에서 게시된 대상자를 Adobe Experience Platform의 새로운 “대상자” 섹션에서 사용할 수 있습니다.<p>이전에는 Customer Journey Analytics에서 게시된 대상자를 Experience Platform의 “세그먼트” 섹션에서 사용할 수 있었습니다.</p><p>이 개선 사항은 다음과 같은 이점이 있습니다.</p><ul><li>대상자가 더 이상 1시간의 지연 없이 Experience Platform에 표시됩니다. 게시된 지 몇 초면 사용할 수 있습니다.</li><li>Experience Platform에서 대상자가 원래 게시된 애플리케이션을 표시하는 “원본” 열을 사용하여 대상자를 정렬할 수 있습니다.</li><li>Experience Platform의 필터링 및 정렬 옵션을 사용하여 해당 대상자를 더 빨리 찾을 수 있습니다.</li></ul> <p>(참조할 설명서 링크)</p> |  | 2024년 7월 14일 월요일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-345454; AN-349816; AN-349905; AN-350617

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 | | |

{style="table-layout:auto"}

## 관련 리소스

* [2024년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2024.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko-KR)
* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ko-KR)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko-KR)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
