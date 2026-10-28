---
title: Customer Journey Analytics에서 유료 미디어 데이터를 웹 데이터와 연결
description: 유료 미디어 요약 데이터를 Adobe Customer Journey Analytics의 웹 사이트 이벤트와 연결하여 광고 지출, 클릭 수, 주문, 매출 및 광고 지출 수익률을 비교할 수 있습니다.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
role: Admin
source-git-commit: 11bc93e0adabd8e8109bda1734e1a098ce8bef1e
workflow-type: tm+mt
source-wordcount: '3907'
ht-degree: 3%
---
# 웹 데이터를 사용하여 유료 미디어 데이터 가입

이 사용 사례 안내서는 [!DNL Adobe Customer Journey Analytics]에서 유료 미디어 요약 데이터를 웹 사이트 동작 이벤트 데이터와 결합하는 방법을 보여 줍니다.


광고 계정(Meta, Google 광고 및 기타)을 Experience Platform에 연결하면 계정, 캠페인, 광고 그룹, 광고, 경험 및 에셋당 일일 노출 횟수, 클릭 수, 지출 및 광고 네트워크에서 보고한 전환 등 Customer Journey Analytics의 유료 미디어 요약 데이터가 제공됩니다. Customer Journey Analytics을 사용하면 페이지 보기 수, 주문 수, 매출과 같은 Web SDK을 통해 고유한 온사이트 행동 이벤트 데이터를 수집할 수 있습니다.

단일 Workspace 자유 형식 테이블에 있는 두 가지 유형의 데이터를 결합하면 웹 사이트의 활동과 광고 성능을 비교할 수 있습니다. 공유 캠페인, 광고 그룹 및 광고 ID를 사용하여 [!DNL Analysis Workspace]에서 유료 랜딩, 주문 및 매출과 함께 노출, 클릭 수 및 지출에 대해 보고합니다.

| 데이터 소스 | 지표 예 |
|---|---|
| 유료 미디어 요약 데이터 | 광고 네트워크에서 보고한 노출 횟수, 클릭 수, 지출, 전환 및 전환 값입니다. |
| 웹 사이트 행동 이벤트 | 유료 랜딩 페이지, 페이지 조회수, 주문 및 웹 사이트에서 측정된 매출 |
| 계산된 지표 | 랜딩 페이지 비율, 웹 전환율, 웹 광고 투자 수익률, 웹 주문당 비용, 네트워크 대 웹 전환 차이 |

이 두 가지 유형의 데이터를 조합하면 사전 클릭 데이터(광고의)와 사후 클릭 데이터(웹 사이트의)를 비교할 수 있습니다.

이 안내서에서는 [!DNL Adobe Content Analytics] 구성에서 관리되는 연결 및 직접 구성하는 연결을 기반으로 하는 시나리오를 다룹니다.

## 작동 방식

아래 다이어그램은 유료 미디어 요약 데이터와 웹 사이트 행동 이벤트 데이터가 Customer Journey Analytics 연결을 통해 수집되는 방식을 보여 줍니다.

데이터 보기는 데이터의 구문 분석 및 정렬을 담당하므로 Workspace을 사용하여 데이터에 대해 올바로 보고할 수 있습니다.

![유료 미디어 가입](./assets/paid-media-web-join.png){zoomable="yes"}

유료 미디어 요약 데이터 세트에는 개인 ID 없이 일별 지표가 포함되어 있습니다. 웹 사이트 이벤트 데이터 세트에는 타임스탬프가 지정된 행동 이벤트와 개인 식별자가 포함됩니다. 요약 데이터 그룹은 동일한 차원 값이 동일한 보고 행에 표시되도록 이러한 데이터 세트의 차원을 연결합니다.

>[!IMPORTANT]
>
>이 조인은 보고를 위해 집계된 요약 데이터와 웹 이벤트를 정렬합니다. 광고 노출 또는 클릭을 개별 사용자에게 연결하지 않습니다. 광고 네트워크 전환은 네트워크의 보고 방식을 유지합니다. 웹 사이트 주문 및 매출은 이 안내서에서 구성하는 속성 설정을 사용합니다.

## 보고 조인 이해

랜딩 페이지 URL 또는 기존 이벤트 필드에 ID가 표시되는 수준에서만 가입할 수 있습니다. 예를 들어 캠페인 전용 태깅은 캠페인 보고를 지원하지만 광고 수준 보고는 지원하지 않습니다. 경험 수준 및 에셋 수준 조인은 추가 URL 매개 변수를 필요로 하며 이 안내서에서 다루지 않습니다.

참조하려면 [요약 데이터](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/summary-data) 및 [요약 데이터 그룹 구성 요소 설정](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/summary-data-group)을 참조하십시오.

### 조인 키 선택

유료 미디어 데이터 세트는 원시 네트워크 ID와 Adobe에서 생성한 GUID(Globally Unique Identifier)를 모두 제공합니다.

| 식별자 | 예 | 용도 |
|---|---|---|
| 네트워크 ID | 캠페인 ID `123456789` | 랜딩 페이지 URL에서 캡처한 ID를 유료 미디어 요약 차원과 일치시킵니다 |
| GUID | `meta_111111111_123456789` | 네트워크, 계정 및 엔티티 계층을 사용하여 유료 미디어 엔티티 식별 |

GUID 구조는 `{adNetwork}_{accountID}[_{campaignID}[_{adGroupID}[_{adID}]]]`입니다. [!DNL Adobe Content Analytics]이(가) 관리하는 유료 미디어 구성 요소는 다음 GUID를 사용합니다.

캠페인, 광고 그룹 및 광고 URL 매크로는 GUID를 재구성하는 데 필요한 모든 정보를 제공하지 않으므로 이 안내서는 웹 조인에 네트워크 ID를 사용합니다. 다음 요약 필드를 사용합니다.

| 보고 수준 | 네트워크 ID 필드 | GUID 필드 |
|---|---|---|
| 캠페인 | `paidMedia.campaignID` | `paidMedia.campaignGUID` |
| 광고 그룹 | `paidMedia.adGroupID` | `paidMedia.adGroupGUID` |
| 광고 | `paidMedia.adID` | `paidMedia.adGUID` |

네트워크 필드는 `paidMedia.adNetwork`입니다. 값의 예로는 `meta` 및 `google_ads`이(가) 있습니다. 파생 필드 출력은 데이터 세트의 값과 정확히 일치해야 합니다.

>[!NOTE]
>
>요약 데이터 그룹은 테이블에 있는 모든 차원의 조합이 아니라 차원 값과 일치합니다. 선택한 ID가 보고하는 계정 및 네트워크에서 개체를 명확하게 식별하는지 확인합니다. 이름 기반 그룹은 이름을 공유하는 개별 엔티티를 결합할 수 있습니다.

## 사전 요구 사항

다음을 보유하고 있는지 확인합니다.

* [!DNL Customer Journey Analytics] 여기에 사용된 파생 필드 함수에 대한 액세스 권한을 가진 이상 선택: [URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse), [대소문자](/help/data-views/derived-fields/derived-fields.md#case-when), [정규식 바꾸기](/help/data-views/derived-fields/derived-fields.md#regex-replace) 및 이름 보강의 경우 [조회](/help/data-views/derived-fields/derived-fields.md#lookup).
* 대상 샌드박스에서 스키마, 데이터 세트 및 데이터 스트림을 관리하고 확인을 위해 데이터 세트 및 쿼리 서비스에 액세스할 수 있는 [!DNL Adobe Experience Platform] 권한.
* 대상 연결 및 데이터 보기를 편집할 수 있는 [!DNL Customer Journey Analytics] 권한입니다.
* 동일한 샌드박스에 구성되어 요약 및 조회 데이터 세트를 수집하는 유료 미디어 소스 커넥터입니다. 예제 커넥터는 [Meta 광고 소스](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads)를 참조하십시오.
* 쿼리 문자열을 포함하여 전체 랜딩 페이지 URL을 캡처하거나 네트워크 ID를 포함하는 해당 필드를 캡처하는 웹 사이트 이벤트.


### 광고 태깅

캠페인, 광고 그룹 및 광고 ID가 포함된 쿼리 매개 변수를 식별합니다. 광고 플랫폼을 변경하지 않고 기존 ID 기반 태깅을 사용할 수 있습니다.

| 태깅 패턴 | 캠페인 매개 변수 | 광고 그룹 매개 변수 | 광고 매개 변수 |
|---|---|---|---|
| 웹 사이트 URL의 Meta ID | <code>campaign_id={{campaign.id}}</code> | <code>adset_id={{adset.id}}</code> | <code>ad_id={{ad.id}}</code> |
| UTM 매개 변수의 Meta ID | <code>utm_campaign={{campaign.id}}</code> | <code>utm_term={{adset.id}}</code> | <code>utm_content={{ad.id}}</code> |
| UTM 매개 변수의 Google 광고 ID | <code>utm_campaign={campaignid}</code> | <code>utm_term={adgroupid}</code> | <code>utm_content={creative}</code> |

Meta UTM 태깅의 경우 `utm_source=fb`과(와) 같은 소스 값이 네트워크를 식별할 수 있습니다. Google Ads UTM 태그 지정의 경우 `utm_source=google`과(와) 같은 소스 값을 사용하십시오.

일부 [!DNL Adobe Advertising] 통합에서는 이 레이아웃에 `s_kwcid` 값을 사용합니다.

```text
AL!<id>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}!{campaignid}!{adgroupid}
```

이 안내서의 뒷부분에 나오는 구문 분석 규칙은 이 레이아웃에만 적용됩니다. 실제 랜딩 URL을 사용하기 전에 검사합니다.

광고 플랫폼에 대한 액세스 권한이 없는 경우 웹 데이터 세트에서 랜딩 URL을 검사하십시오. 이러한 유료 미디어 조회 필드를 검사할 수도 있습니다.

* Google Ads 계정 조회: `google_ads_tracking_url_template` 및 `google_ads_final_url_suffix` 이름이 지정된 항목 `additionalDetails`개.
* Meta 광고 조회: `paidMedia.adDetails.creative.paidMediaCreative.destinationURL`.

저장된 대상 URL의 매크로는 퍼센트 인코딩이 가능합니다. 저장된 URL이 최종 랜딩 URL을 나타낸다고 가정하지 않고 실제 웹 사이트 이벤트에서 확장된 ID의 유효성을 검사합니다.

>[!IMPORTANT]
>
>`utm_campaign=fall_sale`과(와) 같은 캠페인 이름이 캠페인 ID와 일치하지 않습니다. 실제 ID가 포함된 수준에서만 가입합니다. ID가 없는 경우 광고 운영 팀과 함께 향후 트래픽에 대한 태깅을 업데이트합니다. 이 설정은 이전 방문에 대해 누락된 ID를 재구성할 수 없습니다.

### 시작점

사용할 데이터 보기를 열고 구성 요소를 검사하여 시작점을 결정합니다.

| | 시작점 | 기존 구성 | 따라야 할 단계 |
|---|---|---|---|
| A | 웹 또는 모바일 및 유료 미디어가 있는 Content Analytics | 유료 미디어 데이터 세트 및 구성 요소와 Content Analytics 이벤트 및 조회 데이터 세트 | 필요한 경우 웹 사이트 이벤트 데이터 세트를 추가한 다음 웹에서 파생된 필드 및 보고 그룹을 구성합니다 |
| B | 유료 미디어만 있는 Content Analytics | 유료 미디어 데이터 세트 및 구성 요소. 공유 컨텐츠 조회 데이터 세트가 있을 수도 있습니다. | 웹 사이트 이벤트 데이터 세트를 추가한 다음 웹에서 파생된 필드 및 보고 그룹을 구성합니다 |
| C | Content Analytics 프로비저닝 없이 유료 미디어 | 유료 미디어 데이터 세트가 Experience Platform에 있지만 연결 및 데이터 보기에 유료 미디어 구성이 포함되어 있지 않습니다 | 웹 사이트 및 유료 미디어 데이터 세트를 추가한 다음 유료 미디어 및 웹 구성 요소를 만듭니다 |
| D | 유료 미디어가 없는 Content Analytics | Content Analytics 구성 요소만 해당 | Content Analytics 구성에서 유료 미디어 채널을 활성화한 다음 기존 구성 경로를 따릅니다 |

Content Analytics에서 관리하는 연결을 확장할 때 시스템에서 프로비저닝한 데이터 세트 또는 읽기 전용 구성 요소를 제거하거나 수정하지 마십시오.

## 웹 사이트 행동 이벤트 수집

웹 사이트에서 이미 Customer Journey Analytics에 사용된 데이터 세트에 필요한 이벤트를 보낸 경우 스키마, 데이터 세트 및 데이터 스트림 생성을 건너뜁니다. `web.webPageDetails.URL`에 랜딩 페이지 쿼리 문자열이 포함되어 있는지 확인합니다.

### 스키마 및 데이터 세트 만들기

1. Experience Platform에서 타겟 샌드박스를 선택합니다.
1. **[!UICONTROL 데이터 관리]** > **[!UICONTROL 스키마]**(으)로 이동한 다음 **[!UICONTROL 스키마 만들기]**&#x200B;를 선택합니다.
1. **[!UICONTROL 수동]** 및 `XDM ExperienceEvent` 클래스를 선택하십시오.
1. 스키마 이름을 지정합니다(예: `Web Behavioral Events`).
1. 구현에 필요한 필드 그룹을 추가합니다.

   | 필드 그룹 | 필수 데이터 |
   |---|---|
   | AEP 웹 SDK ExperienceEvent | 페이지 URL, 페이지 보기, 레퍼러 및 기타 웹 컨텍스트 |
   | Commerce 세부 정보 | 구매 수, 주문 가격, 통화, 구매 ID 및 제품 세부 정보 |
   | 캠페인 마케팅 세부 정보, 선택 사항 | 구현에서 별도로 캡처하는 경우 추적 코드 |
   | IdentityMap(아직 없는 경우) | 개인 식별자(예: ECID) |

1. 스키마를 저장합니다. 이 보고 사용 사례에는 프로필 활성화가 필요하지 않습니다.
1. **[!UICONTROL 데이터 관리]** > **[!UICONTROL 데이터 세트]** > **[!UICONTROL 데이터 세트 만들기]** > **[!UICONTROL 스키마에서 데이터 세트 만들기]**(으)로 이동합니다.
1. 스키마를 선택하고 이름이 `Web Behavioral Events`인 데이터 집합을 만드십시오. 다른 사용 사례에서 필요로 하지 않는 한 **[!UICONTROL 프로필]**&#x200B;을 사용하지 않도록 설정하십시오.

### 데이터 스트림 및 웹 SDK 구성

1. **[!UICONTROL 데이터 수집]** > **[!UICONTROL 데이터스트림]** > **[!UICONTROL 새 데이터스트림]**(으)로 이동합니다.
1. 데이터스트림 이름을 지정하고 이벤트 스키마를 매핑 스키마로 선택합니다.
1. 저장한 다음 **[!UICONTROL 서비스 추가]** > **[!UICONTROL Adobe Experience Platform]**&#x200B;을(를) 선택합니다.
1. 샌드박스 및 이벤트 데이터 세트를 선택한 다음 **[!UICONTROL 저장]**&#x200B;을 선택합니다.
1. 데이터 스트림 ID를 사용하여 [Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/js-overview)을(를) 구성하십시오.

다음을 캡처합니다.

* `web.webPageDetails.URL` 및 `web.webPageDetails.pageViews.value`의 전체 URL을 `1`(으)로 설정하여 각 페이지에서 페이지 보기를 캡처합니다.
* `commerce.purchases.value`이(가) `1`, `commerce.order.priceTotal`, `commerce.order.currencyCode` 및 `commerce.order.purchaseID`(으)로 설정된 구매 이벤트.
* Customer Journey Analytics 연결에 적합한 개인 식별자.

웹 사이트 코드에서 UTM 매개 변수를 구문 분석할 필요가 없습니다. 이 안내서의 파생 필드는 보고서 시간에 URL을 구문 분석합니다. 구현에서 전용 필드의 ID를 이미 캡처한 경우 대신 해당 필드를 사용하십시오.

### 수집 확인

데이터 세트 활동에서 수집이 성공했는지 확인합니다. 쿼리 서비스에서 `web_behavioral_events`을(를) 데이터 세트의 SQL 테이블 이름으로 바꾸고 다음 쿼리를 실행합니다.

```sql
SELECT timestamp, eventType, web.webPageDetails.URL
FROM web_behavioral_events
WHERE web.webPageDetails.URL RLIKE '[?&](campaign_id|utm_campaign|s_kwcid)='
ORDER BY timestamp DESC
LIMIT 20;
```

반환된 URL에 확장된 네트워크 ID가 포함되어 있는지 확인합니다. 유료 트래픽이 존재하지만 쿼리가 행을 반환하지 않는 경우 최근 랜딩 URL을 검사하고 매개 변수 패턴을 태깅에 맞게 조정합니다.

## 연결 구성

웹 이벤트 데이터 세트를 Customer Journey Analytics으로 수집하려면 관련 연결에 데이터 세트를 추가해야 합니다. 이렇게 하면 웹 동작 이벤트를 유료 미디어 데이터 세트와 함께 사용하여 분석할 수 있습니다.

### 웹 사이트 이벤트 데이터 세트 추가

1. Customer Journey Analytics에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 연결]**(으)로 이동합니다.
1. 유료 미디어 데이터 세트를 포함하는 연결을 편집합니다.
1. **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택하고 웹 사이트 이벤트 데이터 세트를 선택합니다.
1. 데이터 세트를 구성합니다.

   | 설정 | 값 |
   |---|---|
   | 개인 ID | ECID 네임스페이스 또는 구현의 개인 ID 필드가 있는 `identityMap` |
   | 타임스탬프 | `timestamp` |
   | 데이터 소스 유형 | 웹 데이터 |
   | 모든 새 데이터 가져오기 | 활성화됨 |
   | 기존의 모든 데이터 다시 채우기 | 필요한 과거 기간에 대해 활성화됨 |

1. 데이터 세트를 추가하고 연결을 저장합니다.

### 아직 구성되지 않은 경우 유료 미디어 데이터 세트 추가

>[!IMPORTANT]
>
>Content Analytics에서 유료 미디어 데이터 세트를 관리하는 연결에 대해서는 이 섹션을 건너뜁니다.


최소 유료 미디어 광고 요약 및 유료 미디어 계정, 유료 미디어 캠페인, 유료 미디어 광고 그룹 및 유료 미디어 광고 조회 데이터 세트를 추가합니다.

| 데이터 세트 | 유형 | 키 구성 |
|---|---|---|
| 유료 미디어 광고 요약 | 요약 | 스키마의 일별 타임스탬프 구성을 사용합니다. 새 데이터 가져오기 및 필수 채우기를 활성화합니다. |
| 유료 미디어 계정 조회 | 조회 | 키: `paidMedia.accountGUID`; 광고 요약의 일치하는 필드: `paidMedia.accountGUID`. |
| 유료 미디어 캠페인 조회 | 조회 | 키: `paidMedia.campaignGUID`; 광고 요약의 일치하는 필드: `paidMedia.campaignGUID`. |
| 유료 미디어 광고 그룹 조회 | 조회 | 키: `paidMedia.adGroupGUID`; 광고 요약의 일치하는 필드: `paidMedia.adGroupGUID`. |
| 유료 미디어 광고 조회 | 조회 | 키: `paidMedia.adGUID`; 광고 요약의 일치하는 필드: `paidMedia.adGUID`. |

저장하기 전에 연결 편집기에서 의도한 일치 필드를 표시하는지 확인하십시오. 이 안내서의 뒷부분에서 이름 보강은 파생 필드 조회 규칙을 명시적으로 사용합니다.

지역, 인구 통계, 배치 또는 성능과 같은 분류가 필요한 경우에만 사용 가능한 다른 요약 데이터 세트를 추가합니다.

## 데이터 보기 구성

**[!UICONTROL 데이터 관리]** > **[!UICONTROL 데이터 보기]**&#x200B;를 열고 데이터 보기를 선택합니다. 필요한 경우 구성한 연결을 사용하여 데이터 보기를 만듭니다.

새 데이터 보기의 경우, GMT를 사용하여 웹 사이트 이벤트를 UTC 유료 미디어 일에 맞추고, 보고 요구 사항이 다르지 않은 경우 기본 30분 세션 시간 제한을 유지합니다. 기존 데이터 보기의 시간대를 변경하는 것은 다른 보고서에 영향을 줍니다. 변경하기 전에 해당 영향을 평가하십시오.

### 아직 구성되지 않은 경우 유료 미디어 지표 추가

이러한 지표 또는 차원이 이미 있는 경우 이 단계를 건너뜁니다. **[!UICONTROL 유료 미디어 광고 요약]**&#x200B;에서 다음 필드를 추가하십시오.

| 구성 요소 이름 | 스키마 필드 | 포맷 |
|---|---|---|
| **지표** | | |
| 노출 횟수 \| 광고 요약 | `paidMedia.metrics.impressions` | 소수 |
| 클릭 수 \| 광고 요약 | `paidMedia.metrics.clicks` | 소수 |
| 광고 지출 \| 요약 | `paidMedia.metrics.spend` | 통화 |
| 전환 \| 광고 요약 | `paidMedia.metrics.conversions` | 소수 |
| 전환 값 \| 광고 요약 | `paidMedia.metrics.conversionValue` | 통화 |
| **차원** | | |
| 광고 네트워크 | `paidMedia.adNetwork` | 문자열 |
| 계정 GUID | `paidMedia.accountGUID` | 문자열 |
| 캠페인 GUID | `paidMedia.campaignGUID` | 문자열 |
| 광고 그룹 GUID | `paidMedia.adGroupGUID` | 문자열 |
| 광고 GUID | `paidMedia.adGUID` | 문자열 |

통화 서식은 그 자체로 다른 소스 통화를 대사하지 않습니다. 소비와 매출을 비교하기 전에 통화 기준을 확인합니다.

파생된 필드를 사용하여 GUID 차원에 대한 수사적 이름을 만드십시오. [조회](/help/data-views/derived-fields/derived-fields.md#lookup) 규칙을 사용하여 GUID 차원에 대한 수사적 이름을 적용하세요.  예: 키 `paidMedia.accountGUID`과(와) 반환할 값이 일치하는 조회 데이터 세트 **[!UICONTROL 유료 미디어 계정 조회]**&#x200B;를 사용하여 **[!UICONTROL paidMedia.accountGUID(유료 미디어 광고 요약)]**&#x200B;을(를) 조회합니다. `paidMedia.accountDetails.accountName`.


### 웹 네트워크 파생 필드 만들기

**[!UICONTROL 파생 필드 만들기]**&#x200B;를 선택하고 필드 이름을 `PM Network (Web)`로 지정합니다. 아래의 모든 [URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse) 규칙은 여기에서 페이지 URL이라고 하는 웹 사이트 데이터 세트의 `web.webPageDetails.URL` 필드를 읽습니다.

다음 순서로 규칙 추가:

| 규칙 | 함수 | 구성 |
|---|---|---|
| 1 | [URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse) | 페이지 URL. `utm_source`에 대한 쿼리 문자열 값을 가져옵니다. |
| 2 | [URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse) | 페이지 URL. `s_kwcid`에 대한 쿼리 문자열 값을 가져옵니다. |
| 3 | [URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse) | 페이지 URL. `gclid`에 대한 쿼리 문자열 값을 가져옵니다. |
| 4 | [URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse) | 페이지 URL. `fbclid`에 대한 쿼리 문자열 값을 가져옵니다. |
| 5 | [다음의 경우](/help/data-views/derived-fields/derived-fields.md#case-when) | 아래 조건을 적용합니다. |

최종 [Case When](/help/data-views/derived-fields/derived-fields.md#case-when) 규칙을 구성합니다.

1. 규칙 2 또는 규칙 3이 설정된 경우 `google_ads`을(를) 반환합니다.
1. 그렇지 않으면 규칙 4가 설정되어 있거나 규칙 1이 `fb`, `facebook`, `ig`, `instagram` 또는 `meta`인 경우 `meta`을(를) 반환합니다.
1. 그렇지 않으면 규칙 1이 `google`인 경우 `google_ads`을(를) 반환합니다.
1. `paidMedia.adNetwork`에서 해당 값을 확인한 후에만 다른 네트워크에 대한 매핑을 추가하십시오.
1. 그렇지 않으면 값을 반환하지 않습니다.

고정 출력을 입력하려면 값 선택기를 열고 **[!UICONTROL 사용자 지정 문자열 값]**&#x200B;을 선택한 다음 문자열을 입력하십시오.

이러한 분류 규칙은 태깅을 기반으로 하며 유료 광고에서 방문이 발생했다는 증거가 아닙니다. 예를 들어 소스 매개 변수만 비유료 링크에 표시될 수도 있습니다. 필드를 유료 트래픽 분류기로 사용하기 전에 조건을 태깅 규칙에 맞게 조정하십시오.

### 웹 ID 파생 필드 만들기

보고 수준당 하나의 파생 필드를 만듭니다. 다음 구조는 앞에서 설명한 세 가지 태그 지정 패턴을 처리합니다.

| 규칙 | 함수 | 구성 |
|---|---|---|
| 1 | [URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse) | 페이지 URL에서 수준별 Meta 매개 변수 읽기 |
| 2 | [URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse) | 페이지 URL에서 수준별 UTM 매개 변수 읽기 |
| 3 | [URL 구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse) | 페이지 URL에서 `s_kwcid` 읽기 |
| 4 | [정규식 바꾸기](/help/data-views/derived-fields/derived-fields.md#regex-replace) | 규칙별 식을 규칙 3에 적용합니다. 출력 `$1` |
| 5 | [다음의 경우](/help/data-views/derived-fields/derived-fields.md#case-when) | 규칙 3이 설정되면 반환 규칙 4를 반환하고, 규칙 1이 설정되면 반환 규칙 1을 반환하고, 그렇지 않으면 반환 규칙 2를 반환합니다 |

다음 값을 사용하십시오.

| 파생 필드 | Meta 매개 변수 | UTM 매개 변수 | 정규 표현식 |
|---|---|---|---|
| **오후 캠페인 ID(웹)** | `campaign_id` | `utm_campaign` | `^.*!([^!]*)![^!]*$` |
| **오후 광고 그룹 ID(웹)** | `adset_id` | `utm_term` | `^.*!([^!]*)$` |
| **오후 광고 ID(웹)** | `ad_id` | `utm_content` | `^[^!]*![^!]*![^!]*!([^!]*)!.*$` |

최종 [Case When](/help/data-views/derived-fields/derived-fields.md#case-when) 규칙에서 리터럴 문자열로 입력하지 않고 값 선택기에서 이전 규칙 출력을 선택합니다.

캠페인 표현식은 두 번째에서 마지막 사이의 `s_kwcid` 값을 추출하고, 광고 그룹 표현식은 마지막 값을 추출하며, 광고 표현식은 네 번째 값을 추출합니다. 이러한 위치는 앞서 표시된 정확한 레이아웃에 따라 다릅니다.

**[!UICONTROL 최종 출력]**&#x200B;을 사용하여 결과가 유료 미디어 광고 요약의 ID와 일치하는지 확인하십시오. URL에서 다른 레이아웃을 사용하는 경우 `s_kwcid` 구문 분석 분기를 유지하지 마십시오. URL에서 UTM 매개 변수만 사용하는 경우 사용하지 않는 규칙을 생략하고 후속 규칙 참조를 적절하게 업데이트합니다.

각 파생 필드는 최대 5개의 [URL 구문 분석 규칙](/help/data-views/derived-fields/derived-fields.md#url-parse)과 1개의 [Regex 바꾸기 규칙](/help/data-views/derived-fields/derived-fields.md#regex-replace)을 지원합니다. 파생 필드당 하나의 ID를 유지합니다.

### 유료 랜딩 지표 만들기

`PM Campaign ID (Web)`을(를) 입력으로 사용하여 `Paid Media Landings (Web)`(이)라는 파생된 필드를 만듭니다.

입력 필드의 규칙이 새 필드로 확장됩니다. 이러한 규칙 다음에 캠페인 ID 출력이 설정되어 있을 때 사용자 지정 숫자 값 `1`을(를) 반환하는 [Case When](/help/data-views/derived-fields/derived-fields.md#case-when) 규칙을 추가하고 그렇지 않은 경우에는 값을 추가하지 않습니다. 결과를 지표로 추가합니다.

이 지표는 캠페인 ID를 전달하는 이벤트를 계산합니다. 이 지표는 구현에서 반복되거나 관련 없는 이벤트가 아닌 랜딩 이벤트에서 해당 ID 보유 URL을 전송하는 경우에만 랜딩을 나타냅니다.

>[!NOTE]
>
>확장된 파생 필드 규칙은 복사본입니다. ID 필드를 변경하는 경우 해당 랜딩 및 이름 필드도 검사하고 업데이트합니다. 구문 분석 규칙을 생략한 경우 규칙 5라고 가정하지 않고 실제 최종 ID 규칙을 참조합니다.

### 선택적 웹 이름 필드 추가

이름별로 보고하려면 확장된 웹 ID 규칙 다음에 [조회 규칙](/help/data-views/derived-fields/derived-fields.md#lookup)을 사용하여 다음 파생 필드를 만드십시오.

| 파생 필드 | 입력 | 조회 데이터 세트 | 일치 필드 | 반환 필드 |
|---|---|---|---|---|
| PM 캠페인 이름(웹) | PM 캠페인 ID의 최종 출력(웹) | 유료 미디어 캠페인 조회 | `paidMedia.campaignID` | `paidMedia.metadata.name` |
| PM 광고 그룹 이름(웹) | PM 광고 그룹 ID의 최종 출력(웹) | 유료 미디어 광고 그룹 조회 | `paidMedia.adGroupID` | `paidMedia.metadata.name` |
| PM 광고 이름(웹) | PM 광고 ID의 최종 출력(웹) | 유료 미디어 광고 조회 | `paidMedia.adID` | `paidMedia.metadata.name` |

조회를 적용할 필드로 최종 ID 규칙을 선택합니다. 필드를 차원으로 추가하기 전에 최종 출력 미리 보기에서 이름을 확인하십시오. 필요한 일치 필드를 사용할 수 없는 경우 대신 ID 기반 보고를 사용합니다.

이름은 텍스트로 일치합니다. 서로 다른 엔티티가 이름을 공유할 때 ID 차원을 사용합니다.

### 웹 구성 요소 추가 및 속성 구성

웹 ID 및 네트워크 파생 필드를 차원으로 추가합니다. 선택적 이름 필드를 만든 경우 추가합니다. 구성 요소 설정을 해당 그룹에 추가하는 요약 차원과 일치하도록 기본값으로 유지합니다.

데이터 보기에 필요한 웹 구성 요소가 포함되어 있는지 확인합니다.

| 구성 요소 | 유형 | 스키마 필드 |
|---|---|---|
| 페이지 URL | 치수 | `web.webPageDetails.URL` |
| 페이지 이름 | 차원 | `web.webPageDetails.name` |
| 레퍼러 URL | 차원 | `web.webReferrer.URL` |
| 이벤트 유형 | 차원 | `eventType` |
| 제품 SKU | 치수 | `productListItems.SKU` |
| 제품 이름 | 차원 | `productListItems.name` |
| 페이지 보기 횟수 | 지표 | `web.webPageDetails.pageViews.value` |
| 장바구니에 추가 | 지표 | `commerce.productListAdds.value` |
| 주문 | 지표 | `commerce.purchases.value` |
| 매출 | 지표 | `commerce.order.priceTotal` |

유료 랜딩 파생 필드를 지표로 추가한 다음 개별 주문 및 매출 지표를 구성합니다.

1. **[!UICONTROL Orders]**&#x200B;을(를) 복제하고 복사본 이름을 `Orders (Web)`로 지정하십시오. **[!UICONTROL 주문]**&#x200B;이 없는 경우 `commerce.purchases.value`을(를) 직접 추가하십시오.
1. **[!UICONTROL Revenue]**&#x200B;을(를) 복제하고 복사본 이름을 `Revenue (Web)`로 지정하십시오. **[!UICONTROL Revenue]**&#x200B;이(가) 없으면 `commerce.order.priceTotal`을(를) 직접 추가하십시오.
1. **[!UICONTROL 주문(웹)]**&#x200B;은 소수 자릿수가 0인 소수로, **[!UICONTROL 매출(웹)]**&#x200B;은 통화로 형식을 지정하십시오.
1. 두 지표 모두에 대해 **[!UICONTROL 속성]**&#x200B;을 열고 **[!UICONTROL 기본 속성 재정의]**&#x200B;를 사용하도록 설정하십시오.
1. **[!UICONTROL 마지막 터치]** 모델 및 **[!UICONTROL 세션]** 컨테이너를 선택하십시오.

기존 보고서를 유지하려면 원래 **[!UICONTROL 주문]** 및 **[!UICONTROL 매출]** 지표를 변경하지 마십시오. 표시된 기본값이 일치하는 것처럼 보이는 경우에도 이 설정에서는 재정의를 명시적으로 활성화해야 합니다.

재방문 간 전환 크레딧의 경우 대신 **[!UICONTROL 개인]** 컨테이너와 적절한 전환 확인 기간을 고려하십시오. [요약 데이터 사용 사례](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-views/summary-data)를 참조하세요.

웹 ID 차원에 지속성을 추가하는 대신 지표 속성을 사용하십시오. 랜딩 횟수로 해석되는 카운트가 부풀려지지 않도록 ID를 이후 이벤트에 유지하지 마십시오. 이렇게 하면 캠페인 행에 표시되는 이벤트가 변경됩니다.

### 요약 측 조인 차원 만들기

웹 조인에 대한 유료 미디어 광고 요약과 별도의 차원을 추가합니다.

| 구성 요소 이름 | 스키마 필드 |
|---|---|
| 광고 네트워크(가입됨) | `paidMedia.adNetwork` |
| 캠페인 ID(네트워크) | `paidMedia.campaignID` |
| 광고 그룹 ID(네트워크) | `paidMedia.adGroupID` |
| 광고 ID(네트워크) | `paidMedia.adID` |

읽기 전용의 템플릿 관리 유료 미디어 구성 요소를 편집하거나 복제하지 마십시오. 스키마 필드에서 위에 별도의 구성 요소를 만듭니다.

선택적 웹 이름 필드를 만든 경우 이러한 요약 측 조회 파생 필드도 만듭니다.

| 구성 요소 이름 | 광고 요약에서 입력 | 조회 데이터 세트 | 일치 필드 | 반환 필드 |
|---|---|---|---|---|
| 캠페인 이름(가입됨) | `paidMedia.campaignGUID` | 유료 미디어 캠페인 조회 | `paidMedia.campaignGUID` | `paidMedia.metadata.name` |
| 광고 그룹 이름(가입됨) | `paidMedia.adGroupGUID` | 유료 미디어 광고 그룹 조회 | `paidMedia.adGroupGUID` | `paidMedia.metadata.name` |
| 광고 이름(가입됨) | `paidMedia.adGUID` | 유료 미디어 광고 조회 | `paidMedia.adGUID` | `paidMedia.metadata.name` |

요약 데이터 세트의 GUID를 각 조회의 입력으로 사용합니다. 조회 데이터 세트에서 직접 가져온 차원은 요약 데이터 그룹의 요약 차원에 대한 요구 사항을 충족하지 않습니다.

### 요약 데이터 그룹 만들기

보고서에 사용할 웹 차원에서 각 그룹을 만듭니다. 해당 요약 차원을 추가하고 보고에서 추가된 멤버를 숨깁니다.

| 웹 차원: 여기에 그룹 생성 | 요약 차원: 숨겨진 멤버로 추가 |
|---|---|
| PM 네트워크(웹) | 광고 네트워크(가입됨) |
| PM 캠페인 ID(웹) | 캠페인 ID(네트워크) |
| PM 광고 그룹 ID(웹) | 광고 그룹 ID(네트워크) |
| PM 광고 ID(웹) | 광고 ID(네트워크) |
| PM 캠페인 이름(웹), 선택 사항 | 캠페인 이름(가입됨) |
| PM 광고 그룹 이름(웹), 선택 사항 | 광고 그룹 이름(가입됨) |
| PM 광고 이름(웹), 선택 사항 | 광고 이름(가입됨) |

각 행에 대해:

1. 웹 차원을 선택합니다.
1. **[!UICONTROL 요약 데이터 그룹]**&#x200B;을 열고 **[!UICONTROL 그룹화 만들기]**&#x200B;를 사용하도록 설정합니다.
1. 요약 차원을 추가합니다.
1. 추가된 요약 멤버에 대해 **[!UICONTROL 보고에서 숨기기]**&#x200B;를 활성화합니다. 웹 차원을 계속 표시합니다.
1. 소문자, 하위 문자열 및 포함/제외 규칙을 포함한 구성 요소 설정이 멤버 간에 일치하는지 확인합니다.

각 그룹은 최대 10개의 차원을 지원합니다. 다른 요약 데이터 세트의 지표를 포함하려면 해당 데이터 세트의 해당 요약 차원을 숨겨진 멤버와 동일한 그룹에 추가합니다.

>[!IMPORTANT]
>
>웹 차원을 보고 차원으로 사용하고 해당 차원에 대한 그룹을 만듭니다. 역방향 배열은 해당 웹 지표 없이 요약 지표를 표시할 수 있습니다.

데이터 보기를 저장합니다.

### 계산된 지표 만들기

Workspace에서 **[!UICONTROL 구성 요소]** > **[!UICONTROL 계산된 지표]**(으)로 이동하여 구성된 데이터 보기를 사용하여 다음 지표를 만듭니다.

| 이름 | 정의 | 포맷 |
|---|---|---|
| 착륙 비율 | 유료 미디어 랜딩(웹) / 클릭수 \| 광고 요약 | 비율 |
| 웹 전환율 | 주문(웹)/유료 미디어 랜딩(웹) | 비율 |
| 웹 ROAS | 매출(웹) / 지출 \| 광고 요약 | 소수점, 자리 수 |
| 웹 주문당 비용 | 지출 \| 광고 요약/주문(웹) | 통화 |
| 네트워크와 웹 전환 차이 | 전환 \| 광고 요약 - 주문(웹) | 소수점, 자리 수 없음 |

비율 지표를 해석하기 전에 분모가 0인 행을 검토하십시오. 네트워크와 웹 간 전환 격차는 오류를 나타내지 않습니다. 두 소스는 속성, 측정 및 보고 기간이 다를 수 있습니다.

## 보고서 작성 및 유효성 검사

1. 구성된 데이터 보기를 사용하여 Workspace 프로젝트를 만듭니다.
1. 두 소스의 데이터가 있는 날짜 범위를 선택하십시오. 유료 미디어 수집 지연 허용. 요약 데이터는 웹 사이트 이벤트를 하루 지연시킬 수 있습니다.
1. **[!UICONTROL PM 캠페인 ID(웹)]**&#x200B;을(를) 행 차원으로 사용하는 자유 형식 테이블 또는 이름 그룹을 구성한 경우 **[!UICONTROL PM 캠페인 이름(웹)]**&#x200B;을(를) 추가합니다.
1. **[!UICONTROL 노출 횟수 추가 | 광고 요약]**, **[!UICONTROL 클릭 수 | 광고 요약]**, **[!UICONTROL 지출 | 광고 요약]**, **[!UICONTROL 전환 | 광고 요약]**, **[!UICONTROL 유료 미디어 랜딩 | 광고 요약]**, **[!UICONTROL 주문(웹)]**, **[!UICONTROL 매출(웹)]** 및 계산된 지표.
1. 캠페인 행을 웹 광고 그룹 및 광고 차원으로 분류합니다. 요약 및 웹 지표가 구성된 각 수준에서 채워지는지 확인합니다.
1. **[!UICONTROL PM 네트워크(웹)]**&#x200B;를 사용하여 두 번째 테이블을 추가하여 네트워크 수준 합계와 값 없는 행을 검토하십시오.

   ![유료 미디어 및 웹 데이터 작업 영역 프로젝트](./assets/paid-media-and-web-data-workspace.png)

   ![유료 미디어 및 웹 데이터 작업 영역 프로젝트 데이터 없음](./assets/paid-media-and-web-data-workspace-no-value.png)

보고서를 공유하기 전에 다음을 확인하십시오.

* 랜딩 이벤트 ID가 유료 미디어 광고 요약 ID와 일치합니다.
* 유료 미디어 지표와 웹 지표가 동일한 행에 채워집니다.
* 주문 및 매출은 의도한 세션 또는 개인 속성을 받습니다.
* 값 없는 행을 이해할 수 있습니다. 유료 미디어 식별자 없이 일치하지 않는 요약 데이터나 웹 활동을 포함할 수 있습니다.
* 랜딩-클릭 간 차이는 컬렉션 설정, 동의 처리 및 보고 기간과 일치합니다. 보편적인 예상 일치율이 없습니다.

### 불일치 문제 해결

| 증상 | 확인 및 수정 작업 |
|---|---|
| 요약 지표가 채워지지만 모든 웹 지표는 0입니다. | 행이 웹 차원을 사용하고 해당 차원에서 그룹이 생성되었는지 확인합니다. 그런 다음 랜딩 URL에서 이름이 아닌 실제 ID를 검사합니다. |
| 웹 지표가 채워지지만 요약 수준이 비어 있음 | 수준의 요약 차원이 해당 그룹에 있고 선택한 날짜에 대해 일치하는 유료 미디어 데이터가 있는지 확인합니다. |
| 웹 행에 이름이 없습니다. | 최종 출력 미리 보기에서 조회 입력 및 일치 필드를 확인합니다. 이름 강화를 사용할 수 없는 경우 ID 그룹을 사용합니다. |
| 웹 ID에는 리터럴 또는 인코딩된 매크로가 포함되어 있습니다. | 광고 운영팀에 대상 URL을 검사하고 네트워크가 랜딩 전에 매크로를 확장하는지 확인하도록 요청하십시오. |
| Google 광고 ID가 일치하지 않음 | 실제 `s_kwcid` 레이아웃 또는 UTM 매개 변수를 검사하고 구문 분석 규칙을 업데이트합니다. |
| `facebook` 및 `meta`과(와) 같이 네트워크 값이 분할됩니다. | 네트워크 파생 필드 출력을 `paidMedia.adNetwork`과(와) 정확히 일치시킵니다. |
| ID가 별도의 행에 표시됩니다 | 그룹화된 차원 간에 설정이 일치하는지 확인하고 기본 문자열 값을 검사합니다. |
| 웹 사이트 활동이 하루 단위로 전환된 것으로 표시됨 | 데이터 보기 시간대를 UTC 요약 날짜 경계와 비교합니다. |
| 주문 또는 매출이 0이거나 캠페인에서 예기치 않게 낮음 | 지표 속성 재정의를 명시적으로 활성화하고 해당 모델, 컨테이너 및 전환 확인 설정을 확인합니다. |
| 유료 착륙이 예상 외로 높음 | 랜딩 이벤트에만 카운트된 캠페인 매개 변수가 있는지 확인합니다. 반복되는 ID 보유 이벤트도 이 지표에 기여합니다. |
| 고유 캠페인이 이름 행을 공유함 | ID 기반 보고를 사용하여 이름이 동일한 엔티티를 구별합니다. |
