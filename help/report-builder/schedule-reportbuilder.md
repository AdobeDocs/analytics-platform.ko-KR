---
title: Customer Journey Analytics에서 Report Builder를 사용하여 통합 문서를 예약하는 방법
description: Report Builder에서 예약 기능을 사용하는 방법 알아보기
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 7429d8f9-1e8f-4fbd-8b04-cbe7adbff3e2
source-git-commit: 6dd8a70293161ff58361953a7e48a98834b7abe0
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 13%

---

# 통합 문서 예약

통합 문서를 저장하고 분석을 완료한 후 예약 기능을 사용하여 팀의 다른 사용자와 통합 문서를 공유할 수 있습니다. 예약 기능을 사용하면 통합 문서의 데이터를 자동으로 새로 고치는 일정을 만들 수 있습니다. Excel 통합 문서 파일을 특정 날짜와 시간에 지정된 대상자에 대한 첨부 파일로 이메일로 보냅니다. 일정을 설정하면 수신자는 정기적으로 자동 업데이트됩니다. 예약 기능을 사용하여 자동 업데이트를 예약하지 않고도 통합 문서를 한 번에 전송할 수도 있습니다.

단일 통합 문서에 여러 일정을 만들 수 있습니다. 예를 들어 매일 팀에게 통합 문서를 보내고 일주일에 한 번 관리자에게 보내는 두 개의 일정을 만듭니다.

일정 기능을 사용하면 통합 문서에 대한 암호 보호를 설정하고 이전에 예약된 통합 문서를 편집할 수도 있습니다.


>[!BEGINSHADEBOX]

데모 비디오는 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [통합 문서 예약](https://video.tv.adobe.com/v/3417507/?quality=12&learn=on&captions=kor){target="_blank"}을 참조하십시오.

>[!ENDSHADEBOX]


## 통합 문서 예약

워크북을 예약하려면

1. 통합 문서 Excel 파일(.xlsx)을 개인 또는 그룹에 자동으로 배포할 수 있도록 일정을 만들려면 Report Builder 허브에서 **[!UICONTROL 일정]**&#x200B;을 선택하세요.

   ![일정을 만들려면 [일정] 단추를 선택하십시오.](./assets/schedule.png){zoomable="yes"}

1. 새 예약된 통합 문서를 만들려면 **[!UICONTROL 통합 문서 예약]** 또는 ![추가](/help/assets/icons/Add.svg)를 선택하십시오.

   ![통합 문서 예약 창](./assets/schedule-workbook.png){zoomable="yes"}

   예약 창에는 통합 문서 이름과 통합 문서를 마지막으로 수정한 날짜 등 통합 문서에 대한 사전 정의된 일부 정보가 표시됩니다.

### 파일

**[!UICONTROL 파일]** 섹션에서 파일 형식, 이름 및 암호를 자세히 입력하여 파일을 보호합니다.

![일정 창.](./assets/schedule-pane.png){zoomable="yes"}

1. 아직 선택하지 않은 경우 ![TableSelect](/help/assets/icons/TableSelect.svg)을(를) 사용하여 현재 통합 문서를 선택하십시오.

1. (선택 사항) **[!UICONTROL 파일 이름]**&#x200B;을 입력합니다.

   통합 문서 파일 이름은 기본적으로 통합 문서의 이름으로 설정되지만 원하는 경우 파일 이름을 변경할 수 있습니다.

1. **[!UICONTROL 파일 형식]**&#x200B;을(를) 선택하십시오.

   * **[!UICONTROL Excel]**
   * **[!UICONTROL PDF]**
   * **[!UICONTROL CSV]**

   **[!UICONTROL CSV]**&#x200B;을(를) 선택하면 예약된 통합 문서가 zip 첨부 파일로 전송됩니다. 일부 회사 이메일 관리자는 zip 첨부 파일이 있는 이메일을 차단할 수 있습니다. 그에 따라 경고가 표시됩니다.

1. (선택 사항) **[!UICONTROL 파일 이름에 타임스탬프 추가]**&#x200B;를 선택합니다.

   타임스탬프를 파일 이름에 추가하여 통합 문서가 업데이트된 날짜를 식별할 수 있습니다. 타임스탬프는 특정 날짜에 전송된 통합 문서의 버전을 확인하는 데 유용합니다. 선택하면 다음 중 하나를 선택할 수 있습니다.

   * **[!UICONTROL ISO 날짜 형식]**&#x200B;입니다. 이 경우 `YYYY-MM-DD`이(가) 파일 이름에 추가됩니다.
   * **[!UICONTROL ISO 날짜 형식 + 타임스탬프]**&#x200B;입니다. 그러면 `YYYY-MM-DD_HH-MM-SS`이(가) 파일 이름에 추가됩니다.

<!-- Does no longer seem to be an option? 
1. (Optional) Select **.zip compression** to compress the file and set up password protection on the file.

    When you make this selection, you're prompted to enter a password to open the file. This is helpful if you have concerns about data security and you want to password protect the workbook. Protecting the file with a password requires you to select **.zip compression**. The password must be at least 8 characters and contain a number and a special character.

    ![Enter a password in the Password protect the workbook field.](./assets/zip-compression.png){zoomable="yes"}{width="55%"}
-->

1. **[!UICONTROL 통합 문서 암호 보호]**&#x200B;에 암호를 입력하십시오. 유효한 암호에는 8자 이상, 숫자 및 특수 문자가 필요합니다. 암호를 표시하려면 ![VisibilityOff](/help/assets/icons/VisibilityOff.svg)를 선택하고 암호를 숨기려면 ![Visibility](/help/assets/icons/Visibility.svg)을 선택합니다(기본값).


### 이메일

**[!UICONTROL 전자 메일]** 섹션에서 전자 메일의 수신자, 제목 및 설명을 제공합니다.

![전자 메일 설정 예약](assets/schedule-email.png){zoomable="yes"}

1. **수신자**&#x200B;를 입력합니다. 조직에서 인식하는 사람의 이름을 입력할 수 있습니다. 또는 조직 외부에 있는 사람의 이메일 주소를 입력할 수 있습니다.

1. 이메일의 **제목** 및 수신자에 대한 설명을 입력합니다. 제목에 통합 문서 파일 이름이 기본적으로 표시되지만 필요한 경우 제목을 수정할 수 있습니다. 설명 섹션의 세부 정보를 추가할 수 있습니다.

1. **[!UICONTROL 설명]** 텍스트 영역에 설명을 선택적으로 입력할 수 있습니다.


### 예약

**[!UICONTROL 일정]** 섹션에서 통합 문서가 포함된 전자 메일을 받는 사람에게 보내는 일정을 정의할 수 있습니다.

![일정 정의](assets/schedule-enable.png){zoomable="yes"}

1. **[!UICONTROL 예약 옵션 표시]**&#x200B;를 선택하여 일정을 정의합니다.

1. **[!UICONTROL 시작 날짜]**&#x200B;에 시작 날짜를 입력하십시오. 또는 ![달력](/help/assets/icons/Calendar.svg)을 선택하여 달력에서 시작 날짜를 선택하십시오.

1. 종료 날짜를 **[!UICONTROL 종료 날짜]**&#x200B;로 입력하십시오. 또는 ![캘린더](/help/assets/icons/Calendar.svg)를 선택하여 달력에서 종료 날짜를 선택하십시오.

1. **[!UICONTROL 빈도]**&#x200B;를 선택하십시오. 선택한 빈도에 따라 추가 옵션이 있습니다. 아래 표를 참조하십시오.

   | 빈도 | 옵션 |
   |---|---|
   | **[!UICONTROL 시간별 전송]** | **[!UICONTROL 시간 단위로 보내기]**&#x200B;에 대한 값을 입력하십시오. |
   | **[!UICONTROL 매일 보내기]** | **[!UICONTROL 일별 빈도]**&#x200B;를 선택하십시오. **[!UICONTROL 매일 보내기]**, **[!UICONTROL 평일마다 보내기]** 또는 **[!UICONTROL 사용자 지정 빈도]**.<br/>**[!UICONTROL 사용자 지정 빈도]**&#x200B;를 선택한 경우 **[!UICONTROL 일마다 보내기]**&#x200B;에 대한 값을 입력하십시오. |
   | **[!UICONTROL 주별 보내기]** | **[!UICONTROL 주마다 보내기]**&#x200B;에 대한 값을 입력하십시오. **[!UICONTROL 요일]**&#x200B;을 선택하세요. |
   | **[!UICONTROL 요일별로 월별 전송]** | **[!UICONTROL 요일]**&#x200B;과 **[!UICONTROL 월 주]**&#x200B;을(를) 선택하십시오. |
   | **[!UICONTROL 월별 전송(날짜 기준)]** | **[!UICONTROL 이 달의 날짜에 보내기]**&#x200B;에서 값을 선택하십시오. |
   | **[!UICONTROL 매년 해당 월의 날짜별로 보내기]** | **[!UICONTROL 요일]**&#x200B;을 선택하고 **[!UICONTROL 주]**&#x200B;을 선택한 다음 **[!UICONTROL 월별]**&#x200B;을(를) 선택합니다. |
   | **[!UICONTROL 특정 날짜까지 연간 전송]** | **[!UICONTROL 월(한 해 기준)]**&#x200B;을 선택하고 **[!UICONTROL 이 날짜에 보내기]**&#x200B;에서 값을 선택합니다. |

### 보내기

통합 문서를 보내려면:

* **[!UICONTROL 예약 옵션 표시]**&#x200B;를 사용하여 일정을 정의하지 않은 경우 **[!UICONTROL 지금 보내기]**&#x200B;를 선택하여 전자 메일로 통합 문서를 즉시 보냅니다.
* **[!UICONTROL 예약 옵션 표시]**&#x200B;를 사용하여 일정을 정의한 경우 **[!UICONTROL 일정에 따라 보내기]**&#x200B;를 선택하여 정의한 일정을 사용하여 전자 메일로 통합 문서를 보냅니다.

두 경우 모두 Report Builder 허브 하단에 확인 알림이 표시됩니다.

통합 문서 전송을 취소하려면 **[!UICONTROL 취소]**&#x200B;를 선택하십시오.


## 예약된 통합 문서 보기 및 관리

**[!UICONTROL 통합 문서]** 탭에서 모든 예약된 통합 문서를 보고 관리할 수 있습니다.

1. Report Builder 허브에서 **[!UICONTROL 일정]** 선택

1. **[!UICONTROL 통합 문서]** 탭을 선택합니다. 모든 예약된 통합 문서 목록이 표시됩니다.

   ![예약된 통합 문서](assets/scheduled-workbooks.png){zoomable="yes"}

   아이콘 위로 마우스를 가져가 예약된 통합 문서의 상태를 확인할 수 있습니다.

   ![검색](/help/assets/icons/Search.svg)을 사용하여 예약된 특정 통합 문서를 검색합니다.
표시할 열을 정의하려면 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을(를) 사용하십시오.

1. 통합 문서를 하나 이상 선택합니다.

   ![선택한 통합 문서 예약](assets/scheduled-workbooks-selected.png){zoomable="yes"}

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

1. Report Builder 허브에서 **[!UICONTROL 일정]**&#x200B;을(를) 선택하십시오.

1. **[!UICONTROL 기록]** 탭을 선택합니다. 모든 예약된 통합 문서 목록이 표시됩니다.

   ![예약된 내역](assets/scheduled-workbooks-history.png){zoomable="yes"}

   목록에서 특정 통합 문서를 검색하려면 ![Search](/help/assets/icons/Search.svg)을(를) 사용하십시오.
표시할 열을 정의하려면 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을(를) 사용하십시오.

   **[!UICONTROL 기록]** 탭에서 예약된 각 작업의 상태를 검토할 수 있습니다. 각 예약된 작업에 대한 상태 변경 내용은 별도의 행에 설명되어 있습니다.

   * ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg)은 통합 문서가 성공적으로 전송되었음을 나타냅니다.
   * ![AlertRed](/help/assets/icons/AlertRed.svg)은(는) 오류가 발생했음을 나타냅니다.

또는 **[!UICONTROL 통합 문서]** 탭에서 하나 이상의 선택한 통합 문서에 대해 ![기록](/help/assets/icons/History.svg)을 선택할 수 있습니다. 이 작업은 선택한 항목별로 필터링된 목록이 있는 **[!UICONTROL 기록]** 탭을 표시합니다. 필터를 제거하려면 ![CrossSize75](/help/assets/icons/CrossSize75.svg)을(를) 선택하십시오.
