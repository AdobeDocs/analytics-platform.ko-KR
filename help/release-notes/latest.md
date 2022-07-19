---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f95aadbaa9cff775f51ed3d1f8bf9fe54adfd795
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 50%

---

# 현재 Customer Journey Analytics(CJA) 릴리스 노트(2022년 7월)

**마지막 업데이트**: 2022년 7월 19일

>[!NOTE]
>
>이 페이지에는 프리릴리스 정보가 포함되어 있으며 향후 변경될 수 있습니다.

## 주요 기능

| 기능 | 설명 | [목표 날짜](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| 숫자 필드를 조회 키 및 조회 값에 대해 지원 | 제품 SKU의 COGS 또는 여백과 같은 숫자 필드로 문자열 값을 분류하려는 경우에 유용합니다. 조회에서 지표를 허용하면 이러한 데이터 지점을 보고하는 데 도움이 됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | 2022년 7월 20일 |
| 미디어 동시 뷰어 패널 | 최대 동시성이 발생한 위치 또는 중단이 발생한 위치를 이해합니다. 콘텐츠 및 뷰어 참여의 품질에 대한 중요한 통찰력을 얻고 볼륨 및 규모에 대한 문제 해결 또는 계획을 수립하는 데 도움이 됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 2022년 7월 30일 |
| 미디어 재생 소요 시간 패널 | 미디어 재생 시간 을 사용하면 뷰어 참여에 대한 중요한 통찰력을 제공하고 미디어 조직이 시간대 지정 기능을 사용한 고급 체류 시간 분석을 통해 분 단위의 사용자 참여를 통해 보다 깊고 세분화된 통찰력을 얻을 수 있습니다. 특정 시점에 미디어 스트림을 보는 데 소요된 시간을 관찰할 수 있습니다. 새로운 5분, 15분, 30분 단위를 포함하여 다양한 단위로 재생 시간을 분할할 수 있습니다.  [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 2022년 7월 30일 |
| 첫 번째와 반복 세션 보고 | 이제 특정 세션이 사용자의 첫 번째 세션인지 확인할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 2022년 8월 17일 |


## 수정 사항

AN-288455; AN-288828; AN-289323

## CJA 관리자에 대한 중요 공지

| 공지 | 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 향상된 IP-지리적 위치 매핑 | 2022년 7월 11일 | Adobe의 IP 조회 공급업체인 Digital Element 는 IP-to-geolocation 매핑을 위해 향상된 데이터 세트(NetAcity Pulse)로 업그레이드하고 있습니다. Adobe Analytics은 2022년 10월, 시간대에 이 새로운 데이터 세트를 채택할 예정입니다. 새 데이터베이스가 이전 버전보다 더 정확할 것입니다. 일부 IP-지역 매핑은 새 데이터베이스가 채택되면 변경/개선됩니다.<p> Analytics 소스 커넥터를 통해 제공된 CJA 데이터도 새로운 매핑을 자동으로 활용할 수 있습니다. |

>[!MORELIKETHIS]
>[Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
