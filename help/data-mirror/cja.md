---
title: Customer Journey Analytics 구성
description: Experience Platform Data Mirror for Customer Journey Analytics에 Customer Journey Analytics 연결, 데이터 보기 및 프로젝트를 구성하는 방법을 이해합니다
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
source-git-commit: 9bd124ad651274b48052edc56bfb72358aa2d79a
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---


# Customer Journey Analytics 구성

Customer Journey Analytics용 Experience Platform Data Mirror 기능을 사용하려면 연결, 데이터 보기 및 작업 영역 프로젝트를 만들거나 업데이트하여 모델 기반 데이터를 사용해야 합니다.

## 연결

연결에 Data Warehouse 기본 솔루션의 데이터를 나타내는 모델 기반 데이터 세트를 추가합니다. 이러한 데이터 세트에는 모델 데이터 세트 유형이 있습니다.

Data Warehouse 네이티브 솔루션에서 미러링된 데이터가 포함된 모델 기반 데이터 세트를 추가하면 해당 데이터는 일반적으로 이벤트 데이터입니다. 데이터 세트에 대한 올바른 설정을 선택해야 합니다. 예를 들어 올바른 데이터 세트 유형, ID에 대한 필드 및 타임스탬프에 대한 필드를 선택합니다.


## 데이터 보기

모델 기반 스키마의 필드를 데이터 보기의 구성 요소(지표 및 차원)로 정의합니다. 데이터 미러링된 필드는 **[!UICONTROL 이벤트 데이터 세트]** 폴더의 **[!UICONTROL 임시 및 모델 기반 필드]** 하위 폴더에서 사용할 수 있습니다. [파생 필드](/help/data-views/derived-fields/derived-fields.md) 또는 [구성 요소 설정](/help/data-views/component-settings/overview.md)과 같은 기능을 사용하여 모델 기반 필드를 기반으로 하는 구성 요소를 수정하십시오.


## Workspace 프로젝트

모델 기반 데이터의 지표 및 차원을 사용하는 Workspace 프로젝트를 설정합니다. 궁극적으로 Data Warehouse 네이티브 솔루션의 데이터를 기반으로 하는 구성 요소입니다. 구성한 데이터 미러 기능을 기반으로 업데이트됩니다.

>[!MORELIKETHIS]
>
>[Data Mirror 빠른 시작 안내서: 모델 기반 데이터를 미러링하고 사용](data-mirror.md)
>