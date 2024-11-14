---
title: Analytics 소스 커넥터 만들기 및 필드 매핑
description: Analytics 소스 커넥터를 만들고 필드를 매핑하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8e51e97b0616a5406c5c3a29431fde87a551ab9f
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 3%

---

# Analytics 소스 커넥터 만들기 및 필드 매핑

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

Analytics 소스 커넥터를 사용하여 Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform으로 가져올 수 있습니다. 그런 다음 이 데이터를 Customer Journey Analytics에서 내역 데이터로 사용할 수 있습니다.

다음 단계에서는 조직 및 사용하는 특정 Platform 응용 프로그램의 요구 사항에 맞게 조정된 간소화된 스키마를 원하므로 Customer Journey Analytics으로 업그레이드할 때 [XDM 스키마를 만들](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)이라고 가정합니다.

XDM 스키마를 만들면 내역 데이터에 사용할 Adobe Analytics 소스 커넥터를 만들어야 합니다.

소스 커넥터 만들기에 대한 포괄적인 일반 지침은 [UI에서 Adobe Analytics 소스 연결 만들기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)를 참조하십시오.

이전 데이터에 사용할 Adobe Analytics 소스 커넥터를 만들려면 다음 작업을 수행하십시오.

1. Platform UI의 왼쪽 레일의 **[!UICONTROL 연결]** 섹션에서 **[!UICONTROL 소스]**&#x200B;를 선택합니다.

1. [!UICONTROL 범주] 목록에서 **[!UICONTROL Adobe 애플리케이션]**&#x200B;을 선택합니다.

1. Adobe Analytics 타일에서 **[!UICONTROL 데이터 추가]**&#x200B;를 선택합니다.

   ![Adobe 응용 프로그램과 함께 소스가 선택된 Adobe Experience Platform 창 및 강조 표시된 데이터 추가](./assets/sources-overview.png)

1. **[!UICONTROL 보고서 세트]**&#x200B;를 선택한 다음 보고서 세트 목록에서 Customer Journey Analytics에 사용할 기록 데이터가 포함된 보고서 세트를 선택합니다.

   ![보고서 세트 목록을 표시하는 Adobe Experience Platform 창](./assets/report-suites.png)

1. 화면 오른쪽 상단에서 **[!UICONTROL 다음]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL 사용자 지정 스키마]**&#x200B;를 선택한 다음 [Adobe Analytics 필드 그룹을 포함하는 XDM 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)에서 만든 스키마를 선택합니다. <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. 각 Adobe Analytics 차원을 사용자 지정 XDM 스키마 차원에 매핑합니다.

   1. **[!UICONTROL 표준 필드 매핑]** 섹션에서 **[!UICONTROL 사용자 지정]** 탭을 선택합니다.

   1. **[!UICONTROL 새 매핑 추가]**&#x200B;를 선택합니다.

   ![스키마 필드 매핑](assets/schema-mapping.png)

   1. **[!UICONTROL Source 필드]**&#x200B;의 Adobe Analytics ExperienceEvent 템플릿 필드 그룹에서 Adobe Analytics 필드를 선택합니다. 그런 다음 **[!UICONTROL Target 필드]**&#x200B;에서 매핑할 XDM 필드를 선택합니다.

   1. Adobe Analytics에서 데이터를 수집하는 데 사용하는 Adobe Analytics ExperienceEvent 템플릿 필드 그룹의 각 필드에 대해 이 프로세스를 반복합니다.

1. 화면 오른쪽 상단에서 **[!UICONTROL 다음]**&#x200B;을(를) 선택합니다.

1. 데이터 흐름의 이름을 지정하고 (선택 사항) 설명을 제공합니다.

   ![데이터 흐름 세부 정보 섹션을 강조 표시하는 Adobe Experience Platform 창](./assets/dataflow-detail.png)

1. 화면 오른쪽 상단에서 **[!UICONTROL 다음]**&#x200B;을(를) 선택합니다.

1. 연결을 검토한 다음 **[!UICONTROL 마침]**&#x200B;을 선택합니다.

   ![검토를 위해 연결 및 데이터 형식 섹션을 강조 표시하는 Adobe Experience Platform 창](./assets/review.png)

   연결이 만들어지면 데이터 흐름이 자동으로 만들어져 데이터 세트를 보고서 세트의 Adobe Analytics 데이터로 채웁니다. 데이터 흐름은 프로덕션 샌드박스에 대해 최대 13개월의 내역 데이터를 수집합니다. 비프로덕션 샌드박스의 채우기 기간은 3개월로 제한됩니다.

   Analytics 소스 커넥터를 사용하여 내역 데이터를 Customer Journey Analytics 웹 SDK 구현으로 가져오는 경우 자동으로 생성된 이 데이터 세트를 웹 SDK 구현을 위해 만든 연결에 추가해야 합니다.

1. [권장된 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 [동적으로 생성된 업그레이드 단계](https://gigazelle.github.io/cja-ttv/)를 계속 따릅니다.




