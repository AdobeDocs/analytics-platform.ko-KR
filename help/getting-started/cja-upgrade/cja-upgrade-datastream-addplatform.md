---
title: Customer Journey Analytics를 위한 스키마 만들기
description: Adobe Analytics에서 Customer Journey Analytics로 업그레이드할 때 권장되는 경로 자세히 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 100%

---

# 데이터스트림에 서비스로 Platform 추가 {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="데이터스트림에 서비스로 Adobe Experience Platform 추가"
>abstract="데이터스트림에 데이터를 전송하려면 하나 이상의 서비스가 필요합니다. 데이터스트림에 서비스로 Adobe Experience Platform을 설정합니다.<br><br>데이터스트림에 서비스를 추가하는 것은 간단하며 완료까지 몇 분밖에 걸리지 않습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

이 섹션의 단계를 완료하기 전에 이미 데이터스트림이 존재해야 합니다. 데이터스트림이 생성된 시기와 방법은 다음과 같이 Adobe Analytics 구현에 따라 달라집니다.

* Adobe Analytics 구현에서 Web SDK 또는 Web SDK 확장 기능을 사용하는 경우, 데이터스트림은 업그레이드 프로세스 이전에 Adobe Analytics 환경에서 사용할 수 있었습니다.

* 다른 Adobe Analytics 구현의 경우, [Customer Journey Analytics에 사용할 데이터스트림 만들기](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)에 설명된 대로 데이터스트림 만들기는 업그레이드 프로세스의 일부입니다.

데이터스트림을 사용할 수 있으므로 Platform as a Service를 추가해야 합니다.

1. 왼쪽 레일의 Adobe Experience Platform UI에서 [!UICONTROL 데이터 수집]의 **[!UICONTROL 데이터스트림]**&#x200B;을 선택합니다.

1. 이전에 구성된 데이터스트림을 선택합니다. <!--true?-->

1. **[!UICONTROL 서비스 추가]**&#x200B;를 선택합니다.

1. [!UICONTROL 서비스 추가 화면]에서:

   1. [!UICONTROL 서비스] 목록에서 **[!UICONTROL Adobe Experience Platform]**&#x200B;을 선택합니다.

   1. **[!UICONTROL 활성화됨]**&#x200B;이 선택되었는지 확인합니다.

   1. [!UICONTROL 이벤트 데이터 세트] 목록에서 데이터 세트를 선택합니다.

      ![데이터스트림 AEP 서비스](./assets/datastream-aep-service.png)

   1. 다른 설정을 종료하고 **[!UICONTROL 저장]**&#x200B;을 선택하여 데이터스트림을 저장합니다.

   이제 데이터스트림을 구성하여 웹 사이트에서 수집한 데이터를 Adobe Experience Platform의 데이터 세트로 전달합니다.

   데이터스트림을 구성하는 방법과 민감한 데이터를 처리하는 방법에 대한 자세한 내용은 [데이터스트림 개요](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html)를 참조하십시오.

{{upgrade-final-step}}
