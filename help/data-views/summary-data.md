---
title: 요약 데이터
description: 데이터 보기에서 요약 데이터를 사용하고 구성하는 방법에 대한 세부 정보와 정보에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 96%

---

# 요약 데이터

요약 데이터는 개인 ID에 연결되지 않은 시계열 데이터입니다. 요약 데이터는 캠페인과 같이 여러 집계 수준에서 집계된 데이터를 나타냅니다. 이 데이터를 Customer Journey Analytics에 활용해 다양한 사용 사례를 지원할 수 있습니다. 예를 들어 날짜와 단일 지표 값을 포함하는 데이터 또는 여러 차원과 지표를 포함하는 데이터.

이러한 요약 데이터는 상위 수준의 성과 지표를 제시하거나 분석을 수행하는 데 사용될 수 있습니다. 요약 데이터의 예로는 광고 노출 수, 이메일 열람수, 광고 지출액, 매출 원가, S&amp;P 지수 등이 있습니다. 요약 데이터를 사용하여 시간별 또는 일별 목표나 목적을 업로드할 수도 있습니다.

>[!NOTE]
>
>요약 데이터는 요약 데이터 세트의 시계열 데이터입니다. 해당 요약 데이터 세트는 XDM 요약 지표 클래스를 기본 클래스로 사용하는 스키마를 기반으로 합니다.
>시간별 또는 일별 기반의 시계열 데이터만 지원됩니다.

>[!TIP]
>
>연결, 데이터 보기를 구성한 후 요약 데이터에 **대해서만** 보고할 수 있습니다. 구성의 일부로 추가 이벤트, 프로필 또는 조회 데이터가 필요하지 않습니다.


## 예

요약 데이터 활용의 예로는 요약된 광고 캠페인 데이터를 보고를 위해 온사이트 클릭스트림 데이터와 결합하는 것이 있습니다.

### 요약 데이터

요약 데이터에는 다음과 같은 광고 캠페인 데이터가 포함되어 있습니다.

| 캠페인 코드 | 노출 횟수 | 비용 |
|---|---:|---:|
| abc123 | 1,250 | $1,500 |
| def456 | 775 | $650 |
| ghi789 | 500 | $500 |


### 이벤트 데이터

사이트 내 클릭스트림 데이터에는 다음과 같은 이벤트가 포함되어 있습니다.

| 추적 코드 | 클릭스루 | 매출 |
|---|---:|---:|
| abc123 | 1,250 | $7,200 |
| def456 | 775 | $1,250 |
| ghi789 | 500 | $750 |

### 결합된 데이터

[결합된 이벤트 데이터세트](/help/connections/combined-dataset.md)에서 설명한 대로, 연결을 정의할 때 Customer Journey Analytics는 전체적으로 결합된 이벤트 데이터세트를 생성합니다. 요약 데이터 세트에서 시작하는 차원에 대한 데이터 보기를 구성할 때 Workspace에서 보고를 준비하기 위해 차원을 그룹화하고 숨길 수 있는 옵션이 있습니다. 특히 요약 데이터의 경우, 요약 데이터는 [요약 데이터 그룹 구성 요소](component-settings/summary-data-group.md) 구성을 기반으로 이벤트 데이터와 결합됩니다.

| 추적 코드 | 캠페인 코드 | 노출 횟수 | 비용 | 클릭스루 | 매출 |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1,250 | $1,500 | 1,250 | $7,200 |
| def456 | def123 | 775 | $650 | 775 | $1,250 |
| ghi789 | ghi789 | 500 | $500 | 500 | $750 |



### 보고

요약된 이벤트 데이터와 사이트 내 클릭스트림 데이터를 결합하면 Workspace에서 광고 지출 수익률(ROAS)을 보고할 수 있습니다.

| 추적 코드 | 노출 횟수 | 비용 | 클릭스루 | 매출 | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1,250 | $1,500 | 1,250 | $7,200 | 4.80 |
| def456 | 775 | $650 | 775 | $1,250 | 1.92 |
| ghi789 | 500 | $500 | 500 | $750 | 1.50 |


### 조회 데이터

추가 조회 데이터 세트(예: 캠페인 이름)에 정의된 차원을 사용하여 보고하려면 다음 추가 단계를 수행해야 합니다.

1. [조회](/help/data-views/derived-fields/derived-fields.md#lookup) 함수를 사용하여 조회 데이터 세트에서 캠페인 이름을 조회하는 새로운 파생 필드를 만듭니다. [조회](/help/data-views/derived-fields/derived-fields.md#lookup) 함수의 정의에서 캠페인 코드와 추적 코드가 일치하는 항목을 사용하여 캠페인 이름을 조회합니다.
1. 새로 만든 파생 필드를 데이터 보기에 차원 구성 요소로 추가합니다.
1. 새로 만든 파생 필드에 요약 데이터 그룹화를 적용하기 위해 캠페인 이름 차원 구성요소(조회 데이터 세트에서)를 구성합니다.

Customer Journey Analytics에서 요약 데이터를 활용하고, 보고하고, 분석하는 방법에 대한 자세한 내용은 [요약 데이터 수집 및 보고](/help/use-cases/data-views/summary-data.md) 사용 사례를 참조하십시오.


## 사전 요구 사항

보고서와 분석에 요약 데이터를 적절하게 사용하려면 몇 가지 사전 요구 사항이 적용됩니다. 다음 섹션에서는 이러한 사전 요구 사항에 대해 자세히 설명합니다.

### 세부 기간 및 시간대

Customer Journey Analytics에서 요약 데이터가 포함된 데이터 세트를 구성할 때 세부 기간이 데이터에서 자동으로 파생된다는 점을 알 수 있습니다. **[!UICONTROL 타임스탬프]** 및 **[!UICONTROL 시간대]** 드롭다운 메뉴에 대한 선택 항목이 둘 다 스키마 정의에서 파생되었으므로 비활성화됩니다.

#### 세부 기간

하나의 요약 데이터 스키마에서는 요약 데이터의 시간별 세부 기간과 일별 세부 기간을 한 데이터 세트(또는 서로 다른 데이터 세트)에서 혼합하거나 일치시킬 수 없습니다. 예를 들어 광고 캠페인 데이터에 대한 일별 및 시간별 세부 요약 데이터가 있는 경우 일별 요약 데이터와 시간별 요약 데이터용 스키마가 두 개 필요합니다. 그런 다음 적절한 스키마와 연결된 데이터 세트에 관련 세부 데이터를 업로드합니다(예: 시간별 데이터를 시간별 요약 데이터 스키마와 연결된 데이터 세트에 업로드).

#### 시간대

요약 데이터의 시간대는 Experience Platform의 요약 스키마 수준에서 정의됩니다. 시간대는 시간별 세부 데이터에만 적용됩니다.

- 일별 세부 기간의 경우 Experience Platform은 타임스탬프에 시간대 간격이 포함되지 않는 한 UTC를 가정합니다. 일별 요약 데이터가 포함된 요약 데이터 세트를 추가할 때 Customer Journey Analytics는 스키마에 설정된 시간대 정의를 무시하고 데이터 세트의 데이터에 있는 타임스탬프와 연관된 날짜를 따릅니다.
- 시간별 세부 기간의 경우 Customer Journey Analytics는 타임스탬프를 해석할 때 Experience Platform의 요약 데이터 스키마에 구성된 시간대를 따릅니다. 아래 테이블은 이러한 해석의 몇 가지 예를 보여 줍니다.

  | 타임스탬프 <br/>소스 데이터 | 시간대<br/>스키마 | 타임스탬프<br/>Experience<br/>Platform | 시간대<br/> 데이터<br/> 보기 | 타임스탬프<br/>Customer<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *기본 GMT* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *기본 GMT* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *기본 GMT* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *기본 GMT* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *기본 GMT* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  30분 간격이 있는 시간대(예: IST, 인도 표준시)의 경우 요약 데이터를 보고할 때 30분 간격은 삭제됩니다. 예를 들어 12:30이(가) 12:00(으)로 보고됩니다.


시간별 세부 요약 데이터에 적절한 시간대가 사용되도록 하려면 요약 데이터에 사용된 스키마에 적절한 시간대가 구성되어 있는지 확인해야 합니다.

요약 데이터 스키마의 세부 기간과 시간대를 구성하려면, 이를 설정할 수 있는 사용자 인터페이스가 없으므로 다음 API 호출을 사용해야 합니다.

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| 변수 | 값 |
|---|---|
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | 이러한 변수의 값을 지정하는 방법에 대한 자세한 내용은 [Experience Platform API 인증 및 액세스](https://experienceleague.adobe.com/ko/docs/experience-platform/landing/platform-apis/api-authentication)를 참조하십시오. |
| `$SCHEMA_ID` | Experience Platform UI에서 스키마 ID를 찾을 수 있습니다. 스키마 목록에서 요약 스키마를 선택하고 오른쪽 패널에서 **[!UICONTROL API 사용]** > **[!UICONTROL 스키마 ID]**&#x200B;를 찾습니다. 해당 ID를 값으로 사용합니다. |
| `$GRANULARITY` | `hour` 또는 `day`를 값으로 지정합니다. |
| `$TIMEZONE` | [TZ 데이터베이스 시간대 목록](https://ko.wikipedia.org/wiki/List_of_tz_database_time_zones)에서 TZ 식별자 열에서 적절한 시간대 식별자 값을 지정합니다. 예: `America/Los_Angeles`. |

## 구성 요소 설정

요약 데이터 그룹의 구성 요소 설정이 동일한지 확인합니다. 자세한 내용은 [요약 데이터 그룹 구성 요소 설정](component-settings/summary-data-group.md#same-component-settings)을 참조하십시오.

>[!MORELIKETHIS]
>
>- 요약 데이터를 사용하고 보고하는 방법에 대한 자세한 사용 사례 예제는 [요약 데이터 사용](/help/use-cases/data-views/summary-data.md) 문서에서 확인하십시오.
>- 블로그: [요약 데이터가 Adobe Customer Journey Analytics 데이터 세트를 향상하는 방법](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635)

