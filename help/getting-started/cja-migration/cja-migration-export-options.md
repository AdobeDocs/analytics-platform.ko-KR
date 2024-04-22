---
title: Customer Journey Analytics으로 마이그레이션할 때 데이터 피드 및 Data Warehouse 바꾸기
description: Adobe Analytics에서 Customer Journey Analytics으로의 마이그레이션 계획
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 3a99aed3-26b9-494f-aaf9-f8eaa2c2d88f
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# 8단계: Customer Journey Analytics으로 마이그레이션할 때 데이터 피드 및 Data Warehouse 바꾸기

+++이 섹션을 확장하여 이 페이지의 정보가 대규모 마이그레이션 프로세스에 맞는 위치를 확인합니다. 이전 마이그레이션 단계가 모두 완료되었는지 확인합니다.

이 섹션을 계속하기 전에 먼저 이전 마이그레이션 작업을 모두 완료했는지 확인하십시오.

이 페이지의 정보는 아래 표에 강조 표시된 대로 8단계를 다룹니다.

| 마이그레이션 작업 | 세부 사항 |
|---------|----------|
| **1단계: [마이그레이션 시작](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analytics으로 마이그레이션하는 것의 이점 및 기본 마이그레이션 프로세스에 대해 알아봅니다. |
| **2단계: [마이그레이션 방법 선택](/help/getting-started/cja-migration/cja-migration-method.md)** | Customer Journey Analytics으로 마이그레이션하는 데 다양한 방법을 사용할 수 있습니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 조직에 가장 적합한 방법을 선택합니다. |
| **3단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 보내는 프로세스는 1단계에서 선택한 마이그레이션 방법에 따라 다릅니다. |
| **4단계: [XDM 스키마에 데이터 매핑](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM 스키마](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 는 Adobe Experience Platform에서 데이터의 구조를 일관되고 재사용 가능한 방식으로 설명하는 데 사용됩니다. 여러 시스템에서 데이터를 일관되게 정의하면 의미를 쉽게 유지할 수 있으므로 데이터의 가치를 얻을 수 있습니다.<p>대부분의 마이그레이션 방법을 사용하려면 새 XDM 스키마를 만들거나 데이터 스트림 매핑을 사용하여 기존 Adobe Analytics 스키마를 XDM에 매핑해야 합니다.</p> |
| **5단계: [이전 데이터 유지](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다. |
| **6단계: [플랜 사용자 온보딩](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 사용자에게 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점에 익숙해질 수 있는 충분한 시간(3~6개월)을 제공해야 합니다. |
| **7단계: [보고 API 사용 포트](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics 보고 API의 형식은 동일하지만 다른 끝점을 사용합니다. Adobe Analytics 보고 API의 보고 API 사용을 Customer Journey Analytics 보고 API로 포팅합니다. |
| <span class="preview">**8단계: [데이터 피드 및 Data Warehouse 바꾸기](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">Adobe Analytics에서 사용 중이던 데이터 피드 및 Data Warehouse 기능을 대체하기 위해 Customer Journey Analytics에서 사용할 수 있는 내보내기 옵션을 사용하는 방법을 결정합니다.</span> |
| **9단계: [프로젝트 및 구성 요소 마이그레이션](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics의 구성 요소 마이그레이션 영역에서 프로젝트 및 관련 구성 요소를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션할 수 있습니다. |
| **10단계: [마이그레이션 후 작업 수행](/help/getting-started/cja-getting-started.md)** | 마이그레이션을 완료한 후에는 다른 데이터를 Experience Platform으로 가져오기, 플랫폼 데이터 세트와 Customer Journey Analytics 간의 연결 만들기, 데이터 보기 만들기, Analysis Workspace에서 크로스 채널 데이터에 대해 보고하는 방법 학습 등 다양한 작업을 수행해야 합니다. |

{style="table-layout:auto"}

+++

현재 Adobe Analytics에서 데이터 피드 또는 Data Warehouse을 사용하는 경우 다음 표를 사용하여 Customer Journey Analytics에서 사용할 수 있는 다양한 내보내기 옵션에 대해 알아보십시오.

| Adobe Analytics | Customer Journey Analytics |
|---------|----------|
| 데이터 피드 | 데이터 피드 사용 사례를 평가한 다음 Customer Journey Analytics에서 사용할 수 있는 대체 내보내기 방법의 조합을 사용하십시오. <ul><li>원시 데이터 세트를 내보내려면 [클라우드 스토리지 대상으로 데이터 세트 내보내기](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets). &#x200B;</li><li>개인 ID 또는 타임스탬프를 사용하는 대상 또는 이벤트 수준 내보내기의 경우 다음을 사용합니다. [전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md). &#x200B;</li><li>Power BI 및 Tableau와 직접 통합하려면 [Customer Journey Analytics BI 확장](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension). &#x200B;</li><li>Adobe Experience Platform의 데이터에 직접 SQL 액세스를 하려면 다음을 사용하십시오. [Adobe Experience Platform 쿼리 서비스](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> |
| Data Warehouse | 사용할 Adobe Analytics Data Warehouse 내보내기 변경 [전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md) Customer Journey Analytics.<p>Customer Journey Analytics 전체 테이블 내보내기는 Adobe Analytics에서 Data Warehouse 보고서가 발전한 것이며 현재 Data Warehouse에서 사용할 수 없는 많은 새로운 자주 요청하는 기능이 추가되었습니다.</p> |

{style="table-layout:auto"}

## 다음으로 프로젝트 및 구성 요소 마이그레이션

Adobe Analytics의 구성 요소 마이그레이션 영역을 사용하여 [프로젝트 및 관련 구성 요소 마이그레이션](/help/getting-started/cja-migration/cja-migration-projects.md) Adobe Analytics에서 Customer Journey Analytics으로.
