---
source-git-commit: 8943af2bc81de5ece238dc7647ff3f66b14b9776
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 4%

---
# Analytics 소스 커넥터에 대한 Adobe Analytics 처리 규칙, VISTA 및 분류와 데이터 준비

[처리 규칙 및 VISTA 규칙](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) Adobe Analytics에 전달되는 데이터를 변환하고 조작하는 수단을 제공합니다 [데이터 수집](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). 이러한 변환은 Adobe Analytics에서 보고 및 분석 목적으로 데이터가 저장되기 전에 Adobe의 데이터 처리의 일부로 발생합니다.


[데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko-KR) 는 수집된 데이터에 행 기반 매핑 및 변형을 적용할 수 있는 도구입니다 [AEP](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en) cja 등을 포함한 AEP 애플리케이션에서 데이터를 사용할 수 있게 되기 전에 데이터 준비는 많은 AEP와 통합됩니다 [소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en) 및 은 이제 와 통합되었습니다 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko): Adobe Analytics에서 AEP로 보고서 세트 데이터를 수집하는 방법을 제공합니다.

Adobe Analytics에 의해 수집되고 저장된 데이터는 처리 규칙 또는 VISTA 규칙 또는 둘 다로 변환할 수 있습니다. 그러나 그런 다음 Analytics 소스 커넥터를 통해 AEP에 전달되는 보고서 세트는 다시 데이터 준비를 사용하여 변환할 수 있습니다. 이는 여러 가지 목적으로 권장될 수 있습니다.

* **CJA와 RTCDP에서 사용할 보고서 세트 간의 스키마 차이점 해결**. 예를 들어 보고서 세트 A가 eVar1을 검색어로 정의하고 보고서 세트 B가 eVar2를 검색어로 정의하는 경우 데이터 준비를 사용하여 두 개의 다른 eVar를 두 eVar의 데이터를 모두 포함하는 공통 필드에 매핑할 수 있습니다. 이를 통해 다음을 수행할 수 있습니다. [보고서 세트를 다른 스키마와 결합](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) 를 CJA 연결에서 사용하거나 RTCDP에서 사용할 수 있도록 합니다.
* **eVar 필드를 의미상 이름에 매핑**. Analytics 소스 커넥터를 통해 들어오는 eVar 및 prop은 다음과 같은 필드에 매핑됩니다 _\_experience.analytics.customDimensions.eVars.eVar1_.  데이터 준비를 사용하여 eVar 및 prop 필드를 사용자에게 더 의미 있는 이름이 있는 새 필드에 매핑하거나 다른 데이터 소스에서 온 이름과 일치하는 필드에 매핑할 수 있습니다. (하지만 CJA 데이터 보기에서 필드 이름 바꾸기와 같은 다른 방법을 통해 이 작업을 수행할 수도 있습니다.)
* **일반적으로 데이터 변환**. 데이터 준비에는 ADC를 통해 들어오는 데이터를 기반으로 새 필드를 계산하고 계산하는 데 사용할 수 있는 수백 개의 매핑 기능이 있습니다. 구분된 필드를 별도의 필드로 분할할 수 있습니다. 필드를 결합할 수 있습니다. 문자열을 조작할 수 있습니다. 정규 표현식 등을 기반으로 필드에서 정보를 추출할 수 있습니다.


데이터 준비에 [분류](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=ko) 어떤 경우에는 예를 들어 구분된 필드가 있는 경우 데이터 준비를 사용하여 분류를 사용하지 않고 해당 필드를 여러 개별 필드로 분할할 수 있습니다. 일반적으로 분류는 들어오는 Analytics 히트의 스트림 외부에 제공된 조회 파일을 업로드하여 필드에 메타데이터를 추가하는 방법입니다. 예를 들어 SKU를 &#39;크기&#39;, &#39;브랜드&#39;, &#39;색상&#39; 등으로 그룹화하는 분류 파일을 업로드할 수 있습니다. 분류와 데이터 준비 의 또 다른 차이점은 분류가 이전 및 계속 데이터에 적용된다는 것입니다. 반면 데이터 준비 매핑은 매핑이 생성되어 데이터를 준비하는 시점부터 적용됩니다.