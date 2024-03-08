---
title: Marketo Engage 데이터를 Adobe Experience Platform에 수집하고 Customer Journey Analytics에서 보고합니다.
description: Marketo Engage 데이터를 Customer Journey Analytics으로 가져오는 방법 알아보기
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 57%

---

# Marketo Engage 데이터를 Adobe Experience Platform에 수집하고 Customer Journey Analytics에서 보고합니다.

Adobe Experience Platform(Adobe Experience Platform)에서 새로 사용할 수 있는 Marketo Engage 데이터 세트를 활용하여 B2B 마케터에게 중요한 분석 및 보고 솔루션을 제공할 수 있습니다. 그런 다음 Adobe Customer Journey Analytics에서 이러한 데이터 세트에 대해 보고합니다.

## 1단계: Marketo 소스 데이터 필드를 XDM 대상에 매핑

[사용자](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#persons) 및 [활동](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#activities) 오브젝트를 해당 XDM 스키마 대상 필드에 매핑합니다.

## 2단계: Marketo 데이터를 Adobe Experience Platform에 수집

[Marketo Engage 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html)를 사용하여 Marketo에서 Experience Platform으로 데이터를 가져오고 Platform 연결 애플리케이션을 사용하여 이 데이터를 최신 상태로 유지하십시오.

## 3단계: Customer Journey Analytics에서 이 데이터 세트에 대한 연결 설정

Experience Platform 데이터 세트에 대해 보고하려면 먼저 Experience Platform과 Customer Journey Analytics의 데이터 세트 간에 연결을 설정해야 합니다. 자세한 내용은 을 참조하십시오 [연결 만들기 또는 편집](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html).

## 4단계: 하나 이상의 데이터 보기 만들기

[데이터 보기](/help/data-views/data-views.md)는 Customer Journey Analytics와 관련된 컨테이너입니다. 이를 통해 연결에서 데이터를 해석하는 방법을 결정할 수 있습니다. Analysis Workspace에서 사용할 가능한 모든 차원과 지표(이 경우 Marketo와 관련된 지표 및 차원)를 지정합니다. 또한 해당 차원과 지표가 데이터를 얻을 수 있는 열을 지정합니다. 데이터 보기는 Analysis Workspace의 데이터에 대한 보고 준비에 따라 정의됩니다.

## 5단계: Analysis Workspace에서 보고

탐색할 수 있는 한 가지 사용 사례는 다음과 같습니다. 2020년 4월~6월에 리드별 웹 페이지 방문 횟수는?

1. [Analytics Workspace](/help/analysis-workspace/home.md)를 열고 새 프로젝트를 만듭니다.
B2B/B2P CDP를 보유한 고객은 Customer Journey Analytics에서 B2C 스타일의 분석을 수행할 수 있습니다. B2B 오브젝트는 아직 사용할 수 없습니다.

1. 다음과 같이 웹 페이지 조회수에 대한 [필터](/help/components/filters/create-filters.md)를 만듭니다. 이벤트 유형 = web.webpagedetails.pageViews :

   ![이벤트 및 이벤트 유형을 표시하는 정의 창](../assets/marketo-filter.png)

1. 자유 형식 테이블에서 생성한 필터(웹 페이지 조회수)를 가져온 다음 월 날짜 범위를 가져옵니다. 이렇게 하면 매월 리드별 웹 페이지 방문 횟수를 확인할 수 있습니다.

   ![월별 이벤트를 보여 주는 자유 형식 테이블.](../assets/marketo-freeform.png)

1. 또는 개인 키 또는 직장 이메일 주소 차원을 가져옵니다. 이렇게 하면 각 리드의 웹 페이지 방문 횟수를 확인할 수 있습니다.

   ![이벤트 및 workEmail.Address와 웹 페이지 조회수를 보여 주는 자유 형식 테이블입니다.](../assets/marketo-freeform2.png)
