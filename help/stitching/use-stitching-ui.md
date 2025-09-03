---
title: 스티칭 사용
description: 결합 사용 방법
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 4bca14492374939cd1ea6508c774720db61a6283
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 3%

---

# 스티칭 사용

연결의 일부로 구성한 하나 이상의 이벤트 데이터 세트에 대한 결합을 활성화할 수 있습니다. 결합에 활성화할 수 있는 이벤트 데이터 세트의 수는 라이센스가 부여된 Customer Journey Analytics 패키지에 의해 결정됩니다.

[연결을 만들거나](/help/connections/create-connection.md#dataset-settings) [연결을 편집](/help/connections/create-connection.md)할 때 이벤트 데이터 세트에 대한 [데이터 세트 설정](/help/connections/manage-connections.md#edit-a-connection)의 일부로 연결을 활성화할 수 있습니다.

결합을 활성화하려면 **[!UICONTROL 데이터 세트 추가]** 또는 **[!UICONTROL 데이터 세트 편집]** 대화 상자의 이벤트 데이터 세트 섹션에서 다음을 수행합니다.

![ID 결합을 활성화할 때 ID 결합 옵션](assets/identity-stitching-ui.png)

1. **[!UICONTROL ID 연결 사용]**&#x200B;을 선택합니다.

   기존 이벤트 데이터 세트에 대해 연결을 활성화하면 **[!UICONTROL 개인 ID 변경]** 대화 상자에 연결 사용으로 인한 개인 ID 변경의 의미가 표시됩니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

   **[!UICONTROL ID 연결 사용]** 대화 상자에는 ID 연결 결과가 요약되어 있습니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

1. **[!UICONTROL 영구 ID]** 드롭다운 메뉴에서 영구 ID를 선택합니다.

   영구 ID로 **[!UICONTROL ID 맵]**&#x200B;을(를) 선택하는 경우 네임스페이스 를 선택해야 합니다. 두 가지 옵션이 있습니다.

   * 기본 ID 네임스페이스를 사용하려면 **[!UICONTROL 기본 ID 네임스페이스를 사용]**&#x200B;하세요.
   * **[!UICONTROL 네임스페이스]** 드롭다운 메뉴에서 네임스페이스를 선택합니다.

1. **[!UICONTROL 개인 ID]** 드롭다운 메뉴에서 개인 ID를 선택합니다.

   개인 ID로 **[!UICONTROL ID 맵]**&#x200B;을(를) 선택하는 경우 네임스페이스를 선택해야 합니다. 두 가지 옵션이 있습니다.

   * 기본 ID 네임스페이스를 사용하려면 **[!UICONTROL 기본 ID 네임스페이스를 사용]**&#x200B;하세요.
   * **[!UICONTROL 네임스페이스]** 드롭다운 메뉴에서 네임스페이스를 선택합니다.

   개인 ID로 **[!UICONTROL ID 그래프]**&#x200B;를 선택하는 경우 네임스페이스를 선택해야 합니다. 그 전에 결합을 위해 ID 그래프를 사용하기 전에 ID 그래프 설정을 완료했는지 확인하는 **[!UICONTROL ID 그래프로 변경]** 대화 상자가 표시됩니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

   * **[!UICONTROL 네임스페이스]** 드롭다운 메뉴에서 네임스페이스를 선택합니다.


1. **[!UICONTROL 전환 확인 기간]** 드롭다운 메뉴에서 전환 확인 기간을 선택합니다. 옵션은 **[!UICONTROL 1일]**, **[!UICONTROL 7일]**, **[!UICONTROL 14일]** 또는 **[!UICONTROL 30일]**&#x200B;입니다.
