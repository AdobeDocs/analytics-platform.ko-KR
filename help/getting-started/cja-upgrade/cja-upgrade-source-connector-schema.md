---
title: Analytics 소스 커넥터용 사용자 정의 스키마 만들기
description: Analytics 소스 커넥터용 사용자 정의 스키마를 만드는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 100%

---

# Analytics 소스 커넥터용 사용자 정의 스키마 만들기 {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="Analytics 소스 커넥터용 스키마 만들기"
>abstract="이 스키마는 Adobe Analytics ExperienceEvent 필드 그룹과 조직의 사용자 정의 스키마를 구성하는 모든 필드 그룹을 결합한 것입니다. Analytics 소스 커넥터에서 사용하는 필드를 조직의 스키마에 매핑할 수 있으며, 과거 데이터에만 사용됩니다.<br><br>기술적인 측면에서 이 스키마를 만드는 작업은 몇 시간 안에 완료될 수 있으며, 조직의 사용자 정의 스키마를 구성하는 필드 그룹을 정확히 알고 있다면 더 빠를 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-historical"
>title="내역 데이터에 대한 Analytics 소스 커넥터 만들기"
>abstract="Analytics 소스 커넥터를 사용하여 Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform으로 가져올 수 있습니다. 이러한 데이터는 Customer Journey Analytics에서 내역 데이터로 사용될 수 있습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Analytics 소스 커넥터가 내역 데이터를 Customer Journey Analytics로 가져오는 방식 파악

Analytics 소스 커넥터를 사용하여 Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform으로 가져올 수 있습니다. 이러한 데이터는 Customer Journey Analytics에서 내역 데이터로 사용될 수 있습니다.

이 프로세스는 조직의 요구와 사용하는 특정 Platform 애플리케이션에 맞춘 간소화된 스키마가 필요하기 때문에 [Customer Journey Analytics Web SDK 구현에 사용할 사용자 정의 스키마를 만들고자](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) 한다고 가정합니다.

Analytics 소스 커넥터를 사용하여 내역 데이터를 Customer Journey Analytics로 가져오려면 다음 작업을 수행해야 합니다.

1. 아래 설명한 대로 Analytics 소스 커넥터용 사용자 정의 스키마를 만듭니다.

1. 아직 Analytics 소스 커넥터가 없는 경우 [Analytics 소스 커넥터를 생성하고 필드를 사용자 정의 스키마에 매핑](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)합니다.

   또는

   이미 Analytics 소스 커넥터가 있는 경우 [소스 커넥터에서 XDM 스키마로 필드를 매핑](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)합니다.

1. [연결에 Analytics 소스 커넥터 데이터 세트 추가](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Analytics 소스 커넥터용 사용자 정의 스키마 만들기

Customer Journey Analytics와 함께 사용할 Experience Platform Web SDK 구현을 위한 [새로운 사용자 정의 스키마를 이미 생성](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)했어야 합니다. 이 스키마에는 데이터를 수집하려는 필드에 대한 필드 그룹이 포함되어야 합니다.

이제 Web SDK 스키마에서 동일한 필드 그룹을 사용하여 Analytics 소스 커넥터와 함께 사용할 수 있는 새 스키마에 추가해야 합니다.

Analytics 소스 커넥터에 대한 이 스키마에는 다음이 포함되어야 합니다.

* Web SDK 구현을 위해 만든 사용자 정의 스키마에 포함된 모든 필드 그룹(사용자 정의 필드 그룹 포함). (기본 필드 그룹에 속하지 않은 모든 사용자 정의 필드는 사용자 정의 필드 그룹의 일부로 Web SDK 스키마에 추가되어야 합니다.)

* Adobe Analytics ExperienceEvent 템플릿 필드 그룹

Analytics 소스 커넥터와 함께 사용할 사용자 정의 스키마 만드는 방법:

1. Adobe Experience Platform에서 [Customer Journey Analytics Web SDK 구현에 사용할 사용자 정의 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)에 설명된 대로 새 사용자 정의 스키마를 만듭니다.

1. Web SDK 구현을 위해 만든 스키마에 포함된 모든 필드 그룹(사용자 정의 필드 그룹 포함)을 추가합니다.

1. 이러한 필드 그룹을 추가한 후 Adobe Analytics ExperienceEvent 필드 그룹을 추가합니다.

   **[!UICONTROL 필드 그룹]** 섹션에서 **[!UICONTROL 추가]**&#x200B;를 선택하여 필드 그룹을 추가합니다.

   ![스키마에 필드 그룹 추가](assets/schema-add-field-group.png)

1. **[!UICONTROL Adobe Analytics ExperienceEvent 템플릿]** 필드 그룹을 검색해 선택합니다.

   ![Adobe Analytics ExperienceEvent 필드 그룹 추가](assets/schema-experienceevent.png)

1. **[!UICONTROL 필드 그룹 추가]**&#x200B;를 선택합니다.

1. 스키마를 저장하려면 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

{{upgrade-final-step}}
