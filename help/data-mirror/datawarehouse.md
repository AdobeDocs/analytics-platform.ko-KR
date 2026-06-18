---
title: Data Warehouse 기본 솔루션 구성
description: Customer Journey Analytics용 Experience Platform Data Mirror에 대한 Data Warehouse 기본 솔루션을 구성하는 방법을 이해합니다.
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
autotag-review: '2026-05-19T08:56:46.637Z'
TQID: 'https://experienceleague.adobe.com/A3GkkNVAO9qpbOqCrZnf6PNJfRuwMaodJVOOuSRg0w8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 441
ht-degree: 0%

---

# Data Warehouse 기본 솔루션 구성

Customer Journey Analytics용 Experience Platform Data Mirror을 지원하려면 지원되는 세 가지 데이터 웨어하우스 네이티브 솔루션([[!DNL Azure Databricks]](#azure-databricks), [[!DNL Google BigQuery]](#google-bigquery), [[!DNL Snowflake]](#snowflake))에서 사용하려는 데이터에 변경 데이터 캡처를 사용하도록 설정해야 합니다.


## [!DNL Azure Databricks]

원본 연결에서 변경 데이터 캡처를 사용하려면 [!DNL Azure Databricks] 테이블에서 **변경 데이터 피드**&#x200B;를 사용하도록 설정하십시오.

다음 명령을 사용하여 테이블에서 변경 데이터 피드를 활성화합니다.

**새 테이블**

변경 데이터 피드를 새 테이블에 적용하려면 `CREATE TABLE` 명령에서 테이블 속성 `delta.enableChangeDataFeed`을(를) `TRUE`(으)로 설정해야 합니다.

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**기존 테이블**

기존 테이블에 변경 데이터 피드를 적용하려면 `ALTER TABLE` 명령에서 테이블 속성 `delta.enableChangeDataFeed`을(를) `TRUE`(으)로 설정해야 합니다.

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**새 테이블 모두**

모든 새 테이블에 변경 데이터 피드를 적용하려면 기본 속성을 `TRUE`(으)로 설정해야 합니다.

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

자세한 내용은 변경 데이터 피드를 사용하는 방법에 대한 [[!DNL Azure Databricks] 안내서](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed)를 참조하세요.

[!DNL Azure Databricks] 소스 연결에 변경 데이터 캡처를 활성화하는 방법에 대한 단계는 다음 설명서를 참조하십시오.

* [기본 연결 만들기 [!DNL Azure Databricks] 기본 연결 만들기](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/databricks).
* [데이터베이스에 대한 원본 연결을 만듭니다](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Google BigQuery]

[!DNL Google BigQuery] 원본 연결에서 변경 데이터 캡처를 사용하려면 [!DNL Google Cloud] 콘솔에서 [!DNL Google BigQuery] 페이지로 이동하여 `enable_change_history`을(를) `TRUE`(으)로 설정하십시오. 이 속성을 사용하면 데이터 테이블에 대한 변경 내역을 사용할 수 있습니다.

자세한 내용은  [!DNL GoogleSQL][&#128279;](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list)의 데이터 정의 언어 구문에 대한 안내서를 참조하십시오.

[!DNL Google BigQuery] 소스 연결에 변경 데이터 캡처를 활성화하는 방법에 대한 단계는 다음 설명서를 참조하십시오.

* [기본 연결 만들기 [!DNL Google BigQuery] 기본 연결 만들기](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/bigquery).
* [데이터베이스에 대한 원본 연결을 만듭니다](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Snowflake]

원본 연결에서 변경 데이터 캡처를 사용하려면 [!DNL Snowflake] 테이블에서 **변경 내용 추적**&#x200B;을 사용하도록 설정하십시오.

[!DNL Snowflake]에서 `ALTER TABLE`을(를) 사용하고 `CHANGE_TRACKING`을(를) `TRUE`(으)로 설정하여 변경 내용 추적을 사용하도록 설정합니다.

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

자세한 내용은 [[!DNL Snowflake] 변경 내용 절 사용 가이드](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes)를 참조하십시오.

[!DNL Snowflake] 소스 연결에 변경 데이터 캡처를 활성화하는 방법에 대한 단계는 다음 설명서를 참조하십시오.

* [기본 연결 만들기 [!DNL Snowflake] 기본 연결 만들기](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/snowflake).
* [데이터베이스에 대한 원본 연결을 만듭니다](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).


>[!MORELIKETHIS]
>
>[Data Mirror 빠른 시작 안내서: 관계형 데이터를 미러링하고 사용](relational.md)
>
