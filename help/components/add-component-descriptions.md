---
description: 관리자가 데이터 보기 또는 데이터 사전을 사용하여 구성 요소에 설명을 추가하는 방법에 대해 알아봅니다.
title: 구성 요소 설명 추가
feature: Components
role: Admin
exl-id: 99d531cd-50e9-4e6c-adad-a66b606fd877
TQID: 'https://experienceleague.adobe.com/yXxEhHsXsAw-l9c0oVCNDtwoCUq86UZSnyiwvidKLWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
    internal-label: Data Dictionary
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b46a27ff9faca74c3c2baa7938a588b643633705
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 10%
---
# 구성 요소 설명 추가

설명은 사용자가 Analysis Workspace에서 프로젝트를 빌드하거나 보고서를 볼 때 다양한 구성 요소를 사용하는 방법을 아는 데 도움이 됩니다.

Customer Journey Analytics 관리자는 데이터 보기 또는 데이터 사전을 사용하여 구성 요소(차원, 지표, 세그먼트 및 날짜 범위)에 대한 설명을 추가할 수 있습니다.

## 데이터 보기

데이터 보기에 추가한 구성 요소에 설명을 추가할 수 있습니다. [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하세요.

## 데이터 사전

Analysis Workspace의 데이터 사전은 사용자와 관리자 모두가 Customer Journey Analytics 환경의 구성 요소를 추적하고 더 잘 이해할 수 있도록 도와줍니다. 데이터 사전을 사용하면 관리자가 Analysis Workspace 내에서 직접 구성 요소 설명을 추가할 수 있습니다.

데이터 사전의 구성 요소 설명을 편집하는 방법에 대한 자세한 내용은 [데이터 사전의 구성 요소 항목 편집](/help/components/data-dictionary/edit-entries-data-dictionary.md)을 참조하십시오.

데이터 사전에 대한 일반적인 정보는 [데이터 사전 개요](/help/components/data-dictionary/data-dictionary-overview.md)를 참조하십시오.

>[!MORELIKETHIS]
>
>[데이터 보기 구성 요소 설정](/help/data-views/component-settings/overview.md)
>[데이터 사전 구성 요소 항목](/help/components/data-dictionary/edit-entries-data-dictionary.md)
>

## 자동으로 설명 생성

{{release-limited-testing-section}}

Customer Journey Analytics은 각 설명을 수동으로 작성하는 대신 생성 AI를 사용하여 설명을 작성할 수 있습니다. 단일 구성 요소에 대한 설명을 생성하거나 동시에 여러 구성 요소에 대한 설명을 생성할 수 있습니다.

생성된 설명:

* 길이는 3문장밖에 되지 않습니다.
* **[!UICONTROL AI를 사용하여 Adobe에서 생성됨]**&#x200B;이라는 텍스트로 끝나므로 사용자는 설명이 생성되었음을 알 수 있습니다.
* 생성된 후 편집할 수 있습니다.

### 사전 요구 사항

설명을 생성하려면 먼저 조직에서 특정 생성 AI 법률 약관에 동의해야 합니다. 조직에서 이 약관에 동의하지 않은 경우 설명을 생성하는 옵션이 흐리게 표시됩니다. 옵션 옆에 있는 정보 아이콘 ![정보](/help/assets/icons/InfoOutline.svg)을(를) 선택하여 기능을 사용하도록 설정하는 방법을 배우거나 조직의 관리자 또는 Adobe 계정 팀에 문의하십시오.

### 설명을 생성하는 방법

생성된 설명은 구성 요소의 정의 및 구성 요소가 데이터 보기에서 사용되는 방식에 대한 추가 컨텍스트를 기반으로 합니다. 예를 들면 다음과 같습니다.

* 차원의 상위 항목
* 구성 요소와 함께 자주 사용되는 구성 요소

계산된 지표 또는 세그먼트가 다른 세그먼트를 참조할 때 생성된 설명은 참조된 세그먼트의 정의를 설명합니다.

### 다양한 위치에서 설명 생성

Customer Journey Analytics의 다음 영역에서 설명을 생성할 수 있습니다. 일부 위치에서는 여러 구성 요소에 대한 설명을 생성할 수 있지만 다른 위치에서는 생성하지 않습니다.

설명을 생성하는 방법을 배우려면 위치를 선택하십시오.

| 위치 | 지원되는 구성 요소 | 단일 구성 요소 | 여러 구성 요소 |
| --- | --- | --- | --- |
| [데이터 사전](/help/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>차원</li><li>지표</li><li>계산된 지표</li><li>세그먼트</li><li>날짜 범위</li></ul> | 예 | 예 |
| [데이터 보기](/help/data-views/component-settings/overview.md) | <ul><li>차원</li><li>지표</li><li>파생 필드</li><li>공유된 지표 및 차원(자세한 내용은 [공유된 지표 및 차원](#generate-descriptions-for-shared-metrics-and-dimensions)을 참조하십시오.)</li></ul> | 예 | 예 |
| [세그먼트 빌더](/help/components/segments/seg-builder.md) | 세그먼트 | 예 | 아니요 |
| [세그먼트 관리자](/help/components/segments/seg-manage.md#action-bar) | 세그먼트 | 아니요 | 예 |
| [계산된 지표 빌더](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | 계산된 지표 | 예 | 아니요 |
| [계산된 지표 관리자](/help/components/calc-metrics/cm-workflow/cm-manager.md#action-bar) | 계산된 지표 | 아니요 | 예 |
| [날짜 범위 빌더](/help/components/date-ranges/create.md#date-range-builder) | 날짜 범위 | 예 | 아니요 |
| [날짜 범위 관리자](/help/components/date-ranges/manage.md#action-bar) | 날짜 범위 | 아니요 | 예 |

{style="table-layout:auto"}

### 공유 지표 및 차원에 대한 설명 생성

[다양한 위치에서 설명 생성](#generate-descriptions-from-various-locations)의 표에 표시된 대로 데이터 보기 내에서만 공유 지표 및 차원에 대한 설명을 생성할 수 있습니다. [공유 지표 및 차원 관리자](/help/data-views/shared-metrics-dimensions/smd-overview.md#smd-manager)에서 설명을 생성할 수 없습니다.

데이터 보기 내의 공유 지표 또는 차원에 대한 설명을 생성할 때는 다음 사항을 고려하십시오.

* 이 설명은 구성 요소가 공유되는 모든 데이터 보기에 적용되며 다른 모든 데이터 보기와 공유 지표 및 차원 관리자에서 해당 구성 요소에 대한 기존 설명을 대체합니다.

* 설명은 이를 생성하는 데이터 보기(예: 데이터 보기의 최상위 차원 항목)의 컨텍스트를 기반으로 합니다.


