---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 6ae081aecf0143dd78c3feb4e397bb4f7ba32c68
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 98%

---

# 현재 Adobe Customer Journey Analytics 릴리스 정보(2024년 5월)

**마지막 업데이트**: 2024년 6월 6일

이번 릴리스 정보에는 2024년 5월 15일부터 2024년 6월까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics용 AI 어시스턴트** | Customer Journey Analytics UI에서 자연어 질문을 하고 Customer Journey Analytics 문서를 기반으로 답변을 얻을 수 있습니다. [자세히 알아보기](/help/ai-assistant.md) | | 2024년 6월 6일 |
| **B2B 조회 데이터 세트의 변환** | 이제 연결을 정의할 때 [B2B 조회 데이터 세트를 변환](/help/connections/transform-datasets-b2b-lookups.md)할 수 있습니다. 이 변환을 통해 B2B 데이터에 대한 개인 기반 조회를 지원할 수 있습니다. | | 2024년 6월 6일 |
| **BI 확장 기능** | BI 확장 기능을 통해 SQL은 Customer Journey Analytics에서 정의한 데이터 보기에 액세스할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/kr/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 2024년 5월 15일 |
| **대상자가 Experience Platform의 새로운 “대상자” 섹션에 게시됨** | 이제 Customer Journey Analytics에서 게시된 대상자를 Adobe Experience Platform의 새로운 “대상자” 섹션에서 사용할 수 있습니다.<p>이전에는 Customer Journey Analytics에서 게시된 대상자를 Experience Platform의 “세그먼트” 섹션에서 사용할 수 있었습니다.</p><p>이 개선 사항은 다음과 같은 이점이 있습니다.</p><ul><li>대상자가 더 이상 1시간의 지연 없이 Experience Platform에 표시됩니다. 게시된 지 몇 초면 사용할 수 있습니다.</li><li>Experience Platform에서 대상자가 원래 게시된 애플리케이션을 표시하는 “원본” 열을 사용하여 대상자를 정렬할 수 있습니다.</li><li>Experience Platform의 필터링 및 정렬 옵션을 사용하여 해당 대상자를 더 빨리 찾을 수 있습니다.</li></ul> <p>(업데이트된 설명서 링크)</p> |  | 2024년 5월 말~6월 초 |
| **스트리밍 미디어: Web SDK를 통해 웹 데이터를 Adobe Experience Platform Edge Network로 보내기** | 이제 Adobe Experience Platform Web SDK를 사용하여 스트리밍 미디어 웹 데이터를 Adobe Experience Platform Edge Network로 보낼 수 있으며, 이에 따라 더욱 개인화된 캠페인을 구축하고 더욱 개인화된 콘텐츠를 제공할 수 있어 보고할 추적 데이터가 더 많아집니다.<p>이 개선 사항으로 Customer Journey Analytics, RT-CDP, AJO, 이벤트 전달 등 모든 플랫폼 솔루션 전반에 걸쳐 웹 구현을 위한 통합 수집 방법이 확보됩니다. 이전까지 스트리밍 미디어 웹 데이터를 Edge Network로 보내는 유일한 방법은 Media Edge API를 사용하는 것이었습니다. <p>[자세히 알아보기](https://experienceleague.adobe.com/kr/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | 2024년 5월 29일 |
| **파생 필드 - 새 함수 및 함수 템플릿** | 추가 파생 필드 함수([수학](/help/data-views/derived-fields/derived-fields.md#math), [다음 또는 이전](/help/data-views/derived-fields/derived-fields.md#next-or-previous)) 및 [함수 템플릿](/help/data-views/derived-fields/derived-fields.md#function-templates) | | 2024년 6월 5일 |
| **내보내기 및 가져오기에 사용되는 계정 및 위치 공유** | 이제 사용자는 자신이 만든 계정과 위치를 조직의 모든 사용자가 사용할 수 있도록 할 수 있습니다. 계정 및 위치 소유자와 시스템 관리자만 계정과 위치를 편집하고 삭제할 수 있습니다.<p>이전에는 계정과 위치를 생성한 사용자만 사용할 수 있었습니다.</p><p>이러한 설정은 사용자가 클라우드 내보내기 계정을 구성하고 클라우드 내보내기 위치를 구성할 때 사용할 수 있습니다.</p> <p>자세한 내용은 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md) 및 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md).</p> | 2024년 6월 12일 | 2024년 6월 30일 |
| **Adobe Analytics에서 Customer Journey Analytics로 업그레이드에 대한 새로운 설명서** | Adobe Analytics에서 Customer Journey Analytics로 업그레이드하는 조직의 경우 조직의 현재 Adobe Analytics 구현 및 장기 목표를 기반으로 염두에 두어야 할 다양한 업그레이드 옵션 등 고려 사항이 많습니다. 이제 새로운 문서 리소스를 통해 다음 내용을 더 효과적으로 이해할 수 있습니다.<ul><li>존재하는 다양한 업그레이드 경로</li><li>조직의 현재 Adobe Analytics 구현에 따라 사용 가능한 업그레이드 경로</li><li>각 업그레이드 경로의 장점과 단점</li><li>각 업그레이드 경로에 대한 단계별 지침</li><li>내역 데이터 처리 시 고려 사항</li></ul>[Customer Journey Analytics로 업그레이드 시작하기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 지금 사용 가능 |
| **데이터 내보내기 사용 사례에 대한 새 설명서** | 이 새로운 섹션에서는 다음과 같은 [데이터 내보내기 사용 사례](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-usecases/data-export/overview)를 간략하게 설명합니다.<ul><li>데이터 백업</li><li>데이터 유효성 검사</li><li>데이터 레이크, 데이터 웨어하우스 또는 BI 도구</li><li>AI/ML에 대한 준비</li></ul> Experience Platform 및 Customer Journey Analytics 기능을 사용하여 이를 구현하는 방법 | | 지금 사용 가능 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-342309, AN-342312, AN-345267, AN-345909, AN-346016, AN-346049, AN-346052, AN-346287, AN-346624, AN-347919

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
