---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: abaa747934ff2cdd0a3dab867165afb46fbc71db
workflow-type: tm+mt
source-wordcount: '945'
ht-degree: 43%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2024년 4월)

**마지막 업데이트**: 2024년 4월 17일 목요일

이 릴리스 정보는 2024년 4월 10일부터 2024년 5월의 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **스트리밍 미디어: Adobe Experience Platform Edge로 Roku 데이터 보내기** | 다음 경우에 [Experience Platform 에지로 Media Analytics 설치](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), Adobe Experience Platform Roku SDK를 사용하여 스트리밍 미디어 데이터를 Adobe Experience Platform으로 전송할 수 있습니다. |  | 2024년 4월 12일 |
| **보고 활동 관리자에서 노출된 월별 보고서** | 이제 보고 활동 관리자에서 모든 연결에 대한 보고 활동을 볼 때 다음을 보여주는 그래프를 사용할 수 있습니다 [월별 보고서/요청](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) 현재 달과 이전 달 모두에 대해 IMS 조직 수준에서 실행되었습니다.<p>**참고:** 데이터는 2024년 3월 중간에 제공됩니다. | | 2024년 4월 15일 화요일 |
| **모바일 스코어카드의 지능형 캡션** | [지능형 캡션](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)은 비분석가가 분석가의 도움 없이도 데이터를 더 잘 이해할 수 있도록 도와줍니다. 이제 Customer Journey Analytics 스코어카드에서 사용할 수 있습니다. |  | 2024년 4월 17일 |
| **프로젝트 전용의 권한 개선 [!UICONTROL 작업 영역] 구성 요소** | 이전에는 한 사용자(사용자 A)가 다른 사용자(사용자 B)와 프로젝트를 공유하고 사용자 B에게 프로젝트에 대한 편집 액세스 권한을 부여하면 사용자 B가 프로젝트를 편집할 수 있었습니다. 그러나 사용자 B는 편집할 수 없습니다 [!UICONTROL 빠른 세그먼트] 프로젝트에 포함됨. 이제 해당 제한이 제거됨 - 사용자 B가 편집할 수 있음 [!UICONTROL 빠른 세그먼트] 공유 프로젝트에 포함된 다른 프로젝트 전용 구성 요소 |  | 2024년 4월 17일 |
| **관리자가 조직의 모든 위치 관리 가능** | 에 대한 새 옵션 [위치 페이지](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) 을 통해 관리자는 조직의 모든 위치를 보고 관리할 수 있습니다. 이전에는 관리자가 자신이 만든 위치만 보고 관리할 수 있었습니다. |  | 2024년 4월 17일 |
| **Adobe Product Analytics: 기능 매트릭스** | 핵심, 동력, 일회성, 의문스러운 특징이 무엇인지 이해하여 투자 결정을 유도합니다. [!UICONTROL 기능 매트릭스] 사용 빈도와 활성 사용자(%)별로 이벤트를 측정하고 평균 사용량과 비교합니다. | 2024년 4월 17일 | 2024년 4월 30일 |
| **Adobe Product Analytics: 단계의 Enhanced Insights** | 다음에서 [마찰](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) 보기, 작성된 인사이트가 카테고리, 델타 및 설명을 포함하도록 개선되어 차트 및 표를 더 잘 이해할 수 있습니다. | 2024년 4월 17일 | 2024년 4월 26일 토요일 |
| **Adobe Product Analytics: 향상된 보존 보기** | 몇 가지 기능이 [유지](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/retention/retention-rates) 보다 심층적이고 맞춤화가 가능한 유지 통찰력을 도출하기 위한 속도 보기:<ul><li>시작 및 반환 이벤트 연결 해제</li><li>단일 보기에서 여러 반환 이벤트 비교</li><li>각(경계) 및 괄호 설정에 대해 설정 또는 후(경계 없음)에 적용된 보존 모델 사용자 정의</li><li>차트에서 개별 집단 행 표시 및 숨기기</li></ul> | 2024년 4월 24일 목요일 | 2024년 5월 8일 목요일 |
| **Adobe Product Analytics: 단일 이동 단계 내에서 이벤트 비교** | 이제 의 단일 단계 단계에서 이벤트를 비교할 수 있습니다. [마찰](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) 보기. 이는 여정에 단계 옵션이 있거나 A/B 실험이 실행되는 단계가 있는 경우 특히 유용합니다. | 2024년 4월 23일 수요일 | 2024년 5월 3일 토요일 |
| **개인에서 계정으로의 B2B 스키마 변환** | Customer Journey Analytics B2B 보고 시나리오에서 개인 기반 조회를 더 효과적으로 지원하도록 데이터 세트를 변환할 수 있습니다. 이 기능은 다음 클래스를 기반으로 하는 B2B 스키마용 데이터 세트에 사용할 수 있습니다.<ul><li>XDM 비즈니스 계정 사용자 관계</li><li>XDM 비즈니스 영업 기회 사용자 관계</li><li>XDM 비즈니스 마케팅 목록 멤버</li><li>XDM 비즈니스 캠페인 멤버</li></ul> | | 2024년 5월 1일 목요일 |
| **Experience Edge 봇 탐지** | [봇 탐지](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=ko-KR) 기능을 사용하면 Web SDK, Mobile SDK 및 Server API에서 생성된 이벤트가 알려진 스파이더 및 봇에 의해 생성된 것으로 식별할 수 있습니다. | | 2024년 5월 1일 목요일 |
| **파생 필드: 다음 또는 이전 함수** | 이러한 새로운 기능을 사용하면 필드를 입력으로 가져온 다음 n-이전 또는 n-다음 값을 식별하여 사용자 여정을 더 잘 볼 수 있습니다. 이 기능은 의 다른 함수와 결합할 수도 있습니다 [!UICONTROL 파생 필드], 예: [!UICONTROL 연결]을 눌러 새 차원을 생성합니다. |  | 2024년 5월 1일 목요일 |
| **대상자가 Experience Platform의 새로운 “대상자” 섹션에 게시됨** | Customer Journey Analytics에서 게시한 대상은 이제 Adobe Experience Platform의 새 &quot;대상&quot; 섹션에서 사용할 수 있습니다.<p>이전에는 Customer Journey Analytics에서 게시한 대상자를 &quot;세그먼트&quot; 섹션 아래의 Experience Platform에서 사용할 수 있었습니다.</p><p>이 개선 사항은 다음과 같은 이점이 있습니다.</p><ul><li>대상은 더 이상 Experience Platform에 표시되기 전에 1시간 지연되지 않습니다. 대상은 게시된 후 몇 초 후에 사용할 수 있습니다.</li><li>원래 대상이 게시된 애플리케이션을 표시하는 &quot;원본&quot; 열을 사용하여 Experience Platform에서 대상을 정렬할 수 있습니다.</li><li>Experience Platform의 필터 및 정렬 옵션을 사용하면 관련 대상자를 더 빨리 찾을 수 있습니다.</li></ul> |  | 2024년 5월 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-319662, AN-337894, AN-338469, AN-340147, AN-340200, AN-340443, AN-341594, AN-342442, AN-342976, AN-343020, AN-343469, AN-343703, AN-343938, AN-344614, AN-344677,

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **데이터 보기 및 연결 UI의 링크 업데이트됨** | 2월 15일 | 3월 초에 Adobe는 Customer Journey Analytics 제품 사용자 인터페이스에서 다음 링크를 업데이트할 계획입니다. 이에 따라 책갈피를 업데이트하십시오.<ul><li>**데이터 보기 페이지, 데이터 보기 관리자**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**새 데이터 보기 만들기**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**데이터 보기 편집**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [새 링크](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**연결 관리자**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**연결 정보**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**연결 편집**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**새 연결 만들기**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |

{style="table-layout:auto"}

## 관련 리소스

* [2024년 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2024.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko-KR)
* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ko-KR)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko-KR)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
