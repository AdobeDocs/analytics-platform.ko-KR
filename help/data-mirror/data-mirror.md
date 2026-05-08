---
title: Data Mirror 개요
description: Data Warehouse 기본 솔루션과 Customer Journey Analytics 간에 데이터를 동기화하는 방법을 이해합니다.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: dc3aa31c280c1a8ee8a0187edeca9bd34a2c9e2e
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

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

Customer Journey Analytics용 Experience Platform Data Mirror은 선택한 데이터 웨어하우스 네이티브 솔루션([!DNL Azure Databricks], [!DNL Google BigQuery] 및 [!DNL Snowflake])에 사용할 수 있습니다. Experience Platform Data Mirror의 Customer Journey Analytics 버전에는 다음 애플리케이션 또는 구성 요소를 적절히 구성해야 합니다.

* [데이터 웨어하우스 기본 솔루션](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror 빠른 시작 안내서: 관계형 데이터를 미러링하고 사용합니다.](relational.md)
>[Data Mirror (Experience Platform 설명서)](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/data-mirror/overview)
>[관계형 스키마(Experience Platform 설명서)](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/schema/relational)
