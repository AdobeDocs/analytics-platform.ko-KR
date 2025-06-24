---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: cbe5f3894a01f662a6ebe9c380583d0a039863fd
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 86%

---

# 현재 Adobe Customer Journey Analytics 릴리스 정보 (2025년 6월)

**마지막 업데이트**: 2025년 6월 18일


이번 릴리스 정보에는 2025년 6월 2일부터 2025년 7월 15일까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace 왼쪽 패널이 더 이상 마우스를 올려도 열리거나 닫히지 않음** | Analysis Workspace의 왼쪽 패널은 구성 요소, 패널, 시각화와 같은 항목을 프로젝트에 추가하는 데 사용됩니다. 왼쪽에 있는 아이콘 중 하나에 마우스를 올려 놓으면 왼쪽 패널이 일시적으로 열리는 옵션은 더 이상 제공되지 않습니다. 대신 이들 아이콘 중 하나를 클릭하여 패널을 열어 두고, 같은 아이콘을 클릭하여 패널을 닫으십시오. |  | 2025년 6월 2일 <p>(원래 2025년 5월 29일 릴리스로 계획됨)</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition은 매출 성장을 촉진하는 실행 가능한 계정 인사이트를 제공하여 B2B 기업이 마케팅, 영업 및 제품 팀을 조정할 수 있도록 지원합니다. 데이터 모델의 중심에 계정을 두면 모든 분석은 계정 여정에 집중됩니다. 개인 및 시간 기반 이벤트 위에 새로운 계층의 엔티티(계정, 기회, 구매 그룹)를 추가하면 B2B 마케팅 및 수익 라이프사이클에 대한 전체적인 그림이 만들어집니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025년 6월 18일 |
| **Report Builder에서 보안 클라우드 대상 지원** | 이제 Report Builder에서 다음 클라우드 스토리지 대상으로 보고서를 내보낼 수 있습니다.<ul><li>Amazon S3 Role ARN</li><li>Google Cloud 플랫폼</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>이전에는 전자 메일을 통해 통합 문서를 다른 사용자에게 공유할 수 있었지만 Report Builder에서 클라우드 대상으로 보고서를 내보낼 수는 없었습니다.</p><p>자세한 내용은 [클라우드 대상으로 내보내 통합 문서 예약](/help/report-builder/report-builder-export.md)을 참조하십시오.</p> |  | 2025년 6월 19일 (원래는 2025년 6월 18일) |
| **새로운 미리보기 경험** | 세그먼트를 만들거나 데이터 보기의 설정을 구성할 때 사용되는 미리보기 패널에서는 이제 도넛 시각화 대신 가로 막대 시각화를 사용합니다. |  | 2025년 6월 18일 |
| **수정된 속성 모델 대화 상자** | 이제 속성 모델 대화 상자에서 컨테이너와 기간을 별도로 정의할 수 있습니다. |  | 2025년 6월 18일 |
| **연결 맵** | 새로운 [연결 맵 인터페이스](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-connections/create-connection#connection-map)를 사용하면 연결 구성을 시각적으로 표시할 수 있습니다. |  | 2025년 6월 18일 |
| **Analysis Workspace 프로젝트에 댓글 추가 및 보기** | Analysis Workspace에 새롭게 추가된 [댓글 기능](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)을 통해 Analysis Workspace 프로젝트의 컨텍스트 내에서 인사이트를 공유하고 질문할 수 있습니다. 이 기능은 논의 중인 데이터의 컨텍스트 내에서 대화를 유지함으로써 데이터 관련 논의를 간소화할 수 있도록 합니다. 다음과 같은 작업을 수행할 수 있습니다. <ul><li>액세스 권한이 있는 Analysis Workspace 프로젝트에서 댓글 달기</li><li>시각화 내 특정 지점에 대해 댓글을 달거나 프로젝트 전반에 대한 일반적인 댓글 달기</li><li>다른 사용자를 태그하여 댓글에 대한 알림 전송</li><li>기존 댓글 관리 (편집, 고정, 해결 등)</li></ul>Customer Journey Analytics의 관리자는 [조직 수준에서 댓글 기능을 비활성화](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)할 수 있습니다. 프로젝트 소유자는 [프로젝트 수준에서 댓글 기능을 비활성화](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)할 수 있습니다. | 2025년 6월 25일 | 2025년 7월 11일 토요일 <p>(원래 2025년 5월 29일 릴리스로 계획됨)</p> |
| **Chrome 사전 렌더링 지원** | Chrome이 페이지를 사전 렌더링할 때 데이터 컬렉션 라이브러리가 동작하는 방식을 제어합니다. (참조할 설명서 링크) |  | 2025년 6월 30일 |

## Customer Journey Analytics의 수정 사항

**경고**: AN-379554
**Analysis Workspace**: AN-339607; AN-379222; AN-381138; AN-383291
**B2B**: AN-376028
**Tableau용 BI 확장 기능**: AN-377488
**구성 요소**: AN-376174
**데이터 보기**: AN-379011
**내보내기 위치**: AN-382191
**전체 테이블 내보내기**: AN-375646; AN-376986; AN-380355; AN-381310
**여정 캔버스**: AN-375865; AN-378011
**Report Builder**: AN-369786; AN-371395; AN-372809
**보고**: AN-372615; AN-378578;


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
