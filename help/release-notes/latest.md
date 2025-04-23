---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a90bd3b146dce9bc3a177a77619c180febb406f3
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 78%

---

# 현재 Adobe Customer Journey Analytics 릴리스 정보 (2025년 4월)

**마지막 업데이트**: 2025년 4월 23일 목요일

이번 릴리스 정보에는 2025년 3월 27일부터 5월 15일까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **수치 차원의 “값 없음” 라인 항목 업데이트** | 수치 차원의 경우 이 업데이트를 통해 다음과 같은 작업을 수행할 수 있습니다.<ul><li>세그먼트에서 &quot;값 없음&quot; 차원 항목을 사용합니다.</li><li>“값 없음” 라인 항목에 대한 보고서에서 세부 분석을 수행할 수 있습니다.</li></ul> [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | 2025년 3월 27일 |
| **Adobe Content Analytics** | Adobe Content Analytics를 사용하면 대량의 콘텐츠 데이터를 빠르고 쉽게 조사하여 트렌드를 파악하고, 예외 항목을 발견하고, 콘텐츠 피로도를 식별하고, 콘텐츠 노출로부터 인사이트를 얻을 수 있습니다.<p>기본적으로 사전 설치된 보고 템플릿과 자산 검사기 등의 새로운 기능을 사용하면 시간을 절약할 수 있습니다. 이 기능을 사용하면 데이터에 맞춰 자산을 시각화할 수 있을 뿐만 아니라 각 자산에서 성과, 배치, 속성 등을 포함한 요약된 세부 정보를 확인할 수도 있습니다.<p>전체 고객 여정의 맥락에서 이러한 새로운 콘텐츠 데이터를 조사하여 중요한 비즈니스 질문에 답하고, 콘텐츠 성과를 평가하고, 세분화를 개선하고, 최적화 기회를 파악하고, 활성화를 위한 새로운 대상자를 정의할 수 있습니다.<p>Content Analytics는 Customer Journey Analytics의 추가 기능입니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/content-analytics/content-analytics) |  | 2025년 3월 27일 |
| **미디어 컬렉션: 새로운 Media Reporting XDM을 위한 Adobe Source Connector 업데이트** | Analytics Source Connector는 Adobe Analytics의 스트리밍 미디어 데이터를 Web SDK에서 사용하는 동일한 필드에 자동으로 매핑합니다. 이전에는 데이터가 이전 위치와 새 위치 모두에 매핑되어 있었지만 앞으로는 새 위치만 사용됩니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 2025년 3월 31일 |
| **Adobe Experience Platform에 스트리밍 미디어 데이터를 수집하기 위한 업데이트된 XDM 필드** | 스트리밍 미디어 데이터를 Adobe Experience Platform으로 수집할 때 더 이상 스트리밍 미디어 매개 변수 설명서의 &quot;XDM 필드 경로&quot; 제목 아래에 표시된 XDM 필드 경로를 사용하면 안 됩니다. 이러한 필드 경로는 [오디오 및 비디오 매개 변수](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [광고 매개 변수](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [챕터 매개 변수](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [플레이어 상태 매개 변수](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) 및 [품질 매개 변수](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters) 페이지에서 찾을 수 있으며 &quot;사용되지 않음&quot;으로 표시됩니다. <p>대신, 위에서 참조한 Streaming Media 매개 변수 설명서의 &quot;보고 XDM 필드 경로&quot; 머리글 아래에 표시된 대로 고객은 `mediaReporting` 필드 경로로 마이그레이션해야 합니다.<p>3개월의 전환 기간 동안 더 이상 사용되지 않는 XDM 필드 경로에 대한 데이터 수집은 계속됩니다. 그러나 2025년 7월 말에는 사용되지 않는 필드 경로가 완전히 제거되어 더 이상 Adobe Experience Platform 스키마 UI에 표시되지 않으며 `mediaReporting` 필드 경로를 사용해서만 데이터가 전송됩니다.<p>2025년 4월 22일 이전에 스트리밍 미디어 데이터를 플랫폼으로 수집하기 위해 Analytics 소스 커넥터를 구현한 고객은 새 필드 경로를 사용하도록 기존 구성을 마이그레이션해야 합니다. 이 마이그레이션은 2025년 7월 말까지 완료되어야 합니다. 마이그레이션 지원에 대해서는 Adobe Consulting 서비스 또는 계정 팀에 문의해 주십시오. 2025년 4월 22일 이후 Analytics 소스 커넥터를 구현하는 고객은 아무런 조치도 취할 필요가 없습니다.</p> |  | 2025년 4월 22일 |
| **용어 변경: “필터”에서 “세그먼트”로 변경** | 이전에는 Adobe Customer Journey Analytics에서 세그먼트를 “필터”라고 불렀습니다. 이 용어는 이제 Adobe Analytics와 일치하게 되었습니다. 이제 “필터”는 “세그먼트”로 호칭합니다. (물론 검색 필터는 여전히 “필터”라고 부릅니다.) UI가 업데이트되었으며 설명서도 현재 업데이트 중입니다. |  | 2025년 4월 16일 |
| **스티칭: XDM IdentityMap에서 영구 ID 및 임시 ID 가져오기** | 이 기능은 스티칭 프로세스에서 XDM identityMap에 저장된 ID를 사용할 수 있도록 지원합니다. identityMap은 필드 기반 스티칭의 영구 또는 임시 ID로 사용할 수 있으며 그래프 기반 스티칭의 영구 ID로 사용할 수 있습니다. identityMap에서 특정 네임스페이스나 기본 ID를 사용할 수 있습니다. (참조할 설명서 링크) |  | 2025년 4월 28일 화요일 |
| **데이터 보기 전반에 공유된 지표 및 차원** | 여러 데이터 보기에 차원 및 지표 설정을 적용할 수 있습니다. 공유 차원 또는 지표에 적용되는 변경 사항은 모든 해당 데이터 보기 전반에 걸쳐 해당 차원 또는 지표의 모든 인스턴스에 적용됩니다. 이 인터페이스를 사용하면 다수의 데이터 보기가 사용되는 경우 Customer Journey Analytics 관리자가 구성 요소를 더 쉽게 관리할 수 있습니다. (참조할 설명서 링크) |  | 2025년 4월 30일 |


## Customer Journey Analytics의 수정 사항

**Admin Console**: AN-370228
**Analysis Workspace**: AN-371933; AN- 371933; AN-371979
**대상자**: AN-373032
**구성 요소 설정**: AN-367400
**파생 필드**: AN-370614; AN-370959
**내보내기 위치**: AN-371670
**전체 테이블 내보내기**: AN-360492; AN-369204; AN-370755;AN-372294; AN-372363; AN-372754; AN-373040; AN-373081; AN-373168
**여정 캔버스**: AN-373294
**모바일 앱**: AN-363169; AN-368496; AN-371766
**제품 사용**: AN-369501
**보고**: AN-369085; AN-371094; AN-372580


## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 | | |

## 관련 리소스

* [2025년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2025.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
