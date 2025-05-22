---
title: Ad Hoc Analysis을 위한
description: Customer Journey Analytics에서 Customer Journey Analytics B2B edition으로 전환하는 방법 알아보기
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B 에디션"
hide: true
hidefromtoc: true
source-git-commit: c0446bd85b65109fd3311d54e33f9fb33af28f88
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# 전환 안내서

{{draft-b2b}}

이 안내서에서는 Customer Journey Analytics에서 Customer Journey Analytics의 B2B edition으로 전환하는 방법에 대해 설명합니다.

이 문서에서는 사용자가 이미 Customer Journey Analytics을 어느 정도 사용하고 있다고 가정합니다.

* Customer Journey Analytics으로 데이터를 수집하는 [연결](/help/connections/overview.md)이 있습니다.
* 이 연결의 데이터를 사용하는 [데이터 보기](/help/data-views/data-views.md)가 있습니다.
* 이 데이터 보기를 활용하는 보고서 및 시각화가 포함된 [프로젝트](/help/analysis-workspace/home.md)가 있습니다.

이전에 Customer Journey Analytics을 사용한 적이 없다면 [B2B edition 빠른 시작 안내서](cja-b2b-quick-start-guide.md)를 참조하세요.


## 기존 구현

Customer Journey Analytics B2B edition에 대한 라이선스가 부여되고 프로비저닝된 후에는 Customer Journey Analytics의 기존 구현이 전혀 변경되지 않습니다.

기존의 모든 연결은 [사용자 기반 연결](cja-b2b-concepts-features.md#connections-and-identifiers)로 간주되며 업데이트 없이 계속 작동합니다. 데이터 보기, 작업 공간 프로젝트, 세그먼트, 예약된 내보내기, 경고 등 이러한 사용자 기반 연결의 데이터에 의존하는 모든 것은 원래 계획 및 의도한 대로 계속 작동합니다.

>[!IMPORTANT]
>
>기존 사용자 기반 연결을 계정 기반 연결로 변경할 수 없습니다. B2B edition 기능을 사용하려면 새 계정 기반 연결이 필요합니다.
>


## B2B 기능 구현

기존 구현에서 B2B 기능을 구현하려면 다음 단계를 수행해야 합니다.

1. B2B 데이터를 모델링합니다. Customer Journey Analytics B2B edition은 최소 계정 기반 시계열 이벤트 데이터를 가정하며 추가 프로필 또는 조회 레코드 데이터의 이점을 활용합니다. 계정 데이터, 구매 그룹 데이터, 기회 데이터, 마케팅 목록 멤버 데이터 등.

   * 기본 계정 식별자(계정 ID)로 사용할 식별자를 정의합니다. 종종 기존 CRM 또는 기타 도구(예: Demandbase)는 해당 식별자를 결정하는 데 도움이 됩니다.
   * 사용할 다른 B2B 데이터에 대한 추가 식별자(글로벌 계정 식별자, 영업 기회 식별자, 구매 그룹 식별자 및 개인 식별자)를 식별합니다.

1. B2B 데이터를 준비합니다. 모든 시계열 이벤트 데이터 및 관련 레코드 데이터에 계정 식별자를 추가하고 수집해야 합니다. 마찬가지로 시계열 이벤트 데이터 및 조회 레코드에 관련 이벤트에 대한 다른 식별자가 포함되어 있는지 확인합니다. 예를 들어 다른 판매 단계로 이동하라는 신호를 보내는 이벤트에는 영업 기회 식별자가 있어야 합니다. 또한 해당 식별자는 영업 기회 조회 데이터의 일부여야 합니다.

1. [새 계정 기반 연결을 만듭니다](/help/connections/create-connection.md#account-based-connection). 포함할 선택적 컨테이너를 선택하십시오. [데이터 세트 추가](/help/connections/create-connection.md#add-datasets) 및 각 데이터 세트에 대한 [설정 정의](/help/connections/create-connection.md#dataset-settings). 가능하면 조회 레코드 데이터 세트에 대해 [컨테이너별 일치](cja-b2b-concepts-features.md#match-by-container)를 사용하십시오.

1. 새 연결을 기반으로 [데이터 보기를 만듭니다](/help/data-views/create-dataview.md).

   * 수집한 데이터에서 모든 관련 필드를 지표 또는 차원으로 추가해야 합니다.
   * 필요한 경우 구성 요소 설정(예: 지속성, 속성 등)을 적용합니다.
   * 필요한 경우 파생된 필드를 추가합니다.

1. B2B 데이터를 보고하고 이에 대한 통찰력을 얻으려면 [작업 영역 프로젝트를 만듭니다](/help/analysis-workspace/build-workspace-project/create-projects.md). [컨테이너](cja-b2b-concepts-features.md#containers)와 같은 특정 B2B 기능을 사용하여 심도 있는 통찰력을 얻으십시오.

   하나의 작업 영역 프로젝트에서 여러 [패널](/help/analysis-workspace/c-panels/panels.md)을(를) 사용하여 B2B(개인 기반) 및 B2B(계정 기반) 보고서와 통찰력을 결합할 수 있습니다.
