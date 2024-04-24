---
title: Customer Journey Analytics으로 마이그레이션할 때 데이터를 XDM 스키마에 매핑
description: Customer Journey Analytics으로 마이그레이션할 때 데이터를 XDM 스키마에 매핑하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 86ce60cf-b3c7-43b5-aa18-9e16fa942e54
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 0%

---

# 4단계: Customer Journey Analytics으로 마이그레이션할 때 데이터를 XDM 스키마에 매핑

+++이 섹션을 확장하여 이 페이지의 정보가 대규모 마이그레이션 프로세스에 맞는 위치를 확인합니다. 이전 마이그레이션 단계가 모두 완료되었는지 확인합니다.

이 섹션을 계속하기 전에 먼저 이전 마이그레이션 작업을 모두 완료했는지 확인하십시오.

이 페이지의 정보는 아래 표에 강조 표시된 대로 4단계를 다룹니다.

| 마이그레이션 작업 | 세부 사항 |
|---------|----------|
| **1단계: [마이그레이션 시작](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analytics으로 마이그레이션하는 것의 이점 및 기본 마이그레이션 프로세스에 대해 알아봅니다. |
| **2단계: [마이그레이션 경로 선택](/help/getting-started/cja-migration/cja-migration-path.md)** | Customer Journey Analytics으로 마이그레이션하는 데 다양한 방법을 사용할 수 있습니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 조직에 가장 적합한 방법을 선택합니다. |
| <span class="preview">**3단계: [XDM 스키마에 데이터 매핑](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[XDM 스키마](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 는 Adobe Experience Platform에서 데이터의 구조를 일관되고 재사용 가능한 방식으로 설명하는 데 사용됩니다. 여러 시스템에서 데이터를 일관되게 정의하면 의미를 쉽게 유지할 수 있으므로 데이터의 가치를 얻을 수 있습니다.<p>대부분의 마이그레이션 경로에서는 새 XDM 스키마를 만들거나 데이터 스트림 매핑을 사용하여 기존 Adobe Analytics 스키마를 XDM에 매핑해야 합니다.</p></span> |
| **4단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 보내는 프로세스는 2단계에서 선택한 마이그레이션 경로에 따라 다릅니다. |
| **5단계: [이전 데이터 유지](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다. |
| **6단계: [플랜 사용자 온보딩](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 사용자에게 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점에 익숙해질 수 있는 충분한 시간(3~6개월)을 제공해야 합니다. |
| **7단계: [보고 API 사용 포트](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics 보고 API의 형식은 동일하지만 다른 끝점을 사용합니다. Adobe Analytics 보고 API의 보고 API 사용을 Customer Journey Analytics 보고 API로 포팅합니다. |
| **8단계: [데이터 피드 및 Data Warehouse 바꾸기](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analytics에서 사용 중이던 데이터 피드 및 Data Warehouse 기능을 대체하기 위해 Customer Journey Analytics에서 사용할 수 있는 내보내기 옵션을 사용하는 방법을 결정합니다. |
| **9단계: [프로젝트 및 구성 요소 마이그레이션](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics의 구성 요소 마이그레이션 영역에서 프로젝트 및 관련 구성 요소를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션할 수 있습니다. |

{style="table-layout:auto"}

+++

[XDM 스키마](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 는 Adobe Experience Platform에서 데이터의 구조를 일관되고 재사용 가능한 방식으로 설명하는 데 사용됩니다. 여러 시스템에서 데이터를 일관되게 정의하면 의미를 쉽게 유지할 수 있으므로 데이터의 가치를 얻을 수 있습니다.<p>대부분의 마이그레이션 경로에서는 새 XDM 스키마를 만들거나 데이터 스트림 매핑을 사용하여 기존 Adobe Analytics 스키마를 XDM에 매핑해야 합니다.</p>

일부 마이그레이션 경로에서는 Adobe Analytics 데이터를 XDM 스키마에 매핑할 필요가 없습니다. 다음 표는 XDM 스키마 매핑이 필요한 구현 방법을 보여 줍니다.


| 마이그레이션 경로 | XDM 매핑이 필요하십니까? | 추가 정보 |
|---------|----------|---------|
| **Experience Platform 웹 SDK의 새로운 구현**<p>기본 단계는 다음과 같습니다.</p><ol><li>조직에 대한 XDM 스키마 만들기</li><li>웹 SDK 구현</li><li>플랫폼으로 데이터 보내기</li></ol> | 아니요 | 매핑이 필요하지 않습니다. [새 XDM 스키마 설정](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) 를 새 구현의 일부로 사용합니다. |
| **웹 SDK를 사용하도록 Adobe Analytics 구현 마이그레이션**<p>기본 단계는 다음과 같습니다.</p><ol><li>기존 Adobe Analytics 구현을 웹 SDK로 이동하고 모든 것이 제대로 작동하는지 확인하십시오.</li><li>시간이 지남에 따라 조직에 대한 XDM 스키마를 만듭니다.</li><li>데이터 스트림 매핑을 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다.</li><li>플랫폼으로 데이터 보내기</li></ol> | 예 | 데이터 팀과 함께 Customer Journey Analytics에 대한 조직의 이상적인 스키마 디자인을 식별한 다음 eVar 및 Prop을 XDM에 매핑하는 방법을 결정합니다.</br>[데이터 준비를 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **기존 Adobe Analytics Web SDK 구현을 구성하여 데이터를 Customer Journey Analytics으로 전송**<p>기본 단계는 다음과 같습니다.</p><ol><li>Customer Journey Analytics으로 데이터 전송을 시작합니다.<!-- What's involved here? Just point it at CJA? --></li><li>(선택 사항) 시간이 있을 때 조직에 대한 XDM 스키마를 만듭니다.</li><li>데이터 스트림 매핑을 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다.</li></ol> | 예 | 데이터 팀과 함께 Customer Journey Analytics에 대한 조직의 이상적인 스키마 디자인을 식별한 다음 eVar 및 Prop을 XDM에 매핑하는 방법을 결정합니다.</br>[데이터 준비를 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Analytics 소스 커넥터**</br> Adobe Analytics 구현이 AppMeasurement 또는 Analytics 확장 기능인 경우 Customer Journey Analytics의 데이터 보기로 데이터 전송을 시작할 수 있습니다.<p>이는 데이터를 Customer Journey Analytics에 가져오는 가장 쉬운 방법이지만 장기적으로 가장 실행 가능성이 낮은 방법입니다.</p> | 아니요 | Analytics 소스 커넥터가 XDM 스키마가 아닌 기존 Adobe Analytics 스키마를 사용하므로 매핑이 필요하지 않습니다. |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## 그런 다음 Adobe Experience Platform으로 데이터 보내기

위의 정보를 사용하여 마이그레이션 경로를 선택한 후 방법 알아보기 [Adobe Experience Platform에 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) 선택한 마이그레이션 경로에 따라 다릅니다.
