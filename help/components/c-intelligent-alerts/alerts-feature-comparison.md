---
description: Customer Journey Analytics에서 Adobe Analytics과 경고가 어떻게 다른지 알아봅니다.
title: Customer Journey Analytics과 Adobe Analytics 간의 경고 기능 비교
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
TQID: https://experienceleague.adobe.com/NEm3Mu7q6RDKbCyG-PJzOFPrjJF4Y-unHgyBXyKd1HM
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
    internal-label: Alerts
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 4f3c4a214bb9676ced6fe3c9627c969413013790
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 23%
---
# Customer Journey Analytics과 Adobe Analytics 간의 경고 기능 비교

Customer Journey Analytics에서의 경고 사용 프로세스는 Adobe Analytics에서의 경고 사용 프로세스와 거의 동일합니다. 단, 중요한 차이점이 있습니다. 다음 섹션에서는 주요 차이점에 대해 설명합니다.

## 시간별 경고는 특정 데이터 유형에 비현실적일 수 있습니다

다양한 유형의 데이터를 Adobe Experience Platform으로 수집할 수 있으므로 경고에 포함할 수 있는 모든 데이터가 시간별 경고에 실용적인 것은 아닙니다. 특정 유형의 데이터는 한 시간의 제약 조건 내에서 안정적으로 수집되고 사용할 수 없습니다.

자세한 내용은 [데이터 수집 시간이 다릅니다](#data-ingestion-times-vary)를 참조하세요.

## 데이터 수집 시간은 다양합니다

Customer Journey Analytics에서 데이터를 완료하고 보고할 수 있기까지 필요한 시간은 조직에 따라 다릅니다.

이는 다음과 같은 이유 때문입니다.

* 모든 종류의 데이터 스키마와 유형을 보유할 수 있는 플랫폼의 기능

  웹 데이터에서만 보고하는 Adobe Analytics과 달리 [다양한 유형의 데이터를 Adobe Experience Platform에 수집](/help/data-ingestion/data-ingestion.md)하여 Customer Journey Analytics에서 보고할 수 있으며 모든 유형의 데이터를 순차적으로 실시간으로 전송할 수 있는 것은 아닙니다.

* Platform 데이터 세트에 일괄 데이터 전달 지연

  일부 데이터를 더 빨리 보고할 수 있지만 모든 [일괄 처리 데이터는 Platform 데이터 세트](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.)에 수집됩니다. 일반적으로 데이터 이벤트 시간이 3~9시간 경과합니다. 경고가 정확하려면 데이터 세트에서 사용 가능한 모든 일괄 처리 데이터를 사용하여 데이터 수집을 완료해야 합니다. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

이러한 이유로, 수집할 수 있는 다양한 종류의 이벤트 데이터에 대한 데이터 수집은 일정 지연 후에만 완료되며, 일반적으로 데이터 이벤트 시간이 3~9시간 경과합니다. 경고가 정확하려면 지정된 이벤트 범위의 이벤트 데이터가 완전해야 합니다. 즉, Adobe가 지정된 이벤트 범위에 대한 이벤트 데이터를 더 이상 수신하지 않아야 합니다.

이러한 수집 시간 지연을 고려하여 경고가 전송되기까지 기본적으로 9시간이 지연됩니다.

기본 지연 시간인 9시간을 0~24시간 사이의 값으로 조정할 수 있습니다. 그러나 지연 시간을 9시간 이하로 줄이면 불완전한 데이터를 보고하게 되어 부정확한 경고 정보가 제공될 수 있습니다.

지연 조정 방법 및 조정 시 고려해야 할 요소에 대한 자세한 내용은 [경고 만들기](/help/components/c-intelligent-alerts/alert-builder.md)를 참조하십시오.

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## 경고를 생성하는 방법 감소

Adobe Analytics의 Analysis Workspace에서는 [여러 방법으로 Analysis Workspace에서 경고를 만들 수 있습니다](https://experienceleague.adobe.com/en/docs/analytics/components/alerts/alert-builder). Customer Journey Analytics에서는 자유 형식 테이블의 선택 항목에서만 Analysis Workspace에서 [경고를 만들 수 있습니다](alert-builder.md).

Adobe Analytics과 Customer Journey Analytics 모두 [경고 관리자](alert-manager.md)를 통해 경고를 만들 수 있습니다
