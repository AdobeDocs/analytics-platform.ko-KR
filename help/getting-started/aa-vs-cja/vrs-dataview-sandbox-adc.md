---
title: 가상 보고서 세트, 데이터 보기, Adobe Experience Platform 샌드박스 및 Analytics 소스 커넥터
description: 가상 보고 환경 및 샌드박스 환경에 대해 알아보십시오.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: Basics
source-git-commit: cb81422ed08420fe9a16c32ddd748c9569197b17
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 100%

---

# 가상 보고서 세트, 데이터 보기, Adobe Experience Platform 샌드박스 및 Analytics 소스 커넥터

Adobe는 가상 보고 환경과 샌드박스 환경을 만드는 다양한 수단을 제공합니다. 다음 기능 간의 유사점과 차이점 및 이러한 기능이 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko)와 어떻게 관련되어 있는지 이해하는 것이 유용합니다.

* Adobe Analytics 가상 보고서 세트
* Customer Journey Analytics 데이터 보기
* Adobe Experience Platform 샌드박스

## Adobe Analytics 가상 보고서 세트

자세한 내용은 [가상 보고서 세트 개요](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=ko)를 참조하십시오.

가상 보고서 세트:

* Adobe Analytics 세그먼트를 기반으로 할 수 있습니다.
* 과거 데이터와 새 데이터 모두에 비파괴적인 방식으로 적용할 수 있습니다.
* 여러 비즈니스 팀에서 사용할 수 있도록 Adobe Analytics 보고서 세트 위에 가상 보기를 하나 이상 만들 수 있습니다.
* Adobe Analytics에서 다양한 사용자에 대해 다양한 종류의 데이터 액세스를 제어하고 큐레이션하는 데 사용할 수 있습니다.
* Adobe Analytics에 대해 선택적 [보고서 시간 처리](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ko) 기능을 제공합니다. 이 경우 가상 보고서 세트를 사용하여 “방문”에 대한 맞춤형 정의 생성에 사용할 수 있습니다.
* 세그먼트 평가와 유사하게 보고서 런타임에 적용됩니다. 이는 Adobe Analytics 내에서 데이터를 수집하고 저장한 _후_&#x200B;입니다.
* Adobe Analytics에서 [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ko)에 필요합니다.
* 표준 Analytics 보고서 세트(250개 eVar, 250개 Prop, 1,000개 이벤트)와 동일한 수의 변수를 사용할 수 있지만, 가상 보고서 세트 큐레이션은 사용자에게 노출되는 변수를 제한할 수 있습니다.
* 사용자 정의 캘린더 옵션을 지원합니다.

가상 보고서 세트는 다음과 같지 않습니다.

* 보고서 세트를 결합하는 수단입니다.
* Adobe Analytics Data Warehouse에서 사용할 수 있습니다.
* Analytics 소스 커넥터를 통해 Adobe Experience Platform으로의 데이터 흐름을 위한 소스로 사용할 수 있습니다. Analytics 소스 커넥터에서는 전체(가상이 아닌) 보고서 세트만 사용할 수 있습니다.


## Customer Journey Analytics 데이터 보기

자세한 내용은 [데이터 보기 개요](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ko)를 참조하십시오.

데이터 보기:

* Customer Journey Analytics 필터를 기반으로 할 수 있습니다.
* 과거 데이터와 새 데이터 모두에 비파괴적인 방식으로 적용할 수 있습니다.
* 여러 비즈니스 팀에서 사용할 수 있도록 Customer Journey Analytics 연결 위에 가상 보기를 하나 이상 만들 수 있습니다.
* Customer Journey Analytics에서 다양한 사용자에 대해 다양한 종류의 데이터 액세스를 제어하고 큐레이션하는 데 사용할 수 있습니다.
* Customer Journey Analytics 연결을 통해 Customer Journey Analytics로 들어오는 데이터를 변환하고 개선하기 위한 강력한 비파괴적인 옵션을 제공합니다.
* Customer Journey Analytics의 보고 시 처리 기능을 기반으로 합니다.
* 사용자가 “세션”에 대한 맞춤형 정의를 생성하는 것을 허용합니다.
* 필터 평가와 유사하게 보고서 런타임에 적용됩니다. 이는 소스 커넥터(Adobe Analytics 또는 기타)가 Adobe Experience Platform 데이터 레이크의 데이터 세트에 데이터를 기록한 _후_&#x200B;와 Customer Journey Analytics 연결을 통해 데이터가 Customer Journey Analytics에 수집된 _후_&#x200B;입니다.
* 큐레이션은 사용자에게 노출되는 변수를 제한할 수 있지만 변수 개수는 무제한 허용합니다.
* 이벤트, 세션 및 개인 컨테이너의 이름을 사용자 정의할 수 있습니다.
* 사용자 정의 캘린더 옵션을 지원합니다.

데이터 보기는 다음과 같지 않습니다.

* 보고서 세트 또는 기타 데이터 세트를 결합하기 위한 직접적인 수단을 제공합니다. 대신 데이터 세트는 Customer Journey Analytics 연결 내에서 결합됩니다. Customer Journey Analytics 연결의 결합된 데이터는 해당 연결을 기반으로 하는 모든 데이터 보기에서 사용할 수 있습니다.

## Adobe Experience Platform 샌드박스

자세한 내용은 [샌드박스 개요](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ko)를 참조하십시오.

Adobe Experience Platform 샌드박스:

* 단일 Adobe Experience Platform 인스턴스를 별도의 가상 환경(개발, 테스트, 단계, 프로덕션 등)으로 분할하는 수단을 제공합니다. 디지털 경험 애플리케이션을 개발하고 발전시키는 데 도움을 줍니다.
* 주어진 환경에 대한 모든 데이터와 애플리케이션을 저장하는 컨테이너로 생각할 수 있습니다.

Adobe Experience Platform 샌드박스는 다음과 같지 않습니다.

* 가상 보고서 세트, Customer Journey Analytics 연결 또는 데이터 보기와 유사한 기능을 제공합니다.
* 다른 데이터 세트를 포함하거나 포함하지 않고 보고서 세트를 단독으로 결합합니다. 그러나 샌드박스 내의 데이터 세트는 Customer Journey Analytics 연결 내에서 결합할 수 있습니다.

참고:

* 서로 다른 샌드박스의 데이터는 Customer Journey Analytics 내에서 결합할 수 없습니다.
* Analytics 소스 커넥터는 보고서 세트 데이터를 특정 샌드박스로 _보냅니다_. 각 보고서 세트는 단일 샌드박스에 대한 소스로 구성할 수 있습니다. 자세한 내용은 [Analytics 소스 커넥터 설명서](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko)를 참조하십시오.
