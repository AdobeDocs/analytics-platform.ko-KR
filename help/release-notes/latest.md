---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1b39449fa58157fb61d619de82235cba326ffe2c
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 54%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2024년 3월)

**마지막 업데이트**: 2024년 3월 8일 토요일

이 릴리스 노트는 2024년 3월 13일부터 2024년 4월까지의 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **프로젝트 랜딩 페이지에서 사용할 수 있는 새 열** | 다음 **[!UICONTROL 마지막으로 사용한 날짜]** 이제 의 프로젝트 탭을 볼 때 열을 사용할 수 있습니다. [Customer Journey Analytics 랜딩 페이지](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html). 이 정보는 프로젝트를 마지막으로 연 날짜와 시간을 표시하여 프로젝트가 조직의 사용자에게 중요한지 여부를 확인하는 데 도움이 될 수 있습니다. 이전에는 **[!UICONTROL 마지막으로 사용한 날짜]** 열은 계산된 지표 관리자, 세그먼트 관리자 및 경고 관리자에서만 사용할 수 있습니다. |  | 2024년 3월 13일 |
| **사용량 지표** | 사용량 지표 인터페이스는 모든 연결에서 수집되고 보고 가능한 행의 사용량을 보여 줍니다. 이 인터페이스를 사용하면 Customer Journey Analytics 사용량이 계약상 합의된 내용을 준수하는지 여부를 확인할 수 있습니다. |  | 2024년 3월 13일 |
| **Media Analytics 보고 - 대상자 분당 평균 시청 시간(AMA)** | 이제 대상자 분당 평균 시청 시간 패널을 CJA에서 사용할 수 있습니다. Media Analytics 고객은 대상자 분당 평균 시청 시간 패널을 사용하여 콘텐츠의 평균 소비에 대해 더 잘 이해할 수 있습니다. 분당 평균 시청 시간을 통해 모든 길이 또는 모든 장르의 프로그램을 비교할 수 있습니다. 또한 고객은 이 디지털 분당 평균 시청 시간을 유선 TV 평균 시청 시간 지표와 비교하거나 추가할 수 있습니다. 이 패널을 통해 기간 분류가 이후에 업데이트된 경우에도 사용자 정의 기간의 대상자 평균을 보다 유연하게 측정할 수 있습니다. |  | 2024년 3월 12일 |
| **개인 대 계정에 대한 B2B 스키마 변환** | Customer Journey Analytics B2B 보고 시나리오에서 개인 기반 조회를 더 잘 지원하도록 데이터 세트를 변환할 수 있습니다. 이 기능은 다음 클래스를 기반으로 하는 B2B 스키마의 데이터 세트에 사용할 수 있습니다.<ul><li>XDM 비즈니스 계정 사용자 관계</li><li>XDM 비즈니스 영업 기회 사용자 관계</li><li>XDM 비즈니스 마케팅 목록 멤버</li><li>XDM 비즈니스 캠페인 멤버</li></ul> | | 2024년 3월 26일 수요일 |
| **Adobe Product Analytics: 단일 단계 내에서 이벤트 비교** | 단계: 마찰 보기에서 이제 단일 단계 단계 내의 이벤트를 비교할 수 있습니다. 이 기능은 여정에 단계 선택 사항이나 A/B 실험이 실행되는 단계가 있는 경우 특히 유용합니다. | 2024년 3월 29일 토요일 | 2024년 4월 12일 토요일 |
| **관리자는 조직의 모든 위치를 관리할 수 있습니다.** | 위치 페이지의 새 옵션을 사용하여 관리자는 조직의 모든 위치를 보고 관리할 수 있습니다. 이전에는 관리자가 생성한 위치만 보고 관리할 수 있었습니다. | | 2024년 4월 |
| **대상은 Experience Platform의 새 &quot;대상&quot; 섹션에 게시됩니다.** | Customer Journey Analytics에서 게시한 대상은 이제 Experience Platform의 새 &quot;대상&quot; 섹션에서 사용할 수 있습니다. 이전에는 Customer Journey Analytics에서 게시한 대상자를 플랫폼에서 &quot;세그먼트&quot; 섹션 아래서 사용할 수 있었습니다. 이 개선 사항은 다음과 같은 이점을 제공합니다.<ul><li>대상은 더 이상 플랫폼에 표시되기 전에 1시간 지연이 없습니다. 게시된 후 몇 초 후에 사용할 수 있습니다.</li><li>대상이 원래 게시된 애플리케이션을 표시하는 &quot;원본&quot; 열을 사용하여 플랫폼에서 대상을 정렬할 수 있습니다.</li><li>플랫폼의 필터 및 정렬 옵션을 사용하면 관련 대상자를 더 빨리 찾을 수 있습니다.</li></ul>자세한 내용은 섹션을 참조하십시오 [Experience Platform에서 Customer Journey Analytics 대상 사용](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=en#audiences-aep). |  | 2024년 4월 |
| **Experience Edge 봇 탐지** | [봇 탐지](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) 기능을 사용하면 Web SDK, Mobile SDK 및 Server API에서 생성된 이벤트가 알려진 스파이더 및 봇에 의해 생성된 것으로 식별할 수 있습니다. | | 2024년 4월 29일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-340429; AN-341544; AN-341974; AN-342176; AN-342391

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **데이터 보기 및 연결 UI의 링크 업데이트됨** | 2월 15일 | 3월 초에 Adobe는 Customer Journey Analytics 제품 사용자 인터페이스에서 다음 링크를 업데이트할 계획입니다. 이에 따라 책갈피를 업데이트하십시오.<ul><li>**데이터 보기 페이지, 데이터 보기 관리자**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**새 데이터 보기 만들기**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**데이터 보기 편집**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [새 링크](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**연결 관리자**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**연결 정보**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**연결 편집**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**새 연결 만들기**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| Adobe API 오브젝트 멤버 추가 | 2024년 1월 17일 | Adobe는 버전 관리에 대한 공지나 변경 없이 기존 API 오브젝트에 선택적 요청 및 응답 멤버(이름/값 쌍)를 추가할 수 있습니다. 이들 추가 사항은 구현을 위해 중단하는 변경 사항이 아니어야 합니다. Adobe에서는 이들 추가 사항이 이해되지 않는 경우 처리 시 무시되도록 Adobe API와 통합하는 서드파티 도구의 API 설명서를 참조할 것을 권장합니다. Adobe는 릴리스 정보를 통해 제공하는 표준 알림 없이 매개변수를 제거하거나 필수 매개변수를 추가하지 않습니다. |

{style="table-layout:auto"}

## 관련 리소스

* [2023년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2023.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko-KR)
* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
