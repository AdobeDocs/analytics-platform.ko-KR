---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: dea4a862f2e40e31bf96d0898418adfd7ca3a2f7
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 97%

---

# 현재 Adobe Customer Journey Analytics 릴리스 정보 (2024년 3월)

**마지막 업데이트**: 2024년 4월 10일 목요일

이번 릴리스 정보에는 2024년 3월 13일 목요일부터 2024년 4월까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **모바일 스코어카드의 지능형 캡션** | [지능형 캡션](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) 는 분석가의 도움 없이 비분석가가 데이터를 더 잘 이해할 수 있도록 도와줍니다. 이제 Customer Journey Analytics 스코어카드에서 사용할 수 있습니다. |  | 2024년 4월 17일 |
| **Workspace 프로젝트 삭제 프로토콜 변경** | 기존에는 삭제된 Workspace 프로젝트가 시스템에서 제거되지 않았습니다. 이제 180일이 지나면 삭제된 프로젝트의 제거가 시작됩니다. 사용자는 해당 프로젝트로의 URL이 있는 경우 삭제 후 180일 동안 웹 인터페이스를 통해 삭제된 프로젝트에 계속 액세스할 수 있습니다. | | 2024년 3월 14일 |
| **‘프로젝트’ 랜딩 페이지에서 새로운 열 사용 가능** | 이제 [Customer Journey Analytics 랜딩 페이지](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=ko-KR)에서 ‘프로젝트’ 탭을 볼 때 **[!UICONTROL 마지막 사용]** 열을 사용할 수 있습니다. <p>이 정보는 프로젝트를 마지막으로 연 일자와 시간을 표시해 주므로 프로젝트가 조직의 사용자에게 가치가 있는지 여부를 판단하는 데 도움이 될 수 있습니다. 이전에는 계산된 지표 관리자, 세그먼트 관리자 및 경고 관리자만 **[!UICONTROL 마지막 사용]** 열을 사용할 수 있었습니다.</p> |  | 2024년 3월 13일 |
| **사용량 지표** | [사용량 지표 인터페이스](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ko-KR)는 모든 연결에서 수집되고 보고 가능한 행의 사용량을 보여 줍니다. 이 인터페이스를 사용하면 Customer Journey Analytics 사용량이 계약상 합의된 내용을 준수하는지 여부를 확인할 수 있습니다. |  | 2024년 3월 13일 |
| **Media Analytics 보고 - 대상자 분당 평균 시청 시간 (AMA)** | 이제 대상자 분당 평균 시청 시간 패널을 CJA에서 사용할 수 있습니다. Media Analytics 고객은 대상자 분당 평균 시청 시간 패널을 사용하여 콘텐츠의 평균 소비에 대해 더 잘 이해할 수 있습니다. <p>분당 평균 시청 시간을 통해 모든 길이 또는 모든 장르의 프로그램을 비교할 수 있습니다. 또한 고객은 이 디지털 분당 평균 시청 시간을 유선 TV 평균 시청 시간 지표와 비교하거나 추가할 수 있습니다.</p><p> 이 패널을 통해 기간 분류가 이후에 업데이트된 경우에도 사용자 정의 기간의 대상자 평균을 보다 유연하게 측정할 수 있습니다.</p><p>자세한 내용은 [미디어 대상자 분당 평균 시청 시간 패널](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)을 참조하십시오.</p> |  | 2024년 3월 12일 |
| **개인에서 계정으로의 B2B 스키마 변환** | Customer Journey Analytics B2B 보고 시나리오에서 개인 기반 조회를 더 효과적으로 지원하도록 데이터 세트를 변환할 수 있습니다. 이 기능은 다음 클래스를 기반으로 하는 B2B 스키마용 데이터 세트에 사용할 수 있습니다.<ul><li>XDM 비즈니스 계정 사용자 관계</li><li>XDM 비즈니스 영업 기회 사용자 관계</li><li>XDM 비즈니스 마케팅 목록 멤버</li><li>XDM 비즈니스 캠페인 멤버</li></ul> | | 2024년 4월 17일 |
| **계산된 지표 관리자 및 필터 관리자의 “다음에서 사용” 열에 포함된 Report Builder 사용량** | 이제 Report Builder에 대해 계산된 지표 관리자 또는 필터 관리자의 **다음에서 사용** 열을 조회할 때 사용량 데이터를 확인할 수 있습니다.<p>이전에는 필터 관리자의 사용량 데이터는 경고, 프로젝트, 예약된 프로젝트 및 계산된 지표에 대해서만 사용할 수 있었으며, 계산된 지표 관리자의 사용량 데이터는 경고, 프로젝트 및 예약된 프로젝트에 대해서만 사용할 수 있었습니다.</p> |  | 7월 |
| **Adobe Product Analytics: 단일 이동 단계 내에서 이벤트 비교** | ‘이동: 마찰’ 보기에서 이제 단일 이동 단계 내의 이벤트를 비교할 수 있습니다. 이는 여정에 단계 옵션이 있거나 A/B 실험이 실행되는 단계가 있는 경우 특히 유용합니다. | 2024년 3월 29일 | 2024년 4월 12일 |
| **관리자가 조직의 모든 위치 및 계정 관리 가능** | 위치 탭(구성 요소 > 내보내기 페이지)의 새로운 옵션을 통해 관리자가 조직의 모든 위치를 보고 관리할 수 있습니다. <p>위치 계정 탭(구성 요소 > 내보내기 페이지)의 새로운 옵션을 통해 관리자가 조직의 모든 계정을 보고 관리할 수 있습니다.</p><p>이전에는 관리자가 자신이 만든 위치 및 계정만 보고 관리할 수 있었습니다.</p> | | 2024년 4월 |
| **대상자가 Experience Platform의 새로운 “대상자” 섹션에 게시됨** | 이제 Customer Journey Analytics에서 게시된 대상자를 Experience Platform의 새로운 “대상자” 섹션에서 사용할 수 있습니다. 이전에는 Customer Journey Analytics에서 게시된 대상자를 Platform의 “세그먼트” 섹션에서 사용할 수 있었습니다. 이 개선 사항은 다음과 같은 이점이 있습니다.<ul><li>대상자가 더 이상 1시간의 지연 없이 Platform에 표시됩니다. 게시된 지 몇 초면 사용할 수 있습니다.</li><li>Platform에서 대상자가 원래 게시된 애플리케이션을 표시하는 “원본” 열을 사용하여 대상자를 정렬할 수 있습니다.</li><li>Platform의 필터링 및 정렬 옵션을 사용하여 해당 대상자를 더 빨리 찾을 수 있습니다.</li></ul>자세한 내용은 [Experience Platform에서 Customer Journey Analytics 대상자 사용](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=ko-KR#audiences-aep) 섹션을 참조하십시오. |  | 2024년 4월 |
| **Experience Edge 봇 탐지** | [봇 탐지](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=ko-KR) 기능을 사용하면 Web SDK, Mobile SDK 및 Server API에서 생성된 이벤트가 알려진 스파이더 및 봇에 의해 생성된 것으로 식별할 수 있습니다. | | 2024년 4월 29일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-340429; AN-341544; AN-341974; AN-342176; AN-342391

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **데이터 보기 및 연결 UI의 링크 업데이트됨** | 2월 15일 | 3월 초에 Adobe는 Customer Journey Analytics 제품 사용자 인터페이스에서 다음 링크를 업데이트할 계획입니다. 이에 따라 책갈피를 업데이트하십시오.<ul><li>**데이터 보기 페이지, 데이터 보기 관리자**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**새 데이터 보기 만들기**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**데이터 보기 편집**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [새 링크](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**연결 관리자**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**연결 정보**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**연결 편집**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**새 연결 만들기**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| Adobe API 오브젝트 멤버 추가 | 2024년 1월 17일 | Adobe는 버전 관리에 대한 공지나 변경 없이 기존 API 오브젝트에 선택적 요청 및 응답 멤버(이름/값 쌍)를 추가할 수 있습니다. 이들 추가 사항은 구현을 위해 중단하는 변경 사항이 아니어야 합니다. Adobe에서는 이들 추가 사항이 이해되지 않는 경우 처리 시 무시되도록 Adobe API와 통합하는 서드파티 도구의 API 설명서를 참조할 것을 권장합니다. Adobe는 릴리스 정보를 통한 표준 알림 없이 매개변수를 제거하거나 필수 매개변수를 추가하지 않습니다. |

{style="table-layout:auto"}

## 관련 리소스

* [2023년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2023.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko-KR)
* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ko-KR)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko-KR)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
