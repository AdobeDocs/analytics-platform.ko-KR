---
title: Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 활용
description: AEP 및 CJA에 수집하기 위한 Adobe Analytics 보고서 세트를 구성하는 방법
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 13%

---

# Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 활용

Adobe Analytics 고객은 Adobe Experience Platform 및 Customer Journey Analytics에서 보고서 세트를 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR). 다음 토론에서는 이러한 방법을 설명합니다.

## 준비

AEP 및 CJA에서 Adobe Analytics 보고서 세트를 사용할 준비가 되면 Customer Journey Analytics으로 원활하게 이동할 수 있도록 데이터를 준비하기 위해 몇 가지 작업을 수행해야 합니다. 자세한 내용은 다음 페이지를 참조하십시오.

* [Adobe Analytics-Customer Journey Analytics 진화](/help/getting-started/aa-to-cja.md)

## Adobe Experience Platform 및 CJA에 수집하기 위한 보고서 세트를 설정합니다

데이터를 준비했으면 AEP 및 CJA에서 사용할 보고서 세트 구성을 시작할 준비가 되었습니다.

1. **AEP 및 CJA에서 사용할 각 보고서 세트에 대한 데이터 흐름을 만듭니다.** 다음 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) 는 사용자가 사용할 수 있는 도구입니다 [연결 만들기](/help/connections/create-connection.md) (Adobe Analytics과 AEP 간 데이터 흐름 라고도 함). AEP에서 사용할 각 보고서 세트에 대해 소스 커넥터를 사용하여 하나의 데이터 흐름을 만듭니다. 데이터 흐름은 스키마가 로 변환된 보고서 세트 데이터의 사본을 만듭니다  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=ko) cja를 포함한 AEP 애플리케이션별 소비 소스 커넥터를 통해 데이터 흐름으로 구성된 각 보고서 세트는 AEP Data Lake에서 별도의 데이터 세트로 저장됩니다. 13개월의 이전 보고서 세트 데이터는 각 데이터 플로우에 자동으로 포함되며, 새 데이터는 지속적으로 AEP로 전송됩니다. Analytics 소스 커넥터를 사용하면 미리 스키마를 생성할 필요가 없습니다. Adobe Analytics에 특정된 표준화된 스키마가 자동으로 만들어집니다. 그러나 AEP의 [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko-KR) 데이터를 Data Lake에 저장하고 CJA에서 사용할 수 있게 하기 전에 이 스키마를 향상시키는 데 도구를 사용할 수 있습니다. 특정 유형의 데이터는 소스 커넥터로 필터링되며 AEP Data Lake의 데이터 세트에 존재하지 않습니다. 다른 행은 Data Lake와 CJA 간에 필터링될 수 있습니다. 자세한 내용은 [Adobe Analytics 데이터를 CJA 데이터와 비교](/help/troubleshooting/compare.md) 자세한 내용
1. **데이터 준비를 사용하여 CJA에서 보고서 세트를 결합할 수 있습니다.** 데이터 준비는 많은 유형의 데이터 변환에 사용할 수 있으며, Adobe Analytics 데이터에 대한 한 가지 일반적인 사용 방법은 여러 보고서 세트 간에 prop 및/또는 eVar 매핑의 차이점을 해결하여 보고서 세트를 CJA 내에서 쉽게 결합할 수 있도록 하는 것입니다. 자세한 내용은 [보고서 세트를 다른 스키마와 결합](/help/use-cases/aa-data/combine-report-suites.md) 자세한 내용
1. **크로스 채널 분석 활성화** 필요한 경우. CJA에서 여러 데이터 세트를 결합할 때 크로스 채널 분석의 ID 결합 기능을 사용하면 서로 다른 ID 네임스페이스를 여러 장치와 채널에서 고객의 단일 보기를 위해 하나의 결합된 ID로 확인할 수 있습니다. 자세한 내용은 [크로스 채널 분석 개요](/help/connections/cca/overview.md) 자세한 내용
1. **하나 이상의 CJA 연결을 만듭니다 .** 보고서 세트에 대한 데이터 세트를 AEP 데이터 레이크에서 사용할 수 있게 되면 하나 이상의 데이터 세트를 만들 수 있습니다 [CJA 연결](/help/connections/overview.md) 를 사용하여 해당 데이터 세트를 CJA로 가져옵니다. 연결 내에서 보고서 세트 데이터를 다른 유형의 데이터와 결합할 수 있으므로 고객 경험에 대한 진정한 크로스채널 보기를 만들 수 있습니다.
1. **하나 이상의 CJA 데이터 보기를 만듭니다 .** A [데이터 보기](/help/data-views/data-views.md) 는 CJA 연결에서 데이터를 해석하는 방법을 결정할 수 있는 Customer Journey Analytics 전용 컨테이너입니다. 데이터 보기는 강력한 [구성 옵션](/help/data-views/create-dataview.md) 사용자 지정 [Analysis Workspace](/help/analysis-workspace/home.md).

## Customer Journey Analytics과 Adobe Analytics 비교

Customer Journey Analytics과 Adobe Analytics은 많은 공통점을 가지고 있다. 예를 들어 CJA와 Adobe Analytics은 모두 자유 형식 사고형 분석을 위해 Analysis Workspace의 강력한 기능을 제공합니다. 그러나 CJA는 Adobe Experience Platform 내의 애플리케이션이며 데이터 처리에 AEP를 사용하므로 CJA와 Adobe Analytics은 여러 가지 중요한 방법으로 다릅니다. 다음 문서는 이러한 차이점을 이해하는 데 유용합니다.

* [Adobe Analytics 데이터와 CJA 데이터 비교](/help/troubleshooting/compare.md)
* [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Analytics 소스 커넥터를 통해 전달되는 Analytics 데이터의 용어 비교](/help/getting-started/aa-vs-cja/terminology.md)
* [Adobe Analytics 및 CJA 보고 기능 간의 데이터 처리 비교](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [가상 보고서 세트, 데이터 보기, AEP 샌드박스 및 Analytics Source Connector](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [처리 규칙, VISTA 및 분류 대 데이터 준비](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID 및 Analytics 소스 커넥터](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
