---
title: 감사 로그
description: CJA 감사 로그를 보고 관리하는 방법을 알아보십시오.
hide: true
hidefromtoc: true
source-git-commit: 6cf2d5ccbeeea7baeea8a675f2b7e96e6203fe24
workflow-type: ht
source-wordcount: '849'
ht-degree: 100%

---


# 감사 로그

시스템에서 수행되는 활동의 투명성과 가시성을 높이기 위해 Customer Journey Analytics(CJA)를 사용하면 “감사 로그” 형식으로 다양한 서비스 및 기능에 대한 사용자 활동을 감사할 수 있습니다. 이러한 로그는 문제 해결에 도움이 될 수 있는 감사 추적을 형성하며, 기업이 건강 보험 이동성 및 책임법(HIPAA)과 같은 기업 데이터 관리 정책 및 규제 요구 사항을 효과적으로 준수하는 데 도움이 됩니다.

기본적으로 감사 로그는 **어떤 사람**&#x200B;이 **어떤** 작업을 **언제** 수행했는지 알려 줍니다. 로그에 기록된 각 작업에는 작업 유형, 날짜 및 시간, 작업을 수행한 사용자의 이메일 ID 및 작업 유형과 관련된 추가 속성을 나타내는 메타데이터가 포함됩니다.

이 주제에서는 UI에서 보고 관리하는 방법을 포함하여 CJA의 감사 로그를 다룹니다.

## 감사 로그 액세스

조직에서 이 기능을 활성화하면 활동이 발생할 때 감사 로그가 자동으로 수집됩니다. 로그 수집을 수동으로 활성화할 필요가 없습니다.

감사 로그를 보고 내보내려면 Adobe Console의 **[!UICONTROL 감사 로그 액세스]** 액세스 제어 권한이 필요합니다. CJA 기능에 대한 개별 권한을 관리하는 방법을 알아보려면 [액세스 제어 문서](/help/getting-started/cja-access-control.md)를 참조하십시오.

## UI에서 감사 로그 보기

CJA에서 **[!UICONTROL 도구]** > **[!UICONTROL 감사 로그]**&#x200B;로 이동합니다.

기본적으로 오늘과 어제의 감사 로그가 표시됩니다.

![감사 로그](assets/audit_ui.png)

오른쪽 상단의 열 선택기로 이동하여 표시할 열을 선택할 수 있습니다.

## 개별 로그 항목에 대한 정보 보기

설명 옆에 있는 정보(i) 버튼을 더블 클릭합니다.

![감사 로그](assets/info-button-audit.png)

다음 항목이 표시됩니다.

| 항목 | 설명 |
| --- | --- |
| 동작 이름 | 가능한 조치 목록은 다음과 같습니다. <ul><li>API 요청</li><li>승인</li><li>만들기</li><li>편집</li><li>내보내기</li><li>로그인 실패</li><li>로그인 성공</li><li>로그아웃</li><li>조직 변경</li><li>새로 고침</li><li>공유</li><li>전송</li><li>승인 취소</li><li>공유 안 함</li></ul> |
| 설명 | 작업, 구성 요소 유형(ID 포함) 및 기타 값의 요약입니다. |
| 사용자 이름 | 작업을 수행하는 사용자입니다. |
| 구성 요소 유형 | 가능한 구성 요소 유형은 다음과 같습니다. <ul><li>주석</li><li>대상자</li><li>계산된 지표</li><li>연결</li><li>데이터 그룹</li><li>데이터 보기</li><li>기능 액세스</li><li>필터</li><li>IMS 조직</li><li>모바일</li><li>프로젝트</li><li>보고서</li><li>예약된 프로젝트</li><li>사용자</li><li>사용자 그룹</li></ul> |
| IMS 조직 ID | Adobe Experience Cloud에 처음 로그인할 때 인스턴스에 부여되는 고유 ID입니다. 형식은 xxx@AdobeOrg여야 합니다. |
| 사용자 ID | 이 작업을 수행한 사용자를 식별하는 고유 ID입니다. |
| 만든 날짜 | 이 조치가 취해진 때입니다. |
| 이메일 | 작업을 수행하는 사용자의 이메일입니다. |
| 구성 요소 ID | 작업 중인 구성 요소를 식별하는 고유 ID입니다. |
| 로그인 ID | 이 로그 항목을 식별하는 고유 ID입니다. |
| 사용자 유형 | 가능한 구성 요소 유형은 IMS, OKTA입니다. |

### 감사 로그 필터링

깔때기 아이콘(![필터](assets/filter-icon.png))를 선택하면 결과를 좁히는 데 도움이 되는 필터 컨트롤 목록이 표시됩니다. 선택한 다양한 필터에 관계없이 마지막 1,000개의 레코드만 표시됩니다.

![필터](assets/filters.png)

UI의 감사 이벤트에 사용할 수 있는 필터는 다음과 같습니다.

| 필터 | 설명 |
| --- | --- |
| [!UICONTROL 날짜 범위] | 다른 날짜를 선택하거나 여러 날짜에 걸쳐 커서를 끌어 날짜 범위를 선택하여 다른 날짜 범위를 필터링합니다. 기본적으로 오늘과 어제 날짜가 선택됩니다. |
| [!UICONTROL 작업] | 다음 작업 중 하나 이상을 필터링합니다. <ul><li>API 요청</li><li>승인</li><li>만들기</li><li>편집</li><li>내보내기</li><li>로그인 실패</li><li>로그인 성공</li><li>로그아웃</li><li>조직 변경</li><li>새로 고침</li><li>공유</li><li>전송</li><li>승인 취소</li><li>공유 안 함</li></ul> |
| [!UICONTROL 사용자 ID] | 사용자 ID로 특정 사용자를 필터링합니다. 사용자 ID는 사용자 이름 옆에 있는 정보(i) 버튼을 선택하여 찾을 수 있습니다. |
| [!UICONTROL 이메일] | 특정 사용자의 이메일 주소를 필터링합니다. 이메일은 사용자 이름 옆에 있는 정보(i) 버튼을 선택하여 찾을 수 있습니다. |
| [!UICONTROL 구성 요소 ID] | 특정 구성 요소 ID를 필터링합니다. 사용자 ID는 원하는 구성 요소의 정보(i) 버튼을 선택하여 찾을 수 있습니다. |
| [!UICONTROL 구성 요소 유형] | 하나 이상의 구성 요소 유형을 필터링합니다. <ul><li>주석</li><li>대상자</li><li>계산된 지표</li><li>연결</li><li>데이터 그룹</li><li>데이터 보기</li><li>기능 액세스</li><li>필터</li><li>IMS 조직</li><li>모바일</li><li>프로젝트</li><li>보고서</li><li>예약된 프로젝트</li><li>사용자</li><li>사용자 그룹</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 감사 로그로 캡처된 이벤트 유형

다음 표에서는 감사 로그에서 구성 요소 유형을 기록하는 작업을 설명합니다.

| 구성 요소 유형 | 작업 |
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

{style=&quot;table-layout:auto&quot;}

## 감사 로그 다운로드

CSV 또는 JSON 형식의 감사 로그를 다운로드할 수 있습니다. 적용된 필터 또는 선택한 열이 다운로드된 파일에 반영됩니다.

1. 화면 오른쪽 맨 위에 있는 **[!UICONTROL 다운로드]**&#x200B;를 클릭합니다.
1. 포맷을 지정합니다.
1. **[!UICONTROL 다운로드]**&#x200B;를 다시 클릭합니다.

## API에서 감사 로그 관리

UI에서 수행할 수 있는 모든 작업은 API 호출을 사용하여 수행할 수도 있습니다. 자세한 내용은 [CJA API 참조 문서](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs)를 참조하십시오.