---
title: Customer Journey Analytics으로 업그레이드한 후 Adobe Analytics이 필요한 시간을 평가합니다.
description: Customer Journey Analytics으로 업그레이드한 후 Adobe Analytics이 필요한 시간을 평가하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: f4440148d26e81938d029d4a077cd787c868f1be
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---

# Customer Journey Analytics으로 업그레이드한 후 Adobe Analytics이 필요한 시간을 평가합니다. {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Customer Journey Analytics으로 완전히 이동"
>abstract="(권장) Customer Journey Analytics은 조직의 기본 Analytics 도구로 사용하는 것을 목표로 합니다. 하지만 조직에 도구 전용 기능이 많이 사용되고 이러한 워크플로를 변경할 수 없는 경우에도 Adobe Analytics이 필요할 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="두 분석 제품 모두 유지"
>abstract="(권장되지 않음) 이 옵션을 선택하면 Adobe과의 계약에 Adobe Analytics과 Customer Journey Analytics이 모두 포함되어 있으므로 시간이 지남에 따라 조직에 더 많은 비용이 소요될 수 있습니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Adobe Analytics 이 설명서는 [업그레이드 Customer Journey Analytics 설문지](https://gigazelle.github.io/cja-ttv/)의 일부로 사용해야 합니다.

대부분의 조직은 Customer Journey Analytics으로 업그레이드한 후 Adobe Analytics을 비활성화합니다. 이는 두 개의 분석 환경을 유지 관리하는 데 드는 비용과 복잡성 때문입니다.

그러나 Adobe은 Customer Journey Analytics을 구현한 후 일정 기간 동안 Adobe Analytics 환경을 계속 실행하는 것을 권장합니다. 다음 섹션에서는 이러한 작업을 수행하는 이유와 Adobe Analytics을 비활성화하는 제안된 시기에 대해 설명합니다.

## 업그레이드 중 및 업그레이드 후 Adobe Analytics 사용

조직에서 Adobe Analytics을 비활성화해야 하는지 여부와 시기를 결정할 때 Customer Journey Analytics으로 업그레이드하는 동안 및 후에 Adobe Analytics을 다음과 같이 사용하는 것을 고려하십시오.

| 업그레이드 중 및 업그레이드 후 Adobe Analytics 사용 | 설명 |
|---------|----------|
| 병렬 데이터 비교 수행 | Adobe은 새 Customer Journey Analytics 환경이 실행되고 데이터가 수집된 후 일정 기간 동안 Adobe Analytics 환경을 계속 실행할 것을 권장합니다. 이는 Customer Journey Analytics 데이터를 Adobe Analytics 데이터와 나란히 비교하는 가장 좋은 방법입니다.<p>Customer Journey Analytics 환경의 데이터에 익숙해질 때까지 Adobe Analytics을 비활성화하지 마십시오.</p><p>**참고:** Adobe은 이전 데이터에 대한 Analytics 소스 커넥터와 함께 Customer Journey Analytics 환경에 대한 Web SDK의 새로운 구현을 권장합니다. [자세히 알아보기](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Adobe Analytics의 내역 데이터 유지 | Adobe은 새 Customer Journey Analytics 환경이 실행되고 데이터가 수집된 후 일정 기간 동안 Adobe Analytics 환경을 Analytics 소스 커넥터와 함께 유지하는 것을 권장합니다. 이는 내역 Adobe Analytics 데이터를 Customer Journey Analytics으로 가져오는 가장 좋은 방법입니다.<p>새 웹 SDK 구현과 Customer Journey Analytics 시 내역 데이터를 충분히 수집한 후에는 Analytics 소스 커넥터를 완전히 제거할 수 있습니다. 새로운 Customer Journey Analytics 웹 SDK 구현으로 수집한 내역 데이터에만 의존할 수 있을 때 이렇게 하십시오.</p><p>**참고:** Adobe은 이전 데이터에 대한 Analytics 소스 커넥터와 함께 Customer Journey Analytics 환경에 대한 Web SDK의 새로운 구현을 권장합니다. [자세히 알아보기](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 데이터 피드 또는 기타 Adobe Analytics 기능 사용 | Customer Journey Analytics에서 아직 일부 기능을 완전히 사용할 수 없습니다. 이러한 기능에 액세스해야 하는 경우 이러한 기능을 사용할 수 있을 때까지 Adobe Analytics을 Customer Journey Analytics과 함께 사용해야 할 수 있습니다. <p>Customer Journey Analytics에서 완전히 사용할 수 없는 기능에는 데이터 피드 및 기여도 분석이 포함됩니다. 아직 사용할 수 없는 기능의 전체 목록을 보려면 [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)을 참조하세요.</p> |

## Adobe Analytics 비활성화 프로세스 및 타임라인 {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="서드파티 태그 관리 시스템 비활성화"
>abstract="웹 SDK 데이터가 완전히 작동하면 태그 관리자와 협력하여 서드파티 태그 관리 시스템에서 AppMeasurement 라이브러리를 제거합니다.<br><br>이 단계를 수행하는 예상 시간은 태그 관리 제품에서 AppMeasurement을 쉽게 사용하지 않도록 설정할 수 있을 뿐만 아니라 조직에서 태그 코드를 배포하고 관리하는 데 사용하는 릴리스 주기에 따라 다릅니다."

<!-- markdownlint-enable MD034 -->

위의 섹션, [업그레이드 중 및 업그레이드 후 Adobe Analytics 사용](#uses-of-adobe-analytics-during-and-after-an-upgrade)에 설명된 대로 기존 Adobe Analytics 구현은 성공적인 Customer Journey Analytics 업그레이드의 핵심 부분입니다.

위의 섹션에 설명된 용도로 Adobe Analytics이 더 이상 필요하지 않은 경우 다음 정보를 사용하여 Adobe Analytics을 제거하십시오.

1. Adobe Analytics을 사용한 데이터 수집을 중단합니다.

   Adobe Analytics 데이터와 Customer Journey Analytics 데이터의 병렬 비교에 만족하면 Adobe Analytics 구현으로 데이터 수집을 중단할 수 있습니다. 새 Adobe Analytics 데이터는 더 이상 Analytics 소스 커넥터를 통해 Customer Journey Analytics으로 흐르지 않습니다.

   그러나 이 시점 이전에 Adobe Analytics 환경에서 수집한 데이터는 여전히 Analytics 소스 커넥터를 통해 Customer Journey Analytics 시 내역 데이터로 사용할 수 있습니다.

   이 프로세스는 Adobe Analytics을 구현하는 데 사용한 데이터 수집 방법에 따라 다릅니다.

+++ AppMeasurement

   [AppMeasurement 데이터 수집을 사용하지 않도록 설정](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

+++

+++ Analytics 확장(태그)

   태그에서 Analytics 확장을 비활성화합니다.

+++

+++ API

   API 데이터 수집을 비활성화합니다.

+++

+++ 서드파티

   태그 관리자와 협력하여 타사 태그 관리 시스템에서 AppMeasurement 라이브러리를 제거합니다.

+++

1. 데이터 스트림에서 서비스로서의 Adobe Analytics을 제거합니다.

   웹 SDK 데이터가 완전히 작동하면 플랫폼 관리자와 함께 데이터 스트림에서 Adobe Analytics as a service를 제거합니다.

   Adobe Analytics as a service를 제거하기 전에 Analytics 사용자가 Adobe Analytics이 아닌 Customer Journey Analytics을 사용하고 있는지 확인하십시오.

1. Analytics 소스 커넥터를 완전히 제거합니다.

   새 웹 SDK 구현과 Customer Journey Analytics 시 내역 데이터를 충분히 수집한 후에는 Analytics 소스 커넥터를 완전히 제거할 수 있습니다.

   Analytics 소스 커넥터를 통해 Adobe Analytics 환경의 내역 데이터가 더 이상 필요하지 않고 새로운 웹 SDK 구현으로 수집한 내역 데이터만 사용할 수 있는 경우 이렇게 하십시오.

