---
description: 디버거를 사용하여 Analysis Workspace에서 프로젝트 문제를 해결하는 방법에 대해 알아봅니다.
keywords: Analysis Workspace
feature: Workspace Basics
title: 프로젝트 디버거
role: User
exl-id: 1335ec1f-5597-4e23-8228-3d477534de43
source-git-commit: 695d5f686d10fc39b1b3d717a19fd6e874d81b33
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 3%

---

# 프로젝트 디버거

프로젝트 디버거는 귀하 및 Adobe 지원 팀이 Analysis Workspace에서 프로젝트 문제를 해결할 수 있도록 지원합니다. Adobe 지원 센터에서 디버거를 활성화하여 Adobe 지원 시 발생한 티켓 문제를 해결할 수 있도록 요청할 수 있습니다. 문제의 예로는 시각화의 로드 시간 또는 시각화의 구성 요소가 깨진 경우가 있습니다.

>[!NOTE]
>
>디버거를 사용하려면 **편집** 또는 **복사** [프로젝트에 액세스](https://experienceleague.adobe.com/ko/docs/experience-cloud-kcs/kbarticles/ka-25744)해야 합니다.
>


## 디버거 활성화

>[!IMPORTANT]
>
>디버거를 활성화하기 전에 프로젝트를 저장하십시오.
>

디버거를 사용하려면:

1. Analysis Workspace 프로젝트 메뉴에서 **[!UICONTROL 도움말]** > **[!UICONTROL 디버거 사용]**&#x200B;을 선택합니다.
1. **[!UICONTROL 디버거 사용]** 대화 상자에서 **[!UICONTROL 확인]**&#x200B;을 선택합니다.
1. 페이지 또는 사이트를 다시 로드하라는 브라우저의 메시지가 표시되면 확인합니다.


## 디버거 사용

디버거를 활성화하면 프로젝트의 모든 시각화에 추가 ![버그](/help/assets/icons/Bug.svg) 아이콘이 있습니다.

특정 시각화에 디버거를 사용하려면 다음을 수행하십시오.

1. 시각화 맨 위에서 ![버그](/help/assets/icons/Bug.svg)를 선택합니다.

   ![디버거 컨텍스트 메뉴](assets/debugger-context-menu.png)

1. 컨텍스트 메뉴에서 적절한 작업을 선택합니다. 사용 가능한 작업은 시각화에 따라 다르며 수행하려는 디버깅 유형을 나타냅니다. 예를 들어 **[!UICONTROL 예외 항목]**&#x200B;을 선택하면 시각화에서 예외 항목 기능을 디버깅할 수 있습니다.
1. 하위 메뉴에서 타임스탬프를 선택합니다.
1. 시각화가 수행한 특정 기능에 대한 세부 정보가 포함된 **[!UICONTROL Oberon XML]** 디버그 창이 열립니다. 예외 항목 요청의 출력에 대한 예는 아래를 참조하십시오.

   ![디버그 요청 출력](assets/debugger-oberon.png)

   세부 사항은 다음과 같습니다.

   * **[!UICONTROL 타임스탬프 요청]**
   * **[!UICONTROL 응답 타임스탬프]**
   * **[!UICONTROL 요청 시간]**
   * **[!UICONTROL 큐 시간]**
   * **[!UICONTROL 서버 처리 시간]**
   * **[!UICONTROL 조회 시간]**
   * **[!UICONTROL 복잡성]**
   * **[!UICONTROL 월 경계]**
   * **[!UICONTROL 열]**
   * **[!UICONTROL 세그먼트]**
   * **[!UICONTROL XML]** **[!UICONTROL 요청]** 및 **[!UICONTROL 응답]**
   * **[!UICONTROL cURL 요청]**
   * **[!UICONTROL JSON]** **[!UICONTROL 요청]** 및 **[!UICONTROL 응답]**

1. ![복사](/help/assets/icons/Copy.svg) **[!UICONTROL 클립보드에 모든 필드 복사]**&#x200B;를 사용하여 모든 디버그 정보를 클립보드에 복사합니다. 원하는 편집기 또는 도구에 정보를 붙여넣습니다. 정보는 다음과 같이 구성됩니다.

   * XML (요청)
   * XML (응답)
   * JSON (요청)
   * JSON (응답)
   * cURL 요청

1. 요청을 클립보드에 복사하려면 ![복사](/help/assets/icons/Copy.svg) **[!UICONTROL 클립보드에 복사]** cURL 요청&#x200B;**[!UICONTROL 아래의]**&#x200B;을(를) 사용합니다.
1. **[!UICONTROL 요청]** 또는 **[!UICONTROL 응답]** 텍스트 영역 위로 마우스를 가져간 후 ![복사](/help/assets/icons/Copy.svg) **[!UICONTROL 클립보드에 복사]**&#x200B;를 선택하여 해당 텍스트 영역(XML 또는 JSON)의 내용을 클립보드에 복사합니다.

1. 복사한 정보와 Adobe 지원에서 Analysis Workspace 프로젝트의 시각화 문제를 해결하기 위해 요청한 정보를 교환합니다.

1. **[!UICONTROL Oberon XML]** 디버그 창을 닫고 프로젝트로 돌아가려면 **[!UICONTROL 취소]**&#x200B;를 선택하십시오.

문제를 해결할 다른 시각화에 대해 위 단계를 반복합니다.

## 디버거 비활성화

>[!IMPORTANT]
>
>디버거를 비활성화하기 전에 프로젝트에 대한 변경 사항을 저장하고 디버깅 연습의 일부로 유지하려고 합니다.
>

디버거를 비활성화하려면:

1. Analysis Workspace 프로젝트 메뉴에서 **[!UICONTROL 도움말]** > **[!UICONTROL 디버거 사용 안 함]**&#x200B;을 선택합니다.
1. **[!UICONTROL 디버거 사용 안 함]** 대화 상자에서 **[!UICONTROL 확인]**&#x200B;을 선택합니다.
1. 페이지 또는 사이트를 다시 로드하라는 브라우저의 메시지가 표시되면 확인합니다.
