---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a34ca124bac34912323e1a6c4d0b42f4b8cf2e86
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 59%

---

# 현재 Customer Journey Analytics(CJA) 릴리스 노트(2022년 8월)

**마지막 업데이트**: 2022년 8월 12일

## 주요 기능

| 기능 | 설명 | [목표 날짜](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **미디어 동시 뷰어 패널** | 최대 동시성이 발생한 위치 또는 중단이 발생한 위치를 이해합니다. 콘텐츠 및 뷰어 참여의 품질에 대한 중요한 통찰력을 얻고 볼륨 및 규모에 대한 문제 해결 또는 계획을 수립하는 데 도움이 됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 2022년 8월 9일 |
| **미디어 재생 소요 시간 패널** | 미디어 재생 소요 시간은 시청자 참여에 대한 가치 있는 통찰력을 제공하며 미디어 조직에서는 시간대 지정 기능이 있는 고급 소요 시간 분석을 통해 분 단위 사용자 참여에 대한 보다 심층적이고 세부적인 통찰력을 얻을 수 있습니다. 특정 시점에 미디어 스트림을 보는 데 소요된 시간을 관찰할 수 있습니다. 새로운 5분, 15분, 30분 단위를 포함하여 다양한 단위로 재생 시간을 분할할 수 있습니다.  [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 2022년 8월 9일 |
| **실시간 고객 프로필에 게시하는 대상** | 고객 타겟팅 및 개인화를 위해 CJA에서 검색된 대상을 Adobe Experience Platform/실시간 고객 프로필에 게시할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=ko-KR) | 2022년 8월 17일 |
| **데이터 거버넌스 레이블 및 정책에 대한 CJA 지원** | CJA와 Adobe Experience Platform 개인 정보 레이블 및 정책 간의 통합을 자동화합니다. 플랫폼에서 사용하는 데이터 세트에서 만든 데이터 레이블은 중요 필드에서 지표 및/또는 차원을 만드는 사용자를 중지하거나 경고하기 위해 CJA 데이터 보기에 표시됩니다. 또한 데이터를 CJA에서 내보낼 때(작업 공간 또는 Report Builder 보고, 내보내기, API 등을 통해) 보고서에 특정 방식으로 처리해야 하는 중요한 정보가 포함되어 있음을 사용자에게 알리는 추가 경고 또는 레이블이 추가됩니다. [자세히 알아보기](/help/data-views/data-governance.md) | 2022년 8월 17일 |
| **CJA의 날짜 필드 지원** | CJA에서 날짜 및 날짜 시간 필드에 대해 보고할 수 있습니다. [자세히 알아보기](/help/data-views/data-views-usecases.md#date) | 2022년 8월 17일 |
| **CJA용 실험 패널(일반 상승도 및 신뢰도)** | 이 새로운 작업 공간 패널을 사용하면 CJA 사용자가 Adobe 솔루션, Adobe Journey Optimizer 및 BYO 데이터에서 온라인, 오프라인 등 모든 소스 - 모든 A/B 실험의 향상도와 신뢰도를 평가할 수 있습니다. 추가 정보를 따르십시오. | 2022년 8월 24일 |
| **Analytics 소스 커넥터에 대한 지역 간 지원** | 이제 모든 지역(미국, 영국 또는 싱가포르)에서 보고서 세트를 수집할 수 있습니다. 하지만 이러한 보고서 세트는 소스 연결이 만들어지고 있는 Experience Platform 샌드박스 인스턴스와 동일한 조직에 매핑해야 합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko-kr) | 2022년 8월 24일 |
| **첫 번째 세션 보고와 반복 세션 보고 비교** | 이제 특정 세션이 사용자의 첫 번째 세션인지 확인할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ko-kr#new-repeat) | 2022년 8월 24일 |

{style=&quot;table-layout:auto&quot;}

## 수정 사항

AN-297141

## CJA 관리자를 위한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **개선된 IP-to-geolocation 매핑** | 2022년 7월 11일 | Adobe의 IP 조회 공급업체인 Digital Element는 IP-to-geolocation 매핑을 위해 새롭게 개선된 데이터 세트(NetAcuity Pulse)로 업그레이드하고 있습니다. Adobe Analytics은 이 새 데이터 세트를 **2022년 10월 일** 일정. 새 데이터베이스는 이전 버전보다 더 정확합니다. 새 데이터베이스가 채택되면 일부 IP-to-geo 매핑이 변경 및 개선됩니다.<p> Analytics Source Connector를 통해 제공되는 CJA 데이터도 자동으로 새 매핑을 활용합니다. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
