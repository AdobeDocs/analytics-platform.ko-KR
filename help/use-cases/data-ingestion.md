---
title: Customer Journey Analytics의 데이터 수집 옵션
description: 데이터를 Customer Journey Analytics로 수집할 수 있는 다양한 방법 이해
translation-type: tm+mt
source-git-commit: 4ea06ca1f13255c570ccc9f69cb328d57bf975b2
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 97%

---


# Customer Journey Analytics의 데이터 수집 옵션

데이터를 Customer Journey Analytics로 수집하는 방법은 여러 가지가 있습니다. 일부 고객은 기존 Adobe Analytics 데이터를 이전하려는 것으로 간주하며 일부는 Adobe Experience Platform에서 직접 데이터를 수집한다고 가정합니다. 이 참조는 보다 자세한 정보에 대한 링크를 포함하여 따라야 할 고급 단계를 제공합니다.

## 기존 Adobe Analytics에서 데이터 수집

이 워크플로우는 Adobe Analytics 데이터 커넥터를 사용하며, 태그 관리자로 DTM을 사용하는지 또는 Launch를 사용하는지에 따라 달라집니다.

### Dynamic Tag Management(DTM)를 통해

1. 아직 수행하지 않았다면 [데이터 레이어를 만듭니다](https://docs.adobe.com/content/help/ko-KR/analytics/implementation/prepare/data-layer.html). 데이터 계층은 구현에 사용된 모든 변수 값을 포함하는 사이트의 JavaScript 개체의 프레임워크로서, 구현을 보다 세밀하게 제어하고 쉽게 유지 관리할 수 있습니다.
1. 아직 수행하지 않았다면 데이터 수집을 위해 사이트에서 코드를 구현하도록 [DTM](https://docs.adobe.com/content/help/ko-KR/analytics/implementation/other/dtm/dtm-implementation-overview.html)을 사용합니다. Dynamic Tag Management는 여러 소스의 데이터를 푸시하는 단일 데이터 계층을 제공합니다.
1. Adobe Experience Platform에서 [Adobe Analytics 소스 커넥터](https://docs.adobe.com/content/help/ko-KR/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)를 만듭니다. 이 소스 커넥터는 Analytics 데이터를 [XDM(Experience Data Model) 시스템](https://docs.adobe.com/content/help/ko-KR/experience-platform/xdm/home.html)이라는 표준화된 프레임워크에서 Experience Platform에 수집합니다.
1. 채널 간 보고를 알리는 하나 이상의 연결 및 데이터 보기를 만들려면[Customer Journey Analytics](https://docs.adobe.com/content/help/ko-KR/analytics-platform/using/cja-overview/cja-getting-started.html)를 사용합니다.

### Launch를 통해

1. 아직 수행하지 않았다면 [데이터 레이어를 만듭니다](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html). 데이터 계층은 구현에 사용된 모든 변수 값을 포함하는 사이트의 JavaScript 개체의 프레임워크로서, 구현을 보다 세밀하게 제어하고 쉽게 유지 관리할 수 있습니다.
1. 아직 수행하지 않았다면 데이터 수집을 위해 사이트에서 코드를 구현하도록 [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/ko-KR/analytics/implementation/launch/overview.html)를 사용합니다. Launch는 다른 태그 지정 요구 사항과 함께 Analytics 코드를 배포할 수 있도록 해주는 태그 관리 솔루션입니다. Launch는 다른 솔루션 및 제품과의 통합을 제공하며 사용자 지정 코드를 배포할 수 있도록 해줍니다. 따라서 사이트에서 코드를 업데이트하기 위해 조직의 개발 팀에 의존하지 않고도 이러한 모든 작업을 수행할 수 있습니다..
1. Adobe Experience Platform에서 [Adobe Analytics 소스 커넥터](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)를 만듭니다. 이 소스 커넥터는 Analytics 데이터를 [XDM(Experience Data Model) 시스템](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html)이라는 표준화된 프레임워크에서 Experience Platform에 수집합니다.
1. 채널 간 보고를 알리는 하나 이상의 연결 및 데이터 보기를 만들려면[Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html)를 사용합니다.
