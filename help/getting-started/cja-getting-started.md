---
title: Customer Journey Analytics 시작하기
description: Customer Journey Analytics를 구현하는 데 필요한 사전 요구 사항 및 워크플로를 이해합니다.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 7bc4425f11980780ab64a201029cd63e4bd7849c
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 49%

---

# Customer Journey Analytics 시작하기

Customer Journey Analytics를 구현하려면 이 워크플로를 따라야 합니다. 일부 초기 작업은 Adobe Experience Platform에서 수행되고, 일부는 Customer Journey Analytics에서 수행됩니다.

## 사전 요구 사항

Customer Journey Analytics를 사용할 수 있는 고객은 다음과 같습니다.

* [Adobe Experience Platform](https://www.adobe.com/kr/experience-platform.html)이 프로비저닝된 고객 및
* Customer Journey Analytics SKU를 구입한 고객

## 워크플로

| 작업 | 세부 사항 |
| --- | --- |
| **1단계: Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션하는 경우: 마이그레이션 경로를 선택하고 데이터를 Adobe Experience Platform으로 보냅니다.** | Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션할 때 사용할 수 있는 경로에는 여러 가지가 있습니다. 가능한 각 마이그레이션 경로는 고유한 장점과 단점이 있으며 한 조직에 적합한 경로는 다른 조직에 적합하지 않을 수 있습니다. <p>Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션을 시작하려면 다음을 참조하십시오. [Customer Journey Analytics으로 마이그레이션 시작](/help/getting-started/cja-migration/cja-migration-getstarted.md). <!-- [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) --> </p> |
| **2단계: Adobe Experience Platform으로 다른 데이터 가져오기** | Adobe Experience Platform에서 수행되는 이 단계에는 다음과 같은 몇 가지 하위 단계가 포함됩니다.<ul><li>**2a 단계: 데이터 스키마 준비**: [Adobe Experience Data Model(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko-KR)을 사용하여 고객 경험 데이터를 표준화하고 고객 경험 관리를 위한 [스키마를 정의](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ko-KR)할 수 있습니다.</li><li>**2b 단계: 스키마를 기반으로 데이터 세트 만들기**: 플랫폼의 데이터는 이메일 데이터 세트, CRM 데이터 세트, POS 데이터 세트, Adobe Analytics 데이터 세트 등과 같은 데이터 세트로 구성됩니다. 각 데이터 세트는 스키마와 데이터 배치로 구성됩니다. [Experience Platform에서 데이터 세트를 생성](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=ko-KR)할 수 있습니다.</li><li>**2c 단계: 데이터를 Experience Platform에 수집**: 여기, 몇 가지 옵션이 있습니다.</li></ul> |
| **3단계: 플랫폼 데이터 세트와 Customer Journey Analytics 간 연결 만들기** | 연결을 통해 Adobe Experience Platform의 데이터 세트를 작업 영역에 통합할 수 있습니다. Experience Platform 데이터 세트에 대해 보고하려면 먼저 Experience Platform과 작업 영역의 데이터 세트 간에 연결을 설정해야 합니다.<br>[연결 만들기 또는 편집](/help/connections/create-connection.md)을 참조하십시오. |
| **4단계: 데이터 보기 만들기** | 데이터 보기는 데이터의 “필터링된” 보기입니다. 방문 제한 시간, 속성 등에 대한 서로 다른 설정을 사용하여 동일한 연결에 대해 다른 데이터 보기를 만들 수 있습니다. 단일 데이터 세트에 대해 여러 데이터 보기를 만들 수 있습니다.<br>[데이터 보기 만들기](/help/data-views/create-dataview.md)를 참조하십시오. |
| **5단계: 보고 API 사용 포트 지정**</br> Adobe Analytics에서 마이그레이션할 때만 적용됩니다. | Customer Journey Analytics 보고 API의 형식은 동일하지만 다른 끝점을 사용합니다. Adobe Analytics 보고 API의 보고 API 사용을 Customer Journey Analytics 보고 API로 포팅합니다. |
| **6단계: 데이터 피드 및 Data Warehouse 사용 사례 계정**</br> Adobe Analytics에서 마이그레이션할 때만 적용됩니다. | Adobe Analytics에서 사용 중이던 데이터 피드 및 Data Warehouse 기능을 최대한 복제하기 위해 Customer Journey Analytics에서 사용할 수 있는 내보내기 옵션을 사용하는 방법을 결정합니다. <!-- link to docs Rob is creating --> |
| **7단계: 프로젝트 및 구성 요소 마이그레이션**</br> Adobe Analytics에서 마이그레이션할 때만 적용됩니다. | Adobe Analytics의 구성 요소 마이그레이션 영역에서 프로젝트 및 관련 구성 요소를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션할 수 있습니다.<p>Customer Journey Analytics에서 Adobe Analytics 프로젝트를 복제하고 Adobe Analytics 보고서 세트의 프로젝트 구성 요소를 Customer Journey Analytics 데이터 보기에 매핑하는 방법에 대한 자세한 내용은 다음을 참조하십시오. [Adobe Analytics에서 Customer Journey Analytics으로 구성 요소 및 프로젝트 마이그레이션](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html).</p> |
| **8단계: 사용자 온보딩 계획** | Adobe Analytics에서와 마찬가지로 Analysis Workspace은 Customer Journey Analytics에서 사용자를 대면하는 주요 도구입니다. 그러나 Customer Journey Analytics에서 Analysis Workspace을 사용할 때 사용자가 알아야 하는 몇 가지 주요 차이점이 있습니다.<p>사용자에게 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점에 익숙해질 수 있는 충분한 시간(3~6개월)을 제공해야 합니다.</p><p>Adobe Analytics과 Customer Journey Analytics 간의 몇 가지 주요 차이점에 대한 자세한 내용은 [Adobe Analytics 사용자를 위한 사용 안내서](/help/getting-started/aa-to-cja-user.md).</p> |
| **9단계: Workspace에서 교차 채널 데이터 보고하기** | 연결 및 데이터 보기를 만든 후 Analysis Workspace의 강력한 기능과 유연성을 사용하여 가져온 데이터를 분석합니다.<br>[기본 분석 수행](/help/analysis-workspace/perform-basic-analysis.md) 및 [고급 분석 수행](/help/analysis-workspace/perform-adv-analysis.md)을 참조하십시오. |

## 빠른 시작 안내서

[데이터 수집](../data-ingestion/data-ingestion.md) 섹션에서는 위의 워크플로에 대한 빠른 시작 안내서를 제공합니다. 이 빠른 시작 안내서에서는 Adobe Experience Platform의 다양한 소스(Adobe Analytics 포함)에서 데이터를 수집한 다음 Customer Journey Analytics에서 해당 데이터를 사용하는 방법을 설명합니다.
