---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 13790d3857f1635f8efd5d98347fd02b9cbcc144
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 63%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2025년 5월)

**마지막 업데이트**: 2025년 5월 14일


이 릴리스 정보는 2025년 4월 22일부터 6월 18일까지의 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B 에디션은 매출 성장을 촉진하는 실행 가능한 계정 인사이트를 제공하여 B2B 기업이 마케팅, 영업 및 제품 팀을 조정할 수 있도록 지원합니다. 데이터 모델의 중심에 계정을 두면 모든 분석은 계정 여정에 집중됩니다. 개인 및 시간 기반 이벤트 위에 새로운 엔티티(계정, 기회 및 구매 그룹) 계층을 추가하면 B2B 마케팅 및 수익 라이프사이클에 대한 전체 그림이 만들어집니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025년 6월 18일 목요일 |
| **Data Insights Agent** | Customer Journey Analytics의 AI 비서 중 하나인 Data Insights Agent은 생성 AI 대화 에이전트입니다. 데이터 보기의 구성 요소와 실제 데이터를 사용하여 Analysis Workspace에서 관련 시각화를 구축하여 데이터 중심의 질문에 빠르고 효율적으로 답변할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | 2025년 5월 28일 목요일 |
| **Analysis Workspace 프로젝트에서 댓글 추가 및 보기** | Analysis Workspace의 새로운 [댓글 달기 기능](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)을 사용하면 Analysis Workspace 프로젝트 컨텍스트 내에서 통찰력을 공유하고 질문을 할 수 있습니다. 이를 통해 데이터에 대한 토론을 간소화하여 논의되는 데이터의 컨텍스트 내에서 대화를 유지할 수 있습니다. 다음과 같은 작업을 수행할 수 있습니다. <ul><li>액세스 권한이 있는 Analysis Workspace 프로젝트에 대한 댓글</li><li>시각화의 특정 지점에 댓글을 달거나 프로젝트에 대한 일반 댓글을 달기</li><li>다른 사용자를 태그 지정하여 자신의 의견에 대해 알림</li><li>기존 댓글 관리(편집, 고정, 해결 등)</li></ul>Customer Journey Analytics 관리자는 조직 수준에서 [댓글 달기를 비활성화할 수 있습니다](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). 프로젝트 소유자는 프로젝트 수준에서 [댓글 달기를 사용하지 않도록 설정할 수 있습니다](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | 2025년 5월 29일 |
| **전체 테이블 내보내기 한도 증가** | Adobe에서 [전체 테이블 내보내기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics)에 사용할 수 있는 열의 수를 5차원 및 5지표에서 10차원 및 10지표로 늘렸습니다. 이는 모든 Customer Journey Analytics 계층에 적용됩니다. 내보낼 수 있는 행 수에 대한 권한에는 변경 사항이 없습니다. |  | 2025년 4월 30일 |
| **Adobe Experience Platform에 스트리밍 미디어 데이터를 수집하기 위한 업데이트된 XDM 필드** | 스트리밍 미디어 데이터를 Adobe Experience Platform으로 수집할 때, 스트리밍 미디어 매개변수 설명서의 “XDM 필드 경로” 제목 아래에 표시된 XDM 필드 경로는 더 이상 사용해서는 안 됩니다. 이러한 필드 경로는 다음 페이지에서 찾을 수 있으며 “더 이상 사용되지 않음”으로 표시됩니다. [오디오 및 비디오 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/audio-video-parameters), [광고 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/ad-parameters), [챕터 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/chapter-parameters), [플레이어 상태 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/player-state-parameters) 및 [품질 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/quality-parameters). <p>대신, 고객은 위에서 언급한 스트리밍 미디어 매개변수 설명서의 “XDM 필드 경로 보고” 제목에 표시된 대로 `mediaReporting` 필드 경로로 마이그레이션해야 합니다.<p>3개월의 전환 기간 동안, 사용되지 않는 XDM 필드 경로에 대한 데이터 수집이 계속됩니다. 그러나 2025년 7월 말부터는 사용되지 않는 필드 경로가 완전히 제거되고, Adobe Experience Platform 스키마 UI에서 더 이상 표시되지 않으며, 데이터는 `mediaReporting` 필드 경로만 사용하여 전송됩니다.<p>2025년 4월 22일 이전에 플랫폼으로 스트리밍 미디어 데이터를 수집하기 위해 Analytics 소스 커넥터를 구현한 고객은 새 필드 경로를 사용하도록 기존 구성을 마이그레이션해야 합니다. 이 마이그레이션은 2025년 7월 말까지 완료되어야 합니다. 마이그레이션 지원에 대해서는 Adobe Consulting 서비스 또는 계정 팀에 문의해 주십시오. 2025년 4월 22일 이후 Analytics 소스 커넥터를 구현하는 고객은 아무런 조치도 취할 필요가 없습니다.</p> |  | 2025년 4월 22일 |
| **스티칭: XDM IdentityMap에서 영구 ID 및 임시 ID 가져오기** | 이 기능은 스티칭 프로세스에서 XDM identityMap에 저장된 ID를 사용할 수 있도록 지원합니다. identityMap은 필드 기반 스티칭의 영구 또는 임시 ID로 사용할 수 있으며 그래프 기반 스티칭의 영구 ID로 사용할 수 있습니다. identityMap에서 특정 네임스페이스나 기본 ID를 사용할 수 있습니다. [여기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/stitching/fbs#identitymap) 및 [여기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/stitching/gbs#identitymap)에서 자세히 알아보십시오. |  | 2025년 4월 28일 |
| **데이터 보기 전반에 공유된 지표 및 차원** | 여러 데이터 보기에 차원 및 지표 설정을 적용할 수 있습니다. 공유 차원 또는 지표에 적용되는 변경 사항은 모든 해당 데이터 보기 전반에 걸쳐 해당 차원 또는 지표의 모든 인스턴스에 적용됩니다. 이 인터페이스를 사용하면 다수의 데이터 보기가 사용되는 경우 Customer Journey Analytics 관리자가 구성 요소를 더 쉽게 관리할 수 있습니다. [자세히 알아보기](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 2025년 4월 30일 |
| **이벤트 깊이 차원** | 데이터 보기에 필요한 표준 구성 요소 목록에 새 [이벤트 깊이 차원](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components)이 추가되었습니다. |  | 2025년 5월 8일 금요일 |
| **Analysis Workspace 왼쪽 패널이 더 이상 마우스를 올려도 열리거나 닫히지 않음** | Analysis Workspace의 왼쪽 패널은 구성 요소, 패널, 시각화와 같은 항목을 프로젝트에 추가하는 데 사용됩니다. 왼쪽에 있는 아이콘 중 하나에 마우스를 올려 놓으면 왼쪽 패널이 일시적으로 열리는 옵션은 더 이상 제공되지 않습니다. 대신 이들 아이콘 중 하나를 클릭하여 패널을 열어 두고, 같은 아이콘을 클릭하여 패널을 닫으십시오. |  | 2025년 5월 29일 |
| **전체 테이블을 내보낼 때 매니페스트 파일을 사용하지 않도록 설정** | Analysis Workspace에서 전체 테이블을 내보낼 때 기본적으로 포함되는 매니페스트 파일을 비활성화할 수 있습니다. [자세히 알아보기](/help/analysis-workspace/export/export-cloud.md) |  | 2025년 5월 20일 수요일 |


## Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-361874; AN-371360; AN-373079; AN-374382; AN-374447; AN-375277; AN-375680
**대상**: AN-372343
**감사 로그**: AN-378168
**연결**: AN-373121; AN-372996
**데이터 삭제**: AN-375450
**파생 필드**: AN-373689; AN-377852
**위치 내보내기**: AN-374167
**여정 캔버스**: AN-373319
**Report Builder**: AN-369786
**보고**: AN-377326; AN-378051
**활동 관리자 보고**: AN-377148


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
