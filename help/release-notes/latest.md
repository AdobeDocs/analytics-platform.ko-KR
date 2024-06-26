---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8315bf705b576d597e346d17ff3998c336174361
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 95%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2024년 6월)

**마지막 업데이트**: 2024년 6월 18일

이번 릴리스 정보에는 2024년 6월 6일부터 7월까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics용 AI 어시스턴트** | Customer Journey Analytics UI에서 자연어 질문을 하고 Customer Journey Analytics 문서를 기반으로 답변을 얻을 수 있습니다. [자세히 알아보기](/help/ai-assistant.md) | | 2024년 6월 6일 |
| **그래프 기반 결합** | 그래프 기반 결합을 통해 Experience Platform ID 서비스의 ID 그래프를 사용하여 다음과 같이 함으로써 고객 여정을 더 잘 볼 수 있습니다.<ul><li>추가 데이터를 추출, 변환 및 로드하여 단일 식별자를 반영할 필요 없이 다양한 식별자를 사용하여 데이터 세트를 결합합니다.</li><li>데이터 세트 전체에서 ID를 공유하여 단일 데이터 세트에 대한 기본 ID 또는 골든 ID의 적용 범위를 개선합니다.</li><li>Real-Time Customer Data Platform 및 Journey Optimizer에서 생성된 프로필을 Customer Journey Analytics의 사람들과 맞춥니다.</li></ul>[자세히 알아보기](/help/stitching/overview.md) |  | 2024년 6월 28일 |
| **개인에서 계정으로의 B2B 스키마 변환** | B2B 조회 데이터 세트를 변환하여 B2B 데이터(계정, 기회, 마케팅 목록 및 캠페인 포함)에 대한 개인 기반 조회를 지원할 수 있습니다. 이러한 변환은 다음 클래스를 기반으로 하는 B2B 조회 스키마에 대한 데이터가 있는 데이터 세트에만 사용할 수 있습니다.<ul><li>XDM 비즈니스 계정 사용자 관계</li><li>XDM 비즈니스 영업 기회 사용자 관계</li><li>XDM 비즈니스 마케팅 목록 멤버</li><li>XDM 비즈니스 캠페인 멤버</li></ul>[자세히 알아보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 2024년 6월 5일 |
| **파생 필드 - 수학 함수** | 데이터 보기 내에서 간단한 수학 연산자를 사용하여 사용자에 대한 질문에 답할 수 있습니다. 예를 들어 제품, 보증 및 배송 수익을 결합할 수 있습니다. [자세히 알아보기](/help/data-views/derived-fields/derived-fields.md#math)</p> | | 2024년 6월 5일 |
| **파생 필드 - 다음 또는 이전 함수** | 다음 또는 이전 값이 무엇인지 확인할 수 있습니다. 예를 들어 선택한 마케팅 채널 이전에 누군가가 상호 작용했던 이전 마케팅 채널은 무엇이었는지, 또는 선택한 페이지 이전 또는 이후에 사용자가 상호 작용한 페이지는 무엇이었는지, 매장 가기 전에 가장 인기 있는 채널 사용자는 누구와 상호 작용합니까? [자세히 알아보기](/help/data-views/derived-fields/derived-fields.md#next-or-previous)</p> | | 2024년 6월 12일 |
| **파생 필드 - 함수 요약** | 이벤트, 세션 및 사용자 수준에서 지표 또는 차원에 집계 유형 함수를 적용할 수 있습니다. [자세히 알아보기](/help/data-views/derived-fields/derived-fields.md#summarize) | | 2024년 6월 26일 |
| **파생 필드 - 중복 제거 함수** | 값이 반복적으로 계산되는 것을 방지하는 데 도움이 됩니다. 사용자 또는 세션 수준에서 적용하거나 차원의 고유 값을 기반으로 적용할 수 있습니다. (참조할 설명서 링크) |  | 2024년 7월 10일 목요일 |
| **수집 우선 순위 지정 및 지연** | 이제 데이터가 24시간인지, 48시간인지 또는 7일인지 여부에 관계없이 90분(SLT) 이내에 Customer Journey Analytics에서 이벤트 데이터를 수집할 수 있습니다. 이 기능은 회사에서 구입한 SKU 패키지에 따라 다릅니다.<ul><li>CJA 우선 순위 수집 기본: 90분 내 24시간 이전 데이터 SLT 처리(CJA Foundation 및 CJA Select에 사용 가능)</li><li>CJA 우선 순위 수집 중간: 90분 내 72시간 이전 데이터 SLT 처리(CJA Prime에 사용 가능)</li><li>CJA 우선 순위 수집 고급: 90분 내 1주 전 데이터 SLT 처리(CJA Ultimate에서 사용 가능)</li></ul> |  | 2024년 6월 12일 |
| **내보내기 및 가져오기에 사용되는 계정 및 위치 공유** | 이제 사용자는 자신이 만든 계정과 위치를 조직의 모든 사용자가 사용할 수 있도록 할 수 있습니다. 계정 및 위치 소유자와 시스템 관리자만 계정과 위치를 편집하고 삭제할 수 있습니다. 이전에는 계정과 위치를 생성한 사용자만 사용할 수 있었습니다. 이러한 설정은 사용자가 [클라우드 내보내기 계정을 구성](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)하고 [클라우드 내보내기 위치를 구성](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)할 때 사용할 수 있습니다. | 2024년 6월 12일 | 2024년 7월 중순 |
| **드롭다운 필터에서 여러 필드 선택** | 드롭다운 필터에 여러 필드를 추가한 경우 이제 사용자가 한 번에 여러 개의 필드를 선택할 수 있습니다. 선택된 필드를 포함하도록 패널이 필터링됩니다. <p>이전에는 사용자가 드롭다운 필터에서 한 번에 하나의 필드만 선택할 수 있었습니다.</p><p>드롭다운 필터를 마우스 오른쪽 버튼으로 클릭하면 드롭다운 필터에서 선택을 요구하는 옵션이 메뉴로 이동되었습니다.</p><p>이전에는 사용자가 드롭다운 메뉴에서 [필터 없음] 옵션 옆에 있는 (x)를 클릭할 수 있었습니다.</p><p>자세한 내용은 [패널 개요](/help/analysis-workspace/c-panels/panels.md)의 [정적 드롭다운 필터](/help/analysis-workspace/c-panels/panels.md#static-drop-down-filters)를 참조하십시오.</p> |  | 2024년 6월 19일 |
| **Workspace 프로젝트 목차** | 이제 프로젝트에 새로운 목차를 사용할 수 있습니다. 목차는 사용자가 프로젝트 내 패널 및 시각화로 빠르게 이동할 수 있는 링크를 제공합니다. <p>목차는 모든 프로젝트의 왼쪽 레일에서 사용할 수 있습니다.</p><p>자세한 내용은 [프로젝트 목차](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)를 참조하십시오. |  | 2024년 6월 19일 |
| **자유 형식 테이블의 차원 항목에 대한 하이퍼링크 만들기** | 여러 차원 항목에 대한 하이퍼링크를 만들어 Analysis Workspace의 자유 형식 테이블 내에서 해당 항목을 클릭하도록 할 수 있습니다. <p>URL 값이 있는 차원 항목에 대해 하이퍼링크를 만들거나, URL이 아닌 값이 있는 차원 항목에 대해 사용자 정의 URL을 만들 수 있습니다.</p><p>변수를 사용하여 여러 차원 항목에 대한 동적 사용자 정의 URL을 만들 수 있습니다. 변수는 차원 항목의 값을 참조하거나 분류 차원을 참조할 수 있습니다.</p><p>자세한 내용은 [자유 형식 테이블의 차원에 대한 하이퍼링크 만들기](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)를 참조하십시오.</p> |  | 2024년 6월 19일 |
| **Adobe Journey Optimizer와 함께 Customer Journey Analytics 데이터 보기 사용** | Customer Journey Analytics의 새 구성 옵션을 사용하면 수동 구성 없이 Adobe Journey Optimizer와 함께 사용할 Customer Journey Analytics 데이터 보기를 지정할 수 있습니다. <p>이 구성 옵션을 활성화하는 방법에 대한 자세한 내용은 [데이터 보기 만들기 또는 편집](/help/data-views/create-dataview.md)의 [호환성](/help/data-views/create-dataview.md#compatibility) 섹션을 참조하십시오.</p><p>이전에는 Customer Journey Analytics에서 Journey Optimizer 데이터를 볼 때 연결 및 데이터 보기를 수동으로 구성해야 했습니다.</p> |  | 2024년 6월 19일 |
| **대상자가 Experience Platform의 새로운 “대상자” 섹션에 게시됨** | 이제 Customer Journey Analytics에서 게시된 대상자를 Adobe Experience Platform의 새로운 “대상자” 섹션에서 사용할 수 있습니다.<p>이전에는 Customer Journey Analytics에서 게시된 대상자를 Experience Platform의 “세그먼트” 섹션에서 사용할 수 있었습니다.</p><p>이 개선 사항은 다음과 같은 이점이 있습니다.</p><ul><li>대상자가 더 이상 1시간의 지연 없이 Experience Platform에 표시됩니다. 게시된 지 몇 초면 사용할 수 있습니다.</li><li>Experience Platform에서 대상자가 원래 게시된 애플리케이션을 표시하는 “원본” 열을 사용하여 대상자를 정렬할 수 있습니다.</li><li>Experience Platform의 필터링 및 정렬 옵션을 사용하여 해당 대상자를 더 빨리 찾을 수 있습니다.</li></ul> <p>(참조할 설명서 링크)</p> |  | 2024년 7월 14일 |

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
