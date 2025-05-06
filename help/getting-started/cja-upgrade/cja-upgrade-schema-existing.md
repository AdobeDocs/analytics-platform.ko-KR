---
title: Customer Journey Analytics용 스키마 선택
description: Customer Journey Analytics용 스키마를 선택할 때 사용할 수 있는 옵션과 각각의 장단점에 대해 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '475'
ht-degree: 100%

---

# Customer Journey Analytics용 스키마 선택 {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="사용자 정의 스키마 사용"
>abstract="(권장) 스키마를 사용자 정의하면 조직에서 필요한 정보만 추적하고 복잡하고 불필요한 필드에 따른 오버헤드를 피할 수 있습니다. 이 옵션에는 Web SDK가 추가한 필드 그룹과 조직에 맞게 사용자 정의된 필드 그룹이 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="기본 스키마 사용"
>abstract="(권장하지 않음) Adobe Analytics 스키마에는 천 개 이상의 필드가 포함되어 있어 복잡하고 혼란스러울 수 있습니다. 귀하의 조직이 Customer Journey Analytics에서 사용되지 않는 기존 개념인 Prop 및 eVars 개념을 계속 고수해야 합니다. 다른 Adobe Experience Platform 서비스와 통합하는 것은 더 어렵습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

Customer Journey Analytics로 업그레이드할 경우 Adobe는 다른 Platform 서비스를 사용하기 시작할 때 조직의 요구 사항에 더 잘 부합하도록 사용자 정의 경험 데이터 모델(XDM) 스키마를 만드는 것을 권장합니다. 혹은 기존 Adobe Analytics 스키마를 사용할 수도 있습니다.

각각의 장단점을 고려해야 합니다.

## 조직에 맞는 사용자 정의 스키마 만들기(권장)

Adobe는 Customer Journey Analytics로 업그레이드할 때 사용자 정의 스키마를 만드는 것을 권장합니다.

| 장점 | 단점 |
|----------|---------|
| <ul><p>사용자 정의 스키마로 업데이트하는 것의 장점은 다음과 같습니다.</p><ul><li>조직의 요구와 사용하는 특정 Platform 애플리케이션에 맞춘 간소화된 스키마.</li><p>스키마 변경이 필요할 때 업데이트가 필요한 필드를 찾기 위해 수천 개의 사용되지 않은 필드를 선별해야 할 필요가 없습니다.</p></ul> | <p>사용자 정의 스키마로 업데이트하는 것의 단점은 다음과 같습니다.</p><ul><li>스키마를 업데이트하는 것은 Platform으로 데이터를 전송하기 전에 필요한 시간이 많이 소요되는 프로세스입니다.</li></ul> |

## 기존 Adobe Analytics 스키마 사용

기존 Adobe Analytics 스키마를 Customer Journey Analytics와 함께 사용하는 옵션은 Adobe Analytics 구현이 Adobe Experience Platform Web SDK로 구성된 경우에만 사용할 수 있습니다. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| 장점 | 단점 |
|----------|---------|
| <p>Adobe Analytics 스키마 사용의 장점은 다음과 같습니다.</p><ul><li>업그레이드의 용이성<p>이미 Adobe Experience Platform Web SDK를 사용하여 Adobe Analytics로 데이터를 전송하고 있는 경우 데이터스트림에 서비스를 추가하여 Adobe Experience Platform으로 데이터를 전송할 수 있습니다(이 서비스는 Customer Journey Analytics 구성에서 사용할 수 있음).</p></li></ul> | <p>Adobe Analytics 스키마 사용의 단점은 다음과 같습니다.</p><ul><li>Adobe Analytics 스키마를 사용하면 다른 Platform 애플리케이션과 함께 사용할 수 있다는 점에서 제한이 없지만 다른 방식보다 더 복잡한 스키마를 만들 수 있습니다. Adobe Analytics 스키마에는 조직에서 사용할 가능성이 낮은 Adobe Analytics에만 국한된 오브젝트가 많이 포함되어 있기 때문입니다.<p>스키마 변경이 필요할 때 업데이트가 필요한 필드를 찾기 위해 수천 개의 사용되지 않은 필드를 선별해야 합니다.</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the Customer Journey Analytics Upgrade Guide.

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
