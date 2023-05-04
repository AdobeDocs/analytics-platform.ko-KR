---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7737a285c701946dcf92c2610c1918022e05de36
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 66%

---

# 현재 Customer Journey Analytics(CJA) 릴리스 노트(2023년 4월)

**마지막 업데이트**: 2023년 4월 12일

Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 주요 기능 및 업데이트

| 기능 | 설명 | [롤아웃 시작](/help/release-notes/releases.md) | [일반 가용성](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Analytics 소스 커넥터 스트리밍을 위한 행/열 필터링** | 이제 Adobe Experience Platform의 Analytics 소스 커넥터를 통해 [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko)에 프로필을 채우는 데 사용되는 Analytics 데이터를 필터링할 수 있습니다. 행 수준 필터링은 프로필과 관련된 이벤트 수를 줄이는 데 도움이 됩니다. 열 수준 필터링은 이벤트 자체의 내용을 줄이는 데 도움이 되므로 프로필 자격 사용을 최적화할 수 있습니다. 이 필터링은 실시간 고객 프로필 및 [ID 서비스](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ko)로 전송된 데이터에만 적용됩니다. **필터링은 Customer Journey Analytics와 같은 애플리케이션에서 사용하기 위해 데이터 레이크로 전송되는 데이터에 영향을 미치지 않습니다**. [자세히 알아보기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko#filtering-for-profile) | 해당 사항 없음 | 2023년 3월 29일 |
| **Analysis Workspace의 데이터 사전** | 데이터 사전을 통해 사용자와 관리자 모두가 CJA 환경의 구성 요소(차원, 지표)를 추적하고 더 잘 이해할 수 있습니다. [자세히 알아보기](/help/components/data-dictionary/data-dictionary-overview.md) | 2023년 3월 8일 | 2023년 3월 29일 |
| **프로젝트 링크 공유 (로그인 불필요)** | <p>이제 Adobe Analytics에 액세스할 수 없는 사용자에게 Analysis Workspace 프로젝트에 대한 읽기 전용 링크를 공유할 수 있습니다. 여기에는 조직 외부의 사람 또는 CJA가 제공되지 않는 조직 내의 사람과 공유하는 작업이 포함됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link)</p> <p>이 기능은 기본적으로 활성화되어 있으며 시스템 관리자가 비활성화할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023년 5월 3일 | 2023년 6월 |
| **Adobe 제품 분석 - 비공개 베타 액세스만** | 2023년 3월 21일, Adobe은 Customer Journey Analytics에서 크로스 채널 데이터 및 인사이트와 상호 작용하는 새로운 방법인 Adobe 제품 분석 을 발표했습니다. 이러한 새로운 기능을 통해 제품 팀은 안내가 있는 분석 워크플로우를 통해 제품 경험에 대한 데이터와 통찰력을 제공할 수 &#x200B; 있습니다. 팀은 다음 작업을 수행할 수 있습니다.<ul><li>시간에 따른 사용자 참여의 패턴 &#x200B; 이해</li><li>사용자 기반의 증가 &#x200B; 분석</li><li>일련의 단계에서 마찰 영역 식별&#x200B;</li><li>기능 릴리스의 영향 측정&#x200B;</li><li>제품을 통해 평생에 걸친 여정 동안 참여하거나 육성할 수 있는 의미 있는 세그먼트를 &#x200B; 발견합니다</li><li>분석가와의 심층적인 분석 및 공동 작업 등을 위해 Analysis Workspace에서 참여해 보십시오&#x200B;!</li></ul>CJA 고객이고 비공개 베타에 참여하려는 경우 Adobe 계정 팀에 문의하십시오. [자세히 알아보기](https://business.adobe.com/products/product-analytics/adobe-product-analytics.html) | 해당 사항 없음 | 2023년 7월 17일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-313118; AN-313390; AN-314135; AN-316381; AN-316811

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
