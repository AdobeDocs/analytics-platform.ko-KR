---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4eb32d2ac0b225cbb9f5ccdc368e93bc8fd80c61
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 93%

---

# 현재 Customer Journey Analytics 릴리스 정보 (2025년 10월)

**마지막 업데이트**: 2025년 10월 14일

이번 릴리스 정보에는 2025년 10월부터 11월 초까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **라인 시각화 및 스파크라인에 포함된 필터 조건** | 자유 형식 테이블 필터에 적용하는 모든 검색 필터 조건이 이제 스파크라인에 항상 포함됩니다. 또한 연결된 라인 시각화에 검색 필터 조건을 포함할 수 있습니다.<p>연결된 테이블의 지표 열 헤더에서 스파크라인을 선택하여 검색 필터 조건을 포함하도록 라인 시각화를 구성할 수 있습니다.</p><p>이전에는 검색 필터 조건이 스파크라인 또는 연결된 라인 시각화에 포함되지 않았습니다.</p><p>자세한 내용은 [자유 형식 테이블에 대한 트렌드 데이터 보기](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md)를 참조하십시오.</p> | | 2025년 10월 15일 |
| **데이터 스토리텔링: Workspace 보고서에서 슬라이드 프레젠테이션 생성** | 이제 Analysis Workspace 보고서를 기반으로 하는 슬라이드 프레젠테이션(.pptx 포맷)을 자동으로 생성할 수 있습니다. Workspace는 보고서에서 주요 인사이트를 탐지하고 이를 관련자 대상으로 준비가 된 슬라이드로 변환합니다.<p>이 기능을 사용하면 검색 결과를 표시하고, 경영진을 대상으로 하는 설명을 빌드하고, 비즈니스 영향을 전달하는 데 필요한 시간과 노력을 단축할 수 있습니다.</p><p>(참조할 설명서 링크입니다.)</p> | 2025년 10월 22일 | 2026년 1월 |
| **실시간 보고** | [Customer Journey Analytics의 실시간 보고](/help/components/real-time/real-time.md)에서는 Analysis Workspace에 있는 하나 이상의 패널 내의 데이터 및 시각화를 실시간으로 표시하고 업데이트합니다. | 2025년 9월 18일(원래 2025년 8월 15일 릴리스로 계획됨) | 2025년 10월 22일 |
| **Data Mirror 지원** | Experience Platform의 특정 소스 커넥터에 대한 모델 기반 스키마 및 변경 데이터 캡처(CDC) 기능을 지원하면 Customer Journey Analytics은 [, &#x200B;](/help/data-mirror/data-mirror.md) 및 [!DNL Snowflake]과(와) 같은 데이터 웨어하우스 솔루션의 [!DNL Azure Databricks]데이터 미러[!DNL Google BigQuery] 기능을 지원할 수 있습니다.<p>Beta에 참여하려면 Adobe 계정 팀에 문의하여 주십시오.</p> | Beta 릴리스: 2025년 9월 24일 | TBD |
| **연결부 결합** | Customer Journey Analytics 결합 단순화. 데이터 세트를 복제하고 복제된 데이터 세트에 결합을 적용하는 대신, 이제 Customer Journey Analytics에 데이터를 수집할 때 결합을 적용하므로 중복된 데이터 세트와 스키마가 필요하지 않습니다. <p>게다가 고객 지원을 통해 결합을 요청하는 대신, 이제 업데이트된 UI 연결에서 직접 결합을 시작할 수 있습니다.</p><p> *이전에 전달된 출시 날짜는 추가적인 노력이 필요하여 연기되었습니다. 새로운 출시 날짜가 휴일 시즌과 겹치면서 출시에 대한 추가적인 제약이 발생합니다. 이제 연휴 기간 동안 안정성을 보장하고 중단을 최소화하기 위해 단계적 출시가 계획되어 있습니다.*</p> <p>(참조할 설명서 링크입니다.)</p> | 2025년 10월 28일 | 2026년 4월 30일 |
| **스트리밍 미디어 서비스: 일정 데이터 지원** | 이제 과거 라이브 스트리밍 미디어 콘텐츠의 예약된 데이터를 업로드하여 시청자 수를 보다 쉽고 정확하게 추적할 수 있습니다.<p>다음은 일정 데이터 업로드가 지원되는 라이브 콘텐츠의 예입니다.</p><ul><li>FAST(무료 광고 지원 TV) 플랫폼</li><li>로컬 스트림</li><li>라이브 스포츠</li></ul><p>일정 데이터를 업로드하면 업로드 파일에서 지정한 시간 동안 실행된 개별 프로그램의 시청자 수 데이터를 추적할 수 있습니다. 특정 주제나 프로그램 세그먼트에 대한 시청자 수 데이터를 수집할 수도 있습니다.</p><p>이러한 기능은 스트리밍 미디어 컬렉션을 어떻게 구현하든 관계없이 사용할 수 있습니다.</p><p>이전에는 라이브 콘텐츠를 분석할 때 주어진 세션을 특정 프로그램에 정확하게 연결하는 것이 어려웠고, 주어진 세션을 개별 주제나 프로그램 세그먼트에 연결하는 것도 불가능했습니다.</p><p>(참조할 설명서 링크입니다.)<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 2025년 10월 29일 |
| **Analytics 소스 커넥터: Experience Platform에서 보고서 세트 검색** | 이제 대량의 보고서 세트를 보유한 고객이 Analytics 소스 커넥터 데이터 흐름 워크플로 내에서 연결하고자 하는 보고서 세트를 검색할 수 있습니다. <p>이전에는 고객이 잠재적으로 긴 보고서 세트 목록을 페이지 단위로 확인해야 했습니다.</p><p>(참조할 설명서 링크입니다.) | | 2025년 10월 30일 |
| **스트리밍 미디어: 스트리밍 미디어 데이터를 Adobe Experience Platform으로 수집하기 위한 업데이트된 XDM 필드** | 스트리밍 미디어 데이터를 Adobe Experience Platform으로 수집할 때, 스트리밍 미디어 매개변수 설명서의 “XDM 필드 경로” 제목 아래에 표시된 XDM 필드 경로는 더 이상 사용해서는 안 됩니다. 대신, 2025년 5월 9일 이전에 플랫폼으로 스트리밍 미디어 데이터를 수집하기 위해 Analytics 소스 커넥터를 구현한 고객은 스트리밍 미디어 매개변수 설명서의 “보고 XDM 필드 경로” 제목 아래에 표시된 대로 기존 구성을 mediaReporting 필드 경로로 마이그레이션해야 합니다.<p> 이러한 필드 경로는 다음 페이지에서 찾을 수 있으며 “더 이상 사용되지 않음”으로 표시됩니다. [오디오 및 비디오 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/audio-video-parameters), [광고 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/ad-parameters), [챕터 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/chapter-parameters), [플레이어 상태 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/player-state-parameters) 및 [품질 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/quality-parameters). (2025년 5월 9일 이후에 Analytics 소스 커넥터를 구현하고 이미 mediaReporting XDM 경로만 사용하고 있는 고객은 아무런 조치가 필요하지 않습니다.)</p><p>더 이상 사용되지 않는 XDM 필드 경로에 대한 데이터 수집은 2025년 10월 말까지 계속됩니다. 그 후에는 사용되지 않는 필드 경로가 완전히 제거되어 Adobe Experience Platform 스키마 UI에서 더 이상 표시되지 않으며, 데이터는 mediaReporting 필드 경로만 사용하여 전송됩니다.</p><p>자세한 내용은 [Analytics Source Connector 구현을 업데이트된 XDM 스트리밍 미디어 필드로 마이그레이션](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)을 참조하십시오.</p><p>마이그레이션 지원에 대해서는 Adobe Consulting 서비스 또는 계정 팀에 문의해 주십시오. </p> |  | 2025년 10월 |

## Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-400507, AN-400265, AN-399209, AN-397146, AN-394992, AN-390795
**구성 요소**:
**Content Analytics**:
**내보내기**: AN-399012, AN-388578
**가이드 분석**:
**구현**: AN-397551, AN-397550, AN-397190, AN-396127
**Report Builder**: AN-401127, AN-400618, AN-392971, AN-391692
**보고**:
**세분화**:
**예약된 보고서**:
**공유된 지표 및 차원**:
**기타**:


## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 | | |

## 관련 리소스

* [2025년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2025.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko)
* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ko)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
