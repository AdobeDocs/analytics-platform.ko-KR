---
title: Customer Journey Analytics 구성
description: Experience Platform Data Mirror for Customer Journey Analytics에 Customer Journey Analytics 연결, 데이터 보기 및 프로젝트를 구성하는 방법을 이해합니다
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
TQID: https://experienceleague.adobe.com/1LArX1cyRWpEY8O9xMwTcgwc0aUTjMrniFiDXtpkCNY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 230
ht-degree: 2%

---

# Customer Journey Analytics 구성

{{relational-model-based}}

Customer Journey Analytics용 Experience Platform Data Mirror 기능을 사용하려면 연결, 데이터 보기 및 작업 영역 프로젝트를 만들거나 업데이트하여 관계형 데이터를 사용해야 합니다.

## 연결

연결에서 Data Warehouse 기본 솔루션의 데이터를 나타내는 관계형 데이터 세트를 추가합니다. 이러한 데이터 세트에는 관계형 데이터 세트 유형이 있습니다.

Data Warehouse 네이티브 솔루션에서 미러링된 데이터가 포함된 관계형 데이터 세트를 추가하면 해당 데이터는 일반적으로 이벤트 데이터입니다. 데이터 세트에 대한 올바른 설정을 선택해야 합니다. 예를 들어 올바른 데이터 세트 유형, ID에 대한 필드 및 타임스탬프에 대한 필드를 선택합니다.


## 데이터 보기

관계형 스키마의 필드를 데이터 보기의 구성 요소(지표 및 차원)로 정의합니다. 데이터 미러링된 필드는 **[!UICONTROL 이벤트 데이터 세트]** 폴더의 **[!UICONTROL 임시 및 관계 필드]** 하위 폴더에서 사용할 수 있습니다. [파생 필드](/help/data-views/derived-fields/derived-fields.md) 또는 [구성 요소 설정](/help/data-views/component-settings/overview.md)과 같은 기능을 사용하여 관계 필드를 기반으로 하는 구성 요소를 수정하십시오.


## Workspace 프로젝트

관계형 데이터의 지표 및 차원을 사용하는 Workspace 프로젝트를 설정합니다. 궁극적으로 Data Warehouse 네이티브 솔루션의 데이터를 기반으로 하는 구성 요소입니다. 구성한 데이터 미러 기능을 기반으로 업데이트됩니다.

>[!MORELIKETHIS]
>
>[Data Mirror 빠른 시작 안내서: relationald 데이터를 미러링하고 사용](relational.md)
>
