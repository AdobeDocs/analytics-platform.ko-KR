---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f41162d1c4c44f79c59585d1311cd2e431725103
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 96%

---

# 현재 Adobe Customer Journey Analytics 릴리스 정보 (2025년 8월)

**마지막 업데이트**: 2025년 8월 14일


이번 릴리스 정보에는 2025년 8월 13일부터 9월 16일까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **맵 시각화** | 맵 시각화는 Analysis Workspace의 모든 지표(계산된 지표 포함)의 시각적 맵을 작성할 수 있도록 해 주는 시각화 기능입니다. 지리적으로 다른 지역들의 지표 데이터를 식별하고 비교하는 데 유용합니다.<p>이전에는 Adobe Analytics에서만 맵 시각화 기능을 사용할 수 있었습니다.</p><p>Customer Journey Analytics의 맵 시각화에는 Adobe Analytics의 맵 시각화에서 다음과 같은 개선 사항이 포함되어 있습니다.</p><ul><li>데이터 보기의 모든 세그먼트를 데이터 소스로 사용합니다.</li><li>데이터 보기에서 차원을 구성하여 최대 1미터의 정확도를 얻을 수 있습니다.</li><li>새로운 선택 도구를 사용하면 시각화에서 선택한 모든 영역에서 세그먼트, 대상자, 트렌드 또는 분류를 생성할 수 있습니다.</li></ul><p>자세한 내용은 [맵](/help/analysis-workspace/visualizations/map.md)을 참조하십시오.</p> | 2025년 8월 13일 | 2025년 8월 25일 |
| **B2B 템플릿** | Customer Journey Analytics B2B Edition 라이선스를 구비하면 다음과 같은 추가 B2B 템플릿을 Adobe 템플릿 UI에서 사용할 수 있습니다. <ul><li>B2B 계정 참여 개요</li><li>B2B 기회 참여 개요</li><li>B2B 구매 그룹 활동</li></ul><p>자세한 내용은 [템플릿 사용](/help/analysis-workspace/templates/use-templates.md#b2b-templates)에서 [B2B 템플릿](/help/analysis-workspace/templates/use-templates.md)을 참조하세요.</p> |  | 2025년 8월 15일 |
| **PDF로 다운로드된 프로젝트가 워크스테이션에 다운로드됨** | 프로젝트를 PDF로 다운로드하면 해당 PDF는 워크스테이션의 다운로드 폴더에 다운로드됩니다. <p>이전에는 프로젝트를 PDF로 다운로드하면 고유한 URL이 있는 새 브라우저 탭에서 PDF가 실행되었습니다.</p><p>자세한 내용은 [프로젝트 및 데이터 다운로드](/help/analysis-workspace/export/download-send.md)를 참조하십시오.</p> |  | 2025년 8월 25일 |
| **임시 스키마 지원** | [임시 스키마](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/tutorials/ad-hoc)는 CSV 파일 수집 및 특정 종류의 소스 연결 만들기를 포함하여 Experience Platform의 다양한 데이터 수집 워크플로우에서 사용됩니다. <p>이 기능을 사용하면 Customer Journey Analytics에서 애드혹 스키마를 사용할 수 있습니다. 연결 정의의 일부로 이제 애드혹 스키마를 기반으로 데이터 세트를 선택하고 데이터 보기와 Workspace 프로젝트에서 해당 데이터를 사용할 수 있습니다.</p> <p>(참조할 설명서 링크입니다.)</p> |  | 2025년 8월 28일 |
| **조회 키 제한 확장** | Customer Journey Analytics 패키지에 따라 이제 조회 데이터 세트에 최대 10억 개의 고유 키를 포함할 수 있습니다. <p>자세한 내용은 Customer Journey Analytics [가드레일](/help/technotes/guardrails.md) 설명서의 [데이터 전송 한도](/help/technotes/guardrails.md#data-transfer-limits)를 참조하십시오.</p> |  | 2025년 8월 29일 |
| **Platform 스키마의 사용자 정의 맵 필드를 기반으로 지표 및 차원을 생성합니다.** | Experience Platform 스키마에서 정의한 사용자 정의 맵 필드를 이제 Customer Journey Analytics에서 사용할 수 있습니다.<p>Customer Journey Analytics에서 지표 및 차원을 생성할 때 다음 맵 필드를 사용할 수 있습니다.</p><ul><li>문자열에서 문자열로</li><li>문자열을 정수로 변환</li></ul><p>(참조할 설명서 링크입니다.)</p><p>Experience Platform의 맵 필드에 대한 자세한 내용은 [UI에서 맵 필드 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/ui/fields/map)를 참조하십시오.</p> |  | 2025년 8월 말 |
| **삭제된 프로젝트는 URL에서 즉시 사용할 수 없으며 예약된 게재에서 삭제됩니다.** | 삭제된 프로젝트는 예약된 게재에서 즉시 삭제되며 더 이상 URL로 액세스할 수 없습니다.<p>이전에는 프로젝트가 예약된 게재에 포함되었으며 삭제된 후 60일 동안 해당 URL을 통해 액세스할 수 있었습니다.</p><p>프로젝트 삭제에 대한 자세한 내용은 [프로젝트 개요](/help/analysis-workspace/build-workspace-project/freeform-overview.md)를 참조하십시오.</p> | | 2025년 8월 말 |
| **실시간 보고** | Customer Journey Analytics의 실시간 보고는 Analysis Workspace의 하나 이상의 패널 내에서 데이터와 시각화를 실시간으로 표시하고 업데이트합니다.<br/><br/>(다음 문서 링크) | | 2025년 9월 17일 (원래 2025년 8월 15일 출시 예정) |
| **스트리밍 미디어: 스트리밍 미디어 데이터를 Adobe Experience Platform으로 수집하기 위한 업데이트된 XDM 필드** | 스트리밍 미디어 데이터를 Adobe Experience Platform으로 수집할 때, 스트리밍 미디어 매개변수 설명서의 “XDM 필드 경로” 제목 아래에 표시된 XDM 필드 경로는 더 이상 사용해서는 안 됩니다. 대신, 2025년 5월 9일 이전에 플랫폼으로 스트리밍 미디어 데이터를 수집하기 위해 Analytics 소스 커넥터를 구현한 고객은 스트리밍 미디어 매개변수 설명서의 “보고 XDM 필드 경로” 제목 아래에 표시된 대로 기존 구성을 mediaReporting 필드 경로로 마이그레이션해야 합니다.<p> 이러한 필드 경로는 다음 페이지에서 찾을 수 있으며 “더 이상 사용되지 않음”으로 표시됩니다. [오디오 및 비디오 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/audio-video-parameters), [광고 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/ad-parameters), [챕터 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/chapter-parameters), [플레이어 상태 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/player-state-parameters) 및 [품질 매개변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/quality-parameters). (2025년 5월 9일 이후에 Analytics 소스 커넥터를 구현하고 이미 mediaReporting XDM 경로만 사용하고 있는 고객은 아무런 조치가 필요하지 않습니다.)</p><p>더 이상 사용되지 않는 XDM 필드 경로에 대한 데이터 수집은 2025년 10월 말까지 계속됩니다. 그 후에는 사용되지 않는 필드 경로가 완전히 제거되어 Adobe Experience Platform 스키마 UI에서 더 이상 표시되지 않으며, 데이터는 mediaReporting 필드 경로만 사용하여 전송됩니다.</p><p>자세한 내용은 [Analytics Source Connector 구현을 업데이트된 XDM 스트리밍 미디어 필드로 마이그레이션](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)을 참조하십시오.</p><p>마이그레이션 지원에 대해서는 Adobe Consulting 서비스 또는 계정 팀에 문의해 주십시오. </p> |  | 2025년 10월 |
| **연결부 결합** | Customer Journey Analytics 결합 단순화. 데이터 세트를 복제하고 복제된 데이터 세트에 결합을 적용하는 대신, 이제 Customer Journey Analytics에 데이터를 수집할 때 결합을 적용하므로 중복된 데이터 세트와 스키마가 필요하지 않습니다. <p>게다가 고객 지원을 통해 결합을 요청하는 대신, 이제 업데이트된 UI 연결에서 직접 결합을 시작할 수 있습니다.</p><p> *이전에 전달된 출시 날짜는 추가적인 노력이 필요하여 연기되었습니다. 새로운 출시 날짜가 휴일 시즌과 겹치면서 출시에 대한 추가적인 제약이 발생합니다. 이제 연휴 기간 동안 안정성을 보장하고 중단을 최소화하기 위해 단계적 출시가 계획되어 있습니다.*</p> | 2025년 10월 말 | 2026년 1월 말 |

## Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-389683; AN-389534; AN-389207; AN-389066; AN-388687; AN-388478; AN-387089; AN-384865; AN-384560; AN-383486; AN-365768; AN-351639
**구성 요소**:
**콘텐츠 분석**:
**가이드 분석**: AN-384426
**플랫폼**: AN-384410
**Report Builder**: AN-389336; AN-382775
**보고**:
**세분화**:
**공유된 지표 및 차원**:
**기타**: AN-388222; AN-384898; AN-387169


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
