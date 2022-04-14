---
title: B2B 데이터를 AEP에 수집하고 CJA에서 보고합니다
description: Marketo 데이터를 CJA로 가져오는 방법을 알아봅니다
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: e18de2563427941f8c227881b46f73c490be218d
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 5%

---


# Marketo B2B 데이터를 AEP에 수집하고 CJA에서 보고합니다

AEP(Adobe Experience Platform)에서 새로 사용할 수 있는 Marketo B2B 데이터 세트를 활용하여 B2B 마케터에게 중요한 분석 및 보고 솔루션을 제공할 수 있습니다. 그런 다음 Customer Journey Analytics(CJA)에서 이러한 데이터 세트에 대해 보고합니다.

## 1단계: Marketo 소스 데이터 필드를 XDM 대상에 매핑

맵 [사람](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#persons) 및 [활동](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#activities) 대상 필드를 지정합니다.

## 2단계: AEP에 Marketo 데이터 수집

를 사용하십시오 [Marketo Engage 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=en) 플랫폼 연결 애플리케이션을 사용하여 B2B 데이터를 Marketo에서 Experience Platform으로 가져오고 이 데이터를 최신 상태로 유지할 수 있습니다.

## 3단계: CJA에서 이 데이터 세트에 대한 연결을 설정합니다

Experience Platform 데이터 세트에 대해 보고하려면 먼저 Experience Platform의 데이터 세트와 CJA 간에 연결을 설정해야 합니다. 자세한 내용은 [연결 만들기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ko).

## 4단계: 하나 이상의 데이터 보기 만들기

A [데이터 보기](/help/data-views/data-views.md) 은 연결에서 데이터를 해석하는 방법을 결정할 수 있는 Customer Journey Analytics에 대한 컨테이너입니다. Analysis Workspace에서 사용할 수 있는 모든 차원 및 지표(이 경우 Marketo과 관련된 지표 및 차원)를 지정합니다. 또한 해당 차원과 지표가 데이터를 가져오는 열을 지정합니다. 데이터 보기는 Analysis Workspace의 데이터에 대한 보고 준비에 따라 정의됩니다.

## 5단계: Analysis Workspace의 보고서

탐색할 수 있는 활용 사례는 다음과 같습니다. 2020년 4월~6월에 리드에 의한 웹 페이지 방문의 수는 얼마입니까?

1. 열기 [Analytics 작업 공간](/help/analysis-workspace/home.md) 새 프로젝트를 만듭니다.

1. 만들기 [필터](/help/components/filters/create-filters.md) 웹 페이지 보기 수를 다음과 같이 만드는 경우 - 이벤트 유형 = web.webpagedetails.pageViews :

   ![](assets/marketo-filter.png)

1. 자유 형식 테이블로 만든 필터인 웹 페이지 보기를 가져온 다음 월 날짜 범위를 가져옵니다. 이렇게 하면 매월 리드별로 웹 페이지 방문 수가 표시됩니다.

   ![](assets/marketo-freeform.png)

1. 또는 다음 차원을 가져옵니다. 개인 키 또는 회사 전자 메일 주소입니다. 이렇게 하면 각 리드에 의한 웹 페이지 방문이 제공됩니다.

   ![](assets/marketo-freeform2.png)
