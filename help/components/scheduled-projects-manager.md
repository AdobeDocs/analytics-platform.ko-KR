---
description: Analysis Workspace에서 지표를 사용하는 두 가지 방법이 있습니다.
title: 지표
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 26%

---

# 예약된 프로젝트

예약된 Analysis Workspace 프로젝트는 **[!UICONTROL 구성 요소]** > **[!UICONTROL 예약된 프로젝트]**&#x200B;를 사용하여 Customer Journey Analytics에서 관리할 수 있습니다.

**[!UICONTROL 개의 예약된 프로젝트]**&#x200B;에서 반복되는 프로젝트 일정을 편집하고 삭제할 수 있습니다. 검색 필드의 ![검색](/help/assets/icons/Search.svg)을 사용하여 일정을 검색합니다. 또는 왼쪽 패널의 ![필터](/help/assets/icons/Filter.svg) 필터 옵션을 사용하십시오. **[!UICONTROL 태그]**, **[!UICONTROL 소유자]** 및 **[!UICONTROL 기타 필터]**&#x200B;별로 필터링할 수 있습니다.

예약된 프로젝트 목록에는 다음에 대한 열이 표시됩니다.

| 필드 | 설명 |
| --- | --- |
| ![별](/help/assets/icons/Star.svg) | ![별](/help/assets/icons/Star.svg)을(를) 선택하면 이 예약이 즐겨찾기에 등록됩니다. |
| **[!UICONTROL 예약 ID]** | 주로 디버깅을 위해 사용되는 ID입니다. |
| [!UICONTROL 이름] | 이 프로젝트의 이름.<br/>예약된 프로젝트에 대한 자세한 내용을 보려면 ![InfoOutline](/help/assets/icons/InfoOutline.svg)을(를) 선택하십시오.<br/>컨텍스트 메뉴를 열려면 ![자세히](/help/assets/icons/More.svg)를 선택하십시오. 이 메뉴에서 다음 작업을 수행할 수 있습니다.<ul><li>예약된 프로젝트 ![삭제](/help/assets/icons/Delete.svg) **[!UICONTROL 삭제]**</li><li>예약된 프로젝트에 대해 ![레이블](/help/assets/icons/Labels.svg) **[!UICONTROL 태그]**.</li><li>예약된 프로젝트에 대해 ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 승인]**.</li><li>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV 내보내기]**: 예약된 프로젝트를 CSV 파일로 내보냅니다.</li></ul> |
| **[!UICONTROL 소유자]** | 프로젝트를 만들고 소유하고 있는 사람입니다. |
| **[!UICONTROL 태그]** | (선택 사항) 태그 지정은 프로젝트를 구성하는 좋은 방법입니다. 모든 사용자는 태그를 만든 후 하나의 프로젝트에 하나 이상의 태그를 적용할 수 있습니다. 그렇지만 본인이 소유하거나 본인과 공유된 프로젝트에 대한 태그만 볼 수 있습니다. |
| **[!UICONTROL 다음으로 배달됨]** | 이 예약된 프로젝트의 수신자입니다. |
| **[!UICONTROL 만료 날짜]** | 일정 빈도에 상관없이 만료일을 최대 1년으로 설정할 수 있습니다. |
| **[!UICONTROL 빈도]** | 이 일정 프로젝트를 한 명 이상의 수신자에게 보낼 빈도. |
| **[!UICONTROL 실행 시간]** | 이 예약된 프로젝트를 보내고자 하는 하루 중의 시간 |
| **[!UICONTROL 쿼리 개수]** | 이 프로젝트에 대한 쿼리 개수 |
| **** | 예약된 프로젝트에 대해 정의된 가장 긴 날짜 범위입니다. 이 값은 성능 문제를 조사하는 데 적절할 수 있습니다. 자세한 내용은 [보고 활동 관리자](/help/reporting-activity-manager/reporting-activity-overview.md)를 참조하십시오. |
| **[!UICONTROL 쿼리 개수]** | 예약된 프로젝트에 대해 실행된 쿼리 수입니다. 이 값은 성능 문제를 조사하는 데 적절할 수 있습니다. 자세한 내용은 [보고 활동 관리자](/help/reporting-activity-manager/reporting-activity-overview.md)를 참조하십시오. |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을(를) 사용하여 표시할 열을 구성할 수 있습니다.

예약된 프로젝트 는 특정 사용자가 만든 항목을 보여 줍니다. 애플리케이션에서 사용자 계정이 비활성화된 경우 모든 예약된 배달이 중지됩니다.



## 작업

다음은 예약된 프로젝트 관리자의 일반적인 작업입니다. 예약된 프로젝트를 두 개 이상 선택할 때 컨텍스트 메뉴 또는 파란색 작업 표시줄에서 작업을 선택할 수 있습니다.

| 액션 | 설명 |
|---|---|
| **[!UICONTROL 승인]** | 예약된 프로젝트를 승인합니다. |
| **[!UICONTROL 편집]** | 예약 제목을 클릭하여 게재 설정을 업데이트합니다. |
| **[!UICONTROL 삭제]** | 선택한 프로젝트 일정을 삭제합니다. 프로젝트 자체는 삭제되지 않습니다. |
| **[!UICONTROL 태그]** | 프로젝트를 더 쉽게 찾을 수 있도록 예약된 프로젝트에 태그를 지정합니다. |

![필터](/help/assets/icons/Filter.svg) 필터를 사용하여 다음 작업을 수행할 수도 있습니다.

| 액션 | 설명 |
|---|---|
| **[!UICONTROL 실패한 일정 보기]** | **[!UICONTROL 기타 필터]**(으)로 이동한 다음 **[!UICONTROL 실패]**&#x200B;를 선택하여 실패한 일정을 확인합니다. |
| **[!UICONTROL 만료된 일정 보기]** | **[!UICONTROL 기타 필터]**(으)로 이동한 다음 **[!UICONTROL 만료됨]**&#x200B;을(를) 선택하여 만료된 일정을 확인합니다. 예약의 제목을 클릭하여 새 배달 일정을 설정합니다. |

