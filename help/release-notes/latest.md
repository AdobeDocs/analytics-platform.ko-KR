---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 701279f92877ee186160f901f0d4df74fd42f547
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 36%

---

# 최신 Customer Journey Analytics 릴리스 정보 (2026년 4월)

**마지막 업데이트**: 2026년 4월 9일

이 릴리스 정보는 2026년 4월 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **이탈리아어 지원**<br/>&#x200B;이탈리아어 로케일(it-IT)은 이제 Customer Journey Analytics의 Analysis Workspace에서 지원됩니다. <p>Customer Journey Analytics은 [Experience Platform UI에 대한 브라우저 및 언어 지원](https://experienceleague.adobe.com/ko/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)에 설명된 대로 Experience Platform UI에서 지원되는 모든 언어를 지원합니다.</p><p>Experience Platform에서 [기본 언어를 변경](https://experienceleague.adobe.com/ko/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)할 수 있습니다.</p> | | 2026년 4월 8일 목요일 |
| **Adobe 엔지니어링 에이전트에서 데이터 유효성 검사** <br/>Data Engineering Agent 내에서 새로운 데이터 유효성 검사 기술을 사용할 수 있습니다. 이러한 기술은 Customer Journey Analytics에서 데이터를 분석하기 전에 Adobe Experience Platform에서 직접 데이터 품질을 팀이 빠르게 평가하는 데 도움이 됩니다. <p>데이터 유효성 검사 기술을 통해 온디맨드, 필드 수준 및 데이터 세트 수준 유효성 검사를 수행할 수 있으며, 여기에는 통계 요약과 유효하지 않거나 비정상적인 값을 지능적으로 감지하는 기능이 결합되어 있습니다. </p><p>데이터 유효성 검사 기술을 사용하면 수동 QA 노력을 줄이고 데이터 엔지니어링 워크플로 전반에서 신뢰할 수 있는 데이터 온보딩 및 변환을 가속화할 수 있습니다.</p><p>(참조할 설명서 링크입니다.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/ko/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026년 4월 말 <p>(원래 2026년 3월 31일 수요일 릴리스로 계획됨)</p> |
| **Customer Journey Analytics용 MCP 서버** <br/>이제 MCP(Model Context Protocol)를 사용하여 Customer Journey Analytics을 기존 에이전트 워크플로에 연결할 수 있습니다. 자연어를 사용하여 보고서와 통찰력을 요청할 수 있습니다.<p>(참조할 설명서 링크입니다.)</p> | | 2026년 4월 말 |
| **스트리밍 미디어 서비스: 일정 데이터 지원** <br/>이제 이전 라이브 스트리밍 미디어 콘텐츠의 일정 데이터를 업로드하여 시청률을 보다 쉽고 정확하게 추적할 수 있습니다.<p>다음은 일정 데이터 업로드가 지원되는 라이브 콘텐츠의 예입니다.</p><ul><li>FAST(무료 광고 지원 TV) 플랫폼</li><li>로컬 스트림</li><li>라이브 스포츠</li></ul><p>일정 데이터를 업로드하면 업로드 파일에서 지정한 시간 동안 실행된 개별 프로그램의 시청자 수 데이터를 추적할 수 있습니다. 특정 주제나 프로그램 세그먼트에 대한 시청자 수 데이터를 수집할 수도 있습니다.</p><p>이러한 기능은 스트리밍 미디어 컬렉션을 어떻게 구현하든 관계없이 사용할 수 있습니다.</p><p>이전에는 라이브 콘텐츠를 분석할 때 주어진 세션을 특정 프로그램에 정확하게 연결하는 것이 어려웠고, 주어진 세션을 개별 주제나 프로그램 세그먼트에 연결하는 것도 불가능했습니다.</p><p>자세한 내용은 [라이브 콘텐츠를 추적할 일정 데이터 업로드](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/track-schedule-data)를 참조하십시오.</p> | 2025년 10월 29일 | 2026년 상반기<p>(원래 2025년 10월 29일 릴리스로 계획됨)</p> |
| **여러 차원 API 보고**<br/>&#x200B;단일 API 요청에서 여러 차원을 보고하고 차원 수준 검색을 수행합니다. [자세히 알아보기](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | 2026년 3월 |
| **다중 열 API 정렬**<br/> API 요청에서 여러 차원 및 지표 개체를 정렬합니다. 동일한 정렬 정의에서 차원과 지표를 혼합합니다. [자세히 알아보기](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | 2026년 3월 |

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


## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **TLS 1.2 암호 그룹 제거** | 2026년 2월 11일 목요일 | 관리자에게 알림: Adobe은 2026년 5월 27일에 Adobe 데이터 수집 서버에서 다음 TLS 1.2 암호 세트에 대한 지원을 중단할 예정입니다.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>대부분의 구현에 고객 작업이 필요하지 않습니다. 이 변경 사항은 주로 오래된 TLS 라이브러리를 사용하는 이전 기본 애플리케이션에서 전송된 Analytics 데이터와 오래된 브라우저나 운영 체제에서 적은 수의 웹 방문자에게 영향을 줍니다. 이러한 암호 세트에 대한 지원을 제거하면 보안이 강화되고 Adobe이 최신 암호화 표준에 맞게 조정됩니다. 현재 데이터 수집 트래픽의 0.1% 미만이 이러한 암호 세트에 의존합니다.</p> |

## 관련 리소스

* [2025년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2025.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/ko/docs/analytics/release-notes/latest)
* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/ko/docs/media-analytics/using/release-notes/release-notes)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/ko/docs/release-notes/experience-cloud/current)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
