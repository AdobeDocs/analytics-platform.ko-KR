---
title: Target 보고
description: Adobe Target과 Customer Journey Analytics 통합
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: 979564d0249abadd454ce43aba9aeae2c78a44f0
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 41%

---

# Target 보고

Customer Journey Analytics의 Target 보고를 사용하면 Customer Journey Analytics에서 직접 Adobe Target 활동을 측정하고 보고할 수 있습니다. 이 기능은 Analytics for Target(A4T)을 통해 Adobe Analytics(AA)에서 수행되는 것과 비슷하지만 Adobe Experience Platform(AEP)에 연결된 것과 비슷합니다.

이제 Customer Journey Analytics 연결에 Target Experience Platform 조회 데이터 세트(기본적으로 분류에서 사용 가능)를 추가하면 사용자가 Target 보고 도구, Target 주문 속성 및 기타 기능에 적절히 노출될 수 있습니다. Customer Journey Analytics 데이터 보기 내에서 약간의 준비와 조정만 수행하면 Target 데이터를 CJA로 직접 전송하려는 모든 사용자가 이러한 활동을 즉시 사용할 수 있습니다.

## 주요 이점

* 마케터가 언제든지 Customer Journey Analytics 성공 지표를 Target 활동 보고서에 동적으로 적용할 수 있습니다. 활동을 실행하기 전에 모든 항목을 지정할 필요는 없습니다.
* 마케터는 실험 패널과 같은 Customer Journey Analytics 기능을 활용하여 웹 사이트 개인화를 더 자세히 분석할 수 있습니다.
* 마케터는 Adobe Journey Optimizer 및 Target에 대한 단일 보고 소스를 가질 수 있습니다. 두 개인화 제품 모두 Customer Journey Analytics에 연결하여 웹 개인화를 보다 전체적으로 살펴볼 수 있습니다.

## 참고 사항 및 고려 사항

Target 분류 이벤트 데이터 세트가 CJA 연결에 추가되면 이들 구성 요소가 차원으로 추가되면 CJA 데이터 보기 내에서 다음과 같은 몇 가지 사소한 조정을 수행할 수 있습니다.

* 지속성을 Target에서 추적하는 방식과 유사하게 설정합니다(적절한 설정이 있는지 Target 컨설턴트 또는 고객에게 확인).

* 지속성을 모두로 설정하면 여러 Target 활동을 동시에 추적하고 향후 또는 이전 활동에서 덮어쓰지 않습니다.

## 더 자세한 정보

자세한 내용은 Target 설명서의 [Adobe Customer Journey Analytics에서 Target 보고](https://experienceleague.adobe.com/ko/docs/target/using/integrate/cja/target-reporting-in-cja)를 참조하십시오.

분석가가 다양한 사용자 경험, 마케팅 또는 메시지의 변형을 비교하여 어떤 것이 특정 결과를 도출하는 데 가장 적합한지 판단하는 방법에 대한 자세한 내용은 [실험 패널](../analysis-workspace/c-panels/experimentation.md)을 참조하십시오. 온라인, 오프라인, Target 또는 Journey Optimizer와 같은 Adobe 솔루션 및 BYO(Bring Your Own) 데이터 등 모든 실험 플랫폼에서 A/B 실험의 상승도와 신뢰도를 평가할 수 있습니다.
