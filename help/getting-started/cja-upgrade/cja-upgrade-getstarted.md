---
title: Customer Journey Analytics으로 업그레이드 시작
description: Adobe Analytics에서 Customer Journey Analytics으로의 업그레이드 계획
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 9%

---

# 1단계: Customer Journey Analytics으로 업그레이드 시작

>[!AVAILABILITY]
>
>이 페이지의 정보는 다음과 같은 보다 포괄적인 업그레이드 정보로 대체됩니다. <ul><li>**권장된 업그레이드 단계**<p>자세한 내용은 [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)를 참조하십시오.</p></li><li>**Customer Journey Analytics 업그레이드 안내서**<p>조직 및 고유한 환경에 맞게 조정된 업그레이드 단계를 동적으로 생성하는 새로운 업그레이드 가이드를 사용할 수 있습니다.</p><p>Customer Journey Analytics에서 가이드에 액세스하려면 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics으로 업그레이드]**&#x200B;를 선택합니다. 화면에 표시되는 안내를 따릅니다.</p></li></ul>

Customer Journey Analytics은 차세대 analytics입니다. 이를 통해 데이터 보기의 구성 요소 및 파생 필드 정의를 통해 강력한 보고서 시간 처리 기능과 결합된 다중 채널 데이터 수집(온라인 및 오프라인 데이터 모두)을 수행할 수 있습니다.

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 프로세스를 시작하기 전에 Customer Journey Analytics의 장점과 업그레이드를 성공적으로 수행하는 데 필요한 단계를 이해해야 합니다.

## Customer Journey Analytics의 이점 이해

다음과 같은 몇 가지 주요 이점이 있습니다. (이러한 각 주요 기능에 대한 자세한 내용과 전체 목록을 보려면 [Customer Journey Analytics에서만 사용할 수 있는 기능](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics)을 참조하세요.)

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

  값은 숫자, 텍스트, 객체, 목록 또는 이들의 조합일 수 있습니다. 차원은 중첩되거나 계층형 차원일 수 있습니다.

## 업그레이드 프로세스 이해

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
이 페이지의 정보는 아래 표에 강조 표시된 대로 업그레이드 프로세스의 1단계를 다룹니다. 이 표의 모든 단계를 완료하여 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하십시오.

| 업그레이드 작업 | 세부 사항 |
|---------|----------|
| <span class="preview">**1단계: 업그레이드 시작**</span> | <span class="preview">Customer Journey Analytics으로 업그레이드할 때의 이점 및 기본 업그레이드 프로세스에 대해 알아봅니다.</span> |
| **2단계: [업그레이드 경로 선택](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Customer Journey Analytics으로 업그레이드하는 방법은 다양합니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 조직에 가장 적합한 방법을 선택합니다. |
| **3단계: [Adobe Experience Platform에 데이터 보내기](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 전송하는 프로세스는 2단계에서 선택한 업그레이드 경로에 따라 다릅니다. |
| **4단계: [내역 데이터 유지](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다. |
| **5단계: [추가 구현 작업 수행](/help/getting-started/cja-getting-started.md)** | 업그레이드 프로세스의 이 시점에서 Customer Journey Analytics 환경을 사용하기 전에 다양한 작업을 수행해야 합니다.<p>이러한 추가 작업은 새로운 Customer Journey Analytics 구현뿐만 아니라 Adobe Analytics에서의 업그레이드에도 적용됩니다.</p><p>이러한 작업에는 다음이 포함됩니다.</p><ul><li>Experience Platform으로 다른 데이터 가져오기</li><li>Platform 데이터 세트와 Customer Journey Analytics 간 연결 만들기</li><li>데이터 보기 만들기</li><li>보고 API 사용 포팅</li><li>데이터 피드 및 Data Warehouse 계정</li><li>프로젝트 및 구성 요소 마이그레이션</li><li>Planning 사용자 온보딩</li></ul> <p>자세한 내용은 [Customer Journey Analytics 시작](/help/getting-started/cja-getting-started.md)을 참조하세요. |

{style="table-layout:auto"}

## 먼저 업그레이드 경로를 선택합니다

Customer Journey Analytics으로 업그레이드하는 방법은 다양합니다. [조직에 가장 적합한 방법을 선택하십시오](/help/getting-started/cja-upgrade/cja-upgrade-path.md).

선택하는 업그레이드 경로는 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 다릅니다.
