---
title: Customer Journey Analytics BI 확장 기능
description: BI 확장을 사용하여 추가 데이터 세트와 함께 사용할 디지털 데이터를 고유한 BI 도구 또는 Data Lake로 가져오는 방법에 대해 설명합니다.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 669a1305-3e37-4ca2-8178-a89a27958e5d
autotag-review: '2026-05-19T08:00:39.048Z'
TQID: 'https://experienceleague.adobe.com/BgO7hQlR2J3o-nD38ZIg2ILUTwDKGfSXu-i-bEo5SJs'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 25%
---
# BI 확장 기능

이 문서에서는 [!DNL Customer Journey Analytics BI extension]을(를) 사용하여 다음 [데이터 내보내기 사용 사례](overview.md)를 구현하는 방법에 대해 간략히 설명합니다.

* Data Lake, Data Warehouse 또는 BI 도구

## 소개

[!DNL Customer Journey Analytics BI extension]을(를) 사용하여 데이터를 내보내면 Customer Journey Analytics 데이터 보기에서 데이터를 내보낼 수 있습니다.

![BI 확장](../assets/bi-extension.png)

## 추가 정보

[!DNL Customer Journey Analytics BI extension]를 통해 SQL은 Customer Journey Analytics에서 정의한 [데이터 보기](/help/data-views/data-views.md)에 액세스할 수 있습니다. 데이터 엔지니어와 분석가는 Power BI, Tableau 또는 기타 비즈니스 인텔리전스 및 시각화 도구(BI 도구라고도 함)에 익숙합니다. 이제 Customer Journey Analytics 사용자가 Analysis Workspace 프로젝트를 생성할 때 사용하는 것과 동일한 데이터 보기를 기반으로 보고 및 대시보드를 만들 수 있습니다.

BI 확장은 원시 이벤트 수준 행이 아닌 집계된 데이터를 반환합니다. 기본적으로 각 쿼리는 30일 날짜 범위에 대해 50개의 행을 반환하지만, 행 제한을 최대 50,000개의 행으로, 날짜 범위를 사용자 지정 범위로 재정의할 수 있습니다. 자세한 내용은 [기본값 및 제한](../../data-views/bi-extension.md#defaults-and-limitations)을 참조하십시오.

자세한 내용은 [BI 확장](../../data-views/bi-extension.md)에 대한 자세한 설명서를 참조하십시오.
