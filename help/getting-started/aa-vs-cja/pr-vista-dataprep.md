---
title: Analytics 소스 커넥터에 대한 처리 규칙, VISTA 및 분류와 데이터 준비
description: 처리 규칙 및 VISTA를 사용한 데이터 변환과 데이터 준비 사용에 대해 알아봅니다
source-git-commit: f6b8c5f1e8e82d0eb856b5cfed63b72c7ecfe3db
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 6%

---


# 처리 규칙, VISTA 및 분류 대 데이터 준비

Adobe Analytics [처리 규칙 및 VISTA 규칙](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) Adobe Analytics에 전달되는 데이터를 변환하고 조작하는 수단을 제공합니다 [데이터 수집](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). 이러한 변환은 Adobe Analytics에서 보고 및 분석 목적으로 데이터가 저장되기 전에 Adobe의 데이터 처리의 일부로 발생합니다.

[데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko-KR) 는 수집된 데이터에 행 기반 매핑 및 변형을 적용할 수 있는 도구입니다 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en). 그런 다음 CJA 등을 비롯한 Experience Platform 애플리케이션에서 데이터를 사용할 수 있습니다. 데이터 준비는 많은 플랫폼과 통합됩니다 [소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en)뿐만 아니라 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko). 이 커넥터는 Adobe Analytics에서 플랫폼으로 보고서 세트 데이터를 수집하는 방법을 제공합니다.

## 데이터 준비를 사용한 추가 변형 {#data-prep}

Adobe Analytics에 의해 수집되고 저장된 데이터는 처리 규칙 또는 VISTA 규칙 또는 둘 다로 변환할 수 있습니다. 그러나 Analytics 소스 커넥터를 통해 Platform에 전달되는 보고서 세트는 데이터 준비를 사용하여 다른 시간에 변환될 수 있습니다. 이는 다음과 같은 여러 가지 목적으로 권장될 수 있습니다.

* **CJA와 RTCDP에서 사용할 보고서 세트 간의 스키마 차이점 해결**. 예를 들어 보고서 세트 A가 다음을 정의한다고 가정해 보겠습니다 `eVar1` 를 &quot;검색어&quot;로 정의하고 보고서 세트 B는 다음을 정의합니다 `eVar2` 을 &quot;검색어&quot;로 지정합니다. 데이터 준비를 사용하여 두 개의 서로 다른 eVar를 두 eVar의 데이터를 포함하는 공통 필드에 매핑할 수 있습니다. 이를 통해 다음을 수행할 수 있습니다. [보고서 세트를 다른 스키마와 결합](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) 에서 [CJA 연결](/help/connections/overview.md) 또는 를 사용하기 위해 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=ko).
* **매핑 `eVars` 의미상 의미 있는 이름 필드**. `eVars` 및 `props` Analytics 소스 커넥터를 통해 들어오는 것은 다음과 같은 필드에 매핑됩니다. _\_experience.analytics.customDimensions.eVars.eVar1_. 데이터 준비를 사용하여 매핑할 수 있습니다 `eVar` 및 `prop` 사용자에게 더 의미 있는 이름이 있거나 다른 데이터 소스에서 온 이름과 일치하는 새 필드에 필드를 추가합니다. (이 작업은 또한 [CJA 데이터 보기](/help/data-views/create-dataview.md))
* **일반적으로 데이터 변환**. 데이터 준비에는 Analytics 소스 커넥터를 통해 들어오는 데이터를 기반으로 새 필드를 계산하고 계산하는 데 사용할 수 있는 수백 개의 매핑 기능이 있습니다. 구분된 필드를 별도의 필드로 분할할 수 있습니다. 필드를 결합할 수 있습니다. 문자열을 조작할 수 있습니다. 정규 표현식 등을 기반으로 필드에서 정보를 추출할 수 있습니다.

## 데이터 준비 및 분류 {#classifications}

데이터 준비에 [분류](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=ko) 어떤 경우에는

예를 들어, 구분된 필드에서 데이터 준비를 사용하여 분류를 사용하지 않고 해당 필드를 여러 개별 필드로 분할할 수 있습니다. 일반적으로 분류는 들어오는 Analytics 히트의 스트림 외부에 제공된 조회 파일을 업로드하여 필드에 메타데이터를 추가하는 방법입니다.

예를 들어 SKU를 &#39;크기&#39;, &#39;브랜드&#39;, &#39;색상&#39; 등으로 그룹화하는 분류 파일을 업로드할 수 있습니다. 분류와 데이터 준비 간의 또 다른 차이점은 분류가 데이터에 적용된다는 것입니다 _역사적으로나 앞으로 나아가기_. 반면 데이터 준비 매핑은 적용됩니다 _forward_ 매핑 생성 시점부터 데이터까지.

