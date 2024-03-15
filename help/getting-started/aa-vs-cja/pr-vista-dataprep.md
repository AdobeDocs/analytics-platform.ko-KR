---
title: 처리 규칙, VISTA 및 분류 대 Analytics 소스 커넥터에 대한 데이터 준비
description: 처리 규칙 및 VISTA를 사용한 데이터 변환과 데이터 준비를 사용한 데이터 변환에 대해 알아보기
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
feature: Basics
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '546'
ht-degree: 100%

---

# 처리 규칙, VISTA 및 분류 대 데이터 준비

Adobe Analytics [처리 규칙 및 VISTA 규칙](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html)은 Adobe Analytics [데이터 수집](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=ko-KR)으로 전달되는 데이터를 변환하고 조작하는 수단을 제공합니다. 이러한 변환은 Adobe Analytics에 보고 및 분석 목적으로 데이터가 저장되기 전에 Adobe 데이터 처리의 일부로 발생합니다.

[데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko-KR)는 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html)에 수집된 데이터에 행 기반 매핑 및 변환을 적용할 수 있는 도구입니다. 그런 다음 Customer Journey Analytics 등을 포함한 Experience Platform 애플리케이션에 데이터를 사용할 수 있습니다. 데이터 준비는 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)뿐만 아니라 많은 Platform [소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ko)와 통합됩니다. 이 커넥터는 Adobe Analytics에서 플랫폼으로 보고서 세트 데이터를 수집하는 방법을 제공합니다.

## 데이터 준비를 사용한 추가 변환 {#data-prep}

Adobe Analytics에 의해 수집되고 저장되는 데이터는 처리 규칙이나 VISTA 규칙 또는 둘 다에 의해 변환될 수 있습니다. 그러나 Analytics 소스 커넥터를 통해 Platform으로 전달되는 보고서 세트는 다음에 데이터 준비를 사용하여 변환할 수 있습니다. 이는 다음과 같은 여러 가지 목적에 적합할 수 있습니다.

* **Customer Journey Analytics 및/또는 RTCDP에서 사용할 보고서 세트 간의 스키마 차이 해결**. 예를 들어 보고서 세트 A가 `eVar1`을 “검색어”로 정의하고 보고서 세트 B가 `eVar2`를 “검색어”로 정의한다고 합시다. 데이터 준비를 사용하여 두 개의 서로 다른 eVar를 두 eVar의 데이터가 포함된 공통 필드로 매핑할 수 있습니다. 이렇게 하면 [Customer Journey Analytics 연결](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html) 또는 [Real-time Customer Data Platform](/help/connections/overview.md)에서 사용하기 위해 [서로 다른 스키마를 가진 보고서 세트를 결합](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html)할 수 있습니다.
* **`eVars` 필드를 의미 있는 이름으로 매핑**. Analytics 소스 커넥터를 통해 들어오는 `eVars` 및 `props`는 _\_experience.analytics.customDimensions.eVars.eVar1_&#x200B;과 같은 필드에 매핑됩니다. 데이터 준비는 `eVar` 및 `prop` 필드를 사용자에게 더 의미 있는 이름을 가지거나 다른 데이터 소스에서 가져온 이름과 일치하는 새 필드에 매핑하는 데 사용할 수 있습니다. (이 작업은 [Customer Journey Analytics 데이터 보기](/help/data-views/create-dataview.md)의 필드 이름 변경과 같은 다른 방법을 통해서도 수행할 수 있습니다.)
* **일반적으로 데이터 변환**. 데이터 준비에는 Analytics 소스 커넥터를 통해 들어오는 데이터를 기반으로 새 필드를 계산하는 데 사용할 수 있는 수백 개의 매핑 기능이 있습니다. 구분된 필드를 별도의 필드로 분할할 수 있습니다. 필드를 결합할 수 있습니다. 문자열을 조작할 수 있습니다. 정규 표현식 등을 기반으로 필드에서 정보를 추출할 수 있습니다.

## 데이터 준비 및 분류 {#classifications}

데이터 준비는 일부 상황에서 [분류](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html)와 크로스오버가 있습니다.

예를 들어 구분된 필드에서 데이터 준비를 사용하여 분류를 사용하지 않고 해당 필드를 여러 개별 필드로 분할할 수 있습니다. 일반적으로 분류는 들어오는 Analytics 이벤트의 스트림 외부에 제공되는 조회 파일을 업로드하여 필드에 메타데이터를 추가하는 방법입니다.

예를 들어 SKU를 “크기”, “브랜드”, “색상” 등으로 그룹화한 분류 파일을 업로드할 수 있습니다. 분류와 데이터 준비의 또 다른 차이점은 분류가 _과거 및 향후_ 데이터에 모두 적용된다는 것입니다. 반면 데이터 준비 매핑은 매핑이 생성된 시점부터 _향후_ 데이터에 적용됩니다.
