---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4ad92a72f0ced81f84198da744fef9fe4c0a6b0b
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 44%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2024년 5월)

**마지막 업데이트**: 2024년 5월 15일 목요일

이 릴리스 정보는 2024년 5월 15일부터 2024년 6월의 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **BI 확장** | BI 확장을 사용하면 Customer Journey Analytics에서 정의한 데이터 보기에 SQL로 액세스할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 2024년 5월 15일 목요일 |
| **대상자가 Experience Platform의 새로운 “대상자” 섹션에 게시됨** | 이제 Customer Journey Analytics에서 게시된 대상자를 Adobe Experience Platform의 새로운 “대상자” 섹션에서 사용할 수 있습니다.<p>이전에는 Customer Journey Analytics에서 게시된 대상자를 Experience Platform의 “세그먼트” 섹션에서 사용할 수 있었습니다.</p><p>이 개선 사항은 다음과 같은 이점이 있습니다.</p><ul><li>대상자가 더 이상 1시간의 지연 없이 Experience Platform에 표시됩니다. 게시된 지 몇 초면 사용할 수 있습니다.</li><li>Experience Platform에서 대상자가 원래 게시된 애플리케이션을 표시하는 “원본” 열을 사용하여 대상자를 정렬할 수 있습니다.</li><li>Experience Platform의 필터링 및 정렬 옵션을 사용하여 해당 대상자를 더 빨리 찾을 수 있습니다.</li></ul> [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-components/audiences/publish) |  | 2024년 5월 15일 목요일 |
| **Customer Journey Analytics을 위한 AI 지원** | Customer Journey Analytics UI에서 자연어 질문을 하고 Customer Journey Analytics 설명서에 따라 답변을 얻을 수 있습니다. (참조할 설명서 링크) | | 2024년 5월 30일 금요일 |
| **Streaming Media: 웹 SDK를 사용하여 Adobe Experience Platform Edge Network으로 웹 데이터 전송** | 이제 Adobe Experience Platform Web SDK를 사용하여 스트리밍 미디어 웹 데이터를 Adobe Experience Platform Edge Network으로 전송할 수 있으므로 보다 개인화된 캠페인을 작성하고 보다 개인화된 콘텐츠를 제공하여 보고할 더 많은 추적 데이터를 얻을 수 있습니다.<p>이러한 향상된 기능은 Customer Journey Analytics, RT-CDP, AJO 및 이벤트 전달과 같은 모든 플랫폼 솔루션에서 웹 구현을 위한 통합 수집 방법을 제공합니다. 이전에는 스트리밍 미디어 웹 데이터를 Edge Network으로 전송하는 유일한 방법이 Media Edge API를 사용하는 것이었습니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) | | 2024년 5월 31일 |
| **파생 필드 - 수학 함수** | 데이터 보기 내에서 간단한 수학 연산자를 수행하여 사용자에 대한 질문에 답변할 수 있습니다. 예를 들어 제품, 보증 및 배송 수익을 결합할 수 있습니다. (참조할 설명서 링크) | | 2024년 6월 5일 목요일 |
| **파생 필드 - 다음 또는 이전 함수** | 다음 또는 이전 값이 무엇인지 살펴볼 수 있습니다. 예를 들어 선택한 마케팅 채널 전에 어떤 이전 마케팅 채널과 상호 작용했습니까? 또는 페이지 사용자가 선택한 페이지의 이전 또는 이후에 상호 작용한 것은 무엇입니까? 매장 가기 전에 가장 인기 있는 채널 사용자는 누구와 상호 작용합니까?  (참조할 설명서 링크) | | 2024년 6월 12일 목요일 |
| **Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하기 위한 새로운 설명서** | Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 조직의 경우, 조직의 현재 Adobe Analytics 구현 및 장기 목표를 기반으로 여러 업그레이드 옵션 및 고려해야 할 사항이 많습니다. 이제 새로운 문서 리소스를 통해 다음 내용을 더 효과적으로 이해할 수 있습니다.<ul><li>존재하는 다양한 업그레이드 경로</li><li>조직의 현재 Adobe Analytics 구현에 따라 사용 가능한 업그레이드 경로</li><li>각 업그레이드 경로의 장점과 단점</li><li>각 업그레이드 경로에 대한 단계별 지침</li><li>내역 데이터 처리 시 고려 사항</li></ul>[Customer Journey Analytics으로 업그레이드 시작](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 현재 사용 가능 |
| **에 대한 새로운 설명서 [데이터 내보내기 사용 사례](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/overview)** | 이 새로운 섹션에서는 다음과 같은 데이터 내보내기 사용 사례를 간략하게 설명합니다.<ul><li>데이터 백업</li><li>데이터 유효성 검사</li><li>Data Lake, Data Warehouse 또는 BI 도구</li><li>AI/ML 준비</li></ul> Experience Platform 및 Customer Journey Analytics 기능을 사용하여 구현하는 방법도 알아봅니다. | | 현재 사용 가능 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-342309; AN-342312; AN-345267; AN-345909; AN-346016; AN-346049; AN-346052; AN-346287; AN-346624; AN-347919

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
