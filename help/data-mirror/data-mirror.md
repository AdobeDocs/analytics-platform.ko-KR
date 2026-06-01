---
title: Data Mirror 개요
description: Data Warehouse 기본 솔루션과 Customer Journey Analytics 간에 데이터를 동기화하는 방법을 이해합니다.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
autotag-review: '2026-05-19T08:55:53.979Z'
TQID: 'https://experienceleague.adobe.com/10YCh2cnMTVriKKVOyYfzFfngvGQ2VVHOxzedE5NpWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: b4547b6c48adb97f6749ef54147f369632c44fa9
workflow-type: tm+mt
source-wordcount: 496
ht-degree: 3%

---

# Experience Platform Data Mirror 개요

{{release-limited-testing}}

Data Mirror은 관계형 스키마를 사용하여 외부 데이터베이스에서 데이터 레이크로 행 수준 변경 사항을 수집할 수 있는 Experience Platform 기능입니다. ETL(업스트림 추출, 변환 및 로드) 프로세스 없이도 데이터 관계를 유지하고, 고유성을 적용하며, 버전 관리를 지원합니다.

Experience Platform Data Mirror을 사용하여 외부 데이터 웨어하우스 네이티브 솔루션([!DNL Snowflake], [!DNL Azure Databricks] 또는 [!DNL Google BigQuery])에서 삽입, 업데이트 및 삭제(변경 가능한 데이터)를 Experience Platform의 데이터와 직접 동기화할 수 있습니다. Data Mirror을 사용하면 데이터를 Experience Platform으로 가져올 때 기존 데이터베이스 모델 구조와 데이터 무결성을 유지할 수 있습니다.

## 기능 및 이점

Data Mirror은 데이터베이스 동기화를 위한 다음과 같은 필수 기능을 제공합니다.

* **기본 키 적용.** 데이터 세트 내에서 고유성을 보장하고 수집 중에 중복 레코드를 방지합니다.
* **행 수준 변경 수집입니다.** 정밀한 제어를 통해 업데이트 및 삭제를 포함하여 세부적인 데이터 변경 사항을 지원합니다.
* **스키마 관계** 설명자를 통해 데이터 세트 간 외래 및 기본 키 관계를 활성화합니다.
* **잘못된 이벤트 처리.** 버전 및 타임스탬프 설명자가 순서를 벗어나도 변경 이벤트를 처리합니다.
* **직접 웨어하우스 통합.** 실시간 변경 동기화를 위해 지원되는 클라우드 데이터 웨어하우스와 연결합니다.

Data Mirror을 사용하여 소스 시스템에서 직접 변경 사항을 수집하고, 스키마 무결성을 적용하며, 분석, 여정 오케스트레이션 및 규정 준수 워크플로우에 데이터를 사용할 수 있도록 합니다. Data Mirror은 기존 데이터베이스 모델의 직접 미러링을 활성화하여 복잡한 업스트림 ETL 프로세스를 제거하고 구현 시간을 단축합니다. 이를 통해 삭제 및 데이터 위생 작업을 정확하게 제어하여 데이터 거버넌스를 향상시킬 수 있습니다.

Data Mirror의 [Experience Platform 설명서](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}도 참조하세요.

## Customer Journey Analytics용 Data Mirror

>[!NOTE]
>
>Data Mirror은 현재 beta 버전으로 Customer Journey Analytics에서 분석할 CDC(변경 데이터 캡처)를 사용하여 일부 데이터 웨어하우스의 데이터 동기화를 지원하는 기능입니다.<br/>이 기능은 2026년 6월 18일에 Customer Journey Analytics에서 일반적으로 사용할 수 있습니다. 향후 연간 수집 제한 소비에 어떤 영향을 미칠 수 있는지 이해하려면 해당 제품 설명서를 참조하십시오. Data Mirror이 Beta에서 일반 출시로 전환될 때 조직에서 해당 기능에 계속 액세스할 수 있습니다.
>

>[!IMPORTANT]
>
>Data Mirror for Customer Journey Analytics을 위해 Experience Platform에서 생성하는 변경 데이터 캡처 데이터 세트는 Real-Time Customer Data Platform 또는 Journey Optimizer과 같은 다른 Experience Platform 솔루션에서 재사용해서는 안 됩니다. 이러한 솔루션에 동일한 데이터를 사용하려면 동일한 데이터로 대체 데이터 세트를 만드는 것이 좋습니다.
>



Customer Journey Analytics용 Experience Platform Data Mirror은 선택한 데이터 웨어하우스 네이티브 솔루션([!DNL Azure Databricks], [!DNL Google BigQuery] 및 [!DNL Snowflake])에 사용할 수 있습니다. Experience Platform Data Mirror의 Customer Journey Analytics 버전에는 다음 애플리케이션 또는 구성 요소를 적절히 구성해야 합니다.

* [데이터 웨어하우스 기본 솔루션](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror 빠른 시작 안내서: 관계형 데이터를 미러링하고 사용](relational.md)
>[Data Mirror(Experience Platform 설명서)](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/data-mirror/overview)
>[관계형 스키마(Experience Platform 설명서)](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/schema/relational)
