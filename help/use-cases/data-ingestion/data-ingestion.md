---
title: Customer Journey Analytics의 데이터 수집 옵션
description: 데이터를 Customer Journey Analytics로 수집할 수 있는 다양한 방법 이해
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 89%

---

# Customer Journey Analytics의 데이터 수집 옵션

데이터를 Customer Journey Analytics로 수집하는 방법은 여러 가지가 있습니다. 일부 고객은 기존 Adobe Analytics 데이터를 이전하려는 것으로 간주하며 일부는 Adobe Experience Platform에서 직접 데이터를 수집한다고 가정합니다. 이 참조는 보다 자세한 정보에 대한 링크를 포함하여 따라야 할 고급 단계를 제공합니다.

## 기존 Adobe Analytics에서 데이터 수집

이 워크플로는 Analytics 소스 커넥터를 사용하며, 태그 관리자로 DTM을 사용하는지 또는 Launch를 사용하는지에 따라 달라집니다.

### Adobe Experience Platform(이전에는 [!UICONTROL Launch]라고 불렀음)의 태그를 통해

1. 아직 수행하지 않았다면 [데이터 레이어를 만듭니다](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=ko-KR). 데이터 계층은 구현에 사용된 모든 변수 값을 포함하는 사이트의 JavaScript 오브젝트의 프레임워크로서, 구현을 보다 세밀하게 제어하고 쉽게 유지 관리할 수 있습니다.
1. 아직 수행하지 않았다면 데이터 수집을 위해 사이트에서 코드를 구현하도록 [Adobe Experience Platform 태그](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=ko-KR)를 사용합니다. 이는 다른 태그 지정 요구 사항과 함께 Analytics 코드를 배포할 수 있도록 해 주는 태그 관리 솔루션입니다. 태그는 다른 솔루션 및 제품과의 통합을 제공하며 사용자 정의 코드를 배포할 수 있도록 해 줍니다. 따라서 사이트에서 코드를 업데이트하기 위해 조직의 개발 팀에 의존하지 않고도 이러한 모든 작업을 수행할 수 있습니다.
1. Adobe Experience Platform에서 [Adobe Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko-KR)를 만듭니다. 이 소스 커넥터는 Analytics 데이터를 [XDM(Experience Data Model) 시스템](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko-KR)이라는 표준화된 프레임워크에서 Experience Platform에 수집합니다. 또한 [Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 활용](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)을 참조하십시오.
1. 채널 간 보고를 알리는 하나 이상의 연결 및 데이터 보기를 만들려면[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ko-KR)를 사용합니다.

## Adobe Experience Platform Web SDK 및 Edge Network를 통해 데이터 수집

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)는 Adobe Experience Cloud 고객이 Adobe Experience Platform Edge Network를 통해 Experience Cloud에서 다양한 서비스와 상호 작용할 수 있도록 하는 클라이언트측 JavaScript 라이브러리입니다.

1. [태그에서 Adobe Experience Platform 웹 SDK 확장 구성](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) 웹 속성에서 Adobe Experience Platform Edge Network를 통해 Adobe Experience Cloud으로 데이터를 전송합니다.
1. 채널 간 보고를 알리는 하나 이상의 [연결](/help/connections/create-connection.md) 및 [데이터 보기](/help/data-views/data-views.md)를 만들려면 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html)를 사용합니다.

## 일괄 처리 수집 및 스트리밍 수집을 통한 데이터 수집

Adobe Experience Platform은 마케터가 고객의 행동을 더 잘 이해할 수 있도록 여러 소스의 데이터를 함께 가져옵니다. Adobe Experience Platform 데이터 수집은 플랫폼이 이러한 소스에서 데이터를 수집하는 여러 방법과 다운스트림 플랫폼 서비스에서 사용하기 위해 Data Lake 내에서 데이터가 지속되는 방법을 나타냅니다.

### 일괄 처리 수집

1. 데이터를 Adobe Experience Platform에 일괄 처리 파일로 수집할 수 있도록 [일괄 처리 수집](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html#batch)을 설정합니다. 수집되는 데이터는 CRM 시스템의 플랫 파일(예: Parquet 파일)의 프로필 데이터이거나 Experience Data Model(XDM) 레지스트리의 알려진 스키마를 준수하는 데이터일 수 있습니다.
1. 채널 간 보고를 알리는 하나 이상의 [연결](/help/connections/create-connection.md) 및 [데이터 보기](/help/data-views/data-views.md)를 만들려면 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html)를 사용합니다.

### 스트리밍 수집

1. [스트리밍 수집](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html#streaming)을 설정하여 클라이언트 및 서버측 디바이스에서 실시간으로 Experience Platform으로 데이터를 전송합니다.
1. 채널 간 보고를 알리는 하나 이상의 [연결](/help/connections/create-connection.md) 및 [데이터 보기](/help/data-views/data-views.md)를 만들려면 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html)를 사용합니다.

## Customer Journey Analytics에서 분석할 Google Analytics 데이터 가져오기

[Customer Journey Analytics를 이용하여 Google Analytics 데이터 분석](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html)을 수행하는 방법에 대한 튜토리얼을 참조하여 자세한 단계를 검토하십시오.

## 대량 데이터 삽입 API를 사용하여 데이터를 Analytics로 가져온 다음 Experience Platform에서 Analytics 소스 커넥터를 통해 수집하십시오

1. [대량 데이터 삽입 API를 사용](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)하여 서버측 컬렉션 데이터를 Adobe Analytics에 제출합니다. 이벤트 데이터를 포함하는 CSV 형식의 파일을 제출할 수 있습니다.
1. [Adobe Analytics 소스 커넥터 만들기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)를 통해 해당 소비자 데이터를 Adobe Experience Platform으로 가져옵니다.
1. 채널 간 보고를 알리는 하나 이상의 [연결](/help/connections/create-connection.md) 및 [데이터 보기](/help/data-views/data-views.md)를 만들려면 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ko-KR)를 사용합니다.
