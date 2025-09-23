---
title: Data Mirror 개요
description: Data Warehouse 기본 솔루션과 Customer Journey Analytics 간에 데이터를 동기화하는 방법을 이해합니다.
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
source-git-commit: 9bd124ad651274b48052edc56bfb72358aa2d79a
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 1%

---

# Experience Platform Data Mirror 개요

{{release-limited-testing}}

Data Mirror은 모델 기반 스키마를 사용하여 외부 데이터베이스에서 데이터 레이크로 행 수준 변경 수집을 활성화하는 Experience Platform 기능입니다. 데이터 관계를 유지하고, 고유성을 적용하며, 업스트림 추출, 변환, 로드(ETL) 프로세스 없이 버전 관리를 지원합니다.

Data Mirror을 사용하여 [!DNL Snowflake], [!DNL Azure Databricks] 또는 [!DNL Google BigQuery]과(와) 같은 외부 데이터 웨어하우스 네이티브 솔루션에서 삽입, 업데이트 및 삭제(변경 가능한 데이터)를 Experience Platform으로 직접 동기화합니다. Data Mirror을 사용하면 데이터를 Experience Platform으로 가져올 때 기존 데이터베이스 모델 구조와 데이터 무결성을 유지할 수 있습니다.


## 기능 및 이점

Data Mirror은 데이터베이스 동기화를 위한 다음과 같은 필수 기능을 제공합니다.

* **기본 키 적용**. 데이터 세트 내에서 고유성을 보장하고 수집 중에 중복 레코드를 방지합니다.
* **행 수준 변경 수집**. 정밀한 제어를 통해 업데이트 및 삭제를 포함하여 세부적인 데이터 변경 사항을 지원합니다.
* **스키마 관계**. 설명자를 통해 데이터 세트 간 외래 및 기본 키 관계를 활성화합니다.
* **잘못된 이벤트 처리**. 버전 및 타임스탬프 설명자가 순서를 벗어나도 변경 이벤트를 처리합니다.
* **직접 웨어하우스 통합**. 실시간 변경 동기화를 위해 지원되는 클라우드 데이터 웨어하우스와 연결합니다.

Data Mirror을 사용하여 소스 시스템에서 직접 변경 사항을 수집하고, 스키마 무결성을 적용하며, 분석, 여정 오케스트레이션 및 규정 준수 워크플로우에 데이터를 사용할 수 있도록 합니다. Data Mirror은 기존 데이터베이스 모델의 직접 미러링을 활성화하여 복잡한 업스트림 ETL 프로세스를 제거하고 구현 시간을 단축합니다. 이를 통해 삭제 및 데이터 위생 작업을 정확하게 제어하여 데이터 거버넌스를 향상시킬 수 있습니다.

<!-- Add link when AEP docs are ready... -->

Data Mirror에서 Experience Platform 설명서 를 참조하십시오.


## Customer Journey Analytics용 Data Mirror

>[!NOTE]
>
>Customer Journey Analytics용 Experience Platform Data Mirror 기능은 2026년 3월 25일까지 **공개 베타**&#x200B;에서 사용할 수 있습니다. Beta 기간 동안 변경 데이터 캡처(CDC) 업데이트는 조직의 월별 데이터 행의 0.5%로 제한됩니다. 월별 데이터 행은 12로 나눈 데이터 행에 대한 연간 자격을 기반으로 합니다. Adobe은 조직이 이 제한을 초과하는 경우 Experience Platform Data Mirror for Customer Journey Analytics 기능에 대한 베타 액세스를 종료할 수 있는 권한을 보유합니다.
>

선택한 데이터 웨어하우스 네이티브 솔루션([!DNL Azure Databricks], [!DNL Google BigQuery] 및 [!DNL Snowflake])에 Experience Platform Data Mirror for Customer Journey Analytics 기능을 사용할 수 있습니다. Customer Journey Analytics 버전의 Data Mirror 기능을 사용하려면 여러 구성 요소를 적절하게 설정하고 구성해야 합니다.

* [Data Warehouse 네이티브 솔루션](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


>[!MORELIKETHIS]
>
>[Data Mirror 빠른 시작 안내서: 모델 기반 데이터를 미러링하고 사용](data-mirror.md)
>