---
title: Adobe Experience Platform으로 스트리밍 Google Analytics 데이터 구성
description: Google 데이터 레이어를 Adobe Experience Platform에 보내도록 구현을 설정하는 방법을 알아봅니다
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# Adobe Experience Platform으로 스트리밍 Google Analytics 데이터 구성

이 페이지에서는 라이브 Google Analytics 데이터를 Adobe Experience Platform에 수집하는 방법에 중점을 두어 Customer Journey Analytics 내의 데이터 보기에서 해당 데이터 세트를 참조할 수 있도록 합니다. 이 페이지의 단계를 [Google Analytics 내역 데이터를 Adobe Experience Platform에 수집](backfill.md): 이전 데이터가 포함된 데이터 세트를 생성합니다. 스트리밍 데이터 세트와 채우기 데이터 세트를 결합하여 과거의 원활한 보기와 Customer Journey Analytics에 데이터를 표시할 수 있습니다.

데이터 수집 구성에 다음 단계가 포함됩니다.

1. 구현 [Adobe Experience Platform용 태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html). 자세한 내용은 [빠른 시작 안내서](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) 를 클릭하여 기본 구현을 시작하고 실행합니다.
1. 설치 [Google 데이터 레이어 확장](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). 이 확장은 특히 Google 데이터 계층에 초점을 맞춘 Web SDK 확장 프로그램을 설치하는 대신 작동합니다.
1. [데이터 스트림 만들기](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) ( Adobe Experience Platform 데이터 수집). Adobe Experience Platform으로 데이터를 보내도록 데이터 스트림을 구성합니다. 현재 각 Google 데이터 계층 개체를 여기에서 적용 가능한 XDM 필드에 매핑해야 합니다. Adobe은 향후 이 매핑 워크플로우를 간소화할 계획입니다.

사이트에서 원하는 태그를 구현하고 게시하면 다음 작업을 진행할 수 있습니다 [연결 만들기](/help/connections/create-connection.md), 그런 다음 [데이터 보기 만들기](/help/data-views/create-dataview.md).
