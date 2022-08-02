---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b2a6225d6f94b158e217df4963611cb6d55580e
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 100%

---

# 현재 CJA(Customer Journey Analytics) 릴리스 정보 (2022년 7월)

**마지막 업데이트**: 2022년 7월 28일

## 주요 기능

| 기능 | 설명 | [목표 날짜](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| 숫자 필드를 조회 키 및 조회 값에 대해 지원 | 제품 SKU의 COGS 또는 여백과 같은 숫자 필드로 문자열 값을 분류하려는 경우에 유용합니다. 조회에서 지표를 허용하면 이러한 데이터 지점을 보고하는 데 도움이 됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | 2022년 7월 20일 |
| 첫 번째 세션 보고와 반복 세션 보고 비교 | 이제 특정 세션이 사용자의 첫 번째 세션인지 확인할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ko-kr#new-repeat) | 2022년 8월 17일 |
| 미디어 동시 뷰어 패널 | 최대 동시성이 발생한 위치 또는 중단이 발생한 위치를 이해합니다. 콘텐츠 및 뷰어 참여의 품질에 대한 중요한 통찰력을 얻고 볼륨 및 규모에 대한 문제 해결 또는 계획을 수립하는 데 도움이 됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 2022년 8월 31일 |
| 미디어 재생 소요 시간 패널 | 미디어 재생 소요 시간은 시청자 참여에 대한 가치 있는 통찰력을 제공하며 미디어 조직에서는 시간대 지정 기능이 있는 고급 소요 시간 분석을 통해 분 단위 사용자 참여에 대한 보다 심층적이고 세부적인 통찰력을 얻을 수 있습니다. 특정 시점에 미디어 스트림을 보는 데 소요된 시간을 관찰할 수 있습니다. 새로운 5분, 15분, 30분 단위를 포함하여 다양한 단위로 재생 시간을 분할할 수 있습니다.  [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 2022년 8월 31일 |

{style=&quot;table-layout:auto&quot;}

## 수정 사항

AN-288455; AN-288828; AN-289323

## CJA 관리자를 위한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **개선된 IP-to-geolocation 매핑** | 2022년 7월 11일 | Adobe의 IP 조회 공급업체인 Digital Element는 IP-to-geolocation 매핑을 위해 새롭게 개선된 데이터 세트(NetAcuity Pulse)로 업그레이드하고 있습니다. Adobe Analytics는 **2022년 10월**&#x200B;에 이 새로운 데이터 세트를 채택할 예정입니다. 새 데이터베이스는 이전 버전보다 더 정확합니다. 새 데이터베이스가 채택되면 일부 IP-to-geo 매핑이 변경 및 개선됩니다.<p> Analytics Source Connector를 통해 제공되는 CJA 데이터도 자동으로 새 매핑을 활용합니다. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
