---
title: Report Builder에서 예약된 통합 문서 관리
description: Report Builder에서 예약된 통합 문서를 관리하는 방법에 대해 알아봅니다.
role: User, Admin
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 0a0427d9-223e-410b-a8ef-8601390d88aa
source-git-commit: 9d5c895672e422a82ef68b0af6cd85359c9b11ea
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 5%

---

# 예약된 통합 문서 관리

다음 문서에 설명된 대로 이메일을 통해 공유하거나 클라우드 대상으로 내보내는 방식으로 통합 문서를 예약할 수 있습니다.

* [이메일을 통해 공유하여 통합 문서 예약](/help/report-builder/schedule-reportbuilder.md)

* [통합 문서를 클라우드 대상으로 내보내기 예약](/help/report-builder/report-builder-export.md)

다음 섹션에서는 통합 문서를 예약한 후 관리하는 방법을 설명합니다.

## 예약된 통합 문서 보기 및 관리

**[!UICONTROL 통합 문서]** 탭에서 예약된 모든 통합 문서를 보고 관리할 수 있습니다.

1. Report Builder 허브에서 **[!UICONTROL 예약]**&#x200B;을 선택하십시오.

1. **[!UICONTROL 통합 문서]** 탭을 선택합니다. 모든 예약된 통합 문서 목록이 표시됩니다. (또는 **[!UICONTROL 레거시]** 탭을 선택하여 새 Report Builder로 마이그레이션해야 하는 레거시 통합 문서 목록을 볼 수 있습니다.)

   ![예약된 통합 문서](assets/scheduled-workbooks.png){zoomable="yes"}

1. 다음 중 하나를 수행합니다.

   * 아이콘 위로 마우스를 가져가 예약된 통합 문서의 상태를 확인할 수 있습니다.

   * 검색 필드 ![검색](/help/assets/icons/Search.svg)에서 특정 예약된 통합 문서를 검색합니다.

   * 표시할 열을 정의하려면 열 아이콘 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을(를) 선택하십시오.

   * 필터 아이콘 ![필터 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)을 선택한 다음 [!UICONTROL **모두 표시**]&#x200B;를 선택하여 지정된 조직의 예약된 통합 문서를 모두 표시합니다.

1. 하나 이상의 통합 문서를 선택하십시오.

   ![선택한 일정 통합 문서](assets/scheduled-workbooks-selected.png){zoomable="yes"}

   다음 옵션을 사용할 수 있습니다.

   | 옵션 | 설명 |
   |---|---|
   | ![편집](/help/assets/icons/Edit.svg) | 선택한 통합 문서의 일정을 편집합니다. |
   | ![기록](/help/assets/icons/History.svg) | 선택한 통합 문서의 내역을 표시합니다. |
   | ![일시 중지](/help/assets/icons/Pause.svg) | 선택한 통합 문서의 일정을 일시 중지합니다. |
   | ![재생](/help/assets/icons/Play.svg) | 선택한 통합 문서의 일정을 다시 시작합니다. |
   | ![다운로드](/help/assets/icons/Download.svg) | 선택한 통합 문서를 새 통합 문서로 다운로드합니다. |
   | ![삭제](/help/assets/icons/Delete.svg) | 선택한 통합 문서의 일정을 삭제합니다. |


## 예약된 통합 문서의 내역 및 상태

**[!UICONTROL 기록]** 탭에서 예약된 통합 문서의 기록 및 상태를 볼 수 있습니다.

1. Report Builder 허브에서 **[!UICONTROL 예약]**&#x200B;을 선택하십시오.

1. **[!UICONTROL History]** 탭을 선택하십시오. 모든 예약된 통합 문서 목록이 표시됩니다.

   ![예약된 내역](assets/scheduled-workbooks-history.png){zoomable="yes"}

   ![검색](/help/assets/icons/Search.svg)을 사용하여 목록의 특정 통합 문서를 검색하십시오.
표시할 열을 정의하려면 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을(를) 사용합니다.

   **[!UICONTROL History]** 탭에서는 예약된 각 작업의 상태를 검토할 수 있습니다. 별도의 행에는 예약된 각 작업의 상태 변경 내용이 설명되어 있습니다.

   * ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg)은 통합 문서가 성공적으로 전송되었음을 나타냅니다.
   * ![AlertRed](/help/assets/icons/AlertRed.svg)은(는) 오류가 발생했음을 나타냅니다.

또는 ![통합 문서](/help/assets/icons/History.svg) 탭에서 하나 이상의 선택한 통합 문서에 대해 **[!UICONTROL 기록]**&#x200B;을 선택할 수 있습니다. 이 작업은 선택한 항목별로 필터링된 목록이 있는 **[!UICONTROL 기록]** 탭을 표시합니다. 필터를 제거하려면 ![CrossSize75](/help/assets/icons/CrossSize75.svg)을(를) 선택하십시오.
