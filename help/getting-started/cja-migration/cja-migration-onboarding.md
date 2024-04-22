---
title: Customer Journey Analytics으로 마이그레이션할 때 사용자 온보딩 계획
description: Customer Journey Analytics으로 마이그레이션할 때 사용자 온보딩 계획
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 90a4aed62ec64f4e58e982a65bfce45789b5cdbb
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# 6단계: Customer Journey Analytics으로 마이그레이션할 때 사용자 온보딩 계획

+++이 페이지의 정보는 대규모 마이그레이션 프로세스의 일부입니다. 이 섹션을 확장하여 마이그레이션 프로세스에서 이 정보가 어디에 적합한지 확인하십시오. </br></br>이 페이지의 정보를 계속 진행하기 전에 이전의 모든 마이그레이션 단계를 완료해야 합니다.

이 섹션을 계속하기 전에 먼저 이전 마이그레이션 작업을 모두 완료했는지 확인하십시오.

이 페이지의 정보에는 아래 표에 강조 표시된 6단계가 포함됩니다.

| 마이그레이션 작업 | 세부 사항 |
|---------|----------|
| **1단계: [마이그레이션 시작](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analytics으로 마이그레이션하는 것의 이점 및 기본 마이그레이션 프로세스에 대해 알아봅니다. |
| **2단계: [마이그레이션 방법 선택](/help/getting-started/cja-migration/cja-migration-method.md)** | Customer Journey Analytics으로 마이그레이션하는 데 다양한 방법을 사용할 수 있습니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 조직에 가장 적합한 방법을 선택합니다. |
| **3단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 보내는 프로세스는 1단계에서 선택한 마이그레이션 방법에 따라 다릅니다. |
| **4단계: [XDM 스키마에 데이터 매핑 계획](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM 스키마](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 는 Adobe Experience Platform에서 데이터의 구조를 일관되고 재사용 가능한 방식으로 설명하는 데 사용됩니다. 여러 시스템에서 데이터를 일관되게 정의하면 의미를 쉽게 유지할 수 있으므로 데이터의 가치를 얻을 수 있습니다.<p>대부분의 마이그레이션 방법을 사용하려면 새 XDM 스키마를 만들거나 데이터 스트림 매핑을 사용하여 기존 Adobe Analytics 스키마를 XDM에 매핑해야 합니다.</p> |
| **5단계: [이전 데이터 유지](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다. |
| <span class="preview">**6단계: [플랜 사용자 온보딩](/help/getting-started/cja-migration/cja-migration-onboarding.md)**</span> | <span class="preview">사용자에게 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점에 익숙해질 수 있는 충분한 시간(3~6개월)을 제공해야 합니다.</span> |
| **7단계: [보고 API 사용 포트](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics 보고 API의 형식은 동일하지만 다른 끝점을 사용합니다. Adobe Analytics 보고 API의 보고 API 사용을 Customer Journey Analytics 보고 API로 포팅합니다. |
| **8단계: [데이터 피드 및 Data Warehouse 바꾸기](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analytics에서 사용 중이던 데이터 피드 및 Data Warehouse 기능을 대체하기 위해 Customer Journey Analytics에서 사용할 수 있는 내보내기 옵션을 사용하는 방법을 결정합니다. |
| **9단계: [프로젝트 및 구성 요소 마이그레이션](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics의 구성 요소 마이그레이션 영역에서 프로젝트 및 관련 구성 요소를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션할 수 있습니다. |

{style="table-layout:auto"}

+++

Customer Journey Analytics과 Adobe Analytics 사이에는 사용자가 알아야 하는 몇 가지 주요 차이점이 있습니다.

Adobe Analytics에서와 마찬가지로 Analysis Workspace은 Customer Journey Analytics에서 사용자를 대면하는 주요 도구입니다. 그러나 Customer Journey Analytics에서 Analysis Workspace을 사용할 때 사용자가 알아야 하는 몇 가지 주요 차이점이 있습니다.

사용자에게 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점에 익숙해질 수 있는 충분한 시간(3~6개월)을 제공해야 합니다.

Adobe Analytics과 Customer Journey Analytics 간의 몇 가지 주요 차이점에 대한 자세한 내용은 [Adobe Analytics 사용자를 위한 사용 안내서](/help/getting-started/aa-to-cja-user.md).

## 그런 다음 보고 API 사용을 포팅합니다

Customer Journey Analytics 보고 API의 형식은 동일하지만 다른 끝점을 사용합니다. [보고 API 사용 포트](/help/getting-started/cja-migration/cja-migration-api.md) Adobe Analytics 보고 API에서 Customer Journey Analytics 보고 API로 변경되었습니다.