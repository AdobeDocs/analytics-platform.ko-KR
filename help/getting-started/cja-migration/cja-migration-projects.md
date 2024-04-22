---
title: Customer Journey Analytics으로 프로젝트 및 구성 요소 마이그레이션
description: Customer Journey Analytics으로 프로젝트 및 구성 요소를 마이그레이션하기 위한 구성 요소 마이그레이션에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 6e5c3ecf-6eba-4dfa-8bf2-e43d56cfc65f
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 11%

---

# 9단계: 프로젝트 및 구성 요소를 Customer Journey Analytics으로 마이그레이션

+++이 섹션을 확장하여 이 페이지의 정보가 대규모 마이그레이션 프로세스에 맞는 위치를 확인합니다. 이전 마이그레이션 단계가 모두 완료되었는지 확인합니다.

이 섹션을 계속하기 전에 먼저 이전 마이그레이션 작업을 모두 완료했는지 확인하십시오.

이 페이지의 정보는 아래 표에 강조 표시된 대로 9단계를 다룹니다.

| 마이그레이션 작업 | 세부 사항 |
|---------|----------|
| **1단계: [마이그레이션 시작](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analytics으로 마이그레이션하는 것의 이점 및 기본 마이그레이션 프로세스에 대해 알아봅니다. |
| **2단계: [마이그레이션 방법 선택](/help/getting-started/cja-migration/cja-migration-method.md)** | Customer Journey Analytics으로 마이그레이션하는 데 다양한 방법을 사용할 수 있습니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 조직에 가장 적합한 방법을 선택합니다. |
| **3단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 보내는 프로세스는 1단계에서 선택한 마이그레이션 방법에 따라 다릅니다. |
| **4단계: [XDM 스키마에 데이터 매핑](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM 스키마](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 는 Adobe Experience Platform에서 데이터의 구조를 일관되고 재사용 가능한 방식으로 설명하는 데 사용됩니다. 여러 시스템에서 데이터를 일관되게 정의하면 의미를 쉽게 유지할 수 있으므로 데이터의 가치를 얻을 수 있습니다.<p>대부분의 마이그레이션 방법을 사용하려면 새 XDM 스키마를 만들거나 데이터 스트림 매핑을 사용하여 기존 Adobe Analytics 스키마를 XDM에 매핑해야 합니다.</p> |
| **5단계: [이전 데이터 유지](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다. |
| **6단계: [플랜 사용자 온보딩](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 사용자에게 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점에 익숙해질 수 있는 충분한 시간(3~6개월)을 제공해야 합니다. |
| **7단계: [보고 API 사용 포트](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics 보고 API의 형식은 동일하지만 다른 끝점을 사용합니다. Adobe Analytics 보고 API의 보고 API 사용을 Customer Journey Analytics 보고 API로 포팅합니다. |
| **8단계: [데이터 피드 및 Data Warehouse 바꾸기](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analytics에서 사용 중이던 데이터 피드 및 Data Warehouse 기능을 대체하기 위해 Customer Journey Analytics에서 사용할 수 있는 내보내기 옵션을 사용하는 방법을 결정합니다. |
| <span class="preview">**9단계: [프로젝트 및 구성 요소 마이그레이션](/help/getting-started/cja-migration/cja-migration-projects.md)**</span> | <span class="preview">Adobe Analytics의 구성 요소 마이그레이션 영역에서 프로젝트 및 관련 구성 요소를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션할 수 있습니다.</span> |
| **10단계: [마이그레이션 후 작업 수행](/help/getting-started/cja-getting-started.md)** | 마이그레이션을 완료한 후에는 다른 데이터를 Experience Platform으로 가져오기, 플랫폼 데이터 세트와 Customer Journey Analytics 간의 연결 만들기, 데이터 보기 만들기, Analysis Workspace에서 크로스 채널 데이터에 대해 보고하는 방법 학습 등 다양한 작업을 수행해야 합니다. |

{style="table-layout:auto"}

+++

Adobe Analytics의 구성 요소 마이그레이션 영역에서 프로젝트 및 관련 구성 요소를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션할 수 있습니다.

마이그레이션 프로세스에 포함된 사항:

* Customer Journey Analytics에서 Adobe Analytics 프로젝트를 다시 생성합니다.

* Adobe Analytics 보고서 세트의 차원 및 지표를 Customer Journey Analytics 데이터 보기의 차원 및 지표에 매핑합니다.

마이그레이션을 시작하기 전에 먼저 [Adobe Analytics에서 Customer Journey Analytics로 구성 요소와 프로젝트 마이그레이션을 준비](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)하십시오.

필요한 준비를 모두 마치고 나면 [Adobe Analytics의 구성 요소와 프로젝트를 Customer Journey Analytics로 마이그레이션](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html)할 수 있습니다.

## 다음으로 마이그레이션 후 작업 수행

이후 [Adobe Analytics에서 Customer Journey Analytics으로 구성 요소 및 프로젝트 마이그레이션](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html), Customer Journey Analytics 환경 설정을 완료하려면 다양한 작업을 수행해야 합니다. 이러한 작업에는 다른 데이터를 Experience Platform으로 가져오기, 플랫폼 데이터 세트와 Customer Journey Analytics 간에 연결 만들기, 데이터 보기 만들기, Analysis Workspace에서 크로스 채널 데이터에 대해 보고하는 방법 학습 등이 포함됩니다.

에서 이러한 마이그레이션 작업에 대해 자세히 알아보십시오. [Customer Journey Analytics 시작](/help/getting-started/cja-getting-started.md).
