---
title: 현재 Customer Journey Analytics 릴리스 노트
description: 현재 기간에 대한 새로운 기능, 해결된 문제 및 지연된 릴리스를 포함하여 최신 Customer Journey Analytics 릴리스 정보를 확인하십시오.
hold: true
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 4f62a406436915d581ab30f26b82544388957782
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 29%
---
# 최신 Customer Journey Analytics 릴리스 정보 (2026년 9월)

**마지막 업데이트**: 2026년 9월 9일

이 릴리스 정보는 2026년 9월 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **대화 통찰력을 사용하여 Analysis Workspace에서 LLM 고객 경험 분석**<br/> Customer Journey Analytics은 이제 구조화되지 않은 채팅 데이터를 Analysis Workspace으로 가져와서 사용자의 자산 전체에서 발생하는 LLM 기반 탐색 및 구매 경험을 보고할 수 있습니다.<p>이 기능을 사용하여 다음과 같은 작업을 수행할 수 있습니다.</p><ul><li>Web SDK을 통해 대화형 에이전트(조직의 사용자 지정 에이전트 또는 Adobe Brand Concierge)의 프롬프트, 응답 및 에이전트 메타데이터를 수집합니다.</li><li>고객이 무엇을 묻고 있는지, 에이전트가 어떻게 반응하는지, 고객이 상호 작용에 대해 어떻게 느끼는지 이해할 수 있도록 의도, 톤 및 감정을 분석합니다.</li><li>기존 스키마, 데이터 세트 및 데이터 보기를 사용하여 규모에 맞게 분석한 다음 Analysis Workspace에서 통찰력을 표시합니다.</li><li>상담원 상호 작용을 더 광범위한 고객 여정과 연결하여 대화를 결과와 연결하여 전환, 참여 등에 대한 실질적인 영향을 측정할 수 있습니다.</li></ul><p>이전에는 LLM 기반 여정을 측정하기가 어렵고 기존 고객 경험에 연결하는 것이 거의 불가능했습니다.</p><p>자세한 내용은 [대화 인사이트](/help/conversation-insights/overview.md)를 참조하십시오.</p> | | 2026년 10월 8일<p>(원래 2026년 9월 22일로 계획됨)</p> |
| **구성 요소 설명 자동 생성** <br/>이제 차원, 지표, 계산된 지표, 세그먼트 및 날짜 범위에 대한 설명을 자동으로 생성할 수 있습니다. 이를 통해 Workspace 사용자는 특히 큰 구성 요소 라이브러리가 있는 조직에서 사용할 구성 요소를 이해할 수 있습니다. <p>단일 구성 요소에 대한 설명을 생성하거나 동시에 여러 구성 요소에 대한 설명을 생성할 수 있습니다.</p> <p>(참조할 설명서 링크입니다.)<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 2026년 10월 28일 |
| **Adobe Brand Visibility 통합**<br/> AI 기반 검색이 실제 웹 사이트 참여 및 비즈니스 성과로 이어지는 방식을 측정할 수 있도록 Adobe Brand Visibility을 조직의 Adobe Analytics 데이터와 연결합니다.<p>(설명서 링크는 추후 제공됩니다.)</p> | | 2026년 10월</p> |


### Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373, AN-492801, AN-488821, AN-488452, AN-486517, AN-478930 468325
**구성 요소**:
**연결**: AN-451458, AN-365942
**콘텐츠 분석**:
**안내식 분석**: AN-485600
**내보내기**: AN-489161, AN-467131, AN-464746, AN-469034, AN-447252, AN-437803, AN-394444
**데이터 보기**: AN-478732, AN-468836, AN-467851, AN-487651, AN-423592
**데이터 수집**: AN-489829, AN-489722, AN-469451, AN-467436, AN-467049, AN-466087, AN-465049, AN-463524, AN-457433, AN-490288, AN-487500, AN-390916, AN-342311
**구현**:
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695, AN-492330, AN-490564, AN-468293, AN-460921
**보고**: AN-479145, AN-469095, AN-468070, AN-467786, AN-456684, AN-465257, AN-422685, AN-406114, AN-356706, AN-322733
**세그먼테이션**: AN-486561, AN-278260
**예약된 보고서**: AN-479157
**공유된 지표 및 차원**:
**대상 분석**: AN-468237, AN-462553
**기타**: AN-469601, AN-462817, AN-362308, AN-349757, AN-326432, AN-326345, AN-324341, AN-309317

## 연기된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **전체 모집단 보고**<br/>&#x200B;이제 Customer Journey Analytics 연결에 있는 프로필 및 조회 데이터 세트에 정의된 엔터티를 분석하고 보고할 수 있습니다. 이러한 분석 및 보고는 이벤트 데이터 세트의 시간 기반 이벤트 시리즈를 능가합니다. <p>이 기능을 사용하면 비즈니스 고객 기반의 전체 범위를 반영하는 새로운 클래스의 쿼리, 지표 및 대상 정의를 사용할 수 있습니다.</p><p>(설명서 링크는 추후 제공됩니다.)</p> | | TBD<p>(원래 2026년 9월 22일로 계획됨)</p> |
| **스트리밍 미디어 서비스: 일정 데이터 지원** <br/>이제 과거 라이브 스트리밍 미디어 콘텐츠의 예약된 데이터를 업로드하여 시청자 수를 보다 쉽고 정확하게 추적할 수 있습니다.<p>다음은 일정 데이터 업로드를 지원하는 라이브 콘텐츠의 예입니다.</p><ul><li>FAST(무료 광고 지원 TV) 플랫폼</li><li>로컬 스트림</li><li>라이브 스포츠</li></ul><p>일정 데이터를 업로드하면 업로드 파일에서 지정한 시간 동안 실행된 개별 프로그램의 시청자 수 데이터를 추적할 수 있습니다. 특정 주제나 프로그램 세그먼트에 대한 시청자 수 데이터를 수집할 수도 있습니다.</p><p>이러한 기능은 스트리밍 미디어 컬렉션을 어떻게 구현하든 관계없이 사용할 수 있습니다.</p><p>이전에는 라이브 콘텐츠를 분석할 때 주어진 세션을 특정 프로그램에 정확하게 연결하는 것이 어려웠고, 주어진 세션을 개별 주제나 프로그램 세그먼트에 연결하는 것도 불가능했습니다.</p><p>자세한 내용은 [라이브 콘텐츠를 추적할 일정 데이터 업로드](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/track-schedule-data)를 참조하십시오.</p> | 2025년 10월 29일 | TBD<p>(원래 2025년 10월 29일로 계획됨)</p> |

>[!MORELIKETHIS]
>
>* [2026년 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2026.md)
>* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/ko/docs/analytics/release-notes/latest)
>* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/ko/docs/media-analytics/using/release-notes/release-notes)
>* [CX Enterprise 릴리스 노트](https://experienceleague.adobe.com/ko/docs/release-notes/experience-cloud/current)
>* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)

