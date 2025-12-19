---
title: 삭제 영향
description: Customer Journey Analytics 또는 Experience Platform 개체의 삭제 또는 재설정이 갖는 의미를 이해합니다.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: c8b646b7e92663ed9c7e8454a336d25e34415cbe
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 11%

---

# 삭제 및 재설정 의미

Customer Journey Analytics 또는 Experience Platform 개체의 삭제 또는 재설정은 영향을 줍니다. 이러한 의미는 이 문서에 요약되어 있습니다.

## Customer Journey Analytics

Customer Journey Analytics에서 연결, 데이터 보기 또는 데이터 세트를 삭제하기 전에 다음 의미를 고려하십시오.

| 액션 | 의미 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics]에서 연결을 삭제 | 오류 메시지에 다음 내용이 표시됩니다.<ul><li>삭제된 연결에 대해 만들어진 모든 데이터 보기가 더 이상 작동하지 않습니다.</li><li> 마찬가지로 삭제된 연결의 데이터 보기에 의존하는 모든 Workspace 프로젝트가 작동하지 않습니다.</li></ul>다음과 같은 Customer Journey Analytics 연결은 삭제할 수 없습니다.<ul><li>권한이 없는 Adobe Experience Platform 샌드박스에 연결되어 있습니다. 이러한 연결을 기반으로 구축된 데이터 보기에 대한 권한이 있어도 기본 Adobe Experience Platform 샌드박스에 대한 권한이 부여될 때까지 연결을 삭제할 수 없습니다.</li><li>연결과 연결된 데이터 보기에 대해 다음 호환성 옵션을 선택했습니다. **[!UICONTROL Adobe Journey Optimizer에서 기본 데이터 보기로 설정]**<p>이 구성 옵션에 대한 자세한 내용은 [데이터 보기 만들기 또는 편집](/help/data-views/create-dataview.md#compatibility)에서 [호환성](/help/data-views/create-dataview.md)을 참조하십시오.</p></li></ul> |
| [!UICONTROL Customer Journey Analytics]에서 데이터 세트 삭제 | Customer Journey Analytics의 연결에서 데이터 세트를 삭제하면 해당 데이터 세트를 사용하는 모든 데이터 보기 및 프로젝트가 더 이상 작동하지 않습니다. |
| [!UICONTROL Customer Journey Analytics]에서 데이터 보기를 삭제 | Customer Journey Analytics에서 데이터 보기를 삭제하면 Workspace 프로젝트의 데이터 보기에 의존하는 모든 패널이 더 이상 제대로 작동하지 않습니다. |



## Experience Platform

데이터 세트 또는 배치를 삭제하기 전에 또는 Experience Platform에서 샌드박스를 재설정하거나 삭제할 때 다음과 같은 영향을 고려하십시오.

| 액션 | 의미 |
| --- | --- |
| [!UICONTROL Experience Platform]에서 데이터 세트 삭제 | Experience Platform의 해당 데이터 세트에서 해당 데이터 세트를 포함하는 모든 연결로의 데이터 흐름이 중지됩니다. 해당 데이터 세트의 데이터는 연관된 Customer Journey Analytics 연결에서 자동으로 삭제됩니다. |
| [!UICONTROL Experience Platform]의 데이터 세트에서 일괄 처리 삭제 | [!UICONTROL Adobe Experience Platform] 데이터 집합에서 일괄 처리가 삭제되면 해당 특정 일괄 처리가 들어 있는 [!UICONTROL Customer Journey Analytics] 연결에서 동일한 일괄 처리가 제거됩니다. [!UICONTROL Customer Journey Analytics]는 [!UICONTROL Adobe Experience Platform]에서 삭제된 배치에 대한 알림을 받습니다. |
| 일괄 처리를 [!UICONTROL Experience Platform] **수집하는 동안**&#x200B;에서 [!UICONTROL Customer Journey Analytics]&#x200B;(으)로 삭제 | 데이터 세트에 배치가 한 개만 있는 경우 해당 배치의 데이터가 [!UICONTROL Customer Journey Analytics]에서 전혀 표시되지 않거나 일부 표시됩니다. 수집이 롤백됩니다. 데이터 세트에 5개의 일괄 처리가 있고 그 중 3개가 이미 4번째 일괄 처리가 삭제되었을 때 수집된 경우, 해당 3개 일괄 처리의 데이터가 [!UICONTROL Customer Journey Analytics]에 나타납니다. |
| [!UICONTROL Experience Platform]에서 조회 데이터 세트 삭제 | 다른 소스 커넥터에 대해 데이터 세트를 삭제하는 것은 가능하지만 [Analytics 분류 Source 커넥터](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications) 데이터 세트는 삭제할 수 없습니다. 이러한 데이터 세트를 실수로 삭제한 경우 고객 지원 센터에 문의하십시오. |
| Experience Platform에서 샌드박스 삭제 또는 재설정 | [Experience Platform 샌드박스를 삭제](https://experienceleague.adobe.com/ko/docs/experience-platform/sandbox/ui/user-guide#delete-a-sandbox)하면 해당 샌드박스의 모든 스키마, 데이터 세트, 배치, 정책 등도 삭제됩니다. 샌드박스 식별자 및 샌드박스 이름뿐만 아니라 샌드박스가 더 이상 존재하지 않습니다.<br/>Experience Platform 샌드박스를 [재설정](https://experienceleague.adobe.com/ko/docs/experience-platform/sandbox/ui/user-guide#reset-a-sandbox)하면 해당 샌드박스의 모든 스키마, 데이터 세트, 배치, 정책 등이 삭제됩니다. 샌드박스 이름 및 권한은 그대로 유지되지만 재설정이 완료된 후에는 샌드박스 식별자가 변경됩니다.<br/><br/>Customer Journey Analytics은 샌드박스 식별자 및 샌드박스 이름을 사용하여 연결을 샌드박스와 연결합니다. 그 결과는 다음과 같습니다. <ul><li>삭제되거나 재설정된 샌드박스와 연결된 연결이 삭제됩니다.</li><li>삭제된 연결을 기반으로 하는 데이터 보기(및 데이터 보기 내의 파생 필드 등 모든 구성 요소 정의)는 삭제됩니다.</li><li>삭제된 데이터 보기에 의존하는 구성 요소가 삭제됩니다. 세그먼트, 계산된 지표, 주석, 경고, 게시된 대상자 및 내보내기 등이 있습니다.</li><li>삭제된 데이터 보기를 참조하는 Workspace 프로젝트의 패널을 사용할 수 없게 됩니다. 이러한 패널에 **[!UICONTROL 알 수 없는 데이터 보기]** 오류가 표시됩니다. 이러한 패널을 제거하거나, 가능한 경우 이러한 패널을 기존 데이터 보기와 연결합니다.</li><li>BI 확장을 사용하는 도구 또는 쿼리 서비스를 사용하여 Customer Journey Analytics 내에서 이미 사용할 수 있는 삭제된 연결에서 데이터를 더 이상 쿼리하지 말아야 합니다. 결국 Adobe 지원 또는 엔지니어링은 Customer Journey Analytics에서 이 데이터를 삭제합니다.</li></ul>Experience Platform에서 샌드박스를 재설정하거나 삭제해야 하는 경우 샌드박스를 재설정하거나 삭제하기 전에 다음 사항을 고려하십시오.<ul><li>연결을 나열하여 샌드박스에 속한 연결을 파악합니다.</li><li>데이터 보기를 나열하여 연결과 관련된 데이터 보기를 이해합니다.</li><li>중요한 Workspace 프로젝트를 식별하고 해당 프로젝트가 패널에서 참조하는 데이터 보기를 이해합니다.</li><li>BI 확장을 사용하는 도구와의 통합을 식별하고 이러한 통합이 사용하는 데이터 보기를 이해합니다.</li></ul> |
