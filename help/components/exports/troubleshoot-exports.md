---
description: 기존 내보내기에 대한 로그 관리
keywords: Analysis Workspace
title: 실패한 내보내기 문제 해결
feature: Components
hide: true
hidefromtoc: true
source-git-commit: eb7ba8dd7809164bdcddb0d484754376d5b7ca9e
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---

# 실패한 내보내기 문제 해결

다음을 수행하는 경우 [Analysis Workspace에서 클라우드 대상으로 전체 표 내보내기](/help/analysis-workspace/export/export-cloud.md)에서 해당 내보내기의 상태를 볼 수 있습니다. [내보내기 탭](/help/components/exports/manage-exports.md) 및 [로그 탭](/help/components/exports/manage-export-logs.md). 실패한 내보내기 상태는 다음과 같습니다. [!UICONTROL **실패**].

## 일반적인 실패 및 작업

다양한 이유로 내보내기가 실패할 수 있습니다. 다음 표에서는 오류를 해결하기 위해 수행할 수 있는 작업과 함께 가장 일반적인 이유 중 일부를 설명합니다.

| 실패 이유 | 제안된 작업 | 추가 정보 |
|---------|----------|---------|
| 잘못된 위치 또는 계정 정보 | 내보내는 클라우드 계정 및 위치에 대한 자격 증명 및 기타 정보가 올바른지 확인하십시오. | [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md) 및 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md). |
| 보고서의 차원 또는 지표가 데이터 보기에서 제거되었습니다 | 데이터 보기에서 제거된 구성 요소를 확인하려면 시스템 관리자에게 문의하십시오. 내보내기에서 다른 데이터 보기를 사용하거나 더 이상 사용할 수 없는 구성 요소를 테이블에서 제거해야 할 수 있습니다. | [클라우드로 Customer Journey Analytics 보고서 내보내기](/help/analysis-workspace/export/export-cloud.md) |
| 조직에서 시행하는 데이터 거버넌스 정책은 테이블의 구성 요소 내보내기를 제한합니다 | 내보내기가 제한된 구성 요소를 확인하려면 시스템 관리자에게 문의하십시오. 내보내기 전에 제한된 구성 요소를 제거합니다. | *데이터 보기에서 데이터 거버넌스 정책 필터링* 의 섹션 [레이블 및 정책](/help/data-views/data-governance.md) |

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