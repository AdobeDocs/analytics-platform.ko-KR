---
title: Customer Journey Analytics 데이터 피드에서 Parquet 파일 사용
description: Customer Journey Analytics 데이터 피드가 Parquet 파일을 제공하는 이유, Parquet이 CSV, TSV 및 JSON과 비교하는 방법, 파일을 쿼리하거나 로드하는 방법에 대해 알아봅니다.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: f77f416ad958b28a8489d7a6eb13100ba699236e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%
---
# 데이터 피드에서 Parquet 파일 작업

{{release-limited-testing}}

Customer Journey Analytics 데이터 피드는 파일을 Parquet 형식으로 전달합니다. 대부분의 최신 데이터 웨어하우스는 Parquet 파일을 직접 읽을 수 있으므로 일반적으로 파일을 사용하기 전에 변환할 필요가 없습니다.

다음 정보를 사용하여 데이터 피드에서 Parquet를 사용하는 이유, Parquet가 다른 파일 형식과 비교하는 방법, Data Warehouse에서 Parquet 파일을 쿼리하거나 로드하는 방법을 이해합니다.

## 데이터 피드에 Parquet 사용의 이점

Parquet는 다음과 같은 이유로 CSV, TSV 또는 JSON보다 데이터 피드 출력에 더 적합합니다.

* **넓은 피드**: 데이터 피드에 수백 개의 열이 있을 수 있습니다. Parquet을 사용하면 쿼리에 필요한 열만 읽을 수 있습니다.

* **중첩된 필드**: Parquet는 기본적으로 제품 목록과 같은 중첩된 필드를 나타냅니다. CSV와 TSV는 문자열로 인코딩해야만 이를 나타낼 수 있습니다. 자세한 내용은 [데이터 피드의 하위 이벤트 구성 요소](/help/components/exports/cja-data-feeds/df-sub-event.md)를 참조하세요.

* **기본 제공 스키마**: 각 Parquet 파일은 열 이름, 데이터 형식 및 중첩된 구조를 포함하여 자체 스키마를 저장합니다. 스키마가 파일에 있으므로 Data Warehouse는 파일에서 직접 테이블을 만들 수 있습니다. 별도의 헤더 파일이나 스키마 정의를 제공할 필요가 없으며 Data Warehouse에서 데이터 유형을 유추할 필요가 없습니다.

* **대규모 내보내기**: Parquet는 일반적으로 저장 및 전송 비용을 줄입니다. 또한 데이터를 로드할 때 텍스트 구문 분석을 사용하지 않습니다.

## Parquet가 CSV, TSV 및 JSON과 비교하는 방법

CSV, TSV 및 JSON은 일반적인 텍스트 기반 파일 형식입니다.

* **CSV 및 TSV**: 각 데이터 행은 쉼표(CSV) 또는 탭(TSV)으로 구분된 값이 있는 일반 텍스트 줄입니다. Adobe Analytics 데이터 피드는 TSV 파일을 제공합니다. Customer Journey Analytics과 Adobe Analytics의 데이터 피드 간 다른 차이점에 대해서는 [Customer Journey Analytics과 Adobe Analytics의 데이터 피드 비교](/help/components/exports/cja-data-feeds/df-comparison.md)를 참조하십시오.

* **JSON**: 각 레코드는 명명된 필드가 있는 텍스트로 저장되며 중첩된 배열과 개체를 포함할 수 있습니다.

다음 표에서는 Parquet, CSV, TSV 및 JSON의 차이점에 대해 자세히 설명합니다.

| 특성 | 쪽모이 세공 | CSV 또는 TSV | JSON |
| --- | --- | --- | --- |
| **쿼리 속도** | 빨리! 쿼리는 필요한 열만 읽습니다. | 천천히. 전체 행을 읽고 구문 분석해야 합니다. | 천천히. 전체 행을 읽고 구문 분석해야 합니다. |
| **데이터 유형** | 입력. 스키마가 파일에 포함되어 있습니다. | 입력 안 됨. 모든 값은 텍스트이며 데이터를 로드할 때 유형이 추론됩니다. | 느슨하게 입력. |
| **중첩된 데이터** | 배열 및 개체는 기본적으로 지원됩니다. | 지원되지 않습니다. 배열과 개체를 병합하거나 문자열로 인코딩해야 합니다. | 배열 및 개체는 기본적으로 지원됩니다. |
| **가독성** | Data Warehouse, DuckDB 또는 Python과 같은 도구가 필요합니다. | 텍스트 편집기 또는 스프레드시트에서 열립니다. | 텍스트 편집기에서 열립니다. |

## Parquet 파일 쿼리 또는 로드

데이터 피드 파일은 [데이터 피드를 만들 때](/help/components/exports/cja-data-feeds/create-feed.md)선택한 클라우드 저장소 위치에 Parquet 형식으로 전달됩니다.

파일을 다운로드하는 대신 일반적으로 데이터 웨어하우스를 저장소 위치에 연결합니다. 그런 다음 다음 다음 방법 중 하나로 Parquet 파일을 사용할 수 있습니다.

### 그 자리에 있는 파일 쿼리

클라우드 스토리지의 파일을 가리키는 외부 테이블을 정의합니다. 쿼리를 실행하면 데이터 웨어하우스에서 파일을 읽습니다.

* **Snowflake**: 외부 테이블 또는 외부 스테이지에 대한 쿼리
* **데이터 블록**: Amazon S3, Azure ADLS(데이터 레이크 저장소) 또는 Google Cloud Storage를 통한 외부 테이블
* **BigQuery**: Google Cloud Storage의 외부 테이블
* **Amazon Redshift**: Amazon S3의 Redshift 스펙트럼

### 관리되는 테이블에 파일 로드

관리되는 테이블에 파일을 로드하는 것은 반복되는 워크로드에 대한 일반적인 선택입니다. 예:

* **Snowflake**: `COPY INTO`
* **BigQuery**: 작업 로드
* **데이터 블록**: `COPY INTO` 또는 자동 로더

## Parquet 데이터를 CSV 또는 JSON으로 변환

다운스트림 프로세스에 CSV 또는 JSON 파일이 필요한 경우 대부분의 데이터 웨어하우스 및 도구는 Parquet 데이터를 로드한 후 두 형식 중 하나로 내보낼 수 있습니다. 예를 들어 Snowflake에서 `COPY INTO`을(를) 사용하여 쿼리 결과를 CSV 또는 JSON으로 언로드할 수 있습니다.
