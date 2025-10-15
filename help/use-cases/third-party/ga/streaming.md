---
title: 스트리밍 Google Analytics 데이터 구성
description: Google 데이터 레이어를 Adobe Experience Platform으로 전송하는 구현을 설정하는 방법에 대해 알아봅니다.
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
source-git-commit: 8262539078c57e32bc3195ef669325fa4889bea0
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 89%

---

# 스트리밍 Google Analytics 데이터 구성

이 페이지에서는 라이브 Google Analytics 데이터를 Adobe Experience Platform에 수집한 다음 Customer Journey Analytics 내에 있는 데이터 보기에서 수집한 데이터 세트를 참조하는 방법에 중점을 두고 설명합니다. 이 페이지의 단계를 [Google Analytics 내역 데이터를 Adobe Experience Platform으로 수집](backfill.md)과 결합하여 내역 데이터를 포함하는 데이터 세트를 생성할 수 있습니다. 스트리밍 데이터 세트를 채우기 데이터 세트와 결합하여 Customer Journey Analytics의 지난 데이터 및 현재 데이터를 원활하게 볼 수 있습니다.

데이터 수집 구성에는 다음 단계가 포함됩니다.

1. [Adobe Experience Platform용 태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) 구현 구현 시작 및 운영에 대한 기본 사항은 [빠른 시작 안내서](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html)를 참조하십시오.
1. [Google 데이터 레이어 확장](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html) 설치 이 확장은 특히 Google 데이터 레이어에 맞게 설계된 Web SDK 확장 설치의 대안 역할을 합니다.
1. Adobe Experience Platform 데이터 수집에서 [데이터스트림 만들기](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) Adobe Experience Platform으로 데이터를 전송하는 데이터스트림 구성 현재 각 Google 데이터 레이어 오브젝트를 여기에 있는 해당 XDM 필드에 매핑해야 합니다. Adobe는 향후 이 매핑 워크플로를 단순화할 예정입니다.

원하는 태그를 사이트에 구현하고 게시하면 [연결 만들기](/help/connections/create-connection.md), [데이터 보기 만들기](/help/data-views/create-dataview.md)로 진행할 수 있습니다.
