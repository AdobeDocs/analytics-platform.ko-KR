---
title: Google Analytics에서 Customer Journey Analytics으로 데이터 마이그레이션
description: 데이터를 Google Analytics에서 Adobe Experience Platform으로 이동하고 Customer Journey Analytics에서 보고서를 보는 방법에 대한 중요한 워크플로우에 대해 알아봅니다.
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Google Analytics에서 Customer Journey Analytics으로 데이터 마이그레이션

Customer Journey Analytics을 처음 사용하는 경우 조직에 Google Analytics과 같은 다른 Analytics 플랫폼에 기존 데이터가 있을 수 있습니다. 이러한 중요한 단계에 따라 해당 데이터를 Adobe Experience Platform으로 이동하여 Customer Journey Analytics에서 보고서를 볼 수 있습니다.

워크플로우는 이전 데이터와 현재 데이터 수집 모두에 대해 제공됩니다. 조직의 데이터 요구 사항에 따라 이러한 워크플로우 중 하나 또는 둘 다 따를 수 있습니다.

## Google Analytics의 이전 데이터를 Adobe Experience Platform으로 가져오기

내역(채우기) 데이터 섭취에는 Google에서 데이터를 내보내고 해당 데이터를 Adobe Experience Platform으로 가져오는 작업이 포함됩니다. 자세한 내용은 [Adobe Experience Platform에서 Google Analytics 데이터 수집](backfill.md).

이전 데이터를 Platform으로 성공적으로 가져오면 다음 중 하나를 수행할 수 있습니다 [스트리밍 현재 데이터 구성](streaming.md)로 채우거나 CJA에서 즉시 백채워진 데이터에 대한 보고를 시작합니다. [연결 만들기](/help/connections/create-connection.md).

## Adobe Experience Platform에 대한 기존 Google Analytics 구현 구성 {#configure}

현재(스트리밍) 데이터를 수집하면 Adobe Experience Edge로 데이터를 전송한 다음 해당 데이터를 Adobe Experience Platform에 전달합니다. 자세한 내용은 [Adobe Experience Platform에서 스트리밍 Google Analytics 데이터 설정](streaming.md).

## CJA에서 연결 및 데이터 보기 구성

이전 데이터를 성공적으로 수집하고 데이터 수집을 Adobe Experience Platform에 구성하면 다음을 수행할 수 있습니다 [연결 만들기](/help/connections/create-connection.md) Customer Journey Analytics이 해당 데이터를 참조할 수 있도록 허용합니다.

연결을 사용하여 하나 이상 만듭니다 [데이터 보기](/help/data-views/create-dataview.md) Analysis Workspace에서 사용할 수 있습니다.

## 보고서 만들기

데이터 보기 내에서 차원 및 지표를 구성한 후 Analysis Workspace을 사용하여 원하는 보고서를 생성할 수 있습니다. 자세한 내용은 [Customer Journey Analytics의 Google Analytics 데이터에 대한 보고서](report.md).
