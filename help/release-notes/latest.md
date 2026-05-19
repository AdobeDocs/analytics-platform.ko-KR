---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 373deaea2b7d73484a3983bde490a86e950c2c0e
workflow-type: tm+mt
source-wordcount: 818
ht-degree: 45%

---

# 최신 Customer Journey Analytics 릴리스 정보 (2026년 5월)

**마지막 업데이트**: 2026년 5월 13일

이 릴리스 정보는 2026년 5월 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **CJA API Postman 컬렉션** <br/>다운로드 가능한 Postman 컬렉션을 CJA API 끝점을 호출하는 데 사용할 수 있습니다.<p>자세한 내용은 [analytics-cja-postman-collections Github 저장소](https://github.com/AdobeDocs/analytics-cja-postman-collections)를 참조하십시오.  </p> | | 2026년 5월 1일 |
| **Customer Journey Analytics용 MCP 서버** <br/>Analytics MCP(Model Context Protocol) 서버를 사용하면 지원되는 MCP 클라이언트를 Adobe Customer Journey Analytics에 연결할 수 있습니다. 연결되면 MCP 클라이언트는 제품별 도구를 호출하여 데이터를 검색하거나 쿼리를 실행하거나 LLM 또는 에이전트 워크플로우의 일부로 지원되는 작업을 수행할 수 있습니다. 자세한 내용은 [Analytics MCP 서버](https://developer.adobe.com/analytics-mcp/docs/)를 참조하십시오.<p>Beta 기간 동안 이러한 MCP 서버를 사용한 경우 Beta와 프로덕션 엔드포인트 간에 서로 다른 URL이 있습니다. 베타 기간 동안 만들어진 모든 에이전트 워크플로가 5월 31일 이전에 프로덕션 끝점을 사용하도록 업데이트되었는지 확인하십시오.</p> | | 2026년 5월 5일 |
| **기본 모바일 앱 경험에 대한 Content Analytics 지원**<br/>&#x200B;조직은 콘텐츠 성능 분석을 iOS 및 Android 앱으로 확장하여 이미지 에셋과 세분화된 경험 요소를 캡처함으로써 사용자 참여 및 비즈니스 결과를 이끄는 인앱 콘텐츠를 파악할 수 있습니다.<p> [설명서](/help/content-analytics/content-analytics.md)이(가) 모바일 채널 기능 및 구성을 설명하기 위해 업데이트되었습니다. [Content Analytics Mobile SDK 확장](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)에 대한 정보는 [Adobe Developer](https://developer.adobe.com/)에서 사용할 수 있습니다.</p><p>인사이트는 모든 Adobe Content Analytics 고객이 사용할 수 있습니다.</p> | | 2026년 5월 6일 |
| **여정 캔버스 개선 사항** <br/> 여정 캔버스 시각화에서는 다음 개선 사항을 사용할 수 있습니다. <ul><li>여정에서 [노드 제외](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#exclude-nodes).</li><li>노드의 폴아웃 데이터를 사용하여 [세그먼트 만들기](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-a-segment-based-on-a-node-or-arrow), [트렌드](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#view-trend-data), [대상](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-an-audience) 및 [분류](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#apply-a-breakdown)를 만듭니다.</li></ul> | | 2026년 5월 18일 |
| **Adobe Engineering Agent에서 데이터 유효성 검사** <br/>Data Engineering Agent 내에서 새로운 데이터 유효성 검사 기술을 사용할 수 있습니다. 이러한 기술은 Customer Journey Analytics에서 데이터를 분석하기 전에 팀이 Adobe Experience Platform에서 데이터 품질을 직접 신속하게 평가하는 데 도움이 됩니다. <p>데이터 유효성 검사 기술은 통계 요약과 유효하지 않거나 비정상적인 값의 지능형 탐지를 결합하여 온디맨드, 현장 수준, 데이터 세트 수준 유효성 검사를 수행할 수 있습니다. </p><p>데이터 유효성 검사 기술을 사용하면 수작업 QA 작업을 줄이고 데이터 엔지니어링 워크플로 전반에 걸쳐 신뢰할 수 있는 데이터 온보딩 및 변환을 가속화할 수 있습니다.</p><p>(참조할 설명서 링크입니다.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026년 5월 19일 <p>(원래 2026년 3월 31일 릴리스로 계획됨)</p> |
| **Content Analytics: 선 시각화 썸네일 및 미리 보기** <br/>[썸네일 및 미리 보기](/help/content-analytics/report/report.md)를 이제 Content Analytics의 선 시각화에서 에셋 및 경험에 사용할 수 있습니다. |  | 2026년 5월 20일 |
| **스트리밍 미디어 서비스: 일정 데이터 지원** <br/>이제 과거 라이브 스트리밍 미디어 콘텐츠의 예약된 데이터를 업로드하여 시청자 수를 보다 쉽고 정확하게 추적할 수 있습니다.<p>다음은 일정 데이터 업로드가 지원되는 라이브 콘텐츠의 예입니다.</p><ul><li>FAST(무료 광고 지원 TV) 플랫폼</li><li>로컬 스트림</li><li>라이브 스포츠</li></ul><p>일정 데이터를 업로드하면 업로드 파일에서 지정한 시간 동안 실행된 개별 프로그램의 시청자 수 데이터를 추적할 수 있습니다. 특정 주제나 프로그램 세그먼트에 대한 시청자 수 데이터를 수집할 수도 있습니다.</p><p>이러한 기능은 스트리밍 미디어 컬렉션을 어떻게 구현하든 관계없이 사용할 수 있습니다.</p><p>이전에는 라이브 콘텐츠를 분석할 때 주어진 세션을 특정 프로그램에 정확하게 연결하는 것이 어려웠고, 주어진 세션을 개별 주제나 프로그램 세그먼트에 연결하는 것도 불가능했습니다.</p><p>자세한 내용은 [라이브 콘텐츠를 추적할 일정 데이터 업로드](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/track-schedule-data)를 참조하십시오.</p> | 2025년 10월 29일 | 2026년 상반기<p>(원래 2025년 10월 29일 릴리스로 계획됨)</p> |

{style="table-layout:auto"}


## Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189 425215
**구성 요소**:
**연결**: AN-449652, AN-444560, AN-442824, AN-440937, AN-440092, AN-439823, AN-429781
**Content Analytics**:
**분석 가이드**:
**내보내기**: AN-438953, AN-437115
**데이터 보기**: AN-442809
**구현**:
**Report Builder**: AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**보고**: AN-445123, AN-442231, AN-442169, AN-441811, AN-441733, AN-440505, AN-440300, AN-434824, AN-434210, AN-424000, AN-423359, AN-406242
**세그먼테이션**:
**예약된 보고서**:
**공유된 지표 및 차원**:
**기타**: AN-449159, AN-444661, AN-443900, AN-397985

## 관련 리소스

* [2025년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2025.md)
* [Adobe Analytics 릴리스 노트](https://experienceleague.adobe.com/ko/docs/analytics/release-notes/latest)
* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/ko/docs/media-analytics/using/release-notes/release-notes)
* [CX 엔터프라이즈 릴리스 정보](https://experienceleague.adobe.com/ko/docs/release-notes/experience-cloud/current)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
