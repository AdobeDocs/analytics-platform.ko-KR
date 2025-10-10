---
title: Customer Journey Analytics 빠른 시작 안내서
description: Customer Journey Analytics를 구현하는 데 필요한 사전 요구 사항 및 워크플로를 이해합니다.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 6aa6605d12263110ad41523bf838d7a8702f89a2
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 100%

---

# 빠른 시작 안내서

Customer Journey Analytics를 구현하려면 이 워크플로를 따라야 합니다. 일부 초기 작업은 Adobe Experience Platform에서 수행되고, 일부는 Customer Journey Analytics에서 수행됩니다.

## 사전 요구 사항

Customer Journey Analytics를 사용할 수 있는 고객은 다음과 같습니다.

* [Adobe Experience Platform](https://www.adobe.com/kr/experience-platform.html)이 프로비저닝된 고객 및
* Customer Journey Analytics SKU를 구입한 고객

## 워크플로

| 작업 | 세부 사항 |
| --- | --- |
| **1단계: Adobe Analytics에서 Customer Journey Analytics로 업그레이드하는 경우: 업그레이드 경로를 선택하고 데이터를 Adobe Experience Platform으로 전송** | Adobe Analytics에서 Customer Journey Analytics로 업그레이드할 때 다양한 경로를 사용할 수 있습니다. 가능한 각 업그레이드 경로에는 고유한 장단점이 있으며, 하나의 조직에 적합한 경로가 다른 조직에는 적합하지 않을 수 있습니다. <p>Adobe Analytics에서 Customer Journey Analytics로 업그레이드를 시작하려면 다음 중 하나를 수행합니다.</p><ul><li>Adobe가 권장하는 업그레이드 경로를 따르십시오. 자세한 내용은 [Adobe Analytics에서 Customer Journey Analytics로 업그레이드할 때 권장되는 경로](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)를 참조하십시오.</li><li>사용 가능한 모든 업그레이드 경로에 대해 알아보고 조직에 가장 적합한 경로를 선택합니다. 자세한 내용은 [Customer Journey Analytics로 업그레이드 시작하기](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)를 참조하십시오.</li></ul> |
| **2단계: Adobe Experience Platform으로 다른 데이터 가져오기** | Adobe Experience Platform에서 수행되는 이 단계에는 다음과 같은 몇 가지 하위 단계가 포함됩니다.<ul><li>**2a 단계: 데이터 스키마 준비**: [Adobe Experience Data Model(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)을 사용하여 고객 경험 데이터를 표준화하고 고객 경험 관리를 위한 [스키마를 정의](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html)할 수 있습니다.</li><li>**2b 단계: 스키마를 기반으로 데이터 세트 만들기**: 플랫폼의 데이터는 이메일 데이터 세트, CRM 데이터 세트, POS 데이터 세트, Adobe Analytics 데이터 세트 등과 같은 데이터 세트로 구성됩니다. 각 데이터 세트는 스키마와 데이터 배치로 구성됩니다. [Experience Platform에서 데이터 세트를 생성](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html)할 수 있습니다.</li><li>**2c 단계: 데이터를 Experience Platform에 수집**: 여기, 몇 가지 옵션이 있습니다.</li></ul> |
| **3단계: 플랫폼 데이터 세트와 Customer Journey Analytics 간 연결 만들기** | 연결을 통해 Adobe Experience Platform의 데이터 세트를 작업 영역에 통합할 수 있습니다. Experience Platform 데이터 세트에 대해 보고하려면 먼저 Experience Platform과 작업 영역의 데이터 세트 간에 연결을 설정해야 합니다.<br>[연결 만들기 또는 편집](/help/connections/create-connection.md)을 참조하십시오. |
| **4단계: 데이터 보기 만들기** | 데이터 보기는 데이터의 “필터링된” 보기입니다. 방문 제한 시간, 속성 등에 대한 서로 다른 설정을 사용하여 동일한 연결에 대해 다른 데이터 보기를 만들 수 있습니다. 단일 데이터 세트에 대해 여러 데이터 보기를 만들 수 있습니다.<br>[데이터 보기 만들기](/help/data-views/create-dataview.md)를 참조하십시오. |
| **5단계: 보고 API 사용량 포팅**</br> Adobe Analytics에서 마이그레이션하는 경우에만 적용됨 | Customer Journey Analytics 보고 API는 동일한 형식이지만 다른 엔드포인트를 사용합니다. 보고 API 사용량을 Adobe Analytics 보고 API에서 Customer Journey Analytics 보고 API로 포팅합니다. |
| **6단계: 데이터 피드 및 데이터 웨어하우스 사용 사례 고려**</br> Adobe Analytics에서 마이그레이션하는 경우에만 적용됨 | Adobe Analytics에서 사용했던 데이터 피드 및 데이터 웨어하우스 기능을 가장 잘 복제하기 위해 Customer Journey Analytics에서 사용 가능한 내보내기 옵션을 사용할 방법을 결정하십시오. <!-- link to docs Rob is creating --> |
| **7단계: 프로젝트 및 구성 요소 마이그레이션**</br> Adobe Analytics에서 마이그레이션하는 경우에만 적용됨 | Adobe Analytics의 구성 요소 마이그레이션 영역을 사용하면 프로젝트 및 관련 구성 요소를 Adobe Analytics에서 Customer Journey Analytics로 마이그레이션할 수 있습니다.<p>마이그레이션 프로세스에 포함된 사항:</p><ul><li>Customer Journey Analytics에서 Adobe Analytics 프로젝트를 다시 생성합니다.</li><li>Adobe Analytics 보고서 세트의 차원 및 지표를 Customer Journey Analytics 데이터 보기의 차원 및 지표에 매핑합니다.</li></ul><p>마이그레이션을 시작하기 전에 먼저 [Adobe Analytics에서 Customer Journey Analytics로 구성 요소와 프로젝트 마이그레이션을 준비](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)하십시오.</p><p>필요한 준비를 모두 마치고 나면 [Adobe Analytics의 구성 요소와 프로젝트를 Customer Journey Analytics로 마이그레이션](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html)할 수 있습니다.</p> |
| **8단계: 사용자 온보딩 계획 수립** | Adobe Analytics와 마찬가지로 Analysis Workspace는 Customer Journey Analytics의 주요 사용자 대상 도구입니다. 단, Customer Journey Analytics에서 Analysis Workspace를 사용할 때 사용자가 알아 두어야 할 몇 가지 주요 차이점이 있습니다.<p>사용자가 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점을 숙지할 수 있도록 충분한 시간(3~6개월)을 할애하도록 하십시오.</p><p>Adobe Analytics와 Customer Journey Analytics의 주요 차이점에 대한 자세한 내용은 [Adobe Analytics 사용자를 위한 사용 안내서](/help/getting-started/aa-to-cja-user.md)를 참조하십시오.</p> |
| **9단계: Workspace에서 크로스 채널 데이터 보고하기** | 연결 및 데이터 보기를 만든 후 Analysis Workspace의 강력한 기능과 유연성을 사용하여 가져온 데이터를 분석합니다.<br>[기본 분석 수행](/help/analysis-workspace/perform-basic-analysis.md) 및 [고급 분석 수행](/help/analysis-workspace/perform-adv-analysis.md)을 참조하십시오. |

## 빠른 시작 안내서

[데이터 수집](../data-ingestion/data-ingestion.md) 섹션에서는 위의 워크플로에 대한 빠른 시작 안내서를 제공합니다. 이 빠른 시작 안내서에서는 Adobe Experience Platform의 다양한 소스(Adobe Analytics 포함)에서 데이터를 수집한 다음 Customer Journey Analytics에서 해당 데이터를 사용하는 방법을 설명합니다.
