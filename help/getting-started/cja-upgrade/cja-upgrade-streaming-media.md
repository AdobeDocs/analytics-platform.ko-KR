---
title: Customer Journey Analytics용 스트리밍 미디어 컬렉션 설정
description: Customer Journey Analytics용 스트리밍 미디어 컬렉션을 설정하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 68ce73ddf805ec377fdb2c539683507f191c9249
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# Customer Journey Analytics용 스트리밍 미디어 컬렉션 설정 {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Media Edge 설정 및 구현"
>abstract="Experience Platform Edge을 사용하여 Adobe에서 데이터를 사용할 수 있도록 Customer Journey Analytics 스트리밍 미디어 컬렉션을 구성할 수 있습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Customer Journey Analytics에서 스트리밍 미디어 컬렉션을 구현하는 단계는 Adobe Analytics의 현재 스트리밍 미디어 컬렉션 구현에 따라 다릅니다.

Streaming Media Collection은 다음 방법 중 하나로 Adobe Analytics에서 구현할 수 있습니다.

* [스트리밍 미디어 컬렉션을 위한 Edge Network 구현](#edge-network-implementations)

+++ 인포그래픽 보기

  ![Edge 구현에서 Streaming Media](assets/streaming-media-edge.png)

+++

* [스트리밍 미디어 컬렉션을 위한 Adobe Analytics 전용 구현](#adobe-analytics-only-implementations)

+++ 인포그래픽 보기

  ![Analytics 전용 구현](assets/analytics-implementation.png)

+++

이러한 구현 방법의 차이점에 대한 자세한 내용은 Streaming Media Collection Guide의 [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview)을 참조하십시오.

## 스트리밍 미디어 컬렉션을 위한 Edge Network 구현

Streaming Media Collection이 [Adobe Analytics 구현에서 Edge Network을 사용하여 구현됨](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods)인 경우, 이는 Streaming Media Collection을 Customer Journey Analytics으로 업그레이드하는 데 필요한 일부 단계가 Adobe Analytics 구현의 일부로 이미 완료되었음을 의미합니다. 다음은 완료된 단계입니다.

* [Adobe Experience Platform에서 스키마 설정](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Adobe Experience Platform에서 데이터 세트 만들기](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Adobe Experience Platform에서 데이터 스트림 구성](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

Customer Journey Analytics 업그레이드의 일부로 다음과 같은 추가 단계를 완료해야 합니다.

>[!NOTE]
>
>Customer Journey Analytics 업그레이드 단계를 완료할 때 Adobe Analytics의 스트리밍 미디어 컬렉션 구현에서 스키마, 데이터 세트 및 데이터 스트림을 사용해야 합니다.

* [Customer Journey Analytics에 연결 만들기](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Customer Journey Analytics에 데이터 보기 만들기](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## 스트리밍 미디어 컬렉션을 위한 Adobe Analytics 전용 구현

Streaming Media 컬렉션이 [Adobe Analytics 환경에서 Adobe Analytics 전용 구현을 사용하여 구현](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods)된 경우 이는 Streaming Media 데이터가 아직 Edge Network으로 이동하지 않음을 의미합니다.

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 과정의 일부로 스키마, 데이터 세트, 데이터스트림, 연결 및 데이터 보기를 만들 때 스트리밍 미디어 컬렉션 데이터를 처리하기 위해 다음과 같이 선택합니다.

* Customer Journey Analytics에 대한 스키마를 만들 때 `MediaAnalytics Interaction Details` 필드 그룹을 포함하십시오.

  이 필드 그룹 추가에 대한 자세한 내용은 Streaming Media Collection Guide의 [Adobe Experience Platform에서 스키마 설정](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)을 참조하십시오.

  스키마 만들기에 대한 자세한 내용은 [Customer Journey Analytics에서 사용할 사용자 지정 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)를 참조하십시오.

* Customer Journey Analytics에 대한 데이터스트림을 구성할 때 Media Analytics를 활성화합니다.

  이 옵션을 사용하는 방법에 대한 자세한 내용은 Streaming Media Collection Guide의 [Adobe Experience Platform에서 데이터 스트림 구성](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)을 참조하십시오.

  데이터 스트림 만들기에 대한 자세한 내용은 [Customer Journey Analytics에 사용할 데이터 스트림 만들기](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)를 참조하십시오.

* Customer Journey Analytics에 대한 데이터 보기를 만들 때 스트리밍 미디어 컬렉션에 대한 필수 스키마 필드를 포함하십시오.

  이러한 스키마 필드를 XDM 개체의 올바른 값에 매핑해야 합니다.

  필수 필드에 대한 자세한 내용은 Streaming Media Collection Guide의 [Customer Journey Analytics에서 데이터 보기 만들기](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)를 참조하십시오.

  데이터 보기를 만드는 방법에 대한 자세한 내용은 [Customer Journey Analytics에서 데이터 보기 만들기](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)를 참조하십시오.


