---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 CJA 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a7636909c0570655ee6d3638e56828916044d2bd
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 77%

---

# Customer Journey Analytics(CJA) 릴리스 노트(2022년 10월/11월)

**마지막 업데이트**: 2022년 10월 19일

Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 제공 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 주요 기능 및 업데이트

| 기능 | 설명 | [롤아웃 시작](/help/release-notes/releases.md) | [일반 가용성](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **[!UICONTROL 주요 지표 요약] 시각화** | [!UICONTROL 주요 지표 요약] 시각화를 통해 단일 기간 내에서 중요한 지표의 추세를 확인할 수 있습니다. 또한 두 기간에 걸쳐 지표의 성능을 비교할 수 있습니다. [자세히 알아보기](/help/analysis-workspace/visualizations/key-metric.md) | 2022년 10월 5일 | 2022년 10월 19일 |
| **대소문자를 구분하지 않는 다중 값 변수** | 대소문자를 구분하지 않는 다중 값 변수의 경우 `mvvar1` - `mvvar3`에 저장된 값은 더 이상 자동으로 소문자로 변환되지 않습니다. 대신 Analytics Source Connector를 통해 Adobe Experience Platform 및 CJA로 전달된 데이터는 페이지에서 전달된 원래의 사례를 반영하게 됩니다. | 해당 사항 없음 | 2022년 10월 24일 |
| **CJA 감사 로그** | CJA(Customer Journey Analytics)을 사용하면 &quot;감사 로그&quot; 형태로 다양한 서비스 및 기능에 대한 사용자 활동을 감사할 수 있습니다. 이러한 로그는 문제를 해결하는 데 도움이 되는 감사 추적을 형성하며 HIPAA(Health Insurance Portability and Accountability Act)와 같은 기업 데이터 관리 정책 및 규정 요구 사항을 효과적으로 준수할 수 있도록 도와줍니다. 이러한 로그는 이전에는 감사 로그 API를 통해서만 사용할 수 있었습니다. [참조할 설명서] | 해당 사항 없음 | 2022년 10월 26일 |
| **HIPAA 준비** | 팔로우할 설명 | 해당 사항 없음 | 2022년 11월 7일 |

{style=&quot;table-layout:auto&quot;}

## 수정 사항

* 최신 MacOS 버전을 &quot;Macintosh&quot;로 잘못 지정한 문제가 해결되었습니다. 이 수정 사항을 사용하여 OS 차원은 MacOS 11부터 &quot;MacOS&quot; 버전 번호 지정을 사용하여 시작합니다. (AN-301834)

### 기타  수정 사항

AN-302367; AN-302562

## CJA 관리자를 위한 중요 공지

| 공지 | 추가 또는 업데이트된 알림 | 설명 |
| --- | --- | --- |
| **기본 랜딩 페이지** | 2023년 9월 29일 | 올해 초에 도입된 [새 랜딩 페이지](/help/getting-started/landing.md)는 **2023년 1월**&#x200B;에 모든 사용자의 기본 환경이 됩니다. 현재 페이지는 더 이상 사용되지 않으며 모든 사용자는 새 환경을 사용해야 합니다. |
| **개선된 IP-to-geolocation 매핑** | 2022년 9월 29일 | Adobe의 IP 조회 공급업체인 Digital Element는 IP-to-geolocation 매핑을 위해 새롭게 개선된 데이터 세트(NetAcuity Pulse)로 업그레이드하고 있습니다. Adobe Analytics는 이 새로운 데이터 세트의 채택을 **2023년 1월**&#x200B;로 연기했습니다. 새 데이터베이스는 이전 버전보다 더 정확합니다. 새 데이터베이스가 채택되면 일부 IP-to-geo 매핑이 변경 및 개선됩니다.<p> [!UICONTROL Analytics Source Connector]를 통해 제공되는 CJA 데이터도 자동으로 새 매핑을 활용합니다. |
| **[!UICONTROL 예외 항목 탐지] 자동 실행 조건** | 2022년 9월 29일 | 오늘, [!UICONTROL 예외 항목 탐지]가 시계열 자유 형식 테이블의 모든 열에서 자동 실행됩니다. 데이터를 분석에 사용할 수 있고 프로젝트를 더 빠르게 로드할 수 있도록 Adobe는 [!UICONTROL 예외 항목 탐지] 자동 실행 방식을 변경할 것입니다. **2022년 10월 26일**&#x200B;부터 예외 항목 탐지는 테이블의 첫 번째 지표 열에서만 자동 실행됩니다. 필요한 경우 다른 열에서 [!UICONTROL 예외 항목 탐지]를 실행하도록 열 설정을 구성할 수 있습니다. |

{style=&quot;table-layout:auto&quot;}


## 관련 리소스

* [2022년 이전 CJA 릴리스 정보](/help/release-notes/2022.md)

* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko-KR?lang=ko)

* [Media Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ko-KR)

* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko-KR)

* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
