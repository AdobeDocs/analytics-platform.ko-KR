---
title: Customer Journey Analytics 사용 관리
description: Customer Journey Analytics 사용을 관리하는 방법을 설명합니다.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 5311106f486a30dbc7f06b3ef60dc7e666d2fe03
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 42%

---

# Customer Journey Analytics 사용 관리

>[!TIP]
>
>Customer Journey Analytics의 모든 연결에서 수집 및 보고 가능한 행의 사용을 **보기**&#x200B;하려면 [**[!UICONTROL 사용&#x200B;]**인터페이스](/help/connections/manage-connections.md#usage)를 사용하십시오.



[**[!UICONTROL 연결&#x200B;]**인터페이스](/help/connections/create-connection.md)에서 Customer Journey Analytics 사용을 관리할 수 있습니다. 이 인터페이스에서 Customer Journey Analytics 데이터 보존을 연결 수준에서 개월(1개월, 3개월, 6개월 등) 단위의 롤링 기간으로 정의할 수 있습니다.

주요 이점은 적용 가능하고 유용한 데이터에 대해서만 저장하거나 보고하고 더 이상 유용하지 않은 오래된 데이터를 삭제한다는 것입니다. 계약 한도를 유지하고 초과 비용의 위험을 줄이는 데 도움이 됩니다.

기본값(선택 해제)을 그대로 두면 보존 기간이 Adobe Experience Platform 데이터 보존 설정으로 대체됩니다. Experience Platform에 25개월 분량의 데이터가 있는 경우 Customer Journey Analytics은 채우기를 통해 25개월 분량의 데이터를 가져옵니다. Platform에서 이러한 개월 중 10개월을 삭제하면 Customer Journey Analytics는 나머지 15개월을 유지합니다.

데이터 보존은 이벤트 데이터 세트 타임스탬프를 기반으로 하며 이벤트 데이터 세트에만 적용됩니다. 적용 가능한 타임스탬프가 없기 때문에 프로필 또는 조회 데이터 세트에 대한 롤링 데이터 기간 설정이 없습니다. 연결에 프로필 또는 조회 데이터 세트가 포함된 경우 이벤트 데이터 세트와 연결되므로 데이터는 이벤트 데이터 세트 타임스탬프의 데이터 보존 설정에 따라 Customer Journey Analytics에 유지됩니다.


>[!MORELIKETHIS]
>
>[Customer Journey Analytics 사용 보기](/help/connections/manage-connections.md#usage)

