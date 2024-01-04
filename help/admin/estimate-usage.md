---
title: Customer Journey Analytics 사용량 보기 및 관리
description: 사용량을 예측하는 두 가지 방법과 이를 관리하는 한 가지 방법이 표시됩니다.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 71%

---

# Customer Journey Analytics 사용량 보기 및 관리

Customer Journey Analytics 사용량을 보려면 다음과 같은 몇 가지 방법을 사용할 수 있습니다.

* 각 연결의 이벤트 데이터 행을 추가합니다. 다음을 참조하십시오 [연결 크기 예상](#estimate-connection-size) 아래요. 이는 연결당 특정 타임스탬프의 이벤트 행 데이터를 쉽게 확인하는 방법입니다.

* 세 가지 방법으로 사용량을 확인합니다. 각 방법은 아래에 자세히 설명합니다.
   * Analysis Workspace를 사용하여 지난달 이벤트를 보고합니다.
   * Report Builder를 사용하여 지난달 이벤트를 보고합니다.
   * Customer Journey Analytics API를 사용하여 자동화된 보고서를 만듭니다.

Customer Journey Analytics 사용을 관리하려면:

* 롤링 데이터 창을 정의합니다.

## 연결 크기 예상 {#estimate-size}

현재 [!UICONTROL Customer Journey Analytics]에 있는 이벤트 데이터의 행 수를 알고 있어야 합니다. 조직의 이벤트 데이터 레코드(데이터 행) 사용에 대한 정확한 정보를 얻으려면 **조직에서 만든 각 연결**&#x200B;에 대해 다음 작업을 수행하십시오.

>[!NOTE]
>
>해당 날짜에 Adobe에서 최신 사용량 보고서가 실행되므로 매월 첫 번째 금요일에 이 작업을 수행하십시오.

1. [!UICONTROL Customer Journey Analytics]에서 **[!UICONTROL 연결]** 탭을 클릭합니다.

   이제 모든 현재 연결 목록을 볼 수 있습니다.

1. 각 연결 이름을 클릭하여 연결 관리자로 이동합니다.

1. 조직에서 생성한 모든 연결에 **[!UICONTROL 사용 가능한 이벤트 데이터 기록]**&#x200B;을 추가합니다. (연결 크기에 따라 숫자가 표시되는 데 다소 시간이 걸릴 수 있습니다.)

   ![사용 가능한 이벤트 데이터 레코드.](./assets/event-data.png)

   >[!CAUTION]
   >
   >   이 수는 프로필 또는 조회 데이터에는 적용되지 않고 이벤트 데이터에만 적용됩니다. 프로필 및 조회 데이터가 있는 경우 이 수가 약간 높아질 수 있습니다. 하지만 현재는 사용자 인터페이스에서 프로필 및 조회 데이터 사용량에 대해 보고할 방법이 없습니다. 이 기능은 2023년 출시 예정입니다.

1. 모든 이벤트 데이터 행의 합계가 있으면 회사가 Adobe와 체결한 Customer Journey Analytics 계약에서 “데이터 행” 자격을 조회하십시오.

   이렇게 하면 판매 주문서에서 승인된 최대 데이터 행 수를 얻을 수 있습니다. 3단계로 인해 발생한 데이터 행 수가 이 숫자보다 크면 초과가 발생합니다.

1. 이 상황을 해결하려면 다음과 같은 몇 가지 옵션이 있습니다.

   * [데이터 보존 설정](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ko-KR#set-rolling-window-for-connection-data-retention)을 변경합니다.
   * [사용하지 않는 연결을 삭제합니다](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ko-KR#implications-of-deleting-data-components).
   * [Adobe Experience Platform에서 데이터 세트 삭제](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ko-KR#implications-of-deleting-data-components).
   * 추가 용량의 라이센스를 얻으려면 Adobe 계정 팀에 문의하십시오.

## 모든 이벤트 데이터를 사용하여 작업 영역 프로젝트 만들기 {#workspace-event-data}

이 메서드를 사용하여 사용량 데이터와 사용량 내역을 보다 자세히 분석할 수 있습니다.

1. 작업 영역에서 프로젝트를 만들기 전에 필터를 적용하지 않고 각 연결의 [데이터 보기를 만듭니다](/help/data-views/create-dataview.md).

>[!WARNING]
>
>    사용량이 두 배가 될 수 있으므로 사용량을 측정하는 모든 데이터를 포함하는 새 연결은 만들지 않습니다.

1. 작업 영역에서 각 데이터 보기에 따라 새 프로젝트를 만들고 (에서) 모든 이벤트를 가져옵니다. **[!UICONTROL 지표]** 드롭다운 목록)을 클릭하면 현재 Customer Journey Analytics 계약의 첫째 날부터 월의 첫째 금요일까지 표시됩니다.

   ![이벤트를 표시하는 자유 형식 테이블입니다.](./assets/events-usage.png)

   이로써 월별 사용량의 추세를 알 수 있습니다.

1. 요구 사항에 따라 데이터 세트 등으로 드릴다운할 수 있습니다.

## Report Builder에서 데이터 블록 만들기 {#arb}

Report Builder에서 각 데이터 보기에 대해 [하나의 데이터 블록을 만든](/help/report-builder/create-a-data-block.md) 다음 합계합니다.

## Customer Journey Analytics API에서 자동화된 보고서 만들기 {#api-report}

1. 사용 [Customer Journey Analytics 보고 API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) 모든 이벤트 데이터에 대해 보고서를 실행하려면 **모든 연결에 대해**. 이를 설정하면 보고서가 실행됨

   * 매월 첫째 주 금요일마다.
   * 현재 Customer Journey Analytics 계약의 첫 날로 돌아갑니다.

   이로써 월별 사용량의 추세를 알 수 있습니다. 모든 Customer Journey Analytics 연결의 총 행 수를 제공합니다.

1. Excel을 사용하여 이 보고서를 추가로 사용자 정의합니다.

## 롤링 데이터 창을 정의하여 사용량 관리 {#rolling}

사용을 관리하려면 [연결 UI](/help/connections/create-connection.md) Customer Journey Analytics 데이터 보존을 연결 수준에서 개월(1개월, 3개월, 6개월 등) 단위의 롤링 기간으로 정의할 수 있습니다.

주요 이점은 적용 가능하고 유용한 데이터에 대해서만 저장하거나 보고하고 더 이상 유용하지 않은 오래된 데이터를 삭제한다는 것입니다. 계약 한도를 유지하고 초과 비용의 위험을 줄이는 데 도움이 됩니다.

기본값(선택 해제)을 그대로 두면 보존 기간이 Adobe Experience Platform 데이터 보존 설정으로 대체됩니다. Experience Platform에 25개월 분량의 데이터가 있는 경우 Customer Journey Analytics은 채우기를 통해 25개월 분량의 데이터를 받습니다. 플랫폼에서 이러한 개월 중 10개월을 삭제하면 Customer Journey Analytics는 나머지 15개월을 유지합니다.

데이터 보존은 이벤트 데이터 세트 타임스탬프를 기반으로 하며 이벤트 데이터 세트에만 적용됩니다. 적용 가능한 타임스탬프가 없기 때문에 프로필 또는 조회 데이터 세트에 대한 롤링 데이터 기간 설정이 없습니다. 연결에 프로필 또는 조회 데이터 세트가 포함된 경우 이벤트 데이터 세트와 연결되므로 데이터는 이벤트 데이터 세트 타임스탬프의 데이터 보존 설정에 따라 Customer Journey Analytics에 유지됩니다.

