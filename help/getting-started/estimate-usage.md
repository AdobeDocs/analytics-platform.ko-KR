---
title: CJA 사용 예측 및 관리
description: 사용량을 추정하는 두 가지 방법과 이를 관리하는 방법을 보여 줍니다.
role: Admin
feature: CJA Basics
source-git-commit: 2bcf1f805a54581f13f7d08b9ef034535d7959b1
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 42%

---


# CJA 사용 예측 및 관리

CJA 사용을 이해하기 위해 다음 두 가지 방법을 사용할 수 있습니다.

* 각 연결에 대한 이벤트 데이터 행을 추가합니다. (자세한 내용은 **연결 크기 예상** 아래)
* Analysis Workspace을 사용하여 지난달의 이벤트에 대해 보고합니다. (자세한 내용은 **모든 이벤트 데이터를 사용하여 작업 공간 프로젝트 만들기** 아래에 나열된 상태로 남아 있습니다.)

CJA 사용을 관리하려면:

* CJA API를 사용합니다. (자세한 내용은 **CJA API에서 보고서 만들기** 아래에 나열된 상태로 남아 있습니다.)

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

1. Workspace에서 프로젝트를 만들기 전에 [데이터 보기 만들기](/help/data-views/create-dataview.md) 모든 연결에서 데이터를 가져오며 필터가 적용되지 않았습니다. 즉, 모든 데이터가 포함됩니다.

1. Workspace에서 새 프로젝트를 만들고 모든 이벤트(에서)를 가져옵니다 **[!UICONTROL 지표]** 드롭다운)을 클릭하여 제품에서 사용할 수 있습니다.

   ![이벤트](assets/events-usage.png)

1. 이 작업

## CJA API에서 보고서 만들기 {#api-report}

를 사용하십시오 [CJA 보고 API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) 를 눌러 모든 이벤트 데이터에 대해 보고서를 실행합니다.