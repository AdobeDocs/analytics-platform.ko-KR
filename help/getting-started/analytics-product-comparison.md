---
title: Customer Journey Analytics 제품 비교
description: Analysis Workspace, Report Builder, 전체 테이블 내보내기, 데이터 피드, API 및 MCP와 같은 여정 Analytics 보고 및 내보내기 도구의 고객 특성을 비교합니다.
keywords: 클릭스트림, 데이터 피드, 데이터피드, 제품 비교, Analysis Workspace, Report Builder, 전체 테이블 내보내기
feature: Components
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e686fca2c77a8f9739298ece01ccf0fa2fe87b3b
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 44%

---


# Analytics 제품 비교

이 페이지에서는 주요 속성에 대한 Customer Journey Analytics 보고 및 내보내기 도구를 비교하여 분석 또는 데이터 내보내기 요구에 적합한 도구를 선택할 수 있습니다.

| 제품 이름 및 도움말 링크 | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md) | [데이터 피드](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/) | MCP | BI 확장 기능 | 동료 |
|---|---|---|---|---|---|---|---|---|
| **액세스 방법** | 브라우저 | Microsoft Excel | 브라우저 | 브라우저를 통한 설정 | RESTful API 도구 | MCP 호환 도구 | BI 도구 | MCP 호환 도구 |
| **데이터 세부 기간** | 집계됨 | 집계됨 | 집계됨 | 이벤트 | 집계됨 | 집계됨 | 집계됨 | 집계됨 |
| **Experience Cloud ID (ECID) 사용 가능** | 아니요 | 아니요 | 아니요 | 예 | 아니요 | 아니요 | 아니요 | 아니요 |
| **타임스탬프 사용 가능** | 아니요 | 아니요 | 아니요 | 예 | 아니요 | 아니요 | 아니요 | 아니요 |
| **처리 수준** | 완전히 처리됨 | 완전히 처리됨, 별도의 실시간 보고서 사용 | 완전히 처리됨 | 완전히 처리됨 | 완전히 처리됨 | 완전히 처리됨 | 완전히 처리됨 | 완전히 처리됨 |
| **보트 필터링이 적용되는 위치** | [데이터 스트림](https://experienceleague.adobe.com/ko/docs/experience-platform/datastreams/bot-detection) 및/또는 [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) 내 | [데이터 스트림](https://experienceleague.adobe.com/ko/docs/experience-platform/datastreams/bot-detection) 및/또는 [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) 내 | [데이터 스트림](https://experienceleague.adobe.com/ko/docs/experience-platform/datastreams/bot-detection) 및/또는 [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) 내 | [데이터 스트림](https://experienceleague.adobe.com/ko/docs/experience-platform/datastreams/bot-detection) 및/또는 [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) 내 |  |  | [데이터 스트림](https://experienceleague.adobe.com/ko/docs/experience-platform/datastreams/bot-detection) 및/또는 [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) 내 | |
| **표시 행 제한 (페이지 매김 전)** | 400 | 50,000 | 등급에 따라 300만, 3천만, 1억 5천만, 3억으로 제한 | 계층에 따라 다름 | 50,000 | 50,000 | 50,000 | 50,000 |
| **여러 데이터 보기** | 예. 프로젝트에는 여러 데이터 보기의 데이터가 포함될 수 있습니다. | 예. 프로젝트에는 여러 데이터 보기의 데이터가 포함될 수 있습니다. | 아니요. 내보내기에는 하나의 데이터 보기의 데이터만 포함될 수 있습니다. | 아니요. 내보내기에는 하나의 데이터 보기의 데이터만 포함될 수 있습니다. | 아니요, 각 쿼리는 하나의 데이터 보기만 참조할 수 있습니다. | 아니요, 각 쿼리는 하나의 데이터 보기만 참조할 수 있습니다. | 아니요, 각 쿼리는 하나의 데이터 보기만 참조할 수 있습니다. | 예, 사용자에게 메시지가 표시되면 |
| **차원 열 수** | 최대 5개 | ? | 최대 10 | 제한 없음 | 최대 5개 | ? | ? | ? |
| **지표 열 수** | ? | ? | 최대 10 | 제한 없음 | ? | ? | ? | ? |
| **세분화** <br> [자세히 알아보기](/help/components/segments/seg-overview.md) | 예 | 예 | 예 | 예. [제한 사항](/help/components/exports/cja-data-feeds/df-segmentation.md) 있음 | 예 | 예 | 예 | 예 |
| **계산된 지표** <br> [자세히 알아보기](/help/components/calc-metrics/calc-metr-overview.md) | 예 | 예 | 예. [제한 사항](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support) 있음 | 아니요 | 예 | 예 | 예 | 예 |
| **파생 필드** <br> [자세히 알아보기](/help/data-views/derived-fields/derived-fields.md) | 예 | 예 | 예 | 예 | 예 | 예 | 예 | 예 |
| **속성** <br> [자세히 알아보기](/help/analysis-workspace/attribution/overview.md) | 예 | 제한적 | 예. [제한 사항](/help/analysis-workspace/export/export-cloud.md#attribution-behavior) 있음 | 아니요 | 예 | 예 | 예 | 예 |
| **예약된 게재** | 예 | 예 | 예 | 예 | — | — | — | — |
| **게재 대상** | 이메일 | 이메일 | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | — | — | — | — |

{style="table-layout:auto"}
