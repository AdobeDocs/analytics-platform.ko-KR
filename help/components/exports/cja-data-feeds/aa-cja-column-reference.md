---
title: Adobe Analytics 데이터 피드 열을 Customer Journey Analytics에 매핑
description: 주어진 Adobe Analytics 데이터 피드 열을 가져오는 방법을 결정하고 Customer Journey Analytics 구현에서 그에 해당하는 대략적인 내용을 결정합니다.
feature: Components
hide: true
hidefromtoc: true
exl-id: 81d6e79e-8324-4726-9a48-10177b0a91b1
source-git-commit: b0be8b726c4fab1bf9bb5f9462be84f39bdf184a
workflow-type: tm+mt
source-wordcount: '3768'
ht-degree: 48%

---

# Adobe Analytics 데이터 피드 열을 Customer Journey Analytics에 매핑

Adobe Analytics과 Customer Journey Analytics 데이터 피드 열 간에 true 1:1 매핑을 수행할 수 없습니다. 두 제품은 근본적으로 다르며, 각 조직의 구현도 크게 달라질 수 있다.

이 참조는 데이터 엔지니어가 Adobe Analytics 데이터 피드 열을 평가하고 워크플로우에 가장 가까운 Customer Journey Analytics을 식별하는 데 도움이 됩니다.

>[!NOTE]
>
>이 참조에는 [Analytics 데이터 피드 열 참조](https://experienceleague.adobe.com/ko/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference)를 기반으로 Adobe에서 현재 것으로 간주되는 열만 포함됩니다. 이 표에 Analytics 데이터 피드 열이 나열되어 있지 않고 현재 사용 중인 경우에는 조직의 솔루션 디자인 문서를 참조하여 Customer Journey Analytics에서 가장 적합한 데이터 피드를 결정하십시오.

+++**`accept_language`**

이미지 요청의 Accept-Language HTTP 헤더에 표시된 대로 모든 수락된 언어를 나열합니다.

+++

+++**`adload`**

미디어 광고 로드

{{cja-df-post}}

+++

+++**`aemassetid`**

Adobe Experience Manager Assets 세트의 자산 ID(GUID)에 해당하는 다중 값 변수입니다. 노출 이벤트를 증가시킵니다.

{{cja-df-post}}

+++

+++**`aemassetsource`**

자산 이벤트의 소스를 식별합니다. Adobe Experience Manager에서 사용됩니다.

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

Adobe Experience Manager 자산의 자산 ID입니다. 클릭 이벤트를 증가시킵니다.

{{cja-df-post}}

+++

+++**`amo_cid`**

Adobe Advertising 통합에 사용되는 AMO ID 차원입니다.

{{cja-df-post}}

+++

+++**`amo_ef_id`**

Adobe Advertising 통합에 사용되는 AMO EF ID 차원입니다.

{{cja-df-post}}

+++

+++**`browser`**

브라우저를 나타내는 숫자 ID.

{{cja-df-lookup}}

+++

+++**`browser_height`**

브라우저 높이 차원.

{{cja-df-post}}

+++

+++**`browser_width`**

브라우저 너비

{{cja-df-post}}

+++

+++**`campaign`**

추적 코드 차원.

{{cja-df-post}}

+++

+++**`carrier`**

이동통신사를 지정합니다.

{{cja-df-lookup}}

{{cja-df-ua}}

+++

+++**`channel`**

사이트 섹션 차원.

{{cja-df-post}}

+++

+++**`ch_hdr`**

HTTP 요청 헤더를 통해 수집된 클라이언트 힌트입니다.

Adobe Analytics에서 클라이언트 힌트는 이 열에서 연결된 문자열로 포함됩니다. `user_agent` 열보다 최신 접근 방식으로 간주됩니다.

{{cja-df-ua}}

+++

+++**`ch_js`**

사용자 에이전트 클라이언트 힌트 JavaScript API를 통해 수집된 클라이언트 힌트입니다.

Adobe Analytics에서 클라이언트 힌트는 이 열에서 연결된 문자열로 포함됩니다. `user_agent` 열보다 최신 접근 방식으로 간주됩니다.

웹 SDK을 구성할 때 [`highEntropyUserAgentHints`](https://experienceleague.adobe.com/ko/docs/experience-platform/collection/js/commands/configure/context) 컨텍스트 문자열을 사용하여 이 데이터를 수집할 수 있습니다. 하나의 길게 연결된 문자열 대신 여러 XDM 필드가 채워집니다.

* **운영 체제 버전**: `xdm.environment.browserDetails.userAgentClientHints.platformVersion`
* **아키텍처**: `xdm.environment.browserDetails.userAgentClientHints.architecture`
* **장치 모델**: `xdm.environment.browserDetails.userAgentClientHints.model`
* **비트 수**: `xdm.environment.browserDetails.userAgentClientHints.bitness`
* **브라우저 공급업체**: `xdm.environment.browserDetails.userAgentClientHints.vendor`
* **브라우저 이름**: `xdm.environment.browserDetails.userAgentClientHints.brand`
* **브라우저 버전**: `xdm.environment.browserDetails.userAgentClientHints.version`

자세한 내용은 [사용자 에이전트 클라이언트 힌트](https://experienceleague.adobe.com/ko/docs/experience-platform/collection/use-cases/client-hints)를 참조하십시오.

{{cja-df-ua}}

+++

+++**`clickmaplink`**

Activity Map 링크 차원.

{{cja-df-post}}

{{cja-df-na}}

Customer Journey Analytics은 아직 Activity Map을 지원하지 않으므로 이 열은 적용되지 않습니다.

+++

+++**`clickmaplinkbyregion`**

지역별 Activity Map 링크 차원.

{{cja-df-post}}

{{cja-df-na}}

Customer Journey Analytics은 아직 Activity Map을 지원하지 않으므로 이 열은 적용되지 않습니다.

+++

+++**`clickmappage`**

Activity Map 페이지 차원.

{{cja-df-post}}

{{cja-df-na}}

Customer Journey Analytics은 아직 Activity Map을 지원하지 않으므로 이 열은 적용되지 않습니다.

+++

+++**`clickmapregion`**

Activity Map 지역 차원.

{{cja-df-post}}

{{cja-df-na}}

Customer Journey Analytics은 아직 Activity Map을 지원하지 않으므로 이 열은 적용되지 않습니다.

+++

+++**`code_ver`**

이미지 요청을 컴파일하고 전송하는 데 사용되는 API 또는 클라이언트 SDK 버전입니다.

+++

+++**`color`**

`c_color` 열의 값을 기반으로 하는 색상 심도 ID입니다.

{{cja-df-lookup}}

+++

+++**`connection_type`**

연결 유형 차원을 나타내는 숫자 ID입니다.

{{cja-df-lookup}}

+++

+++**`cookies`**

쿠키 지원 차원.<br>Y: 활성화됨<br>N: 비활성화됨<br>U: 알 수 없음

{{cja-df-post}}

+++

+++**`country`**

방문자의 국가를 나타내는 숫자 ID. `country.tsv` 조회 테이블을 참조합니다.

{{cja-df-lookup}}

+++

+++**`currency`**

거래 중에 사용된 통화 코드. `currencyCode`를 사용하여 설정합니다.

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

+++

+++**`ct_connect_type`**

`connection_type` 열과 관련이 있습니다. 가장 일반적인 값은 LAN/Wifi, 이동통신사 및 모뎀입니다.

+++

+++**`curr_factor`**

통화 소수점 자리를 결정합니다. 통화 전환에 사용됩니다. 예를 들어 USD는 소수점 이하 두 자리를 사용하므로 이 열 값은 `2`입니다.

+++

+++**`curr_rate`**

거래가 발생했을 때 환율. Adobe에서는 현재 날짜의 환율을 결정하기 위해 XE와 파트너 관계를 맺습니다.

+++

+++**`customer_perspective`**

히트가 모바일 배경 히트인지 여부를 결정합니다.

{{cja-df-post}}

{{cja-df-na}}

Customer Journey Analytics에는 히트의 컨텍스트에 따라 히트를 자동으로 포함하거나 제외하는 이벤트 유형의 기본 개념이 없습니다. `xdm.eventType`을(를) 사용하여 대부분의 보고서에서 포함 및 제외할 이벤트를 결정할 수 있습니다.

+++

+++**`cust_hit_time_gmt`**

타임스탬프가 활성화된 보고서 세트 전용입니다. UNIX® 시간을 기반으로 하는 히트와 함께 전송된 타임스탬프입니다.

Customer Journey Analytics에는 타임스탬프와 타임스탬프가 아닌 보고서 세트의 개념이 없습니다. 대신 `xdm.timestamp`을(를) 사용하고 원하는 대로 구성 요소 설정을 조정하십시오.

{{cja-df-post}}

+++

+++**`cust_visid`**

`visitorID`를 사용하여 설정한 경우 사용자 정의 방문자 ID.

Customer Journey Analytics은 [`identityMap`](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/field-groups/profile/identitymap)을(를) 사용하여 원하는 수의 id를 지원합니다. 조직에서 사용자 정의 ID를 사용하는 경우 ID 맵 내에 있을 수 있습니다.

{{cja-df-post}}

+++

+++**`c_color`**

색상 팔레트의 비트 심도입니다. 색상 심도 차원 계산의 일부로 사용됩니다. AppMeasurement는 JavaScript 함수 `screen.colorDepth()`를 사용합니다.

+++

+++**`daily_visitor`**

히트가 새 일별 방문자인지 판별하는 플래그.

+++

+++**`dataprivacyconsentoptin`**

동의 관리 옵트인 차원. 히트 당 여러 값이 있을 수 있으며 파이프(`\|`)로 구분됩니다. 유효한 값은 `DMP`, `SELL`입니다.

조직에 데이터 관리 플랫폼이 있는 경우 이 차원에 대해 원하는 XDM 필드를 채울 수 있습니다.

+++

+++**`dataprivacyconsentoptout`**

동의 관리 옵트아웃 차원. 히트 당 여러 값이 있을 수 있으며 파이프(`\|`)로 구분됩니다. 유효한 값은 `SSF`, `DMP`, `SELL`입니다.

조직에 데이터 관리 플랫폼이 있는 경우 이 차원에 대해 원하는 XDM 필드를 채울 수 있습니다.

+++

+++**`date_time`**

보고서 세트의 시간대를 기반으로 한 읽을 수 있는 포맷으로 된 히트 시간입니다.

`xdm.timestamp`을(를) 사용하고 **[!UICONTROL 날짜]** 또는 **[!UICONTROL 날짜-시간]** [형식](/help/data-views/component-settings/format.md) 구성 요소 설정을 적용할 수 있습니다.

+++

+++**`domain`**

도메인 차원. 방문자의 인터넷 액세스 포인트를 기반으로 합니다.

**[!UICONTROL 데이터 스트림을 구성]**&#x200B;할 때 [네트워크 조회](https://experienceleague.adobe.com/ko/docs/experience-platform/datastreams/configure)를 사용합니다. XDM 필드가 스키마에 포함된 경우 `xdm.environment.domain`입니다.

+++

+++**`duplicated_from`**

히트 복사 VISTA 규칙을 포함하는 보고서 세트에서만 사용됩니다. 히트가 복사된 보고서 세트를 나타냅니다.

{{cja-df-na}}

Customer Journey Analytics에는 VISTA 규칙에 대한 개념이 없으므로 이 열이 적용되지 않습니다.

+++

+++**`duplicate_events`**

중복으로 카운트된 각 이벤트를 나열합니다.

{{cja-df-na}}

Customer Journey Analytics에는 모든 지표에 대해 중복 제거 플래그 역할을 하는 단일 필드가 없습니다. 대신 각 지표에는 고유한 [지표 중복 제거 구성 요소 설정](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication)이 포함되어 있습니다. 따라서 Customer Journey Analytics에는 이 Adobe Analytics 데이터 피드 열에 대한 동등한 필드가 없습니다.

+++

+++**`duplicate_purchase`**

중복이라는 이유로 이 히트에 대한 구매 이벤트가 무시되는지 여부를 결정하는 플래그.

이 Analytics 데이터 피드 열에 대한 직접 번역은 없지만 구매 중복 제거를 수행하는 기능은 여전히 존재합니다. [[!UICONTROL Commerce 세부 정보]](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/field-groups/event/commerce-details) 필드 그룹을 사용하는 경우 [중복 제거 ID](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication)이(가) **[!UICONTROL 인]**&#x200B;지표 중복 제거 구성 요소 설정`xdm.commerce.purchases.id`을 설정할 수 있습니다.

중복 구매에 대한 플래그를 원하는 위치에 직접 번역해야 하는 경우 규칙 집합에서 [중복 제거](/help/data-views/derived-fields/derived-fields.md) 함수를 사용하여 **파생 필드**&#x200B;를 사용할 수 있습니다.

+++

+++**`ef_id`**

Adobe Advertising 통합에 사용되는 EF ID.

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

사용자 정의 변수 1-250입니다. eVar 차원에 사용됩니다. 각 조직은 eVar를 다르게 사용합니다. 조직이 각 eVar를 채우는 방법에 대한 자세한 정보는 조직별 솔루션 설계 문서를 참조하십시오.

{{cja-df-post}}

+++

+++**`event_list`**

히트로 트리거된 이벤트를 나타내는 숫자 ID를 쉼표로 구분한 목록. 상거래 이벤트와 사용자 지정 이벤트 1-1000을 모두 포함합니다. `event.tsv` 조회를 사용합니다.

이 열은 구현에 따라 수십 개의 개별 지표에 매핑될 수 있습니다. Adobe은 Customer Journey Analytics의 각 지표를 이 Analytics 데이터 피드 열에 표시된 해당 숫자 값에 매핑하기 위해 다음 프로세스를 권장합니다.

1. `event.tsv` 조회를 사용하여 각 숫자 값을 해당 지표 이름에 매핑합니다.
1. 솔루션 디자인 문서를 사용하여 각 Analytics 이벤트 이름을 Customer Journey Analytics의 해당 지표 이름에 매핑합니다.
1. 데이터 보기 UI에서 매핑된 구성 요소를 선택하고 구성 요소 ID를 확인합니다. 구성 요소 ID가 너무 까다로운 경우 데이터 피드 별칭 ID 필드를 채우고 대신 사용할 수 있습니다.
1. 조직에서 사용하는 모든 지표에 대해 이 작업을 반복합니다.

{{cja-df-post}}

스키마에서 [[!UICONTROL Commerce 세부 정보]](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/field-groups/event/commerce-details) 필드 그룹을 사용하는 경우 일부 지표가 다음 XDM 필드에 직접 매핑될 수 있습니다.

* **체크아웃**: `xdm.commerce.checkouts.value`
* **장바구니 추가**: `xdm.commerce.productListAdds.value`
* **장바구니 열기**: `xdm.commerce.productListOpens.value`
* **장바구니 제거**: `xdm.commerce.productListRemovals.value`
* **장바구니 보기**: `xdm.commerce.productListViews.value`
* **제품 보기**: `xdm.commerce.productViews.value`
* **주문**: `xdm.commerce.purchases.value`

일부 지표는 Adobe Analytics에서 중복 제거를 완전히 제어하는 방식인 이벤트 직렬화를 사용할 수 있습니다. [지표 중복 제거](/help/data-views/component-settings/metric-deduplication.md) 구성 요소 설정을 사용하여 중복 제거 패리티를 달성할 수 있습니다.

* Adobe Analytics에서 지표가 방문별로 중복을 제거하는 경우 해당 지표의 구성 요소 설정에서 중복 제거 범위를 세션으로 설정할 수 있습니다.
* 지표가 Adobe Analytics에서 이벤트 ID별로 중복을 제거하는 경우 해당 지표에 대한 XDM 개체에 `value` 및 `id` 필드가 모두 포함되어 있을 수 있습니다. 스키마에서 [[!UICONTROL Commerce 세부 정보]](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/field-groups/event/commerce-details) 필드 그룹을 사용하는 경우 해당 지표는 다음 XDM 필드에 있을 수 있습니다. 지표의 구성 요소 설정에서 **[!UICONTROL 중복 제거 ID]** 필드를 설정할 수 있습니다.

   * **체크아웃**: `xdm.commerce.checkouts.id`
   * **장바구니 추가**: `xdm.commerce.productListAdds.id`
   * **장바구니 열기**: `xdm.commerce.productListOpens.id`
   * **장바구니 제거**: `xdm.commerce.productListRemovals.id`
   * **장바구니 보기**: `xdm.commerce.productListViews.id`
   * **제품 보기**: `xdm.commerce.productViews.id`

주문 지표의 중복을 제거하려는 경우 `duplicate_purchase`을(를) 참조하십시오.

+++

+++**`exclude_hit`**

히트가 보고에서 제외되는지 여부를 결정하는 플래그. `visit_num` 열은 제외된 히트에 대해 증가하지 않습니다.

Customer Journey Analytics은 기본 제공되는 &quot;제외된 히트&quot;를 지원하지 않습니다. 그러나 제외할 특정 히트에 플래그를 지정하는 XDM 필드가 있는 경우 이 기능을 다시 만들 수 있습니다.

1. 제외된 히트에 플래그를 지정하는 XDM 필드가 구성 요소(이 플래그를 설정한 방법에 따라 차원 또는 지표)로 포함되어 있는지 확인합니다. [보고에서 구성 요소 숨기기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/component-settings/overview)를 선택하면 이 필드에 도움이 될 수 있습니다.
1. [데이터 보기 설정](/help/data-views/session-settings.md)에서 **[!UICONTROL 세그먼트 추가]** 드롭다운 메뉴를 선택하고 **[!UICONTROL 세그먼트 만들기]**&#x200B;를 선택합니다.
1. 제외 히트 구성 요소가 존재하거나 제외할 값을 포함하는 모든 이벤트를 제외하는 세그먼트를 만듭니다.
1. 세그먼트와 데이터 보기 모두에서 **[!UICONTROL 저장]**&#x200B;을(를) 선택하십시오.

제외된 히트는 이제 Customer Journey Analytics 보고에 없지만 데이터 피드 내보내기에서 계속 사용할 수 있습니다.

+++

+++**`first_hit_pagename`**

원래 시작 페이지 차원입니다. 방문자의 원래 시작 페이지 이름.

+++

+++**`first_hit_page_url`**

방문자의 첫 번째 URL.

+++

+++**`first_hit_referrer`**

방문자의 첫 번째 참조 URL.

+++

+++**`first_hit_ref_domain`**

최초 참조 도메인 차원. `first_hit_referrer`를 기반으로 합니다. 방문자의 첫 번째 참조 도메인입니다.

+++

+++**`first_hit_ref_type`**

방문자의 첫 번째 레퍼러 유형을 나타내는 숫자 ID입니다.

{{cja-df-lookup}}

+++

+++**`first_hit_time_gmt`**

UNIX® 시간에서 방문자의 첫 번째 히트 타임스탬프입니다.

+++

+++**`geo_city`**

IP를 기반으로 하는 히트가 발생한 시/군/구의 이름. 도시 차원에 사용됩니다.

+++

+++**`geo_country`**

IP를 기반으로 하는 히트가 발생한 국가의 약어. 국가 차원에 사용됩니다.

+++

+++**`geo_dma`**

IP를 기반으로 하는 히트가 발생한 인구 통계학적 지역의 숫자 ID. US DMA 차원에 사용됩니다.

+++

+++**`geo_region`**

IP를 기반으로 하는 히트가 발생한 시/도 또는 지역의 이름. 지역 차원에 사용됩니다.

+++

+++**`geo_zip`**

IP를 기반으로 하는 히트가 발생한 지역의 우편 번호입니다. 우편 번호 차원을 채우는 데 도움이 됩니다. 참조: `zip`.

+++

+++**`hitid_high`**

히트를 식별하기 위해 `hitid_low`와 함께 사용됩니다.

+++

+++**`hitid_low`**

히트를 식별하기 위해 `hitid_high`와 함께 사용됩니다.

+++

+++**`hit_source`**

히트가 발생한 소스. 히트 소스 1과 2가 청구됩니다. <br>1: 타임스탬프가 없는 표준 이미지 요청 <br>2: 타임스탬프가 있는 표준 이미지 요청 <br>3: 타임스탬프가 있는 라이브 데이터 소스 업로드 <br>4: 사용되지 않음 <br>5: 일반 데이터 소스 업로드 <br>6: 더 이상 사용되지 않음, 데이터 소스 업로드 전체 처리 <br>7: TransactionID 데이터 소스 업로드 <br>8: 더 이상 사용되지 않음, Adobe Advertising 데이터 소스의 이전 버전 <br>9: 더 이상 사용되지 않음, Adobe Social 요약 지표 <br>10: Audience Manager 서버측 전달이 사용됨

+++

+++**`hit_time_gmt`**

히트 Adobe 데이터 수집 서버의 타임스탬프가 UNIX® 시간을 기준으로 히트를 받았습니다.

+++

+++**`hourly_visitor`**

히트가 새로운 시간별 방문자인지 판별하는 플래그.

+++

+++**`ip`**

이미지 요청의 HTTP 헤더를 기반으로 한 IPv4 주소입니다. `ipv6`과 상호 배타적입니다. 이 열에 난독화되지 않은 IP 주소가 포함된 경우 `ipv6`은 비어 있습니다.

+++

+++**`ipv6`**

압축된 IPv6 주소입니다(사용 가능한 경우). `ip`과 상호 배타적입니다. 이 열에 난독화되지 않은 IP 주소가 포함된 경우 `ip`은 비어 있습니다.

+++

+++**`javascript`**

`j_jscript`을(를) 기반으로 하는 JavaScript 버전의 조회 ID입니다.

{{cja-df-lookup}}

+++

+++**`java_enabled`**

Java 활성화 차원. <br>Y: 활성화됨<br>N: 비활성화됨<br>U: 알 수 없음

{{cja-df-post}}

+++

+++**`j_jscript`**

브라우저가 지원하는 JavaScript 버전입니다.

+++

+++**`language`**

방문자의 언어를 나타내는 숫자 ID입니다.

{{cja-df-lookup}}

+++

+++**`last_hit_time_gmt`**

이전 히트의 타임스탬프(UNIX® 시간)입니다. 마지막 방문 이후의 일수 차원을 계산하는 데 사용됩니다.

+++

+++**`last_purchase_num`**

고객 충성도 차원. 방문자가 수행한 이전 구매 횟수입니다. <br>0: 이전 구매 없음 (고객이 아님) <br>1: 1회 이전 구매 (신규 고객) <br>2: 2회 이전 구매 (재방문 고객) <br>3: 3회 이상 이전 구매 (단골 고객)

+++

+++**`last_purchase_time_gmt`**

마지막 구매 이후 일수 차원에 사용됩니다. 마지막으로 수행한 구매의 타임스탬프(UNIX® 시간)입니다. 이전에 구입한 적이 없는 최초 구매 및 방문자의 경우 이 값은 `0`입니다.

+++

+++**`latlon1`**

위치 (10km까지)

+++

+++**`latlon23`**

위치 (100m까지)

+++

+++**`latlon45`**

위치 (1m까지)

+++

+++**`mcvisid`**

Experience Cloud 방문자 ID. 19자리에 채워진 두 개의 연결된 64비트 숫자로 구성된 128비트 숫자.

+++

+++**`mc_audiences`**

방문자가 속한 Audience Manager 세그먼트 ID 목록입니다. `post_mc_audiences` 열은 구분 기호를 `--**--`로 변경합니다.

{{cja-df-post}}

+++

+++**`mobileaction`**

모바일 작업입니다. 모바일 구현에서 `trackAction`이 호출되면 자동으로 수집됩니다. 앱에서 경로를 지정하는 자동 작업을 허용합니다.

{{cja-df-post}}

+++

+++**`mobileappid`**

모바일 앱 ID입니다. 애플리케이션 이름과 버전을 다음 포맷으로 저장: `[AppName] [BundleVersion]`

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

+++

+++**`mobileappperformanceappid`**

Apteligent Data Connector에서 사용됩니다. Apteligent에 사용되는 앱 ID입니다.

+++

+++**`mobileappperformancecrashid`**

Apteligent Data Connector에서 사용됩니다. Apteligent에 사용되는 충돌 ID입니다.

+++

+++**`mobileappstoreobjectid`**

[!DNL Appfigures] Data Connector에서 사용됩니다. 앱스토어 오브젝트 ID.

+++

+++**`mobilebeaconmajor`**

Mobile Services 비콘 Major

+++

+++**`mobilebeaconminor`**

Mobile Services 비콘 Minor

+++

+++**`mobilebeaconproximity`**

Mobile Services 비콘 Proximity

+++

+++**`mobilebeaconuuid`**

Mobile Services 비콘 UUID

+++

+++**`mobilecampaigncontent`**

링크를 표시한 콘텐츠의 이름 또는 ID. 모바일 앱 획득을 통해 채워집니다.

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

배너 또는 이메일과 같은 마케팅 매체. 모바일 앱 획득을 통해 채워집니다.

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

캠페인 변수에도 저장되는 캠페인의 이름. 모바일 앱 획득을 통해 채워집니다.

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

뉴스레터 또는 소셜 미디어 네트워크와 같은 원본 레퍼러. 모바일 앱 획득을 통해 채워집니다.

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

이 획득으로 추적할 유료 키워드 또는 기타 조건입니다. 모바일 앱 획득을 통해 채워집니다.

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

앱을 시작한 요일의 수입니다.

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

앱을 처음 실행한 이후 경과일 수입니다.

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

앱을 마지막으로 실행한 이후 경과일 수입니다.

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

컨텍스트 데이터 변수 `a.deeplink.id`에서 수집됩니다. 모바일 획득 링크의 식별자로 획득 보고서에 사용됩니다.

+++

+++**`mobiledevice`**

모바일 디바이스 이름입니다. iOS에서는 쉼표로 구분된 2자리 문자열로 저장됩니다. 첫 번째 숫자는 디바이스 생성을 나타내고 두 번째 숫자는 디바이스 제품군을 나타냅니다.

{{cja-df-post}}

+++

+++**`mobilehourofday`**

앱이 실행된 시간을 정의합니다. 24시간 숫자 포맷을 따릅니다.

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

모바일 설치 날짜입니다. 사용자가 모바일 앱을 처음 연 날짜를 제공합니다.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

모바일 앱을 시작할 때마다 1씩 증가합니다.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

컨텍스트 데이터 변수 `a.message.button.id`에서 수집됩니다. 메시지를 닫은 버튼을 식별하는 인앱 메시지에 사용됩니다.

{{cja-df-post}}

+++

+++**`mobilemessageid`**

인앱 메시지 ID

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

인앱 메시지 온라인

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

컨텍스트 데이터 변수 `a.push.optin`에서 수집됩니다. 사용자가 푸시 메시지를 사용할 때 “true”로 설정됩니다. 그러지 않는 경우에는 값이 “false”입니다.

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

컨텍스트 데이터 변수 `a.push.payloadid`에서 수집됩니다. 푸시 메시지에 페이로드 식별자로 사용됩니다.

{{cja-df-post}}

+++

+++**`mobileosversion`**

Mobile Services 운영 체제 버전

{{cja-df-post}}

+++

+++**`mobileplaceaccuracy`**

컨텍스트 데이터 변수 `a.loc.acc`에서 수집됩니다. 수집 시 GPS의 정확도를 미터 단위로 나타냅니다.

+++

+++**`mobileplacecategory`**

컨텍스트 데이터 변수 `a.loc.category`에서 수집됩니다. 특정 위치의 카테고리를 설명합니다.

+++

+++**`mobileplaceid`**

컨텍스트 데이터 변수 `a.loc.id`에서 수집됩니다. 지정된 관심 영역에 대한 식별자입니다.

+++

+++**`mobilepushoptin`**

모바일 서비스 푸시 옵트인

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

모바일 서비스 푸시 페이로드 ID

{{cja-df-post}}

+++

+++**`mobilerelaunchcampaigncontent`**

Mobile Services 실행 콘텐츠

+++

+++**`mobilerelaunchcampaignmedium`**

Mobile Services 실행 미디어

+++

+++**`mobilerelaunchcampaignsource`**

Mobile Services 실행 소스

+++

+++**`mobilerelaunchcampaignterm`**

Mobile Services 실행 용어

+++

+++**`mobilerelaunchcampaigntrackingcode`**

컨텍스트 데이터 변수 `a.launch.campaign.trackingcode`에서 수집됩니다. 실행 캠페인에 대한 추적 코드로 획득에 사용됩니다.

+++

+++**`mobileresolution`**

모바일 디바이스의 해상도입니다. `[Width] x [Height]` 픽셀 단위.

{{cja-df-post}}

+++

+++**`mobile_id`**
사용자가 모바일 디바이스를 사용하는 경우 디바이스의 숫자 ID입니다.

{{cja-df-lookup}}

+++

+++**`monthly_visitor`**

해당 방문자가 현재 월에 처음 방문하는 방문자인지 여부를 판단하는 플래그.

+++

+++**`mvvar1`** - **`mvvar3`**

목록 변수 값입니다. 구현에 따라 구분된 사용자 정의 값 목록을 포함합니다. `post_mvvar1` - `post_mvvar3`열은 원래 구분 기호를 `--**--`으로 바꿉니다.

{{cja-df-post}}

+++

+++**`mvvar1_instances`** - **`mvvar3_instances`**

현재 히트에 설정된 목록 변수 값입니다. 원래 구분 기호를 `--**--`로 바꿉니다. 일반적으로 `post` 열에는 데이터가 없습니다.

{{cja-df-post}}

+++

+++**`new_visit`**

현재 히트가 새 방문인지를 판별하는 플래그. 30분 동안 방문 활동이 없으면 Adobe 서버에서 설정합니다.

+++

+++**`os`**

방문자의 운영 체제를 나타내는 숫자 ID. `user_agent` 열을 기반으로 합니다.

{{cja-df-lookup}}

[데이터 스트림을 구성](https://experienceleague.adobe.com/ko/docs/experience-platform/datastreams/configure)할 때 **[!UICONTROL 장치 조회]**&#x200B;를 사용할 수 있습니다. 활성화된 경우 **[!UICONTROL 운영 체제]** 확인란을 선택하십시오. 스키마에 이러한 필드를 포함하면 다음 XDM 필드가 자동으로 채워집니다.

* **OS 공급업체**: `xdm.environment.operatingSystemVendor`
* **OS 이름**: `xdm.environment.operatingSystem`
* **OS 버전**: `xdm.environment.operatingSystemVersion`

{{cja-df-ua}}

+++

+++**`pagename`**

페이지 차원. `pagename` 변수가 비어 있으면 Analytics가 `page_url`을 대신 사용합니다.

{{cja-df-post}}

+++

+++**`pagename_no_url`**

`pagename`과 비슷하지만 `page_url`로 대체되지 않습니다. `post` 열만 사용할 수 있습니다.

{{cja-df-post}}

+++

+++**`page_event`**

이미지 요청(표준 히트, 다운로드 링크, 사용자 지정 링크, 종료 링크)에서 전송된 히트 유형입니다.

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`page_event_var1`**

링크 추적 이미지 요청에서만 사용됩니다. 클릭한 다운로드 링크, 종료 링크 또는 사용자 정의 링크의 URL입니다.

{{cja-df-post}}

+++

+++**`page_event_var2`**

링크 추적 이미지 요청에서만 사용됩니다. 링크의 사용자 지정 이름 (지정된 경우). `page_event`의 값에 따라 사용자 지정 링크, 다운로드 링크 또는 종료 링크를 설정합니다.

{{cja-df-post}}

+++

+++**`page_type`**

페이지를 찾을 수 없음 차원은 일반적으로 404 페이지에 사용됩니다.

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`**: 히트의 URL입니다. 텍스트 데이터 형식을 사용합니다.<br>**`post_page_url`**: 링크 추적 이미지 요청(`tl()`)을 제거했습니다.

{{cja-df-post}}

+++

+++**`paid_search`**

히트가 유료 검색 발견과 일치하는 지 판별하는 플래그.

+++

+++**`persistent_cookie`**

영구적 쿠키 지원 차원에 사용됩니다. 방문자가 각 히트 후 삭제되지 않은 쿠키를 지원하는지 여부를 나타냅니다.

{{cja-df-post}}

+++

+++**`pointofinterest`**

Mobile Services 관심 영역 이름

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

Mobile Services 관심 영역 중앙까지의 거리

{{cja-df-post}}

+++

+++**`product_list`**

`products` 페이지 변수. 카테고리, 제품, 판매량 및 매출을 포함하여 여러 차원 및 지표를 채우는 데 도움이 됩니다.

{{cja-df-post}}

+++

+++**`prop1`** - **`prop75`**

사용자 정의 트래픽 변수 1 - 75. Prop 차원에 사용됩니다.

{{cja-df-post}}

+++

+++**`purchaseid`**

`purchaseID` 변수를 사용하여 설정되는 구매의 고유 식별자입니다. `duplicate_purchase` 열에서 사용됩니다.

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

히트가 새 분기별 방문자인지 판별하는 플래그.

+++

+++**`referrer`**

레퍼러 차원. `referrer`에서 varchar(255)의 데이터 유형을 사용하는 동안 `post_referrer`에서는 varchar(244)의 데이터 유형을 사용합니다.

{{cja-df-post}}

+++

+++**`ref_domain`**

참조 도메인 차원. `referrer` 열을 기반으로 합니다.

+++

+++**`ref_type`**


히트에 대한 참조 유형을 나타내는 숫자 ID. 레퍼러 유형 차원에 사용됩니다.<br>1: 사이트 내부<br>2: 기타 웹 사이트<br>3: 검색 엔진<br>4: 하드 드라이브<br>5: USENET<br>6: 입력/책갈피 표시(레퍼러 없음)<br>7: 전자 메일<br>8: JavaScript 없음<br>9: 소셜 네트워크<br>10: 대화형 AI 도구

+++

+++**`resolution`**

모니터의 해상도를 나타내는 숫자 ID. 모니터 해상도 차원에 사용됩니다.

{{cja-df-lookup}}

+++

+++**`search_engine`**

방문자에게 사이트를 참조하도록 하는 검색 엔진을 나타내는 숫자 ID. 검색 엔진 차원에 사용됩니다.

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`search_page_num`**

모든 검색 페이지 등급 차원에 사용됩니다. 사용자가 사이트를 클릭하기 전에 사이트가 표시된 검색 결과 페이지를 나타냅니다.

+++

+++**`secondary_hit`**

히트가 보조 히트인지 여부를 결정하는 플래그. 이 플래그는 일반적으로 히트 수를 복사하는 다중 세트 태그 지정 및 VISTA 규칙에서 시작됩니다.

+++

+++**`sourceid`**

소스 ID

+++

+++**`stats_server`**

사용하지 않습니다. 히트를 처리한 Adobe 내부 서버입니다.

+++

+++**`s_kwcid`**

Adobe Advertising 통합에 사용되는 키워드 ID입니다.

{{cja-df-post}}

+++

+++**`s_resolution`**

Raw 화면 해상도 값입니다. JavaScript 함수 `screen.width x screen.height`를 사용하여 수집됩니다.

+++

+++**`tnt`**

Adobe Target 통합에서 사용됩니다. 현재 자격이 있는 모든 테스트를 나타냅니다. 포맷: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`입니다.

{{cja-df-post}}

+++

+++**`tnt_action`**

Adobe Target 통합에서 사용됩니다. 히트 자격이 있는 모든 테스트를 나타냅니다.

{{cja-df-post}}

+++

+++**`tnt_instances`**

Adobe Target 통합에서 사용됩니다. 대상 인스턴스 변수

+++

+++**`transactionid`**

데이터 소스를 통해 나중에 다양한 데이터 포인트를 업로드할 수 있는 고유 식별자입니다. `transactionID` 변수를 사용하여 수집됩니다.

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

이미지 요청이 잘렸음을 나타내는 플래그(부분 히트가 수신됨)입니다. <br>Y: 히트가 잘림, 일부 히트 수신 <br>N: 히트가 잘리지 않음, 전체 히트 수신

+++

+++**`t_time_info`**

방문자의 로컬 시간입니다. 포맷: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

+++

+++**`userid`**

사용하지 않습니다. 보고서 세트 ID의 숫자 ID. 대신 `username`를 사용하십시오.

+++

+++**`username`**

히트에 대한 보고서 세트 ID.

+++

+++**`user_agent`**

이미지 요청의 HTTP 헤더에서 전송된 사용자 에이전트 문자열.

+++

+++**`user_hash`**

사용하지 않습니다. 보고서 세트 ID의 해시. 대신 `username`를 사용하십시오.

+++

+++**`user_server`**

서버 차원에 사용됩니다.

{{cja-df-post}}

+++

+++**`va_closer_detail`**

마지막 터치 세부 사항 차원.

+++

+++**`va_closer_id`**

마지막 터치 채널 차원을 식별하는 숫자 ID입니다.

{{cja-df-lookup}}

+++

+++**`va_finder_detail`**

첫 번째 터치 세부 사항 차원입니다.

+++

+++**`va_finder_id`**

첫 번째 터치 채널 차원을 식별하는 숫자 ID입니다.

{{cja-df-lookup}}

+++

+++**`va_instance_event`**

마케팅 채널 인스턴스를 식별하는 플래그.

+++

+++**`va_new_engagement`**

마케팅 채널 새 참여를 식별하는 플래그입니다.

+++

+++**`video`**

컨텐츠 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videoad`**

Ad Streaming Media 서비스 차원.

{{cja-df-post}}

+++

+++**`videoadinpod`**

Pod의 광고는 스트리밍 미디어 서비스 차원을 배치합니다.

{{cja-df-post}}

+++

+++**`videoadlength`**

광고 길이(변수) 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videoadname`**

광고 이름(변수) 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videoadplayername`**

광고 플레이어 이름 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videoadpod`**

Ad pod streaming media 서비스 차원.

{{cja-df-post}}

+++

+++**`videoadvertiser`**

Advertiser Streaming Media 서비스 차원.

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

앨범 스트리밍 미디어 서비스 차원.

+++

+++**`videoaudioartist`**

아티스트 스트리밍 미디어 서비스 차원.

+++

+++**`videoaudioauthor`**

Streaming Media 서비스 작성 차원.

+++

+++**`videoaudiolabel`**

스트리밍 미디어 서비스에 레이블 지정 차원입니다.

+++

+++**`videoaudiopublisher`**

Publisher Streaming Media 서비스 차원입니다.

+++

+++**`videoaudiostation`**

스테이션 스트리밍 미디어 서비스 차원.

+++

+++**`videocampaign`**

캠페인 ID 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videochannel`**

콘텐츠 채널 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videochapter`**

챕터 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videocontenttype`**

컨텐츠 유형 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videodaypart`**

방송 시간대 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videoepisode`**

에피소드 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videofeedtype`**

미디어 피드 유형 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videogenre`**

장르 스트리밍 미디어 서비스 차원. 이 차원을 사용하면 동일한 히트에서 쉼표로 구분된 여러 값을 사용할 수 있습니다.

{{cja-df-post}}

+++

+++**`videolength`**

콘텐츠 길이(변수) 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videomvpd`**

MVPD 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videoname`**

컨텐츠 이름(변수) 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videonetwork`**

네트워크 스트리밍 미디어 서비스 차원입니다.

{{cja-df-post}}

+++

+++**`videopath`**

미디어 경로 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videoplayername`**

컨텐츠 플레이어 이름 스트리밍 미디어 서비스 차원입니다.

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

평균 비트율 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

비트율은 스트리밍 미디어 서비스 차원을 변경합니다.

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

버퍼 이벤트 스트리밍 미디어 서비스 차원입니다.

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

스트리밍 미디어 서비스의 총 버퍼 지속 시간 차원입니다.

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

Streaming Media 서비스 차원에서 삭제된 프레임.

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

스트리밍 미디어 서비스 오류 차원.

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

스트리밍 미디어 서비스 차원의 외부 오류 ID. 이 차원을 사용하면 동일한 히트에서 여러 값을 사용할 수 있습니다.

+++

+++**`videoqoeplayersdkerrors`**

스트리밍 미디어 서비스 차원에서 플레이어 SDK 오류 ID입니다. 이 차원을 사용하면 동일한 히트에서 여러 값을 사용할 수 있습니다.

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

스트리밍 미디어 서비스 시작 시간 차원.

{{cja-df-post}}

+++

+++**`videoseason`**

시즌 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videosegment`**

콘텐츠 세그먼트 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videosessionid`**

미디어 세션 ID 스트리밍 미디어 서비스 차원.

{{cja-df-post}}

+++

+++**`videoshow`**

스트리밍 미디어 서비스 표시 차원.

{{cja-df-post}}

+++

+++**`videoshowtype`**

Streaming Media 서비스 표시 유형입니다.

{{cja-df-post}}

+++

+++**`videostreamtype`**

스트림 유형 스트리밍 미디어 서비스 차원.

+++

+++**`visid_high`**

방문자를 고유하게 식별하기 위해 `visid_low`와 함께 사용됩니다.

{{cja-df-post}}

+++

+++**`visid_low`**

방문자를 고유하게 식별하기 위해 `visid_high`와 함께 사용됩니다.

{{cja-df-post}}

+++

+++**`visid_new`**

히트에 새로 생성된 방문자 ID가 포함되어 있는지 여부를 결정하는 플래그.

+++

+++**`visid_timestamp`**

방문자 ID가 새로 생성된 경우 방문자 ID가 생성된 시점의 타임스탬프를 UNIX® 시간 단위로 제공합니다.

+++

+++**`visid_type`**

외부용이 아닙니다. Adobe가 최적화 처리를 위해 내부적으로 사용합니다. 방문자를 식별하는 데 사용된 방법을 나타내는 숫자 ID.<br>`0`: 사용자 정의 방문자 ID 또는 알 수 없음/적용할 수 없음<br>`1`: IP 및 사용자 에이전트 폴백 <br>`2`: HTTP 모바일 구독자 헤더 <br>`3`: 기존 쿠키 값(`s_vi`) <br>`4`: 대체 쿠키 값(`s_fid`) <br>`5`: ID 서비스

{{cja-df-post}}

+++

+++**`visit_keywords`**

검색 키워드 차원. 이 열은 Adobe에서 사용하는 백엔드 로직을 수용하기 위해 비표준 문자 제한인 varchar(244)를 사용합니다. 후처리된 열은 `**post_keywords**`이(가) 아닌 `**post_visit_keywords**`입니다.

{{cja-df-post}}

+++

+++**`visit_num`**

방문 횟수 차원. 1에서 시작하여 새 방문이 방문자별로 시작될 때마다 증가합니다.

+++

+++**`visit_page_num`**

히트 깊이 차원. 방문자가 생성하는 각 히트마다 1씩 증가합니다. 각 방문을 재설정합니다.

+++

+++**`visit_referrer`**

방문의 첫 번째 레퍼러입니다.

+++

+++**`visit_ref_domain`**

`visit_referrer` 열을 기반으로 합니다. 방문의 첫 번째 참조 도메인.

+++

+++**`visit_ref_type`**

방문의 첫 번째 레퍼러 유형을 나타내는 숫자 ID입니다.

{{cja-df-lookup}}

+++

+++**`visit_search_engine`**

방문의 첫 번째 검색 엔진을 나타내는 숫자 ID입니다.

{{cja-df-lookup}}

+++

+++**`visit_start_pagename`**

방문의 첫 번째 히트 페이지입니다.

+++

+++**`visit_start_page_url`**

방문의 첫 번째 히트 URL.

+++

+++**`visit_start_time_gmt`**

방문의 첫 번째 히트 타임스탬프(UNIX® 시간)입니다.

+++

+++**`weekly_visitor`**

히트가 새로운 주별 방문자인지 판별하는 플래그.

+++

+++**`yearly_visitor`**

히트가 새로운 연별 방문자인지 판별하는 플래그.

+++

+++**`zip`**

우편 번호 차원을 채우는 데 도움이 됩니다. 참조: `geo_zip`.

{{cja-df-post}}

+++
