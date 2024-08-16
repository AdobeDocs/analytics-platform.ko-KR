---
title: B2B 프로젝트 예시
description: B2B 데이터를 설정, 구성 및 보고하는 방법을 알아봅니다
solution: Customer Journey Analytics
feature: Use Cases
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 3f83b4c141324a7b255ac5af039fa1d7607f3b15
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 7%

---

# B2B 프로젝트 예시

이 문서에서는 Customer Journey Analytics의 B2B 데이터를 기반으로 프로필(개인) 수준을 설정, 구성 및 보고하는 방법을 설명합니다.

## 연결

Experience Platform의 모든 관련 B2B 데이터 세트를 포함하도록 연결을 정의합니다. 연결에 추가할 수 있는 데이터 세트:

| 데이터 세트 | 스키마 | 스키마 유형 | 기본 클래스 | 설명 |
|---|---|---|---|---|
| B2B 활동 데이터 세트 | B2B 활동 스키마 | 이벤트 | XDM ExperienceEvent | ExperienceEvent는 시점 및 관련된 개인의 ID를 포함하여 발생한 일에 대한 팩트 레코드입니다. ExperienceEvents는 명시적(직접 관찰 가능한 인간 동작) 또는 암시적(직접 인간 동작 없이 발생)일 수 있으며 집계나 해석 없이 기록됩니다. 경험 이벤트는 주어진 시간 내에 발생하는 변경 사항을 관찰 및 분석하고, 트렌드를 추적하기 위해 여러 시간 창을 비교할 수 있으므로 시간 도메인 분석에 중요합니다. |
| B2B 개인 데이터 세트 | B2B 개인 스키마 | 프로필 | XDM 개별 프로필 | XDM 개인 프로필은 식별된 개인과 부분적으로 식별된 개인 모두의 속성 및 관심사의 단일 표현을 형성한다. 식별이 불가능한 프로필에는 브라우저 쿠키와 같은 익명 동작 신호만 포함될 수 있으며 식별이 잘되는 프로필에는 이름, 생년월일, 위치 및 이메일 주소와 같은 자세한 개인 정보가 포함될 수 있습니다. 프로필이 성장하면 개인의 개인 정보, 식별 정보, 연락처 세부 정보 및 커뮤니케이션 환경 설정을 저장하는 강력한 저장소가 됩니다. |
| B2B 계정 데이터 세트 | B2B 계정 스키마 | 조회 | XDM 비즈니스 계정 | XDM 비즈니스 계정은 비즈니스 계정의 최소 필요 속성을 캡처하는 표준 경험 데이터 모델(XDM) 클래스입니다. 이 XDM 클래스는 B2B 또는 B2P 에디션을 보유한 고객의 프로필에만 포함될 수 있습니다. |
| B2B 영업 기회 데이터 세트 | B2B 영업 기회 스키마 | 조회 | XDM 비즈니스 영업 기회 | XDM 비즈니스 영업 기회는 비즈니스 영업 기회의 최소 필요 속성을 캡처하는 표준 경험 데이터 모델(XDM) 클래스입니다. 이 XDM 클래스는 B2B 또는 B2P 에디션을 보유한 고객의 프로필에만 포함될 수 있습니다. |
| B2B 캠페인 데이터 세트 | B2B 캠페인 스키마 | 조회 | XDM 비즈니스 캠페인 | XDM 비즈니스 캠페인은 비즈니스 캠페인의 최소 필요 속성을 캡처하는 표준 경험 데이터 모델(XDM) 클래스입니다. 이 XDM 클래스는 B2B 또는 B2P 에디션을 보유한 고객의 프로필에만 포함될 수 있습니다. |
| B2B 마케팅 목록 데이터 세트 | B2B 마케팅 목록 스키마 | 조회 | XDM 비즈니스 마케팅 목록 | XDM 비즈니스 마케팅 목록은 마케팅 목록의 최소 필요 속성을 캡처하는 표준 경험 데이터 모델(XDM) 클래스입니다. 마케팅 목록을 사용하면 제품을 구매할 가능성이 가장 높은 잠재 고객을 우선 지정할 수 있습니다. 이 XDM 클래스는 B2B 또는 B2P 에디션을 보유한 고객의 프로필에만 포함될 수 있습니다. |
| B2B 계정 사용자 관계 데이터 세트 | B2B 계정 사용자 관계 스키마 | 조회 | XDM 비즈니스 계정 사용자 관계 | XDM 비즈니스 계정 사용자 관계는 비즈니스 계정과 연결된 사용자의 최소 필요 속성을 캡처하는 표준 경험 데이터 모델(XDM) 클래스입니다. |
| B2B 영업 기회 사용자 관계 데이터 세트 | B2B 영업 기회 사용자 관계 스키마 | 조회 | XDM 비즈니스 영업 기회 사용자 관계 | XDM 비즈니스 영업 기회 사용자 관계는 비즈니스 영업 기회와 연계된 사용자의 최소 필요 속성을 캡처하는 표준 경험 데이터 모델(XDM) 클래스입니다. |
| B2B 마케팅 목록 구성원 데이터 세트 | B2B 마케팅 목록 구성원 스키마 | 조회 | XDM 마케팅 목록 멤버 | XDM 비즈니스 마케팅 목록 멤버는 마케팅 목록과 연계된 멤버, 사용자 또는 연락처를 설명하는 표준 경험 데이터 모델(XDM) 클래스입니다. |
| B2B 캠페인 멤버 데이터 세트 | B2B 캠페인 멤버 스키마 | 조회 | XDM 비즈니스 캠페인 멤버 | XDM 비즈니스 캠페인 멤버는 비즈니스 캠페인과 연결된 연락처 또는 잠재 고객을 설명하는 표준 경험 데이터 모델(XDM) 클래스입니다. |

<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


B2B 조회 스키마, 프로필 스키마 및 이벤트 스키마 간의 관계는 Experience Platform 내의 B2B 설정에서 정의됩니다. [Real-time Customer Data Platform B2B 에디션의 스키마](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b) 및 [Real-time Customer Data Platform B2B 에디션의 두 스키마 간의 다대일 관계 정의](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/relationship-b2b)를 참조하십시오.


B2B 데이터의 개인 기반 조회를 지원하는 연결을 적절하게 설정하려면 개요를 보려면 다음 그림을 사용하고 다음 단계를 수행하십시오.

![B2B 스키마에 주석이 추가됨](assets/b2b-schemas-annotated.svg)

1. 위 표의 데이터 세트를 연결에 추가합니다.
1. 연결에 추가하는 각 조회 데이터 세트에 대해 **[!UICONTROL 데이터 세트 편집]** 대화 상자에서 **[!UICONTROL 키]** 및 **[!UICONTROL 일치하는 키]**&#x200B;을(를) 사용하여 이벤트 데이터 세트에 대한 관계를 명시적으로 정의해야 합니다.
1. 개인 기반 B2B 조회에 대해 변환할 각 조회 데이터 세트에 대해 **[!UICONTROL 데이터 세트 변환]**&#x200B;을 활성화하여 개인 기반 조회에 대해 데이터가 변환되도록 합니다. 자세한 내용은 [B2B 조회를 위한 데이터 세트 변환](/help/connections/transform-datasets-b2b-lookups.md)을 참조하십시오.

   ![키 - 일치하는 키](assets/key-matchingkey.png)

   아래 표는 각 데이터 세트에 대한 [!UICONTROL 개인 ID], [!UICONTROL 키] 및 [!UICONTROL 일치하는 키] 값의 예제 개요를 제공합니다.

   | 데이터 세트 | 개인 ID | 키 | 일치하는 키 <br/>(이벤트 데이터 세트) |
   |---|---|---|---| 
   | B2B 활동 데이터 세트 | SourceKey <br/>**personKey.sourceKey** | | |
   | B2B 개인 데이터 세트 | SourceKey <br/>**b2b.personKey.sourceKey** | | |
   | B2B 계정 데이터 세트 | | SourceKey <br/>**accountKey.sourceKey**❶ | SourceKey<br>(B2B 개인 데이터 세트)<br/>**b2b.accountKey.sourceKey**❶ |
   | B2B 영업 기회 데이터 세트 | | Source 키&#x200B;<br/>**opportunityKey.sourceKey**❷ | SourceKey<br/>(B2B 영업 기회 관계 데이터 세트)<br/>**opportunityKey.sourceKey**❷ |
   | B2B 캠페인 데이터 세트 | | SourceKey <br/>**campaignKey.sourceKey**❸ | SourceKey<br/>(B2B 캠페인 멤버 데이터 세트)<br/>c **campaignKey.sourceKey**❸<br/> |
   | B2B 마케팅 목록 데이터 세트 | | SourceKey <br/>**marketingListKey.sourceKey**❹ | SourceKey<br/>(B2B 마케팅 목록 구성원 데이터 세트)<br/>**marketingListKey.sourceKey**❹ |
   | B2B 계정 사용자 관계 데이터 세트 | | SourceKey <br/>**personKey.sourceKey**❺ | Source 키<br/>(이벤트 데이터 세트)<br/>**personKey.sourceKey**❺ |
   | B2B 영업 기회 사용자 관계 데이터 세트 | | SourceKey <br/>**personKey.sourceKe** y❻ | Source 키<br/>(이벤트 데이터 세트)<br/>**personKey.sourceKey**❻ |
   | B2B 캠페인 멤버 데이터 세트 | | SourceKey <br/>**personKey.sourceKey**❼ | Source 키<br/>(이벤트 데이터 세트)<br/>**personKey.sourceKey**❼ |
   | B2B 마케팅 목록 구성원 데이터 세트 | | SourceKey <br/>**personKey.sourceKey**❽ | Source 키<br/>(이벤트 데이터 세트)<br/>**personKey.sourceKey**❽ |

{style="table-layout:auto"}

데이터 집합에 대한 설정을 구성하는 방법에 대한 자세한 내용은 [데이터 집합 추가 및 구성](../../connections/create-connection.md)을 참조하십시오.


## 데이터 보기

Workspace 프로젝트를 작성할 때 관련 B2B 차원 및 지표에 액세스하려면 그에 따라 데이터 보기를 정의해야 합니다.

예를 들어 데이터 보기에 다음 구성 요소를 추가하여 B2B 데이터를 기반으로 개인 기반 수준에 대해 보고할 수 있습니다. 구성 요소 이름은 원래 스키마 이름과 명확하게 일치하도록 수정되는 경우가 있습니다.

+++지표

| 구성 요소 이름 | 데이터 세트 | 데이터 유형 | 스키마 경로 |
|---|---|---|---|
| 연간 계정 수익 | B2B 계정 데이터 세트 | 이중 | accountOrganization.annualRevenue.amount |
| 직원 수 | B2B 계정 데이터 세트 | 정수 | accountOrganization.numberOfEmployees |
| 실제 캠페인 비용 | B2B 캠페인 데이터 세트 | 이중 | actualCost.amount |
| 예산 캠페인 비용 | B2B 캠페인 데이터 세트 | 이중 | budgetedCost.amount |
| 예상 영업 기회 수익 | B2B 영업 기회 데이터 세트 | 이중 | expectedRevenue.amount |
| 예상 캠페인 수익 | B2B 캠페인 데이터 세트 | 이중 | expectedRevenue.amount |
| 영업 기회 금액 | B2B 영업 기회 데이터 세트 | 이중 | opportunityAmount.amount |

+++

+++Dimension

| 구성 요소 이름 | 데이터 세트 | 데이터 유형 | 스키마 경로 |
|---|---|---|---|
| 계정 이름 | B2B 계정 데이터 세트 | 문자열 | accountName |
| 캠페인 이름 | B2B 캠페인 데이터 세트 | 문자열 | campaignName |
| 채널 이름 | B2B 캠페인 데이터 세트 | 문자열 | channelName |
| 국가 | B2B 계정 데이터 세트 | 문자열 | accountBillingAddress.country |
| 예측 범주 이름 | B2B 영업 기회 데이터 세트 | 문자열 | forecastCategoryName |
| 업종 | B2B 계정 데이터 세트 | 문자열 | accountOrganization.industry |
| 성 | B2B 개인 데이터 세트 | 문자열 | person.name.lastName |
| 마케팅 목록 이름 | B2B 마케팅 목록 데이터 세트 | 문자열 | marketingListName |
| 영업 기회 이름 | B2B 영업 기회 데이터 세트 | 문자열 | opportunityName |
| 영업 기회 단계 | B2B 영업 기회 데이터 세트 | 문자열 | opportunityStage |
| 영업 기회 유형 | B2B 영업 기회 유형 데이터 세트 | 문자열 | opportunityType |
| 웨비나 세션 이름 | B2B 캠페인 데이터 세트 | 문자열 | 웨비나 세션 이름 |

+++

## 작업 영역

데이터 보기에서 구성 요소를 제대로 정의하면 이제 Workspace 프로젝트에서 특정 B2B 보고서와 시각화를 작성할 수 있습니다.

다음은 위에서 설명한 연결 및 데이터 보기에 의존하는 예제 프로젝트의 스크린샷입니다. 시각화 설명은 자유 형식 테이블 시각화 중 변환된 B2B 조회 데이터에 의존하는 것을 설명합니다.

![샘플 프로젝트](assets/sample-workspace-project.png)

