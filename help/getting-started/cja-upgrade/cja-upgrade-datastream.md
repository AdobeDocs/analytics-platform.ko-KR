---
title: Customer Journey Analytics을 위한 스키마 만들기
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 35%

---

# Customer Journey Analytics에 사용할 데이터 스트림 만들기

>[!NOTE]
>
>Adobe Analytics 이 설명서는 [업그레이드 Customer Journey Analytics 설문지](https://gigazelle.github.io/cja-ttv/)를 작성한 후 사용해야 합니다.
> 
>조직에 대해 동적으로 생성된 이전 단계를 모두 완료한 후에만 이 페이지의 단계를 따르십시오.
>
>이 페이지의 단계를 완료한 후 [Adobe Analytics에서 조직에 대해 동적으로 생성된 업그레이드 단계를 계속 수행하여 업그레이드 질문을 Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/)하십시오.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

데이터스트림은 Adobe Experience Platform Web 및 Mobile SDK 구현 시 서버측 구성을 나타냅니다. Adobe Experience Platform SDK로 데이터를 수집하는 경우 데이터는 Adobe Experience Platform Edge Network로 전송됩니다. 데이터가 전달되는 서비스를 결정하는 데이터 스트림입니다.

설정에서 Adobe Experience Platform의 데이터 세트로 웹 사이트에서 수집한 데이터를 전송하려고 합니다.

데이터스트림을 설정하는 경우:

1. Adobe Experience Platform의 왼쪽 레일에서 [!UICONTROL 데이터 수집]에서 **[!UICONTROL 데이터스트림]**&#x200B;을 선택합니다.

1. **[!UICONTROL 새 데이터스트림]**&#x200B;을 선택합니다.

1. 데이터스트림의 이름을 지정하고 데이터스트림에 대해 설명합니다. [!UICONTROL 이벤트 스키마] 목록에서 스키마를 선택합니다.

   ![새 데이터스트림](assets/new-datastream.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

1. [Adobe Analytics에서 업그레이드 Customer Journey Analytics 설문 조사](https://gigazelle.github.io/cja-ttv/)로 조직에 대해 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

