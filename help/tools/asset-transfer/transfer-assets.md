---
title: 에셋 전송
description: 한 사용자에서 다른 사용자로 구성 요소를 전송하는 방법에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
source-git-commit: faa9545fa3928a19aeaaf7285a9643e7dc253cea
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---


# 에셋 전송

에셋 전송 도구를 사용하여 에셋의 소유권을 다른 사용자에게 이전할 수 있습니다. Assets에는 프로젝트, 필터, 날짜 범위, 계산된 지표, 주석, 경고 및 예약된 프로젝트와 같은 구성 요소가 포함될 수 있습니다.

Assets은 종종 개별 소유자에게 연결되며, 경우에 따라 필터 및 계산된 지표와 같이 관리자가 편집하거나 공유할 수 없습니다. 사용자가 조직을 떠나거나 역할이 변경될 때, 연속성과 적절한 액세스를 보장하기 위해 이러한 자산의 소유권을 다른 사용자에게 이전해야 할 수 있습니다.

## 권한

Customer Journey Analytics을 전송하려면 제품 관리자 권한이 필요합니다.

## 에셋 전송

1. CJA에서 **[!UICONTROL 도구]** > **[!UICONTROL 자산 전송]**&#x200B;으로 이동합니다.

   ![자산 전송 메뉴 항목](/help/tools/asset-transfer/assets/asset-transfer.png)

1. **[!UICONTROL 사용자]** 대화 상자에서 에셋을 전송할 사용자를 검색하고 선택합니다.

   >[!IMPORTANT]
   >
   >한 사용자에서 다른 사용자로 1:1 전송만 수행할 수 있습니다. 일대다 또는 다대일 전송은 지원되지 않습니다.


1. 사용자를 선택하면 화면 하단에 에셋 전송 옵션이 나타납니다.

   ![메뉴 옵션](/help/tools/asset-transfer/assets/after-selection.png)

1. **[!UICONTROL 자산 전송]**&#x200B;을 클릭합니다.

1. **[!UICONTROL 자산 전송]** 화면에서 먼저 자산을 전송할 수신자를 선택합니다.

1. 이제 왼쪽 탐색 영역에서 각 구성 요소 폴더를 통해 전송할 폴더의 개별 구성 요소 또는 모든 에셋을 선택합니다.

   관리자로부터 관리자가 아닌 사용자에게 자산을 전송해도 수신자가 관리자로 업그레이드되지 않습니다.

1. 폴더에서 _모두_&#x200B;개의 자산을 선택하려면 표 상단의 **[!UICONTROL 이름]** 옆에 있는 상자를 선택합니다.

   ![전송할 자산 선택](/help/tools/asset-transfer/assets/select-assets.png)

1. 모든 선택을 마친 후 오른쪽 상단의 **[!UICONTROL 전송]**&#x200B;을 클릭합니다.

1. 확인 메시지가 나타나면 **[!UICONTROL 확인]**&#x200B;을 클릭합니다.

   >[!IMPORTANT]
   >
   >공정 유산을 피하기 위해 이송 중 화면을 닫지 않도록 합니다. 이를 통해 원활한 전송 경험이 보장됩니다.

## Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 동안 에셋 전송

에셋 전송에 대한 주요 사용 사례 중 하나는 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 동안입니다.

Adobe Analytics의 [구성 요소 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) 기능을 사용하면 관리자가 소유한 프로젝트를 다른 관리자로 마이그레이션할 수 있습니다. 그런 다음 이러한 프로젝트를 구성하는 모든 구성 요소는 Customer Journey Analytics에서 다시 만들어지고 받는 사람 관리자는 구성 요소를 만든 사람에 관계없이 이러한 모든 구성 요소를 소유합니다.

이 자산 전송 도구를 사용하면 관리자가 구성 요소를 올바른 소유자에게 재할당할 수 있습니다.

## CSV로 내보내기

한 사용자에서 다른 사용자로 전송된 자산 목록을 .csv 파일로 내보낼 수 있습니다.

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->