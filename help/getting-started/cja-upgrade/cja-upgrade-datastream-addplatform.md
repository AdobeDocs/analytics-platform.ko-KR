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
source-wordcount: '318'
ht-degree: 29%

---

# 데이터스트림에 서비스로 플랫폼 추가

>[!NOTE]
>
>Adobe Analytics 이 설명서는 [업그레이드 Customer Journey Analytics 설문지](https://gigazelle.github.io/cja-ttv/)를 작성한 후 사용해야 합니다.
> 
>조직에 대해 동적으로 생성된 이전 단계를 모두 완료한 후에만 이 페이지의 단계를 따르십시오.
>
>이 페이지의 단계를 완료한 후 [Adobe Analytics에서 조직에 대해 동적으로 생성된 업그레이드 단계를 계속 수행하여 업그레이드 질문을 Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/)하십시오.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

이 섹션의 단계를 완료하기 전에 데이터 스트림이 이미 있어야 합니다. 데이터 스트림이 생성된 시기와 방법은 다음과 같이 Adobe Analytics 구현에 따라 다릅니다.

* Adobe Analytics 구현에서 Web SDK 또는 Web SDK 확장을 사용하는 경우 업그레이드 프로세스 전에 Adobe Analytics 환경에서 데이터 스트림을 사용할 수 있었습니다.

* 다른 Adobe Analytics 구현의 경우 [Customer Journey Analytics에 사용할 데이터 스트림 만들기](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)에 설명된 대로 데이터 스트림을 만드는 것은 업그레이드 프로세스의 일부입니다.

데이터 스트림을 사용할 수 있는 경우 Platform as a Service를 추가해야 합니다.

1. 왼쪽 레일의 Adobe Experience Platform UI에서 [!UICONTROL 데이터 수집]의 **[!UICONTROL 데이터스트림]**&#x200B;을 선택합니다.

1. 이전에 구성한 데이터 스트림을 선택합니다. <!--true?-->

1. **[!UICONTROL 서비스 추가]**&#x200B;를 선택합니다.

1. [!UICONTROL 서비스 추가 화면]에서:

   1. [!UICONTROL 서비스] 목록에서 **[!UICONTROL Adobe Experience Platform]**&#x200B;을 선택합니다.

   1. **[!UICONTROL 활성화됨]**&#x200B;이 선택되었는지 확인합니다.

   1. [!UICONTROL 이벤트 데이터 세트] 목록에서 데이터 세트를 선택합니다.

      ![데이터스트림 AEP 서비스](./assets/datastream-aep-service.png)

   1. 다른 설정을 종료하고 **[!UICONTROL 저장]**&#x200B;을 선택하여 데이터스트림을 저장합니다.

   이제 데이터스트림을 구성하여 웹 사이트에서 수집한 데이터를 Adobe Experience Platform의 데이터 세트로 전달합니다.

   데이터스트림을 구성하는 방법과 민감한 데이터를 처리하는 방법에 대한 자세한 내용은 [데이터스트림 개요](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html)를 참조하십시오.

1. [Adobe Analytics에서 업그레이드 Customer Journey Analytics 설문 조사](https://gigazelle.github.io/cja-ttv/)로 조직에 대해 동적으로 생성된 업그레이드 단계를 계속 수행합니다.
