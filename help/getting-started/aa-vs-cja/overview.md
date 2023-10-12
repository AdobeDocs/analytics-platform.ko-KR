---
title: Adobe Analytics와의 비교
description: Customer Journey Analytics과 Adobe Analytics의 비교 개요.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 59aabb38ea3e5ba1501ab8da11d14ea2385d8a6b
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 8%

---

# Adobe Analytics와의 비교

이 설명서 섹션에서는 Adobe Analytics과 Customer Journey Analytics 간의 차이점을 비교하고 이해하는 방법에 대해 설명합니다.

두 솔루션의 근본적인 차이점은 보고서와 분석을 작성할 때 고려할 수 있는 데이터의 폭입니다.

Customer Journey Analytics, *임의* 데이터 소스는 보고 및 분석에 사용하는 데이터의 일부일 수 있습니다. Adobe Analytics은 주로 웹 사이트 및 모바일 앱에서 수집된 온라인 데이터를 대상으로 합니다. Adobe Analytics은 다른 소스에서 데이터를 가져오는 기능을 제공하지만, 주요 목적은 이전에 언급된 온라인 데이터에 더 많은 컨텍스트를 제공하는 것입니다.

## 데이터 수집

Customer Journey Analytics은 Experience Platform 데이터 세트에 저장된 데이터에 의존합니다. Experience Platform의 이러한 데이터 세트에서 데이터를 수집하고 수집하는 몇 가지 옵션이 있습니다. 이러한 옵션은 다음에 더 자세히 설명되어 있습니다. [데이터 수집 개요](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

Adobe Analytics은 궁극적으로 솔루션 자체 내에서 데이터를 수집합니다. 다시 말하지만, 해당 데이터를 수집할 수 있는 몇 가지 옵션이 있습니다. 이러한 옵션은 다음에 더 자세히 설명되어 있습니다. [Adobe Analytics 구현 안내서](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=ko).

다음을 사용하여 Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터를 사용할 수 있습니다. [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko-KR). 이 커넥터는 Adobe Analytics에서 수집된 데이터를 사용하여 Experience Platform에서 수집한 다음 Customer Journey Analytics에서 사용합니다. 다음을 참조하십시오 [Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 사용](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=ko-KR) 추가 정보.


## 데이터 처리

데이터에 대해 보고하려면 먼저 해당 데이터를 처리하여 데이터를 해당 목적에 맞게 사용할 수 있도록 해야 하는 경우가 많습니다. 이러한 데이터 처리는 수집 시간 및 보고 시간에 발생할 수 있습니다.

일반적으로 Customer Journey Analytics은 보고서 시간에 Experience Platform 데이터 세트에 수집 및 저장된 데이터로 작동하도록 디자인됩니다. Customer Journey Analytics은 강력한 보고서 처리 시간 기능을 제공하여 데이터가 보고 및 분석할 수 있도록 합니다. Experience Platform에서 수집되기 전에 데이터를 매핑, 변형 및 유효성 검사를 해야 하는 경우 [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko) Experience Platform 기능.

Adobe Analytics에서 대부분의 데이터 처리는 데이터를 수집한 직후에 발생한다.

다음을 참조하십시오 [Adobe Analytics 및 Customer Journey Analytics 간 데이터 처리 비교](data-processing-comparisons.md) 및 [처리 규칙, VISTA 및 분류 대 데이터 준비](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=ko-KR) 추가 정보.


## 용어

Customer Journey Analytics은 기본 XDM(Experience Data Model) 기반 스키마가 제공하는 유연성으로 활성화된 차원 및 지표를 정의하는 방법에 대한 유연성을 제공합니다. 예를 들어 Adobe Analytics에서 방문자, 방문 횟수 및 히트 수를 사용하는 경우 Customer Journey Analytics은 사람, 세션 및 이벤트를 동등한 개념으로 사용하지만 필요에 따라 이름을 변경할 수 있습니다.

다음을 참조하십시오 [Analytics 소스 커넥터를 통해 전달되는 Analytics 데이터의 용어 비교](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) 용어의 차이점에 대해서는 를 참조하십시오.


## 가상 보고 환경 및 샌드박스

Adobe Analytics에는 수집된 데이터를 세그먼트화하고 세그먼트화된 데이터에 대한 액세스를 제어할 수 있는 가상 보고서 세트 라는 개념이 있습니다.

Customer Journey Analytics은 데이터 보기 라는 유사한 개념을 가지고 있습니다. 데이터 보기는 연결에서 데이터를 해석하는 방법을 결정할 수 있는 컨테이너입니다. 보고 및 분석에 대비하여 차원 및 지표를 지정하고 구성할 수 있는 최고의 유연성을 제공합니다.

Experience Platform은 주어진 환경에 대한 데이터 및 애플리케이션을 저장하는 컨테이너로 생각할 수 있는 샌드박스를 제공합니다. 샌드박스의 기능은 Adobe Analytics 가상 보고서 세트 또는 Customer Journey Analytics 데이터 보기와 관련이 없습니다. Adobe Analytics 자체에는 Experience Platform 샌드박스와의 종속성이나 관계가 전혀 없습니다. Customer Journey Analytics은 Experience Platform 샌드박스를 지원하지만 몇 가지 중요한 고려 사항이 있습니다.

다음을 참조하십시오 [가상 보고서 세트, 데이터 보기, Adobe Experience Platform 샌드박스 및 Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=ko) 추가 정보.


## ID

Customer Journey Analytics은 데이터가 포함된 데이터 세트가 준수하는 스키마의 일부로 정의하는 ID를 지원합니다. 따라서 ID는 Customer Journey Analytics이 를 설정할 때 사용하는 Experience Platform 기본 개념입니다. [연결](../../connections/overview.md) (각 데이터 세트에 대한 개인 ID를 정의하여) 및 적용 시 [결합](../../stitching/overview.md) 크로스 채널 분석용. Experience Platform SDK 및 API에서 사용하는 중요한 ID는 ECID(Experience Cloud ID)입니다.

Adobe Analytics은 AAID(Adobe Analytics ID)와 같은 보다 명확한 ID 필드 세트를 사용합니다. Analytics 소스 커넥터를 사용하는 경우 이러한 Adobe Analytics 식별 필드에는 특별한 처리가 적용됩니다. 다음을 참조하십시오 [AAID, ECID, AACUSTOMID 및 Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) 추가 정보.


## 기능

Adobe Analytics 기능에 대한 개요와 이러한 기능이 Customer Journey Analytics에서 어떻게 지원되는지 알아보십시오. [Customer Journey Analytics 기능 지원](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).





