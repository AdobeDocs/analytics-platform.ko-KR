---
title: Customer Journey Analytics로 업그레이드할 때 데이터 세트 수집 모니터링
description: Customer Journey Analytics으로 업그레이드할 때 데이터 세트 수집을 모니터링하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 32%

---

# Customer Journey Analytics로 업그레이드할 때 데이터 세트 수집 모니터링 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="데이터 세트의 데이터 검증"
>abstract="Web SDK 구현을 구성했으므로, 데이터 세트 활동 관리자를 사용하여 수집된 배치와 실패한 배치를 확인할 수 있습니다. 주로 수집된 배치가 보이면 이 단계가 완료됩니다. 주로 실패한 배치가 있거나 배치가 없는 경우 Web SDK 구현을 확인하여 Adobe로 데이터를 올바르게 전송하고 있는지 확인합니다.<br><br>모든 것이 올바르고 완벽하게 이루어졌다면 이 단계는 하루 안에 완료될 수 있습니다. 데이터 수집에 여러 문제가 있는 경우 문제 해결에 상당한 시간이 걸릴 수 있습니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나 [Adobe Analytics-Customer Journey Analytics 업그레이드 설문지](https://gigazelle.github.io/cja-ttv/)를 통해 조직에 대해 동적으로 생성된 업그레이드 단계를 따를 수 있습니다.
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

   **[!UICONTROL 상태]** 필드에 **[!UICONTROL 실패]**&#x200B;가 표시되면 웹 SDK 구현을 확인하여 Adobe에 데이터를 올바르게 보내고 있는지 확인하십시오.

   이 단계를 반복하여 각 배치의 상태를 확인합니다.

1. [권장된 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 [동적으로 생성된 업그레이드 단계](https://gigazelle.github.io/cja-ttv/)를 계속 따릅니다.

