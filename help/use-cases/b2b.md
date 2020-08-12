---
title: (B2B) 계정 수준 데이터를 조회 데이터 세트로 추가
description: 계정 기반 데이터를 조회 데이터 세트로 CJA에 추가하는 방법 살펴보기
translation-type: tm+mt
source-git-commit: e3d4a672c33b8c536246836a062d544e3d5b8a01
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---


# (B2B) 계정 수준 데이터를 조회 데이터 세트로 추가

이 B2B 사용 사례는 분석을 위한 개인 수준이 아닌 계정 수준에서 데이터를 지정하는 방법을 보여줍니다. 계정 수준 분석은

* 이 계정과 일치하는 회사 이름은 무엇입니까?
* 이 계정/회사와 연계되는 직원은 몇 명입니까?
* 이 계정에는 어떤 역할이 표시됩니까?
* 다른 계정과 비교하여 특정 마케팅 캠페인과 관련하여 이 계정이 전체적으로 어떻게 수행됩니까?
* 한 계정에서 특정 역할(예: IT 관리자)이 다른 계정에서 동일한 역할과 다르게 동작합니까?

계정 수준 정보를 [조회](/help/getting-started/cja-glossary.md) 데이터 세트(기존 Adobe Analytics의 분류와 유사).

먼저 Adobe Experience Platform에서 조회 스키마를 만든 다음 .csv 기반 계정 수준 데이터를 인제스트하여 조회 테이블 데이터 세트를 만듭니다. 그런 다음 생성한 검색과 같은 서로 다른 데이터 세트를 결합하는 연결 CJA를 만듭니다. 그런 다음 데이터 뷰를 만들고 Workspace에서 이 모든 데이터를 활용할 수 있습니다.

>[!NOTE]
>
>조회 테이블 크기는 최대 1GB입니다.

## 1. 조회 스키마 만들기(Experience Platform)

Creating your own schema for the [조회](/help/getting-started/cja-glossary.md) 표는 사용되는 데이터 세트를 올바른 설정(레코드 유형)으로 CJA에서 사용할 수 있도록 합니다. 모범 사례는 [사용자 정의 스키마 클래스 만들기](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) &quot;조회&quot;라고 하며 모든 조회 테이블에 다시 사용할 수 있는 요소가 비어 있습니다.

![](assets/create-new-class.png)

## 2. 조회 데이터 세트 만들기(Experience Platform)

스키마가 만들어지면 Experience Platform에서 해당 스키마에서 조회 데이터 세트를 만들어야 합니다. 이 조회 데이터 집합에는 다음과 같은 계정 수준 마케팅 정보가 포함됩니다.회사 이름, 총 직원 수, 도메인 이름, 해당 기업이 속한 업계, 연간 매출, 해당 고객이 Experience Platform의 현재 고객인지 여부, 현재 영업 단계, 계정 내에서 CJA를 사용하고 있는 팀 등

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 관리 > 데이터 집합]**.
1. 클릭 **[!UICONTROL + 데이터 세트 만들기]**.
1. 클릭 **[!UICONTROL 스키마에서 데이터 집합 만들기]**.
1. 생성한 스키마 조회 클래스를 선택합니다.
1. **[!UICONTROL 다음]**&#x200B;을 클릭합니다.
1. 데이터 세트 이름(예: B2B 정보)을 지정하고 설명을 제공합니다.
1. **[!UICONTROL 마침을 클릭합니다]**.

## 3. Experience Platform에 데이터 수집

방법 지침 [XDM 스키마에 CSV 파일 매핑](https://docs.adobe.com/content/help/en/experience-platform/ingestion/tutorials/map-a-csv-file.html) CSV 파일을 사용하는 경우 도움이 필요합니다.

[기타 방법](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) 이 제공되고 있습니다.

데이터를 온보딩하고 조회를 설정하는 데 조회 테이블의 크기에 따라 약 2~4시간이 소요됩니다.

## 4. 데이터 세트를 연결(Customer Journey Analytics)에 결합

이 예에서는 세 개의 데이터 세트를 하나의 CJA 연결로 결합합니다.

| 데이터 집합 이름 | 설명 | AEP 스키마 클래스 | 데이터 세트 세부 정보 |
|---|---|---|---|
| B2B 노출 | 계정 수준에서 클릭스트림, 이벤트 수준 데이터를 포함합니다. 예를 들어 마케팅 광고를 실행하기 위한 이메일 ID 및 해당 계정 ID와 마케팅 이름이 포함되어 있습니다. 또한 사용자당 해당 광고에 대한 노출 횟수도 포함됩니다. | XDM ExperienceEvent 스키마 클래스 기반 | The `emailID` 는 기본 ID로 사용되고 `Customer ID` namespace. 그 결과, 기본값이 **[!UICONTROL 개인 ID]** customer journey analytics에서 ![노출 횟수](assets/impressions-mixins.png) |
| B2B 프로필 | 이 프로필 데이터 집합은 자신의 직책, 해당 계정이 속한 계정, LinkedIn 프로필 등과 같은 계정의 사용자에 대해 자세히 알려줍니다. | XDM 개별 프로필 스키마 클래스 기반 | 선택할 필요 없음 `emailID` 을 이 스키마의 기본 ID로 추가했습니다. 활성화 **[!UICONTROL 프로필]**;그렇지 않으면 CJA에서 `emailID` 인 B2B Profile with the `emailID` (B2B 노출 횟수 데이터). 이 기능을 필드 기반 스티칭이라고 합니다. ![프로필](assets/profile-mixins.png) |
| B2B 정보 | 위의 &quot;조회 데이터 세트 만들기&quot;를 참조하십시오. | B2BAccount(사용자 정의 조회 스키마 클래스) | The relationship between `accountID` 및 B2B 노출 횟수 데이터 세트는 아래 단계에 설명된 대로 B2B 정보 데이터 세트와 CJA의 B2B 노출 횟수 데이터 세트를 연결하여 자동으로 생성됩니다. ![조회](assets/lookup-mixins.png) |

데이터 세트를 결합하는 방법은 다음과 같습니다.

1. Customer Journey Analytics에서 **[!UICONTROL 연결]** tab.
1. 결합할 데이터 세트(예: 위의 세 개)를 선택합니다.
1. B2B 정보 데이터 세트에 대해 `accountID` 키. 그런 다음 일치하는 키(해당 차원)를 선택합니다. `accountID` 이벤트 데이터세트에 있는
1. **[!UICONTROL 다음]**&#x200B;을 클릭합니다.
1. 연결 이름 및 설명 및 [이러한 지침](/help/connections/create-connection.md).
1. **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

## 5. 이 연결에서 데이터 보기를 만듭니다.

다음 지침을 따르십시오. [dataviews 생성](/help/data-views/create-dataview.md).

* 데이터 세트에서 필요한 모든 구성 요소(차원 및 지표)를 추가합니다.

## 6. Workspace에서 데이터 분석

이제 3개 데이터 세트의 데이터를 기반으로 Workspace 프로젝트를 만들 수 있습니다.

예를 들어 소개에 제시된 질문에 대한 답변을 찾을 수 있습니다.

* emailID를 accountID로 분류하여 이메일 ID가 속한 회사를 파악합니다.
* 몇 명의 직원이 특정 계정 ID에 매핑됩니까?
* 계정 ID는 어떤 업계에 속합니까?

![](assets/project-lookup.png)
