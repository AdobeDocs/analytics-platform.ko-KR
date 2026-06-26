---
description: 데이터 피드를 사용하여 Customer Journey Analytics에서 원시 데이터를 가져오는 방법에 대해 알아봅니다. 데이터 피드 사용을 위한 사전 요구 사항을 확인하고 다음 작업을 수행합니다.
keywords: 클릭스트림, 데이터 피드, 데이터피드, 데이터 피드
title: Analytics 데이터 피드 개요
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: b31ae6194d30115f4d653addaf5efff5790e987c
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 21%

---

# 데이터 피드 개요

데이터 피드는 Customer Journey Analytics에서 원시 데이터를 가져오는 강력한 방법입니다. 조직의 판단에 따라 Adobe 외부의 다른 플랫폼에서 이 원시 데이터를 사용할 수 있습니다. 데이터는 매 시간이 끝날 때 시간별 배치로 전달되거나, 하루가 끝날 때 일별 배치로 전달됩니다.

## 사전 요구 사항

데이터 피드를 사용하기 전에 다음 요구 사항을 모두 충족하는지 확인하십시오.

* Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->에 수집되는 데이터를 사용하는 작업 구현
* 계정이 Analytics 제품 관리자이거나 계정이 데이터 피드 <!--???-->에 대한 액세스 권한이 있는 제품 프로필에 속합니다.
* [!DNL Amazon S3], [!DNL Google Cloud Platform], [!DNL Azure RBAC] 또는 [!DNL Azure SAS]에 구성된 버킷

## 시작하기

Customer Journey Analytics에서 데이터 피드를 사용하려면 먼저 Customer Journey Analytics의 데이터 피드가 Adobe Analytics의 데이터 피드와 어떻게 다른지 이해하십시오. 차이점을 이해하면 Adobe Analytics 데이터 피드를 Customer Journey Analytics에 매핑한 다음 데이터 피드 만들기를 시작할 수 있습니다.

1. [Customer Journey Analytics과 Adobe Analytics의 데이터 피드 간 차이점을 이해합니다](/help/components/exports/cja-data-feeds/df-comparison.md).

1. [Adobe Analytics 데이터 피드 열을 Customer Journey Analytics에 매핑](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

1. [데이터 피드를 만듭니다](/help/components/exports/cja-data-feeds/create-feed.md).
