---
title: B2B 조회를 위한 데이터 세트 변환
description: 특정 B2B 조회 스키마의 데이터 세트에서 데이터를 변환하는 방법을 설명합니다
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 2%

---

# B2B 조회를 위한 데이터 세트 변환

B2B 데이터(계정, 기회, 마케팅 목록 및 캠페인 포함)에 대한 사용자 기반 조회를 지원하기 위해 B2B 조회 데이터 세트를 변환하면 데이터 정확도를 향상시킬 수 있습니다.

이 변환은 다음 클래스를 기반으로 B2B 조회 스키마에 대한 데이터가 있는 데이터 세트에만 사용할 수 있습니다.

* [XDM 비즈니스 계정 사용자 관계](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM 비즈니스 영업 기회 사용자 관계](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM 비즈니스 마케팅 목록 구성원](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM 비즈니스 캠페인 멤버](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>각 ID에는 최대 10,000개의 항목으로 제한됩니다. 이 제한은 주어진 개인 ID에 대해 계정 10,000개, 기회 10,000개, 마케팅 목록 10,000개 또는 캠페인 10,000개만 가질 수 있음을 의미합니다.

>[!PREREQUISITES]
>
>수집이 제대로 작동하려면 B2B 조회 데이터 세트에 B2B 조회 스키마에 정의된 대로 다음 필드에 대해 채워진 데이터가 있는지 확인해야 합니다.
>
>| 스키마를 따르는 데이터가 포함된 데이터 세트 | 데이터로 채워진 필드 |
>|---|---|
>| XDM 비즈니스 계정 사용자 관계 | `accountPersonID` |
>| XDM 비즈니스 영업 기회 사용자 | `opportunityPersonID` |
>| XDM 비즈니스 마케팅 목록 | `marketingListMemberID` |
>| XDM 비즈니스 캠페인 멤버 | `campaign.sourceKey` |
>

B2B 조회 데이터 세트에 대한 변환을 활성화하려면 다음을 수행합니다.

![변환 데이터 세트 사용](/help/connections/assets/transform.gif)

* 각 데이터 세트에 대해 **[!UICONTROL Key]** 및 **[!UICONTROL 일치하는 키]**&#x200B;에 대해 제안된 값을 확인하십시오. 제안 값에서 값을 변경하면 계속 진행하라는 경고가 표시됩니다. 다음을 확인해야 합니다.

   * **키**&#x200B;에 대해 선택한 값은 개인 ID 데이터 형식을 기반으로 합니다.
   * **일치하는 키**&#x200B;에 대해 선택한 값이 이벤트 데이터 세트에 대한 기본 ID 필드로 정의됩니다.

* 새 데이터 및 데이터 세트 채우기를 가져오는 옵션을 선택합니다.

* **[!UICONTROL B2B 조회에 대한 데이터 집합 변형]**&#x200B;을 선택하십시오.

  이 옵션은 B2B 시나리오에서 사용자 기반 조회에 사용할 수 있도록 데이터 세트를 변환합니다.


  >[!IMPORTANT]
  >
  >일단 켜지고 연결이 저장되면 변환은 되돌릴 수 없습니다. 키, 일치하는 키 및 변형 데이터 세트 구성은 수정할 수 없습니다. 데이터 세트를 제거, 추가 및 재구성할 수만 있습니다.

기존 연결에 이미 포함된 하나 이상의 데이터 세트에 대해 변환을 활성화하려면 다음을 수행합니다.

1. 연결에서 데이터 세트를 제거합니다.
1. 연결을 저장합니다.
1. 데이터 세트에 대한 변환을 켜면서 데이터 세트를 연결에 추가합니다.

## 배경 정보

위에서 언급한 4개의 스키마 클래스를 기반으로 하는 스키마의 경우 변형되지 않은 데이터 세트에는 단일 개인 식별자에 대한 여러 행이 포함될 수 있습니다. 개인 기반 조회는 해당 개인 식별자의 가장 최근 발생에만 일치하므로 계정, 기회, 마케팅 목록 또는 캠페인에 대한 적절한 개인 id 기반 조회를 방지할 수 있습니다.

변환은 각 개인 식별자에 대해 조회 데이터 세트(아래 그림에 있는 분홍색)의 관련 데이터(계정, 기회, 마케팅 목록 또는 캠페인)에 대한 (오브젝트) 배열이 생성되도록 4개의 스키마 클래스 각각의 데이터 세트를 수정합니다(아래 그림에 있는 주황색). 이 변환을 통해 개인 ID 기반 조회를 올바르게 수행할 수 있습니다.

![B2B 스키마](./assets/b2b-schemas.svg)
