---
title: B2B 프로젝트 예시
description: B2B 데이터를 설정, 구성 및 보고하는 방법을 알아봅니다
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: c3d97fe2353011f4747d0c1742e49189cc91b85c
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 10%

---

# B2B 프로젝트 예시

이 문서에서는 Customer Journey Analytics의 B2B 데이터를 기반으로 프로필(개인) 수준을 설정, 구성 및 보고하는 방법을 설명합니다.

## 연결

Experience Platform의 모든 관련 B2B 데이터 세트를 포함하도록 연결을 정의합니다. 일반적인 B2B 개인 기반 보고 시나리오에 필요한 모든 관련 조회 데이터 세트를 포함하고 변환해야 합니다. 자세한 내용은 [B2B 조회 데이터 세트 변환](/help/connections/transform-datasets-b2b-lookups.md)을 참조하십시오.

연결에 추가할 수 있는 데이터 세트:

| 데이터 세트 | 스키마 | 스키마 유형 | 기본 클래스 | 설명 |
|---|---|---|---|---|
| B2B 활동 데이터 세트 | B2B 활동 스키마 | 이벤트 | XDM ExperienceEvent | ExperienceEvent는 시점 및 관련된 개인의 ID를 포함하여 발생한 일에 대한 팩트 레코드입니다. ExperienceEvents는 명시적(직접 관찰 가능한 인간 동작) 또는 암시적(직접 인간 동작 없이 발생)일 수 있으며 집계나 해석 없이 기록됩니다. 지정된 시간 내에 발생하는 변경 사항을 관찰 및 분석하고, 트렌드를 추적하기 위해 여러 시간 창을 비교할 수 있으므로 시간 도메인 분석에 중요합니다. |
| B2B 개인 데이터 세트 | B2B 개인 스키마 | 프로필 | XDM 개별 프로필 | XDM 개인 프로필은 식별된 개인과 부분적으로 식별된 개인 모두의 속성 및 관심사의 단일 표현을 형성한다. 식별이 불가능한 프로필에는 브라우저 쿠키와 같은 익명 동작 신호만 포함될 수 있으며 식별이 잘되는 프로필에는 이름, 생년월일, 위치 및 이메일 주소와 같은 자세한 개인 정보가 포함될 수 있습니다. 프로필이 성장하면 개인의 개인 정보, 식별 정보, 연락처 세부 정보 및 커뮤니케이션 환경 설정을 저장하는 강력한 저장소가 됩니다. |
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


조회 스키마, 프로필 스키마 및 이벤트 스키마 간의 관계는 Experience Platform 내의 B2B 설정에서 정의됩니다. 자세한 내용은 [Real-time Customer Data Platform B2B 에디션](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html)의 스키마 및 [Real-time Customer Data Platform B2B 에디션의 두 스키마 간의 다대일 관계 정의](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html)를 참조하십시오.

![B2B 스키마 간의 관계](assets/classes.png)

연결에 추가하는 각 조회 데이터 세트에 대해 **[!UICONTROL 데이터 세트 편집]** 대화 상자에서 **[!UICONTROL 키]** 및 **[!UICONTROL 일치하는 키]**&#x200B;을(를) 사용하여 이벤트 데이터 세트에 대한 관계를 명시적으로 정의해야 합니다. 예:

![키 - 일치하는 키](assets/key-matchingkey.png)

개인 스키마를 다른 관련 스키마에 연결하는 데 명시적으로 사용되는 4가지 스키마(계정, 영업 기회, 캠페인 및 마케팅 목록)가 있습니다. 이러한 스키마는 다음 스키마 클래스를 기반으로 합니다.

* XDM 비즈니스 계정 사용자 관계
* XDM 비즈니스 영업 기회 사용자 관계
* XDM 비즈니스 마케팅 목록 멤버
* XDM 비즈니스 캠페인 멤버

각 조회 데이터 세트에 대해 이러한 스키마 클래스를 기반으로 하는 스키마에 대해 **[!UICONTROL 데이터 세트 변환]**&#x200B;을 활성화하여 개인 기반 조회에 대한 데이터가 변환되도록 할 수도 있습니다. 자세한 내용은 [B2B 조회를 위해 데이터 세트 변환](/help/connections/transform-datasets-b2b-lookups.md)을 참조하십시오.

아래 표는 각 데이터 세트에 대한 [!UICONTROL 개인 ID], [!UICONTROL 키] 및 [!UICONTROL 일치하는 키] 값의 예제 개요를 제공합니다.


| 데이터 세트 | 개인 ID | 키 | 일치하는 키(이벤트 데이터 세트 내) |
|---|---|---|---|
| B2B 활동 데이터 세트 | `personKey.sourceKey` | | |
| B2B 개인 데이터 세트 | `b2b.personKey.sourceKey` | | |
| B2B 계정 사용자 데이터 세트 | | `personKey.sourceKey` | `personKey.sourceKey` |
| B2B 영업 기회 데이터 세트 | | `personKey.sourceKey` | `personKey.sourceKey` |
| B2B 캠페인 멤버 데이터 세트 | | `personKey.sourceKey` | `personKey.sourceKey` |
| B2B 마케팅 목록 데이터 세트 | | `personKey.sourceKey` | `personKey.sourceKey` |

{style="table-layout:auto"}

데이터 집합에 대한 설정을 구성하는 방법에 대한 자세한 내용은 [데이터 집합 추가 및 구성](../../connections/create-connection.md)을 참조하십시오.


## 데이터 보기

Workspace 프로젝트를 작성할 때 관련 B2B 차원 및 지표에 액세스하려면 데이터 보기를 적절하게 정의해야 합니다.

다음 구성 요소를 데이터 보기에 차원으로 추가하여 B2B 데이터를 기반으로 개인 기반 수준을 보고할 수 있습니다. 구성 요소 이름을 명확하게 하기 위해 수정되었습니다.

| 구성 요소 이름 | 데이터 세트 | 스키마 데이터 유형 | 스키마 경로 |
|---|---|---|---|
| 사람 | B2B 활동 | 문자열 | `personID` |
| 계정 | B2B 계정 사용자 | 문자열 | `accountKey.sourceID` |
| 캠페인 | B2B 캠페인 멤버 | 문자열 | `campaignKey.sourceKey` |
| 마케팅 목록 이름 | B2B 마케팅 목록 | 문자열 | `marketingListID` |
| 영업 기회 | B2B 영업 기회 담당자 | 문자열 | `opportunityKey.sourceID` |


<!--
This section provides recommendations and suggestions on what dimensions and metrics to include when defining the [components](../../data-views/create-dataview.md#components) for B2B datasets in your data view.

For each component, the name, schema type, schema path, and (when applicable) details about the configuration are provided.


+++ B2B Activity dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Add To Campaign | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.addToCampaign` |
| Add To Opportunity | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.addToOpportunity` |
| Application Closed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.close` |
| Application Launch | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.launch` |
| Campaign Stream | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** ` leadOperation.changeCampaignStream` |
| Checkout | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.checkouts` |
| Convert Lead | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.convertLead` |
| Email Clicked | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailClicked` |
| Email Delivered | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailDelivered` |
| Email Opened | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailOpened` |
| Email Sent | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailSent` |
| Email Unsubscribed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailUnsubscribed` |
| Form Filled Out | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `web.formFilledOut` |
| Form Started | String | `web.fillOutForm.webFormName` | |
| Leads | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.newLead` |
| Opportunity Updated | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.opportunityUpdated` |
| Price | Double | *_organizationID*`.interactions.products.price` |  |
| Priority | Integer | `leadOperation.changeScore.priority` |  |
| Prod List Add | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListAdds.value` |
| Prod List Open | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListOpens.value` |
| Prod View | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |
| Purchases | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.purchases.value` |
| Remove From Opportunity | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.removeFromOpportunity` |
| Save for Laters | String | eventType |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Account Key (Source Key) | String | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| Converted Status | String | `leadOperation.convertLead.convertedStatus` | |
| Event Type | String | `eventType` | |
| Form Name | String | `leadOperation.newLead.formName` | |
| Identifier | String | `_id` | |
| Is Sent Notification | Boolean | `leadOperation.convertLead.isSentNotificationEmail` | |
| Keywords | String | `search.keywords` | |
| List ID | String | `listOperations.listID` | |
| List Name | String | `leadOperation.newLead.listName` | |
| Page Name | String | `web.webPageDetails.name` | |
| Person Key (Source Key) | String | `personKey.sourceKey` | |
| Produced By | String | producedBy | |
| Product Name | String | *_organizationID*`.Interactions.products.name` | |
| Role | String | `opportunityEvent.role` | | 
| Timestamp | Date-time | `timestamp` | Date-Time format: **[!UICONTROL Day]** |
| URL | String | `web.webPageDetails.URL` | |
| Web Form Name | String | `web.fillOutForm.webFormName` | |
| Product URL | String | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ B2B Person dataset


### Metrics

No metric components are defined as part of this dataset.


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Last Activity Date | Date-time | `extSourceSystemAudit.lastActivityDate` | Date-Time format: **[!UICONTROL Day]** |
| Person ID | String | `personID` | |

{style="table-layout:auto"}

+++

+++ B2B Account Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Annual Revenue | Double | `accountOrganization.annualRevenue.amount` | |
| Number of employees | Integer | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Acount | String | `accountKey.sourceID` | 

{style="table-layout:auto"}

| Account Identifier | String | `accountID` | |
| Account Type | String | `accountType` | |
| City | String | `accountBillingAddress.city` | |
| Country | String | `accountBillingAddress.country` | |
| Industry | String | `accountOrganization.industry` | |
| Region | String | `accountBillingAddress.region` | |
| Source ID | String | `accountKey.sourceID` | |
| Source Instance ID | String | `accountKey.sourceInstanceID` | |
| Source Key | String | `accountKey.sourceKey` | |
| Source Type | String | `accountKey.sourceType` | |


+++

+++  B2B Opportunity Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Expected Revenue | Double | `expectedRevenue.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Amount | Double | `opportunityAmount.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Stage - Closed Book | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Closed - Booked` |
| Opportunity Stage - Prospect | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Prospect` |
| Opportunity Stage - Qualification | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Opportunity Qualification` |
| Opportunity Stage - Solution Definition | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Closed Flag | Boolean | `isClosed` | |
| Company ID | String | `opportunityID` | |
| Forecast Category | String | `forecastCategoryName` | |
| Last Activity Date | Date-time | `lastActivityDate` | Date-time format: **[!UICONTROL Day]** |
| Lead Source | String | `leadSource` | |
| Opportunity Name | String | `opportunityName` | | 
| Opportunity Status | String | `opportunityStage` | |
| Won Flag | Boolean | `isWon` | |

{style="table-layout:auto"}

+++


+++ B2B Campaign Member dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Bounced | Long | *_organizationID*`.campaignBounced` | Behavior: **[!UICONTROL Count values]** |
| Clicked | Long | *_organizationID*`.campaignClicked` | Behavior: **[!UICONTROL Count values]** |
| Opened | Long | *_organizationID*`.CampaignOpened` | Behavior: **[!UICONTROL Count values]** |
| Sent | Long | *_organizationID*`.campaignSent` | Behavior: **[!UICONTROL Count values]** |
| Subscribed | Long | *_organizationID*`.campaignSubscribed` | Behavior: **[!UICONTROL Count values]** |
| Webinar Registrations | Long | *_organizationID*`.Registrations` | Behavior: **[!UICONTROL Count values]** |

{style="table-layout:auto"}

### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Campaign ID | String | `campaignID` | |
| Campaign Member ID | String | `campaignMemberID` | |
| Campaign Member Status | String | `memberStatus` | |
| Campaign Member Status Reason | String | `memberStatusReason` | |
| Created Date | Date-time | `extSourceSystemAudit.createdDate` | Date-time format: **[!UICONTROL Day]** |
| First Responded Date | String | `firstRespondedDate` | Date-time format: **[!UICONTROL Day]** |
| Has Reached Success | Boolean | `hasReachedSuccess` | |
| Has Responded | Boolean | `hasResponded` | |
| Last Status | String | `lastStatus` | |
| Last Updated Date | Date-time | `extSourceSystemAudit.lastUpdatedDate` | Date-time format: **[!UICONTROL Day]** |
| Membership Date | Date-time | `membershipDate` | Date-time format: **[!UICONTROL Day]** |
| Nurture Cadence | String | `nurtureCadence` | |
| Nurture Track Name | String | `nurtureTrackName` | |
| Person ID | String | `personID` | |
| Reached Success Date | Date-time | `reachedSuccessDate` | Date-time format: **[!UICONTROL Day]** |
| Webinar Registration ID | String | `webinarRegistrationID` | |
| Webinar Registration URL | String | `webinarConfirmationUrl` | |
| isExhausted | Boolean | isExhausted | |

{style="table-layout:auto"}

+++

+++ B2B Marketing List Member dataset

### Metrics

### Dimensions

+++

-->

## 작업 영역

이제 데이터 보기에서 구성 요소를 제대로 정의하면 Workspace 프로젝트에서 특정 B2B 보고서와 시각화를 작성할 수 있습니다.

다음은 위에서 설명한 연결 및 데이터 보기에 의존하는 예제 프로젝트입니다.

![샘플 프로젝트](assets/sample-project.png)

<!-- See the descriptions for each visualization for more details.

+++ Example project

![Visualizations](assets/visualizations.png)

+++
-->
