---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0eb56aa15104cec3dd08aa28bcfff6dd8966f14a
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 97%

---

# 최신 Customer Journey Analytics 릴리스 정보 (2026년 1월)

**마지막 업데이트**: 2026년 1월 14일

이 릴리스 정보에는 2026년 1월 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics의 Experience Platform 프로필 데이터 세트에서 대상자 분석** | 이제 Experience Platform 프로필 데이터 세트의 대상자 멤버십 데이터를 Customer Journey Analytics 연결로 수집할 수 있습니다. 대상자는 Analysis Workspace에서 사용할 수 있는 새 차원으로 제공됩니다.<p>이 작업은 Customer Journey Analytics에서 XDM 오브젝트 맵을 수집할 수 있는 새로운 기능 덕분에 가능해졌으며, 이를 통해 프로필 AudienceID도 수집할 수 있습니다.</p><p>이전에는 간단한 XDM 맵만 Customer Journey Analytics로 수집할 수 있었습니다.</p><p>Analysis Workspace의 프로젝트에 대상자 데이터를 차원으로 추가할 수 있을 뿐만 아니라 다음과 같은 새로운 Workspace 템플릿도 사용할 수 있습니다.</p><ul><li>Audience Analytics 개요</li><li>동의 정책 개요</li></ul><p>자세한 내용은 [대상자 분석 개요](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview)를 참조하십시오.</p> | 2025년 10월 22일 | 2026년 1월 27일 <p> (원래 2026년 1월 22일로 계획됨)</p> |
| **데이터 스토리텔링: Workspace 보고서에서 슬라이드 프레젠테이션 생성** | 이제 Analysis Workspace 보고서를 기반으로 하는 슬라이드 프레젠테이션(.pptx 형식)을 자동으로 생성할 수 있습니다. Workspace는 보고서에서 주요 인사이트를 탐지하고 이를 관련자 대상으로 준비가 된 슬라이드로 변환합니다.<p>이 기능을 사용하면 검색 결과를 표시하고, 경영진을 대상으로 하는 설명을 빌드하고, 비즈니스 영향을 전달하는 데 필요한 시간과 노력을 단축할 수 있습니다.</p><p>자세한 내용은 [데이터 스토리텔링: Workspace 보고서에서 슬라이드 프레젠테이션 생성](/help/analysis-workspace/curate-share/generate-slides.md)을 참조하십시오.</p> | 2025년 10월 22일 | 2026년 1월 28일 |
| **자유 형식 테이블에 여러 차원 열 포함** | 이제 자유 형식 테이블에 최대 5개의 차원 열을 포함하여 여러 차원 항목을 나란히 볼 수 있습니다. 차원 항목의 각 행은 연결된 단일 차원 항목처럼 작동합니다.<p>여러 차원 열이 있는 자유 형식 테이블에 필터, 정렬, 분류 등을 적용하여 더욱 심층적이고 사용자 정의된 분석을 만들 수 있습니다.</p><p>이전에는 자유 형식 테이블에 차원 열을 1개만 포함할 수 있었습니다.</p><p>자세한 내용은 [자유 형식 테이블에 여러 차원 열 포함](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)을 참조하십시오.</p> | 2026년 1월 28일 | 2026년 2월 18일 |
| **여러 열을 기준으로 테이블 정렬** | 이제 Analysis Workspace에서 자유 형식 테이블의 데이터를 차원 또는 지표와 관계없이 여러 열을 기준으로 정렬할 수 있습니다.<p>여러 열에 대해 데이터를 정렬할 때 데이터는 각 열에 할당한 우선순위에 따라 정렬됩니다. 우선순위 번호는 정렬 아이콘 옆에 표시됩니다.</p><p>자세한 내용은 [자유 형식 테이블 필터링 및 정렬](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)에서 [여러 열을 기준으로 테이블 정렬](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables-by-multiple-columns-advanced-sorting)을 참조하십시오.</p> | 2026년 1월 28일 | 2026년 2월 18일 |
| **여러 IMS 조직의 데이터 소스 결합** | 이제 Analytics 소스 커넥터를 사용하여 다양한 IMS 조직의 여러 데이터 소스를 결합할 수 있습니다. 이를 통해 조직은 고객 데이터가 여러 IMS 조직에 분산된 경우에도 고객 데이터를 결합하여 볼 수 있습니다. <p>**참고:** 이 구성은 Adobe 고객 지원 센터에 요청을 제출하는 경우에만 사용할 수 있습니다.</p>  <p>(참조할 설명서 링크입니다.)</p> |  | 2026년 1월 30일 |
| **연결부 결합** | 이제 Customer Journey Analytics의 결합 프로세스가 더 간단해졌습니다. 데이터 세트를 복제하고 복제된 데이터 세트에 결합을 적용하는 대신, 이제 Customer Journey Analytics에 데이터를 수집할 때 결합을 적용하므로 중복된 데이터 세트와 스키마가 필요하지 않습니다. <p>또한 Adobe 고객 지원 센터를 통해 결합을 요청하지 않고도 [업데이트된 연결 인터페이스를 통해 직접 결합을 시작](/help/stitching/use-stitching-ui.md)할 수 있습니다. | 2025년 10월 28일 | 2026년 1월 30일 |
| **Data Mirror 지원** | Experience Platform의 특정 소스 커넥터에 대한 모델 기반 스키마와 변경 데이터 캡처(CDC) 기능 지원을 통해 Customer Journey Analytics에서 [!DNL Snowflake], [!DNL Azure Databricks] 및 [!DNL Google BigQuery]와 같은 데이터 웨어하우스 솔루션의 [데이터 미러](/help/data-mirror/data-mirror.md) 기능을 지원할 수 있게 되었습니다.<p>Beta에 액세스하려면 Adobe 계정 팀에 문의하십시오.</p> | Beta 릴리스: 2025년 9월 24일 | TBD |
| **스트리밍 미디어 서비스: 일정 데이터 지원** | 이제 과거 라이브 스트리밍 미디어 콘텐츠의 예약된 데이터를 업로드하여 시청자 수를 보다 쉽고 정확하게 추적할 수 있습니다.<p>다음은 일정 데이터 업로드가 지원되는 라이브 콘텐츠의 예입니다.</p><ul><li>FAST(무료 광고 지원 TV) 플랫폼</li><li>로컬 스트림</li><li>라이브 스포츠</li></ul><p>일정 데이터를 업로드하면 업로드 파일에서 지정한 시간 동안 실행된 개별 프로그램의 시청자 수 데이터를 추적할 수 있습니다. 특정 주제나 프로그램 세그먼트에 대한 시청자 수 데이터를 수집할 수도 있습니다.</p><p>이러한 기능은 스트리밍 미디어 컬렉션을 어떻게 구현하든 관계없이 사용할 수 있습니다.</p><p>이전에는 라이브 콘텐츠를 분석할 때 주어진 세션을 특정 프로그램에 정확하게 연결하는 것이 어려웠고, 주어진 세션을 개별 주제나 프로그램 세그먼트에 연결하는 것도 불가능했습니다.</p><p>자세한 내용은 [라이브 콘텐츠를 추적할 일정 데이터 업로드](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/track-schedule-data)를 참조하십시오.</p> | 2025년 10월 29일 | 2026년 상반기<p>(원래 2025년 10월 29일 릴리스로 계획됨)</p> |

## Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-423389, AN-423316, AN-422636, AN-422482, AN-422121, AN-422116, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-405796, AN-405033, AN-404893, AN-404871, AN-404842, AN-404713, AN-404502, AN-404353, AN-404352, AN-404048, AN-403241, AN-402523, AN-400795, AN-396149, AN-390990, AN-390646, AN-383484, AN-376980, AN-371729, AN-347570, AN-404835
**구성 요소**:
**Content Analytics**:
**가이드 분석**: AN-421274
**내보내기**:
**데이터 보기**: AN-421891, AN-404627
**구현**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**보고**:
**세분화**:
**예약된 보고서**: AN-423087, AN-422686
**공유된 지표 및 차원**:
**기타**: AN-422946, AN-422775, AN-422273, AN-422100, AN-420045, AN-404891, AN-390912


## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 |  |  |

## 관련 리소스

* [2025년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2025.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/ko/docs/analytics/release-notes/latest)
* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/ko/docs/media-analytics/using/release-notes/release-notes)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/ko/docs/release-notes/experience-cloud/current)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
