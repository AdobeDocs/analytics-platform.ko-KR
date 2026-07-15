---
description: 관리자는 데이터 사전 상태를 모니터링해야 합니다. 여기에는 구성 요소가 데이터를 수집하고 있는지, 승인되었는지, 설명이 포함되어 있는지, 중복이 없는지 여부가 포함됩니다.
title: 데이터 사전 상태 모니터링
feature: Components
role: Admin
exl-id: 8bc89ac7-078d-469d-8627-3905823d4100
TQID: https://experienceleague.adobe.com/RKh01bcmVkoZ2wkHDvBM-oX9rRagVaOqK4fn2A-IpaI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df28738e-9c71-4aa8-929e-edde22340cc6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 7c679fcbf52d2a5832d16bf138bd197f11f4ceb7
workflow-type: tm+mt
source-wordcount: 434
ht-degree: 87%

---

# 데이터 사전 상태 모니터링 {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="데이터 사전"
>abstract="이 옵션을 선택하면 기본 구성 요소가 중복 구성 요소에 액세스할 수 있는 모든 사람(소유자 및 구성 요소를 공유하는 모든 사람)과 공유됩니다. 공유 받은 사용자는 향후 프로젝트에 대한 구성 요소 목록에서 기본 구성 요소를 선택할 수 있습니다. 그러나 통합된 중복 구성 요소의 소유자일 경우에도 구성 요소를 편집할 수 없습니다. <br/>이 옵션은 기본 구성 요소가 세그먼트, 계산된 지표 또는 날짜 범위인 경우에만 사용할 수 있습니다. 지표 및 차원은 항상 모든 사용자가 사용할 수 있습니다.
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_share_primary"
>title="기본 구성 요소 공유"
>abstract="이 옵션을 선택하면 기본 구성 요소가 중복 구성 요소에 액세스할 수 있는 모든 사람(소유자 및 구성 요소를 공유하는 모든 사람)과 공유됩니다. 공유 받은 사용자는 향후 프로젝트에 대한 구성 요소 목록에서 기본 구성 요소를 선택할 수 있습니다. 그러나 통합된 중복 구성 요소의 소유자일 경우에도 구성 요소를 편집할 수 없습니다."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="datadictionary_delete_duplicates"
>title="교체된 중복 요소 삭제"
>abstract="이 옵션을 선택하면 통합된 중복 요소를 더 이상 사용할 수 없습니다. 중복 요소를 계속 사용하려면 이 옵션을 선택 취소합니다."

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics 관리자는 건강한 데이터 사전을 유지 관리할 책임이 있습니다.

## 정상적인 데이터 사전의 특징

정상적인 데이터 사전의 모든 구성 요소는 다음과 같습니다.

* 사용 중이며 데이터 수집 중임

* 사용자가 가장 잘 사용하는 방법을 알 수 있도록 유용한 설명 포함

* 불필요한 중복이 없음

* 관리자의 승인을 받음

## 데이터 사전의 상태 확인

데이터 사전의 상태 문제를 식별하는 방법:

1. Analysis Workspace 프로젝트를 엽니다.

1. Analysis Workspace의 왼쪽에서 데이터 사전 아이콘을 선택합니다. (데이터 사전에 액세스하는 다른 방법은 [데이터 사전 개요](/help/components/data-dictionary/data-dictionary-overview.md)의 “데이터 사전 액세스”에 설명되어 있음)

   데이터 사전 창이 표시됩니다.

   ![사전 상태를 표시하는 데이터 사전 관리자의 보기](assets/data-dictionary-admin.png)

1. 드롭다운 메뉴에서 올바른 데이터 보기가 선택되어 있는지 확인합니다.

1. [!UICONTROL **사전 상태**] 탭에서 다음 옵션 옆에 있는 [!UICONTROL **보기**]&#x200B;를 선택합니다.

   * [!UICONTROL **구성 요소에 대한 설명 누락**]

   * [!UICONTROL **구성 요소에 중복이 있음**]

   * [!UICONTROL **구성 요소에 연결된 데이터 없음**]

   선택한 항목에 따라 적절한 세그먼트가 데이터 사전에 적용되고 관련 구성 요소만 표시됩니다.

1. 구성 요소를 편집하여 데이터 사전의 상태를 개선합니다. 데이터 사전에서 구성 요소를 편집하는 방법에 대한 자세한 내용은 [데이터 사전의 구성 요소 항목 편집](/help/components/data-dictionary/edit-entries-data-dictionary.md)을 참조하십시오.
