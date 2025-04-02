---
title: Customer Journey Analytics용 스트리밍 미디어 컬렉션 설정
description: Customer Journey Analytics용 스트리밍 미디어 컬렉션을 설정하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b807099d-a61d-48f9-9fec-94ecc6b76213
source-git-commit: 380ed5c9ee0c21ea9855a41728afec040637ce65
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 20%

---

# Customer Journey Analytics용 스트리밍 미디어 컬렉션 설정 {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Media Edge 설정 및 구현"
>abstract="스트리밍 미디어 컬렉션을 Customer Journey Analytics와 함께 사용하려면 업그레이드 프로세스의 특정 단계에서 특정 작업을 수행해야 합니다. 예를 들어 스키마에 MediaAnalytics 인터랙션 세부 정보 필드 그룹을 추가하고 데이터스트림에서 Media Analytics를 활성화하는 등의 작업이 필요합니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe Analytics과 마찬가지로 스트리밍 미디어 컬렉션을 사용하여 Customer Journey Analytics에서 사용할 스트리밍 미디어 데이터를 수집할 수 있습니다. Adobe Analytics에서 스트리밍 미디어 컬렉션을 사용하는 경우 Customer Journey Analytics 업그레이드 계획에 이를 포함해야 합니다.

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 단계를 진행할 때 스트리밍 미디어 컬렉션 데이터를 설명하기 위해 다음과 같이 선택합니다.

* Customer Journey Analytics에 대한 스키마를 만들 때 `MediaAnalytics Interaction Details` 필드 그룹을 포함하십시오.

  이 필드 그룹 추가에 대한 자세한 내용은 Streaming Media Collection Guide의 [Adobe Experience Platform에서 스키마 설정](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)을 참조하십시오.

  스키마 만들기에 대한 자세한 내용은 [Customer Journey Analytics에서 사용할 사용자 지정 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)를 참조하십시오.

* Customer Journey Analytics에 대한 데이터스트림을 구성할 때 Media Analytics를 활성화합니다.

  이 옵션을 사용하는 방법에 대한 자세한 내용은 Streaming Media Collection Guide의 [Adobe Experience Platform에서 데이터 스트림 구성](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)을 참조하십시오.

  데이터 스트림 만들기에 대한 자세한 내용은 [Customer Journey Analytics에 사용할 데이터 스트림 만들기](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)를 참조하십시오.

  >[!NOTE]
  >
  >Adobe Analytics 구현에서 이미 Experience Platform Web SDK을 사용 중인 경우 이 단계는 필요하지 않습니다.

* Customer Journey Analytics에 대한 데이터 보기를 만들 때 스트리밍 미디어 컬렉션에 대한 필수 스키마 필드를 포함하십시오.

  이러한 스키마 필드를 XDM 개체의 올바른 값에 매핑해야 합니다.

  필수 필드에 대한 자세한 내용은 Streaming Media Collection Guide의 [Customer Journey Analytics에서 데이터 보기 만들기](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)를 참조하십시오.

  데이터 보기를 만드는 방법에 대한 자세한 내용은 [Customer Journey Analytics에서 데이터 보기 만들기](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)를 참조하십시오.

<!--

------------------

The steps for implementing the Streaming Media Collection in Customer Journey Analytics differ depending on your current Streaming Media Collection implementation in Adobe Analytics. 

Streaming Media Collection can be implemented in Adobe Analytics in either of the following ways:

* [Edge Network implementations for the Streaming Media Collection](#edge-network-implementations)

* [Adobe Analytics-only implementations for the Streaming Media Collection](#adobe-analytics-only-implementations)

For more information about the differences between these implementation methods, see [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) in the Streaming Media Collection Guide.

## Edge Network implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using the Edge Network in your Adobe Analytics implementation](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), this means that some steps that are required to upgrade the Streaming Media Collection to Customer Journey Analytics have already been completed as part of your Adobe Analytics implementation. Following are the completed steps:

* [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Create a dataset in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

The following additional steps need to be completed as part of the upgrade to Customer Journey Analytics:

>[!NOTE]
>
>As you complete the Customer Journey Analytics upgrade steps, make sure you use the schema, dataset, and datastream from your Streaming Media Collection implementation in Adobe Analytics.

* [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Adobe Analytics-only implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using an Adobe Analytics-only implementation in your Adobe Analytics environment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), this means that Streaming Media data is not yet going to Edge Network. 

As you create the schema, dataset, datastream, connection, and data view as part of your upgrade from Adobe Analytics to Customer Journey Analytics, make the following selections to account for Streaming Media Collection data:

* When creating the schema for Customer Journey Analytics, include the `MediaAnalytics Interaction Details` field group.

  For more information about adding this field group, see [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the schema, see [Create a custom schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* When configuring the datastream for Customer Journey Analytics, enable Media Analytics. 

  For more information about enabling this option, see [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the datastream, see [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* When creating a data view for Customer Journey Analytics, include the required schema fields for the Streaming Media Collection.

  Make sure you map these schema fieldds to the correct values in the XDM object.

  For more information about the required fields, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) in the Streaming Media Collection Guide.

  For information about creating the data view, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

  -->
