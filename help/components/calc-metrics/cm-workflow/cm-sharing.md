---
description: 전체 조직, 그룹 또는 개별 사용자와 지표를 공유하는 방법을 알아봅니다.
title: 계산된 지표 공유
feature: Calculated Metrics
exl-id: b2a3e4e3-f0aa-4505-b3f5-7d9f14dc1640
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 6%

---

# 계산된 지표 공유

[계산된 지표 관리자](cm-manager.md)에서 계산된 지표를 공유할 수 있습니다. 사용 권한에 따라, 전체 조직, 그룹 또는 개별 사용자와 계산된 지표를 공유할 수 있습니다.

* **관리자**: 관리자는 전체 조직, 조직 내 그룹 및 개별 사용자와 계산된 지표를 공유할 수 있습니다. 자세한 내용은 [Admin Console 설명서](https://helpx.adobe.com/kr/enterprise/using/manage-products.html)를 참조하십시오.
* **관리자가 아닌 사용자**: 관리자가 아닌 사용자는 자신이 만든 계산된 지표만 개별 사용자와 공유할 수 있습니다.

하나 이상의 계산된 지표를 공유하려면 다음을 수행하십시오.

1. [계산된 지표 관리자](cm-manager.md)에서 공유할 계산된 지표 중 하나 이상을 선택합니다.
1. 작업 표시줄에서 ![공유](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 공유]**&#x200B;를 선택합니다.
1. **[!UICONTROL 계산된 지표 공유]** 대화 상자에서:

   ![계산된 지표 공유 대화 상자](assets/share-calculated-metrics-dialog.png)

   1. (선택 사항) ![검색](/help/assets/icons/Search.svg)을 사용하여 *개인 또는 그룹을 검색*&#x200B;하고 계산된 지표를 공유할 그룹 또는 개인 목록을 제한하십시오.

   1. **[!UICONTROL 조직]** 또는 **[!UICONTROL 그룹]** 섹션에서 옵션을 하나 이상 선택하거나 한 명 이상의 개인을 검색하고 선택하십시오. 사용 가능한 옵션은 역할에 따라 다릅니다.

   1. 계산된 지표를 공유하려면 **[!UICONTROL 저장]**&#x200B;을(를) 선택하십시오. 취소하려면 **[!UICONTROL 취소]**&#x200B;를 선택합니다.

## 모범 사례

다음은 계산된 지표를 공유해야 할 때와 계산된 지표를 공유해야 할 사람에 대한 몇 가지 모범 사례입니다.

* 관리자는 조직의 누군가가 계산된 지표를 사용하는 것이 익숙하다고 확신하는 경우에만 계산된 지표를 모두와 공유하십시오. 이러한 계산된 지표를 선호하는 것도 고려할 수 있습니다. 자세한 내용은 [계산된 지표를 즐겨찾기로 표시](cm-favorite.md)를 참조하십시오.

* 관리자는 계산된 지표가 해당 그룹의 사용자 부분에 대한 비즈니스 가치를 제공하는 경우 계산된 지표를 특정 그룹과 공유할 수 있습니다.

* 관리자 또는 개별 사용자는 계산된 지표를 하나 이상의 개인과 공유하여 계산된 지표의 유효성을 검사합니다. 세그먼트가 유용하지 않은 것으로 판명되면 계산된 지표를 삭제할 수 있습니다.


<!--

Depending on your permissions, you can share metrics with your whole organization, groups, or individual users.

|  Role | Permissions |
|---|---|
|  Administrator  | Can share metrics with All, with Groups, and with Users. Groups are set up as permission groups in the Admin console.  |
|  Non-Administrator  | Can share metrics only with individual users.  |

To share a calculated metric:

1. In the Calculated metrics manager, mark the checkbox next to the metric you want to share.

   ![Calculated metrics manager showing the available icons across the top of the window including Hide Filters, Tag, Share, Delete, and Copy.](assets/cm_task_bar.png)

1. Select the **[!UICONTROL Share]** icon. ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)

   The Share Calculated metric dialog box displays.

   ![Share Calculated metric window with All selected for the Organization.](assets/cm_share.png)

1. Select **[!UICONTROL Share]**.

1. Choose who you want to share with:

   * **[!UICONTROL All]** (Administrators only): Shares with all users in the organization.

     Consider sharing with all only if it's of use to the entire company and everyone is comfortable using it. In this case, you should also consider making it an [approved metric](/help/components/calc-metrics/cm-workflow/cm-approving.md).
   
   * **[!UICONTROL Groups]** (Administrators only): Select any groups you want to share with.

     Consider sharing with a group if the metric provides good business value for that team.
   
   * **[!UICONTROL Individual users]**: Search for and select the individual users you want to share with.

      This is the only share option available to all users. Administrators might want to use this option to vet and validate a metric prior to making it available to a group or to everyone. If the metric isn't useful, it can be discarded. Administrators should not officially approve this type of metric.

1. Select **[!UICONTROL Share]**.

   The Shared icon appears next to the metric: ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg).

1. You can filter on metrics shared with you by going to **[!UICONTROL Filters]** > **[!UICONTROL Other Filters]** > **[!UICONTROL Shared with Me]**.

1. (Optional) To filter the list of calculated metrics in the Calculated metrics manager to show only metrics that are shared with you, select the **Filter** icon, expand **[!UICONTROL Other filters]**, then select **[!UICONTROL Shared with me]**.

-->