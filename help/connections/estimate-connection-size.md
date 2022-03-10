---
title: CJA 연결 크기 예상 방법
description: 현재 Customer Journey Analytics 사용 현황 보고
exl-id: 5599b34f-342d-4c68-b7c9-2ac3ea50d078
solution: Customer Journey Analytics
feature: Connections
source-git-commit: cd48a91ca3affc39cf71451bdd8a44ca7669523b
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 51%

---

# 연결 크기 예상

현재 [!UICONTROL Customer Journey Analytics]에 있는 데이터의 행 수를 알고 있어야 합니다. 조직의 이벤트 데이터 레코드(데이터 행) 사용을 정확하게 계산하려면 다음을 수행하십시오 **조직에서 만든 각 연결에 대해**.

1. [!UICONTROL Customer Journey Analytics]에서 **[!UICONTROL 연결]** 탭을 클릭합니다.

   이제 모든 현재 연결 목록을 볼 수 있습니다.

1. 각 연결 이름을 클릭하여 연결 관리자로 이동합니다.

1. 추가 **[!UICONTROL 사용 가능한 이벤트 데이터 레코드]** 생성된 모든 연결에 대해 사용할 수 있습니다. (연결 크기에 따라 숫자가 표시되는 데 시간이 좀 걸릴 수 있습니다.)

   ![이벤트 데이터](assets/event-data.png)

1. 모든 이벤트 데이터 행의 합계가 있는 경우 회사가 Adobe으로 서명한 Customer Journey Analytics 계약에서 &quot;데이터 행&quot; 자격 조건을 조회합니다.

   이렇게 하면 판매 주문에서 승인된 데이터의 최대 행 수를 제공합니다. 3단계에서 발생한 데이터 행 수가 이 수보다 큰 경우 오버레이가 발생합니다.

1. 이 상황을 해결하기 위해 다음과 같은 몇 가지 옵션을 사용할 수 있습니다.

   * 변경 [데이터 보존 설정](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ko-KR#set-rolling-window-for-connection-data-retention).
   * [사용하지 않은 연결 삭제](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ko-KR#implications-of-deleting-data-components).
   * [AEP에서 데이터 세트 삭제](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components).
   * 추가 용량의 라이센스를 얻으려면 Adobe 계정 관리자에게 문의하십시오.

## 사용 초과 관련

사용량 제한은 Adobe에 의해 매일 엄격하게 모니터링 및 적용됩니다. 데이터 행 은 Customer Journey Analytics 내에서 분석할 수 있는 일일 평균 데이터 행을 의미합니다.

계약 자격이 행 수를 100만 개로 제한한다고 가정합니다. Customer Journey Analytics을 사용하는 1일에 200만 개의 데이터 행을 업로드한다고 가정해 보십시오. 2일에서는 100만 개의 행을 삭제하고 해당 커밋된 최대 사용 시간을 유지합니다. 1일에 대한 과사용료가 여전히 발생합니다.

## 불일치 진단

경우에 따라 연결에서 수집된 총 이벤트 수가 [!UICONTROL Adobe Experience Platform]의 데이터 세트에 있는 행 수와 다를 수 있습니다. 이 예에서 데이터 세트 &quot;B2B 노출 횟수&quot;에는 7650개의 행이 있지만 데이터 세트에 [!UICONTROL Adobe Experience Platform]의 3830개의 행이 포함됩니다. 불일치 발생에는 몇 가지 이유가 있으며 다음 단계를 수행하여 진단할 수 있습니다.

1. 이 차원을 **[!UICONTROL 플랫폼 데이터 세트 ID]**&#x200B;로 분류하면 크기가 같지만 다른 **[!UICONTROL 플랫폼 데이터 세트 ID]**&#x200B;를 사용하는 데이터 세트가 2개 있음을 알 수 있습니다. 각 데이터 세트에 3825개의 레코드가 있습니다. 즉, 개인 ID가 없거나 타임스탬프가 누락되어 [!UICONTROL Customer Journey Analytics]에서 5개의 레코드를 무시했습니다.

   ![분류](assets/data-size2.png)

1. 또한 [!UICONTROL Adobe Experience Platform]에서 체크인하는 경우, 첫 연결이 만들어졌을 때 누군가 이 특정 데이터 세트를 [!UICONTROL Adobe Experience Platform]에서 삭제했으므로 ID가 &quot;5f21c12b732044194bffc1d0&quot;인 데이터 세트가 없습니다. 나중에 Customer Journey Analytics에 다시 추가되었지만 다른 [!UICONTROL 플랫폼 데이터 세트 ID]가 [!UICONTROL Adobe Experience Platform]에 의해 생성되었습니다.

[!UICONTROL Customer Journey Analytics] 및 [!UICONTROL Adobe Experience Platform]의 [데이터 세트 및 연결 삭제에 대한 의미](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components)에 관하여 자세히 읽어보십시오.
