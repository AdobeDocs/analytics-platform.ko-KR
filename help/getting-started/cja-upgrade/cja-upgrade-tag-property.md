---
title: 태그 속성을 만들고 웹 SDK 확장 추가
description: 태그 속성을 만들고 웹 SDK 확장을 추가하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 45%

---

# 속성용 태그 만들기 {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="Adobe Experience Platform 데이터 수집에 태그 속성 만들기"
>abstract="태그 사용은 데이터 수집의 일반적인 표준입니다. Adobe Experience Platform 인터페이스에 태그를 만들면 언제든지 데이터 수집 변수를 업데이트할 수 있습니다.<br><br>태그 속성 생성은 클릭 몇 번만으로 완료할 수 있으며, 몇 분 밖에 걸리지 않습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Experience Platform 내의 태그 기능을 사용하여 사이트에서 코드를 구현하여 데이터를 수집할 수 있습니다. 이는 다른 태그 지정 요구 사항과 함께 코드를 배포할 수 있도록 해 주는 태그 관리 솔루션입니다. 태그는 Adobe Experience Platform Web SDK 확장을 사용하여 Adobe Experience Platform과 원활하게 통합할 수 있도록 해 줍니다.

다음 정보는 속성에 대한 태그를 만드는 방법을 설명합니다. 자세한 내용은 Experience Platform 설명서에서 [웹 SDK 태그 확장 구성](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)을 참조하십시오. 웹 SDK에는 기본적으로 [!UICONTROL Adobe Experience Cloud ID 서비스]가 포함되어 있으므로 태그에 ID 서비스 확장을 추가할 필요가 없습니다.

속성은 사이트에 태그를 배포할 때 기본적으로 확장, 규칙, 데이터 요소 및 라이브러리로 채우는 컨테이너입니다. 많은 사람들이 동일한 태그 세트를 배포하려는 각 웹 사이트(또는 밀접하게 관련된 사이트 그룹)에 대한 속성을 만듭니다. 속성에 대한 자세한 내용은 Experience Platform 데이터 수집 설명서에서 [속성](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties)을 참조하십시오.

속성에 대한 태그를 만들려면 다음을 수행하십시오.

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. **[!UICONTROL 새 속성]**&#x200B;을 선택합니다.

   태그 이름을 지정하고 **[!UICONTROL 웹]**&#x200B;을 선택한 다음 도메인 이름을 입력합니다. 계속하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

   ![속성 만들기](assets/create-property.png)

{{upgrade-final-step}}
