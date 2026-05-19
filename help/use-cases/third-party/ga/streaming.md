---
title: 스트리밍 Google Analytics 데이터 구성
description: Google 데이터 레이어를 Adobe Experience Platform으로 전송하는 구현을 설정하는 방법에 대해 알아봅니다.
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T09:49:39.181Z'
TQID: 'https://experienceleague.adobe.com/xav7bGdbGLjYXm70GJBSxnDMfNDZpYp5qij1IqkaZSY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 259
ht-degree: 90%

---

# 스트리밍 Google Analytics 데이터 구성

이 페이지에서는 라이브 Google Analytics 데이터를 Adobe Experience Platform에 수집한 다음 Customer Journey Analytics 내에 있는 데이터 보기에서 수집한 데이터 세트를 참조하는 방법에 중점을 두고 설명합니다. 이 페이지의 단계를 [Google Analytics 내역 데이터를 Adobe Experience Platform으로 수집](backfill.md)과 결합하여 내역 데이터를 포함하는 데이터 세트를 생성할 수 있습니다. 스트리밍 데이터 세트를 채우기 데이터 세트와 결합하여 Customer Journey Analytics의 지난 데이터 및 현재 데이터를 원활하게 볼 수 있습니다.

데이터 수집 구성에는 다음 단계가 포함됩니다.

1. [Adobe Experience Platform용 태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) 구현 구현 시작 및 운영에 대한 기본 사항은 [빠른 시작 안내서](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html)를 참조하십시오.
1. [Google 데이터 레이어 확장](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html) 설치 이 확장은 특히 Google 데이터 레이어에 맞게 설계된 Web SDK 확장 설치의 대안 역할을 합니다.
1. Adobe Experience Platform 데이터 수집에서 [데이터스트림 만들기](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) Adobe Experience Platform으로 데이터를 전송하는 데이터스트림 구성 현재 각 Google 데이터 레이어 오브젝트를 여기에 있는 해당 XDM 필드에 매핑해야 합니다. Adobe는 향후 이 매핑 워크플로를 단순화할 예정입니다.

원하는 태그를 사이트에 구현하고 게시하면 [연결 만들기](/help/connections/create-connection.md), [데이터 보기 만들기](/help/data-views/create-dataview.md)로 진행할 수 있습니다.
