---
title: 서드파티 분석 솔루션에서 Customer Journey Analytics로 업그레이드
description: 타사 분석 솔루션에서 Customer Journey Analytics으로 업그레이드하는 방법에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: d2d945724e7972bd4a29fa13291577bb76288229
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 9%

---

# 서드파티 분석 솔루션에서 Customer Journey Analytics로 업그레이드 {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Adobe Analytics 이외의 제품"
>abstract="Google Analytics과 같은 Adobe Analytics 이외의 제품에 대한 데이터를 수집하는 구현입니다. 이 옵션을 선택하면 Adobe Analytics이 아닌 제품에서 Customer Journey Analytics으로 업그레이드할 때 적용되지 않는 몇 가지 선택 사항이 설문지에서 비활성화됩니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analytics 업그레이드 확인 목록](https://gigazelle.github.io/cja-ttv/)의 질문에 답변할 때 이 페이지의 정보를 사용하십시오.

Adobe Analytics 이외의 Analytics 솔루션에서 Customer Journey Analytics으로 업그레이드하는 권장 프로세스는 Customer Journey Analytics에서 선호하는 데이터 수집 방법인 Experience Platform Web SDK의 새로운 구현입니다. 웹 SDK과 함께 Adobe에서는 타사 분석 솔루션의 내역 데이터를 Adobe Experience Platform으로 수집할 것을 권장합니다.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Google Analytics과 같은 서드파티 분석 솔루션에서 Customer Journey Analytics으로 이동할 때 다음 프로세스를 사용합니다.

1. [자세한 권장 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)를 따르십시오.

   이러한 단계는 Adobe Analytics에서 업그레이드하는 조직을 위한 것입니다. 이 단계를 수행할 때 다음 사항을 이해하십시오.

   * 데이터 스트림을 생성해야 합니다.

   * 비 Adobe Analytics 솔루션에서는 프로젝트 및 구성 요소를 마이그레이션할 수 없습니다.

   * 분석 솔루션에 따라 내역 데이터 수집에 소스 커넥터를 사용할 수 있습니다. 자세한 내용은 Experience Platform 설명서의 [Source 커넥터 개요](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home)에서 [분석](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#analytics)을 참조하십시오.


보다 구체적인 조언, 안내 또는 지원이 필요한 경우 Adobe 담당자에게 문의하십시오.

