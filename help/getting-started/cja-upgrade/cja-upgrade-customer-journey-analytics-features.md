---
title: Customer Journey Analytics의 고유한 기능 이해
description: Customer Journey Analytics의 고유한 기능에 대해 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 74719504960f00f4593633bb62f29d8655cdadd9
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 34%

---

# Customer Journey Analytics의 고유한 기능 이해 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="다양한 출처의 데이터 연결"
>abstract="(권장) 다른 채널의 분석 데이터를 결합하는 기능은 Customer Journey Analytics의 기본 사용 사례입니다."

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
>title="결합된 데이터 세트를 생성하려면 Adobe 고객 지원 센터에 문의하십시오"
>abstract="여러 데이터 세트에 있지만 기본 식별자가 아닌 식별자가 포함된 필드가 있는 경우 해당 필드를 사용하여 일관된 식별자로 새 데이터 세트를 생성할 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Real-time CDP와 통합"
>abstract="여러 소스의 프로필 데이터를 결합하여 사용자 트레이트를 기반으로 대상 및 세그먼트를 생성합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Adobe Target과 임시 통합"
>abstract="Adobe에서는 개인화 사용 사례를 위해 Adobe Journey Optimizer과 통합하는 것이 좋습니다. Adobe Target과 통합할 수는 있지만 임시 해결 방법이 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Journey Optimizer과 통합"
>abstract="고객에게 연관성 있고 상황에 맞는 개인화된 경험을 제공합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Adobe Audience Manager와 일시적으로 통합"
>abstract="Adobe에서는 대상 기반 사용 사례를 위해 Adobe Real-time CDP와 통합하는 것이 좋습니다. Audience Manager과 통합할 수는 있지만 임시 해결 방법이 있습니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analytics 업그레이드 확인 목록](https://gigazelle.github.io/cja-ttv/)의 질문에 답변할 때 이 페이지의 정보를 사용하십시오.

다음 목록은 업그레이드 프로세스 중에 고려해야 하는 Customer Journey Analytics 기능만 보여 줍니다. Customer Journey Analytics에서 완전히 지원되거나, 부분적으로 지원되거나, 지원되지 않는 Adobe Analytics 기능을 보여 주는 포괄적인 목록을 보려면 [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)을 참조하십시오.

Customer Journey Analytics으로 업그레이드할 때 다음 Customer Journey Analytics 기능 중 채택할 기능을 고려하십시오.

| Customer Journey Analytics 기능 | 함수 |
|---------|----------|
| [웹 데이터를 콜 센터 데이터와 같은 다른 채널의 데이터와 연결](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics는 모든 종류의 데이터 스키마와 유형을 보유할 수 있는 Experience Platform의 기능과 결합되어 있습니다. [경험 데이터 모델(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)을 사용하여 데이터를 조합하고 탐색할 수 있도록 균일하게 나타내고 구성할 수 있습니다. Adobe Analytics는 일부 [데이터 가져오기](https://experienceleague.adobe.com/docs/analytics/import/home.html) 기능을 사용하여 주로 웹 및 모바일 분석 데이터에 중점을 둡니다. |
| [사용자 지정 차원을 사용하여 다른 데이터 세트의 히트를 연결합니다](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics를 사용하면 여러 보고서 세트의 데이터를 마치 Adobe Analytics의 단일 보고서 세트인 것처럼 [결합](/help/connections/combined-dataset.md)할 수 있습니다. |
| [Adobe Real-time CDP와 통합](/help/components/audiences/audiences-overview.md) | 고객 타기팅 및 맞춤화를 위해 Customer Journey Analytics에서 검색된 대상을 [만들어 Adobe Experience Platform의 실시간 고객 프로필에 게시](/help/components/audiences/audiences-overview.md)할 수 있습니다. |
| [Adobe Target(A4T)와 임시 통합](/help/integrations/at.md) | Customer Journey Analytics의 Target 보고를 사용하면 Customer Journey Analytics에서 직접 [Adobe Target 활동을 측정하고 보고](/help/integrations/at.md)할 수 있습니다. |
| [Adobe Journey Optimizer과 통합](/help/integrations/ajo.md) | Journey Optimizer에서 생성된 데이터를 구성하여 [Customer Journey Analytics에서 고급 분석을 수행](/help/integrations/ajo.md)할 수 있습니다. |
| Adobe Audience Manager와 일시적으로 통합 |  |


