---
title: Data Mirror 개요
description: Data Warehouse 기본 솔루션과 Customer Journey Analytics 간에 데이터를 동기화하는 방법을 이해합니다.
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: 578e19d8a8205bdfa034900c45d7d4a2d8f6a797
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 1%

---

# Experience Platform Data Mirror 개요

{{release-limited-testing}}

Data Mirror은 모델 기반 스키마를 사용하여 외부 데이터베이스에서 데이터 레이크로 행 수준 변경 수집을 활성화하는 Experience Platform 기능입니다. ETL(업스트림 추출, 변환 및 로드) 프로세스 없이도 데이터 관계를 유지하고, 고유성을 적용하며, 버전 관리를 지원합니다.

Experience Platform Data Mirror을 사용하여 외부 데이터 웨어하우스 네이티브 솔루션([!DNL Snowflake], [!DNL Azure Databricks] 또는 [!DNL Google BigQuery])에서 삽입, 업데이트 및 삭제(변경 가능한 데이터)를 Experience Platform의 데이터와 직접 동기화할 수 있습니다. Data Mirror을 사용하면 데이터를 Experience Platform으로 가져올 때 기존 데이터베이스 모델 구조와 데이터 무결성을 유지할 수 있습니다.

## 기능 및 이점

Data Mirror은 데이터베이스 동기화를 위한 다음과 같은 필수 기능을 제공합니다.

* **기본 키 적용.** 데이터 세트 내에서 고유성을 보장하고 수집 중에 중복 레코드를 방지합니다.
* **행 수준 변경 수집입니다.** 전체 자릿수 제어로 업데이트 및 삭제를 포함하여 세부적인 데이터 변경 내용을 지원합니다.
* **스키마 관계.** 설명자를 통해 데이터 세트 간에 외래 및 기본 키 관계를 사용하도록 설정합니다.
* **잘못된 이벤트 처리.** 버전 및 타임스탬프 설명자가 순서를 벗어나도 변경 이벤트를 처리합니다.
* **직접 웨어하우스 통합.** 실시간 변경 동기화를 위해 지원되는 클라우드 데이터 웨어하우스와 연결합니다.

Data Mirror을 사용하여 소스 시스템에서 직접 변경 사항을 수집하고, 스키마 무결성을 적용하며, 분석, 여정 오케스트레이션 및 규정 준수 워크플로우에 데이터를 사용할 수 있도록 합니다. Data Mirror은 기존 데이터베이스 모델의 직접 미러링을 활성화하여 복잡한 업스트림 ETL 프로세스를 제거하고 구현 시간을 단축합니다. 이를 통해 삭제 및 데이터 위생 작업을 정확하게 제어하여 데이터 거버넌스를 향상시킬 수 있습니다.

Data Mirror의 [Experience Platform 설명서](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}도 참조하세요.

## Customer Journey Analytics용 Data Mirror

>[!NOTE]
>
>Customer Journey Analytics용 Experience Platform Data Mirror 기능은 2026년 3월 25일까지 **공개 베타**&#x200B;에서 사용할 수 있습니다. Beta 기간 동안 변경 데이터 캡처(CDC) 업데이트는 Customer Journey Analytics에 대한 1천만 개의 일일 변경 행 권한으로 제한됩니다. Adobe은 조직이 이 제한을 초과하는 경우 Experience Platform Data Mirror 기능에 대한 beta 액세스를 종료할 수 있는 권한을 보유합니다. 이 기능에 대한 액세스 권한을 요청하려면 Adobe 계정 팀에 문의하십시오.
>

Customer Journey Analytics용 Experience Platform Data Mirror은 선택한 데이터 웨어하우스 네이티브 솔루션([!DNL Azure Databricks], [!DNL Google BigQuery] 및 [!DNL Snowflake])에 사용할 수 있습니다. Experience Platform Data Mirror의 Customer Journey Analytics 버전에는 다음 애플리케이션 또는 구성 요소를 적절히 구성해야 합니다.

* [Data Warehouse 기본 솔루션](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror 빠른 시작 안내서: 모델 기반 데이터를 미러링하고 사용](model-based.md)
>&#x200B;>[Data Mirror(Experience Platform 설명서)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>
