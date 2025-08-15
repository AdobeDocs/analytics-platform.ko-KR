---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f959ac6c12280f745a986237c39d7fb1e7af5aa7
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 18%

---

# 최신 Adobe Customer Journey Analytics 릴리스 정보 (2025년 8월)

**마지막 업데이트**: 2025년 8월 14일 금요일


이 릴리스 정보는 2025년 8월 13일부터 9월 16일까지의 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **맵 시각화** | 맵 시각화는 모든 지표(계산된 지표 포함)의 시각적 맵을 작성할 수 있도록 해 주는 Analysis Workspace의 시각화입니다. 다른 지역 간에 지표 데이터를 식별하고 비교하는 데 유용합니다.<p>이전에는 맵 시각화를 Adobe Analytics에서만 사용할 수 있었습니다.</p><p>Customer Journey Analytics의 맵 시각화에는 Adobe Analytics의 맵 시각화에서 다음과 같은 개선 사항이 포함되어 있습니다.</p><ul><li>데이터 보기의 세그먼트를 데이터 소스로 사용합니다.</li><li>데이터 보기에서 차원을 구성하여 최대 1미터의 정확도입니다.</li><li>새로운 선택 도구를 사용하면 시각화에서 선택한 모든 영역에서 세그먼트, 대상, 트렌드 또는 분류를 만들 수 있습니다.</li></ul><p>자세한 내용은 [맵](/help/analysis-workspace/visualizations/map.md)을 참조하세요.</p> | 2025년 8월 13일 목요일 | 2025년 8월 25일 |
| **실시간 보고** | Customer Journey Analytics의 실시간 보고는 Analysis Workspace에 있는 하나 이상의 패널 내에 데이터와 시각화를 실시간으로 표시하고 업데이트합니다. | | 2025년 8월 15일 토요일 |
| **B2B 템플릿** | Customer Journey Analytics B2B edition에 라이선스를 부여하는 경우 이제 Adobe 템플릿 UI에서 다음과 같은 추가 B2B 템플릿을 사용할 수 있습니다. <ul><li>B2B 계정 참요 개요</li><li>B2B 기회 참여 개요</li><li>B2B 구매 그룹 활동</li></ul><p>(참조할 설명서 링크입니다.)</p> |  | 2025년 8월 15일 토요일 |
| **PDF로 다운로드된 프로젝트가 워크스테이션에 다운로드됨** | 프로젝트를 PDF으로 다운로드하면 PDF이 워크스테이션의 다운로드 폴더로 다운로드됩니다. <p>이전에는 프로젝트를 PDF으로 다운로드하면 새 브라우저 탭에서 고유한 URL로 PDF이 시작되었습니다.</p><p>자세한 내용은 [프로젝트 및 데이터 다운로드](/help/analysis-workspace/export/download-send.md)를 참조하십시오.</p> |  | 2025년 8월 25일 |
| **임시 스키마 지원** | [임시 스키마](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/tutorials/ad-hoc)는 CSV 파일 수집 및 특정 종류의 소스 연결 만들기를 포함하여 Experience Platform의 다양한 데이터 수집 워크플로우에서 사용됩니다. <p>이 기능을 사용하면 Customer Journey Analytics에서 임시 스키마 사용을 지원할 수 있습니다. 이제 연결 정의의 일부로, 임시 스키마를 기반으로 하는 데이터 세트를 선택하고 데이터 보기 및 작업 공간 프로젝트에서 데이터를 사용할 수 있습니다.</p> <p>(참조할 설명서 링크입니다.)</p> |  | 2025년 8월 28일 금요일 |
| **연결 결합** | Customer Journey Analytics 결합을 단순화합니다. 이제 데이터 세트를 복제하고 복제된 데이터 세트에 결합을 적용하는 대신 Customer Journey Analytics으로의 데이터 수집에 결합이 수행되므로 데이터 세트와 스키마가 복제될 필요가 없습니다. <p>또한 고객 지원을 통해 결합을 요청할 필요 없이 업데이트된 연결 UI에서 직접 결합을 시작할 수 있습니다.</p><p> *추가 노력이 필요하므로 이전에 전달한 릴리스 날짜가 푸시됩니다. 새 릴리스 날짜는 추가 릴리스 제한을 도입하는 휴가철과 겹칩니다. 이제 휴가 기간 동안 안정성을 보장하고 중단을 최소화하기 위해 단계별 롤아웃이 계획되었습니다.*</p> | 2025년 10월 말 | 2026년 1월 말 |
| **조회 키 제한 확장** | Customer Journey Analytics 패키지에 따라 이제 조회 데이터 세트에 최대 10억 개의 고유 키를 가질 수 있습니다. <p>자세한 내용은 Customer Journey Analytics [보호 기능](/help/technotes/guardrails.md#data-transfer-limits) 설명서에서 [데이터 전송 제한](/help/technotes/guardrails.md)을 참조하십시오.</p> |  | 2025년 8월 29일 토요일 |
| **플랫폼 스키마의 사용자 정의 맵 필드를 기반으로 지표 및 차원을 만듭니다** | Experience Platform 스키마에서 정의하는 사용자 정의 맵 필드를 이제 Customer Journey Analytics에서 사용할 수 있습니다.<p>Customer Journey Analytics에서 지표 및 차원을 생성할 때 다음 맵 필드를 사용할 수 있습니다.</p><ul><li>문자열을 문자열로 변환</li><li>문자열을 정수로 변환</li></ul><p>(참조할 설명서 링크입니다.)</p><p>Experience Platform의 맵 필드에 대한 자세한 내용은 [UI에서 맵 필드 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/ui/fields/map)를 참조하십시오.</p> |  | 2025년 8월 말 |
| **삭제된 프로젝트는 URL에서 즉시 사용할 수 없으며 예약된 게재에서 삭제됩니다** | 삭제된 프로젝트는 예약된 게재에서 즉시 삭제되며 더 이상 URL로 액세스할 수 없습니다.<p>이전에는 프로젝트가 예약된 게재에 포함되었으며 삭제된 후 60일 동안 URL로 액세스할 수 있었습니다.</p><p>프로젝트 삭제에 대한 자세한 내용은 [프로젝트 개요](/help/analysis-workspace/build-workspace-project/freeform-overview.md)를 참조하십시오.</p> | | 2025년 8월 말 |
| **스트리밍 미디어: Adobe Experience Platform으로 스트리밍 미디어 데이터를 수집하기 위한 XDM 필드를 업데이트했습니다** | 스트리밍 미디어 데이터를 Adobe Experience Platform으로 수집할 때, 스트리밍 미디어 매개변수 설명서의 “XDM 필드 경로” 제목 아래에 표시된 XDM 필드 경로는 더 이상 사용해서는 안 됩니다. 대신 2025년 5월 9일 이전에 스트리밍 미디어 데이터를 플랫폼으로 수집하도록 Analytics 소스 커넥터를 구현한 고객은 스트리밍 미디어 매개 변수 설명서의 &quot;보고 XDM 필드 경로&quot; 제목 아래에 표시된 대로 기존 구성을 mediaReporting 필드 경로로 마이그레이션해야 합니다.<p> 이러한 필드 경로는 [오디오 및 비디오 매개 변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/audio-video-parameters), [광고 매개 변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/ad-parameters), [챕터 매개 변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/chapter-parameters), [플레이어 상태 매개 변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/player-state-parameters) 및 [품질 매개 변수](https://experienceleague.adobe.com/ko/docs/media-analytics/using/implementation/variables/quality-parameters) 페이지에서 찾을 수 있으며 &quot;사용되지 않음&quot;으로 표시됩니다. (2025년 5월 9일 이후에 Analytics 소스 커넥터를 구현하고 이미 mediaReporting XDM 경로만 사용 중인 고객은 작업이 필요하지 않습니다.)</p><p>더 이상 사용되지 않는 XDM 필드 경로에 대한 데이터 수집은 2025년 10월 말까지 계속됩니다. 그 이후에는 더 이상 사용되지 않는 필드 경로가 완전히 제거되어 Adobe Experience Platform 스키마 UI에 더 이상 표시되지 않으며, mediaReporting 필드 경로를 통해서만 데이터가 전송됩니다.</p><p>자세한 내용은 [업데이트된 XDM 스트리밍 미디어 필드로 Analytics Source 커넥터 구현 마이그레이션](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)을 참조하십시오.</p><p>마이그레이션 지원에 대해서는 Adobe Consulting 서비스 또는 계정 팀에 문의하십시오. </p> |  | 2025년 10월 |

## Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-389683; AN-389534; AN-389207; AN-389066; AN-388687; AN-388478; AN-387089; AN-384865; AN-384560; AN-383486; AN-365768; AN-351639
**구성 요소**:
**Content Analytics**:
**안내식 분석**: AN-384426
**플랫폼**: AN-384410
**Report Builder**: AN-389336; AN-382775
**보고**:
**세그먼테이션**:
**공유된 지표 및 차원**:
**기타**: AN-388222; AN-384898; AN-387169


## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| 해당 사항 없음 | | |

## 관련 리소스

* [2025년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2025.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ko)
* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ko)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ko)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
