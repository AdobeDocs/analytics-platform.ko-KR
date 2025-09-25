---
title: Experience Platform 구성
description: Customer Journey Analytics용 Experience Platform Data Mirror에 대한 스키마 및 데이터 세트를 구성하는 방법을 이해합니다
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: 8946f1bc57cc856adeac4ee0a96799040f7e698c
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 3%

---

# Experience Platform 구성

{{release-limited-testing}}

Experience Platform Data Mirror for Customer Journey Analytics을 사용하려면 여러 Experience Platform 구성 요소를 적절하게 구성해야 합니다.

* 스키마
* 데이터 세트
* 소스 커넥터

이러한 각 구성 요소를 구성할 때 고려해야 하는 세부 사항은 아래에서 확인하십시오.

## 스키마

미러링할 Data Warehouse 네이티브 테이블을 모델링하는 모델 기반 스키마를 만들어야 합니다. 모델 기반 스키마를 구성할 때 다음 요구 사항이 충족되는지 확인하십시오.

* 모델 기반 스키마 유형을 입력하라는 메시지가 표시되면 수동 옵션을 선택해야 합니다.
* 데이터 유형에 적절한 스키마를 선택합니다. Experience Platform Data Mirror은 대부분 시계열 데이터(예: 이벤트 데이터)에 사용됩니다.

* 스키마의 필드 및 해당 속성을 정의합니다.
* 모델 기반 스키마의 필드에 필요한 속성을 구성합니다.

   * 기본 키
   * 버전 식별자
   * 타임스탬프 식별자(시계열 데이터용).

## 데이터 세트

스키마에 대한 데이터 세트를 미리 설정하거나 소스 커넥터를 설정할 때 데이터 세트를 만들 수 있습니다.
데이터 집합을 미리 만들거나 데이터 집합을 선택할 때 데이터가 이전에 만든 모델 기반 [스키마](#schema)을(를) 사용하는지 확인하십시오.


## 소스 커넥터

지원되는 Data Warehouse 네이티브 솔루션에 대한 소스 커넥터를 설정하려면 설정을 안내하는 소스 워크플로우를 사용합니다. 이 워크플로우는 다음 단계로 구성됩니다.

### 인증

지원되는 Data Warehouse 네이티브 솔루션에 대한 인증은 관련 Experience Platform 설명서를 참조하십시오.

* [Azure 데이터베이스](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/connectors/databases/snowflake)


### 데이터 선택

Data Warehouse 네이티브 솔루션에 성공적으로 연결되면 데이터 미러링에 사용할 Data Warehouse 네이티브 솔루션에서 테이블을 선택합니다. 선택하면 데이터 내용의 미리보기가 표시됩니다.


### 데이터 흐름 세부 정보

변경 데이터 캡처를 활성화해야 합니다. 변경 데이터 캡처에 대한 요구 사항을 설명하는 정보 패널이 표시됩니다.

이전에 만든 모델 기반 스키마를 기반으로 하는 새 데이터 세트 또는 기존 데이터 세트를 지정합니다. 데이터 흐름 세부 정보 인터페이스에서 다른 옵션을 지정하고 선택합니다.


### 매핑

Data Warehouse 네이티브 솔루션에 있는 테이블의 필드를 모델 기반 스키마에 지정한 필드에 매핑합니다.


### 예약

Data Warehouse 네이티브 솔루션의 테이블에서 Experience Platform의 데이터 세트로 데이터를 미러링하는 일정을 정의합니다.


### 자세한 내용은

데이터 미러를 지원하고 데이터 캡처를 변경하는 Data Warehouse 네이티브 솔루션에 대한 소스 커넥터 설정을 검토하십시오.


소스 커넥터 설정을 완료하면 데이터 흐름이 만들어집니다. 그 순간부터 Data Warehouse 네이티브 솔루션의 데이터 변경 사항(삽입, 업데이트, 삭제)은 지정된 데이터 세트로 미러링됩니다.


>[!MORELIKETHIS]
>
>[Data Mirror 빠른 시작 안내서: 모델 기반 데이터를 미러링하고 사용](model-based.md)
>
