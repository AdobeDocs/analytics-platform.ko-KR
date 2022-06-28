---
title: AAID, ECID, AACUCUSTOMER 및 Analytics 소스 커넥터
description: Analytics 소스 커넥터가 Adobe Analytics ID 필드를 어떻게 처리하는지 알아봅니다.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
source-git-commit: 20ebfb36e769f7d683ad44ec84b11aafb301a737
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 9%

---

# AAID, ECID, AACUCUSTOMER 및 Analytics 소스 커넥터

Adobe Analytics 데이터에는 여러 ID 필드가 포함되어 있습니다. 세 가지 중요한 신원 분야는 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko): AAID, ECID, AACUCUSTOMER.

## AAID

AAID(Adobe Analytics ID)는 Adobe Analytics의 기본 장치 식별자이며, Analytics 소스 커넥터를 통해 전달된 모든 이벤트에 존재할 수 있습니다. AAID를 &quot;기존 Analytics ID&quot;라고도 하거나 `s_vi` 쿠키 id. 그러나 AAID는 `s_vi` 쿠키가 없습니다. AAID는 `post_visid_high/post_visid_low` 열 [Adobe Analytics 데이터 피드](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ko-KR#columns%2C-descriptions%2C-and-data-types).

Analytics 소스 커넥터에서 AAID가 `HEX(post_visid_high) + "-" + HEX(post_visid_low)`. 지정된 이벤트의 AAID 필드에는 에 설명된 대로 여러 유형 중 하나일 수 있는 단일 ID가 포함되어 있습니다 [Analytics ID 작업 순서](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (전체 보고서 세트 내에서 AAID에는 여러 이벤트 간에 유형이 혼합되어 있을 수 있습니다. 각 히트에 대한 유형은 `post _visid_type` analytics 데이터 피드의 열.) 다음을 참조하십시오. [데이터 열 참조](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ko-KR).

## ECID

ECID(Experience Cloud ID)는 MCID(Marketing Cloud ID)라고도 하며, 를 사용하여 Analytics를 구현할 때 Adobe Analytics에 채워지는 별도의 장치 식별자 필드입니다 [Experience Cloud ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=ko-KR). ECID는 `mcvisid` Adobe Analytics 데이터 피드의 열.

ECID가 이벤트에 있으면 AAID는 Analytics가 있는지에 따라 ECID를 기반으로 할 수 있습니다 [유예 기간](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=ko-KR) 가 구성되어 있습니다. 다음을 참조하십시오. [Analytics 및 Experience Cloud ID 요청](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).

## AACUCUSTOMER

AACUSTOMID는 를 사용하여 Adobe Analytics에 채워지는 별도의 식별자 필드입니다 `s.VisitorID` 변수로 식별됩니다. AACUSTOMID는 `cust_visid` Adobe Analytics 데이터 피드의 열. AACUSTOMID가 있으면 AAID는 AACUCUSTOMER id를 기반으로 합니다. (AACUSTOMID는 위에 언급된 작업 순서에 의해 정의된 다른 모든 식별자를 우선합니다.)

## Analytics 소스 커넥터에서 이러한 ID를 처리하는 방법

Analytics 소스 커넥터는 다음과 같이 XDM 양식의 Adobe Experience Platform에 이러한 ID를 전달합니다.

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

이러한 필드는 ID로 표시되지 않습니다. 대신 동일한 ID가 XDM의 **_identityMap_** 키 값 쌍은 다음과 같습니다.

* `{ “key”: “AAID”, “value”: [ { “id”: “<identity>”, “primary”: <true or false> } ] }`
* `{ “key”: “ECID”, “value”: [ { “id”: “<identity>”, “primary”: <true or false> } ] }`
* `{ “key”: “AACUSTOMID”, “value”: [ { “id”: “<identity>”, “primary”: false } ] }`

대괄호 안에 있는 항목

idMap:

* ECID가 있으면 이벤트의 기본 ID로 표시됩니다. 이 경우 AAID는 위의 논의에 따라 ECID를 기반으로 할 수 있습니다.
그렇지 않으면 AAID가 이벤트의 기본 ID로 표시됩니다.
* AACUSTOMID는 이벤트의 기본 ID로 표시되지 않습니다. 그러나 AACUCUSTOMER ID가 있으면 AAID는 위의 설명에 따라 AACUCUSTOMER ID를 기반으로 합니다.

CJA에 관한 한 기본 ID의 정의는 최종 사용자가 기본 ID를 개인 ID로 사용하기로 결정하는 경우에만 중요합니다. 그렇다고 꼭 필요한 것은 아니다. 사용자는 다른 ID 열을 개인 ID로 선택할 수 있습니다.
