---
title: CJA 사용 예측 및 관리
description: 사용량을 추정하는 두 가지 방법과 이를 관리하는 방법을 보여 줍니다.
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: d80a4c277fa1ebd2a354aa454d1356a8561bb517
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 43%

---

# CJA 사용 예측 및 관리

CJA 사용을 이해하기 위해 다음 3가지 방법을 사용할 수 있습니다.

* 각 연결에 대한 이벤트 데이터 행을 추가합니다. (자세한 내용은 **연결 크기 예상** 아래)은 특정 타임스탬프에 대한 연결당 이벤트 행 데이터를 쉽게 볼 수 있는 방법입니다.
* Analysis Workspace을 사용하여 지난달의 이벤트에 대해 보고합니다. (자세한 내용은 **모든 이벤트 데이터를 사용하여 작업 공간 프로젝트 만들기** 아래에 나열된 상태로 남아 있습니다.) 이를 통해 사용 내역 및 사용량 데이터를 보다 심층적으로 분석할 수 있습니다.
* CJA API를 사용하여 자동화된 보고서를 만듭니다. (자세한 내용은 **CJA API에서 보고서 만들기** 아래에 나열된 상태로 남아 있습니다.)

CJA 사용을 관리하려면:

* 롤링 데이터 창을 정의합니다. (자세한 내용은 **롤링 데이터 창 정의** 아래에 나열된 상태로 남아 있습니다.)

## 연결 크기 예상 {#estimate-size}

현재 있는 이벤트 데이터의 행 수를 알고 있어야 합니다 [!UICONTROL Customer Journey Analytics]. 조직의 이벤트 데이터 레코드(데이터 행) 사용에 대한 정확한 정보를 얻으려면 **조직에서 만든 각 연결**&#x200B;에 대해 다음 작업을 수행하십시오.

>[!NOTE]
>
>Adobe이 해당 날짜에서 최신 사용량 보고서를 실행하므로 매월 첫 번째 금요일에 그렇게 합니다.

1. [!UICONTROL Customer Journey Analytics]에서 **[!UICONTROL 연결]** 탭을 클릭합니다.

   이제 모든 현재 연결 목록을 볼 수 있습니다.

1. 각 연결 이름을 클릭하여 연결 관리자로 이동합니다.

1. 추가 **[!UICONTROL 사용 가능한 이벤트 데이터 레코드]** 을 입력합니다. (연결 크기에 따라 숫자가 표시되는 데 다소 시간이 걸릴 수 있습니다.)

   ![이벤트 데이터](assets/event-data.png)

   >[!CAUTION]
   >
   >   이 카운트는 프로필 또는 조회 데이터가 아닌 이벤트 데이터만 적용됩니다. 프로필 및 조회 데이터가 있는 경우 카운트가 약간 더 높습니다. 그러나 현재 사용자 인터페이스에서 프로필 및 조회 데이터 사용을 보고할 방법은 없습니다. 이 기능은 2023년에 제공될 예정입니다.

1. 모든 이벤트 데이터 행의 합계가 있으면 회사가 Adobe와 체결한 Customer Journey Analytics 계약에서 “데이터 행” 자격을 조회하십시오.

   이렇게 하면 판매 주문서에서 승인된 최대 데이터 행 수를 얻을 수 있습니다. 3단계로 인해 발생한 데이터 행 수가 이 숫자보다 크면 초과가 발생합니다.

1. 이 상황을 해결하려면 다음과 같은 몇 가지 옵션이 있습니다.

   * [데이터 보존 설정](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ko-KR#set-rolling-window-for-connection-data-retention)을 변경합니다.
   * [사용하지 않는 연결을 삭제합니다](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ko-KR#implications-of-deleting-data-components).
   * [AEP에서 데이터 세트를 삭제합니다](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ko-KR#implications-of-deleting-data-components).
   * 추가 용량 라이선스를 얻으려면 Adobe 계정 관리자에게 문의하십시오.

## 모든 이벤트 데이터를 사용하여 작업 공간 프로젝트 만들기 {#workspace-event-data}

1. Workspace에서 프로젝트를 만들기 전에 [데이터 보기 만들기](/help/data-views/create-dataview.md) 적용된 필터 없이 각 연결에 대해

1. Workspace에서 각 데이터 보기를 기반으로 새 프로젝트를 만들고 모든 이벤트(에서)를 가져옵니다 **[!UICONTROL 지표]** 드롭다운) 현재 CJA 계약의 첫 날로 시작하여 그 달의 첫 번째 금요일까지 옵니다.

   ![이벤트](assets/events-usage.png)

   따라서 월별 사용 트렌드를 파악할 수 있습니다.

1. 필요에 따라 데이터 세트 등으로 드릴다운할 수 있습니다.


## CJA API에서 자동화된 보고서 만들기 {#api-report}

1. 를 사용하십시오 [CJA 보고 API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) 모든 이벤트 데이터에 대한 보고서를 실행하려면 **모든 연결에 대해**. 보고서가 실행되도록 설정합니다

   * 매달 셋째 주 금요일에.
   * 현재 CJA 계약의 첫 날로 돌아갑니다.

   따라서 월별 사용 트렌드를 파악할 수 있습니다. 모든 CJA 연결에 대한 총 행 수를 제공합니다.

1. 이 보고서를 더 사용자 지정하려면 Excel을 사용하십시오.

## 롤링 데이터 창 정의 {#rolling}

사용을 관리하려면 [연결 UI](/help/connections/create-connection.md) cja 데이터 보존 을 연결 수준에서 월(1개월, 3개월, 6개월 등)로 롤링 창으로 정의할 수 있습니다.

주요 이점은 적용 가능하고 유용한 데이터에 대해서만 저장하거나 보고하고 더 이상 유용하지 않은 오래된 데이터를 삭제한다는 것입니다. 계약 한도를 유지하고 초과 비용의 위험을 줄이는 데 도움이 됩니다.

기본값(선택 해제)을 그대로 두면 보존 기간이 Adobe Experience Platform 데이터 보존 설정으로 대체됩니다. Experience Platform에 25개월 분량의 데이터가 있는 경우 CJA는 채우기를 통해 25개월 분량의 데이터를 받습니다. 플랫폼에서 이러한 개월 중 10개월을 삭제하면 CJA는 나머지 15개월을 유지합니다.

데이터 보존은 이벤트 데이터 세트 타임스탬프를 기반으로 하며 이벤트 데이터 세트에만 적용됩니다. 적용 가능한 타임스탬프가 없기 때문에 프로필 또는 조회 데이터 세트에 대한 롤링 데이터 기간 설정이 없습니다. 그러나 연결에 프로필 또는 조회 데이터 세트(하나 이상의 이벤트 데이터 세트 제외)가 포함된 경우 해당 데이터는 동일한 기간 동안 유지됩니다.

