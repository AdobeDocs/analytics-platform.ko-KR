---
title: Analytics 소스 커넥터 및 맵 필드 만들기
description: Analytics 소스 커넥터를 만들고 필드를 매핑하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 24%

---

# Analytics 소스 커넥터 및 맵 필드 만들기 {#create-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create"
>title="Analytics 소스 커넥터 만들기"
>abstract="Analytics 소스 커넥터를 사용하여 Customer Journey Analytics에 사용할 보고서 모음 데이터를 수집합니다.<br><br>기본 설정으로 Analytics 소스 커넥터를 만들면 몇 분밖에 걸리지 않습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-map-fields"
>title="Analytics 소스 커넥터 및 맵 스키마 필드 만들기"
>abstract="소스 커넥터는 Adobe Analytics 필드를 조직의 스키마에 매핑하는 방법을 알아야 합니다. 이 인터페이스를 사용하여 소스 커넥터에 해당 매핑을 제공합니다. 이 단계는 Customer Journey Analytics에 과거 데이터를 추가하는 과정의 일부입니다.<br><br>이 단계가 걸리는 시간은 매핑해야 하는 차원과 지표의 수에 따라 크게 달라집니다. 이 단계는 지루하고 반복적인 만큼 어렵지 않습니다. 데이터 스트림 매핑을 완료하는 데 약 일주일 정도 걸릴 것으로 예상됩니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Analytics 소스 커넥터가 내역 데이터를 Customer Journey Analytics으로 가져오는 방법을 이해합니다

Analytics 소스 커넥터를 사용하여 Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform으로 가져올 수 있습니다. 그런 다음 이 데이터를 Customer Journey Analytics에서 내역 데이터로 사용할 수 있습니다.

이 프로세스에서는 조직 및 사용하는 특정 Platform 응용 프로그램의 요구 사항에 맞게 조정된 간소화된 스키마를 원하므로 [Customer Journey Analytics Web SDK 구현에 사용할 사용자 지정 스키마를 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)하려고 하는 것으로 가정합니다.

Analytics 소스 커넥터를 사용하여 내역 데이터를 Customer Journey Analytics으로 가져오려면 다음을 수행해야 합니다.

1. [Analytics 소스 커넥터용 사용자 정의 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. Analytics 소스 커넥터가 없는 경우 아래 설명된 대로 Analytics 소스 커넥터를 만들고 필드를 사용자 지정 웹 SDK 스키마에 매핑합니다.

   또는

   Analytics 소스 커넥터가 이미 있는 경우 [소스 커넥터의 필드를 사용자 지정 웹 SDK 스키마에 매핑](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)하십시오.

1. [연결에 Analytics 소스 커넥터 데이터 세트 추가](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## Analytics 소스 커넥터 및 맵 필드 만들기

사용자 지정 스키마를 만들면 내역 데이터에 사용할 Adobe Analytics 소스 커넥터를 만들어야 합니다. (소스 커넥터 만들기에 대한 포괄적인 일반 지침은 [UI에서 Adobe Analytics 소스 연결 만들기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)를 참조하십시오.)

이전 데이터에 사용할 Adobe Analytics 소스 커넥터를 만들려면 다음 작업을 수행하십시오.

1. Platform UI의 왼쪽 레일의 **[!UICONTROL 연결]** 섹션에서 **[!UICONTROL 소스]**&#x200B;를 선택합니다.

1. [!UICONTROL 범주] 목록에서 **[!UICONTROL Adobe 애플리케이션]**&#x200B;을 선택합니다.

1. Adobe Analytics 타일에서 **[!UICONTROL 데이터 추가]**&#x200B;를 선택합니다.

   ![Adobe 응용 프로그램과 함께 소스가 선택된 Adobe Experience Platform 창 및 강조 표시된 데이터 추가](./assets/sources-overview.png)

1. **[!UICONTROL 보고서 세트]**&#x200B;를 선택한 다음 보고서 세트 목록에서 Customer Journey Analytics에서 사용할 내역 데이터가 포함된 보고서 세트를 선택합니다.

   ![보고서 세트 목록을 표시하는 Adobe Experience Platform 창](./assets/report-suites.png)

1. 화면 오른쪽 상단에서 **[!UICONTROL 다음]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL 사용자 지정 스키마]**&#x200B;를 선택한 다음 [Adobe Analytics 필드 그룹을 포함하는 사용자 지정 스키마를 만들기](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)에서 만든 스키마를 선택합니다. <!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. 각 Adobe Analytics 차원을 사용자 지정 스키마 차원에 매핑합니다.

   1. **[!UICONTROL 표준 필드 매핑]** 섹션에서 **[!UICONTROL 사용자 지정]** 탭을 선택합니다.

   1. **[!UICONTROL 새 매핑 추가]**&#x200B;를 선택합니다.

   ![스키마 필드 매핑](assets/schema-mapping.png)

   1. **[!UICONTROL Source 필드]**&#x200B;의 Adobe Analytics ExperienceEvent 템플릿 필드 그룹에서 Adobe Analytics 필드를 선택합니다. 그런 다음 **[!UICONTROL Target 필드]**&#x200B;에서 매핑할 XDM 스키마의 사용자 지정 필드를 선택합니다.

      AppMeasurement과 XDM 간의 고유한 아키텍처 차이로 인해 모든 Adobe Analytics 필드에 XDM의 해당 필드가 있는 것은 아닙니다.

   1. Adobe Analytics에서 데이터를 수집하는 데 사용하는 Adobe Analytics ExperienceEvent 템플릿 필드 그룹의 각 필드에 대해 이 프로세스를 반복합니다.

1. 화면 오른쪽 상단에서 **[!UICONTROL 다음]**&#x200B;을(를) 선택합니다.

1. 데이터 흐름의 이름을 지정하고 (선택 사항) 설명을 제공합니다.

   ![데이터 흐름 세부 정보 섹션을 강조 표시하는 Adobe Experience Platform 창](./assets/dataflow-detail.png)

1. 화면 오른쪽 상단에서 **[!UICONTROL 다음]**&#x200B;을(를) 선택합니다.

1. 연결을 검토한 다음 **[!UICONTROL 마침]**&#x200B;을 선택합니다.

   ![검토를 위해 연결 및 데이터 형식 섹션을 강조 표시하는 Adobe Experience Platform 창](./assets/review.png)

   연결이 만들어지면 데이터 흐름이 자동으로 만들어져 데이터 세트를 보고서 세트의 Adobe Analytics 데이터로 채웁니다. 데이터 흐름은 프로덕션 샌드박스에 대해 최대 13개월의 내역 데이터를 수집합니다. 비프로덕션 샌드박스의 채우기 기간은 3개월로 제한됩니다.

   Analytics 소스 커넥터를 사용하여 이전 데이터를 Customer Journey Analytics Web SDK 구현으로 가져오는 경우, 자동으로 생성된 이 데이터 세트를 웹 SDK 구현을 위해 만든 연결에 추가해야 합니다.

{{upgrade-final-step}}
