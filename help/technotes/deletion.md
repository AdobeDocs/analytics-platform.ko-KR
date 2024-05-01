---
title: 삭제 영향
description: Customer Journey Analytics 또는 Adobe Experience Platform에서 연결, 데이터 세트 또는 배치를 삭제할 때 발생하는 일에 대한 내용입니다.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 71%

---

# 삭제 영향

Customer Journey Analytics 또는 Adobe Experience Platform에서 연결, 데이터 세트 또는 배치를 삭제하기 전에 이 내용을 고려하십시오.

| 다음 작업을 수행하는 경우 | 발생하는 결과 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics]에서 연결을 삭제 | 오류 메시지에 다음 내용이 표시됩니다.<ul><li>삭제된 연결에 대해 만들어진 모든 데이터 보기가 더 이상 작동하지 않습니다.</li><li> 마찬가지로, 삭제된 연결의 데이터 보기에 의존하는 모든 Analysis Workspace 프로젝트의 작동이 정지됩니다.</li></ul>권한이 없는 Adobe Experience Platform 샌드박스에 연결된 Customer Journey Analytics 연결은 삭제할 수 없습니다. 이러한 연결을 기반으로 구축된 데이터 보기에 대한 권한이 있어도 기본 Adobe Experience Platform 샌드박스에 대한 권한이 부여될 때까지 연결을 삭제할 수 없습니다. |
| 에서 데이터 세트 삭제 [!UICONTROL Adobe Experience Platform] | AEP에서 데이터 세트를 삭제하면 해당 데이터 세트에서 해당 데이터 세트를 포함하는 모든 연결로의 데이터 흐름이 중지됩니다. 해당 데이터 세트의 모든 데이터는 연관된 Customer Journey Analytics 연결에서 자동으로 삭제됩니다. |
| [!UICONTROL Customer Journey Analytics]에서 데이터 세트 삭제 | Customer Journey Analytics의 연결에서 데이터 세트를 삭제하면 해당 데이터 세트에 의존한 모든 데이터 보기 및 프로젝트가 더 이상 작동하지 않습니다. |
| [!UICONTROL Adobe Experience Platform]의 데이터 세트에서 배치를 삭제 | [!UICONTROL Adobe Experience Platform] 데이터 세트에서 일괄 처리가 삭제되면 해당 특정 일괄 처리가 들어 있는 [!UICONTROL Customer Journey Analytics] 연결에서 동일한 일괄 처리가 제거됩니다. [!UICONTROL Customer Journey Analytics]는 [!UICONTROL Adobe Experience Platform]에서 삭제된 일괄 처리에 대한 알림을 받습니다. |
| 배치를 **Customer Journey Analytics**&#x200B;에 [!UICONTROL 수집하는 동안] 배치를 삭제 | 데이터 세트에 일괄 처리가 한 개만 있는 경우, 해당 일괄 처리의 데이터가 [!UICONTROL Customer Journey Analytics]에서 전혀 표시되지 않거나 일부 표시됩니다. 처리가 롤백됩니다. 데이터 세트에 5개의 일괄 처리가 있고 그 중 3개가 이미 데이터 세트를 삭제할 때 수집된 경우, 해당 3개 일괄 처리의 데이터가 [!UICONTROL Customer Journey Analytics]에 표시됩니다. |
| 조회 데이터 세트 삭제 [!UICONTROL Adobe Experience Platform] | 다른 소스 커넥터에 대해 데이터 세트를 삭제하는 것은 가능하지만 현재 [Analytics 분류 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html)에 대해서는 이 기능이 지원되지 않습니다. 실수로 데이터 세트를 삭제하는 경우 Adobe 고객 지원 센터에 문의하십시오. |
