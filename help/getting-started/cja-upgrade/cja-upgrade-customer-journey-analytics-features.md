---
title: Customer Journey Analytics의 고유한 기능 이해
description: Customer Journey Analytics의 고유한 기능 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 100%

---

# Customer Journey Analytics의 고유한 기능 이해 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="다양한 출처의 데이터 연결"
>abstract="(권장) 다양한 웹, 모바일, 오프라인 속성의 데이터를 연결하여 고객 행동에 대한 단일 통합 보기를 생성합니다. 다른 채널의 분석 데이터를 결합하는 이 기능은 Customer Journey Analytics의 기본 사용 사례입니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="여러 데이터 세트에서 히트 결합"
>abstract="데이터 세트 중 하나라도 기본 식별자(예: Experience Cloud ID)를 공유하지 않는 경우에도 로그인 사용자 이름이나 이메일 주소와 같은 다른 차원을 사용하여 해당 데이터를 연결할 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="Adobe 고객 지원 센터에 문의하여 결합된 데이터 세트 생성"
>abstract="여러 데이터 세트에 존재하지만 기본 식별자가 아닌 식별자를 포함하는 필드가 있는 경우, 이를 활용하여 일관된 식별자를 가진 새 데이터 세트를 생성할 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Real-Time CDP와 통합"
>abstract="다양한 소스의 프로필 데이터를 결합하여 사용자 특성을 기반으로 대상자와 세그먼트를 생성합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Adobe Target과 일시적으로 통합"
>abstract="개인화 사용 사례에 대해서는 Adobe Journey Optimizer와 통합하는 것이 좋습니다. Adobe Target과 통합하는 것은 가능하지만 단기적인 솔루션일 뿐입니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Journey Optimizer와 통합"
>abstract="고객에게 연관성 있고 상황에 맞는 개인화된 경험을 제공합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Adobe Audience Manager와 일시적으로 통합"
>abstract="대상자 기반 사용 사례에 대해서는 Adobe Real-Time CDP와 통합하는 것이 좋습니다. Audience Manager와 통합하는 것은 가능하지만 단기적인 솔루션일 뿐입니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

다음 목록은 업그레이드 프로세스 중에 고려해야 할 Customer Journey Analytics 기능만 보여 줍니다. Customer Journey Analytics에서 전체적으로 지원되는 Adobe Analytics 기능, 부분적으로 지원되는 기능 또는 지원되지 않는 기능을 보여 주는 포괄적인 목록을 확인하려면 [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)을 참조하십시오.

Customer Journey Analytics로 업그레이드할 때 다음 중 어떤 Customer Journey Analytics 기능을 도입할지 고려합니다.

| Customer Journey Analytics 기능 | 함수 |
|---------|----------|
| [콜센터 데이터 등 다른 채널의 데이터와 웹 데이터 연결](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics는 모든 종류의 데이터 스키마와 유형을 보유할 수 있는 Experience Platform의 기능과 결합되어 있습니다. [경험 데이터 모델(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko)을 사용하여 데이터를 조합하고 탐색할 수 있도록 균일하게 나타내고 구성할 수 있습니다. Adobe Analytics는 일부 [데이터 가져오기](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=ko) 기능을 사용하여 주로 웹 및 모바일 분석 데이터에 중점을 둡니다. |
| [사용자 정의 차원을 사용하여 다른 데이터 세트에서 히트 결합](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics를 사용하면 여러 보고서 세트의 데이터를 마치 Adobe Analytics의 단일 보고서 세트인 것처럼 [결합](/help/connections/combined-dataset.md)할 수 있습니다. |
| [Adobe 실시간 CDP와 통합](/help/components/audiences/audiences-overview.md) | 고객 타기팅 및 맞춤화를 위해 Customer Journey Analytics에서 발견된 [대상자를 Adobe Experience Platform의 실시간 고객 프로필을 만들어 게시](/help/components/audiences/audiences-overview.md)할 수 있습니다. |
| [Adobe Target(A4T)과 통합](/help/integrations/at.md) | Customer Journey Analytics의 타깃 보고를 사용하면 Customer Journey Analytics에서 직접 [Adobe Target 활동을 측정하고 보고](/help/integrations/at.md)할 수 있습니다. 그러나 개인화 사용 사례에 대해서는 Adobe Journey Optimizer와 통합하는 것이 좋습니다. |
| [Adobe Journey Optimizer와 통합](/help/integrations/ajo.md) | Journey Optimizer에서 생성된 데이터를 구성해 [Customer Journey Analytics에서 고급 분석을 수행](/help/integrations/ajo.md)할 수 있습니다. |
| [Adobe Audience Manager와 통합](https://experienceleague.adobe.com/ko/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | [Audience Manager 특성과 세그먼트를 Adobe Experience Platform에 공유](https://experienceleague.adobe.com/ko/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing)할 수 있습니다. 그러나 대상자 기반 사용 사례에 대해서는 Adobe Real-Time CDP와 통합하는 것이 좋습니다. |
