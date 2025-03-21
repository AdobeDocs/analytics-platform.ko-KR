---
title: Adobe Journey Optimizer와 함께 사용할 개인화 오브젝트 사용
description: Adobe Journey Optimizer에 사용할 개인화 개체를 사용하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5086ac6e-5bee-4f0f-b7e5-a3d9bd8a1332
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 80%

---

# Adobe Journey Optimizer와 함께 사용할 개인화 오브젝트 사용 {#upgrade-personalization}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-personalization"
>title="Adobe Journey Optimizer에 대한 개인화 오브젝트 사용"
>abstract="최첨단 관리 머신 러닝 및 딥 러닝 기술을 활용하여, 개인화된 최적화는 비즈니스 사용자(마케터)가 비즈니스 목표를 정의하고, 고객 데이터를 활용하여 비즈니스 지향적인 모델을 훈련시켜 맞춤형 오퍼를 제공하고 KPI를 극대화할 수 있도록 합니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

최첨단 관리 머신 러닝 및 딥 러닝 기술을 활용하여, 개인화된 최적화는 비즈니스 사용자(마케터)가 비즈니스 목표를 정의하고, 고객 데이터를 활용하여 비즈니스 지향적인 모델을 훈련시켜 맞춤형 오퍼를 제공하고 KPI를 극대화할 수 있도록 합니다.

1. Journey Optimizer 안내서의 [개인화된 최적화 모델](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/offer-decisioning/rankings/ai-models/personalized-optimization-model)에 있는 정보를 따르십시오.

{{upgrade-final-step}}

<!--

The result of the personalization object ends up in a dataset. The result of experimentation. When a customer has used AA with Target, that ends up in a complete different space than when they're migrating to CJA and they're going to use CJA with Adobe Target. 

Target was the old way of setting up an A/B test or experimentation. Then ensuring the results of those tests in Target ended up in AA for reporting. Now if you're using Target, instead of saying that you want the data in Target, you can now select CJA as your reporting source for an Adobe Target activity. So if a customer is doing this in AA and they want to move to CJA, ...

If a customer has AJO, and is using Offers in AJO, then they can set up offers, and that also creates datasets in Platform... But that's not relevant with upgrade, exactly.



Questions we need to answer:

1. How do we determine the personalization criteria (Red for user A and blue for User B)

1. What do we implement on the site to determine the red / blue object?


2 ways we can do it:

Manually rendering content or Automatically rendering content. 


## Manual implementation of the Web SDK


## Mobile SDK implementation 





## Tags

-->
