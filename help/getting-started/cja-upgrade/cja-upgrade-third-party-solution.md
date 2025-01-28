---
title: 서드파티 분석 솔루션에서 Customer Journey Analytics으로 업그레이드
description: 타사 분석 솔루션에서 Customer Journey Analytics으로 업그레이드하는 방법에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 8%

---

# 서드파티 분석 솔루션에서 Customer Journey Analytics으로 업그레이드 {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="서드파티 분석 제품"
>abstract="Google Analytics과 같은 서드파티 분석 제품에 대한 데이터를 수집하는 구현입니다. 이 옵션을 선택하면 서드파티 분석 제품에서 Customer Journey Analytics으로 업그레이드할 때 적용되지 않는 몇 가지 설문 조사 옵션이 비활성화됩니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analytics 업그레이드 확인 목록](https://gigazelle.github.io/cja-ttv/)의 질문에 답변할 때 이 페이지의 정보를 사용하십시오.

타사 분석 솔루션에서 Customer Journey Analytics으로 업그레이드하는 권장 프로세스는 Experience Platform에 기본 제공되는 데이터 수집 방법인 Customer Journey Analytics 웹 SDK의 새로운 구현입니다. 웹 SDK과 함께 Adobe에서는 타사 분석 솔루션의 내역 데이터를 Adobe Experience Platform으로 수집하는 것을 권장합니다.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Google Analytics과 같은 서드파티 Customer Journey Analytics 솔루션에서 분석으로 이동할 때 다음 프로세스를 사용하십시오.

1. ...


보다 구체적인 조언, 안내 또는 지원이 필요한 경우 Adobe 담당자에게 문의하십시오.

| 기존 분석 솔루션 | 설명 | 사용 가능한 업그레이드 경로 |
|---------|----------|----------|
| AppMeasurement | JavaScript용 AppMeasurement은 지금까지 Adobe Analytics을 구현하는 일반적인 방법이었습니다.<p>이 구현 유형에 대한 자세한 내용은 [JavaScript용 AppMeasurement을 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)을 참조하십시오.</p> | <ul><li>Experience Platform [(권장) 지속적인 데이터 수집을 위한 Analytics Web SDK의 새로운 구현; 이전 데이터를 위한 Analytics Source 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform 웹 SDK의 새 구현](/help/data-ingestion/aepwebsdk.md) </li><li>Adobe Analytics을 웹 SDK으로 마이그레이션</li><li>[Analytics Source 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Adobe Analytics 확장(태그) | <p>Adobe Experience Platform의 태그는 다른 태그 지정 요구 사항과 함께 Analytics 코드를 배포할 수 있도록 해 주는 태그 관리 솔루션입니다. Adobe는 다른 솔루션 및 제품과의 통합을 제공하며 사용자 정의 코드를 배포할 수 있도록 해 줍니다. 따라서 사이트에서 코드를 업데이트하기 위해 조직의 개발 팀에 의존하지 않고도 이러한 모든 작업을 수행할 수 있습니다.</p><p>이 구현 유형에 대한 자세한 내용은 [Analytics 확장을 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)을 참조하십시오.</p> | <ul><li>Experience Platform [(권장) 지속적인 데이터 수집을 위한 Analytics Web SDK의 새로운 구현; 이전 데이터를 위한 Analytics Source 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform 웹 SDK의 새 구현](/help/data-ingestion/aepwebsdk.md) </li><li>Adobe Analytics을 웹 SDK으로 마이그레이션</li><li>[Analytics Source 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform 웹 SDK(alloy.js) | 웹 SDK Experience Platform은 Adobe Analytics 구현을 위해 Adobe이 현재 권장하는 방법입니다. Adobe Experience Platform Edge Network을 사용하면 여러 제품으로 전송되는 데이터를 중앙 위치에 전송할 수 있습니다. <p>이 구현 유형에 대한 자세한 내용은 [Adobe Experience Platform Edge Network을 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)을 참조하십시오.</p> | <ul><li>Experience Platform [(권장) 지속적인 데이터 수집을 위한 Analytics Web SDK의 새로운 구현; 이전 데이터를 위한 Analytics Source 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform 웹 SDK의 새 구현](/help/data-ingestion/aepwebsdk.md) </li><li>Platform으로 데이터를 전송하도록 Adobe Analytics Web SDK 구현 구성</li></ul> |
| Experience Platform Web SDK 확장 (태그) | 웹 SDK Experience Platform은 웹 데이터에 대해 Adobe Analytics을 구현하기 위해 Adobe이 현재 권장하는 방법입니다. Adobe Experience Platform Edge Network을 사용하면 여러 제품으로 전송되는 데이터를 중앙 위치에 전송할 수 있습니다. <p>이 구현 유형에 대한 자세한 내용은 [Adobe Experience Platform Web SDK을 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)을 참조하십시오.</p> | <ul><li>Experience Platform [(권장) 지속적인 데이터 수집을 위한 Analytics Web SDK의 새로운 구현; 이전 데이터를 위한 Analytics Source 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform 웹 SDK의 새 구현](/help/data-ingestion/aepwebsdk.md)</li><li>Platform으로 데이터를 전송하도록 Adobe Analytics Web SDK 구현 구성</li></ul> |
| Experience Platform Mobile SDK | 모바일 SDK Experience Platform은 모바일 데이터용 Adobe Analytics을 구현하기 위해 Adobe이 현재 권장하는 방법입니다. Adobe Experience Platform Edge Network을 사용하면 여러 제품으로 전송되는 데이터를 중앙 위치에 전송할 수 있습니다.<p>Adobe Experience Platform Mobile SDK은 Adobe의 Experience Cloud 솔루션과 서비스를 모바일 앱에서 제공하는 데 도움이 됩니다. </p><p>이 구현 유형에 대한 자세한 내용은 [Adobe Experience Platform Mobile SDK을 사용하여 Adobe Analytics 구현](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)을 참조하십시오.</p> | <ul><li>Experience Platform [(권장) 지속적인 데이터 수집을 위한 Analytics Web SDK의 새로운 구현; 이전 데이터를 위한 Analytics Source 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform 웹 SDK의 새 구현](/help/data-ingestion/aepwebsdk.md) </li><li>Platform으로 데이터를 전송하도록 Adobe Analytics Web SDK 구현 구성</li></ul> |
| 대량 데이터 삽입 API | Bulk Data Insertion API(BDIA)는 AppMeasurement과 같은 클라이언트측 라이브러리를 사용하지 않고 서버 호출 데이터를 파일 배치에 업로드할 수 있는 Adobe Analytics 기능입니다. </p><p>이 구현 유형에 대한 자세한 내용은 [대량 데이터 삽입 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)를 참조하십시오.</p> | <ul><li>Experience Platform [(권장) 지속적인 데이터 수집을 위한 Analytics Web SDK의 새로운 구현; 이전 데이터를 위한 Analytics Source 커넥터](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform 웹 SDK의 새 구현](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network 서버 API 및 Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}