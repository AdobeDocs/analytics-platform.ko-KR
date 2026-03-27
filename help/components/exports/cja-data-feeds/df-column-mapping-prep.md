---
description: Adobe Analytics의 데이터 피드 열을 Customer Journey Analytics에 매핑하는 방법을 알아봅니다.
keywords: 클릭스트림, 데이터 피드, 데이터피드, 데이터 피드
title: Adobe Analytics에서 Customer Journey Analytics으로 데이터 피드 열 매핑 준비
feature: Components
hide: true
hidefromtoc: true
exl-id: d0a9e697-1e48-4cfb-8613-2f932bf5015b
source-git-commit: 9403a4c6d0e0389de19aa4627d9d952f0c31f1a2
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 2%

---

# Adobe Analytics에서 Customer Journey Analytics으로 데이터 피드 열 매핑 준비

Customer Journey Analytics은 데이터 피드에 포함할 수 있는 열을 결정하기 위해 Adobe Analytics보다 유연한 아키텍처를 제공합니다. 대부분의 조직은 Customer Journey Analytics에서 내보낸 열과 Adobe Analytics에서 내보낸 열이 다를 것으로 예상해야 합니다. 이러한 차이는 다음 요인으로 인해 발생합니다.

* **[스키마 아키텍처](#schema-architecture)**: Adobe Analytics 데이터 피드 열은 Analytics 변수에서 파생되지만 Customer Journey Analytics 데이터 피드 열은 데이터 보기 스키마에서 파생됩니다.

* **[데이터 처리](#data-processing)**: Adobe Analytics과 Customer Journey Analytics 간에 기본 데이터 처리 차이가 있으며, 특히 많은 Adobe Analytics 열에 대해 사전 처리된 열과 사후 처리된 열이 모두 있습니다.

* **[사용되지 않은 열](#unused-columns)**: Adobe Analytics에 1,100개 이상의 데이터 피드 열이 있습니다. 대부분의 조직은 내보내는 모든 열의 데이터를 사용하지 않습니다.

* **[크로스 채널 열](#cross-channel-columns)**: Customer Journey Analytics은 Adobe Analytics에서 사용할 수 없는 크로스 채널 데이터(예: 콜 센터 데이터)를 지원합니다.

Adobe Analytics 데이터 피드 열을 Customer Journey Analytics 데이터 피드 열에 매핑하기 전에 아래 섹션을 검토하여 매핑에 영향을 주는 이러한 주요 요소를 더 잘 이해하십시오.

이 정보를 검토한 후 [데이터 열 참조](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)에 설명된 대로 Customer Journey Analytics에 유지할 각 Adobe Analytics 데이터 피드 열에 대한 매핑 지침을 따르십시오.

## 스키마 아키텍처

Customer Journey Analytics은 데이터 피드에 포함할 수 있는 열을 결정하기 위해 Adobe Analytics보다 유연한 아키텍처를 제공합니다.

### Adobe Analytics 아키텍처

데이터 피드 열로 포함하는 데 사전 정의된 정적 변수 목록을 사용할 수 있습니다.

조직 전체에서 해당 열에 포함된 데이터가 사용되지 않는 경우에도 모든 열을 포함하기 쉽고, 많은 고객이 이를 수행합니다.

### Customer Journey Analytics 아키텍처

데이터 보기 스키마에 포함된 모든 구성 요소는 데이터 피드 열로 포함될 수 있습니다. 각 잠재적 Adobe Analytics 데이터 피드 열에 대한 이 프로세스에 대한 자세한 내용은 [데이터 열 참조](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)를 참조하십시오.

구성 요소는 다음 표에 설명된 방법 중 하나로 데이터 보기 스키마에 포함됩니다.

| 데이터 보기 스키마에 포함하는 방법 | 추가 정보 |
|---------|----------|
| XDM 스키마 필드는 데이터 보기에서 구성 요소로 큐레이션됩니다 | XDM 스키마에 있는 필드는 데이터 보기에서 구성 요소로 조정된 후 Customer Journey Analytics에서 데이터 보기 스키마의 일부가 됩니다. <p>Customer Journey Analytics XDM 스키마에서 기본적으로 사용할 수 있는 필드 수는 Customer Journey Analytics 구현을 위해 데이터를 수집하는 방법에 따라 다음과 같이 다를 수 있습니다.</p><ul><li>**새로운 웹 SDK 구현**: Customer Journey Analytics 구현에서 사용자 지정 스키마를 사용하는 경우 Adobe Analytics 데이터 피드에 있는 많은 열이 Customer Journey Analytics에 존재하지 않을 수 있습니다. 마찬가지로 Customer Journey Analytics에는 Adobe Analytics 데이터 피드에 존재하지 않는 필드가 포함될 수 있습니다.<p>가능한 경우 조직의 Customer Journey Analytics 구현에 대해 XDM 스키마를 아키텍트한 팀 또는 개인에게 문의하십시오. XDM 스키마를 만들 때 Customer Journey Analytics에서 Adobe Analytics 필드가 필요한지 결정하는 경우가 많았습니다. 자세한 내용은 [Customer Journey Analytics에 사용할 스키마 설계](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)를 참조하십시오.</p></li><li>**Analytics Source 커넥터 구현**: Analytics Source 커넥터는 XDM 스키마에서 Analytics Experience Event 필드 그룹을 사용하므로 많은 데이터 피드 열에 대해 기본적으로 일대일 필드 매핑이 있습니다. 이 필드 그룹의 필드에 매핑되는 Adobe Analytics 필드에 대한 자세한 내용은 Experience Platform 설명서의 [Analytics 필드 매핑](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)을 참조하십시오.</li></ul> |
| 구성 요소는 파생 필드를 사용하여 데이터 보기 내에서 만들어집니다 | 데이터 보기 내에서 직접 구성 요소를 만들 수 있으므로 XDM 스키마에서 사용할 수 없는 데이터 피드 열을 만들 수 있습니다. |

## 데이터 처리

Adobe Analytics과 Customer Journey Analytics 간의 데이터 처리 차이는 다음과 같이 내보내기에 사용할 수 있는 데이터 피드 열에 영향을 줍니다.

* **Adobe Analytics**: 많은 데이터 피드 필드를 두 개의 개별 열로 내보냅니다. 하나는 사전 처리된 데이터를 포함하고 다른 하나는 사후 처리된 데이터를 포함합니다. (후 처리된 데이터에는 서버측 논리, 처리 규칙, VISTA 규칙, 차원 지속성 규칙 등이 포함됩니다.)

  Adobe Analytics은 일부 필드에 대한 데이터를 두 개의 개별 열(사전 처리된 데이터에 대한 열과 사후 처리된 데이터에 대한 열)로 내보내므로, Adobe Analytics에는 Customer Journey Analytics보다 더 많은 데이터 피드 열이 포함되어 있습니다. 필드를 매핑할 때 이 점을 염두에 두십시오.

* **Customer Journey Analytics**: 데이터 보기에서 필드를 만든 후 데이터 피드에 사용할 수 있습니다. 일반적으로 Customer Journey Analytics 데이터 보기의 필드에는 후처리된 데이터만 포함됩니다. 그러나 일반적으로 Customer Journey Analytics 데이터 보기 내에 필드의 두 번째 버전을 만들고 히트 시 만료되도록 구성하여 Adobe Analytics 사전 처리된 필드 버전을 근사화할 수 있습니다.

## 사용되지 않은 열

Adobe Analytics에서 내보낼 수 있는 데이터 피드 열은 1,100개가 넘습니다. 그러한 열 중 일부만 Customer Journey Analytics 데이터 피드에 사용됩니다. 이 불일치는 Customer Journey Analytics 데이터 피드 열이 충분하지 않음을 나타내는 것이 아닙니다.

조직에서 사용하는 Adobe Analytics 데이터 피드 열을 식별합니다. 이렇게 하면 Customer Journey Analytics 데이터 피드에 필요한 열을 알려줍니다. 사용할 열을 결정하려면 다음 작업을 수행하십시오.

* **Adobe Analytics에만 적용되는 필드 식별**: Adobe Analytics 데이터 피드의 특정 열은 Adobe Analytics의 데이터 처리 엔진에 따라 다르므로 Customer Journey Analytics에는 적용되지 않습니다. 이러한 열의 예는 `exclude_hit` 및 `hit_source`입니다.

* **조직에 적용되는 필드 식별**: 모든 Adobe Analytics 고객이 사용 가능한 열을 모두 내보내는 것은 아니지만 많은 고객이 실제로 사용하는 것보다 더 많이 내보냅니다.

  Customer Journey Analytics에서 데이터 피드 내보내기를 시작하기 전에 먼저 조직에서 현재 사용하는 Adobe Analytics 데이터 피드 열을 결정한 다음 이러한 구성 요소가 Customer Journey Analytics 데이터 보기 스키마에 있는지 확인해야 합니다. 이 정보를 수집하려면 Adobe Analytics에 대한 데이터 피드 콘텐츠를 사용하는 조직 내의 팀 또는 개인에게 문의하십시오.

## 크로스 채널 열

Customer Journey Analytics은 Adobe Analytics에서 사용할 수 없는 크로스 채널 데이터(예: 콜 센터 데이터)를 지원합니다. 이러한 크로스 채널 필드는 Customer Journey Analytics 데이터 피드에 포함할 수 있는 새 열의 예이며 Adobe Analytics에서 지원되지 않습니다.

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
