---
title: Target 보고
description: Adobe Target과 Customer Journey Analytics 통합
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
TQID: https://experienceleague.adobe.com/7Q8q-e58PrmANht9DpOXuNFImYC48ELhrXPRhBG6gYQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 44%

---

# Target 보고

Customer Journey Analytics의 Target 보고를 사용하면 Customer Journey Analytics에서 직접 Adobe Target 활동을 측정하고 보고할 수 있습니다. 이 기능은 Analytics for Target(A4T)을 통해 Adobe Analytics(AA)에서 수행되는 것과 비슷하지만 Adobe Experience Platform(AEP)에 대한 연결을 통해 수행됩니다.

이제 Experience Platform에서 기본적으로 사용할 수 있는 Target 분류 조회 데이터 세트를 Customer Journey Analytics 연결에 추가하여 사용자가 Target 보고 도구, Target 주문 속성 및 기타 기능에 적절히 노출할 수 있습니다. Customer Journey Analytics 데이터 보기 내에서 약간의 준비와 조정만 수행하면 Target 데이터를 CJA으로 직접 전송하려는 모든 사용자가 이러한 활동을 즉시 사용할 수 있습니다.

## 주요 이점

* 마케터가 언제든지 Customer Journey Analytics 성공 지표를 Target 활동 보고서에 동적으로 적용할 수 있습니다. 활동을 실행하기 전에 모든 항목을 지정할 필요는 없습니다.
* 마케터는 실험 패널과 같은 Customer Journey Analytics 기능을 활용하여 웹 사이트 개인화를 더 자세히 분석할 수 있습니다.
* 마케터는 Adobe Journey Optimizer 및 Target에 대한 단일 보고 소스를 가질 수 있습니다. 두 개인화 제품 모두 Customer Journey Analytics에 연결하여 웹 개인화를 보다 전체적으로 살펴볼 수 있습니다.

## 참고 사항 및 고려 사항

Target 활동에서는 [보고 소스로 Customer Journey Analytics을 사용](https://experienceleague.adobe.com/ko/docs/target/using/integrate/cja/target-reporting-in-cja)해야 합니다.

Target 분류 이벤트 데이터 세트가 연결에 추가되면 이들 구성 요소가 차원으로 추가되면 데이터 보기 내에서 다음과 같은 몇 가지 사소한 조정을 수행할 수 있습니다.

* 지속성을 Target에서 추적하는 방식과 유사하게 설정합니다(적절한 설정이 있는지 Target 컨설턴트 또는 고객에게 확인).

* 지속성을 모두로 설정하면 여러 Target 활동을 동시에 추적하고 향후 또는 이전 활동에서 덮어쓰지 않습니다.

## 더 자세한 정보

자세한 내용은 Target 설명서의 [Adobe Customer Journey Analytics에서 Target 보고](https://experienceleague.adobe.com/ko/docs/target/using/integrate/cja/target-reporting-in-cja)를 참조하십시오.

분석가가 다양한 사용자 경험, 마케팅 또는 메시지의 변형을 비교하여 어떤 것이 특정 결과를 도출하는 데 가장 적합한지 판단하는 방법에 대한 자세한 내용은 [실험 패널](../analysis-workspace/c-panels/experimentation.md)을 참조하십시오. 온라인, 오프라인, Target 또는 Journey Optimizer와 같은 Adobe 솔루션 및 BYO(Bring Your Own) 데이터 등 모든 실험 플랫폼에서 A/B 실험의 상승도와 신뢰도를 평가할 수 있습니다.
