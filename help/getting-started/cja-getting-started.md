---
title: Customer Journey Analytics 시작하기
description: Customer Journey Analytics를 구현하는 데 필요한 사전 요구 사항 및 워크플로를 이해합니다.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 100%

---

# Customer Journey Analytics 시작하기

Customer Journey Analytics를 구현하려면 이 워크플로를 따라야 합니다. 일부 초기 작업은 Adobe Experience Platform에서 수행되고, 일부는 Customer Journey Analytics에서 수행됩니다.

## 전제 조건

Customer Journey Analytics를 사용할 수 있는 고객은 다음과 같습니다.

* Adobe Analytics [Select, Prime 또는 Ultimate](https://www.adobe.com/kr/analytics/compare-adobe-analytics-packages.html) 고객 및
* [Adobe Experience Platform](https://www.adobe.com/kr/experience-platform.html)이 프로비저닝된 고객 및
* Customer Journey Analytics SKU를 구입한 고객

## 워크플로

| 작업 | 세부 사항 |
|---|---|
| **1단계: Adobe Experience Platform으로 데이터 가져오기** | Adobe Experience Platform에서 수행되는 이 단계에는 다음과 같은 몇 가지 하위 단계가 포함됩니다.<ul><li>**1a 단계: 데이터 스키마 준비**: [Adobe Experience Data Model(XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html)을 사용하여 고객 경험 데이터를 표준화하고 고객 경험 관리를 위한 [스키마를 정의](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)할 수 있습니다.</li><li>**1b 단계: 스키마를 기반으로 데이터 세트 만들기**: 플랫폼의 데이터는 이메일 데이터 세트, CRM 데이터 세트, POS 데이터 세트, Adobe Analytics 데이터 세트 등과 같은 데이터 세트로 구성됩니다. 각 데이터 세트는 스키마와 데이터 배치로 구성됩니다. [Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)에서 데이터 세트를 만들 수 있습니다.</li><li>**1c 단계: Experience Platform에 데이터 섭취**: 최신 Adobe Analytics Platform 커넥터를 사용하면 기존 Adobe Analytics 데이터를 플랫폼에 가져올 수 있습니다. 보고서 세트당 하나의 소스 연결을 만들 수 있습니다. Adobe Experience Platform 설명서의 [Adobe Analytics와 소스 연결 만들기](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)를 참조하십시오. 연결이 만들어지면 들어오는 데이터를 포함하도록 대상 스키마와 데이터 세트가 자동으로 생성됩니다. 또한 데이터 다시 채우기가 발생하고 최대 13개월 동안의 이전 데이터가 수집됩니다. 초기 수집이 완료되면 `Step 2`를 진행하여 이 Analytics 데이터 세트와 Customer Journey Analytics 간의 연결을 만들 수 있습니다. 또는 [일괄 처리 섭취](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md),[스트리밍 통합](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) 또는 [기타 소스 커넥터](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)를 통해 다른 데이터 유형을 섭취할 수 있습니다.</li></ul> |
| **2단계: 플랫폼 데이터 세트와 Customer Journey Analytics 간 연결 만들기** | 연결을 통해 Adobe Experience Platform의 데이터 세트를 작업 영역에 통합할 수 있습니다. Experience Platform 데이터 세트에 대해 보고하려면 먼저 Experience Platform과 작업 영역의 데이터 세트 간에 연결을 설정해야 합니다.<br>[연결 만들기](/help/connections/create-connection.md)를 참조하십시오. |
| **3단계: 데이터 보기 만들기** | 데이터 보기는 데이터의 &quot;필터링된&quot; 보기입니다. 방문 제한 시간, 속성 등에 대한 서로 다른 설정을 사용하여 동일한 연결에 대해 다른 데이터 보기를 만들 수 있습니다. 단일 데이터 세트에 대해 여러 데이터 보기를 만들 수 있습니다.<br>[데이터 보기 만들기](/help/data-views/create-dataview.md)를 참조하십시오. |
| **4단계: Analysis Workspace에서 크로스 채널 데이터 보고하기** | 연결 및 데이터 보기를 만든 후 Analysis Workspace의 강력한 기능과 유연성을 사용하여 가져온 데이터를 분석합니다.<br>[기본 분석 수행](/help/analysis-workspace/perform-basic-analysis.md) 및 [고급 분석 수행](/help/analysis-workspace/perform-adv-analysis.md)을 참조하십시오. |
