---
title: 현재 Customer Journey Analytics 릴리스 노트
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
source-git-commit: 99135905f825cbef805c1664f6fb554497df3c3d
workflow-type: tm+mt
source-wordcount: 986
ht-degree: 27%

---

# 최신 Customer Journey Analytics 릴리스 정보 (2026년 8월)

**마지막 업데이트**: 2026년 8월 5일

이 릴리스 정보는 2026년 8월 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **여정 캔버스 개선 사항**<br>&#x200B;다음 여정 캔버스 개선 사항을 사용할 수 있습니다.<ul><li>여정을 이전 시간대와 비교합니다. 4주 전, 2분기 전, 1년 전 여정 또는 사용자 지정 날짜 범위와 현재 여정을 비교합니다.</li><li>선택한 노드의 경우 여정의 임의의 지점에서 선택한 노드 뒤에 오는 상위 차원 항목을 표시합니다. 선택한 노드가 분석의 주요 이벤트이고 이후에 사람들이 무슨 작업을 수행하는지 보려는 경우 사용합니다.<p>이전에는 선택한 노드의 앞 또는 뒤에 바로 위 노드만 표시할 수 있었습니다. </p></li><li>노드 사이의 화살표 모양 및 스타일을 변경합니다. 노드 사이에 화살표를 드래그하여 화살표의 모양(곡률)을 변경하고, 화살표를 마우스 오른쪽 버튼으로 클릭하여 스타일을 단색, 파선, 점선, 파선 점 또는 애니메이션 중 하나로 변경합니다.</li></ul><p></p>자세한 내용은 [여정 캔버스 시각화 구성](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)을 참조하십시오. |  | 2026년 8월 18일 |
| **추가 데이터 사용 레이블 지원**<br>&#x200B;이제 Customer Journey Analytics에서 데이터 집합 내의 요소에 대해 다음과 같은 추가 데이터 사용 레이블을 지원합니다.<ul><li>C2 - 서드파티 데이터 내보내기 제한(현재 사용 가능)</li><li>C3 - 직접 식별 가능한 데이터 조합 제한(현재 사용 가능)</li><li>C9 - 데이터 과학 제한(8월 또는 9월 릴리스 예정)</li></ul><p>자세한 내용은 [레이블, 정책 및 마케팅 작업](/help/data-views/data-governance.md)을 참조하십시오.</p> | | 2026년 8월 또는 9월 |
| **Content Analytics: 유료 미디어 데이터** <br/>유료 미디어를 이제 Content Analytics의 세 번째 채널로 사용할 수 있습니다.<p>(설명서 링크는 추후 제공됩니다.)</p> | | 2026년 8월 31일 |
| **B2B: 개인 대 계정 연결**<br> B2B 계정 연결은 계정 정보로 이벤트 데이터 세트를 강화하고 Customer Journey Analytics의 전체 고객 여정에서 전체 분석을 가능하게 합니다. <p>이벤트에 수집에 필요한 Customer Journey Analytics B2B edition의 계정 ID가 없는 경우 계정 결합은 사용자가 제공하는 개인-계정 매핑 데이터 세트를 사용하여 해당 정보를 자동으로 파생하고 추가합니다.</p><p>자세한 내용은 [B2B 계정 연결](/help/stitching/b2b/b2b-person-to-account-stitching.md)을 참조하세요.</p> | | 2026년 8월 31일 |
| **CJA Report API 첫 번째 호출 안내서**<br> Adobe Customer Journey Analytics API 첫 번째 호출 안내서는 기본 보고서 요청을 구성하는 지침 및 예를 제공합니다. | | 2026년 8월 10일 |
| **CJA Report API 날짜 트렌드 가이드**<br> Adobe Customer Journey Analytics API 날짜 트렌드 가이드는 기본 보고서 요청을 구성하는 지침 및 예를 제공합니다. | | 2026년 8월 17일 |
| **세그먼트를 보고 날짜 범위로 제한**<br/>&#x200B;세그먼트에 날짜 범위 구성 요소가 포함된 경우 Workspace 보고서의 데이터는 보고 날짜 범위를 초과할 수 있습니다.<p>이제 세그먼트에 포함된 날짜 구성 요소에 관계없이 결과를 보고 날짜 범위로 제한할 수 있는 새 옵션을 사용할 수 있습니다. <p>이 옵션은 최상위 컨테이너가 개인인 세그먼트를 만들거나 수정할 때 사용할 수 있습니다.</p><p>자세한 내용은 [세그먼트 빌드](/help/components/segments/seg-builder.md#components)를 참조하세요.</p> | 2026년 8월 26일 | 2026년 9월 9일 |
| **동의 정책 필터링 및 보고**<br>&#x200B;이제 Adobe Experience Platform 동의 정책과 일치하는 방문자를 보고할 수 있습니다. (동의 정책 차원 및 지표가 연결의 데이터 보기에 추가됩니다.)<p>또한 데이터가 Customer Journey Analytics에 수집되기 전에 동의하지 않는 방문자를 제외할 수 있습니다.</p><p>(참조할 설명서 링크입니다.)<!--For more information, see Consent reporting and filtering overview.--></p> | | 2026년 9월 |

### Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-466867, AN-465995, AN-465315, AN-465313, AN-464375, AN-463634, AN-463248, AN-463175, AN-463049, AN-462347, AN-462124, AN-461922, AN-458398, AN-457849, AN-455002, AN-453357, AN-456863, AN-459816, AN-459034, AN-460774, AN-460671 457760 443594
**구성 요소**:
**연결**: AN-464934, AN-460768
**콘텐츠 분석**:
**안내식 분석**:
**내보내기**: AN-451819, AN-448419, AN-456001
**데이터 보기**: AN-453201, AN-441965, AN-460967
**데이터 수집**: AN-462123, AN-451836, AN-453790, AN-459000, AN-456057, AN-461271, AN-459016, AN-460935
**구현**:
**Report Builder**: AN-465346, AN-464768, AN-464580, AN-464301, AN-463048, AN-462800, AN-457042, AN-461033, AN-459042, AN-454250, AN-451735, AN-450776, AN-450200 451665
**보고**: AN-463576, AN-462400, AN-456394, AN-455619, AN-459530, AN-454103, AN-452866, AN-461181
**세그먼테이션**: AN-459002, AN-457730, AN-457146
**예약된 보고서**: AN-455009, AN-460037, AN-462093
**공유된 지표 및 차원**:
**대상 분석**: AN-458292
**기타**: AN-466935, AN-462116, AN-454493, AN-457666, AN-457557, AN-456742, AN-437975, AN-460959

## 연기된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **스트리밍 미디어 서비스: 일정 데이터 지원** <br/>이제 과거 라이브 스트리밍 미디어 콘텐츠의 예약된 데이터를 업로드하여 시청자 수를 보다 쉽고 정확하게 추적할 수 있습니다.<p>다음은 일정 데이터 업로드가 지원되는 라이브 콘텐츠의 예입니다.</p><ul><li>FAST(무료 광고 지원 TV) 플랫폼</li><li>로컬 스트림</li><li>라이브 스포츠</li></ul><p>일정 데이터를 업로드하면 업로드 파일에서 지정한 시간 동안 실행된 개별 프로그램의 시청자 수 데이터를 추적할 수 있습니다. 특정 주제나 프로그램 세그먼트에 대한 시청자 수 데이터를 수집할 수도 있습니다.</p><p>이러한 기능은 스트리밍 미디어 컬렉션을 어떻게 구현하든 관계없이 사용할 수 있습니다.</p><p>이전에는 라이브 콘텐츠를 분석할 때 주어진 세션을 특정 프로그램에 정확하게 연결하는 것이 어려웠고, 주어진 세션을 개별 주제나 프로그램 세그먼트에 연결하는 것도 불가능했습니다.</p><p>자세한 내용은 [라이브 콘텐츠를 추적할 일정 데이터 업로드](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/track-schedule-data)를 참조하십시오. | 2025년 10월 29일 | TBD<p>(원래 2025년 10월 29일로 계획됨)</p> |

>[!MORELIKETHIS]
>
>* [2026년 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2026.md)
>* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/ko/docs/analytics/release-notes/latest)
>* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/ko/docs/media-analytics/using/release-notes/release-notes)
>* [CX 엔터프라이즈 릴리스 노트](https://experienceleague.adobe.com/ko/docs/release-notes/experience-cloud/current)
>* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)

