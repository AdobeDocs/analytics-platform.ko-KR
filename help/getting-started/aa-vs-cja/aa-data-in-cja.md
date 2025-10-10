---
title: Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 사용
description: Adobe Experience Platform 및 Customer Journey Analytics에 수집하기 위한 Adobe Analytics 보고서 세트를 구성하는 방법
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 100%

---

# Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 사용

Adobe Analytics 고객은 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR)를 사용하여 Adobe Experience Platform 및 Customer Journey Analytics에서 보고서 세트를 쉽게 활용할 수 있습니다. 다음은 이를 수행하는 방법에 대해 설명합니다.

>[!IMPORTANT]
>
>여러 보고서 세트에서 데이터 분석을 수행하려면 **Select** 패키지가 있어야 합니다. 보유하고 있는 Customer Journey Analytics 패키지가 무엇인지 확실하지 않은 경우 관리자에게 문의하십시오.&#x200B;

## 준비

Adobe Experience Platform 및 Customer Journey Analytics에서 Adobe Analytics 보고서 세트를 사용할 준비가 되면 Customer Journey Analytics로 원활하게 이동할 수 있도록 데이터를 준비하기 위해 고려해야 할 몇 가지 사항이 있습니다. 자세한 내용은 다음 페이지를 참조하십시오.

* [Adobe Analytics에서 Customer Journey Analytics로의 진화](/help/getting-started/aa-to-cja.md)

## Adobe Experience Platform 및 Customer Journey Analytics에 수집하기 위한 보고서 세트 설정

데이터가 준비되면 Adobe Experience Platform 및 Customer Journey Analytics에서 사용할 보고서 세트 구성을 시작할 수 있습니다.

1. **Adobe Experience Platform 및 Customer Journey Analytics에서 사용하려는 각 보고서 세트에 대해 데이터 흐름을 만듭니다.** [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR)는 Adobe Analytics와 Adobe Experience Platform 간에 [연결을 생성](/help/connections/create-connection.md)(데이터 흐름이라고도 함)할 수 있는 도구입니다. 소스 커넥터를 사용하여 Adobe Experience Platform에서 사용하려는 각 보고서 세트에 대해 하나의 데이터 흐름을 만듭니다. 데이터 흐름은 Customer Journey Analytics를 포함한 Adobe Experience Platform 애플리케이션에서 사용할 수 있도록 스키마가 [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=ko-KR)으로 변환된 보고서 세트 데이터의 복사본을 만듭니다.<p>소스 커넥터를 통한 데이터 흐름으로 구성된 각 보고서 세트는 Adobe Experience Platform 데이터 레이크에 별도의 데이터 세트로 저장됩니다. 각 데이터 흐름에는 13개월 분량의 기록 보고서 세트 데이터가 자동으로 포함되며, 새 데이터가 지속적으로 Adobe Experience Platform으로 유입됩니다. (2023년 4월 26일부터 비프로덕션 샌드박스의 채우기는 3개월로 제한됩니다.) Analytics 소스 커넥터를 사용하면 스키마를 미리 만들 필요가 없습니다. Adobe Analytics 전용 표준화된 스키마가 자동으로 생성됩니다. 그러나 데이터가 데이터 레이크에 저장되고 Customer Journey Analytics에서 사용할 수 있게 되기 전에 Adobe Experience Platform의 [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko-KR) 도구를 사용하여 이 스키마를 향상시킬 수 있습니다. 일부 데이터 유형은 소스 커넥터에 의해 세그먼트화되며 Adobe Experience Platform 데이터 레이크의 데이터 세트에 표시되지 않습니다. 다른 행은 데이터 레이크와 Customer Journey Analytics 간에 세그먼트화될 수 있습니다. 자세한 내용은 [Adobe Analytics 데이터와 Customer Journey Analytics 데이터 비교](/help/troubleshooting/compare.md)를 참조하십시오.
1. **데이터 준비를 사용하여 Customer Journey Analytics에서 보고서 세트를 결합할 수 있습니다.** 데이터 준비는 다양한 유형의 데이터 변환에 사용할 수 있으며 Adobe Analytics 데이터의 일반적인 용도 중 하나는 Customer Journey Analytics 내에서 보고서 세트를 쉽게 결합할 수 있도록 여러 보고서 세트에서 prop 및/또는 eVar 매핑의 차이를 해결하는 것입니다. 자세한 내용은 [보고서 세트를 다른 스키마와 결합](/help/use-cases/aa-data/combine-report-suites.md)을 참조하십시오.
1. 필요에 따라 **결합을 활성화합니다**. Customer Journey Analytics에서 여러 데이터 세트를 결합할 때 결합 기능을 사용하면 서로 다른 ID 네임스페이스를 결합된 단일 ID로 변환하여 여러 디바이스 및 채널에서 고객을 한 눈에 볼 수 있습니다. 자세한 내용은 [결합 개요](../../stitching/overview.md)를 참조하십시오.
1. **하나 이상의 Customer Journey Analytics 연결을 만듭니다.** Adobe Experience Platform 데이터 레이크에서 보고서 세트의 데이터 세트를 사용할 수 있게 되면 하나 이상의 [Customer Journey Analytics 연결](/help/connections/overview.md)을 만들어 해당 데이터 세트를 Customer Journey Analytics로 가져올 수 있습니다. 연결 내에서 보고서 세트 데이터를 다른 유형의 데이터와 결합하여 고객 경험에 대한 진정한 크로스 채널 보기를 만들 수 있습니다.
1. **하나 이상의 Customer Journey Analytics 데이터 보기를 만듭니다.** [데이터 보기](/help/data-views/data-views.md)는 Customer Journey Analytics와 관련된 컨테이너입니다. 이를 통해 Customer Journey Analytics 연결에서 데이터를 해석하는 방법을 결정할 수 있습니다. 데이터 보기에는 [Analysis Workspace](/help/analysis-workspace/home.md)에서 사용자에게 제공되는 데이터를 맞춤화하기 위한 강력한 [구성 옵션](/help/data-views/create-dataview.md)이 다수 준비되어 있습니다.

## Customer Journey Analytics 및 Adobe Analytics 비교

Customer Journey Analytics와 Adobe Analytics 사이에는 많은 유사점이 있습니다. 예를 들어 Customer Journey Analytics와 Adobe Analytics 모두 Analysis Workspace 기능을 제공하여 자유 형식의 사고 속도 분석을 가능하게 합니다. 그러나 Customer Journey Analytics는 Adobe Experience Platform의 애플리케이션으로 Adobe Experience Platform을 사용하여 데이터를 수집하기 때문에 Customer Journey Analytics와 Adobe Analytics는 여러 가지 중요한 면에서 차이가 있습니다. 다음 문서는 이러한 차이점을 이해하는 데 유용합니다.

* [Adobe Analytics 데이터와 Customer Journey Analytics 데이터 비교](/help/troubleshooting/compare.md)
* [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Analytics 소스 커넥터를 통해 전달되는 Analytics 데이터의 용어 비교](/help/getting-started/aa-vs-cja/terminology.md)
* [Adobe Analytics 및 Customer Journey Analytics 보고 기능 간의 데이터 처리 비교](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [가상 보고서 세트, 데이터 보기, Adobe Experience Platform 샌드박스 및 Analytics 소스 커넥터](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [처리 규칙, VISTA 및 분류 대 데이터 준비](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID 및 Analytics 소스 커넥터](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
