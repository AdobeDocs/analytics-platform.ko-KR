---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 466b4e22ba39197208a191a7298bf37a0b3e36c8
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 100%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2024년 7월)

**마지막 업데이트**: 2024년 8월 7일 목요일

이번 릴리스 정보에는 2024년 7월 17일부터 8월까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **지능형 경고** | 이제 Customer Journey Analytics에서 지능형 경고를 사용하면 데이터에 비정상적인 이벤트 발생 시 즉시 알림을 받게 됩니다.<p>예외 항목 임계값, 백분율 변경 또는 특정 데이터 포인트를 기준으로 지능형 경고가 트리거되도록 설정할 수 있습니다. 경고는 예외 항목 탐지 기능과 통합하여 필요 시 트리거되는 세부적인 제어를 제공합니다.</p><p>Customer Journey Analytics에서 지능형 경고의 사용 프로세스는 Adobe Analytics에서 지능형 경고의 사용 프로세스와 거의 동일합니다. 한 가지 주요 차이점은 시간별 경고는 Customer Journey Analytics에서 사용할 수 없다는 것입니다. 이러한 차이는 가져올 수 있는 다양한 이벤트 데이터에 대한 데이터 수집이 일반적으로 데이터 이벤트 시간보다 3~9시간 정도 지연된 이후에 완료되기 때문입니다.</p><p>(업데이트된 설명서 링크)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | TBD |
| **클라우드로 보고서 내보내기에 사용되는 계정 및 위치를 제어하는 관리자 설정** | 관리자는 [위치 관리자의 새로운 “관리자 설정” 탭](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only)을 통해 사용자가 계정과 위치를 생성하고 편집할 수 있는지 여부를 제어할 수 있습니다.<p>이러한 설정은 사용자가 [클라우드 내보내기 계정을 구성](/help/components/exports/cloud-export-accounts.md)하고 [클라우드 내보내기 위치를 구성](/help/components/exports/cloud-export-locations.md)할 때 적용됩니다.</p><p>관리자는 사용자가 만들고 사용할 수 있는 계정 유형을 제한할 수도 있습니다. 계정 유형에는 Google Cloud Platform, Azure RBAC, Amazon S3, AEP Data Landing Zone, Snowflake 등이 포함됩니다.</p><p>이전에는 모든 사용자가 모든 유형의 계정에 대해 계정과 위치를 만들고, 편집하고, 사용할 수 있었습니다.</p> | 2024년 7월 11일 | 2024년 7월 19일 |
| **요약 수준 데이터 소스** | 개인 ID가 없는 시계열 데이터를 가져올 수 있습니다. 이 시계열 데이터를 사용하여 다음과 같은 다양한 사용 사례를 지원할 수 있습니다.<ul><li>이벤트 수준 데이터의 일부 또는 거의 유사한 높은 수준의 성과 지표를 제공합니다. 여기에는 날짜 및 단일 지표 값 등 간단한 항목이 포함되거나 광고 노출 횟수, 이메일 열기, 광고 비용, 매출 원가 등 여러 차원 항목 및 지표가 포함될 수 있습니다.</li><li>일일, 주간, 월간, 분기별로 대상이나 목표를 업로드하고 이벤트 수준 지표에 대한 해당 대상이나 목표를 지정하여 조직의 대상 또는 목표에 대한 지표의 추세를 시각화하는 데 도움을 줍니다.</li></ul><p>(업데이트된 설명서 링크)</p> |  | 2024년 8월 11일 월요일 |
| **파생 필드 - 중복 제거 함수** | 파생 필드의 [중복 제거 함수](/help/data-views/derived-fields/derived-fields.md#deduplicate) 을 사용하면 값이 여러 번 계산되는 것을 방지하는 데 도움이 됩니다. |  | 2024년 7월 17일 |
| **CJA 고객을 위한 안내식 분석 프로비저닝** | 안내식 분석을 이용하면 사용자는 Customer Journey Analytics의 교차 채널 데이터를 기반으로 구축된 안내식 워크플로를 통해 고객 여정에 대한 고품질 데이터와 인사이트를 직접 얻을 수 있습니다. <p>마케팅부터 제품까지 다양한 부서의 팀이 실시간으로 교류하여 이러한 보고서를 사용하고 이해할 수 있습니다.</p><p>이제 CJA 패키지 내에서 최대 11개의 안내식 분석 보기를 사용할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 2024년 7월 17일 |
| **내보내기 및 가져오기에 사용되는 계정 및 위치 공유** | 이제 사용자는 자신이 만든 계정과 위치를 조직의 모든 사용자가 사용할 수 있도록 할 수 있습니다. 계정 및 위치 소유자와 시스템 관리자만 계정과 위치를 편집하고 삭제할 수 있습니다. 이전에는 계정과 위치를 생성한 사용자만 사용할 수 있었습니다. 이러한 설정은 사용자가 [클라우드 내보내기 계정을 구성](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)하고 [클라우드 내보내기 위치를 구성](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)할 때 사용할 수 있습니다. | 2024년 6월 12일 | 2024년 7월 19일 |
| **대상자가 Experience Platform의 새로운 “대상자” 섹션에 게시됨** | 이제 Customer Journey Analytics에서 게시된 대상자를 Adobe Experience Platform의 새로운 “대상자” 섹션에서 사용할 수 있습니다.<p>이전에는 Customer Journey Analytics에서 게시된 대상자를 Experience Platform의 “세그먼트” 섹션에서 사용할 수 있었습니다.</p><p>이 개선 사항은 다음과 같은 이점이 있습니다.</p><ul><li>대상자가 더 이상 1시간의 지연 없이 Experience Platform에 표시됩니다. 게시된 지 몇 초면 사용할 수 있습니다.</li><li>Experience Platform에서 대상자가 원래 게시된 애플리케이션을 표시하는 “원본” 열을 사용하여 대상자를 정렬할 수 있습니다.</li><li>Experience Platform의 필터링 및 정렬 옵션을 사용하여 해당 대상자를 보다 빨리 찾을 수 있습니다.</li></ul> <p>(참조할 설명서 링크)</p> | 2024년 8월 14일 목요일 | 2024년 8월 22일 금요일 |

{style="table-layout:auto"}

## Customer Journey Analytics의 수정 사항

AN-306000; AN-288748; AN-351547; AN-351110

## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 | | |

{style="table-layout:auto"}

## 관련 리소스

* [2024년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2024.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [스트리밍 미디어 컬렉션 추가 기능 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
