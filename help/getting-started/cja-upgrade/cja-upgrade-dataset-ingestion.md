---
title: Customer Journey Analytics로 업그레이드할 때 데이터 세트 수집 모니터링
description: Customer Journey Analytics로 업그레이드할 때 데이터 세트 수집 모니터링 방법 자세히 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 100%

---

# Customer Journey Analytics로 업그레이드할 때 데이터 세트 수집 모니터링 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="데이터 세트의 데이터 검증"
>abstract="구현을 구성했으므로, 데이터 세트 활동 관리자를 사용하여 수집된 배치와 실패한 배치를 확인할 수 있습니다. 주로 수집된 배치가 보이면 이 단계가 완료됩니다. 주로 실패한 배치가 있거나 배치가 없는 경우 구현을 확인하여 Adobe로 데이터를 올바르게 전송하고 있는지 확인합니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Web SDK 또는 API 구현을 구성한 후에는 개별 배치의 상태를 확인하여 데이터가 데이터 세트에 수집되고 있는지 확인해야 합니다.

1. Experience Platform UI의 왼쪽 탐색 창에서 **[!UICONTROL 모니터링]**&#x200B;을 선택합니다.

   모니터링 대시보드가 표시됩니다. 이 대시보드를 사용하면 배치 또는 스트리밍 수집에서 수신되는 데이터의 상태를 확인할 수 있습니다.

   <!-- insert screenshot -->

1. 배치 목록을 보려면 **[!UICONTROL 전체 일괄 처리]**&#x200B;를 선택합니다.

   배치가 표시되지 않으면 구현을 확인하여 Adobe로 데이터를 올바르게 전송하고 있는지 확인합니다.

   <!-- insert screenshot -->

1. 주어진 데이터 세트에 대한 배치 ID를 선택한 후 **[!UICONTROL 상태]** 필드에 **[!UICONTROL 성공]**&#x200B;이 표시되는지 확인합니다.

   **[!UICONTROL 상태]** 필드에 **[!UICONTROL 실패]**&#x200B;가 표시되는 경우 구현을 확인하여 Adobe로 데이터를 올바르게 전송하고 있는지 확인합니다.

   각 배치의 상태를 확인하려면 이 단계를 반복합니다.

{{upgrade-final-step}}

