---
description: 데이터 피드를 사용하여 Customer Journey Analytics에서 원시 이벤트 수준 데이터를 내보내고 사전 요구 사항을 검토하며 시작하는 데 필요한 문서를 찾는 방법에 대해 알아봅니다.
keywords: 클릭스트림, 데이터 피드, 데이터피드, 데이터 피드
title: Customer Journey Analytics 데이터 피드 개요
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 34959e37a7040bcd861a506968895ad6f051b686
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%
---
# 데이터 피드 개요

{{release-limited-testing}}

데이터 피드는 원시 이벤트 수준 데이터를 Customer Journey Analytics에서 클라우드 대상으로 내보냅니다. 이 데이터는 Data Warehouse와 같은 Adobe 외부의 다른 플랫폼에서 사용할 수 있습니다.

데이터 피드는 데이터 보기의 구성 요소에서 빌드됩니다. 포함하는 각 차원 및 지표는 데이터 피드의 열이 되며 지속성, 파생된 필드 및 세그먼트와 같은 데이터 보기 설정이 데이터에 적용됩니다. 파일은 Parquet 형식으로 전달됩니다.

다음 유형의 데이터 피드를 만들 수 있습니다.

* **라이브 피드**: 시간별 또는 일별 현재 및 미래 데이터를 내보냅니다. 각 게재는 시간 또는 일이 끝나고 처리 지연이 경과된 후에 전송됩니다.

* **피드 채우기**: 지난 날짜 범위에 대한 이전 데이터를 내보냅니다.

데이터 피드를 전체 테이블 내보내기와 같은 다른 Customer Journey Analytics 내보내기 방법과 비교하려면 [Analytics 제품 비교](/help/getting-started/analytics-product-comparison.md)를 참조하십시오.

## 사전 요구 사항

데이터 피드를 사용하기 전에 다음 요구 사항을 모두 충족하는지 확인하십시오.

* 데이터가 Customer Journey Analytics에 수집되고 있으며 연결 및 [데이터 보기](/help/data-views/create-dataview.md)가 구성되었습니다. <!-- For more information, see Data ingestion overview - add link -->

* 계정이 Customer Journey Analytics 제품 관리자이거나 사용할 데이터 보기에 대한 [!UICONTROL **데이터 피드**] 권한([!UICONTROL **데이터 보기 도구**] 범주)이 있는 제품 프로필에 속합니다. 자세한 내용은 [액세스 제어](/help/technotes/access-control.md)를 참조하십시오. <!--Add a Data Feeds row to the Data View Tools permissions table in access-control.md.-->

* 클라우드 내보내기 계정 및 위치가 [!DNL Amazon S3], [!DNL Google Cloud Platform], [!DNL Azure RBAC] 또는 [!DNL Azure SAS]에 대해 구성되어 있습니다. 자세한 내용은 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md) 및 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md)을 참조하십시오.

>[!TIP]
>
>데이터 보기의 구성 요소에 대한 변경 내용은 구성 요소를 사용하는 모든 데이터 피드에 영향을 주므로 데이터 피드에만 사용되는 데이터 보기를 만드는 것이 좋습니다.
>
>* **장점**: Analysis Workspace 보고에 대한 변경 사항이 데이터 피드 출력을 예기치 않게 변경하는 위험을 줄여 줍니다.
>
>* **단점**: 다른 데이터 보기와 함께 추가 데이터 보기를 유지해야 합니다.

## 시작하기

다음 문서를 사용하여 데이터 피드를 계획, 마이그레이션 및 만드십시오.

### 데이터 피드 계획

* [Customer Journey Analytics 및 Adobe Analytics의 데이터 피드 비교](/help/components/exports/cja-data-feeds/df-comparison.md): 이전에 Adobe Analytics 데이터 피드를 사용한 경우 기능과 개념의 차이점을 이해합니다.

* [데이터 피드와 Analysis Workspace 간의 데이터 불일치 이해](/help/components/exports/cja-data-feeds/df-comparison-workspace.md): 데이터 피드 출력이 Analysis Workspace의 보고서와 일치하지 않는 이유를 알아봅니다.

* [데이터 피드의 구성 요소 가용성](/help/components/exports/cja-data-feeds/df-components.md): 데이터 피드에서 필수, 지원되지 않거나 제한된 차원 및 지표를 알아봅니다.

### Adobe Analytics 데이터 피드에서 마이그레이션

1. [데이터 피드 열 매핑 준비](/help/components/exports/cja-data-feeds/df-column-mapping-prep.md): Adobe Analytics 열이 Customer Journey Analytics에 매핑되는 방식에 영향을 주는 요소를 이해합니다.

1. [Adobe Analytics 데이터 피드 열을 Customer Journey Analytics에 매핑](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md): 유지할 각 Adobe Analytics 열의 해당하는 Customer Journey Analytics을 찾습니다.

### 데이터 피드 만들기 및 구성

* [데이터 피드 만들기](/help/components/exports/cja-data-feeds/create-feed.md): 구성 요소를 선택하고 일정을 구성하고 게재를 설정합니다.

* [데이터 피드의 세그멘테이션](/help/components/exports/cja-data-feeds/df-segmentation.md): 세그먼트를 적용하여 데이터 피드의 데이터를 필터링합니다.

* [데이터 변환 적용](/help/components/exports/cja-data-feeds/df-data-transformations.md): 구성 요소 설정, 파생 필드 또는 SQL을 사용하여 데이터를 변환합니다.

* [데이터 피드의 하위 이벤트 구성 요소](/help/components/exports/cja-data-feeds/df-sub-event.md): 배열 및 맵의 구성 요소를 내보내는 방법과 쿼리하는 방법을 알아봅니다.

