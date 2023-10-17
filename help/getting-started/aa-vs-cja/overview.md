---
title: Adobe Analytics와의 비교
description: Customer Journey Analytics와 Adobe Analytics의 비교 개요입니다.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 4cbf01d397e7f89e67ae20702790129478d45cce
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 73%

---

# Adobe Analytics와의 비교

이 설명서 섹션에서는 Adobe Customer Journey Analytics과 Adobe Analytics 간의 차이점을 비교하고 이해하는 방법에 대해 설명합니다.

두 솔루션의 기본적인 차이점은 보고서 및 분석을 작성할 때 고려할 수 있는 데이터의 폭입니다.

Customer Journey Analytics에서는 *모든* 데이터 소스가 보고 및 분석에 사용하는 데이터의 일부가 될 수 있습니다. Adobe Analytics는 주로 웹 사이트와 모바일 앱에서 수집된 온라인 데이터를 대상으로 합니다. Adobe Analytics은 다른 소스에서 데이터를 가져오는 기능을 제공하지만, 주요 목적은 이전에 언급된 온라인 데이터에 대한 추가 컨텍스트를 제공하는 것입니다.

## 데이터 수집

Customer Journey Analytics은 Adobe Experience Platform 데이터 세트에 저장된 데이터를 사용합니다. Experience Platform의 이러한 데이터 세트에서 데이터를 수집하고 수집하는 몇 가지 옵션이 있습니다. 이 옵션은 [데이터 수집 개요](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=ko)에 자세히 설명되어 있습니다.

Adobe Analytics는 최종적으로 솔루션 자체 내에서 데이터를 수집합니다. 다시 말하지만, 데이터를 수집하는 몇 가지 옵션이 있으며, 이에 대해서는 [Adobe Analytics 구현 안내서](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=ko)에 자세히 나와 있습니다.

Customer Journey Analytics에서 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko)를 통해 Adobe Analytics 보고서 세트 데이터를 사용할 수 있습니다. 이 커넥터는 Adobe Analytics에서 수집된 데이터를 Experience Platform에 수집합니다. 그런 다음 Customer Journey Analytics에서 이 데이터 세트에 대한 연결을 만들 수 있습니다. 자세한 내용은 [Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 사용](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=ko)을 참조하십시오.


## 데이터 처리

데이터에 대해 보고하기 전에 해당 데이터를 처리하여 데이터가 보고에 제대로 사용될 수 있도록 해야 하는 경우가 많습니다. 데이터 처리는 수집 시간 및 보고 시간에 발생할 수 있습니다.

일반적으로 Customer Journey Analytics는 보고 시간에 Experience Platform 데이터 세트에서 수집 및 저장된 데이터를 사용하도록 설계되었습니다. Customer Journey Analytics는 강력한 보고 시 처리 기능을 제공하여 보고 및 분석할 수 있도록 데이터를 준비합니다. Experience Platform에 데이터를 수집하기 전에 해당 데이터를 매핑, 변환 및 검증해야 하는 경우, Experience Platform의 [ 데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko) 기능을 사용할 수 있습니다.

Adobe Analytics에서 데이터 처리는 대부분 데이터가 수집되면 발생합니다.

자세한 내용은 [Adobe Analytics 및 Customer Journey Analytics 보고 기능 간의 데이터 처리 비교](data-processing-comparisons.md) 및 [처리 규칙, VISTA 및 분류 대 데이터 준비](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=ko)을 참조하십시오.


## 용어

Customer Journey Analytics는 기본 XDM(경험 데이터 모델) 기반의 스키마에 갖춰진 유연성을 통해 차원과 지표를 유연하게 정의합니다. 예를 들어 Adobe Analytics에서 방문자, 방문 횟수 및 히트 수를 사용하는 경우 Customer Journey Analytics은 사람, 세션 및 이벤트를 동등한 개념으로 사용합니다(필요에 따라 이름을 변경할 수 있음).

용어 차이에 대한 자세한 내용은 [Analytics 소스 커넥터를 통해 전달되는 Analytics 데이터의 용어 비교](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=ko)를 참조하십시오.


## 가상 보고 환경 및 샌드박스

Adobe Analytics에는 수집된 데이터를 세그먼트화하고 세그먼트화된 데이터에 대한 액세스를 제어할 수 있는 가상 보고서 세트라는 개념이 있습니다.

Customer Journey Analytics은 데이터 보기라고 하는 유사한 개념을 가지고 있습니다. 데이터 보기는 연결에서 데이터를 해석하는 방법을 결정할 수 있는 컨테이너입니다. 보고와 분석에 대비하여 차원과 지표를 지정하고 구성할 수 있는 최고의 유연성을 제공합니다.

Experience Platform은 주어진 환경에 대한 데이터와 애플리케이션을 저장하는 컨테이너로 간주될 수 있는 샌드박스를 제공합니다. 샌드박스 기능은 Adobe Analytics 가상 보고서 세트 또는 Customer Journey Analytics 데이터 보기와 관련이 없습니다. Adobe Analytics 자체는 Experience Platform 샌드박스와 종속성이나 관계가 전혀 없습니다. Customer Journey Analytics은 Experience Platform 샌드박스를 지원하지만 몇 가지 중요한 고려 사항이 있습니다.

자세한 내용은 [가상 보고서 세트, 데이터 보기, Adobe Experience Platform 샌드박스 및 Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=ko)를 참조하십시오.


## ID

Customer Journey Analytics는 데이터가 포함된 데이터 세트가 준수하는 스키마의 일부로 정의되는 ID를 지원합니다. 따라서, ID는 Experience Platform의 기본 개념으로, 이는 [연결](../../connections/overview.md)을 설정(각 데이터 세트에 대한 개인 ID 정의)하고 크로스 채널 분석 시 [결합](../../stitching/overview.md)을 적용할 때 Customer Journey Analytics에서 사용합니다. Experience Platform SDK 및 API에서 사용되는 중요한 ID는 ECID(Experience Cloud ID)입니다.

Adobe Analytics는 Adobe Analytics ID(AAID)와 같은 보다 명확한 ID 필드 세트를 사용합니다. Analytics 소스 커넥터를 사용할 때 이러한 Adobe Analytics ID 필드는 특별 처리됩니다. 자세한 내용은 [AAID, ECID, AACUSTOMID 및 Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=ko)를 참조하십시오.


## 지원되는 기능

Adobe Analytics 기능 및 Customer Journey Analytics에서 이러한 기능이 지원되는 방식에 대한 개요는 [Customer Journey Analytics 기능 지원](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=ko)에서 확인할 수 있습니다.





