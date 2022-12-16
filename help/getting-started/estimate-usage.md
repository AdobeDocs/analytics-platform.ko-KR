---
title: CJA 사용 예측 및 관리
description: 사용량을 추정하는 두 가지 방법과 이를 관리하는 방법을 보여 줍니다.
role: Admin
feature: CJA Basics
source-git-commit: 58d582b693708f883842fb6a18cc57d481f2b2ab
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 68%

---


# CJA 사용 예측 및 관리

CJA 사용을 이해하기 위해 다음 두 가지 방법을 사용할 수 있습니다.

* 각 연결에 대한 이벤트 데이터를 추가합니다( **연결 크기 예상** 아래)
* Analysis Workspace을 사용하여..

CJA 사용을 관리하려면:

* CJA API 사용

## 연결 크기 예상 {#estimate-size}

현재 있는 이벤트 데이터의 행 수를 알고 있어야 합니다 [!UICONTROL Customer Journey Analytics]. 조직의 이벤트 데이터 레코드(데이터 행) 사용에 대한 정확한 정보를 얻으려면 **조직에서 만든 각 연결**&#x200B;에 대해 다음 작업을 수행하십시오.

>[!NOTE]
>
>Adobe이 해당 날짜에서 최신 사용량 보고서를 실행하므로 매월 첫 번째 금요일에 그렇게 합니다.

1. [!UICONTROL Customer Journey Analytics]에서 **[!UICONTROL 연결]** 탭을 클릭합니다.

   이제 모든 현재 연결 목록을 볼 수 있습니다.

1. 각 연결 이름을 클릭하여 연결 관리자로 이동합니다.

1. 생성된 모든 연결에 **[!UICONTROL 사용 가능한 이벤트 데이터 기록]**&#x200B;을 추가합니다. (연결 크기에 따라 숫자가 표시되는 데 다소 시간이 걸릴 수 있습니다.)

   ![이벤트 데이터](assets/event-data.png)

1. 모든 이벤트 데이터 행의 합계가 있으면 회사가 Adobe와 체결한 Customer Journey Analytics 계약에서 “데이터 행” 자격을 조회하십시오.

   이렇게 하면 판매 주문서에서 승인된 최대 데이터 행 수를 얻을 수 있습니다. 3단계로 인해 발생한 데이터 행 수가 이 숫자보다 크면 초과가 발생합니다.

1. 이 상황을 해결하려면 다음과 같은 몇 가지 옵션이 있습니다.

   * [데이터 보존 설정](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ko-KR#set-rolling-window-for-connection-data-retention)을 변경합니다.
   * [사용하지 않는 연결을 삭제합니다](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ko-KR#implications-of-deleting-data-components).
   * [AEP에서 데이터 세트를 삭제합니다](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ko-KR#implications-of-deleting-data-components).
   * 추가 용량 라이선스를 얻으려면 Adobe 계정 관리자에게 문의하십시오.
