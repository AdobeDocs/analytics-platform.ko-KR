---
title: Customer Journey Analytics 연결 개요
description: Customer Journey Analytics에서 연결에 대해 알아보십시오.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: e4ddb98b800457e407bb414ed4929c5d5018cf30
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 10%

---

# 연결 개요

Customer Journey Analytics 제품 관리자는 연결을 통해 이벤트, 조회, 프로필 및 요약 데이터 세트와 같은 다양한 [!DNL Adobe Experience Platform] 데이터 소스와의 연결을 설정할 수 있습니다. 이러한 연결을 통해 연결의 데이터를 파생 데이터 보기에 통합할 수 있습니다. 연결은 Customer Journey Analytics의 기반이며 [!DNL Experience Platform] 소스 데이터 세트에서 만들어집니다.

>[!IMPORTANT]
>
>여러 [!DNL Experience Platform] 데이터 세트를 하나의 연결로 결합할 수 있습니다.


## 연결 워크플로

![연결 워크플로](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

상위 수준에서 연결 워크플로를 사용하여 다음을 수행할 수 있습니다.

| 인터페이스 | 설명 |
|:---:|---|
| ➊ | 연결 관리자에서 연결 및 Customer Journey Analytics의 전체 사용을 [관리합니다](manage-connections.md). |
| ➋ | [수집, 건너뛰기 또는 삭제된 데이터 세트 레코드와 같은 연결의 세부 정보를 검사합니다](manage-connections.md#connection-details). |
| ➌ | [롤링 데이터 창과 같은 연결의 구성을 만들거나 편집](create-connection.md#create-or-edit-a-connection) 및 연결에 포함된 데이터 세트를 선택합니다. |
| ➍ | [연결에 데이터 세트 추가](create-connection.md#add-datasets). 연결에는 하나 이상의 이벤트 또는 요약 데이터 세트가 있어야 하지만 다양한 이벤트, 프로필, 조회 및 요약 데이터 세트를 포함할 수 있습니다. |
| ➎ | 추가하는 데이터 세트에 대해 [설정을 구성](create-connection.md#dataset-settings)합니다. 따라서 일반 사용자 기반 또는 [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} 계정 기반 식별자를 기반으로 서로 다른 데이터 세트를 연결하는 방법을 결정할 수 있습니다. |
| ➏ | [기존 데이터 집합에 대한 설정을 편집합니다](create-connection.md#edit-a-dataset). 나중에 언제든지 데이터 세트 설정을 다시 방문할 수 있습니다. |



## 액세스 제어

연결 관리에 대한 액세스는 핵심 관리 그룹으로 제한해야 합니다. 연결 구성에는 Customer Journey Analytics으로 가져온 데이터에 대한 볼륨 할당과 관련된 계약상의 의미가 있습니다.

>[!MORELIKETHIS]
>
>[액세스 제어](/help/technotes/access-control.md).

