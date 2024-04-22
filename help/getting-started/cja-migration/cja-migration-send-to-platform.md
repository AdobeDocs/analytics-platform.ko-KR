---
title: Customer Journey Analytics으로 마이그레이션할 때 Adobe Experience Platform으로 데이터 보내기
description: Customer Journey Analytics으로 마이그레이션할 때 Adobe Experience Platform으로 데이터 보내기
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 1%

---

# 3단계: Customer Journey Analytics으로 마이그레이션할 때 Adobe Experience Platform으로 데이터 보내기

+++이 섹션을 확장하여 이 페이지의 정보가 대규모 마이그레이션 프로세스에 맞는 위치를 확인합니다. 이전 마이그레이션 단계가 모두 완료되었는지 확인합니다.

이 섹션을 계속하기 전에 먼저 이전 마이그레이션 작업을 모두 완료했는지 확인하십시오.

이 페이지의 정보는 아래 표에 강조 표시된 대로 3단계를 다룹니다.

| 마이그레이션 작업 | 세부 사항 |
|---------|----------|
| **1단계: [마이그레이션 시작](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analytics으로 마이그레이션하는 것의 이점 및 기본 마이그레이션 프로세스에 대해 알아봅니다. |
| **2단계: [마이그레이션 방법 선택](/help/getting-started/cja-migration/cja-migration-method.md)** | Customer Journey Analytics으로 마이그레이션하는 데 다양한 방법을 사용할 수 있습니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 조직에 가장 적합한 방법을 선택합니다. |
| <span class="preview">**3단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)**</span> | <span class="preview">Adobe Experience Platform으로 데이터를 보내는 프로세스는 1단계에서 선택한 마이그레이션 방법에 따라 다릅니다.</span> |
| **4단계: [XDM 스키마에 데이터 매핑](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM 스키마](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 는 Adobe Experience Platform에서 데이터의 구조를 일관되고 재사용 가능한 방식으로 설명하는 데 사용됩니다. 여러 시스템에서 데이터를 일관되게 정의하면 의미를 쉽게 유지할 수 있으므로 데이터의 가치를 얻을 수 있습니다.<p>대부분의 마이그레이션 방법을 사용하려면 새 XDM 스키마를 만들거나 데이터 스트림 매핑을 사용하여 기존 Adobe Analytics 스키마를 XDM에 매핑해야 합니다.</p> |
| **5단계: [이전 데이터 유지](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다. |
| **6단계: [플랜 사용자 온보딩](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 사용자에게 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점에 익숙해질 수 있는 충분한 시간(3~6개월)을 제공해야 합니다. |
| **7단계: [보고 API 사용 포트](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics 보고 API의 형식은 동일하지만 다른 끝점을 사용합니다. Adobe Analytics 보고 API의 보고 API 사용을 Customer Journey Analytics 보고 API로 포팅합니다. |
| **8단계: [데이터 피드 및 Data Warehouse 바꾸기](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analytics에서 사용 중이던 데이터 피드 및 Data Warehouse 기능을 대체하기 위해 Customer Journey Analytics에서 사용할 수 있는 내보내기 옵션을 사용하는 방법을 결정합니다. |
| **9단계: [프로젝트 및 구성 요소 마이그레이션](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics의 구성 요소 마이그레이션 영역에서 프로젝트 및 관련 구성 요소를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션할 수 있습니다. |

{style="table-layout:auto"}

+++


이후 [마이그레이션 방법 선택](#step-2-choose-your-customer-journey-analytics-migration-method) 조직에 가장 적합합니다. Adobe Experience Platform에 데이터를 전송하여 Customer Journey Analytics에서 사용할 수 있도록 할 수 있습니다.

각 마이그레이션 방법에 대해 데이터를 Experience Platform에 보내는 프로세스는 아래에 나와 있습니다. 자세한 내용은 아래 표의 링크를 참조하십시오.

| 마이그레이션 메서드 | 데이터를 플랫폼으로 전송하는 프로세스 |
|---------|----------|
| 웹 SDK의 새로운 구현 | [Adobe Experience Platform Web SDK를 통해 데이터 수집](/help/data-ingestion/aepwebsdk.md) |
| 웹 SDK를 사용하도록 Adobe Analytics 구현 마이그레이션 | Analytics 태그 확장을 사용하는 경우: [Adobe Analytics 태그 확장에서 웹 SDK 태그 확장으로 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)<p>또는</p><p>AppMeasurement을 사용하는 경우: [AppMeasurement에서 웹 SDK로 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) |
| 기존 Adobe Analytics Web SDK 구현을 구성하여 데이터를 Customer Journey Analytics으로 전송 | [데이터 스트림 설정](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream) 위치: [Adobe Experience Platform Web SDK를 통해 데이터 수집](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) |
| Analytics 소스 커넥터 | [기존 Adobe Analytics에서 데이터 수집 및 사용](/help/data-ingestion/analytics.md) |

## 그런 다음 데이터를 XDM 스키마에 매핑합니다

위 표의 링크를 따라 데이터를 Experience Platform으로 보낸 후 다음을 수행해야 할 수 있습니다. [데이터를 XDM 스키마에 매핑](/help/getting-started/cja-migration/cja-migration-xdm.md)선택한 구현 방법에 따라 다릅니다.

다음 구현 방법을 사용하려면 데이터를 XDM 스키마에 매핑해야 합니다.

* Adobe Analytics 태그 확장에서 웹 SDK 태그 확장으로 마이그레이션

* 기존 Adobe Analytics Web SDK 구현을 구성하여 데이터를 Customer Journey Analytics으로 전송

또는 웹 SDK의 새 구현을 수행하기로 선택한 경우 이미 존재하기 때문에 매핑이 필요하지 않습니다 [새 XDM 스키마 설정](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) 를 새 구현의 일부로 사용합니다.

마이그레이션에 Analytics 소스 커넥터를 사용하도록 선택한 경우 Analytics 소스 커넥터가 XDM 스키마가 아닌 기존 Adobe Analytics 스키마를 사용하므로 매핑이 필요하지 않습니다.
