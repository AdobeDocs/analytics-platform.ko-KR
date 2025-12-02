---
title: Adobe Analytics 구현 방식과 Customer Journey Analytics 업그레이드에 미치는 영향을 이해하기
description: Adobe Analytics에서 Customer Journey Analytics로 업그레이드할 때 권장되는 경로 자세히 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 100%

---

# Adobe Analytics 구현 방식과 Customer Journey Analytics 업그레이드에 미치는 영향을 이해하기 {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (수동 JS 파일)"
>abstract="JavaScript 구현 방식으로, 페이지에서 AppMeasurement.js를 로드하고, s 오브젝트(예: s.eVar1)를 사용하여 Adobe로 데이터를 전송합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Adobe Analytics 확장 기능 (태그)"
>abstract="Adobe Experience Platform 데이터 수집(이전의 Launch)을 로드하는 태그 구현 방식입니다. 이 태그에는 Adobe Analytics 확장 기능이 설치되어 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="Web SDK (alloy.js)"
>abstract="JavaScript 구현 방식으로, 페이지에서 Web SDK 라이브러리(alloy.js)를 로드하고 JSON 페이로드를 사용하여 Adobe로 데이터를 전송합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Web SDK 확장 기능 (태그)"
>abstract="Adobe Experience Platform 데이터 수집(이전의 Launch)을 로드하는 태그 구현 방식입니다. 이 태그에는 Web SDK 확장 기능이 설치되어 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="데이터 삽입 API"
>abstract="데이터 삽입 API 또는 대량 데이터 삽입 API를 사용하는 구현 방식입니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="Mobile SDK"
>abstract="Adobe Experience Platform Mobile SDK를 사용하는 구현 방식입니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-third-party"
>title="서드파티 태그 관리 도구를 사용한 AppMeasurement"
>abstract="서드파티 태그 관리 도구를 사용하는 구현입니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="알 수 없는 구현 방식"
>abstract="구현을 관리하는 담당자가 아니라면 일시적으로 이 옵션을 선택할 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="기존의 구현 유형 확인"
>abstract="조직 내부에서 현재 Adobe Analytics로 데이터를 전송하는 데 사용하고 있는 구현 유형을 확인하십시오. Customer Journey Analytics로 업그레이드할 때 이 정보를 아는 개인이나 팀과 협력하십시오.<br><br>조직에서 사용하는 구현 유형을 확인한 후 Customer Journey Analytics 업그레이드 안내서의 답변을 수정하십시오."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics는 다양한 방법으로 구현될 수 있습니다 Customer Journey Analytics로 업그레이드할 때 모든 Adobe Analytics 구현에 대해 모든 업그레이드 경로를 사용할 수 있는 것은 아닙니다 그러나 권장 업그레이드 경로는 조직에서 Adobe Analytics를 구현하는 방식에 관계없이 사용할 수 있습니다.

아래 정보를 활용하여 현재 Adobe Analytics 구현과 조직에서 사용할 수 있는 업그레이드 경로에 대해 알아봅니다.

더욱 구체적인 조언, 지침 또는 지원이 필요한 경우 Adobe 담당자에게 문의하십시오.

| 기존 Adobe Analytics 구현 | 설명 | 사용 가능한 업그레이드 경로 |
|---------|----------|----------|
| AppMeasurement | AppMeasurement for JavaScript는 지금까지 Adobe Analytics를 구현하는 일반적인 방법이었습니다.<p>이 구현 유형에 대한 자세한 내용은 [JavaScript용 AppMeasurement로 Adobe Analytics 구현](https://experienceleague.adobe.com/ko/docs/analytics/implementation/js/overview)을 참조하십시오.</p> | <ul><li>[(추천) 지속적인 데이터 수집을 위한 Experience Platform Web SDK의 새로운 구현, 내역 데이터에 대한 Analytics 소스 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK의 새로운 구현](/help/data-ingestion/aepwebsdk.md) </li><li>[Adobe Analytics를 Web SDK로 마이그레이션](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analytics 소스 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Adobe Analytics 확장 기능(태그) | <p>Adobe Experience Platform의 태그는 다른 태그 지정 요구 사항과 함께 Analytics 코드를 배포할 수 있도록 해 주는 태그 관리 솔루션입니다. Adobe는 다른 솔루션 및 제품과의 통합을 제공하며 사용자 정의 코드를 배포할 수 있도록 해 줍니다. 따라서 사이트에서 코드를 업데이트하기 위해 조직의 개발 팀에 의존하지 않고도 이러한 모든 작업을 수행할 수 있습니다.</p><p>이 구현 유형에 대한 자세한 내용은 [Analytics 확장 기능을 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/ko/docs/analytics/implementation/launch/overview)을 참조하십시오.</p> | <ul><li>[(추천) 지속적인 데이터 수집을 위한 Experience Platform Web SDK의 새로운 구현, 내역 데이터에 대한 Analytics 소스 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK의 새로운 구현](/help/data-ingestion/aepwebsdk.md) </li><li>[Adobe Analytics를 Web SDK로 마이그레이션](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analytics 소스 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform Web SDK(alloy.js) | Experience Platform Web SDK는 Adobe Analytics 구현을 위한 표준화된 권장 방법입니다. Adobe Experience Platform Edge Network를 사용하면 여러 제품을 대상으로 한 데이터를 중앙 위치에 전송할 수 있습니다. <p>이 구현 유형에 대한 자세한 내용은 [Adobe Experience Platform Edge Network를 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/ko/docs/analytics/implementation/aep-edge/overview)을 참조하십시오.</p> | <ul><li>[(추천) 지속적인 데이터 수집을 위한 Experience Platform Web SDK의 새로운 구현, 내역 데이터에 대한 Analytics 소스 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK의 새로운 구현](/help/data-ingestion/aepwebsdk.md) </li><li>[Adobe Analytics Web SDK 구현을 구성하여 Platform으로 데이터 전송](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Web SDK 확장 기능(태그) | Experience Platform Web SDK는 웹 데이터를 위한 Adobe Analytics 구현을 위한 표준화된 권장 방법입니다. Adobe Experience Platform Edge Network를 사용하면 여러 제품을 대상으로 한 데이터를 중앙 위치에 전송할 수 있습니다. <p>이 구현 유형에 대한 자세한 내용은 [Adobe Experience Platform Web SDK를 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/ko/docs/analytics/implementation/aep-edge/web-sdk/overview)을 참조하십시오.</p> | <ul><li>[(추천) 지속적인 데이터 수집을 위한 Experience Platform Web SDK의 새로운 구현, 내역 데이터에 대한 Analytics 소스 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK의 새로운 구현](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Analytics Web SDK 구현을 구성하여 Platform으로 데이터 전송](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK는 모바일 데이터를 위한 Adobe Analytics 구현을 위한 표준화된 권장 방법입니다. Adobe Experience Platform Edge Network를 사용하면 여러 제품을 대상으로 한 데이터를 중앙 위치에 전송할 수 있습니다.<p>Adobe Experience Platform Mobile SDK는 모바일 앱에서 Adobe의 Experience Cloud 솔루션 및 서비스를 강화하는 데 도움이 됩니다. </p><p>이 구현 유형에 대한 자세한 내용은 [Adobe Experience Platform Mobile SDK를 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/ko/docs/analytics/implementation/aep-edge/mobile-sdk/overview)을 참조하십시오.</p> | <ul><li>[(추천) 지속적인 데이터 수집을 위한 Experience Platform Web SDK의 새로운 구현, 내역 데이터에 대한 Analytics 소스 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK의 새로운 구현](/help/data-ingestion/aepwebsdk.md) </li><li>[Adobe Analytics Web SDK 구현을 구성하여 Platform으로 데이터 전송](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| 대량 데이터 삽입 API | 대량 데이터 삽입 API(BDIA)는 AppMeasurement와 같은 클라이언트측 라이브러리를 사용하지 않고 서버 호출 데이터를 파일 배치에 업로드할 수 있는 Adobe Analytics 기능입니다. </p><p>이 구현 유형에 대한 자세한 내용은 [대량 데이터 삽입 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)를 참조하십시오.</p> | <ul><li>[(추천) 지속적인 데이터 수집을 위한 Experience Platform Web SDK의 새로운 구현, 내역 데이터에 대한 Analytics 소스 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK의 새로운 구현](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network Server API 및 Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


