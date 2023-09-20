---
description: 이메일로 Analysis Workspace 프로젝트를 보내거나 게재할 일정을 예약합니다.
keywords: Analysis Workspace
title: 이메일로 다른 사람에게 Customer Journey Analytics 데이터 보내기
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 8eda6e9ed27ab458951cd4bd08f511987bc61eb0
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 63%

---

# 이메일을 통해 다른 사용자에게 Customer Journey Analytics 데이터 보내기

이메일을 통해 선택한 수신자에게 Customer Journey Analytics 데이터를 전송하여 내보낼 수 있습니다. 파일을 임시로 보내거나 일정에 따라 보낼 파일을 구성할 수 있습니다. 파일은 CSV 또는 PDF 형식으로 보낼 수 있습니다.

프로젝트에 적용된 모든 태그는 내보내기에 자동으로 적용됩니다.

에 설명된 대로 Customer Journey Analytics 데이터를 내보내는 다른 방법도 사용할 수 있습니다 [내보내기 개요](/help/analysis-workspace/export/export-project-overview.md).

## 지금 파일 보내기 {#now}

전자 메일로 수신자에게 파일을 즉시 보내려면 다음과 같이 하십시오.

1. 클릭 **[!UICONTROL 공유] > [!UICONTROL 파일 내보내기]**.
1. 파일 형식 지정:
   * [!UICONTROL **CSV**]: 일반 텍스트 데이터를 원하는 경우 이 옵션을 선택합니다.
   * [!UICONTROL **PDF**]: 다운로드한 파일에 프로젝트에 표시된 (볼 수 있는) 모든 테이블 및 시각화를 포함하려면 이 옵션을 선택합니다.
1. (선택 사항) 수신되는 파일을 설명하기 위해 이메일에 포함할 설명을 추가합니다.
1. 수신자 또는 그룹을 추가합니다. 이메일 주소를 입력할 수도 있습니다.
1. (Healthcare Shield 고객만 해당) 암호를 입력합니다. 암호로 예약된 보고서 보호 섹션을 참조하십시오.
1. **[!UICONTROL 지금 보내기]**&#x200B;를 클릭합니다.
1. (선택 사항) 게재 일정을 지정하려면 **[!UICONTROL 예약 옵션 표시]**&#x200B;를 클릭합니다.

![지금 파일 보내기](assets/send-file-no-scheduling-options.JPG)

## 일정에 따라 파일 보내기 {#schedule}

되풀이하는 일정으로 수신자에게 파일을 이메일로 보내려면:

1. 클릭 **[!UICONTROL 공유] > [!UICONTROL 파일 내보내기 예약]**.
1. 파일 유형(CSV 또는 PDF)을 지정합니다.
1. (선택 사항) 수신되는 파일을 설명하기 위해 이메일에 포함할 설명을 추가합니다.
1. 수신자 또는 그룹을 추가합니다. 이메일 주소를 입력할 수도 있습니다.
1. (Healthcare Shield 고객만 해당) 암호를 입력합니다. 암호로 예약된 보고서 보호 섹션을 참조하십시오.
1. 입력 시 시작 및 종료를 수정하여 일정이 전달될 범위를 지정합니다. 종료 날짜는 일정을 만들거나 수정한 날로부터 1년 이내여야 합니다.
1. 게재 빈도를 지정합니다. 각 빈도에서는 다양한 맞춤화를 사용할 수 있습니다.
1. **[!UICONTROL 일정에 따라 보내기]**&#x200B;를 클릭합니다.

![](assets/send-file.JPG)

## 예약된 프로젝트 관리자 {#manager}

예약된 Analysis Workspace 프로젝트는 **[!UICONTROL Analytics] > [!UICONTROL 구성 요소] > [!UICONTROL 예약된 프로젝트]**&#x200B;에서 관리할 수 있습니다.

예약된 프로젝트 관리자에서 반복되는 프로젝트 일정을 편집하고 삭제할 수 있습니다. 검색 창에서 또는 왼쪽 레일의 필터 옵션을 사용하여 예약을 검색하십시오. 태그, 승인된 일정, 소유자 등으로 필터링할 수 있습니다.

| 필드 | 설명 |
| --- | --- |
| [!UICONTROL 즐겨찾기] | 별표 아이콘을 선택하면 이 예약이 즐겨찾기에 등록됩니다. |
| [!UICONTROL 예약 ID] | 이 ID는 주로 디버깅 목적으로 사용됩니다. |
| [!UICONTROL 제목 및 설명] | 이 프로젝트의 제목과 설명 |
| [!UICONTROL 소유자] | 프로젝트를 만들고 소유하고 있는 사람입니다. |
| [!UICONTROL 태그] | (선택 사항) 태그 지정은 프로젝트를 구성하는 좋은 방법입니다. 모든 사용자는 태그를 만든 후 하나의 프로젝트에 하나 이상의 태그를 적용할 수 있습니다. 그렇지만 본인이 소유하거나 본인과 공유된 프로젝트에 대한 태그만 볼 수 있습니다. |
| [!UICONTROL 제공 대상] | 이 예약된 프로젝트의 수신자 |
| [!UICONTROL 만료 날짜] | 일정 빈도에 상관없이 만료일을 최대 1년으로 설정할 수 있습니다. |
| [!UICONTROL 빈도] | 이 예약된 프로젝트를 수신자에게 보내고자 하는 빈도 |
| [!UICONTROL 실행 시간] | 이 예약된 프로젝트를 보내고자 하는 하루 중의 시간 |
| [!UICONTROL 쿼리 개수] | 이 프로젝트에 대한 쿼리 개수 |

다음은 예약된 프로젝트 관리자의 일반적인 작업입니다.

| 작업 | 설명 |
|---|---|
| **[!UICONTROL 예약 편집]** | 예약 제목을 클릭하여 게재 설정을 업데이트합니다. |
| **[!UICONTROL 예약 삭제]** | 목록에서 예약된 프로젝트를 선택한 다음, 메뉴에서 삭제를 클릭합니다. 선택한 프로젝트 예약이 삭제됩니다. 프로젝트 자체는 삭제되지 않습니다. |
| **[!UICONTROL 태그 추가]** | 일정을 구성하고 검색하기 더 쉽게 하려면 목록에서 예약된 프로젝트를 선택한 다음 “태그” 또는 “승인”을 선택합니다. |
| **[!UICONTROL 실패한 일정 보기]** | 실패한 예약을 보려면 왼쪽 레일 > 기타 필터 > 실패로 이동합니다. |
| **[!UICONTROL 만료된 일정 보기]** | 만료된 예약을 보려면 왼쪽 레일 > 기타 필터 > 만료됨으로 이동합니다. 예약의 제목을 클릭하여 새 게재 예약을 설정합니다. |
| **[!UICONTROL 예약 ID 보기]** | 오른쪽 상단의 열 옵션으로 이동하고 예약 ID 열을 테이블에 추가합니다. 예약된 ID는 종종 디버깅에 유용합니다. |

예약된 프로젝트 관리자는 특정 사용자가 만든 항목을 보여 줍니다. 애플리케이션에서 사용자 계정이 비활성화된 경우 모든 예약된 게재가 중지됩니다.
자세한 내용은 [예약된 프로젝트](/help/components/scheduled-projects-manager.md).

## 암호로 예약된 프로젝트 보호 {#password}

>[!NOTE]
>
>예약된 프로젝트를 암호로 보호하는 옵션은 프로젝트를 구입한 Customer Journey Analytics 고객에게만 표시됩니다. [헬스케어 실드](https://business.adobe.com/solutions/experience-cloud-for-healthcare.html) 추가 기능 제품.

Adobe는 .pdf 또는 .csv 포맷으로 전송되는지 여부에 관계없이 암호를 사용하여 예약된 프로젝트를 암호화합니다.

귀사에서 Healthcare Shield SKU를 구매하고 활성화한 후 다음 상황에서 예약된 프로젝트에 대한 암호를 생성하라는 메시지가 표시됩니다.

* 누군가 예약된 프로젝트를 새로 만드는 경우

* 기존의 예약된 프로젝트를 전송하려고 하는 경우 암호 보호가 적용될 때까지 현재 예약된 프로젝트를 사용할 수 없습니다. 예약된 프로젝트의 소유자는 이 요구 사항을 알리는 이메일을 수신합니다.

![암호 보호](assets/password.png)

### 암호 요구 사항

암호 요구 사항은 Adobe 표준을 따르며 최소 하나의 숫자와 하나의 특수 문자를 포함하여 8자 이상이어야 합니다.

### 암호로 예약된 새 프로젝트 보호

1. 프로젝트를 저장한 다음 로 이동합니다. **[!UICONTROL 공유]** > **[!UICONTROL 지금 파일 보내기]**, 또는 **[!UICONTROL 공유]** > **[!UICONTROL 일정에 따라 파일 보내기]**.
1. [지금 파일 보내기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=ko-KR#now) 또는 [일정에 따라 파일 보내기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=ko-KR#schedule)에 대해 위 지침을 따르십시오.

### 암호로 예약된 기존 프로젝트 보호

프로젝트가 예약되기 전에 프로젝트 소유자는 다음과 유사한 이메일을 수신합니다.

![이메일](assets/email-password.png)

1. Customer Journey Analytics에 로그인합니다.
1. 선택 **[!UICONTROL 예약된 프로젝트 보기]**.
1. **[!UICONTROL 예약된 프로젝트 편집]** 대화 상자에서 암호를 입력한 후 다시 입력합니다.
1. 예약된 프로젝트의 수신자에게 이 암호를 알려 주십시오. 예약된 프로젝트의 수신자가 아닌 사람에게 암호를 배포하지 마십시오.
