---
title: Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 활용
description: Adobe Experience Platform 및 Customer Journey Analytics에 수집하기 위한 Adobe Analytics 보고서 세트를 구성하는 방법
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 29%

---

# Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 활용

Adobe Analytics 고객은 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko)를 사용하여 Adobe Experience Platform 및 Customer Journey Analytics에서 보고서 세트를 쉽게 활용할 수 있습니다. 다음은 이를 수행하는 방법에 대해 설명합니다.

## 준비

Adobe Experience Platform 및 Customer Journey Analytics에서 Adobe Analytics 보고서 세트를 사용할 준비가 되면 Customer Journey Analytics으로 원활하게 이동할 수 있도록 데이터를 준비하기 위해 고려해야 할 몇 가지 사항이 있습니다. 자세한 내용은 다음 페이지를 참조하십시오.

* [Adobe Analytics에서 Customer Journey Analytics로의 진화](/help/getting-started/aa-to-cja.md)

## Adobe Experience Platform 및 Customer Journey Analytics에 수집하기 위한 보고서 세트 설정

데이터를 준비했으면 Adobe Experience Platform 및 Customer Journey Analytics에서 사용할 보고서 세트 구성을 시작할 준비가 되었습니다.

1. **Adobe Experience Platform 및 Customer Journey Analytics에서 사용하려는 각 보고서 세트에 대한 데이터 흐름을 만듭니다.** 다음 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko) 은 다음 작업을 수행할 수 있는 도구입니다. [연결 만들기](/help/connections/create-connection.md) Adobe Analytics과 Adobe Experience Platform 간 (데이터 흐름이라고도 함) 소스 커넥터를 사용하여 Adobe Experience Platform에서 사용할 각 보고서 세트에 대해 하나의 데이터 흐름을 만듭니다. 데이터 흐름은 스키마가 변환된 보고서 세트 데이터의 복사본을 만듭니다.  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=ko) Customer Journey Analytics을 포함한 Adobe Experience Platform 애플리케이션에서 사용합니다.<p>소스 커넥터를 통한 데이터 흐름으로 구성된 각 보고서 세트는 Adobe Experience Platform 데이터 레이크에 별도의 데이터 세트로 저장됩니다. 각 데이터 흐름에는 13개월 분량의 기록 보고서 세트 데이터가 자동으로 포함되며, 새로운 데이터가 지속적으로 Adobe Experience Platform으로 유입됩니다. (2023년 4월 26일부터 비프로덕션 샌드박스의 채우기 기간은 3개월로 제한됩니다.) Analytics 소스 커넥터를 사용하면 스키마를 미리 생성할 필요가 없습니다. Adobe Analytics 전용 표준화된 스키마가 자동으로 생성됩니다. 그러나 Adobe Experience Platform [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko) 데이터가 데이터 레이크에 저장되고 Customer Journey Analytics에서 사용할 수 있게 되기 전에 도구를 사용하여 이 스키마를 향상시킬 수 있습니다. 특정 유형의 데이터는 소스 커넥터에 의해 필터링되며 Adobe Experience Platform 데이터 레이크의 데이터 세트에 표시되지 않습니다. 다른 행은 데이터 레이크와 Customer Journey Analytics 간에 필터링될 수 있습니다. 다음을 참조하십시오 [Adobe Analytics 데이터와 Customer Journey Analytics 데이터 비교](/help/troubleshooting/compare.md) 을 참조하십시오.
1. **데이터 준비를 사용하여 Customer Journey Analytics에서 보고서 세트를 결합할 수 있습니다.** 데이터 준비는 다양한 유형의 데이터 변환에 사용할 수 있으며 Adobe Analytics 데이터의 일반적인 용도 중 하나는 보고서 세트를 Customer Journey Analytics 내에서 쉽게 결합할 수 있도록 여러 보고서 세트에서 prop 및/또는 eVar 매핑의 차이를 해결하는 것입니다. 자세한 내용은 [보고서 세트를 다른 스키마와 결합](/help/use-cases/aa-data/combine-report-suites.md)을 참조하십시오.
1. **결합 활성화** 필요한 경우. Customer Journey Analytics에서 여러 데이터 세트를 결합할 때 결합 기능을 사용하면 서로 다른 ID 네임스페이스를 결합된 단일 ID로 변환하여 여러 디바이스 및 채널에서 고객을 한 눈에 볼 수 있습니다. 다음을 참조하십시오 [결합 개요](../../stitching/overview.md) 을 참조하십시오.
1. **하나 이상의 Customer Journey Analytics 연결을 만듭니다.** Adobe Experience Platform 데이터 레이크에서 보고서 세트의 데이터 세트를 사용할 수 있으면 하나 이상을 만들 수 있습니다 [Customer Journey Analytics 연결](/help/connections/overview.md) Customer Journey Analytics 상태로 전환합니다. 연결 내에서 보고서 세트 데이터를 다른 유형의 데이터와 결합하여 고객 경험에 대한 진정한 크로스 채널 보기를 만들 수 있습니다.
1. **하나 이상의 Customer Journey Analytics 데이터 보기를 만듭니다.** A [데이터 보기](/help/data-views/data-views.md) 는 Customer Journey Analytics 연결에서 데이터를 해석하는 방법을 결정할 수 있도록 해주는 Customer Journey Analytics과 관련된 컨테이너입니다. 데이터 보기에는 [Analysis Workspace](/help/analysis-workspace/home.md)에서 사용자에게 제공되는 데이터를 맞춤화하기 위한 강력한 [구성 옵션](/help/data-views/create-dataview.md)이 다수 준비되어 있습니다.

## Customer Journey Analytics 및 Adobe Analytics 비교

Customer Journey Analytics와 Adobe Analytics 사이에는 많은 유사점이 있습니다. 예를 들어, Customer Journey Analytics과 Adobe Analytics은 모두 자유 형식의 사고 속도 분석을 위한 Analysis Workspace 기능을 제공합니다. 그러나 Customer Journey Analytics은 Adobe Experience Platform 내의 애플리케이션이며 데이터 수집에 Adobe Experience Platform을 활용하므로 Customer Journey Analytics과 Adobe Analytics은 여러 가지 중요한 면에서 다릅니다. 다음 문서는 이러한 차이점을 이해하는 데 유용합니다.

* [Adobe Analytics 데이터와 Customer Journey Analytics 데이터 비교](/help/troubleshooting/compare.md)
* [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Analytics 소스 커넥터를 통해 전달되는 Analytics 데이터의 용어 비교](/help/getting-started/aa-vs-cja/terminology.md)
* [Adobe Analytics 및 Customer Journey Analytics 보고 기능 간의 데이터 처리 비교](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [가상 보고서 세트, 데이터 보기, Adobe Experience Platform 샌드박스 및 Analytics 소스 커넥터](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [처리 규칙, VISTA 및 분류 대 데이터 준비](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID 및 Analytics 소스 커넥터](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
