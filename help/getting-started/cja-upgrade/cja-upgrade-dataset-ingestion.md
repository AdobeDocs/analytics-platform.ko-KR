---
title: Customer Journey Analytics으로 업그레이드 시 데이터 세트 수집 모니터링
description: Customer Journey Analytics으로 업그레이드할 때 데이터 세트 수집을 모니터링하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a5425eccff643cd45fd630172b0113e646b2a9cc
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Customer Journey Analytics으로 업그레이드 시 데이터 세트 수집 모니터링

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

웹 SDK 구현을 구성한 후에는 개별 배치의 상태를 확인하여 데이터가 데이터 세트에 수집되고 있는지 확인해야 합니다.

1. Experience Platform UI의 왼쪽 탐색에서 **[!UICONTROL 모니터링]**&#x200B;을 선택합니다.

   모니터링 대시보드가 표시됩니다. 이 대시보드를 사용하면 일괄 처리 또는 스트리밍 수집에서 인바운드 데이터의 상태를 볼 수 있습니다.

   <!-- insert screenshot -->

1. 일괄 처리 목록을 보려면 **[!UICONTROL 일괄 처리 전체]**&#x200B;를 선택하십시오.

   일괄 처리가 표시되지 않으면 웹 SDK 구현에서 데이터를 Adobe에 올바르게 보내고 있는지 확인하십시오.

   <!-- insert screenshot -->

1. 지정된 데이터 세트에 대한 배치 ID를 선택한 다음 **[!UICONTROL 상태]** 필드에 **[!UICONTROL 성공]**&#x200B;이 표시되는지 확인하십시오.

   **[!UICONTROL 상태]** 필드에 **[!UICONTROL 실패]**&#x200B;가 표시되면 Web SDK 구현을 확인하여 Adobe에게 데이터를 올바르게 보내고 있는지 확인하십시오.

   이 단계를 반복하여 각 배치의 상태를 확인합니다.




