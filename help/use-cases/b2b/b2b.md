---
title: 계정 수준 데이터를 조회 데이터 세트로 추가
description: Customer Journey Analytics에 조회 데이터 세트로 계정 기반 데이터를 추가하는 방법 알아보기
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 74%

---

# 계정 수준 데이터를 조회 데이터 세트로 추가

이 B2B 사용 사례는 분석을 위한 개인 수준이 아닌 계정 수준에서 데이터를 지정하는 방법을 보여 줍니다. 계정 수준 분석은 다음과 같은 질문에 답변할 수 있습니다.

* 이 계정과 일치하는 회사 이름은 무엇입니까?
* 이 계정/회사와 연계되는 직원은 몇 명입니까?
* 이 계정에는 어떤 역할이 표시됩니까?
* 다른 계정과 비교하여 특정 마케팅 캠페인과 관련하여 이 계정이 전체적으로 어떻게 수행됩니까?
* 한 계정에서 특정 역할(예: IT 관리자)이 다른 계정에서 동일한 역할과 다르게 동작합니까?

계정 수준 정보를 [조회](/help/getting-started/cja-glossary.md) 데이터 세트로 가져와 이 모든 작업을 수행할 수 있습니다.

먼저 Adobe Experience Platform에서 조회 스키마를 만든 다음 .csv 기반 계정 수준 데이터를 수집하여 조회 테이블 데이터 세트를 만듭니다. 그런 다음 생성한 조회를 포함하여 서로 다른 데이터 세트를 결합하는 Customer Journey Analytics(Customer Journey Analytics)에서 연결을 만듭니다. 그런 다음 데이터 보기를 만들고 최종적으로 작업 영역에서 이 모든 데이터를 활용할 수 있습니다.

>[!NOTE]
>
>조회 테이블 크기는 최대 1GB입니다.

## 1. 조회 스키마 만들기 (Experience Platform)

에 대한 자체 스키마 만들기 [조회](/help/getting-started/cja-glossary.md) 표는 사용된 데이터 세트를 올바른 설정(레코드 유형)을 사용하여 Customer Journey Analytics에서 사용할 수 있도록 합니다. 모범 사례는 “조회”라고 하는 [사용자 정의 스키마 클래스 만들기](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ko-KR#create-new-class)이며 모든 조회 테이블에 다시 사용할 수 있는 요소가 비어 있습니다.

![새 클래스 만들기 대화 상자](../assets/create-new-class.png)

## 2. 조회 데이터 세트 만들기(Experience Platform)

스키마가 만들어지면 Experience Platform의 해당 스키마에서 조회 데이터 세트를 만들어야 합니다. 이 조회 데이터 세트에는 다음과 같은 계정 수준 마케팅 정보가 포함됩니다. 회사 이름, 총 직원 수, 도메인 이름, 해당 기업이 속한 업계, 연간 매출, 해당 Experience Platform의 현재 고객인지 여부, 현재 영업 단계, 계정 내에서 Customer Journey Analytics을 사용 중인 팀 등.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 관리 > 데이터 세트]**&#x200B;로 이동합니다.
1. **[!UICONTROL + 데이터 세트 만들기]**&#x200B;를 클릭합니다.
1. **[!UICONTROL 스키마에서 데이터 세트 만들기]**&#x200B;를 클릭합니다.
1. 생성한 스키마 조회 클래스를 선택합니다.
1. **[!UICONTROL 다음]**&#x200B;을 클릭합니다.
1. 데이터 세트 이름(예: B2B 정보)을 지정하고 설명을 제공합니다.
1. **[!UICONTROL 마침]**&#x200B;을 클릭합니다.

## 3. Experience Platform에 데이터 수집

[XDM 스키마에 CSV 파일 매핑](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html?lang=ko-KR) 방법에 대한 지침은 CSV 파일을 사용하는 경우 도움이 됩니다.

[기타 방법](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ko-KR)도 제공되고 있습니다.

데이터를 온보딩하고 조회를 설정하는 데 조회 테이블의 크기에 따라 약 2~4시간이 소요됩니다.

## 4. 데이터 세트를 연결(Customer Journey Analytics)에 결합

이 예에서는 3개의 데이터 세트를 하나의 Customer Journey Analytics 연결로 결합합니다.

| 데이터 세트 이름 | 설명 | Adobe Experience Platform 스키마 클래스 | 데이터 세트 세부 정보 |
| --- | --- | --- | --- |
| B2B 노출 | 계정 수준에서 클릭스트림, 이벤트 수준 데이터를 포함합니다. 예를 들어 마케팅 광고를 실행하기 위한 이메일 ID 및 해당 계정 ID와 마케팅 이름이 포함되어 있습니다. 또한 사용자당 해당 광고에 대한 노출 횟수도 포함됩니다. | XDM ExperienceEvent 스키마 클래스 기반 | `emailID`는 기본 ID로 사용되고 `Customer ID` 네임스페이스가 할당됩니다. 그 결과 Customer Journey Analytics에서 기본값 **[!UICONTROL 개인 ID]**&#x200B;로 표시됩니다. ![노출 횟수](../assets/impressions-mixins.png) |
| B2B 프로필 | 이 프로필 데이터 세트는 자신의 직책, 해당 계정이 속한 계정, LinkedIn 프로필 등과 같은 계정의 사용자에 대해 자세히 알려 줍니다. | XDM 개별 프로필 스키마 클래스 기반 | 선택 `emailID` 를 이 스키마의 기본 ID로 사용하십시오. |
| B2B 정보 | 위의 &quot;조회 데이터 세트 만들기&quot;를 참조하십시오. | B2BAccount (사용자 정의 조회 스키마 클래스) | 다음 사이의 관계 `accountID` 및 B2B 노출 데이터 세트는 아래 단계에 설명된 대로 Customer Journey Analytics의 B2B 노출 데이터 세트와 B2B 정보 데이터 세트를 연결하여 자동으로 생성됩니다. ![조회](../assets/lookup-mixins.png) |

데이터 세트를 결합하는 방법은 다음과 같습니다.

1. Customer Journey Analytics에서 **[!UICONTROL 연결]** 탭을 선택합니다.
1. 결합할 데이터 세트(예: 위의 세 개)를 선택합니다.
1. B2B 정보 데이터 세트에 대해 조회 테이블에서 사용될 `accountID` 키를 선택합니다. 그런 다음 일치 키(해당 차원)와 이벤트 데이터 세트에 있는 `accountID`도 선택합니다.
1. **[!UICONTROL 다음]**&#x200B;을 클릭합니다.
1. 연결의 이름을 지정하고 연결에 대해 설명하고 [이러한 지침](/help/connections/create-connection.md)에 따라 구성합니다.
1. **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

## 5. 이 연결에서 데이터 보기를 만듭니다.

[데이터 보기 생성](/help/data-views/create-dataview.md)에 대한 지침을 따르십시오.

* 데이터 세트에서 필요한 모든 구성 요소(차원 및 지표)를 추가합니다.

## 6. 작업 영역에서 데이터 분석

이제 3개 데이터 세트의 데이터를 기반으로 작업 영역 프로젝트를 만들 수 있습니다.

예를 들어 소개에 제시된 질문에 대한 답변을 찾을 수 있습니다.

* emailID를 accountID로 분류하여 이메일 ID가 속한 회사를 파악합니다.
* 몇 명의 직원이 특정 계정 ID에 매핑됩니까?
* 계정 ID는 어떤 업계에 속합니까?

![project-lookup2](assets/analyze.png)
