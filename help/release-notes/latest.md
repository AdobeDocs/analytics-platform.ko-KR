---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: ae368ea39b6521e2e350aa7849568cd225ecef90
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 63%

---

# 현재 Customer Journey Analytics 릴리스 정보 (2026년 4월)

**마지막 업데이트**: 2026년 4월 22일

이 릴리스 정보에는 2026년 4월 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **이탈리아어 지원**<br/>&#x200B;이탈리아어 로케일(it-IT)은 이제 Customer Journey Analytics의 Analysis Workspace에서 지원됩니다. <p>Customer Journey Analytics은 Experience Platform UI에 대한 [브라우저 및 언어 지원에 설명된 대로 Experience Platform UI](https://experienceleague.adobe.com/ko/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)에서 지원되는 모든 언어를 지원합니다.</p><p>Experience Platform에서 [기본 언어를 변경](https://experienceleague.adobe.com/ko/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)할 수 있습니다.</p> | | 2026년 4월 8일 |
| **Adobe Engineering Agent에서 데이터 유효성 검사** <br/>Data Engineering Agent 내에서 새로운 데이터 유효성 검사 기술을 사용할 수 있습니다. 이러한 기술은 Customer Journey Analytics에서 데이터를 분석하기 전에 팀이 Adobe Experience Platform에서 데이터 품질을 직접 신속하게 평가하는 데 도움이 됩니다. <p>데이터 유효성 검사 기술은 통계 요약과 유효하지 않거나 비정상적인 값의 지능형 탐지를 결합하여 온디맨드, 현장 수준, 데이터 세트 수준 유효성 검사를 수행할 수 있습니다. </p><p>데이터 유효성 검사 기술을 사용하면 수작업 QA 작업을 줄이고 데이터 엔지니어링 워크플로 전반에 걸쳐 신뢰할 수 있는 데이터 온보딩 및 변환을 가속화할 수 있습니다.</p><p>(참조할 설명서 링크입니다.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/ko/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026년 5월 <p>(원래 2026년 3월 31일 릴리스로 계획됨)</p> |
| **Customer Journey Analytics용 MCP 서버** <br/>Analytics MCP(Model Context Protocol) 서버를 사용하면 지원되는 MCP 클라이언트를 Adobe Customer Journey Analytics에 연결할 수 있습니다. 연결되면 MCP 클라이언트는 제품별 도구를 호출하여 데이터를 검색하거나 쿼리를 실행하거나 LLM 또는 에이전트 워크플로우의 일부로 지원되는 작업을 수행할 수 있습니다. 자세한 내용은 [Analytics MCP 서버](https://developer.adobe.com/analytics-mcp/docs/)를 참조하십시오.<p>Beta 기간 동안 이러한 MCP 서버를 사용한 경우 Beta와 프로덕션 엔드포인트 간에 서로 다른 URL이 있습니다. 베타 기간 동안 만들어진 모든 에이전트 워크플로가 5월 31일 이전에 프로덕션 끝점을 사용하도록 업데이트되었는지 확인하십시오.</p> | | 2026년 5월 5일 |
| **기본 모바일 앱 경험에 대한 Content Analytics 지원**<br/>&#x200B;조직은 콘텐츠 성능 분석을 iOS 및 Android 앱으로 확장하여 이미지 에셋과 세분화된 경험 요소를 캡처함으로써 사용자 참여 및 비즈니스 결과를 이끄는 인앱 콘텐츠를 파악할 수 있습니다. [설명서](/help/content-analytics/content-analytics.md)이(가) 모바일 채널 기능 및 구성을 설명하기 위해 업데이트되었습니다. [Content Analytics Mobile SDK 확장](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)에 대한 정보는 [Adobe Developer](https://developer.adobe.com)에서 사용할 수 있습니다.<p>인사이트는 모든 Adobe Content Analytics 고객이 사용할 수 있습니다.</p> | 2026년 5월 6일 | 2026년 5월 6일 |
| **스트리밍 미디어 서비스: 일정 데이터 지원** <br/>이제 과거 라이브 스트리밍 미디어 콘텐츠의 예약된 데이터를 업로드하여 시청자 수를 보다 쉽고 정확하게 추적할 수 있습니다.<p>다음은 일정 데이터 업로드가 지원되는 라이브 콘텐츠의 예입니다.</p><ul><li>FAST(무료 광고 지원 TV) 플랫폼</li><li>로컬 스트림</li><li>라이브 스포츠</li></ul><p>일정 데이터를 업로드하면 업로드 파일에서 지정한 시간 동안 실행된 개별 프로그램의 시청자 수 데이터를 추적할 수 있습니다. 특정 주제나 프로그램 세그먼트에 대한 시청자 수 데이터를 수집할 수도 있습니다.</p><p>이러한 기능은 스트리밍 미디어 컬렉션을 어떻게 구현하든 관계없이 사용할 수 있습니다.</p><p>이전에는 라이브 콘텐츠를 분석할 때 주어진 세션을 특정 프로그램에 정확하게 연결하는 것이 어려웠고, 주어진 세션을 개별 주제나 프로그램 세그먼트에 연결하는 것도 불가능했습니다.</p><p>자세한 내용은 [라이브 콘텐츠를 추적할 일정 데이터 업로드](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/track-schedule-data)를 참조하십시오.</p> | 2025년 10월 29일 | 2026년 상반기<p>(원래 2025년 10월 29일 릴리스로 계획됨)</p> |
| **다중 차원 API 보고**<br/>&#x200B;단일 API 요청에서 다중 차원을 보고하고 차원 수준 검색을 수행합니다. [자세히 알아보기](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | 2026년 3월 |
| **다중 열 API 정렬**<br/> API 요청에서 여러 차원 및 지표 오브젝트를 정렬합니다. 동일한 정렬 정의에서 차원과 지표를 혼합합니다. [자세히 알아보기](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | 2026년 3월 |

## Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-442813, AN-442410, AN-442231, AN-441943, AN-441717, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**구성 요소**:
**연결**: AN-442824, AN-440937, AN-440092, AN-429781
**Content Analytics**:
**분석 가이드**:
**내보내기**:
**데이터 보기**: AN-442809, AN-434824, AN-434210, AN-424000
**구현**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**보고**: AN-443900, AN-441811, AN-441506, AN-440919, AN-440545, AN-440505, AN-440300
**세그먼테이션**:
**예약된 보고서**:
**공유된 지표 및 차원**:
**기타**: AN-423359, AN-406242, AN-397985

## 관련 리소스

* [2025년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2025.md)
* [Adobe Analytics 릴리스 노트](https://experienceleague.adobe.com/ko/docs/analytics/release-notes/latest)
* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/ko/docs/media-analytics/using/release-notes/release-notes)
* [Adobe Experience Cloud 릴리스 노트](https://experienceleague.adobe.com/ko/docs/release-notes/experience-cloud/current)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
