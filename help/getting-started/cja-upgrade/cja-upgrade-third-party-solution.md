---
title: 서드파티 분석 솔루션에서 Customer Journey Analytics로 업그레이드
description: 서드파티 분석 솔루션에서 Customer Journey Analytics로 업그레이드하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
autotag-review: '2026-05-19T08:20:34.368Z'
TQID: 'https://experienceleague.adobe.com/fwYoa9oeIs2tujyDEWUj-GaAgpZQNBwup-YsHIe-TdU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 100%

---

# 서드파티 분석 솔루션에서 Customer Journey Analytics로 업그레이드 {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Adobe Analytics가 아닌 제품"
>abstract="Google Analytics와 같은 Adobe Analytics가 아닌 제품에 대한 데이터를 수집하는 구현 방식입니다. 이 옵션을 선택하면 Adobe Analytics가 아닌 제품에서 Customer Journey Analytics로 업그레이드할 때 적용되지 않는 업그레이드 안내서의 여러 옵션이 비활성화됩니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics가 아닌 분석 솔루션에서 Customer Journey Analytics로 업그레이드하는 데 권장되는 프로세스는 Customer Journey Analytics용 기본 데이터 수집 방법인 Experience Platform Web SDK의 새로운 구현입니다. Adobe는 Web SDK와 함께 서드파티 분석 솔루션의 내역 데이터를 Adobe Experience Platform으로 수집하는 것을 권장합니다.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Google Analytics와 같은 서드파티 분석 솔루션에서 Customer Journey Analytics로 전환하는 경우 다음 프로세스를 사용합니다.

1. [자세한 권장 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)를 따르십시오.

   이들 단계는 Adobe Analytics에서 업그레이드하는 조직을 대상으로 합니다. 이러한 단계를 따를 때 다음 사항을 이해하십시오.

   * 데이터스트림을 만들어야 합니다.

   * Adobe Analytics 솔루션이 아닌 솔루션에서는 프로젝트와 구성 요소를 마이그레이션할 수 없습니다.

   * 분석 솔루션에 따라 내역 데이터를 수집하기 위한 소스 커넥터를 사용할 수 있습니다. 자세한 내용은 Experience Platform 설명서의 [소스 커넥터 개요](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/home)에서 [분석](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/home#analytics)을 참조하십시오.


더욱 구체적인 조언, 지침 또는 지원이 필요한 경우 Adobe 담당자에게 문의하십시오.

