---
title: 대상 분석 개요
description: Customer Journey Analytics의 RTCDP에서 대상 분석에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 840bf65d186178fb944041ff486e95ba60dc6037
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---

# 대상 분석 개요

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md and this article: /help/analysis-workspace/templates/use-templates.md-->

>[!NOTE]
>
>대상 분석과 대상 게시의 차이점을 이해합니다.
>
>* **대상 분석**: Experience Platform 프로필 데이터 세트의 대상 멤버십 데이터를 Customer Journey Analytics 연결로 수집할 수 있습니다.
>* **대상 게시**: 고객 타기팅 및 개인화를 위해 Customer Journey Analytics에서 검색된 대상을 만들어 Adobe Experience Platform에 게시할 수 있습니다. 대상 게시에 대한 자세한 내용은 [대상 게시 개요](/help/components/audiences/audiences-overview.md)를 참조하십시오.

대상 분석을 사용하면 Experience Platform 프로필 데이터 세트의 대상 멤버십 데이터를 Customer Journey Analytics 연결로 수집할 수 있습니다. 대상은 Analysis Workspace에서 사용할 새 차원으로 사용할 수 있게 됩니다.

다음 다이어그램 및 관련 테이블은 Customer Journey Analytics의 대상 분석 구성을 통해 Experience Platform 대상 데이터를 Analysis Workspace에서 사용할 수 있게 되는 방법에 대한 높은 수준의 표현을 보여 줍니다.

![대상 분석 개요](assets/audience-analysis-overview.png)

| 숫자 | 기능 | 함수 |
|---------|----------|---------|
| 1 | 대상 분석 구성 | 대상 분석을 구성하는 데 사용되는 Customer Journey Analytics의 구성 인터페이스입니다. |
| 2 | 샌드박스 | 연결에 추가할 프로필 데이터 세트를 포함해야 합니다. |
| 3 | 프로필 데이터 세트 | 분석할 Experience Platform 대상 데이터를 포함해야 합니다. 이 프로필 데이터 세트는 선택한 연결에 추가됩니다. |
| 4 | 병합 정책 | 분석할 Experience Platform 대상과 연결된 병합 정책입니다. |
| 5 | 프로필 데이터 | 선택한 병합 정책과 연결된 프로필 데이터입니다. 이 데이터는 Experience Platform 데이터 세트 내에서 사용할 수 있습니다. |
| 6 | 새 조회 데이터 세트 | 새로 만든 대상 차원에 대해 친숙한 이름을 제공합니다. <p>조회 데이터 세트는 사용자가 선택한 프로필 데이터 세트와 함께 자동으로 생성되고 연결에 추가됩니다.</p> |
| 7 | 연결 | 선택한 프로필 데이터 세트를 추가할 연결입니다. |
| 8 | 새 대상 차원 | 선택한 프로필 데이터 세트에 포함되어 있으며 Analysis Workspace에서 보고할 수 있는 Experience Platform 대상을 나타내는 새 대상 차원<!--and metrics?-->입니다. 이러한 차원은 자동으로 생성됩니다. |
| 9 | 데이터 보기 | 선택한 데이터 보기는 연결과 연결됩니다. Analysis Workspace 내에서 Experience Platform 대상 데이터를 분석할 때 사용할 데이터 보기입니다. 이러한 데이터 보기는 보고를 위해 Experience Platform 대상 데이터로 자동으로 구성됩니다. |

## 대상 분석 구성

대상 분석을 구성할 때 분석하려는 Experience Platform 대상과 연결된 샌드박스 및 병합 정책을 선택합니다. Customer Journey Analytics은 새 조회 데이터 세트를 만든 다음 사용자가 선택한 연결에 조회 데이터 세트와 프로필 데이터 세트를 자동으로 추가합니다.

>[!NOTE]
>
>대상은 대상 분석 구성을 만든 다음 날에 Customer Journey Analytics 데이터 보기에서 사용할 수 있습니다.

자세한 내용은 [대상 분석 구성](/help/connections/audience-analysis/audience-analysis-configure.md)을 참조하십시오.

## 대상 분석 구성 관리

대상 분석 구성을 만든 후 관리할 수 있습니다. 구성을 보고, 편집하고, 삭제할 수 있습니다.

기존 대상 분석 구성 관리에 대한 자세한 내용은 [대상 분석 구성 관리](/help/connections/audience-analysis/audience-analysis-manage.md)를 참조하십시오.

## Customer Journey Analytics에서 대상 데이터 분석

Customer Journey Analytics에서 사용할 수 있는 대상 데이터를 통해 대상 구성원이 다양한 채널에서 어떻게 행동하는지에 대한 실용적인 통찰력을 얻을 수 있습니다.

예를 들어 동일한 이메일 프로모션에 포함된 개별 고객의 행동을 추적할 수 있습니다. Customer Journey Analytics에서 사용할 수 있는 대상을 통해 각 대상 구성원에 대한 다음과 같은 정보를 볼 수 있습니다.

* 이메일에서 사이트까지 클릭스루하여 결과적으로 구매

* 스토어에서 구매한 고객 구성원

자세한 내용은 [Customer Journey Analytics에서 Experience Platform 대상 분석](/help/connections/audience-analysis/analyze-audiences.md)을 참조하십시오.

## 대상 분석 역할 및 권한 요구 사항

대상 분석에 필요한 Customer Journey Analytics 역할 및 Experience Platform 권한은 다음과 같습니다.

| 기능 | Customer Journey Analytics 역할 또는 권한 요구 사항 | Experience Platform 권한 요구 사항 |
|---------|----------|----------|
| [대상 분석 구성 만들기](/help/connections/audience-analysis/audience-analysis-configure.md) | 시스템 관리자 | <ul><li>데이터 세트: 읽기 권한</li><li>스키마: 읽기, 쓰기</li><li>ID 네임스페이스: 읽기</li></ul> |
| [데이터 보기에서 대상 분석 차원 보기](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | 데이터 보기가 할당된 제품 프로필의 제품 프로필 관리자 <p>자세한 내용은 [액세스 제어](/help/technotes/access-control.md)를 참조하십시오.</p> | 해당 사항 없음 |
| Analysis Workspace에서 대상 분석 차원 사용 | 대상 분석 차원이 추가된 데이터 보기에 대한 액세스 권한 | 해당 사항 없음 |










