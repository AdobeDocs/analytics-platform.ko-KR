---
title: 현재 Customer Journey Analytics 릴리스 정보 보기
description: 최신 Customer Journey Analytics 릴리스 정보
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7d915fc9b50163b7ec9c48232b99a85a3b063a77
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 51%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2024년 7월)

**마지막 업데이트**: 2024년 7월 17일 목요일

이 릴리스 정보는 2024년 7월 17일부터 2024년 8월의 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 제공 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **지능형 알림** | 이제 Customer Journey Analytics에서 지능형 경고를 사용할 수 있으므로 데이터에서 비정상 이벤트가 발생할 때 즉시 알림을 받을 수 있습니다.<p>예외 항목 임계값, 변경된 백분율 또는 특정 데이터 포인트를 기반으로 트리거되도록 경고를 설정할 수 있습니다. 경고는 예외 항목 탐지와 통합되는 세분화된 제어를 제공하여 가장 필요할 때 트리거합니다.</p><p>Customer Journey Analytics에서 지능형 경고를 사용하는 프로세스는 Adobe Analytics에서 지능형 경고를 사용하는 프로세스와 거의 동일합니다. 한 가지 주요 차이점은 Customer Journey Analytics에서 시간별 경고를 사용할 수 없다는 것입니다. 이러한 차이는 수집할 수 있는 다양한 종류의 이벤트 데이터에 대한 데이터 수집은 지연 후에만 완료되며 일반적으로 데이터 이벤트 시간이 3~9시간 경과하기 때문입니다.</p><p>(참조할 설명서 링크가 업데이트되었습니다.)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 2024년 7월 26일 토요일 |
| **클라우드로 보고서 내보내기에 사용되는 계정 및 위치를 제어하는 관리자 설정** | 관리자는 [위치 관리자의 새로운 “관리자 설정” 탭](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only)을 통해 사용자가 계정과 위치를 생성하고 편집할 수 있는지 여부를 제어할 수 있습니다.<p>이러한 설정은 사용자가 [클라우드 내보내기 계정을 구성](/help/components/exports/cloud-export-accounts.md)하고 [클라우드 내보내기 위치를 구성](/help/components/exports/cloud-export-locations.md)할 때 적용됩니다.</p><p>관리자는 사용자가 만들고 사용할 수 있는 계정 유형을 제한할 수도 있습니다. 계정 유형에는 Google Cloud Platform, Azure RBAC, Amazon S3, AEP Data Landing Zone, Snowflake 등이 포함됩니다.</p><p>이전에는 모든 사용자가 모든 유형의 계정에 대해 계정과 위치를 만들고, 편집하고, 사용할 수 있었습니다.</p> | 2024년 7월 11일 | 2024년 7월 19일 |
| **요약 수준 데이터 원본** | 개인 ID가 없는 시계열 데이터를 가져올 수 있습니다. 이 시계열 데이터는 다음과 같은 다양한 사용 사례를 지원하는 데 사용할 수 있습니다.<ul><li>이벤트 수준 데이터의 일부 또는 다음으로 높은 수준의 성과 지표 표시. 여기에는 날짜 및 단일 지표 값과 같은 간단한 항목을 포함하거나 광고 노출 횟수, 이메일 열기, 광고 지출, 매출 원가 등과 같은 여러 차원 및 지표를 포함할 수 있습니다.</li><li>일별, 주별, 월별 또는 분기별로 타겟 또는 목표를 업로드하고 이벤트 수준 지표에 대해 이러한 타겟 또는 목표를 포지셔닝하여 조직 타겟 또는 목표에 대한 지표의 추세를 시각화하는 데 도움이 됩니다.</li></ul><p>(참조할 설명서 링크가 업데이트되었습니다.)</p> |  | 2024년 7월 31일 목요일 |
| **파생 필드 - 중복 제거 함수** | 파생 필드의 [중복 제거 함수](/help/data-views/derived-fields/derived-fields.md#deduplicate)을(를) 사용하면 값을 여러 번 카운트하지 않도록 할 수 있습니다. |  | 2024년 7월 17일 목요일 |
| **CJA 고객을 위한 가이드 분석 프로비저닝** | 안내식 분석을 통해 사용자는 Customer Journey Analytics의 크로스 채널 데이터를 기반으로 구축된 안내식 워크플로우를 통해 고품질 데이터와 고객 여정에 대한 통찰력을 자체 제공할 수 있습니다. <p>마케팅부터 제품까지 다양한 부서의 팀이 실시간으로 교류하여 이러한 보고서를 사용하고 이해할 수 있습니다.</p><p>이제 CJA 패키지 내에서 최대 11개의 가이드 분석 보기를 사용할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 2024년 7월 17일 목요일 |
| **내보내기 및 가져오기에 사용되는 계정 및 위치 공유** | 이제 사용자는 자신이 만든 계정과 위치를 조직의 모든 사용자가 사용할 수 있도록 할 수 있습니다. 계정 및 위치 소유자와 시스템 관리자만 계정과 위치를 편집하고 삭제할 수 있습니다. 이전에는 계정과 위치를 생성한 사용자만 사용할 수 있었습니다. 이러한 설정은 사용자가 [클라우드 내보내기 계정을 구성](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)하고 [클라우드 내보내기 위치를 구성](https://experienceleague.adobe.com/kr/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)할 때 사용할 수 있습니다. | 2024년 6월 12일 | 2024년 7월 중순 |
| **대상자가 Experience Platform의 새로운 “대상자” 섹션에 게시됨** | 이제 Customer Journey Analytics에서 게시된 대상자를 Adobe Experience Platform의 새로운 “대상자” 섹션에서 사용할 수 있습니다.<p>이전에는 Customer Journey Analytics에서 게시된 대상자를 Experience Platform의 “세그먼트” 섹션에서 사용할 수 있었습니다.</p><p>이 개선 사항은 다음과 같은 이점이 있습니다.</p><ul><li>대상자가 더 이상 1시간의 지연 없이 Experience Platform에 표시됩니다. 게시된 지 몇 초면 사용할 수 있습니다.</li><li>Experience Platform에서 대상자가 원래 게시된 애플리케이션을 표시하는 “원본” 열을 사용하여 대상자를 정렬할 수 있습니다.</li><li>Experience Platform의 필터 및 정렬 옵션을 사용하면 관련 대상자를 더 빨리 찾을 수 있습니다.</li></ul> <p>(참조할 설명서 링크)</p> |  | TBD |

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
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko-KR)
* [스트리밍 미디어 컬렉션 추가 기능 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ko-KR)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko-KR)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
