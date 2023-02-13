---
description: 이메일을 통해 Analysis Workspace 프로젝트를 전송하거나 게재할 일정을 예약합니다.
keywords: Analysis Workspace
title: 프로젝트 예약
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: af9113f3afced902b385747bceaa9e51b72d83e6
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 98%

---

# 프로젝트 예약

작업 영역 **공유 메뉴**&#x200B;에서 이메일을 통해 선택한 수신자에게 Analysis Workspace 프로젝트를 보낼 수 있습니다. 파일은 CSV 또는 PDF 형식으로 보낼 수 있습니다.

## 지금 파일 보내기 {#now}

이메일을 통해 파일을 수신자에게 즉시 보내려면

1. **공유 > 지금 파일 보내기**&#x200B;를 클릭합니다.
1. 파일 유형(CSV 또는 PDF)을 지정합니다.
1. (선택 사항) 수신되는 파일을 설명하기 위해 이메일에 포함할 설명을 추가합니다.
1. 수신자 또는 그룹을 추가합니다. 이메일 주소를 입력할 수도 있습니다.
1. (Healthcare Shield 고객만 해당) 암호를 입력합니다. 암호로 예약된 보고서 보호 섹션을 참조하십시오.
1. **지금 보내기**&#x200B;를 클릭합니다.
1. (선택 사항) 게재 일정을 지정하려면 **예약 옵션 표시**&#x200B;를 클릭합니다.

![지금 파일 보내기](assets/send-file-no-scheduling-options.JPG)

## 일정에 따라 파일 보내기 {#schedule}

이메일을 통해 되풀이되는 일정으로 수신자에게 파일을 보내려면

1. **공유 > 일정에 따라 파일 보내기**&#x200B;를 클릭합니다.
1. 파일 유형(CSV 또는 PDF)을 지정합니다.
1. (선택 사항) 수신되는 파일을 설명하기 위해 이메일에 포함할 설명을 추가합니다.
1. 수신자 또는 그룹을 추가합니다. 이메일 주소를 입력할 수도 있습니다.
1. (Healthcare Shield 고객만 해당) 암호를 입력합니다. 암호로 예약된 보고서 보호 섹션을 참조하십시오.
1. 입력 시 시작 및 종료를 수정하여 일정이 전달될 범위를 지정합니다. 종료 날짜는 일정을 만들거나 수정한 날로부터 1년 이내여야 합니다.
1. 게재 빈도를 지정합니다. 각 빈도에서는 다양한 맞춤화를 사용할 수 있습니다.
1. **일정에 따라 보내기**&#x200B;를 클릭합니다.

![](assets/send-file.JPG)

## 예약된 프로젝트 관리자 {#manager}

예약된 Analysis Workspace 프로젝트는 **Analytics > 구성 요소 > 예약된 프로젝트**&#x200B;에서 관리할 수 있습니다.

예약된 프로젝트 관리자에서 반복되는 프로젝트 일정을 편집하고 삭제할 수 있습니다. 검색 창에서 또는 왼쪽 레일의 필터 옵션을 사용하여 예약을 검색하십시오. 태그, 승인된 일정, 소유자 등으로 필터링할 수 있습니다.

다음은 예약된 프로젝트 관리자의 일반적인 작업입니다.

| 작업 | 설명 |
|---|---|
| **예약 편집** | 예약 제목을 클릭하여 게재 설정을 업데이트합니다. |
| **예약 삭제** | 목록에서 예약된 프로젝트를 선택한 다음, 메뉴에서 삭제를 클릭합니다. 선택한 프로젝트 예약이 삭제됩니다. 프로젝트 자체는 삭제되지 않습니다. |
| **태그 추가** | 일정을 구성하고 검색하기 더 쉽게 하려면 목록에서 예약된 프로젝트를 선택한 다음, &quot;태그&quot; 또는 &quot;승인&quot;을 선택합니다. |
| **실패한 일정 보기** | 실패한 예약을 보려면 왼쪽 레일 > 기타 필터 > 실패로 이동합니다. |
| **만료된 일정 보기** | 만료된 예약을 보려면 왼쪽 레일 > 기타 필터 > 만료됨으로 이동합니다. 예약의 제목을 클릭하여 새 게재 예약을 설정합니다. |
| **예약 ID 보기** | 오른쪽 상단의 열 옵션으로 이동하고 예약 ID 열을 테이블에 추가합니다. 예약된 ID는 종종 디버깅에 유용합니다. |

예약된 프로젝트 관리자는 특정 사용자가 만든 항목을 보여 줍니다. 애플리케이션에서 사용자 계정이 비활성화된 경우 모든 예약된 게재가 중단됩니다.

## 암호로 예약된 프로젝트 보호 {#password}

>[!NOTE]
>
>예약된 프로젝트를 암호로 보호하는 옵션은 [Healthcare Shield](https://experienceleague.adobe.com/docs/customer-data-management-voices-events/events/governance/healthcare-shield.html?lang=en) 추가 기능 제품을 구입한 CJA 고객에게만 표시됩니다.

Adobe는 .pdf 또는 .csv 포맷으로 전송되는지 여부에 관계없이 암호를 사용하여 예약된 프로젝트를 암호화합니다.

귀사에서 Healthcare Shield SKU를 구매하고 활성화한 후 다음 두 가지 상황에서 예약된 프로젝트에 대한 암호를 생성하라는 메시지가 표시됩니다.

* 누군가 예약된 프로젝트를 새로 만드는 경우

* 기존의 예약된 프로젝트를 전송하려고 하는 경우 현재의 예약된 프로젝트는 암호 보호가 적용될 때까지 비활성화됩니다. 예약된 프로젝트의 소유자는 이에 대한 이메일 알림을 수신하게 됩니다.

![암호 보호](assets/password.png)

### 암호 요구 사항

암호 요구 사항은 Adobe 표준을 따르며 최소 하나의 숫자와 하나의 특수 문자를 포함하여 8자 이상이어야 합니다.

### 암호로 예약된 새 프로젝트 보호

1. 프로젝트를 저장하고 나면 **[!UICONTROL 공유]** > **[!UICONTROL 지금 파일 보내기]** 또는 [!UICONTROL 공유] > **[!UICONTROL 일정에 따라 파일 보내기]**&#x200B;로 이동합니다.
1. [지금 파일 보내기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#now) 또는 [일정에 따라 파일 보내기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#schedule)에 대해 위 지침을 따르십시오.

### 암호로 예약된 기존 프로젝트 보호

프로젝트가 예약되기 전에 해당 프로젝트의 소유자는 다음과 유사한 내용의 이메일을 수신하게 됩니다.

![이메일](assets/email-password.png)

1. Customer Journey Analytics에 다시 로그인합니다.
1. **[!UICONTROL 예약된 프로젝트 보기]**&#x200B;를 클릭합니다.
1. **[!UICONTROL 예약된 프로젝트 편집]** 대화 상자에서 암호를 입력한 후 다시 입력합니다.
1. 예약된 프로젝트의 수신자에게만 이 암호를 알려 주십시오.


