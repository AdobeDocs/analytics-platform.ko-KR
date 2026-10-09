---
title: Content Analytics 유료 미디어 자동 구성
description: 데이터 세트의 자동 구성, 연결, 데이터 보기 등에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: e9274ad7899537837723e2eb9cd842c5449530ff
workflow-type: tm+mt
source-wordcount: '2309'
ht-degree: 2%
---
# 유료 미디어 자동 구성

Content Analytics에서 유료 미디어 채널을 활성화하고 구성을 저장하면 Adobe에서 유료 미디어 데이터 세트에 대한 보고 구성으로 선택한 연결 및 데이터 보기를 업데이트합니다. 기본 차원, 지표, 조회 논리 또는 요약 데이터 그룹을 직접 다시 만들 필요는 없습니다.

다음과 같은 세 가지 객체 레이어가 만들어집니다.

| 개체 | 다음 포함 | 용도 |
| --- | --- | --- |
| 요약 데이터 세트 | 지원되는 경우 별도의 인구 통계/지리 분류가 있는 광고, 경험 배치 또는 에셋 수준의 Advertising 네트워크 성능 데이터입니다. | 게재, 클릭 수, 지출 및 광고 네트워크에서 보고한 결과를 측정할 수 있습니다. |
| 메타데이터 및 속성 조회 데이터 세트 | 계정, 캠페인, 광고 그룹, 광고, 경험 및 에셋 세부 정보, Content Analytics 광고 속성. | 식별자를 사용하는 대신 인식 가능한 이름, 창의적인 세부 사항, 썸네일 및 콘텐츠 속성을 사용하여 보고할 수 있습니다. |
| 데이터 보기 구성 요소 및 구성 | 차원, 지표, 계산된 지표, 파생 필드 및 요약 데이터 그룹. | 이러한 데이터 세트 간의 관계를 수동으로 다시 작성하지 않고도 Workspace 분석을 작성할 수 있습니다. |

유료 미디어를 활성화해도 유료 미디어 데이터가 사이트의 주문, 예약 또는 매출에 자동으로 연결되지 않습니다. 경험 이벤트 데이터와 유료 미디어 데이터 간의 상관 관계를 사용하려면 고객별 추적 키 매핑 및 보고 구성이 필요합니다.

## 요약 데이터 세트

아래 그림은 Content Analytics에서 하나 이상의 광고 네트워크에 대해 유료 미디어 채널을 활성화하면 요약 데이터 세트가 생성되는 방식을 보여 줍니다. 사용 가능한 광고 네트워크의 관련 API를 사용하여 경험, 에셋 및 광고 데이터를 다운로드하고 잠재적으로 6개의 요약 데이터 세트로 변환합니다.

![요약 데이터 세트의 유료 미디어 생성](/help/content-analytics/assets/paid-media-generation-of-datasets.png)

특정 광고 네트워크는 만들 요약 데이터 세트를 결정합니다. 소스 커넥터를 구성한 모든 광고 네트워크가 가능한 6개의 요약 데이터 세트를 모두 생성하는 것은 아닙니다. 다음 정보가 포함된 요약 데이터 세트에 대한 개요는 아래 표를 참조하십시오.

* 요약 데이터 세트 이름, 이벤트 유형 및 구성 요소 접미사
* 엔티티
* 분류
* 다음 네트워크에 대해 ![확인 표시](/help/assets/icons2/Checkmark.svg)되는 데이터 세트:
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) Google
  * ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) Pinterest
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * ![TikTok](/help/assets/icons2/TikTok.svg) TikTok

    >[!AVAILABILITY]
    >
    >Pinterest, Snapchat 및 TikTok은 릴리스의 제한된 테스트 단계에 있으며 사용 중인 환경에서는 아직 사용할 수 없습니다. 기능이 일반적으로 제공되면 이 메모는 제거됩니다. Customer Journey Analytics 릴리스 프로세스에 대한 정보는 [Customer Journey Analytics 기능 릴리스](/help/release-notes/releases.md)를 참조하십시오.
    >


* 요약 데이터 세트의 각 행이 나타내는 사항.

| 요약 데이터 집합<br/>이벤트 유형<br/>구성 요소 접미사 | 엔터티<br/>분류 | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | 각 행은 다음을 나타냅니다 |
|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | 광고<br/>없음 | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | 인구 통계학적 또는 지리적 분류가 없는 광고의 일일 성과. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Ad<br/>나이, 성별 | ![체크 표시](/help/assets/icons2/Checkmark.svg) | | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | 광고의 일일 성과<br/>연령과 성별에 따라 분류합니다. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Ad<br/>국가, 지역 | ![체크 표시](/help/assets/icons2/Checkmark.svg) | | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | 광고의 일일 성과<br/>를 국가 및 지역별로 분류했습니다. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | 경험<br>플랫폼, 위치 | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | 광고 크리에이티브 경험과 <br/>연계된 <br/>일별 성과를 플랫폼 및 위치별로 분류합니다. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | 자산<br/>없음 | ![체크 표시](/help/assets/icons2/Checkmark.svg) | ![체크 표시](/help/assets/icons2/Checkmark.svg) | | | ![체크 표시](/help/assets/icons2/Checkmark.svg) | 인구 통계학적 또는 지리적 분류 없이 광고/캠페인 컨텍스트에서 <br/>일별 자산 수준 성과<br/>입니다. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | 자산<br/>연령, 성별 | ![체크 표시](/help/assets/icons2/Checkmark.svg) | | | | | 광고/캠페인 컨텍스트에서 <br/>일별 자산 수준 성과<br/>연령과 성별에 따라 분류합니다. |


이 표에서는 데이터 세트 범위를 설명하지만, 특정 네트워크가 모든 지표 또는 메타데이터 필드를 입력한다는 보장이 아닙니다. 분석에 필요한 필드를 확인합니다. 사용할 수 없는 필드 또는 지원되지 않는 분류는 필드에 대해 측정된 0 값과 동일하지 않습니다.

별도의 조회 데이터 세트는 계정, 캠페인, 광고 그룹, 광고, 경험 및 에셋을 설명합니다. 엔터티 GUID를 사용하여 이름과 메타데이터를 제공합니다. 요약 데이터 세트와 6개의 조회 데이터 세트 사이에는 일대일 연결이 없습니다.

요약 데이터 그룹화는 동일한 차원을 통합합니다. 그룹화하면 6개의 성능 지표 합계가 집계되지 않습니다.

## 구성 요소

Content Analytics 유료 미디어 채널도 활성화되면 여러 데이터 보기 구성 요소를 생성합니다. 이러한 구성 요소에는 유사한 이름의 구성 요소를 서로 구분하기 위한 구성 요소 접미사가 제공됩니다.

### 지표

광고 네트워크마다 서로 다른 성능 분류를 반환합니다. Content Analytics은 지표의 모든 버전을 호환성으로 처리하는 대신 이러한 구분을 유지합니다.

예:

| 구성 요소 | 의미 | 적절한 시작 분석 |
| --- | --- | --- |
| 클릭 수 \| 광고 요약 | 광고의 분류 없음 수준에서 보고된 클릭 수 | 캠페인 또는 광고 성과 |
| 클릭 수 \| 자산 요약 | 자산 수준에서 보고된 클릭 수 | Creative-asset 성과 |
| 클릭 수 \| 광고 지역 | 광고 지리 보고서 클릭 수 | 국가 또는 지역별 성과 |
| 클릭 수 \| 경험 배치 | 경험 배치 보고서의 클릭 수 | 배치별 Creative 성능 |

각 클릭 지표 구성 요소는 다른 보고 컨텍스트에 사용됩니다. 이러한 지표 구성 요소를 총계로 합할 수 없습니다. 동일한 기본 광고 활동을 둘 이상의 요약 데이터 세트에 나타낼 수 있습니다.

### 차원

각 요약 데이터 세트에는 ID 및 GUID가 포함되어 있습니다. ID는 광고 네트워크에서 제공하는 ID(계정, 캠페인, 광고 그룹, 광고, 경험 및 자산)이며 광고 네트워크 데이터에서 고유한 **내부**&#x200B;입니다. GUID는 Adobe 제공 ID(계정, 캠페인, 광고 그룹, 광고, 경험 및 자산)이며 **광고 네트워크에서 고유한**&#x200B;입니다. ID 및 GUID는 해당 이름 및 메타데이터를 조회하는 데 사용됩니다.

### 파생 필드

파생 필드는 자동 보고 구성의 일부입니다. 파생 필드는 식별자를 이름과 메타데이터로 번역하고 크리에이티브 속성을 노출하며 보고 소스에서 사용되는 동등한 차원을 지원합니다. 추가적인 광고 활동을 만들거나 웹 사이트 전환을 자동으로 기여하지 않습니다.

분석 내의 지표 및 해당 분류에서 지원하는 차원에 대해 동일한 분류를 사용합니다. 인구 통계학적 및 지리적 합계는 광고 네트워크의 분류 안 함 합계와 반드시 같지 않으며 수집 실패를 의미하지 않습니다.

## 보고 및 분석

Content Analytics 유료 미디어 설정 및 수집을 완료하면 보고 및 분석으로 시작할 수 있습니다. 몇 가지 예는 아래 표를 참조하십시오. 사용 가능한 경우 표준 그룹 차원을 사용하고 일치하는 보고 수준에서 지표를 선택합니다.

| 비즈니스 질문 | 시작 수준 | 행 및 분류 | 시작 지표 | 중요 경계 |
| --- | --- | --- | --- | --- |
| 내 캠페인 및 광고의 성과는 어떻습니까? | 광고 요약 | 캠페인 이름, 광고 그룹 이름, 광고 이름(선택 사항), 광고 네트워크 및 계정 이름 | 노출 횟수 \| 광고 요약, 클릭 수 \| 광고 요약, 지출 \| 광고 요약, 일치하는 CTR 및 CPC | 게재/지출 합계에 한 수준을 사용합니다. 계정을 결합하기 전에 통화를 검증합니다. |
| 어떤 크리에이티브 에셋이 가장 높은 반응을 얻습니까? | 자산 요약 | 자산 이름(유료 미디어), 자산 ID, 광고 네트워크(선택 사항) | 노출 횟수 \| 에셋 요약, 클릭 수 \| 에셋 요약, 클릭스루 비율 \| 에셋 요약 | 이는 나중에 현장에서 전환할 수 있는 증거가 아니라 네트워크에서 보고하는 자산 성능입니다. |
| 성능과 연관된 이미지 특성은 무엇입니까? | 자산 요약 | 자산 태그, 자산 객체, 자산 사용자 범주, 자산 장면 또는 기타 사용 가능한 자산 속성 | 자산 요약 노출 횟수, 클릭 수 및 CTR | 속성 추출을 사용할 수 있어야 합니다. 다중 값 속성 범주가 겹칠 수 있습니다. |
| 유료 성능과 관련된 메시징 특성은 무엇입니까? | 경험 배치 | 경험 키워드, 경험 톤, 경험 설득 전략 또는 기타 사용 가능한 경험 속성(플랫폼 및 배치 선택 사항) | 노출 횟수 \| 경험 배치, 클릭 수 \| 경험 배치, 일치 CTR | 채워진 경험 속성이 필요합니다. 결과는 배치별로 다르며 인과적 영향이 아닌 연관성을 설명합니다. |
| 성과가 가장 좋은 배치는 무엇입니까? | 경험 배치 | 경험 이름, 플랫폼, 배치 | 노출 횟수 \| 경험 배치, 클릭 수 \| 경험 배치, 일치 CTR | 배치 정의 및 사용 가능한 값은 광고 네트워크별로 다릅니다 |
| Meta 및 Google 광고/에셋/경험은 어떻게 비교합니까? | 질문에 대해 선택된 광고 요약, 에셋 요약 또는 경험 배치 | 적절한 캠페인, 에셋 또는 경험 차원이 있는 광고 네트워크 | 두 네트워크에 대한 동일한 수준 및 지표 정의 | 두 네트워크에서 채운 필드만 비교합니다. Google은 이 모델의 세 가지 인구 통계/지리 요약을 채우지 않습니다. |

이러한 보고서는 크리에이티브 속성과 성과 간의 연관성을 보여줄 수 있으며, 속성이 결과를 초래했음을 증명할 수는 없습니다.

호환되지 않는 조합 방지: 광고 요약 지표가 있는 에셋 이름(유료 미디어)은 에셋 보고서를 대체하지 않습니다. 자산 분석에는 자산 요약 지표를 사용하고 지역 분석에는 광고 지역 지표를 사용합니다. 호환되지 않는 페어링에서 빈 셀이나 0이 있는 셀은 활동이 없음을 증명하는 것으로 해석해서는 안 됩니다.

### 예

다음은 유료 미디어 성과를 보고하고 분석하는 방법과 Content Analytics 경험 및 에셋 데이터를 유료 미디어 데이터와 결합하는 방법에 대한 예입니다.

#### 광고 캠페인 성과

광고 수준에서 캠페인 성과를 보고하려고 합니다. Analysis Workspace에서 캠페인 이름 을 차원(행)으로 사용하고 아래 표에 설명된 대로 지표를 사용합니다. 각 지표에는 동일한 구성 요소 접미사가 있습니다.

| 지표 | 보고 수준 |
| --- | --- |
| 노출 횟수 | 광고 요약 |
| 클릭 수 | 광고 요약 |
| 지출 | 광고 요약 |
| 클릭스루 비율 | 광고 요약 |
| 클릭당 비용 | 광고 요약 |

선택적으로 캠페인 이름을 광고 이름으로 분류하지만 5개의 열을 모두 광고 요약 수준으로 유지합니다.

개별 에셋을 조사하려면 에셋 이름(유료 미디어)과 일치하는 에셋 요약 열이 있는 별도의 테이블을 사용합니다. 두 표의 합계를 함께 추가하지 마십시오.

#### 최상의 성능 광고 식별

Meta 광고의 성과가 가장 좋은 위치를 알고 싶으십니까?

조사하려면 지역 및 인구 분포에 대해 추가 분류를 사용합니다. 캠페인 이름 또는 광고 이름 을 차원으로 사용하고 아래 표에 설명된 대로 지표를 사용합니다. 각 지표에는 동일한 구성 요소 접미사가 있습니다.

| 지표 | 보고 수준 |
| --- | --- |
| 노출 횟수 | 광고 지역 |
| 클릭 수 | 광고 지역 |
| 지출 | 광고 요약 |
| 클릭스루 비율 | 광고 지역 |
| 클릭당 비용 | 광고 요약 |


#### 유료 미디어 데이터를 경험 이벤트 데이터로 참여

캠페인 및 광고가 웹 사이트 참여, 전환 및 매출과 어떻게 관련되는지를 이해하려면 온사이트 행동 데이터와 함께 유료 미디어 성능에 참여하십시오. 예를 들어 광고 네트워크 클릭 수 및 비용을 동일한 캠페인의 방문으로 인한 주문과 비교합니다.

이 보고를 구성하려면 유료 미디어 요약 데이터 세트와 온사이트 이벤트 데이터 세트를 동일한 Customer Journey Analytics 연결에 포함하십시오. 랜딩 페이지 URL 매개 변수 또는 기존 이벤트 필드에서 안정적인 캠페인, 광고 또는 지원되는 자산 식별자를 캡처합니다. 필요에 따라 파생 필드를 사용하여 해당 값을 구문 분석하고 해당 유료 미디어 식별자에 매핑하여 필요한 네트워크 및 계정 컨텍스트를 보존합니다. 식별자를 문자열로 유지합니다. 일치하는 이벤트 및 요약 차원을 연결하려면 데이터 보기에서 요약 데이터 그룹을 구성합니다. 유료 미디어 채널을 활성화해도 이 구현별 URL 추적 및 매핑이 자동으로 구성되지 않습니다.


| 추적 옵션 | 고려 사항 |
|---|---|
| Meta 광고 | 지원되는 경우 `campaign.id`, `adset.id` 및 `ad.id`과(와) 같은 동적 식별자를 사용하여 대상 URL 매개 변수를 구성합니다. 웹 사이트에서 해결된 값을 캡처합니다. 커넥터를 활성화해도 이러한 매개 변수가 광고 URL에 자동으로 추가되지는 않습니다. |
| Google Ads | |
| 개별 자산 | 다운스트림 결과에 대한 에셋 수준 보고에는 클릭과 연결된 특정 에셋에 매핑되는 캡처된 식별자가 필요합니다. 사용자 지정 URL 매개 변수는 광고 형식에서 자산별 추적을 허용하는 경우 이를 지원할 수 있습니다. 광고 식별자만으로는 광고 내의 여러 에셋을 구분할 수 없으며 전체 다중 에셋 광고에 적용된 하나의 정적 에셋 매개 변수는 클릭과 연결된 에셋을 식별하지 않습니다. |

Analysis Workspace에서 캠페인 또는 광고 비교에 **[!UICONTROL 광고 요약]** 지표를 사용하고 지원되는 자산 비교에 **[!UICONTROL 자산 요약]** 지표를 사용합니다. 보고 질문을 반영하는 온사이트 전환 지표에 속성 모델 및 전환 확인 기간 을 적용합니다.

다음 사항에 유의하십시오.

* 유료 미디어 데이터는 개인 ID가 없는 요약 데이터로 집계됩니다. 온사이트 비헤이비어는 이벤트 데이터입니다.
* 그룹화 일치 차원은 이러한 소스에서 보고를 지원하지만 개별 광고 네트워크 전환을 웹 사이트 전환과 일치시키거나 개인 수준 결합을 수행하지는 않습니다.
* 비교는 인과적 상승도가 아닌 연관성을 보여준다.
* 전환 정의, 속성 창, 뷰스루 또는 모델 전환, 동의 및 보고 날짜 또는 시간대로 인해 결과가 다를 수 있습니다.
* 추적 매개 변수가 여러 채널에서 재사용되는 경우 캠페인 태그가 지정된 방문의 소스를 확인합니다.


#### 캠페인 성과를 현장 주문과 비교

랜딩 페이지 URL에는 여러 추적 매개 변수가 포함될 수 있습니다. 이 예제에서는 캠페인 지출과 웹 사이트 주문을 비교하는 데 `utm_id`의 캠페인 ID를 사용합니다.

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215

이 비교에 사용되는 매개 변수: `utm_id=120218706543980215`. 다른 매개 변수는 소스, 미디어 및 캠페인 레이블을 설명하지만 이 예에서 사용되는 일치 필드로 사용되지 않습니다.

URL이 웹 사이트 이벤트 데이터에 캡처되고 웹 사이트 이벤트 데이터 세트와 유료 미디어 데이터 세트가 모두 동일한 Customer Journey Analytics 연결에 포함된 경우:

1. 캠페인을 식별합니다. 파생 필드를 사용하여 URL에서 `utm_id`을(를) 읽고 해당 값을 유료 미디어 데이터의 해당 캠페인 식별자에 매핑합니다.
1. 일치하는 차원을 그룹화합니다. 데이터 보기에서 유료 캠페인 차원의 `Summary Data Group`에 웹 사이트 캠페인 차원을 추가하여 기존 구성원을 유지합니다.
1. 지출과 주문을 비교합니다. Analysis Workspace에서 그룹화된 캠페인 차원을 자유 형식 테이블의 행으로 사용합니다. `Ad Summary` 지출 및 웹 사이트 `Orders`을(를) 열로 추가합니다. `Orders`에 대한 속성 모델 및 전환 확인 기간을 설정합니다.


자유 형식 테이블은 각 캠페인에 속하는 웹 사이트 주문과 함께 광고 네트워크 소비를 보여줍니다. 광고 지출이 유사한 두 캠페인의 다운스트림 웹 사이트 작업 수가 다릅니다. 이 비교를 사용하여 광고 지표만으로 성능을 평가하는 대신 추가 조사 또는 테스트를 위한 캠페인 및 랜딩 페이지 경험을 식별합니다.

예제에서는 캠페인 ID를 사용하지만, 일치하는 값을 캡처할 수 있을 때 동일한 접근 방식으로 광고 그룹, 광고 또는 자산 식별자를 사용할 수 있습니다. **[!UICONTROL 에셋 전경색]**&#x200B;과 같은 Content Analytics 특성을 사용하면 크리에이티브 특성과 유료 미디어 성능을 비교할 수 있습니다. 두 소스 모두에 구성된 자산별 추적 및 일치 속성 차원을 사용하여 해당 비교를 속성 웹 사이트 주문으로 확장하고 결과를 사용하여 크리에이티브 테스트를 안내할 수 있습니다.

#### 에셋 성능과 웹 데이터 결합

유료 미디어 투자와 관련된 자산 성과를 보고하고 분석하려면 광고 네트워크 유료 미디어 구성에 특정 자산 UTM 매개 변수를 추가하는 것이 좋습니다. 예를 들어, s`ite_source_name`, `campaign.id`, `adset.id` 또는 `placement`과(와) 같은 표준 동적 매개 변수 외에 `aca_asset_id=999999`과(와) 같은 정적 사용자 지정 매개 변수를 추가합니다.

이 사용자 지정 매개 변수는 랜딩 페이지 URL에 추가됩니다. 예: https://www.example.com/home.html?utm_content=120241705099850539%2Caca_asset_id%3D9999999%2Caca_placement%3DFacebook_Desktop_Feed&aca_id_2=8888888&utm_medium=paid&utm_source=fb&utm_id=120241705099830539&utm_term=120241705099840539&utm_campaign=120241705099830539

이제 페이지의 에셋과 유료 미디어 데이터 간의 관계가 유지됩니다. Analysis Workspace의 해당 관계를 사용하여 Content Analytics 에셋 메타데이터(예: **[!UICONTROL 에셋 전경색]**)가 유료 미디어 캠페인 성공에 어떻게 기여하는지 확인하십시오.


<!--

Do we need to include the tables from the Wiki?

## Reference

The following table lists paid media fields, their XDM paths, provisioned components, and reporting visibility.

+++ Paid media fields

| Field name | XDM path | ACA Paid Media component | Provisioning status | Reporting visibility |
| --- | --- | --- | --- | --- |
| Ad Network | `paidMedia.adNetwork` | Ad Network (dimension) | existing | visible through shared grouping: Ad Network |
| Channel | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | existing | visible through shared grouping: Content Channel |
| Account GUID | `paidMedia.accountGUID` | Account GUID (dimension) | existing | visible through shared grouping: Account GUID |
| Campaign GUID | `paidMedia.campaignGUID` | Campaign GUID (dimension) | existing | visible through shared grouping: Campaign GUID |
| Ad Group GUID | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | existing | visible through shared grouping: AdGroup GUID |
| Ad GUID | `paidMedia.adGUID` | Ad GUID (dimension) | existing | visible through shared grouping: Ad GUID |
| Experience GUID | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | existing | visible through shared grouping: Experience Id |
| Asset GUID | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | existing | visible through shared grouping: Asset Id |
| Name | `paidMedia.metadata.name` | Ad Name (derived field)<br/>Ad Name (shared dimension)<br/>AdGroup Name (derived field)<br/>AdGroup Name (shared dimension)<br/>Asset Name (Paid Media) (derived field)<br/>Asset Name (Paid Media) (shared dimension)<br/>Campaign Name (derived field)<br/>Campaign Name (shared dimension)<br/>Experience Name (derived field)<br/>Experience Name (shared dimension) | existing | visible through shared grouping: Ad Name, AdGroup Name, Asset Name (Paid Media), Campaign Name, Experience Name |
| Status | `paidMedia.metadata.status` | Ad Status (derived field)<br/>Ad Status (shared dimension)<br/>Ad Group Status (derived field)<br/>Ad Group Status (shared dimension)<br/>Campaign Status (derived field)<br/>Campaign Status (shared dimension) | curated net-new | visible through shared grouping: Ad Status, Ad Group Status, Campaign Status |
| Serving Status | `paidMedia.metadata.servingStatus` | | excluded | missing provisioned component |
| Updated Time | `paidMedia.metadata.updatedTime` | | excluded | missing provisioned component |
| Account Name | `paidMedia.accountDetails.accountName` | Account Name (derived field)<br/>Account Name (shared dimension) | existing | visible through shared grouping: Account Name |
| Currency | `paidMedia.accountDetails.currency` | Account Currency (derived field)<br/>Account Currency (shared dimension) | curated net-new | visible through shared grouping: Account Currency |
| Timezone | `paidMedia.accountDetails.timezone` | Account Timezone (derived field)<br/>Account Timezone (shared dimension) | curated net-new | visible through shared grouping: Account Timezone |
| Account Type | `paidMedia.accountDetails.accountType` | Account Type (derived field)<br/>Account Type (shared dimension) | curated net-new | visible through shared grouping: Account Type |
| Business Name | `paidMedia.accountDetails.businessName` | Account Business Name (derived field)<br/>Account Business Name (shared dimension) | curated net-new | visible through shared grouping: Account Business Name |
| Campaign Type | `paidMedia.campaignDetails.campaignType` | Campaign Type (derived field)<br/>Campaign Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Type |
| Objective | `paidMedia.campaignDetails.objective` | Campaign Objective (derived field)<br/>Campaign Objective (shared dimension) | curated net-new | visible through shared grouping: Campaign Objective |
| Is Automated Campaign | `paidMedia.campaignDetails.isAutomatedCampaign` | Campaign Is Automated \| Ad Summary (derived field) | curated net-new | hidden |
| Bid Strategy | `paidMedia.campaignDetails.budgetSettings.bidStrategy` | Campaign Bid Strategy (derived field)<br/>Campaign Bid Strategy (shared dimension) | curated net-new | visible through shared grouping: Campaign Bid Strategy |
| Budget Type | `paidMedia.campaignDetails.budgetSettings.budgetType` | Campaign Budget Type (derived field)<br/>Campaign Budget Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Budget Type |
| Daily Budget | `paidMedia.campaignDetails.budgetSettings.dailyBudget` | Campaign Daily Budget (derived field)<br/>Campaign Daily Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Daily Budget |
| Lifetime Budget | `paidMedia.campaignDetails.budgetSettings.lifetimeBudget` | Campaign Lifetime Budget (derived field)<br/>Campaign Lifetime Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Lifetime Budget |
| Campaign Budget Optimization | `paidMedia.campaignDetails.budgetSettings.isCampaignBudgetOptimization` | Campaign Budget Optimization \| Ad Summary (derived field) | curated net-new | hidden |
| Catalog ID | `paidMedia.campaignDetails.catalogId` | Campaign Catalog ID \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.campaignDetails.startTime` | Campaign Start Time (derived field)<br/>Campaign Start Time (shared dimension) | curated net-new | visible through shared grouping: Campaign Start Time |
| End Time | `paidMedia.campaignDetails.endTime` | Campaign End Time (derived field)<br/>Campaign End Time (shared dimension) | curated net-new | visible through shared grouping: Campaign End Time |
| Ad Group Type | `paidMedia.adGroupDetails.adGroupType` | Ad Group Type (derived field)<br/>Ad Group Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Type |
| Bid Strategy Type | `paidMedia.adGroupDetails.budgetSettings.bidStrategyType` | Ad Group Bid Strategy Type (derived field)<br/>Ad Group Bid Strategy Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Bid Strategy Type |
| Optimization Goal | `paidMedia.adGroupDetails.optimizationSettings.optimizationGoal` | Ad Group Optimization Goal (derived field)<br/>Ad Group Optimization Goal (shared dimension) | curated net-new | visible through shared grouping: Ad Group Optimization Goal |
| Delivery Status | `paidMedia.adGroupDetails.deliverySettings.deliveryStatus` | Ad Group Delivery Status \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.adGroupDetails.startTime` | Ad Group Start Time (derived field)<br/>Ad Group Start Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group Start Time |
| End Time | `paidMedia.adGroupDetails.endTime` | Ad Group End Time (derived field)<br/>Ad Group End Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group End Time |
| Ad Type | `paidMedia.adDetails.adType` | Ad Type (derived field)<br/>Ad Type (shared dimension) | curated net-new | visible through shared grouping: Ad Type |
| Delivery Status | `paidMedia.adDetails.deliveryStatus` | Ad Delivery Status (derived field)<br/>Ad Delivery Status (shared dimension) | curated net-new | visible through shared grouping: Ad Delivery Status |
| Review Status | `paidMedia.adDetails.reviewStatus` | Ad Review Status (derived field)<br/>Ad Review Status (shared dimension) | curated net-new | visible through shared grouping: Ad Review Status |
| Creative Type | `paidMedia.adDetails.creative.paidMediaCreative.creativeType` | Ad Creative Type (derived field)<br/>Ad Creative Type (shared dimension) | curated net-new | visible through shared grouping: Ad Creative Type |
| Title | `paidMedia.adDetails.creative.paidMediaCreative.title` | Ad Title (derived field)<br/>Ad Title (shared dimension) | curated net-new | visible through shared grouping: Ad Title |
| Call to Action | `paidMedia.adDetails.creative.paidMediaCreative.callToAction` | Ad Call to Action (derived field)<br/>Ad Call to Action (shared dimension) | curated net-new | visible through shared grouping: Ad Call to Action |
| Destination URL | `paidMedia.adDetails.creative.paidMediaCreative.destinationURL` | Ad Destination URL (derived field)<br/>Ad Destination URL (shared dimension) | curated net-new | visible through shared grouping: Ad Destination URL |
| Display URL | `paidMedia.adDetails.creative.paidMediaCreative.displayURL` | Ad Display URL (derived field)<br/>Ad Display URL (shared dimension) | curated net-new | visible through shared grouping: Ad Display URL |
| Experience Type | `paidMedia.experienceDetails.experienceType` | Experience Type (derived field)<br/>Experience Type (shared dimension) | curated net-new | visible through shared grouping: Experience Type |
| Landing Page URL | `paidMedia.experienceDetails.landingPageURL` | Experience Landing Page URL (derived field)<br/>Experience Landing Page URL (shared dimension) | curated net-new | visible through shared grouping: Experience Landing Page URL |
| Call To Action | `paidMedia.experienceDetails.callToAction` | Experience Call to Action (derived field)<br/>Experience Call to Action (shared dimension) | curated net-new | visible through shared grouping: Experience Call to Action |
| Card Count | `paidMedia.experienceDetails.carouselProperties.cardCount` | Experience Card Count \| Ad Summary (derived field) | curated net-new | hidden |
| Asset Type | `paidMedia.assetDetails.assetType` | Asset Type (derived field)<br/>Asset Type (shared dimension) | curated net-new | visible through shared grouping: Asset Type |
| Permalink URL | `paidMedia.assetDetails.mediaProperties.permalinkURL` | Asset Permalink URL \| Ad Summary (derived field) | curated net-new | hidden |
| Width | `paidMedia.assetDetails.dimensions.width` | Asset Width (derived field)<br/>Asset Width (shared dimension) | curated net-new | visible through shared grouping: Asset Width |
| Height | `paidMedia.assetDetails.dimensions.height` | Asset Height (derived field)<br/>Asset Height (shared dimension) | curated net-new | visible through shared grouping: Asset Height |
| Aspect Ratio | `paidMedia.assetDetails.dimensions.aspectRatio` | Asset Aspect Ratio (derived field)<br/>Asset Aspect Ratio (shared dimension) | curated net-new | visible through shared grouping: Asset Aspect Ratio |
| Orientation | `paidMedia.assetDetails.dimensions.orientation` | Asset Orientation \| Ad Summary (derived field)<br/>Asset Orientation (shared dimension) | curated net-new | visible through shared grouping: Asset Orientation |
| MIME Type | `paidMedia.assetDetails.fileProperties.mimeType` | Asset MIME Type \| Ad Summary (derived field) | curated net-new | hidden |
| Impressions | `paidMedia.metrics.impressions` | Impressions \| Ad Summary (metric) | existing | visible |
| Clicks | `paidMedia.metrics.clicks` | Clicks \| Ad Summary (metric) | existing | visible |
| Spend | `paidMedia.metrics.spend` | Spend \| Ad Summary (metric) | existing | visible |
| Reach | `paidMedia.metrics.reach` | Reach \| Ad Summary (metric) | curated net-new | visible |
| Conversions | `paidMedia.metrics.conversions` | Conversions \| Ad Summary (metric) | curated net-new | visible |
| Conversion Value | `paidMedia.metrics.conversionValue` | Conversion Value \| Ad Summary (metric) | curated net-new | visible |
| Video Views | `paidMedia.metrics.videoViews` | Video Views \| Ad Summary (metric) | curated net-new | visible |
| Engagements | `paidMedia.metrics.engagements` | Engagements \| Ad Summary (metric) | curated net-new | visible |
| Post-Click Conversions | `paidMedia.conversionMetrics.postClickConversions` | Post-Click Conversions \| Ad Summary (metric) | curated net-new | visible |
| Post-View Conversions | `paidMedia.conversionMetrics.postViewConversions` | Post-View Conversions \| Ad Summary (metric) | curated net-new | visible |
| Purchases | `paidMedia.conversionMetrics.conversionsByType.purchases` | Purchases \| Ad Summary (metric) | curated net-new | visible |
| Add to Cart | `paidMedia.conversionMetrics.conversionsByType.addToCart` | Add to Cart \| Ad Summary (metric) | curated net-new | visible |
| Leads | `paidMedia.conversionMetrics.conversionsByType.leads` | Leads \| Ad Summary (metric) | curated net-new | visible |
| Registrations | `paidMedia.conversionMetrics.conversionsByType.registrations` | Registrations \| Ad Summary (metric) | curated net-new | visible |
| Downloads | `paidMedia.conversionMetrics.conversionsByType.downloads` | Downloads \| Ad Summary (metric) | curated net-new | visible |
| Subscriptions | `paidMedia.conversionMetrics.conversionsByType.subscriptions` | Subscriptions \| Ad Summary (metric) | curated net-new | visible |
| Landing Page View | `paidMedia.conversionMetrics.conversionsByType.landingPageView` | Landing Page Views \| Ad Summary (metric) | curated net-new | visible |
| Total Order Value | `paidMedia.conversionMetrics.totalOrderValue` | Total Order Value \| Ad Summary (metric) | curated net-new | visible |
| Video Plays | `paidMedia.videoMetrics.videoPlays` | Video Plays \| Ad Summary (metric) | curated net-new | visible |
| Video Completions | `paidMedia.videoMetrics.videoCompletions` | Video Completions \| Ad Summary (metric) | curated net-new | visible |
| Link Clicks | `paidMedia.extendedMetrics.linkClicks` | Link Clicks \| Ad Summary (metric) | curated net-new | visible |
| Outbound Clicks | `paidMedia.extendedMetrics.outboundClicks` | Outbound Clicks \| Ad Summary (metric) | curated net-new | visible |
| App Installs | `paidMedia.extendedMetrics.appInstalls` | App Installs \| Ad Summary (metric) | curated net-new | visible |
| Lead Submissions | `paidMedia.extendedMetrics.leadSubmissions` | Lead Submissions \| Ad Summary (metric) | curated net-new | visible |
| Device Type | `paidMedia.dimensionalBreakdowns.deviceType` | | excluded | removed in source range |
| Placement | `paidMedia.dimensionalBreakdowns.placement` | Placement (dimension) | curated net-new | visible through shared grouping: Placement |
| Platform | `paidMedia.dimensionalBreakdowns.platform` | Platform (dimension) | curated net-new | visible through shared grouping: Platform |
| Country | `paidMedia.dimensionalBreakdowns.country` | Country (dimension) | curated net-new | visible through shared grouping: Country |
| Region | `paidMedia.dimensionalBreakdowns.region` | Region (dimension) | curated net-new | visible through shared grouping: Region |
| Other connector-populated fields | See field tables | No named component | excluded | not surfaced |

+++

### Identifiers

| Field name | Description | XDM path | ACA Paid Media component | ACA context label | Meta | Google Ads | Pinterest | Snapchat | TikTok |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Record ID | *Unique record URI, inherited from data/record.* | `@id` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (pinterest:&lt;entity&gt;: source-derived composite record ID; GUIDs use pinterest_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (snapchat:&lt;entity&gt;: source-derived composite record ID; GUIDs use snapchat_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (tiktok:&lt;entity&gt;: source-derived composite record ID; GUIDs use tiktok_; summary IDs omit dimension values; writer emits _id.) |
| Entity Type | The type of paid media entity | `entityType` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) |
| Ad Network | The advertising platform/network | `paidMedia.adNetwork` | Ad Network (dimension) | Ad Network | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads`) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Network | Alias of adNetwork for migration from GenStudio templates | `paidMedia.network` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Channel | Content channel indicating the source of the data (e.g., Web, Mobile, PaidMedia). Used as a reporting dimension for cross-channel breakdowns. | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | Content Channel (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) |
| Hierarchy Path | Full hierarchical path showing parent-child relationships (e.g., account_id/campaign_id/adgroup_id/ad_id) | `paidMedia.hierarchyPath` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account ID | Unique identifier for the ad account within the network | `paidMedia.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Unique identifier for the ad account across all networks | `paidMedia.accountGUID` | Account GUID (dimension) | Account Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign ID | Unique identifier for the campaign within the network | `paidMedia.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign GUID | Unique identifier for the campaign across all networks | `paidMedia.campaignGUID` | Campaign GUID (dimension) | Campaign Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group ID | Unique identifier for the ad group/ad set/ad squad within the network | `paidMedia.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group GUID | Unique identifier for the ad group/ad set/ad squad across all networks | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | AdGroup Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad ID | Unique identifier for the individual ad within the network | `paidMedia.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad GUID | Unique identifier for the individual ad across all networks | `paidMedia.adGUID` | Ad GUID (dimension) | Ad Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Experience ID | Unique identifier for creative experience (multi-asset compositions) within the network | `paidMedia.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Ad ID on Experience lookup and summaries; null on Ad lookup; asset reverse join recovers ad ID when metadata matches.) |
| Experience GUID | Unique identifier for creative experience (multi-asset compositions) across all networks | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | Experience Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset ID | Unique identifier for creative assets (images, videos, etc.) within the network | `paidMedia.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset GUID | Unique identifier for creative assets (images, videos, etc.) across all networks | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | Asset Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Account GUID (class entityIDs hierarchy) | `entityIDs.account.accountGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Account ID | Account ID (class entityIDs hierarchy) | `entityIDs.account.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign GUID | Campaign GUID (class entityIDs hierarchy) | `entityIDs.campaign.campaignGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign ID | Campaign ID (class entityIDs hierarchy) | `entityIDs.campaign.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group GUID | Ad Group GUID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group ID | Ad Group ID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad GUID | Ad GUID (class entityIDs hierarchy) | `entityIDs.ad.adGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad ID | Ad ID (class entityIDs hierarchy) | `entityIDs.ad.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience GUID | Experience GUID (class entityIDs hierarchy) | `entityIDs.experience.experienceGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience ID | Experience ID (class entityIDs hierarchy) | `entityIDs.experience.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset GUID | Asset GUID (class entityIDs hierarchy) | `entityIDs.asset.assetGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset ID | Asset ID (class entityIDs hierarchy) | `entityIDs.asset.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group Name | Display name of the ad group/ad set/ad squad. Mirrors metadata.name from the ad group lookup. | `paidMedia.denormalizedNames.adGroupName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad group name"))`) | | |
| Ad Name | Display name of the individual ad. Mirrors metadata.name from the ad lookup. | `paidMedia.denormalizedNames.adName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad name"))`) | | |
| Campaign Name | Display name of the campaign. Mirrors metadata.name from the campaign lookup. | `paidMedia.denormalizedNames.campaignName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Campaign name"))`) | | |

-->
