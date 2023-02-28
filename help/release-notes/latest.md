---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4e41bda273f0f7e93941bb00b55bffc6b357ac1f
workflow-type: ht
source-wordcount: '524'
ht-degree: 100%

---

# 최신 CJA(Customer Journey Analytics) 릴리스 정보 (2023년 2월)

**마지막 업데이트 날짜**: 2023년 2월 23일

Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 주요 기능 및 업데이트

| 기능 | 설명 | [롤아웃 시작](/help/release-notes/releases.md) | [일반 가용성](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **CJA 대상자 업데이트** | 대상자가 생성된 후 Adobe는 각각의 새로운 CJA 대상자에 대해 Experience Platform 스트리밍 세그먼트를 만듭니다. 스트리밍 세그먼트는 조직이 스트리밍 세그먼테이션에 대해 설정된 경우에만 생성됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created) | 해당 사항 없음 | 2023년 2월 3일 |
| **모바일 스코어카드에서 비교 날짜 범위 숨기기** | 이제 모바일 스코어카드를 사용하여 비교 날짜 범위를 숨길 수 있습니다. | 해당 사항 없음 | 2023년 2월 8일 |
| **Workspace의 캘린더 업데이트** | <ul><li>앵커 패널 날짜: 패널 캘린더를 기준으로 날짜 범위 구성 요소를 만들 수 있습니다. [자세히 알아보기](/help/components/date-ranges/calendar.md)</li><li>캘린더 스타일 업데이트: UI 전체의 캘린더 스타일이 업그레이드되어 보다 일관되고 사용하기 쉬운 워크플로를 제공합니다.</li><li>캘린더 수식 업데이트: 상대 날짜를 사용하는 경우 모든 캘린더 수식이 패널 날짜 범위의 시작을 반영합니다. [자세히 알아보기](/help/components/date-ranges/calendar.md)</li></ul> | 해당 사항 없음 | 2023년 2월 8일 |
| **패널 날짜 범위 업데이트** | Workspace에서 다음 개선 사항이 추가되었습니다.<ul><li>2월 릴리스부터 구성 요소 및 데이터 미리보기는 지난 90일이 아닌 패널 날짜 범위를 기반으로 합니다. </li><li>왼쪽 레일에 나열된 모든 구성 요소는 패널 날짜 범위에 따라 사용할 수 있습니다.</li><li>세그먼트 및 계산된 지표 빌더의 모든 날짜 미리보기는 패널 날짜 범위를 기반으로 합니다(연결된 패널이 없는 구성 요소 관리자에서 액세스하지 않는 한 여전히 지난 90일을 기반으로 함).</li><li>모든 데이터 미리보기는 패널 날짜 범위를 기반으로 데이터 또는 구성 요소를 표시합니다.</li></ul> | 해당 사항 없음 | 2023년 2월 8일 |
| **Adobe Analytics 소스 커넥터 스트리밍을 위한 행/열 필터링** | 이제 Adobe Experience Platform의 Analytics 소스 커넥터를 통해 [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko)에 프로필을 채우는 데 사용되는 Analytics 데이터를 필터링할 수 있습니다.<p>행 수준 필터링은 프로필과 관련된 이벤트 수를 줄이는 데 도움이 됩니다. 열 수준 필터링은 이벤트 자체의 내용을 줄이는 데 도움이 되므로 프로필 자격 사용을 최적화할 수 있습니다. 이 필터링은 실시간 고객 프로필 및 [ID 서비스](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ko-KR)로 전송된 데이터에만 적용됩니다.<p>**필터링은 Customer Journey Analytics와 같은 애플리케이션에서 사용하기 위해 데이터 레이크로 전송되는 데이터에 영향을 미치지 않습니다**. [자세히 알아보기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | 해당 사항 없음 | 2023년 3월 29일로 일정 변경 |

{style=&quot;table-layout:auto&quot;}

## Customer Journey Analytics의 수정 사항

AN-309106

## CJA 관리자를 위한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 공지 사항 없음 | 해당 사항 없음 | 해당 사항 없음 |

{style=&quot;table-layout:auto&quot;}

## 관련 리소스

* [2023년 이전 CJA 릴리스 정보](/help/release-notes/2023.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko-KR)
* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ko-KR)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko-KR)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
