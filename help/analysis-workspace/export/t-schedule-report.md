---
description: 이메일을 통해 Analysis Workspace 프로젝트를 보내거나 게재할 일정을 예약합니다.
keywords: Analysis Workspace
title: 이메일로 다른 사람에게 보고서 보내기
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: a462e736ddcdf1a5ea84a85eea2c2ce0b8a34fb0
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 58%

---

# 다른 사람에게 필터 보내기

선택된 사용자에게 Customer Journey Analytics 보고서를 파일로 이메일을 보낼 수 있습니다. 파일을 애드혹으로 보낼 수도 있고, 일정에 따라 파일을 보내도록 구성할 수도 있습니다. 파일은 CSV 또는 PDF 형식으로 보낼 수 있습니다.

프로젝트에 적용된 모든 태그는 자동으로 내보내기에 적용됩니다.

Customer Journey Analytics 데이터를 내보내는 다른 방법도 사용할 수 있으며, 자세한 내용은 [내보내기 개요](/help/analysis-workspace/export/export-project-overview.md)에서 설명합니다.

![파일 보내기](assets/send-file.png)

## 파일 보내기

전자 메일로 수신자에게 파일을 보내려면 다음과 같이 하십시오.

1. **[!UICONTROL 공유] > [!UICONTROL 파일 보내기]**&#x200B;를 선택합니다.
1. 파일 유형을 지정합니다.
   * [!UICONTROL **CSV**]: 일반 텍스트 데이터를 원하는 경우 이 옵션을 선택합니다.
   * [!UICONTROL **PDF**]: 다운로드한 파일에 프로젝트에 표시된(표시되는) 테이블과 시각화가 모두 포함되도록 하려면 이 옵션을 선택합니다.
1. (선택 사항) 전자 메일에 포함할 설명을 추가하려면 **[!UICONTROL 설명]**&#x200B;을 사용합니다.
1. 수신자 또는 그룹을 추가합니다. 이메일 주소를 입력할 수도 있습니다.
1. (Healthcare Shield 고객만 해당) [예약된 보고서를 암호로 보호](#password-protect-a-new-scheduled-project)하려면 암호를 제공하세요.
1. (선택 사항) **[!UICONTROL 예약 옵션 표시]**&#x200B;를 선택하여 [파일 내보내기 예약](#schedule-file-export)을 선택합니다.
1. **[!UICONTROL 지금 보내기]**&#x200B;를 클릭합니다. 취소하려면 **[!UICONTROL 취소]**&#x200B;를 선택합니다.


## 파일 내보내기 예약 {#schedule}

이메일로 수신자에게 일정에 따라 파일을 보내려면

1. **[!UICONTROL 공유] > [!UICONTROL 파일 내보내기 예약]**&#x200B;을 선택합니다.
1. 파일 유형을 지정합니다.
   * [!UICONTROL **CSV**]: 일반 텍스트 데이터를 원하는 경우 이 옵션을 선택합니다.
   * [!UICONTROL **PDF**]: 다운로드한 파일에 프로젝트에 표시된(표시되는) 테이블과 시각화가 모두 포함되도록 하려면 이 옵션을 선택합니다.
1. (선택 사항) 전자 메일에 포함할 설명을 추가하려면 **[!UICONTROL 설명]**&#x200B;을 사용합니다.
1. 수신자 또는 그룹을 추가합니다. 이메일 주소를 입력할 수도 있습니다.
1. (Healthcare Shield 고객만 해당) [예약된 보고서를 암호로 보호](#password-protect-a-new-scheduled-project)하려면 암호를 제공하세요.
1. **[!UICONTROL 예약 옵션 표시]**&#x200B;를 선택했는지 확인하십시오.
1. **[!UICONTROL 빈도]**&#x200B;를 선택하십시오. 다음 중 하나를 선택할 수 있습니다.

   | 빈도 | 옵션 |
   |---|---|
   | **[!UICONTROL 시간별 전송]** | **[!UICONTROL 시간 단위로 보내기]**&#x200B;에 대한 값을 입력하십시오. |
   | **[!UICONTROL 매일 보내기]** | **[!UICONTROL 일별 빈도]**&#x200B;를 선택하십시오. **[!UICONTROL 매일 보내기]**, **[!UICONTROL 평일마다 보내기]** 또는 **[!UICONTROL 사용자 지정 빈도]**.<br/>**[!UICONTROL 사용자 지정 빈도]**&#x200B;를 선택한 경우 **[!UICONTROL 일마다 보내기]**&#x200B;에 대한 값을 입력하십시오. |
   | **[!UICONTROL 주별 보내기]** | **[!UICONTROL 주마다 보내기]**&#x200B;에 대한 값을 입력하십시오. **[!UICONTROL 요일]**&#x200B;을 선택하세요. |
   | **[!UICONTROL 요일별로 월별 전송]** | **[!UICONTROL 요일]**&#x200B;과 **[!UICONTROL 월 주]**&#x200B;을(를) 선택하십시오. |
   | **[!UICONTROL 월별 전송(날짜 기준)]** | **[!UICONTROL 이 달의 날짜에 보내기]**&#x200B;에서 값을 선택하십시오. |
   | **[!UICONTROL 매년 해당 월의 날짜별로 보내기]** | **[!UICONTROL 요일]**&#x200B;을 선택하고 **[!UICONTROL 주]**&#x200B;을 선택한 다음 **[!UICONTROL 월별]**&#x200B;을(를) 선택합니다. |
   | **[!UICONTROL 특정 날짜까지 연간 전송]** | **[!UICONTROL 월(한 해 기준)]**&#x200B;을 선택하고 **[!UICONTROL 이 날짜에 보내기]**&#x200B;에서 값을 선택합니다. |

1. **[!UICONTROL 시작 날짜]**&#x200B;에 시작 날짜를 입력하십시오. 또는 ![달력](/help/assets/icons/Calendar.svg)을 선택하여 달력에서 시작 날짜를 선택하십시오.

1. 종료 날짜를 **[!UICONTROL 종료 날짜]**&#x200B;로 입력하십시오. 또는 ![캘린더](/help/assets/icons/Calendar.svg)를 선택하여 달력에서 종료 날짜를 선택하십시오.
1. **[!UICONTROL 일정에 따라 보내기]**&#x200B;를 선택합니다. 취소하려면 **[!UICONTROL 취소]**&#x200B;를 선택합니다.


## 암호로 예약된 프로젝트 보호 {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_sendfile_password"
>title="암호 암호화"
>abstract="제공된 암호는 예약 프로젝트의 파일을 암호화하는 데 사용됩니다. 조직의 보안 요구 사항에 따라 암호를 암호화해야 합니다."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>예약된 프로젝트를 암호로 보호하는 옵션은 [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html) 추가 기능 제품을 구입한 Customer Journey Analytics 고객에게만 표시됩니다.

Adobe는 .pdf 또는 .csv 포맷으로 전송되는지 여부에 관계없이 암호를 사용하여 예약된 프로젝트를 암호화합니다.

귀사에서 Healthcare Shield SKU를 구매하고 활성화한 후 다음 상황에서 예약된 프로젝트에 대한 암호를 생성하라는 메시지가 표시됩니다.

* 누군가 예약된 프로젝트를 새로 만드는 경우

* 기존의 예약된 프로젝트를 전송하려고 하는 경우 현재의 예약된 프로젝트는 암호 보호가 적용될 때까지 비활성화됩니다. 예약된 프로젝트의 소유자는 이 요구 사항을 알리는 이메일을 받습니다.

### 암호 요구 사항

암호 요구 사항은 Adobe 표준을 따르며 최소 하나의 숫자와 하나의 특수 문자를 포함하여 8자 이상이어야 합니다.

### 암호로 예약된 새 프로젝트 보호

1. 프로젝트를 저장하고 나면 **[!UICONTROL 공유]** > **[!UICONTROL 지금 파일 보내기]** 또는 **[!UICONTROL 공유]** > **[!UICONTROL 일정에 따라 파일 보내기]**&#x200B;로 이동합니다.
1. [지금 파일 보내기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=ko-KR#now) 또는 [일정에 따라 파일 보내기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=ko-KR#schedule)에 대해 위 지침을 따르십시오.

### 암호로 예약된 기존 프로젝트 보호

기존 예약된 프로젝트를 암호로 보호하면 프로젝트 소유자에게 다음과 유사한 이메일이 전송됩니다.

![조직에 비밀번호 암호화가 필요하다 내용의 Customer Journey Analytics 이메일 알림.](assets/email-password.png)

1. Customer Journey Analytics로 로그인합니다.
1. **[!UICONTROL 예약된 프로젝트 보기]**&#x200B;를 선택합니다.
1. **[!UICONTROL 예약된 프로젝트 편집]** 대화 상자에서 암호를 입력한 후 다시 입력합니다.
1. 예약된 프로젝트의 수신자에게 이 암호를 알려 줍니다. 예약된 프로젝트의 수신자가 아닌 사람에게 암호를 배포하지 마십시오.



## 예약된 프로젝트 관리자 {#manager}

예약된 Analysis Workspace 프로젝트는 **[!UICONTROL 구성 요소]** > **[!UICONTROL 예약된 프로젝트]**&#x200B;를 사용하여 기본 인터페이스에서 관리할 수 있습니다. 자세한 내용은 [예약된 프로젝트](/help/components/scheduled-projects-manager.md)를 참조하십시오.
