---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 94%

---

# 현재 Adobe Customer Journey Analytics 릴리스 정보(2024년 2월)

**마지막 업데이트**: 2024년 3월 5일 수요일

이번 릴리스 정보에는 2024년 2월 14일부터 2024년 3월까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **시계열 예측** | [예측](../analysis-workspace/c-forecast/forecasting.md)은 자유 형식 테이블 및 선 차트용으로 지원되는 시간 단위(시간별, 일별, 주별, 월별, 연간)를 사용하여 표준 또는 계산된 지표를 예측하는 새로운 Analysis Workspace 기능입니다. | 2024년 1월 31일 | 2024년 2월 21일 |
| **조회 및 프로필 데이터에 대한 행 수 지표** | 연결의 일부로 구성된 데이터 세트의 행 수 지표에 이제 프로필 및 조회 데이터 세트에서 추가되거나, 생략되거나, 삭제된 레코드가 포함됩니다. |  | 2024년 2월 14일 |
| **에지 네트워크 보트 탐지** | [보트 탐지](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) 웹 SDK, 모바일 SDK 및 서버 API에서 생성된 이벤트가 알려진 스파이더 및 보트에서 생성된 것으로 식별할 수 있습니다. | | 2024년 4월 29일 |
| **사용량 지표** | 사용량 지표 인터페이스는 모든 연결에서 수집되고 보고 가능한 행의 사용량을 보여 줍니다. 이 인터페이스를 사용하면 Customer Journey Analytics 사용량이 계약상 합의된 내용을 준수하는지 여부를 확인할 수 있습니다. | 2024년 2월 20일 | 2024년 3월 13일 목요일 |
| **Adobe Product Analytics: 모두와 공유** | Product Analytics에 액세스할 수 없는 사용자에게 Adobe Product Analytics 프로젝트에 대한 읽기 전용 링크를 공유할 수 있습니다. |  | 2024년 3월 말 |
| **Adobe Product Analytics: 계산된 지표 적용** | 이제 Analysis Workspace에서 만든 계산된 지표에 액세스하거나 추세: 사용량 보기의 계산된 지표 빌더에 액세스하여 시간 경과에 따른 지표의 추세를 파악하고 비교할 수 있습니다. |  | 2024년 2월 16일 |
| **데이터 보기 및 연결 UI의 링크 업데이트됨** | 3월 초에 Adobe는 Customer Journey Analytics 제품 사용자 인터페이스에서 다음 링크를 업데이트할 계획입니다. 이에 따라 책갈피를 업데이트하십시오.<ul><li>**데이터 보기 페이지, 데이터 보기 관리자**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**새 데이터 보기 만들기**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**데이터 보기 편집**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [새 링크](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**연결 관리자**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**연결 정보**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**연결 편집**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**새 연결 만들기**: [기존 링크](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [새 링크](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |  | 2024년 3월 |
| **Media Analytics 보고 - 대상자 분당 평균 시청 시간(AMA)** | 이제 대상자 분당 평균 시청 시간 패널을 CJA에서 사용할 수 있습니다. Media Analytics 고객은 대상자 분당 평균 시청 시간 패널을 사용하여 콘텐츠의 평균 소비에 대해 더 잘 이해할 수 있습니다. 분당 평균 시청 시간을 통해 모든 길이 또는 모든 장르의 프로그램을 비교할 수 있습니다. 또한 고객은 이 디지털 분당 평균 시청 시간을 유선 TV 평균 시청 시간 지표와 비교하거나 추가할 수 있습니다. 이 패널을 통해 기간 분류가 이후에 업데이트된 경우에도 사용자 정의 기간의 대상자 평균을 보다 유연하게 측정할 수 있습니다. |  | 2024년 3월 14일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-333172; AN-336887; AN-337402; AN-337593; AN-338482; AN-338684; AN-339883; AN-340200

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| Adobe API 오브젝트 멤버 추가 | 2024년 1월 17일 | Adobe는 버전 관리에 대한 공지나 변경 없이 기존 API 오브젝트에 선택적 요청 및 응답 멤버(이름/값 쌍)를 추가할 수 있습니다. 이들 추가 사항은 구현을 위해 중단하는 변경 사항이 아니어야 합니다. Adobe에서는 이들 추가 사항이 이해되지 않는 경우 처리 시 무시되도록 Adobe API와 통합하는 서드파티 도구의 API 설명서를 참조할 것을 권장합니다. Adobe는 릴리스 정보를 통해 제공하는 표준 알림 없이 매개변수를 제거하거나 필수 매개변수를 추가하지 않습니다. |

{style="table-layout:auto"}

## 관련 리소스

* [2023년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2023.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko-KR)
* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
