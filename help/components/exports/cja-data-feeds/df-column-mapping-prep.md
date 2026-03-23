---
description: Adobe Analytics의 데이터 피드 열을 Customer Journey Analytics에 매핑하는 방법을 알아봅니다.
keywords: 클릭스트림, 데이터 피드, 데이터피드, 데이터 피드
title: Adobe Analytics에서 Customer Journey Analytics으로 데이터 피드 열 매핑 준비
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 5dada1744a479cd4736c9fb7f3c807471e8da226
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 2%

---

# Adobe Analytics에서 Customer Journey Analytics으로 데이터 피드 열 매핑 준비

Adobe Analytics 데이터 피드에서 Customer Journey Analytics 데이터 피드로 전환하는 경우 모든 Adobe Analytics 데이터 피드 열을 Customer Journey Analytics의 데이터 피드 열에 매핑하는 것이 당연합니다.

하지만 Adobe Analytics에서 Customer Journey Analytics으로 데이터 피드 열을 매핑하는 것은 거의 일대일 매핑이 아닙니다. 이는 다음과 같은 요인에 기인합니다.

* **[스키마 아키텍처](#schema-architecture)**: Adobe Analytics 데이터 피드 열은 Analytics 변수에서 파생되지만 Customer Journey Analytics 데이터 피드 열은 Experience Platform의 XDM 스키마 필드 및 Customer Journey Analytics의 데이터 보기 구성 요소에서 파생됩니다.

* **[구현 유형](#implementation-type)**: Adobe Analytics 및 Customer Journey Analytics은 각각 여러 구현 구성을 지원합니다. 개별 필드를 매핑하는 데 필요한 단계는 이러한 구현에 따라 다릅니다.

* **[데이터 처리](#data-processing)**: Adobe Analytics과 Customer Journey Analytics 간에 기본 데이터 처리 차이가 있습니다.

* **[사용되지 않은 열](#unused-columns)**: Adobe Analytics에 1,100개 이상의 데이터 피드 열이 있습니다. 필요한 열만 매핑할 수 있도록 조직에서 사용하는 이러한 열을 식별합니다.

Adobe Analytics 데이터 피드 열을 Customer Journey Analytics 데이터 피드 열에 매핑하기 전에 아래 섹션을 검토하여 매핑에 영향을 주는 이러한 주요 요소를 더 잘 이해하십시오.

이 정보를 검토한 후 [데이터 열 참조](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)에 설명된 대로 Customer Journey Analytics에 유지할 각 Adobe Analytics 데이터 피드 열에 대한 매핑 지침을 따르십시오.

## 스키마 아키텍처

XDM(경험 데이터 모델) 스키마와 Customer Journey Analytics에서 사용되는 데이터 보기는 Adobe Analytics 변수 기반 모델보다 더 유연합니다. 따라서 조직의 XDM 스키마에는 일대일 데이터 피드 열 매핑으로 변환되는 필드가 포함되지 않을 수 있습니다.

스키마 아키텍처에 대한 다음 사항을 고려하십시오.

* 일대일 열 매핑이 부족하다고 해서 Customer Journey Analytics XDM 스키마가 부족한 것은 아닙니다. 즉, 현재 사용 중인 Adobe Analytics 데이터 피드 열을 먼저 결정한 다음 해당 열만 Customer Journey Analytics 데이터 피드에 매핑해야 합니다.

* Customer Journey Analytics XDM 스키마는 Adobe Analytics에서 사용할 수 없는 크로스 채널 데이터(예: 콜 센터 데이터)를 지원합니다. 이러한 크로스 채널 필드는 Adobe Analytics에서 지원되지 않는 Customer Journey Analytics 데이터 피드에 포함할 수 있는 새 열의 예입니다.

* 필드는 Customer Journey Analytics의 XDM 스키마에 포함된 다음 Customer Journey Analytics의 데이터 보기 내에서 사용하도록 조정된 후에만 Experience Platform 데이터 피드에 포함할 수 있습니다.

  각 잠재적 Adobe Analytics 데이터 피드 열에 대한 이 프로세스에 대한 자세한 내용은 [데이터 열 참조](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)를 참조하십시오.

>[!TIP]
>
>가능한 경우 조직의 Customer Journey Analytics 구현에 대해 XDM 스키마를 아키텍트한 팀 또는 개인에게 문의하십시오. XDM 스키마를 만들 때 Customer Journey Analytics에서 Adobe Analytics 필드가 필요한지 결정하는 경우가 많았습니다. 자세한 내용은 [Customer Journey Analytics에 사용할 스키마 설계](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)를 참조하십시오.

## 구현 유형

<!--  tons of different AA implementations + tons of different CJA schemas -->

Customer Journey Analytics XDM 스키마에서에 매핑할 수 있는 필드 수는 Customer Journey Analytics 구현을 위해 데이터를 수집하는 방법에 따라 다음과 같이 달라질 수 있습니다.

* **새로운 웹 SDK 구현**: Customer Journey Analytics 구현에서 사용자 지정 스키마를 사용하는 경우 Adobe Analytics 데이터 피드에 있는 많은 열이 Customer Journey Analytics에 존재하지 않을 수 있습니다. 마찬가지로 Customer Journey Analytics에는 Adobe Analytics 데이터 피드에 존재하지 않는 필드가 포함될 수 있습니다.

* **Analytics Source 커넥터 구현**: Analytics Source 커넥터는 XDM 스키마에서 Analytics Experience Event 필드 그룹을 사용하므로 많은 데이터 피드 열에 대해 기본적으로 일대일 필드 매핑이 있습니다. 이 필드 그룹의 필드에 매핑되는 Adobe Analytics 필드에 대한 자세한 내용은 Exprience Platform 설명서의 [Analytics 필드 매핑](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)을 참조하십시오.

<!-- **Data layer**: ??? -->

## 데이터 처리

Adobe Analytics과 Customer Journey Analytics의 데이터 처리는 다음과 같이 다릅니다.

**Adobe Analytics**: 많은 데이터 피드 필드를 두 개의 개별 열로 내보냅니다. 하나는 사전 처리된 데이터를 포함하고 다른 하나는 사후 처리된 데이터를 포함합니다. (후 처리된 데이터에는 서버측 논리, 처리 규칙, VISTA 규칙, 차원 지속성 규칙 등이 포함됩니다.)

Adobe Analytics은 일부 필드에 대한 데이터를 두 개의 개별 열(사전 처리된 데이터에 대한 열과 사후 처리된 데이터에 대한 열)로 내보내므로, Adobe Analytics에는 Customer Journey Analytics보다 더 많은 데이터 피드 열이 포함되어 있습니다. 필드를 매핑할 때 이 점을 염두에 두십시오.

**Customer Journey Analytics**: 데이터 보기에서 필드를 만든 후 데이터 피드에 사용할 수 있습니다. 일반적으로 Customer Journey Analytics 데이터 보기의 필드에는 후처리된 데이터만 포함됩니다. 그러나 일반적으로 Customer Journey Analytics 데이터 보기 내에 필드의 두 번째 버전을 만들고 히트 시 만료되도록 구성하여 Adobe Analytics 사전 처리된 필드 버전을 근사화할 수 있습니다.

## 사용되지 않은 열

Adobe Analytics에서 내보낼 수 있는 데이터 피드 열은 1,100개가 넘습니다. 그러한 열 중 일부만 Customer Journey Analytics 데이터 피드에 사용됩니다.

사용할 열을 결정하려면 다음 작업을 수행하십시오.

* **Adobe Analytics에만 적용되는 필드 식별**: Adobe Analytics 데이터 피드의 특정 열은 Adobe Analytics의 데이터 처리 엔진에 따라 다르므로 Customer Journey Analytics에는 적용되지 않습니다. 이러한 열의 예는 `exclude_hit` 및 `hit_source`입니다.

* **조직에 적용되는 필드 식별**: 모든 Adobe Analytics 고객이 사용 가능한 열을 모두 내보내는 것은 아니지만 많은 고객이 실제로 사용하는 것보다 더 많이 내보냅니다.

  데이터 피드 열 매핑을 시작하기 전에 조직 전체에서 실제로 사용 중인 필드를 식별하십시오. 이 정보를 수집하려면 Adobe Analytics에 대한 데이터 피드 콘텐츠를 사용하는 팀 또는 개인에게 문의하십시오.



<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
