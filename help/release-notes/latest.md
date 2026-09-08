---
title: 현재 Customer Journey Analytics 릴리스 노트
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
hold: true
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: b9c679f4cd71fb2ae9c9c3af1b680982f92e6c83
workflow-type: tm+mt
source-wordcount: 1189
ht-degree: 21%

---

# 최신 Customer Journey Analytics 릴리스 정보 (2026년 9월)

**마지막 업데이트**: 2026년 9월 8일

이 릴리스 정보는 2026년 9월 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **Customer Journey Analytics MCP 서버 플러그인**<br/> ChatGPT 및 Cloud용 새로운 Customer Journey Analytics MCP 서버 플러그인을 사용하여 데이터에 빠르게 액세스할 수 있습니다. <p>자세한 내용은 [ChatGPT 플러그인 안내서](https://developer.adobe.com/analytics-mcp/docs/guides/chatgpt) 및 [Claude 커넥터 안내서](https://developer.adobe.com/analytics-mcp/docs/guides/claude)를 참조하십시오.</p> | 2026년 9월 1일 | 2026년 9월 1일 |
| **추가 데이터 사용 레이블 지원**<br>&#x200B;이제 Customer Journey Analytics에서 데이터 집합 내의 요소에 대해 다음과 같은 추가 데이터 사용 레이블을 지원합니다.<ul><li>C2 - 서드파티 데이터 내보내기 제한(현재 사용 가능)</li><li>C3 - 직접 식별 가능한 데이터 조합 제한(현재 사용 가능)</li><li>C9 - 데이터 과학 제한(8월 또는 9월 릴리스 예정)</li></ul><p>자세한 내용은 [레이블, 정책 및 마케팅 작업](/help/data-views/data-governance.md)을 참조하십시오.</p> | | 2026년 9월 3일 |
| **동의 정책 필터링 및 보고**<br>&#x200B;이제 Adobe Experience Platform 동의 정책과 일치하는 방문자를 보고할 수 있습니다. (동의 정책 차원 및 지표가 연결의 데이터 보기에 추가됩니다.)<p>또한 데이터가 Customer Journey Analytics에 수집되기 전에 동의하지 않는 방문자를 제외할 수 있습니다.</p><p>(참조할 설명서 링크입니다.)<!--For more information, see Consent reporting and filtering overview.--></p> | | 2026년 9월 |
| **세그먼트를 보고 날짜 범위로 제한**<br/>&#x200B;세그먼트에 날짜 범위 구성 요소가 포함된 경우 Workspace 보고서의 데이터는 보고 날짜 범위를 초과할 수 있습니다.<p>이제 세그먼트에 포함된 날짜 구성 요소에 관계없이 결과를 보고 날짜 범위로 제한할 수 있는 새 옵션을 사용할 수 있습니다.</p><p>이 옵션은 최상위 컨테이너가 개인인 세그먼트를 만들거나 수정할 때 사용할 수 있습니다.</p><p>자세한 내용은 [세그먼트 빌드](/help/components/segments/seg-builder.md#components)를 참조하세요.</p> | 2026년 8월 26일 | 2026년 9월 9일 |
| **대화 통찰력을 사용하여 Analysis Workspace에서 LLM 고객 경험 분석**<br/> Customer Journey Analytics은 이제 구조화되지 않은 채팅 데이터를 Analysis Workspace으로 가져와서 사용자의 자산 전체에서 발생하는 LLM 기반 탐색 및 구매 경험을 보고할 수 있습니다.<p>이 기능을 사용하여 다음과 같은 작업을 수행할 수 있습니다.</p><ul><li>웹 SDK을 통해 대화형 에이전트(조직의 사용자 지정 에이전트 또는 Adobe Brand Concierge)에서 프롬프트, 응답 및 에이전트 메타데이터를 수집합니다.</li><li>고객이 무엇을 묻고 있는지, 에이전트가 어떻게 반응하는지, 고객이 상호 작용에 대해 어떻게 느끼는지 이해할 수 있도록 의도, 톤 및 감정을 분석합니다.</li><li>기존 스키마, 데이터 세트 및 데이터 보기를 사용하여 규모에 맞게 분석한 다음 Analysis Workspace에서 통찰력을 표시합니다.</li><li>상담원 상호 작용을 더 광범위한 고객 여정과 연결하여 대화를 결과와 연결하여 전환, 참여 등에 대한 실질적인 영향을 측정할 수 있습니다.</li></ul><p>이전에는 LLM 기반 여정을 측정하기가 어렵고 기존 고객 경험에 연결하는 것이 거의 불가능했습니다.</p><p>(설명서 링크는 추후 제공됩니다.)</p> | | 2026년 9월 22일 |
| **전체 모집단 보고**<br/>&#x200B;이제 Customer Journey Analytics 연결에 있는 프로필 및 조회 데이터 세트에 정의된 엔터티를 분석하고 보고할 수 있습니다. 이러한 분석 및 보고는 이벤트 데이터 세트의 시간 기반 이벤트 시리즈를 능가합니다. <p>이 기능을 사용하면 비즈니스 고객 기반의 전체 범위를 반영하는 새로운 클래스의 쿼리, 지표 및 대상 정의를 사용할 수 있습니다.</p><p>(설명서 링크는 추후 제공됩니다.)</p> | | 2026년 9월 22일 |
| **시간별 경고**<br/>&#x200B;이제 경고의 시간 세부기간을 시간별로 설정할 수 있습니다.<p>시간별 경고는 지정된 시간 내에 도착하는 데이터를 위한 것입니다. 데이터의 지연 시간이 1시간을 초과하는 경우 세부 기간이 길수록 경고가 전체 데이터를 평가하게 됩니다. 데이터가 도착하는 데 걸리는 시간을 모를 경우 데이터 엔지니어에게 문의하십시오.</p>p>(참조할 설명서 링크)</p> | | 2026년 9월 |
| **경고 게재는 구성된 지연을 엄격히 준수합니다**<br/>&#x200B;이제 지정된 이벤트 범위에 대한 데이터의 완료 여부와 관계없이 사용자가 설정한 지연 기간이 끝날 때 경고가 전달됩니다. 지연 기간 후에 도착하는 데이터는 경고에 포함되지 않습니다.<p>이전에는 구성된 지연 기간 후에 경고가 전달되었더라도 늦게 도착하는 데이터를 기다린 백그라운드 처리 검사가 경고에 포함되었습니다.</p>p>(참조할 설명서 링크)</p> | | 2026년 9월 |
| **Adobe Brand Visibility 통합**<br/> AI 기반 검색이 실제 웹 사이트 참여 및 비즈니스 성과로 이어지는 방식을 측정할 수 있도록 Adobe Brand Visibility을 조직의 Customer Journey Analytics 데이터와 연결합니다.<p>(설명서 링크는 추후 제공됩니다.)</p> | | 2026년 9월 |
| **CX Enterprise Coworker의 추가 기술**<br> Coworker에 다음을 포함한 새로운 기술이 제공됩니다.<ul><li><strong>구현 가이드</strong>: 짧은 검색 대화를 CSV, Jira, Workfront 및 Markdown으로 즉시 내보내기를 사용하여 개인화되고 종속성을 인식하는 구현 계획으로 전환합니다.</li><li><strong>지능형 구현 검사 목록</strong>: 검색 대화를 Coworker Projects의 관리 및 추적 가능한 구현 프로젝트로 전환합니다. 할당, 모니터링 및 유효성을 검사할 수 있는 순서가 지정된 검사 목록입니다.</li><li><strong>데이터 유효성 검사</strong>: Coworker에서 직접 데이터 필드와 데이터 세트를 확인하여 신뢰할 수 있고 정확한 데이터(Adobe Agent Orchestrator v1에서 업그레이드됨)에서 작업하고 있는지 확인하십시오.</li><li><strong>스트리밍 미디어 유효성 검사</strong>: Coworker에서 스트리밍 미디어 데이터의 유효성을 검사하여 데이터가 정확하고 보고할 준비가 되었는지 확인합니다.</li></ul><p>(다음 설명서 링크)</p> | | 2026년 9월 30일 |

### Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373
**구성 요소**:
**연결**: AN-451458
**콘텐츠 분석**:
**안내식 분석**: AN-485600
**내보내기**: AN-489161, AN-467131, AN-464746
**데이터 보기**: AN-478732, AN-468836, AN-467851
**데이터 수집**: AN-489829, AN-489722, AN-469451, AN-467436, AN-467049, AN-466087, AN-465049, AN-463524, AN-457433
**구현**:
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695
**보고**: AN-479145, AN-469095, AN-468070, AN-467786, AN-456684
**세그먼테이션**: AN-486561
**예약된 보고서**:
**공유된 지표 및 차원**:
**대상 분석**: AN-468237, AN-462553
**기타**:

## 연기된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **스트리밍 미디어 서비스: 일정 데이터 지원** <br/>이제 과거 라이브 스트리밍 미디어 콘텐츠의 예약된 데이터를 업로드하여 시청자 수를 보다 쉽고 정확하게 추적할 수 있습니다.<p>다음은 일정 데이터 업로드를 지원하는 라이브 콘텐츠의 예입니다.</p><ul><li>FAST(무료 광고 지원 TV) 플랫폼</li><li>로컬 스트림</li><li>라이브 스포츠</li></ul><p>일정 데이터를 업로드하면 업로드 파일에서 지정한 시간 동안 실행된 개별 프로그램의 시청자 수 데이터를 추적할 수 있습니다. 특정 주제나 프로그램 세그먼트에 대한 시청자 수 데이터를 수집할 수도 있습니다.</p><p>이러한 기능은 스트리밍 미디어 컬렉션을 어떻게 구현하든 관계없이 사용할 수 있습니다.</p><p>이전에는 라이브 콘텐츠를 분석할 때 주어진 세션을 특정 프로그램에 정확하게 연결하는 것이 어려웠고, 주어진 세션을 개별 주제나 프로그램 세그먼트에 연결하는 것도 불가능했습니다.</p><p>자세한 내용은 [라이브 콘텐츠를 추적할 일정 데이터 업로드](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/track-schedule-data)를 참조하십시오.</p> | 2025년 10월 29일 | TBD<p>(원래 2025년 10월 29일로 계획됨)</p> |

>[!MORELIKETHIS]
>
>* [2026년 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2026.md)
>* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/ko/docs/analytics/release-notes/latest)
>* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/ko/docs/media-analytics/using/release-notes/release-notes)
>* [CX 엔터프라이즈 릴리스 노트](https://experienceleague.adobe.com/ko/docs/release-notes/experience-cloud/current)
>* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)

