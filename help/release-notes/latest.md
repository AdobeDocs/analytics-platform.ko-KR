---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4cea79a6ba26a2e4f06bfc9c60fdfc03341a7d60
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 100%

---

# 최신 CJA(고객 여정 분석) 릴리스 정보 (2025년 9월)

**마지막 업데이트**: 2025년 9월 23일


이번 릴리스 정보에는 2025년 9월부터 10월 초까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **사용 인터페이스 업데이트** | [사용 인터페이스](/help/connections/manage-connections.md#usage)에 핵심 데이터 볼륨과 평균 행 크기에 대한 정보가 추가되었습니다.<p>자세한 내용은 [연결 관리](/help/connections/manage-connections.md#usage)를 참조하십시오.</p> | | 2025년 9월 4일 |
| **Customer Journey Analytics로 프로젝트 및 구성 요소를 마이그레이션할 때의 개선 사항** | Adobe Analytics에서 Customer Journey Analytics로 프로젝트 및 구성 요소를 마이그레이션할 때 다음과 같은 개선 사항이 적용됩니다.<ul><li>여러 프로젝트를 한 번에 마이그레이션합니다.<br/>한 번에 최대 20개의 프로젝트 마이그레이션이 가능합니다.<br/>기존에는 한 번에 한 개의 프로젝트만 마이그레이션 가능했습니다.</li><li>이전 프로젝트 마이그레이션을 통해 이미 매핑된 차원 및 메트릭에 대한 매핑을 업데이트합니다.<br/>이제 이전 마이그레이션에서 동일한 차원과 메트릭이 매핑된 경우에도 프로젝트를 마이그레이션할 때마다 해당 매핑을 업데이트할 수 있습니다.<br/>이전에는 선택한 모든 매핑이 향후 모든 프로젝트 마이그레이션에 영구 적용되었습니다.</li><li>많은 프로젝트가 있는 조직에서 성과가 향상됩니다.</li></ul><p>이 기능은 Adobe Analytics 인터페이스에서 사용할 수 있습니다. 자세한 내용은 [Adobe Analytics에서 Customer Journey Analytics로 구성 요소 및 프로젝트 마이그레이션](https://experienceleague.adobe.com/ko/docs/analytics/admin/admin-tools/component-migration/component-migration)을 참조하십시오.</p> | 2025년 9월 15일 | 2025년 9월 18일 |
| **조회 키 제한이 최대 10억 개로 증가했습니다.** | Customer Journey Analytics 권한에 따라 조회 데이터 세트의 최대 고유 키 수를 이제 최대 10억 개까지 지원합니다. <p>기존에는 모든 권한에 대해 최대 1,000만 개로 제한되었습니다.<p>자세한 정보는 [가드레일](/help/technotes/guardrails.md)을 참조하십시오.</p> | | 2025년 9월 25일 |
| **애드혹 및 모델 기반 스키마 지원** | [애드혹](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/tutorials/ad-hoc) 및 모델 기반 스키마는 Experience Platform의 데이터 수집 및 데이터 미러 워크플로에서 사용됩니다. |  | 2025년 9월 23일(원래 2025년 8월 28일 릴리스로 계획됨) |
| **실시간 보고** | Customer Journey Analytics의 실시간 보고는 Analysis Workspace의 하나 이상의 패널 내에서 데이터와 시각화를 실시간으로 표시하고 업데이트합니다.<br/><br/>(참조할 설명서 링크입니다.) | 2025년 9월 18일(원래 2025년 8월 15일 릴리스로 계획됨) | 2025년 10월 27일 화요일 |
| **Data Mirror 지원** | Experience Platform의 특정 소스 커넥터에 대한 모델 기반 스키마와 변경 데이터 캡처(CDC) 기능 지원을 통해 Customer Journey Analytics에서 [!DNL Snowflake], [!DNL Azure Databrick], [!DNL Google BigQuery]와 같은 데이터웨어하우스 솔루션의 Data Mirror 기능을 지원할 수 있게 되었습니다.<p>Beta에 참여하려면 Adobe 계정 팀에 문의하여 주십시오.</p><p>(참조할 설명서 링크입니다.)</p> | Beta 릴리스는 2025년 9월 24일부터 시작됩니다. | TBD |
| **스트리밍 미디어 서비스: 일정 데이터 지원** | 이제 과거 라이브 스트리밍 미디어 콘텐츠의 예약된 데이터를 업로드하여 시청자 수를 보다 쉽고 정확하게 추적할 수 있습니다.<p>다음은 일정 데이터 업로드가 지원되는 라이브 콘텐츠의 예입니다.</p><ul><li>FAST(무료 광고 지원 TV) 플랫폼</li><li>로컬 스트림</li><li>라이브 스포츠</li></ul><p>일정 데이터를 업로드하면 업로드 파일에서 지정한 시간 동안 실행된 개별 프로그램의 시청자 수 데이터를 추적할 수 있습니다. 특정 주제나 프로그램 세그먼트에 대한 시청자 수 데이터를 수집할 수도 있습니다.</p><p>이러한 기능은 스트리밍 미디어 컬렉션을 어떻게 구현하든 관계없이 사용할 수 있습니다.</p><p>이전에는 라이브 콘텐츠를 분석할 때 주어진 세션을 특정 프로그램에 정확하게 연결하는 것이 어려웠고, 주어진 세션을 개별 주제나 프로그램 세그먼트에 연결하는 것도 불가능했습니다.</p><p>(참조할 설명서 링크입니다.)<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 2025년 10월 29일 |
| **스트리밍 미디어: 스트리밍 미디어 데이터를 Adobe Experience Platform으로 수집하기 위한 업데이트된 XDM 필드** | 스트리밍 미디어 데이터를 Adobe Experience Platform으로 수집할 때, 스트리밍 미디어 매개변수 설명서의 “XDM 필드 경로” 제목 아래에 표시된 XDM 필드 경로는 더 이상 사용해서는 안 됩니다. 대신, 2025년 5월 9일 이전에 플랫폼으로 스트리밍 미디어 데이터를 수집하기 위해 Analytics 소스 커넥터를 구현한 고객은 스트리밍 미디어 매개변수 설명서의 “보고 XDM 필드 경로” 제목 아래에 표시된 대로 기존 구성을 mediaReporting 필드 경로로 마이그레이션해야 합니다.<p> 이러한 필드 경로는 다음 페이지에서 찾을 수 있으며 “더 이상 사용되지 않음”으로 표시됩니다. [오디오 및 비디오 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/audio-video-parameters), [광고 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/ad-parameters), [챕터 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/chapter-parameters), [플레이어 상태 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/player-state-parameters) 및 [품질 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/quality-parameters). (2025년 5월 9일 이후에 Analytics 소스 커넥터를 구현하고 이미 mediaReporting XDM 경로만 사용하고 있는 고객은 아무런 조치가 필요하지 않습니다.)</p><p>더 이상 사용되지 않는 XDM 필드 경로에 대한 데이터 수집은 2025년 10월 말까지 계속됩니다. 그 후에는 사용되지 않는 필드 경로가 완전히 제거되어 Adobe Experience Platform 스키마 UI에서 더 이상 표시되지 않으며, 데이터는 mediaReporting 필드 경로만 사용하여 전송됩니다.</p><p>자세한 내용은 [Analytics Source Connector 구현을 업데이트된 XDM 스트리밍 미디어 필드로 마이그레이션](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)을 참조하십시오.</p><p>마이그레이션 지원에 대해서는 Adobe Consulting 서비스 또는 계정 팀에 문의해 주십시오. </p> |  | 2025년 10월 |
| **연결부 결합** | Customer Journey Analytics 결합 단순화. 데이터 세트를 복제하고 복제된 데이터 세트에 결합을 적용하는 대신, 이제 Customer Journey Analytics에 데이터를 수집할 때 결합을 적용하므로 중복된 데이터 세트와 스키마가 필요하지 않습니다. <p>게다가 고객 지원을 통해 결합을 요청하는 대신, 이제 업데이트된 UI 연결에서 직접 결합을 시작할 수 있습니다.</p><p> *이전에 전달된 출시 날짜는 추가적인 노력이 필요하여 연기되었습니다. 새로운 출시 날짜가 휴일 시즌과 겹치면서 출시에 대한 추가적인 제약이 발생합니다. 이제 연휴 기간 동안 안정성을 보장하고 중단을 최소화하기 위해 단계적 출시가 계획되어 있습니다.*</p> <p>(참조할 설명서 링크입니다.)</p> | 2025년 10월 말 | 2026년 1월 말 |

## Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-391719, AN-380838, AN-389402, AN-389373, AN-390851, AN-391593, AN-391404, AN-393064, AN-379337
**구성 요소**: AN-393810
**Content Analytics**:
**가이드 분석**:
**플랫폼**:
**Report Builder**: AN-387741, AN-386777, AN-388720, AN-389343
**보고**: AN-391439, AN-391228, AN-393620, AN-393640, AN-391334, AN-393304
**세분화**:
**예약된 보고서**: AN-391150, AN-390474
**공유된 지표 및 차원**:
**기타**: AN-387858


## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 | | |

## 관련 리소스

* [2025년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2025.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
