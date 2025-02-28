---
title: 요약 데이터
description: 데이터 보기에서 요약 데이터를 사용하고 구성하는 방법에 대한 세부 정보 및 정보.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: e2e04432682f94b18bf9ed25d15f906c05bfd59d
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 7%

---

# 요약 데이터

요약 데이터는 개별 개인 ID에 연결되지 않은 시계열 데이터입니다. 요약 데이터는 캠페인과 같이 여러 집계 수준에서 집계된 데이터를 나타냅니다. 이 데이터를 Customer Journey Analytics에 활용해 다양한 사용 사례를 지원할 수 있습니다. 예를 들어, 날짜 및 단일 지표 값이 포함된 데이터나 여러 차원 및 지표가 포함된 데이터가 있을 수 있습니다.

그런 다음 이 요약 데이터를 사용하여 높은 수준의 성과 지표를 제시하거나 분석을 수행할 수 있습니다. 요약 데이터의 예로는 광고 노출 횟수, 이메일 열기, 광고 지출, 매출 원가, S&amp;P 지수 등이 있습니다. 요약 데이터를 사용하여 시간별 또는 일별로 대상이나 목표를 업로드할 수도 있습니다.

>[!NOTE]
>
>요약 데이터는 요약 데이터 세트의 시계열 데이터입니다. 해당 요약 데이터 세트는 XDM 요약 지표 클래스를 기본 클래스로 사용하는 스키마를 기반으로 합니다.
>시간별 또는 일별 기반 시계열 데이터만 지원됩니다.

>[!TIP]
>
>연결, 데이터 보기를 구성하고 이후에 **전용** 요약 데이터에 대해 보고할 수 있습니다. 구성의 일부로 추가 이벤트, 프로필 또는 조회 데이터가 필요하지 않습니다.


## 예

요약 데이터를 사용하는 예는 요약된 광고 캠페인 데이터와 온사이트 클릭스트림 데이터를 결합하여 보고하는 것입니다.

### 요약 데이터

요약 데이터에는 다음 광고 캠페인 데이터가 포함됩니다.

| 캠페인 코드 | 노출 횟수 | 비용 |
|---|---:|---:|
| abc123 | 1,250 | 1,500달러 |
| def456 | 775 | 650달러 |
| ghi789 | 500 | 500달러 |


### 이벤트 데이터

온사이트 클릭스트림 데이터에는 다음 이벤트가 포함됩니다.

| 추적 코드 | 클릭스루 | 매출 |
|---|---:|---:|
| abc123 | 1,250 | US$7,200 |
| def456 | 775 | US$1,250 |
| ghi789 | 500 | 750달러 |

### 결합된 데이터

[결합된 이벤트 데이터 세트](/help/connections/combined-dataset.md)에서 설명한 대로 연결을 정의하면 Customer Journey Analytics에서 전체 결합된 이벤트 데이터 세트를 만듭니다. 요약 데이터 세트에서 가져온 차원에 대한 데이터 보기를 구성할 때 Workspace에서 보고를 위한 준비로 차원을 그룹화하고 숨기는 데 옵션을 사용할 수 있습니다. 특히 요약 데이터의 경우 [요약 데이터 그룹 구성 요소](component-settings/summary-data-group.md) 구성을 기반으로 요약 데이터가 이벤트 데이터와 결합됩니다.

| 추적 코드 | 캠페인 코드 | 노출 횟수 | 비용 | 클릭스루 | 매출 |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1,250 | 1,500달러 | 1,250 | US$7,200 |
| def456 | def123 | 775 | 650달러 | 775 | US$1,250 |
| ghi789 | ghi789 | 500 | 500달러 | 500 | 750달러 |



### 보고

요약된 이벤트 데이터와 온사이트 클릭스트림 데이터를 결합하면 Workspace에서 광고 투자 수익률(ROAS)에 대해 보고할 수 있습니다.

| 추적 코드 | 노출 횟수 | 비용 | 클릭스루 | 매출 | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1,250 | 1,500달러 | 1,250 | US$7,200 | 4.80 |
| def456 | 775 | 650달러 | 775 | US$1,250 | 1.92 |
| ghi789 | 500 | 500달러 | 500 | 750달러 | 1.50 |


### 조회 데이터

추가 조회 데이터 세트에 정의된 차원(예: 캠페인 이름)을 사용하여 보고하려면 다음 추가 단계를 수행해야 합니다.

1. [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup) 함수를 사용하여 조회 데이터 집합에서 캠페인 이름을 조회하는 새 파생 필드를 만듭니다. [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup) 함수의 정의에서는 캠페인 코드와 추적 코드 간의 일치 항목을 사용하여 캠페인 이름을 조회합니다.
1. 새로 생성된 파생 필드를 데이터 보기에 차원 구성 요소로 추가합니다.
1. 조회 데이터 세트에서 캠페인 이름 차원 구성 요소를 구성하여 새로 생성된 파생 필드로 요약 데이터 그룹화를 만듭니다.

Customer Journey Analytics에서 요약 데이터를 사용, 보고 및 분석하는 방법에 대한 자세한 문서는 [요약 데이터 수집 및 보고](/help/use-cases/data-views/summary-data.md) 사용 사례를 참조하십시오.


## 사전 요구 사항

보고서 및 분석에서 요약 데이터를 제대로 사용하려면 많은 사전 요구 사항이 적용됩니다. 다음 섹션에서는 이러한 사전 요구 사항에 대해 자세히 설명합니다.

### 세부기간 및 시간대

Customer Journey Analytics에서 요약 데이터가 포함된 데이터 세트를 구성할 때 세부 기간이 데이터에서 자동으로 파생됩니다. **[!UICONTROL 타임스탬프]** 및 **[!UICONTROL 시간대]** 드롭다운에 대한 선택 항목이 둘 다 스키마 정의에서 파생되었으므로 비활성화됩니다.

#### 세부 기간

하나의 요약 데이터 스키마를 사용하여 하나의 데이터 세트(또는 다른 데이터 세트)에서 요약 데이터의 시간별 및 일별 세부기간을 혼합하고 일치시킬 수 없습니다. 예를 들어 광고 캠페인 데이터에 대한 일별 및 시간별 세부 요약 데이터가 있는 경우 일별 및 시간별 요약 데이터의 스키마 두 개가 필요합니다. 그런 다음 적절한 스키마와 연결된 데이터 세트에 관련 세부 데이터를 업로드합니다(예: 시간별 데이터를 시간별 요약 데이터 스키마와 연결된 데이터 세트에 업로드).

#### 시간대

요약 데이터의 시간대는 Experience Platform의 요약 스키마 수준에서 정의됩니다. 시간대는 시간별 세부 데이터에만 적용됩니다.

- 일별 세부기간의 경우 시간대 오프셋이 타임스탬프에 포함되지 않으면 Experience Platform은 UTC를 가정합니다. 일별 요약 데이터가 포함된 요약 데이터 세트를 추가할 때 Customer Journey Analytics은 스키마에 설정된 시간대 정의를 무시하고 데이터 세트의 데이터에서 타임스탬프와 연결된 일을 준수합니다.
- 시간별 세부기간의 경우 Customer Journey Analytics은 타임스탬프를 해석할 때 Experience Platform의 요약 데이터 스키마에 구성된 시간대를 따릅니다. 아래 표는 이러한 해석의 몇 가지 예를 제공한다.

  | 타임스탬프 <br/>원본 데이터 | 시간대<br/>스키마 | 타임스탬프<br/>경험<br/>플랫폼 | 시간대<br/> 데이터<br/>보기 | 타임스탬프<br/>고객<br/>여정<br>분석 |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:0 | *기본 GMT* | 2024-07-29T01:00:0 | GMT | 2024-07-29T01:00:0 |
  | 2024-07-29T01:00:0 | *기본 GMT* | 2024-07-29T01:00:0 | PST | 2024년 7월 28일:00:0 |
  | 2024-07-30T01:00:00-05:00 | *기본 GMT* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *기본 GMT* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:0 |
  | 2024년 8월 2일 | *기본 GMT* | 2024-08-02T00:00:0 | IST | 2024-08-02T05:00:0 |
  | 2024-07-29T01:00:0 | `America/`<br/>`Los_Angeles` | 2024년 7월 28일:00:0 | PST | 2024년 7월 28일:00:0 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  30분 오프셋이 있는 시간대(예: IST, 인도 표준시)의 경우 요약 데이터에 대해 보고할 때 30분 오프셋이 삭제됩니다. 예를 들어 12:30은 12:00으로 보고됩니다.


시간별 세부 요약 데이터에 적절한 시간대가 사용되도록 하려면 요약 데이터에 사용되는 스키마에 적절한 시간대가 구성되어 있는지 확인해야 합니다.

요약 데이터 스키마에 대한 세부 기간 및 시간대를 구성하려면 사용 가능한 동등한 사용자 인터페이스가 없으므로 다음 API 호출을 사용해야 합니다.

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
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | 이러한 변수에 대한 값을 지정하는 방법에 대한 자세한 내용은 [Experience Platform API 인증 및 액세스](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication)를 참조하십시오. |
| `$SCHEMA_ID` | Experience Platform UI에서 스키마 ID를 찾을 수 있습니다. 스키마 목록에서 요약 스키마를 선택하고 오른쪽 패널에서 **[!UICONTROL API 사용량]** > **[!UICONTROL 스키마 ID]**&#x200B;을(를) 찾습니다. 해당 ID를 값으로 사용합니다. |
| `$GRANULARITY` | `hour` 또는 `day`을(를) 값으로 지정합니다. |
| `$TIMEZONE` | [tz 데이터베이스 표준 시간대 목록](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)의 TZ 식별자 열에서 올바른 표준 시간대 식별자 값을 지정하십시오. 예: `America/Los_Angeles`. |

## 구성 요소 설정

요약 데이터 그룹에 대한 구성 요소 설정이 동일한지 확인합니다. 자세한 내용은 [요약 데이터 그룹 구성 요소 설정](component-settings/summary-data-group.md#same-component-settings)을 참조하세요.

>[!MORELIKETHIS]
>
>- 요약 데이터를 사용하고 보고하는 방법에 대한 자세한 사용 사례 예제는 [사용 요약 데이터](/help/use-cases/data-views/summary-data.md) 문서를 참조하십시오.
>- 블로그: [요약 데이터가 Adobe Customer Journey Analytics 데이터 세트를 향상시키는 방법](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635)

