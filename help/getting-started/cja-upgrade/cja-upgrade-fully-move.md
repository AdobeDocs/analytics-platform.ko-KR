---
title: Customer Journey Analytics로 업그레이드한 후 Adobe Analytics가 필요한 기간 평가
description: Customer Journey Analytics로 업그레이드한 후 Adobe Analytics가 필요한 기간 평가 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 100%

---

# Customer Journey Analytics로 업그레이드한 후 Adobe Analytics 비활성화 시기 {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Customer Journey Analytics로 완전 전환"
>abstract="(권장) Adobe Analytics에서 Customer Journey Analytics로 완전히 전환하는 것이 좋습니다. 전환 기간 동안 Customer Journey Analytics와 함께 Adobe Analytics를 실행하여 데이터를 나란히 비교하는 계획을 세워야 합니다. 데이터에 익숙해지면 Adobe Analytics를 비활성화할 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="두 가지 분석 제품 모두 유지"
>abstract="(권장하지 않음) 이 옵션을 선택하면 Adobe와의 계약에 Adobe Analytics와 Customer Journey Analytics가 모두 포함되므로 시간이 지남에 따라 조직에 더 많은 비용이 들 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="Analytics 소스 커넥터를 비활성화하여 Web SDK에서만 데이터 사용"
>abstract="Analytics 소스 커넥터는 나란히 배치된 데이터 비교, 과거 데이터 제공 및 Customer Journey Analytics에서 완전히 사용할 수 없는 일부 기능에 대한 액세스를 제공하는 데 사용됩니다. 더 이상 이러한 용도로 Adobe Analytics가 필요하지 않으면 Analytics 소스 커넥터를 비활성화할 수 있습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

대부분의 조직은 Customer Journey Analytics로 업그레이드한 후 결국 Adobe Analytics를 비활성화합니다. 이는 두 가지 분석 환경을 유지 관리하는 데 드는 비용과 복잡성 때문입니다.

하지만 Adobe에서는 Customer Journey Analytics를 구현한 후에도 일정 기간 동안 Adobe Analytics 환경을 실행 상태로 유지하는 것을 권장합니다. 다음 섹션에서는 Adobe Analytics를 비활성화하는 이유와 권장되는 비활성화 시기를 설명합니다.

## 업그레이드 도중 및 이후의 Adobe Analytics 사용

조직에서 Adobe Analytics를 비활성화할지 여부와 시기를 결정할 때 Customer Journey Analytics로 업그레이드 도중과 업그레이드 후에 Adobe Analytics를 다음과 같이 사용하는 것을 고려해 보십시오.

| 업그레이드 도중 및 이후의 Adobe Analytics 사용 | 설명 |
|---------|----------|
| 나란히 데이터 비교 수행 | Adobe에서는 새로운 Customer Journey Analytics 환경을 실행하고 데이터를 수집한 후에도 일정 기간 동안 Adobe Analytics 환경을 계속 실행하는 것을 권장합니다. 이는 Customer Journey Analytics 데이터와 Adobe Analytics 데이터를 나란히 비교하는 가장 좋은 방법입니다.<p>Customer Journey Analytics 환경의 데이터에 익숙해질 때까지 Adobe Analytics를 비활성화하지 마십시오.</p><p>**참고:** Adobe는 내역 데이터에 대한 Analytics 소스 커넥터와 함께 Customer Journey Analytics 환경을 위한 Web SDK의 새로운 구현을 권장합니다. [자세히 알아보기](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Adobe Analytics의 내역 데이터 유지 | Adobe는 새로운 Customer Journey Analytics 환경이 실행되고 데이터를 수집한 후에도 일정 기간 동안 Analytics 소스 커넥터와 함께 Adobe Analytics 환경을 유지하는 것을 권장합니다. 이는 기존 Adobe Analytics 데이터를 Customer Journey Analytics로 가져오는 가장 좋은 방법입니다.<p>새로운 Web SDK 구현을 통해 Customer Journey Analytics에서 충분한 내역 데이터를 수집한 후에는 Analytics 소스 커넥터를 완전히 제거할 수 있습니다. 새로운 Customer Journey Analytics Web SDK 구현을 통해 수집한 내역 데이터에만 의존할 수 있는 경우 이를 수행해야 합니다.</p><p>**참고:** Adobe는 내역 데이터에 대한 Analytics 소스 커넥터와 함께 Customer Journey Analytics 환경을 위한 Web SDK의 새로운 구현을 권장합니다. [자세히 알아보기](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 데이터 피드 또는 기타 Adobe Analytics 기능 사용 | Customer Journey Analytics에서는 아직 일부 기능을 완전히 사용할 수 없습니다. 이러한 기능에 액세스해야 하는 경우, 이러한 기능을 사용할 수 있을 때까지 Adobe Analytics를 Customer Journey Analytics와 함께 사용해야 할 수도 있습니다. <p>Customer Journey Analytics에서 완전히 사용할 수 없는 기능에는 데이터 피드 및 속성 분석이 포함됩니다. 아직 사용할 수 없는 기능의 전체 목록을 보려면 [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)을 참조하십시오.</p> |

## Adobe Analytics 비활성화 프로세스 및 타임라인 {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="서드파티 태그 관리 시스템 비활성화"
>abstract="Web SDK 데이터가 완벽하게 작동하면 태그 관리자와 협력하여 서드파티 태그 관리 시스템에서 AppMeasurement 라이브러리를 제거합니다.<br><br>이 단계를 수행하는 데 예상되는 시간은 태그 관리 제품에서 AppMeasurement를 비활성화하는 용이성과 태그 코드를 배포하고 관리하는 데 사용하는 릴리스 주기에 따라 달라집니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="태그에서 Analytics 확장 기능 비활성화"
>abstract="Web SDK 데이터가 완전히 작동하면 태그 관리자와 협력하여 태그 속성에서 Adobe Analytics 확장 기능을 제거합니다. 이 작업을 수행하기 전에 사용자가 Adobe Analytics에서 Customer Journey Analytics로 전환했는지 확인하십시오."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="Adobe Analytics에 대한 API 데이터 수집 비활성화"
>abstract="Web SDK 데이터가 완전히 작동하면 해당 엔지니어링 팀과 협력하여 프로젝트에서 Adobe Analytics 코드를 제거합니다. 이 작업을 수행하기 전에 사용자가 Adobe Analytics에서 Customer Journey Analytics로 전환했는지 확인하십시오."

<!-- markdownlint-enable MD034 -->

기존 Adobe Analytics 구현은 위 섹션인 [업그레이드 도중 및 이후의 Adobe Analytics 사용](#uses-of-adobe-analytics-during-and-after-an-upgrade)에서 설명한 대로 Customer Journey Analytics로의 성공적인 업그레이드에 중요한 부분입니다.

위 섹션에 설명된 목적에 더 이상 Adobe Analytics가 필요하지 않은 경우 다음 정보를 사용하여 Adobe Analytics를 제거합니다.

1. Adobe Analytics로 데이터 수집을 중지합니다.

   Adobe Analytics 데이터와 Customer Journey Analytics 데이터를 나란히 비교하여 만족스러운 결과를 얻은 후에는 Adobe Analytics 구현에서 데이터 수집을 중지할 수 있습니다. 새로운 Adobe Analytics 데이터는 Analytics 소스 커넥터를 통해 더 이상 Customer Journey Analytics로 전송되지 않습니다.

   그러나 이 시점 이전에 Adobe Analytics 환경에서 수집한 데이터는 Analytics 소스 커넥터를 통해 Customer Journey Analytics에서 내역 데이터로 여전히 사용할 수 있습니다.

   이 프로세스는 Adobe Analytics를 구현하는 데 사용한 데이터 수집 방법에 따라 다릅니다.

   +++ AppMeasurement

   [AppMeasurement 데이터 수집 비활성화](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

   +++

   +++ Analytics 확장 기능(태그)

   태그에서 Analytics 확장 기능 비활성화.

   +++

   +++ API

   API 데이터 수집 비활성화.

   +++

   +++ 서드파티

   태그 관리자와 협력하여 서드파티 태그 관리 시스템에서 AppMeasurement 라이브러리를 제거합니다.

   +++

1. 데이터스트림에서 Adobe Analytics as a Service 제거.

   Web SDK 데이터가 완벽하게 작동하면 플랫폼 관리자와 협력하여 데이터스트림에서 Adobe Analytics as a Service를 제거하십시오.

   Adobe Analytics를 서비스로 제거하기 전에 Analytics 사용자가 Adobe Analytics가 아닌 Customer Journey Analytics를 사용하고 있는지 확인합니다.

1. Analytics 소스 커넥터 완전히 제거.

   새로운 Web SDK 구현을 통해 Customer Journey Analytics에서 충분한 내역 데이터를 수집한 후에는 Analytics 소스 커넥터를 완전히 제거할 수 있습니다.

   Adobe Analytics 환경의 내역 데이터가 Analytics 소스 커넥터를 통해 더 이상 필요하지 않고, 새로운 Web SDK 구현을 통해 수집한 내역 데이터에만 의존할 수 있는 경우에 이 작업을 수행하십시오.

{{upgrade-final-step}}

