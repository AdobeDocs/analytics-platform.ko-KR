---
title: Customer Journey Analytics을 위한 스키마 만들기
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 41965bcd5ae8252fbf2ceda0d2b633ec6dc0e9a3
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 23%

---

# Customer Journey Analytics에 사용할 데이터 스트림 만들기

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

데이터스트림은 Adobe Experience Platform Web 및 Mobile SDK 구현 시 서버측 구성을 나타냅니다. Adobe Experience Platform SDK로 데이터를 수집하는 경우 데이터는 Adobe Experience Platform Edge Network로 전송됩니다. 데이터가 전달되는 서비스를 결정하는 데이터 스트림입니다.

설정에서는 수집된 데이터를 Adobe Experience Platform의 데이터 세트로 전송하도록 데이터 스트림을 구성할 수 있습니다.

>[!NOTE]
>
>다음 단계는 AppMeasurement 또는 Analytics 확장(태그)을 사용하는 Adobe Analytics 구현에만 필요합니다.
>
>Adobe Analytics 구현에서 웹 SDK 또는 웹 SDK 확장을 사용하는 경우 데이터 스트림이 이미 Adobe Analytics 환경에 있습니다.

데이터스트림을 설정하는 경우:

1. Adobe Experience Platform의 왼쪽 레일에서 [!UICONTROL 데이터 수집]에서 **[!UICONTROL 데이터스트림]**&#x200B;을 선택합니다.

1. **[!UICONTROL 새 데이터스트림]**&#x200B;을 선택합니다.

1. 데이터스트림의 이름을 지정하고 데이터스트림에 대해 설명합니다. [!UICONTROL 이벤트 스키마] 목록에서 스키마를 선택합니다.

   ![새 데이터스트림](assets/new-datastream.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

1. [권장된 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 [동적으로 생성된 업그레이드 단계](https://gigazelle.github.io/cja-ttv/)를 계속 따릅니다.
