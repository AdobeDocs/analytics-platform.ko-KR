---
description: 기존 내보내기에 대한 로그 관리
keywords: Analysis Workspace
title: 실패한 내보내기 문제 해결
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 8%

---

# 실패한 내보내기 문제 해결

[Analysis Workspace에서 클라우드 대상으로 전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md)를 수행하는 경우 [내보내기 탭](/help/components/exports/manage-exports.md) 및 [로그 탭](/help/components/exports/manage-export-logs.md)에서 이러한 내보내기 상태를 확인할 수 있습니다. 내보내기에 실패한 경우 [!UICONTROL **실패**] 상태가 표시됩니다.

## 일반적인 실패 및 작업

다양한 이유로 내보내기가 실패할 수 있습니다. 다음 표에서는 오류를 해결하기 위해 수행할 수 있는 작업과 함께 가장 일반적인 이유 중 일부를 설명합니다.

| 실패 이유 | 제안된 작업 | 추가 정보 |
|---------|----------|---------|
| 잘못된 위치 또는 계정 정보 | 내보내는 클라우드 계정 및 위치에 대한 자격 증명 및 기타 정보가 올바른지 확인하십시오. | [클라우드 내보내기 계정을 구성](/help/components/exports/cloud-export-accounts.md) 및 [클라우드 내보내기 위치를 구성](/help/components/exports/cloud-export-locations.md)합니다. |
| 보고서의 차원 또는 지표가 데이터 보기에서 제거되었습니다 | 데이터 보기에서 제거된 구성 요소를 확인하려면 시스템 관리자에게 문의하십시오. 내보내기에서 다른 데이터 보기를 사용하거나 더 이상 사용할 수 없는 구성 요소를 테이블에서 제거해야 할 수 있습니다. | [클라우드로 Customer Journey Analytics 보고서 내보내기](/help/analysis-workspace/export/export-cloud.md) |
| 행 제한 초과됨 | 라이선스 유형에 따라 최대 300만, 3000만, 1억 5000만 또는 3억 개의 행을 내보낼 수 있습니다. 내보내려는 테이블을 업데이트하여 총 행 수를 줄입니다. | [클라우드로 Customer Journey Analytics 보고서 내보내기](/help/analysis-workspace/export/export-cloud.md) |
| 예약된 내보내기 만료 | 구성한 예약된 내보내기가 만료되었습니다. 내보내기의 만료를 업데이트합니다. | [내보내기 관리](/help/components/exports/manage-exports.md) |
| Dimension이 지원되지 않음 | <p>다음 기준을 모두 충족하는 차원은 전체 테이블 내보내기에서 지원되지 않습니다.</p> <ul><li>개체 배열의 일부인 필드에서 만들어졌습니다.</li><li>지속성이 활성화됨<li>바인딩 차원을 사용하지 않음</li> | <ul><li>[ 개체 배열 사용 ](/help/use-cases/object-arrays.md)</li><li>[지속성 구성 요소 설정](/help/data-views/component-settings/persistence.md)<li>[Customer Journey Analytics에서 바인딩 차원 및 지표 사용](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| 조직에서 시행하는 데이터 거버넌스 정책은 테이블의 구성 요소 내보내기를 제한합니다 | 내보내기가 제한된 구성 요소를 확인하려면 시스템 관리자에게 문의하십시오. 내보내기 전에 제한된 구성 요소를 제거합니다. | *데이터 보기에서 데이터 거버넌스 정책 필터링* [레이블 및 정책](/help/data-views/data-governance.md) 섹션 |

## Adobe 고객 지원에 문의하십시오

문제가 계속 발생하면 Adobe 고객 지원 센터에 문의하십시오. 실패한 내보내기와 관련하여 고객 지원 센터에 문의할 때 다음 정보를 사용할 수 있는지 확인하십시오.

* 내보내기 이름

* 내보내기 ID

* 인스턴스 ID

* 데이터 보기 이름

* 위치

* 계정

* 연결

* 회사 이름
