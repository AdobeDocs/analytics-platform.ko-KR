---
description: 기존 내보내기 관리
keywords: Analysis Workspace
title: 내보내기 관리
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
role: User
source-git-commit: 6f8a43acfba23d6faeff078873742315f1506699
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 3%

---

# 내보내기 관리

에 설명된 대로 전체 테이블을 내보낸 후 [클라우드로 Customer Journey Analytics 보고서 내보내기](/help/analysis-workspace/export/export-cloud.md)에서 내보내기를 사용할 수 있습니다. [!UICONTROL 내보내기] 의 탭 [!UICONTROL 내보내기] 페이지를 가리키도록 업데이트하는 중입니다.

사용자가 만든 내보내기만 볼 수 있습니다.

## 내보내기 필터링 및 검색

필요한 정보를 찾으려면 내보내기 목록을 필터링하거나 내보내기를 검색할 수 있습니다.

### 내보내기 목록 필터링

1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].

1. 다음 항목 선택 [!UICONTROL **내보내기**] 탭.

1. 다음 항목 선택 **필터** 아이콘.

   <!--add screenshot -->

   다음 기준으로 필터링할 수 있습니다.

   | 필터 | 설명 |
   |---------|----------|
   | [!UICONTROL **계정 유형**] | 내보내기와 연결된 계정 유형입니다. 다음 계정 유형을 사용할 수 있습니다. <ul><li>[!UICONTROL **AEP 데이터 랜딩 영역**]</li><li>[!UICONTROL **Amazon S3 역할 ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google 클라우드 플랫폼**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **상태**] | 내보내기의 상태입니다. 다음 상태를 사용할 수 있습니다. <ul><li>[!UICONTROL **활성**]: 예약된 내보내기가 아직 만료되지 않았거나 일회성 내보내기가 아직 완료되지 않았음을 나타냅니다. </li><li>[!UICONTROL **완료됨**]: 내보내기가 성공적으로 내보내기되었음을 나타냅니다. 예약된 내보내기의 경우 일정이 만료되었음을 나타냅니다.</li><li>[!UICONTROL **실패**]<p>다음과 같은 경우 내보내기에 실패할 수 있습니다. 마우스로 가리키기 [!UICONTROL **실패**] 장애에 대한 세부 정보를 볼 수 있는 상태. <ul><li>예약된 내보내기 만료</li><li>예약된 내보내기에 대한 행 제한에 도달했습니다. </li></ul> </p></li></ul> |
   | [!UICONTROL **빈도**] | 내보내기가 발생하는 빈도. 다음 빈도를 사용할 수 있습니다. <ul><li>[!UICONTROL **1회**]</li><li>[!UICONTROL **매일**]</li><li>[!UICONTROL **매주**]</li><li>[!UICONTROL **월별**]</li><li>[!UICONTROL **연간**]</li></ul> |

   {style="table-layout:auto"}

### 내보내기 검색

1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].

1. 다음 항목 선택 [!UICONTROL **내보내기**] 탭.

1. 검색 필드에 검색 중인 내보내기와 관련된 정보를 입력합니다. 테이블에서 사용할 수 있는 열에서 데이터를 검색할 수 있습니다.

## 내보내기 편집

내보내기의 속성, 형식, 예약 및 위치 정보를 편집할 수 있습니다.

1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].

1. 다음에서 [!UICONTROL **내보내기**] 탭에서 편집할 내보내기 옆에 있는 확인란을 선택합니다.

   여러 내보내기를 선택할 때는 이 옵션을 사용할 수 없습니다.

1. 선택 [!UICONTROL **편집**].

   다음 [!UICONTROL **전체 테이블 내보내기**] 대화 상자가 표시됩니다.

1. 사용 가능한 옵션을 업데이트합니다. 각 옵션에 대한 자세한 내용은 [Analysis Workspace에서 전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) 위치: [클라우드로 Customer Journey Analytics 보고서 내보내기](/help/analysis-workspace/export/export-cloud.md).

## 내보내기 복제

기존 내보내기를 복제할 수 있습니다.

1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].

1. 다음에서 [!UICONTROL **내보내기**] 탭에서 복제할 내보내기 옆에 있는 확인란을 선택합니다.

   여러 내보내기를 선택할 때는 이 옵션을 사용할 수 없습니다.

1. 선택 [!UICONTROL **복제**].

   내보내기의 복제본이 생성됩니다. 새 내보내기의 이름은 원본 내보내기의 이름과 일치합니다. _[!UICONTROL - 복사]_ 파일 이름에 추가됩니다.

1. (선택 사항) [새 내보내기 편집](#edit-an-export), 파일 이름 및 변경할 기타 모든 속성 포함

## 수동으로 내보내기 시작

예약된 내보내기 또는 이전에 완료된 일회성 내보내기에 대해 수동으로 내보내기를 시작할 수 있습니다.

1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].

1. 다음에서 [!UICONTROL **내보내기**] 탭에서 실행할 내보내기 옆의 확인란을 선택합니다.

   여러 내보내기를 선택할 때는 이 옵션을 사용할 수 없습니다.

1. 선택 [!UICONTROL **지금 내보내기**].

## 내보내기에 태그 지정

내보내기에 태그를 적용하면 [!UICONTROL 태그] 의 열 [!UICONTROL 내보내기] 페이지를 가리키도록 업데이트하는 중입니다. 다음을 참조하십시오 [열 구성](#configure-columns) 추가 정보.

1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].

1. 다음에서 [!UICONTROL **내보내기**] 탭에서 태깅할 하나 이상의 내보내기 옆에 있는 확인란을 선택합니다.

1. 선택 [!UICONTROL **태그 편집**].

1. 다음에서 [!UICONTROL **태그 내보내기**] 대화 상자에서 태그 이름을 입력하여 새 태그를 만들거나 드롭다운 메뉴에서 기존 태그를 선택합니다.

   선택한 내보내기 간의 모든 공통 태그가 태그 대화 상자에 표시됩니다. <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. 선택 [!UICONTROL **태그 적용**].

## 내보내기 삭제

내보내기 페이지에서 내보내기를 삭제할 수 있습니다. 삭제된 예약된 내보내기는 더 이상 전송되지 않습니다.

1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].

1. 다음에서 [!UICONTROL **내보내기**] 탭에서 삭제할 하나 이상의 내보내기 옆에 있는 확인란을 선택합니다.

1. 선택 [!UICONTROL **삭제**]&#x200B;을 선택한 다음 을 선택합니다. [!UICONTROL **삭제**] 확인 메시지가 표시되면

## 에서 열 구성 [!UICONTROL 내보내기] 페이지

에서 열을 추가하거나 제거할 수 있습니다. [!UICONTROL 내보내기] 탭으로 이동하여 표시할 정보를 구성합니다.

해당 열별로 내보내기를 정렬하려면 열 헤더를 선택하십시오. 기본적으로 내보내기는 내보내기가 마지막으로 수정된 날짜와 시간별로 정렬됩니다.

1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].

1. 다음에서 [!UICONTROL **내보내기**] 탭에서 **표 맞춤화** 아이콘 ![표 맞춤화](assets/customize-table-icon.png) 의 오른쪽 상단에 [!UICONTROL 내보내기] 페이지를 가리키도록 업데이트하는 중입니다.

   다음 열을 사용할 수 있습니다.

   | 사용 가능한 열 | 설명 |
   |---------|----------|
   | 이름 | 내보내기의 이름입니다. 사용자는에 설명된 대로 내보내기를 만들 때 이름을 지정합니다 [클라우드로 Customer Journey Analytics 보고서 내보내기](/help/analysis-workspace/export/export-cloud.md). |
   | ID | 내보낼 때 자동으로 할당되는 ID입니다. <!-- True? --> |
   | 데이터 보기 이름 | 내보내기와 연결된 데이터 보기의 이름입니다. 사용자는 내보내기를 만들 때 다음에 설명된 대로 데이터 보기를 선택할 수 있습니다. [클라우드로 Customer Journey Analytics 보고서 내보내기](/help/analysis-workspace/export/export-cloud.md). |
   | 상태 | 내보내기의 상태입니다. 사용 가능한 상태는 다음과 같습니다 [!UICONTROL 활성], [!UICONTROL 완료됨], 및 [!UICONTROL 실패].<p> **참고:** 내보내기 실패 문제 해결에 대한 자세한 내용은 다음을 참조하십시오. [실패한 내보내기 문제 해결](/help/components/exports/troubleshoot-exports.md).</p> |
   | 태그 | 내보내기에 적용되는 모든 태그를 표시합니다. 내보내기에 태그를 적용하는 방법에 대한 자세한 내용은 [내보내기에 태그 지정](#tag-an-export). |
   | 표 크기 (마지막 전송) | 마지막으로 전송된 내보내기 크기입니다. |
   | 작성자 | 내보내기를 만든 사용자입니다. |
   | 생성됨 | 내보내기가 생성된 날짜와 시간입니다. <!-- true? --> |
   | 위치 | 데이터를 내보낸 계정의 위치입니다. |
   | 계정 | 데이터를 내보낸 계정입니다. |
   | 빈도 | 내보내기가 전송되는 빈도입니다. 사용 가능한 옵션은 다음과 같습니다 [!UICONTROL 1회], [!UICONTROL 매일], [!UICONTROL 매주], [!UICONTROL 요일별 월간], [!UICONTROL 매월(날짜 기준)], [!UICONTROL 연간 날짜(월 기준)], 및 [!UICONTROL 특정 날짜별 연간]. |
   | 전송 시간 | 내보내기가 전송된 시간입니다. |
   | 마지막으로 보냄 | 내보내기가 마지막으로 전송된 시간입니다. |
   | 마지막 수정 | 내보내기가 마지막으로 수정된 시간입니다. 내보내기 페이지의 항목은 기본적으로 이 열을 기준으로 정렬됩니다. |
   | 계정 유형 | 데이터를 내보낸 클라우드 계정 유형입니다. 사용 가능한 계정 유형은 다음과 같습니다 [!UICONTROL Amazon S3 역할 ARN], [!UICONTROL Google 클라우드 플랫폼], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake], 및 [!UICONTROL Adobe Experience Platform]. |

   {style="table-layout:auto"}

1. 표시할 열이 선택되어 있는지 확인합니다. 선택한 열이 내보내기 페이지에 나타나고 관련 정보가 표시됩니다.
