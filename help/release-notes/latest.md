---
title: 현재 Customer Journey Analytics 릴리스 노트
description: 현재 기간에 대한 새로운 기능, 해결된 문제 및 지연된 릴리스를 포함하여 최신 Customer Journey Analytics 릴리스 정보를 확인하십시오.
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
source-git-commit: 0a83f4d08806b4d9b97265989f9d687011b232c3
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 28%
---
# 최신 Customer Journey Analytics 릴리스 정보 (2026년 10월)

**마지막 업데이트**: 2026년 10월 7일

이 릴리스 정보는 2026년 10월 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **Customer Journey Analytics MCP 서버에 대한 읽기 전용 권한**<br/>&#x200B;이제 관리자는 사용자에게 Customer Journey Analytics MCP 서버에 대한 읽기 전용 액세스 권한을 부여할 수 있습니다. 새 [!UICONTROL MCP 읽기 전용] 권한 항목은 사용자에게 프로젝트, 세그먼트 또는 계산된 지표를 만들지 않고도 모든 읽기 전용 도구에 액세스할 수 있도록 합니다.<p>기존 [!UICONTROL MCP 액세스] 권한 항목의 이름이 [!UICONTROL MCP 전체 액세스]&#x200B;(으)로 변경되었습니다. 이 권한이 있는 사용자는 구성 요소를 만들거나, 변경하거나, 삭제하는 도구를 포함하여 모든 도구에 대한 액세스 권한을 유지합니다.</p><p>자세한 내용은 [Customer Journey Analytics MCP 서버](https://developer.adobe.com/analytics-mcp/docs/cja/)를 참조하십시오.</p> | | 2026년 10월 6일 |
| **대화 통찰력을 사용하여 Analysis Workspace에서 LLM 고객 경험 분석**<br/> Customer Journey Analytics은 이제 구조화되지 않은 채팅 데이터를 Analysis Workspace으로 가져와서 사용자의 자산 전체에서 발생하는 LLM 기반 탐색 및 구매 경험을 보고할 수 있습니다.<p>이 기능을 사용하여 다음과 같은 작업을 수행할 수 있습니다.</p><ul><li>Web SDK을 통해 대화형 에이전트(조직의 사용자 지정 에이전트 또는 Adobe Brand Concierge)의 프롬프트, 응답 및 에이전트 메타데이터를 수집합니다.</li><li>고객이 무엇을 묻고 있는지, 에이전트가 어떻게 반응하는지, 고객이 상호 작용에 대해 어떻게 느끼는지 이해할 수 있도록 의도, 톤 및 감정을 분석합니다.</li><li>기존 스키마, 데이터 세트 및 데이터 보기를 사용하여 규모에 맞게 분석한 다음 Analysis Workspace에서 통찰력을 표시합니다.</li><li>상담원 상호 작용을 더 광범위한 고객 여정과 연결하여 대화를 결과와 연결하여 전환, 참여 등에 대한 실질적인 영향을 측정할 수 있습니다.</li></ul><p>이전에는 LLM 기반 여정을 측정하기가 어렵고 기존 고객 경험에 연결하는 것이 거의 불가능했습니다.</p><p>자세한 내용은 [대화 인사이트](/help/conversation-insights/overview.md)를 참조하십시오.</p> | | 2026년 10월 8일<p>(원래 2026년 9월 22일로 계획됨)</p> |
| **구성 요소 설명 자동 생성** <br/>이제 차원, 지표, 계산된 지표, 세그먼트 및 날짜 범위에 대한 설명을 자동으로 생성할 수 있습니다. 이를 통해 Workspace 사용자는 특히 큰 구성 요소 라이브러리가 있는 조직에서 사용할 구성 요소를 이해할 수 있습니다. <p>단일 구성 요소에 대한 설명을 생성하거나 동시에 여러 구성 요소에 대한 설명을 생성할 수 있습니다.</p> <p>(참조할 설명서 링크입니다.)<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 2026년 10월 28일 |
| **Adobe Brand Visibility 통합**<br/> AI 기반 검색이 실제 웹 사이트 참여 및 비즈니스 성과로 이어지는 방식을 측정할 수 있도록 Adobe Brand Visibility을 조직의 Customer Journey Analytics 데이터와 연결합니다.<p>(설명서 링크는 추후 제공됩니다.)</p> | | 2026년 10월 |


### Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-495340, AN-494789, AN-493307, AN-468900
**구성 요소**: AN-492523
**연결**: AN-492236
**콘텐츠 분석**:
**안내식 분석**: AN-495592
**내보내기**: AN-495077, AN-494337, AN-486563, AN-469919, AN-462560, AN-462372
**데이터 보기**: AN-492093, AN-467770, AN-455367, AN-444467
**데이터 수집**: AN-496439, AN-495339, AN-493456, AN-491984, AN-490515, AN-490479, AN-470065
**구현**:
**Report Builder**: AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**보고**: AN-495661, AN-493562, AN-487058, AN-478768
**세분화**:
**예약된 보고서**: AN-491103, AN-468049
**공유된 지표 및 차원**: AN-493722
**대상 분석**: AN-469101
**기타**: AN-493865

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

