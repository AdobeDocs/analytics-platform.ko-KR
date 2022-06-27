---
title: 가상 보고서 세트, 데이터 보기, AEP 샌드박스 및 Analytics 소스 커넥터
description: 가상 보고 환경 및 샌드박스 환경에 대해 알아봅니다.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 9%

---

# 가상 보고서 세트, 데이터 보기, AEP 샌드박스 및 Analytics 소스 커넥터

Adobe은 가상 보고 환경과 샌드박스 환경을 만드는 다양한 방법을 제공합니다. 다음 기능과 이러한 기능이 와 어떻게 관련되는지를 이해하는 데 유용합니다 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko):

* Adobe Analytics 가상 보고서 세트
* CJA 데이터 보기
* AEP 샌드박스

## Adobe Analytics VRS(가상 보고서 세트)

자세한 내용은 다음을 참조하십시오. [가상 보고서 세트 개요](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=ko-KR).

VRS:

* Adobe Analytics 세그먼트를 기반으로 할 수 있습니다.
* 이전 데이터와 새 데이터 모두에 비파괴적인 방식으로 적용할 수 있습니다.
* 다른 비즈니스 팀에서 사용할 Adobe Analytics 보고서 세트 맨 위에 하나 이상의 가상 보기를 만들 수 있습니다.
* Adobe Analytics에서 다양한 사용자에 대한 다양한 종류의 데이터에 대한 액세스를 제어하고 조정하는 데 사용할 수 있습니다.
* 옵션 제공 [보고서 처리 시간](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=ko-KR) Adobe Analytics의 기능. 이 경우 VRS를 사용하여 &quot;방문&quot;에 대한 사용자 지정 정의를 만들 수 있습니다.
* 는 세그먼트 평가와 유사하게 보고서 런타임에 적용됩니다. 이것은 _after_ 데이터가 Adobe Analytics 내에서 수집 및 저장되었습니다.
* 에 필요합니다. [교차 디바이스 분석](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=ko-KR) Adobe Analytics.
* VRS 큐레이션은 사용자에게 노출된 변수를 제한할 수 있지만, 표준 Analytics 보고서 세트(250개의 eVar, 250개의 prop, 1000개의 이벤트)로 사용할 동일한 수의 변수를 사용할 수 있습니다.
* 사용자 지정 달력 옵션을 지원합니다.

가상 보고서 세트는 다음 항목이 아닙니다.

* 보고서 세트를 결합하는 방법입니다.
* Adobe Analytics Data Warehouse에서 사용할 수 있습니다.
* Analytics 소스 커넥터를 통해 AEP로 데이터 흐름의 소스로 사용할 수 있습니다. Analytics 소스 커넥터에서 전체(비가상) 보고서 세트만 사용할 수 있습니다.


## CJA 데이터 보기

자세한 내용은 다음을 참조하십시오. [데이터 보기 개요](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ko-KR).

데이터 보기:

* CJA 필터를 기반으로 할 수 있습니다.
* 이전 데이터와 새 데이터 모두에 비파괴적인 방식으로 적용할 수 있습니다.
* 다른 비즈니스 팀에서 사용할 CJA 연결 위에 하나 이상의 가상 보기를 만들 수 있습니다.
* CJA의 다양한 사용자에 대한 다양한 종류의 데이터에 대한 액세스를 제어하고 조정하는 데 사용할 수 있습니다.
* CJA 연결을 통해 CJA로 전송되는 데이터를 변환하고 개선하기 위한 강력한 비파괴 옵션을 제공합니다.
* 는 CJA의 보고서 시간 처리 기능을 기반으로 합니다.
* 사용자가 &quot;session&quot;에 대한 사용자 지정 정의를 만들 수 있습니다.
* 는 필터 평가와 유사하게 보고서 런타임에 적용됩니다. 이것은 _after_ 소스 커넥터(Adobe Analytics 또는 기타)가 AEP 데이터 레이크의 데이터 세트에 데이터를 기록했습니다. _after_ 데이터는 CJA 연결을 통해 CJA에 수집되었습니다.
* 큐레이션은 사용자에게 표시되는 변수를 제한할 수 있지만, 변수를 무제한으로 허용합니다
* 이벤트, 세션 및 개인 컨테이너의 사용자 지정 이름을 지정할 수 있습니다.
* 사용자 지정 달력 옵션을 지원합니다.

데이터 보기는 다음을 수행하지 않습니다.

* 보고서 세트 또는 기타 데이터 세트를 결합할 수단을 직접 제공합니다. 대신 데이터 세트가 CJA 연결에서 와 결합됩니다. CJA 연결의 결합된 데이터는 해당 연결을 기반으로 한 모든 데이터 보기에서 사용할 수 있습니다.

## AEP 샌드박스

자세한 내용은 다음을 참조하십시오. [샌드박스 개요](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ko-KR).

AEP 샌드박스:

* 단일 AEP 인스턴스를 별도의 가상 환경(개발, 테스트, 스테이지, 프로덕션 등)으로 분할하는 방법을 제공합니다. 디지털 경험 애플리케이션을 개발하고 발전시키는 데 도움이 됩니다.
* 은 주어진 환경에 대한 모든 데이터 및 애플리케이션을 보유하는 컨테이너로 생각할 수 있습니다.

AEP 샌드박스는 다음을 수행하지 않습니다.

* 가상 보고서 세트, CJA 연결 또는 데이터 보기 와 유사한 기능을 제공합니다.
* 자체적으로 다른 데이터 세트를 사용하거나 사용하지 않고 보고서 세트를 결합합니다. 하지만 샌드박스 내의 데이터 세트는 CJA 연결 내에서 결합할 수 있습니다.

참고:

* 다른 샌드박스의 데이터를 CJA 내에서 결합할 수 없습니다.
* Analytics 소스 커넥터가 보고서 세트 데이터를 전송합니다 _변환_ 특정 샌드박스. 각 보고서 세트는 단일 샌드박스의 소스로 구성할 수 있습니다. 자세한 내용은 [Analytics 소스 커넥터 설명서](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) 자세한 내용
