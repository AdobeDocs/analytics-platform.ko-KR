---
title: 감사 로그
description: Customer Journey Analytics 감사 로그를 보고 관리하는 방법에 대해 알아봅니다.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: 2ef96ad194f8c7acec35bd7635c650af4370531a
workflow-type: tm+mt
source-wordcount: '967'
ht-degree: 98%

---

# 감사 로그 {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_userid"
>title="사용자 ID"
>abstract="사용자 ID는 원하는 사용자가 포함된 로그 항목의 정보 버튼을 눌러 찾을 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_componentid"
>title="구성 요소 ID"
>abstract="구성 요소 ID는 원하는 구성 요소가 포함된 로그 항목의 정보 버튼을 눌러 찾을 수 있습니다."

<!-- markdownlint-enable MD034 -->


시스템에서 수행되는 활동의 투명성과 가시성을 높이기 위해 Adobe Customer Journey Analytics를 사용하면 “감사 로그” 형식으로 다양한 서비스 및 기능에 대한 사용자 활동을 감사할 수 있습니다. 이러한 로그는 문제 해결에 도움이 될 수 있는 감사 추적을 형성하며, 기업이 건강 보험 이동성 및 책임법(HIPAA)과 같은 기업 데이터 관리 정책 및 규제 요구 사항을 효과적으로 준수하는 데 도움이 됩니다.

기본적으로 감사 로그는 **어떤 사람**&#x200B;이 **어떤** 액션을 **언제** 수행했는지 알려 줍니다. 로그에 기록된 각 액션에는 작업 유형, 날짜 및 시간, 작업을 수행한 사용자의 이메일 ID 및 작업 유형과 관련된 추가 속성을 나타내는 메타데이터가 포함됩니다.

감사 로그는 90일 동안 유지됩니다. 이후 감사 로그는 자동으로 삭제됩니다.

이 주제에서는 UI에서 보고 관리하는 방법을 포함하여 Customer Journey Analytics의 감사 로그를 다룹니다.

## 감사 로그 액세스

조직에서 이 기능을 활성화하면 활동이 발생할 때 감사 로그가 자동으로 수집됩니다. 로그 수집을 수동으로 활성화할 필요가 없습니다.

감사 로그를 보고 내보내려면 Adobe Console의 **[!UICONTROL 감사 로그 액세스]** 액세스 제어 권한이 필요합니다. Customer Journey Analytics 기능에 대한 개별 권한을 관리하는 방법을 알아보려면 [액세스 제어 문서](../technotes/access-control.md)를 참조하십시오.

## UI에서 감사 로그 보기

Customer Journey Analytics에서 **[!UICONTROL 도구]** > **[!UICONTROL 감사 로그]**&#x200B;로 이동합니다.

기본적으로 오늘과 어제의 감사 로그가 표시됩니다.

![오늘과 어제를 강조 표시한 감사 로그. &#x200B;](assets/audit_ui.png)

오른쪽 상단의 열 선택기로 이동하여 표시할 열을 선택할 수 있습니다.

## 개별 로그 항목에 대한 정보 보기

설명 옆에 있는 정보(i) 버튼을 더블 클릭합니다.

![정보 버튼을 강조한 감사 로그. &#x200B;](assets/info-button-audit.png)

다음 항목이 표시됩니다.

* **[!UICONTROL 액션 이름]**: 수행된 액션. 가능한 값은 다음과 같습니다.
   * API_REQUEST: 모든 액션이 백엔드 API 요청을 트리거합니다. API 요청이 무엇이었는지에 대한 세부정보가 표시됩니다.
   * APPROVE: “승인” 액션이 수행되었습니다.
   * CREATE: “생성” 액션이 수행되었습니다.
   * 삭제: “삭제” 액션이 수행되었습니다.
   * EDIT: “편집” 액션이 수행되었습니다.
   * EMBARGO: [보고 활동 관리자](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/reporting-activity-manager/reporting-activity-cancel-requests)에서 요청을 제한하면 해당 작업이 감사 로그에 EMBARGO로 기록됩니다.
   * EXPORT: “내보내기” 액션이 수행되었습니다.
   * ORG_CHANGE: 조직 변경 액션이 수행되었습니다.
   * REFRESH: “새로 고침” 액션이 수행되었습니다.
   * SHARE: “공유” 액션이 수행되었습니다.
   * TRANSFER: 이전 액션이 수행되었습니다.
   * UNAPPROVE: “승인 취소” 액션이 수행되었습니다.
   * UNSHARE: “공유 취소” 액션이 수행되었습니다.
* **[!UICONTROL 생성 날짜]**: 액션이 수행된 날짜 및 시간.
* **[!UICONTROL 설명]**: 액션 요약.
* **[!UICONTROL 사용자 이름]**: 액션을 수행한 사용자. 경우에 따라 사용자 이름이 누락될 수도 있습니다. [제품 사용](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/tools/product-usage/usage-overview) 기능은 항상 로그인 사용자 이름을 포함하므로 사용하는 것을 고려해 보십시오.
* **[!UICONTROL 이메일]**: 액션을 수행한 사용자의 이메일 주소.
* **[!UICONTROL 구성 요소 이름]**: 사용자가 액션을 취한 구성 요소.
* **[!UICONTROL 구성 요소 유형]**: 구성 요소의 유형. 가능한 값은 다음과 같습니다.
   * 주석
   * 대상자
   * CALCULATED_METRIC
   * 연결
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * 필터
   * IMS_ORG
   * 모바일
   * 프로젝트(Workspace)
   * 보고서
   * SCHEDULED_PROJECT
   * 사용자
   * USER_GROUP
* **[!UICONTROL 구성 요소 ID]**: 사용자가 액션 수행한 구성 요소의 ID.
* **[!UICONTROL IMS 조직 ID]**: 조직의 IMS ID이며 형식은 `ABC123@AdobeOrg`입니다.
* **[!UICONTROL 로그 ID]**: 이 로그 항목을 식별하는 고유 ID.
* **[!UICONTROL 사용자 ID]**: 액션을 수행한 사용자를 식별하는 고유 ID.
* **[!UICONTROL 사용자 유형]**: 사용된 인증 유형. 유효 값 항목:
   * IMS
   * OKTA

### 감사 로그 필터링

깔때기 아이콘(![필터](assets/filter-icon.png))를 선택하면 결과를 좁히는 데 도움이 되는 필터 컨트롤 목록이 표시됩니다. 선택한 다양한 필터에 관계없이 마지막 1,000개의 레코드만 표시됩니다.

![날짜 범위에 대한 필터를 보여 주는 감사 로그.](assets/filters.png)

UI의 감사 이벤트에 사용할 수 있는 필터는 다음과 같습니다.

| 필터 | 설명 |
| --- | --- |
| [!UICONTROL 날짜 범위] | 다른 날짜를 선택하거나 여러 날짜에 걸쳐 커서를 끌어 날짜 범위를 선택하여 다른 날짜 범위를 필터링합니다. 기본적으로 오늘과 어제 날짜가 선택됩니다. |
| [!UICONTROL 액션] | 위에 나열된 모든 액션 이름을 필터링합니다. |
| [!UICONTROL 사용자 ID] | 사용자 ID로 특정 사용자를 필터링합니다. 사용자 ID는 사용자 이름 옆에 있는 정보(i) 버튼을 선택하여 찾을 수 있습니다. |
| [!UICONTROL 이메일] | 특정 사용자의 이메일 주소를 필터링합니다. 이메일은 사용자 이름 옆에 있는 정보(i) 버튼을 선택하여 찾을 수 있습니다. |
| [!UICONTROL 구성 요소 ID] | 특정 구성 요소 ID를 필터링합니다. 사용자 ID는 원하는 구성 요소의 정보(i) 버튼을 선택하여 찾을 수 있습니다. |
| [!UICONTROL 구성 요소 유형] | 위에 나열된 모든 구성 요소 유형을 필터링합니다. |

{style="table-layout:auto"}

## 감사 로그로 캡처된 이벤트 유형

다음 테이블에서는 감사 로그에서 구성 요소 유형을 기록하는 액션을 설명합니다.

| 구성 요소 유형 | 액션 |
| --- | --- |
| [!UICONTROL 주석] | <ul><li>만들기</li><li>삭제</li><li>편집</li></ul> |
| [!UICONTROL 대상자] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li><li>내보내기</li><li>새로 고침</li></ul> |
| [!UICONTROL 계산된 지표] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li></ul> |
| [!UICONTROL 연결] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li></ul> |
| [!UICONTROL 데이터 보기] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li></ul> |
| [!UICONTROL 날짜 범위] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li></ul> |
| [!UICONTROL 필터] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li></ul> |
| [!UICONTROL IMS 조직] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li></ul> |
| [!UICONTROL 프로젝트] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li></ul> |
| [!UICONTROL 보고서] | <ul><li>API 요청</li></ul> |
| [!UICONTROL 예약된 프로젝트] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li></ul> |
| [!UICONTROL 사용자] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li></ul> |
| [!UICONTROL 사용자 그룹] | <ul><li>API 요청</li><li>만들기</li><li>삭제</li><li>편집</li></ul> |

{style="table-layout:auto"}

## 감사 로그 다운로드

CSV 또는 JSON 형식의 감사 로그를 다운로드할 수 있습니다. 적용된 필터 또는 선택한 열이 다운로드된 파일에 반영됩니다.

1. 화면 오른쪽 맨 위에 있는 **[!UICONTROL 다운로드]**&#x200B;를 클릭합니다.
1. 포맷을 지정합니다.
1. **[!UICONTROL 다운로드]**&#x200B;를 다시 클릭합니다.

## API에서 감사 로그 관리

UI에서 수행할 수 있는 모든 액션은 API 호출을 사용하여 수행할 수도 있습니다. 자세한 내용은 [Customer Journey Analytics API 참조 문서](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs)를 참조하십시오.
