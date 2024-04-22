---
title: Customer Journey Analytics으로 마이그레이션 시작
description: Adobe Analytics에서 Customer Journey Analytics으로의 마이그레이션 계획
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 8%

---

# 1단계: Customer Journey Analytics으로 마이그레이션 시작

Customer Journey Analytics은 차세대 분석입니다. 이를 통해 데이터 보기의 구성 요소 및 파생 필드 정의를 통해 강력한 보고서 시간 처리 기능과 결합된 다중 채널 데이터 수집(온라인 및 오프라인 데이터 모두)을 수행할 수 있습니다.

Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션하는 프로세스를 시작하기 전에 Customer Journey Analytics의 장점과 성공적으로 마이그레이션하는 데 필요한 단계를 이해해야 합니다.

## Customer Journey Analytics의 이점 이해

다음과 같은 몇 가지 주요 이점이 있습니다. (포괄적인 목록과 이러한 각 주요 기능에 대한 자세한 내용은 다음을 참조하십시오. [Customer Journey Analytics에서만 사용할 수 있는 기능](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [다중 채널 보고](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics는 모든 종류의 데이터 스키마와 유형을 보유할 수 있는 Experience Platform의 기능과 결합되어 있습니다. 디지털(웹), 판매 지점 시스템, 모바일, CRM 시스템 등 여러 채널의 데이터를 수집하고 보고합니다.

* [데이터 보기의 보고서 시간 변환](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Customer Journey Analytics의 데이터 보기를 사용하여 연결에서 데이터를 추가 해석할 수 있습니다. 구현을 변경하지 않고 데이터를 변경하거나 제거할 수 있고, 하위 문자열을 사용하여 차원을 조작하거나, 모든 값에서 지표를 생성하거나, 하위 이벤트를 필터링하거나, 파생된 필드를 사용할 수 있습니다. 이러한 모든 변환은 비파괴적입니다.

* [이전 및 새 데이터에 변형 적용](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  데이터 보기 조작은 과거 데이터와 새 데이터 모두에 비파괴인 방식으로 적용할 수 있습니다.

* [파생 필드](/help/data-views/derived-fields/derived-fields.md)

  파생 필드를 통해 데이터에 대한 보고 시간 변환이 가능합니다. 데이터는 즉시 결합하거나, 수정하거나, 생성할 수 있으며 모든 보고에 소급 적용됩니다.

* [데이터 보기가 가상 보고서 세트를 대체합니다.](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  데이터 보기 가상 보고서 세트의 개념을 가져와 을(를) 데이터에 대한 추가 제어 사용 연결에서 사용할 수 있습니다. 이러한 변경 사항은 시간대 및 세션 시간 초과 간격과 같은 일반 설정을 구성 및 소급 적용할 수 있도록 합니다.

* [무제한 고객 차원 및 지표](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  값은 숫자, 텍스트, 객체, 목록 또는 이들의 조합일 수 있습니다. Dimension은 중첩되거나 계층화될 수 있습니다.

## 마이그레이션 프로세스 이해

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
이 페이지는 다음 표와 같이 마이그레이션의 1단계를 나타냅니다. 이 표의 모든 단계를 완료하여 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션합니다.

| 작업 | 세부 사항 |
|---------|----------|
| **1단계: [마이그레이션 시작](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analytics으로 마이그레이션하는 것의 이점 및 기본 마이그레이션 프로세스에 대해 알아봅니다. |
| **2단계: [마이그레이션 방법 선택](/help/getting-started/cja-migration/cja-migration-method.md)** | Customer Journey Analytics으로 마이그레이션하는 데 다양한 방법을 사용할 수 있습니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표를 고려하여 조직에 가장 적합한 방법을 선택합니다. |
| **3단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 보내는 프로세스는 1단계에서 선택한 마이그레이션 방법에 따라 다릅니다. |
| **4단계: [XDM 스키마에 데이터 매핑](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM 스키마](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 는 Adobe Experience Platform에서 데이터의 구조를 일관되고 재사용 가능한 방식으로 설명하는 데 사용됩니다. 여러 시스템에서 데이터를 일관되게 정의하면 의미를 쉽게 유지할 수 있으므로 데이터의 가치를 얻을 수 있습니다.<p>대부분의 마이그레이션 방법을 사용하려면 새 XDM 스키마를 만들거나 데이터 스트림 매핑을 사용하여 기존 Adobe Analytics 스키마를 XDM에 매핑해야 합니다.</p> |
| **5단계: [이전 데이터 유지](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다. |
| **6단계: [플랜 사용자 온보딩](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 사용자에게 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점에 익숙해질 수 있는 충분한 시간(3~6개월)을 제공해야 합니다. |
| **7단계: [보고 API 사용 포트](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics 보고 API의 형식은 동일하지만 다른 끝점을 사용합니다. Adobe Analytics 보고 API의 보고 API 사용을 Customer Journey Analytics 보고 API로 포팅합니다. |
| **8단계: [데이터 피드 및 Data Warehouse 바꾸기](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analytics에서 사용 중이던 데이터 피드 및 Data Warehouse 기능을 대체하기 위해 Customer Journey Analytics에서 사용할 수 있는 내보내기 옵션을 사용하는 방법을 결정합니다. |
| **9단계: [프로젝트 및 구성 요소 마이그레이션](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics의 구성 요소 마이그레이션 영역에서 프로젝트 및 관련 구성 요소를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션할 수 있습니다. |
| **10단계: [마이그레이션 후 작업 수행](/help/getting-started/cja-getting-started.md)** | 마이그레이션을 완료한 후에는 다른 데이터를 Experience Platform으로 가져오기, 플랫폼 데이터 세트와 Customer Journey Analytics 간의 연결 만들기, 데이터 보기 만들기, Analysis Workspace에서 크로스 채널 데이터에 대해 보고하는 방법 학습 등 다양한 작업을 수행해야 합니다. |

{style="table-layout:auto"}

## 먼저 마이그레이션 방법을 선택합니다

Customer Journey Analytics으로 마이그레이션하는 데 다양한 방법을 사용할 수 있습니다. [조직에 가장 적합한 방법 선택](/help/getting-started/cja-migration/cja-migration-method.md).

선택하는 마이그레이션 방법은 조직의 현재 Adobe Analytics 환경과 장기적인 목표에 따라 다릅니다.
