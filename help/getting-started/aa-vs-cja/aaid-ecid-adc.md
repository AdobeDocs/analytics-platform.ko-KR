---
title: AAID, ECID, AACUSTOMID 및 Analytics 소스 커넥터
description: Analytics 소스 커넥터가 Adobe Analytics ID 필드를 어떤 방식으로 처리하는지 알아봅니다.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
feature: Basics
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 99%

---

# AAID, ECID, AACUSTOMID 및 Analytics 소스 커넥터

Adobe Analytics 데이터에는 여러 ID 필드가 포함되어 있습니다. [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)에 의해 AAID, ECID, AACUSTOMID 이상 세 가지 중요한 ID 필드가 특별히 처리됩니다.

## AAID

AAID(Adobe Analytics ID)는 Adobe Analytics의 기본 디바이스 식별자이며, Analytics 소스 커넥터를 통해 전달되는 모든 이벤트에 존재할 수 있습니다. AAID를 때로 “레거시 Analytics ID” 또는 `s_vi` 쿠키 ID라고도 합니다. 단, AAID는 `s_vi` 쿠키가 없는 경우에도 생성됩니다. AAID는 [Adobe Analytics 데이터 피드](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ko-KR#columns%2C-descriptions%2C-and-data-types)의 `post_visid_high/post_visid_low` 열에 표시됩니다.

Analytics 소스 커넥터에서 AAID는 `HEX(post_visid_high) + "-" + HEX(post_visid_low)`로 변환됩니다. 주어진 이벤트의 AAID 필드는 [Analytics ID에 대한 작업 순서](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html%5B%5D)에서 설명한 바와 같이 여러 가지 다른 유형 중 하나일 수 있는 단일 ID를 포함합니다. (전체 보고서 세트 내에서 AAID에는 여러 이벤트에 걸쳐 혼합된 유형을 포함할 수 있습니다. 각 이벤트 유형은 Analytics 데이터 피드의 `post_visid_type` 열에 표시됩니다.) 또한 [데이터 열 참조](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html)도 살펴보십시오.

## ECID

ECID(Experience Cloud ID) 또는 MCID(Marketing Cloud ID)는 Adobe Analytics에서 [Experience Cloud ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=ko-KR)를 사용하여 Analytics가 구현될 때 채워지는 별도의 디바이스 식별자 필드입니다. ECID는 Adobe Analytics 데이터 피드의 `mcvisid` 열에 표시됩니다.

이벤트에 ECID가 존재하는 경우, AAID는 Analytics [유예 기간](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html)이 구성되어 있는지 여부에 따라 ECID에 기반할 수 있습니다. [Analytics 및 Experience Cloud ID 요청](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html)도 참조하십시오.

## AACUSTOMID

AACUSTOMID는 Analytics 구현에서의 `s.VisitorID` 변수 사용에 따라 Adobe Analytics에 채워지는 별도의 식별자 필드입니다. AACUSTOMID는 Adobe Analytics 데이터 피드의 `cust_visid` 열에 표시됩니다. AACUSTOMID가 있으면 AAID는 AACUSTOMID를 기반으로 합니다. (AACUSTOMID는 위에 언급된 작업 순서에 의해 정의된 다른 모든 식별자를 우선합니다.)

## Analytics 소스 커넥터가 이들 ID를 처리하는 방법

Analytics 소스 커넥터는 다음과 같이 XDM 형식으로 Adobe Experience Platform에 이들 ID를 전달합니다.

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

이들 필드는 ID로 표시되지 않습니다. 대신, 동일한 ID가 다음과 같이 키 값 쌍으로 XDM의 **_identityMap_**&#x200B;에 복사됩니다.

* `{ "key": "AAID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "ECID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "AACUSTOMID", "value": [ { "id": "<identity>", "primary": false } ] }`

대괄호 &lt;> 안의 항목은 실제 값이 표시되는 위치를 나타냅니다.

identityMap 내:

* ECID가 있으면 이벤트의 기본 ID로 표시됩니다. 이 경우 AAID는 위의 설명에 따라 ECID를 기반으로 할 수 있습니다.
그렇지 않으면 AAID가 이벤트의 기본 ID로 표시됩니다.
* AACUSTOMID는 이벤트의 기본 ID로 표시되지 않습니다. 단, AACUSTOMID가 있으면 AAID는 위의 설명에 따라 AACUSTOMID를 기반으로 합니다.

## Customer Journey Analytics 및 기본 ID

Customer Journey Analytics에 관한 한, 기본 ID의 정의는 기본 ID를 개인 ID로 사용하기로 결정한 경우에만 중요합니다. 단, 반드시 필요한 것은 아닙니다. 다른 ID 열을 개인 ID로 선택할 수 있습니다.
