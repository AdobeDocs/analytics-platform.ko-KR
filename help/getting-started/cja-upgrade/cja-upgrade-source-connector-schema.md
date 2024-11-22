---
title: Analytics 소스 커넥터용 XDM 스키마 만들기
description: Analytics 소스 커넥터에 대한 XDM 스키마를 만드는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 8%

---

# Analytics 소스 커넥터용 XDM 스키마 만들기

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

## Analytics 소스 커넥터가 내역 데이터를 Customer Journey Analytics으로 가져오는 방법을 이해합니다

Analytics 소스 커넥터를 사용하여 Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform으로 가져올 수 있습니다. 그런 다음 이 데이터를 Customer Journey Analytics에서 내역 데이터로 사용할 수 있습니다.

이 프로세스에서는 조직의 요구 사항과 사용하는 특정 Platform 애플리케이션에 맞게 조정된 간소화된 스키마를 원하므로 [Customer Journey Analytics으로 업그레이드할 때 XDM 스키마를 생성](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)한다고 가정합니다.

Analytics 소스 커넥터를 사용하여 내역 데이터를 Customer Journey Analytics으로 가져오려면 다음을 수행해야 합니다.

1. 아래 설명된 대로 Analytics 소스 커넥터에 대한 XDM 스키마를 만듭니다.

1. Analytics 소스 커넥터가 없는 경우 [Analytics 소스 커넥터를 만들고 필드를 XDM 스키마에 매핑하십시오](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

   또는

   Analytics 소스 커넥터가 이미 있는 경우 [소스 커넥터의 필드를 XDM 스키마에 매핑](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)하십시오.

1. [연결에 Analytics 소스 커넥터 데이터 세트 추가](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Analytics 소스 커넥터용 XDM 스키마 만들기

Customer Journey Analytics에서 사용할 Experience Platform Web SDK 구현에 대해 이미 [새 XDM 스키마를 생성](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)했어야 합니다. 이 스키마에는 데이터를 수집하려는 필드에 대한 필드 그룹이 포함되어야 합니다.

이제 웹 SDK 스키마에서 이러한 동일한 필드 그룹을 사용하여 Analytics 소스 커넥터와 함께 사용할 수 있는 새 스키마에 추가해야 합니다.

Analytics 소스 커넥터에 대한 이 스키마에는 다음이 포함되어야 합니다.

* 웹 SDK 구현을 위해 만든 사용자 지정 스키마에 포함된 모든 필드 그룹(사용자가 만든 사용자 지정 필드 그룹 포함). (기본 필드 그룹에 속하지 않는 모든 사용자 지정 필드는 사용자 지정 필드 그룹의 일부로 웹 SDK 스키마에 추가했어야 합니다.)

* Adobe Analytics ExperienceEvent 템플릿 필드 그룹

Analytics 소스 커넥터와 함께 사용할 XDM 스키마를 만들려면 다음 작업을 수행하십시오.

1. [Customer Journey Analytics에 사용할 XDM 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)에 설명된 대로 Adobe Experience Platform에서 새 XDM 스키마를 만들기 시작합니다.

1. 웹 SDK 구현을 위해 만든 스키마에 포함된 모든 필드 그룹(사용자 정의 필드 그룹 포함)을 추가합니다.

1. 이러한 필드 그룹 추가를 완료한 후 Adobe Analytics ExperienceEvent 필드 그룹을 추가합니다.

   **[!UICONTROL 필드 그룹]** 섹션에서 **[!UICONTROL 추가]**&#x200B;를 선택하여 추가 필드 그룹을 추가합니다.

   ![스키마에 필드 그룹 추가](assets/schema-add-field-group.png)

1. **[!UICONTROL Adobe Analytics ExperienceEvent 템플릿]** 필드 그룹을 검색하여 선택하십시오.

   ![Adobe Analytics ExperienceEvent 필드 그룹 추가](assets/schema-experienceevent.png)

1. **[!UICONTROL 필드 그룹 추가]**&#x200B;를 선택합니다.

1. 스키마를 저장하려면 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

1. [권장된 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 [동적으로 생성된 업그레이드 단계](https://gigazelle.github.io/cja-ttv/)를 계속 따릅니다.
