---
title: B2B 조회를 위한 데이터 세트 변환
description: 특정 B2B 조회 스키마의 데이터 세트에서 데이터를 변환하는 방법을 설명합니다
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
source-git-commit: 6e50e9341c2eedd6e4882cc3eb943cbcb8dfc332
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 0%

---

# B2B 조회를 위한 데이터 세트 변환

B2B 데이터(계정, 기회, 마케팅 목록 및 캠페인 포함)에 대한 개인 기반 조회를 지원하려면 B2B 조회 데이터 세트의 변환이 필요합니다.

이 변환은 다음 클래스를 기반으로 B2B 조회 스키마에 대한 데이터가 있는 데이터 세트에만 사용할 수 있습니다.

* [XDM 비즈니스 계정 사용자 관계](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM 비즈니스 영업 기회 사용자 관계](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM 비즈니스 마케팅 목록 멤버](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM 비즈니스 캠페인 멤버](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

이러한 데이터 세트에 대한 변환을 활성화하려면 다음을 수행하십시오.

![변형 데이터 세트 활성화](assets/transform-dataset.gif)

* 다음에 대한 적절한 식별자를 선택하십시오. **[!UICONTROL 키]** 및 **[!UICONTROL 일치하는 키]**, 예 `personKey.sourceKey`.

* 새 데이터 및 데이터 세트 채우기를 가져오는 옵션을 선택합니다.

* 선택 **[!UICONTROL B2B 조회를 위한 데이터 세트 변환]**.

  이 옵션은 B2B 시나리오에서 사용자 기반 조회에 사용할 수 있도록 데이터 세트를 변환합니다.


  >[!IMPORTANT]
  >
  >일단 켜지고 연결이 저장되면 변환은 되돌릴 수 없습니다. 연결을 저장한 후에는 해당 연결을 한 번 더 제거하고 추가하는 것 이외의 다른 방법으로는 데이터 세트에 대한 변형 설정을 수정할 수 없습니다.

기존 연결에 이미 포함된 하나 이상의 데이터 세트에 대해 변환을 활성화하려면 다음을 수행합니다.

1. 연결에서 데이터 세트를 제거합니다.
1. 연결을 저장합니다.
1. 데이터 세트에 대한 변환을 켜면서 데이터 세트를 연결에 추가합니다.

## 배경 정보

위에서 언급한 4개의 스키마 클래스를 기반으로 하는 스키마의 경우 변형되지 않은 데이터 세트에는 단일 개인 식별자에 대한 여러 행이 포함될 수 있습니다. 개인 기반 조회는 해당 개인 식별자의 가장 최근 발생에만 일치하므로 계정, 기회, 마케팅 목록 또는 캠페인에 대한 적절한 개인 id 기반 조회를 방지할 수 있습니다.

변환은 각 개인 식별자에 대해 조회 데이터 세트(아래 그림에 있는 분홍색)의 관련 데이터(계정, 기회, 마케팅 목록 또는 캠페인)에 대한 (오브젝트) 배열이 생성되도록 4개의 스키마 클래스 각각의 데이터 세트를 수정합니다(아래 그림에 있는 주황색). 이 변환을 통해 개인 ID 기반 조회를 올바르게 수행할 수 있습니다.

![B2B 스키마](./assets/b2b-schemas.svg)
