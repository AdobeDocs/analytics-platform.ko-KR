---
title: Customer Journey Analytics로 업그레이드할 때 데이터 세트 수집 모니터링
description: Customer Journey Analytics으로 업그레이드할 때 데이터 세트 수집을 모니터링하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 14%

---

# Customer Journey Analytics로 업그레이드할 때 데이터 세트 수집 모니터링 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="데이터 세트의 데이터 검증"
>abstract="구현을 구성했으므로 이제 데이터 세트 활동 관리자를 사용하여 수집된 일괄 처리와 실패한 일괄 처리를 볼 수 있습니다. 주로 수집된 배치가 보이면 이 단계가 완료됩니다. 주로 실패한 일괄 처리가 있거나 일괄 처리가 없는 경우, Adobe에 데이터를 올바르게 보내고 있는지 구현을 확인하십시오."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

웹 SDK 또는 API 구현을 구성한 후에는 개별 배치의 상태를 확인하여 데이터가 데이터 세트에 수집되고 있는지 확인해야 합니다.

1. Experience Platform UI의 왼쪽 탐색에서 **[!UICONTROL 모니터링]**&#x200B;을 선택합니다.

   모니터링 대시보드가 표시됩니다. 이 대시보드를 사용하면 일괄 처리 또는 스트리밍 수집에서 인바운드 데이터의 상태를 볼 수 있습니다.

   <!-- insert screenshot -->

1. 일괄 처리 목록을 보려면 **[!UICONTROL 일괄 처리 전체]**&#x200B;를 선택하십시오.

   일괄 처리가 표시되지 않으면 Adobe에 데이터를 올바르게 보내고 있는지 구현을 확인하십시오.

   <!-- insert screenshot -->

1. 지정된 데이터 세트에 대한 배치 ID를 선택한 다음 **[!UICONTROL 상태]** 필드에 **[!UICONTROL 성공]**&#x200B;이 표시되는지 확인하십시오.

   **[!UICONTROL 상태]** 필드에 **[!UICONTROL 실패]**&#x200B;가 표시되면 구현을 확인하여 Adobe에 데이터를 올바르게 보내고 있는지 확인하십시오.

   이 단계를 반복하여 각 배치의 상태를 확인합니다.

{{upgrade-final-step}}

