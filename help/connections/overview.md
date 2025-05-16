---
title: Customer Journey Analytics 연결 개요
description: Customer Journey Analytics에서 연결에 대해 알아보십시오.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 836c793ae74185728af03636b0ba3e838f46f05d
workflow-type: ht
source-wordcount: '257'
ht-degree: 100%

---

# 연결 개요

연결을 통해 Customer Journey Analytics 제품 관리자는 이벤트, 조회, 프로필 및 요약 데이터 세트 등 다양한 [!DNL  Experience Platform] 데이터 소스 간의 연결을 설정할 수 있습니다. 이러한 연결로 데이터를 연결에서 파생 데이터 보기로 통합할 수 있습니다. 연결은 Customer Journey Analytics의 기반이며 [!DNL Experience Platform] 소스 데이터 세트에서 만들어집니다.

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

높은 수준에서 연결 워크플로를 사용하면 다음과 같은 작업을 수행할 수 있습니다.

| 인터페이스 | 설명 |
|:---:|---|
| ➊ | 연결 관리자에서 Customer Journey Analytics의 [전반적인 사용과 연결을 관리합니다](manage-connections.md). |
| ➋ | 수집, 건너뛰기 또는 삭제된 데이터 세트 레코드와 같은 [연결의 세부 사항을 검사합니다](manage-connections.md#connection-details). |
| ➌ | 롤링 데이터 창, 사용할 샌드박스, 연결에 포함된 데이터 세트 등과 같은 [연결 구성을 만들거나 편집합니다](create-connection.md#create-or-edit-a-connection). |
| ➍ | [연결에 데이터 추가](create-connection.md#add-datasets). 연결에는 최소한 하나의 이벤트 또는 요약 데이터 세트가 있어야 하지만 다양한 이벤트, 프로필, 조회 및 요약 데이터 세트를 포함할 수 있습니다. |
| ➎ | 추가할 데이터 세트의 [설정을 구성합니다.](create-connection.md#dataset-settings) 공통된 개인 기반 또는 [!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"} 계정 기반 식별자에 따라 다양한 데이터 세트를 연결하는 방법을 결정할 수 있습니다. |
| ➏ | [기존 데이터 세트의 설정 편집](create-connection.md#edit-a-dataset). 데이터 세트 설정은 나중에 언제든지 다시 확인할 수 있습니다. |



## 액세스 제어

연결 관리에 대한 액세스는 핵심 관리 그룹으로 제한되어야 합니다. 연결 구성에는 Customer Journey Analytics로 가져온 데이터의 볼륨 할당과 관련하여 계약상 의미가 포함됩니다.

>[!MORELIKETHIS]
>
>[액세스 제어](/help/technotes/access-control.md).

