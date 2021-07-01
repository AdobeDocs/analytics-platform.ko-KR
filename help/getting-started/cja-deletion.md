---
title: 삭제 의미
description: Customer Journey Analytics 또는 Adobe Experience Platform에서 연결, 데이터 세트 또는 배치를 삭제할 때 발생하는 작업
source-git-commit: 3fa2c562abaf4aa1f18baa5de5ee66c7ad828f52
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 68%

---

# 삭제 의미

Customer Journey Analytics 또는 Adobe Experience Platform에서 연결, 데이터 세트 또는 배치를 삭제하기 전에 이를 고려하십시오.

| 새... | 다음 상황이 발생하는 경우 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics]에서 연결을 삭제하시겠습니까 | 오류 메시지에 다음 내용이 표시됩니다.<ul><li>삭제된 연결에 대해 만들어진 모든 데이터 보기가 더 이상 작동하지 않습니다.</li><li> 마찬가지로, 삭제된 연결의 데이터 보기에 의존하는 모든 Analysis Workspace 프로젝트의 작동이 정지됩니다.</li></ul> |
| [!UICONTROL Adobe Experience Platform]에서 데이터 세트 삭제(AEP) | AEP에서 데이터 세트를 삭제하면 해당 데이터 세트에서 해당 데이터 세트를 포함하는 모든 연결로의 데이터 흐름이 중지됩니다. 해당 데이터 세트의 데이터는 연관된 CJA 연결에서 자동으로 삭제되지 않습니다. |
| [!UICONTROL Customer Journey Analytics]에서 데이터 세트를 삭제하시겠습니까 | 현재 저장된 연결 내에서는 데이터 세트를 삭제할 수 없습니다. 전체 연결을 삭제하고 다시 시작해야 합니다. (그러나 [!UICONTROL Adobe Experience Platform]에서 데이터 세트를 삭제할 수 있습니다.) |
| 데이터 세트에서 일괄 처리를 삭제합니다( [!UICONTROL Adobe Experience Platform]에서). | [!UICONTROL Adobe Experience Platform] 데이터 세트에서 일괄 처리가 삭제되면 해당 특정 일괄 처리가 들어 있는 [!UICONTROL Customer Journey Analytics] 연결에서 동일한 일괄 처리가 제거됩니다. [!UICONTROL Customer Journey Analytics]는 [!UICONTROL Adobe Experience Platform]에서 삭제된 일괄 처리에 대한 알림을 받습니다. |
| 일괄 처리를 **Customer Journey Analytics**&#x200B;에 [!UICONTROL 수집하는 동안] 삭제하시겠습니까 | 데이터 세트에 일괄 처리가 한 개만 있는 경우, 해당 일괄 처리의 데이터가 [!UICONTROL Customer Journey Analytics]에서 전혀 표시되지 않거나 일부 표시됩니다. 처리가 롤백됩니다. 데이터 세트에 5개의 일괄 처리가 있고 그 중 3개가 이미 데이터 세트를 삭제할 때 수집된 경우, 해당 3개 일괄 처리의 데이터가 [!UICONTROL Customer Journey Analytics]에 표시됩니다. |
| [!UICONTROL Adobe Experience Platform]에서 조회 데이터 세트 삭제 | 다른 소스 커넥터에서 데이터 세트를 삭제할 수 있지만 현재 [Analytics 분류 데이터 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=en)에 대해서는 지원되지 않습니다. 실수로 데이터 세트를 삭제하는 경우 Adobe 고객 지원 센터에 문의하십시오. |