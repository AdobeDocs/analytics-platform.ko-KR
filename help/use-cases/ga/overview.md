---
title: Google Analytics에서 Customer Journey Analytics로 데이터 마이그레이션
description: Google Analytics에서 Adobe Experience Platform으로 데이터를 이동하는 방법과 Customer Journey Analytics에서 보고서를 보는 방법에 대한 중요한 워크플로에 대해 알아봅니다.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 79%

---

# Google Analytics에서 Customer Journey Analytics로 데이터 마이그레이션

Customer Journey Analytics를 처음 사용하는 경우 귀사는 Google Analytics와 같은 다른 Analytics 플랫폼에서 데이터를 보유하고 있을 수 있습니다. 다음과 같은 중요한 단계를 따라 데이터를 Adobe Experience Platform으로 이동하여 Customer Journey Analytics에서 보고서를 볼 수 있습니다.

내역 데이터 및 현재 데이터 수집 모두에 워크플로가 제공됩니다. 귀사의 데이터 요구 사항에 맞게 이들 워크플로 중 하나 이상을 따라 작업을 수행할 수 있습니다.

## Google Analytics 내역 데이터를 Adobe Experience Platform으로 가져오기

내역(채우기) 데이터 수집에는 Google 데이터를 내보내고 해당 데이터를 Adobe Experience Platform으로 가져오는 작업이 포함됩니다. [Google Analytics 데이터를 Adobe Experience Platform으로 수집](backfill.md)을 참조하십시오.

내역 데이터를 Platform으로 성공적으로 가져온 다음에는 다음 중 하나를 수행할 수 있습니다. [현재 데이터 스트리밍 구성](streaming.md)또는 다음 방법으로 Customer Journey Analytics의 채워진 데이터에 대한 보고를 즉시 시작합니다. [연결 만들기](/help/connections/create-connection.md).

## Adobe Experience Platform용 기존 Google Analytics 구현 구성 {#configure}

현재(스트리밍) 데이터 수집에는 Adobe Experience Platform Edge Network로 데이터를 보낸 다음 해당 데이터를 Adobe Experience Platform으로 전달하는 작업이 포함됩니다. [Adobe Experience Platform으로의 Google Analytics 데이터 스트리밍 설정](streaming.md)을 참조하십시오.

## Customer Journey Analytics에서 연결 및 데이터 보기 구성

내역 데이터 수집 및/또는 Adobe Experience Platform으로의 데이터 수집 구성을 정상적으로 완료했다면 [연결을 만들어](/help/connections/create-connection.md) Customer Journey Analytics에서 해당 데이터를 참조하도록 할 수 있습니다.

연결을 사용하여 Analysis Workspace에서 사용할 하나 이상의 [데이터 보기](/help/data-views/create-dataview.md)를 만드십시오.

## 보고서 생성

데이터 보기 내에 차원 및 지표를 구성한 다음에는 Analysis Workspace를 사용하여 원하는 보고서를 생성할 수 있습니다. [Customer Journey Analytics에서 Google Analytics 데이터에 대한 보고](report.md)를 참조하십시오.
