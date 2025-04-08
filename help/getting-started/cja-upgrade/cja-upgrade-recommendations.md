---
title: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 단계에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dfc9ba843fbddc135c0f8160fb672adb36e9146f
workflow-type: tm+mt
source-wordcount: '3281'
ht-degree: 18%

---

# Adobe Analytics에서 Customer Journey Analytics으로 업그레이드

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 [권장되는 업그레이드 단계](#recommended-upgrade-steps-for-most-organizations)를 따를 수 있습니다. 또는 조직의 고유 상황에 맞게 [업그레이드 단계를 동적으로 생성](#dynamically-generate-upgrade-steps-for-your-organization)할 수 있습니다.

## 대부분의 조직에 권장되는 업그레이드 단계 {#upgrade-process}

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 권장 프로세스는 Experience Platform Web SDK의 새로운 구현이며, Customer Journey Analytics에서 선호하는 데이터 수집 방법입니다. 웹 SDK과 함께 Adobe에서는 Analytics 소스 커넥터를 사용하여 Customer Journey Analytics으로 전환하는 것을 권장합니다. Analytics 소스 커넥터를 사용하여 이전 Adobe Analytics 데이터를 유지하고 병렬 데이터 비교를 수행할 수 있습니다.

Experience Platform Web SDK을 사용하여 내역 데이터가 충분하고 Customer Journey Analytics으로 완전히 전환한 후에는 Analytics 소스 커넥터를 끄고 웹 SDK을 독점적으로 사용할 수 있습니다.

>[!NOTE]
>
>이 섹션에 설명된 업그레이드 단계가 조직에 실용적이지 않은 경우 Customer Journey Analytics 업그레이드 안내서 를 사용하여 조직의 고유 상황에 맞는 업그레이드 단계를 동적으로 생성합니다. (Customer Journey Analytics에서 가이드에 액세스하려면 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics으로 업그레이드]**&#x200B;를 선택합니다. 화면에 표시되는 안내를 따릅니다.)

### 높은 수준 권장 업그레이드 프로세스 {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Adobe Analytics의 이전 데이터"
>abstract="Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform 및 Customer Journey Analytics로 가져옵니다."

<!-- markdownlint-enable MD034 -->

1. **지속적인 데이터 수집을 위해 Experience Platform Web SDK 구현**

   Experience Platform Web SDK의 새로운 구현은 Customer Journey Analytics에 대한 데이터를 수집하는 가장 좋은 방법입니다. Customer Journey Analytics 구현을 위한 가장 성능적이고, 간단하며, 미래에 대비할 수 있는 방법이기 때문에 Customer Journey Analytics을 최대한 활용할 수 있는 최고의 기반을 제공합니다.

   * Adobe Experience Platform은 실시간 개인화 사용 사례를 지원하기 위해 구축되었으므로 성능 높은 보고 및 데이터 가용성

   * 다른 Experience Cloud 제품(AJO, RTCDP 등) 간에 Adobe Experience Cloud 데이터 수집을 위한 구현 통합

   * Adobe Analytics 명명법(prop, eVar, 이벤트 등)에 의존하지 않음

1. **이전 데이터를 가져올 Adobe Analytics 소스 커넥터 설정**

   Customer Journey Analytics에서 Experience Platform Web SDK을 사용하는 것으로 원활하게 전환하는 데 도움이 되도록 Adobe에서는 Adobe Analytics 소스 커넥터 를 사용하는 것이 좋습니다. 이렇게 하면 Customer Journey Analytics의 기존 Adobe Analytics 구현에서 새 Experience Platform 웹 SDK 구현의 데이터와 나란히 내역 데이터를 유지하고 데이터를 볼 수 있습니다.

   Analytics 소스 커넥터를 사용하면 다음 작업을 수행할 수 있습니다.

   * Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform 및 Customer Journey Analytics로 가져옵니다.

     내역 Adobe Analytics 데이터를 유지해야 하는 동안 Analytics 소스 커넥터를 계속 실행할 수 있습니다.

   * Customer Journey Analytics 내에서 원래 Adobe Analytics 구현(AppMeasurement, Analytics 확장 또는 Web SDK 확장)으로 수집된 데이터를 봅니다. 이 데이터를 새 웹 SDK 구현의 데이터와 나란히 비교할 수 있습니다.

     차이점을 잘 알고 있을 때까지 Analytics 소스 커넥터를 계속 실행할 수 있습니다. <!--elaborate on what those differences are? -->

   독립 실행형 구현으로서의 Analytics 소스 커넥터는 Customer Journey Analytics 사용에 권장되는 장기적인 방법이 아닙니다. 이는 지연 시간이 길고, 복잡하고 복잡한 스키마, Adobe Analytics 명명법(prop, eVar 등)에 의존하고, 결국 Analytics 소스 커넥터에서 권장되는 웹 SDK 구현으로 이동하기 어렵기 때문입니다.

### 자세한 권장 업그레이드 단계

다음 단계에서는 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 권장 프로세스에 대해 간략히 설명합니다.

각 단계는 보다 자세한 프로세스에 대한 높은 수준의 설명을 제공합니다. 각 단계에 대한 링크를 따라 관련 작업을 완료한 후 이 페이지로 돌아와 프로세스의 다음 단계를 계속합니다.

1. [XDM 스키마 아키텍처를 계획하십시오](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Adobe Experience Platform에서 원하는 사용자 지정 스키마를 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   스키마를 생성할 때 다음 옵션을 고려하십시오.

   * Customer Journey Analytics을 RTCDP과 통합하려면 [Customer Journey Analytics에서 사용할 XDM 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)에 설명된 대로 스키마에서 **[!UICONTROL 프로필]** 옵션을 활성화해야 합니다. 이 옵션이 활성화된 경우 이 스키마를 기반으로 한 데이터 세트에 데이터를 수집하면 해당 데이터가 실시간 고객 프로필에 병합됩니다.

   * 스트리밍 미디어 데이터를 포함하려면 [스트리밍 데이터를 수집 및 사용하도록 스키마를 구성](/help/data-ingestion/streaming.md)해야 합니다.

1. [Adobe Experience Platform에서 데이터 세트를 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (선택 사항) Adobe Analytics에서 분류 데이터를 사용하는 경우 Customer Journey Analytics에서 분류 데이터를 데이터 세트에 추가할 수 있습니다.

   이렇게 하려면 [분류 데이터를 포함하는 각 차원에 대한 조회 데이터 집합을 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. AppMeasurement 또는 Analytics 확장 기능(태그)을 사용하는 Adobe Analytics 구현의 경우 [Adobe Experience Platform에서 데이터 스트림을 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Web SDK을 사용하는 Adobe Analytics 구현의 경우 데이터 스트림이 이미 있습니다. 자세한 내용은 [데이터를 플랫폼으로 보내도록 기존 Adobe Analytics Web SDK 구현 구성](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)을 참조하십시오.

1. [데이터스트림에 서비스로 Adobe Experience Platform 추가](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (선택 사항) Customer Journey Analytics을 Adobe Journey Optimizer과 통합하려면 Adobe Journey Optimizer에서 사용할 개인화 개체를 구현에 사용하십시오.

1. Customer Journey Analytics 구현을 위해 Experience Platform Web SDK을 구현하는 방법을 설명하는 섹션을 확장한 다음 관련 단계를 완료합니다.

   +++수동 구현(JS 파일)

   1. [사이트에 alloy.js 추가](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. XDM 개체를 채우고 데이터스트림으로 보냅니다.

+++

   +++태그

   1. [태그 속성을 만들고 Adobe Experience Platform Web SDK 확장을 추가합니다](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [태그 속성에 Adobe Experience Platform Web SDK 확장 기능 추가](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [사이트에서 로더 태그를 구현합니다](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [태그에 XDM 데이터 수집 논리 추가](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Edge Network API를 사용하여 데이터를 원하는 데이터 스트림으로 전송합니다.

+++

1. [웹 SDK 구현이 데이터 집합에 데이터를 보내고 있는지 확인](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Customer Journey Analytics에서 연결을 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (선택 사항) 웹 데이터를 콜 센터 데이터와 같은 다른 채널의 데이터와 연결합니다.

   [콜센터 및 웹 데이터 가져오기](/help/use-cases/cross-channel/call-center.md)에 설명된 대로 Customer Journey Analytics 연결에 추가 데이터 세트를 추가하여 이 작업을 수행할 수 있습니다.

1. [Customer Journey Analytics에서 데이터 보기를 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [데이터가 Customer Journey Analytics의 데이터 보기로 이동하는지 확인](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. Adobe Analytics 환경에서 [Analytics 인벤토리를 사용](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory)하여 프로젝트 및 구성 요소 수, 보고서 세트, 사용자 등을 포함하여 Adobe Analytics 환경에 대한 포괄적인 개요를 확인하세요.

1. [프로젝트 및 구성 요소 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (선택 사항) Adobe Analytics에서 마케팅 채널을 사용하는 경우 [Customer Journey Analytics에서 마케팅 채널 파생 필드를 만들 수 있습니다](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   파생 필드는 Customer Journey Analytics 실시간 보고의 중요한 측면입니다. 파생 필드를 사용하면 사용자 정의 가능한 규칙 빌더를 통해 즉석에서 (복잡한) 데이터 조작을 정의할 수 있습니다.

   파생 필드의 한 가지 사용은 하나 이상의 조건(예: URL 매개 변수, 페이지 URL 또는 페이지 이름)을 기반으로 적절한 마케팅 채널을 결정하는 파생된 마케팅 채널 필드를 정의하는 것입니다.

   파생 필드에서 [마케팅 채널 함수 템플릿](/help/data-views/derived-fields/derived-fields.md#marketing-channels)을(를) 사용하여 마케팅 채널의 파생 필드를 신속하게 만듭니다.

1. 이전 구현의 Adobe Analytics 데이터와 새 구현의 Customer Journey Analytics 데이터를 비교하고, 차이점 및 차이점이 존재하는 이유를 이해해야 합니다. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Analytics 소스 커넥터를 사용하여 Adobe Analytics에서 내역 데이터 가져오기:

   >[!NOTE]
   >
   >이전에 Analytics 소스 커넥터를 만들지 않은 경우 다음 단계를 사용하십시오.
   >
   >Customer Journey Analytics에서 Analytics 소스 커넥터를 이미 사용하고 있는 경우 [Analytics 소스 커넥터에서 Customer Journey Analytics용 웹 SDK으로 전환](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)의 단계를 따르십시오.

   1. [Analytics 소스 커넥터용 XDM 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Analytics 소스 커넥터가 없는 경우 [Analytics 소스 커넥터를 만들고 필드를 XDM 스키마에 매핑하십시오](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      또는

      Analytics 소스 커넥터가 이미 있는 경우 [소스 커넥터의 필드를 XDM 스키마에 매핑](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)하십시오.

   1. [연결에 Analytics 원본 커넥터 데이터 집합을 추가](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)합니다.

1. 사용자 온보딩을 계획합니다.

   Adobe Analytics와 마찬가지로 Analysis Workspace는 Customer Journey Analytics의 주요 사용자 대상 도구입니다. 단, Customer Journey Analytics에서 Analysis Workspace를 사용할 때 사용자가 알아 두어야 할 몇 가지 주요 차이점이 있습니다.

   사용자가 Customer Journey Analytics에서 Analysis Workspace의 주요 차이점을 숙지할 수 있도록 충분한 시간(3~6개월)을 할애하도록 하십시오.

   Adobe Analytics와 Customer Journey Analytics의 주요 차이점에 대한 자세한 내용은 [Adobe Analytics 사용자를 위한 사용 안내서](/help/getting-started/aa-to-cja-user.md)를 참조하십시오.

1. Customer Journey Analytics의 [기능 지원에 대해 알아보세요](/help/getting-started/aa-vs-cja/cja-aa.md). 대부분의 Adobe Analytics 기능은 Customer Journey Analytics에서 지원되며, Customer Journey Analytics에서 많은 추가 기능을 사용할 수 있습니다.

1. Customer Journey Analytics 웹 SDK 구현이 완료되고 수집 중인 데이터에 익숙해지면 Adobe Analytics을 비활성화하십시오.

   Adobe은 Customer Journey Analytics을 구현한 후 일정 기간 동안 Adobe Analytics 환경을 계속 실행할 것을 권장합니다.

   업그레이드 중이나 업그레이드 후 Adobe Analytics을 사용하는 방법과 Adobe Analytics을 사용하지 않도록 설정하는 제안 시점에 대한 자세한 내용은 [Customer Journey Analytics으로 업그레이드한 후 Adobe Analytics이 필요한 시간 평가](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)를 참조하십시오.

## 조직에 대한 업그레이드 단계를 동적으로 생성

타임라인 및 리소스 제한과 같은 여러 요인에 따라 [권장 업그레이드 단계 이해](#recommended-upgrade-steps-for-most-organizations)에 설명된 권장 업그레이드 단계가 조직에 실용적이지 않을 수 있습니다. 이 경우 조직의 고유 환경에 대한 업그레이드 단계를 동적으로 생성할 수 있습니다. 이러한 단계를 생성하는 프로세스는 Customer Journey Analytics에 대한 액세스 권한이 이미 있는지 여부에 따라 다릅니다.

### Customer Journey Analytics에 액세스할 수 있는 고객

조직의 고유 환경에 대한 업그레이드 단계를 동적으로 생성하려면 다음을 수행합니다.

1. Customer Journey Analytics 업그레이드 안내서를 완료합니다.

   Customer Journey Analytics에서 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics으로 업그레이드]**&#x200B;를 선택합니다. 화면에 표시되는 안내를 따릅니다.

   이 업그레이드 안내서를 완료한 후 조직 요구 사항에 맞는 최적의 업그레이드 단계를 설명하는 단계별 지침이 제공됩니다. 기존 Adobe Analytics 환경 및 Customer Journey Analytics 목표에 가장 적합한 업그레이드 단계입니다. 업그레이드 단계는 공유 가능한 링크 또는 다운로드 가능한 .csv 파일로 사용할 수 있습니다.

1. 생성된 단계별 지침에 따라 Customer Journey Analytics으로 업그레이드하십시오.

### Customer Journey Analytics에 대한 액세스 권한이 없는 고객의 경우

조직의 고유 환경에 대한 업그레이드 단계를 동적으로 생성하려면 다음을 수행합니다.

1. Adobe 계정 팀에 문의하여 Customer Journey Analytics 업그레이드 가이드를 완료합니다.

   Adobe 계정 팀은 업그레이드 안내서를 통해 질문, 답변 및 조직에 고유한 동적으로 생성된 업그레이드 단계가 포함된 .csv 파일을 제공할 수 있습니다.

   Adobe 계정 팀에 문의하기 전에 Customer Journey Analytics 업그레이드 가이드에 포함된 질문에 대해 숙지하고 답변을 파악하십시오. Customer Journey Analytics 업그레이드 안내서에는 다음과 같은 질문과 대답이 포함되어 있습니다.


   | 질문 | 사용 가능한 답변 | 추가 정보 |
   |---------|----------|---------|
   | 현재 사용 중인 Adobe Analytics 구현 방식을 선택하십시오. 이 정보는 Customer Journey Analytics 업그레이드 시 사용할 수 있는 대체 업그레이드 옵션에 영향을 줄 수 있습니다. | 하나 선택: <ul><li>**AppMeasurement:**<br/>&#x200B;페이지에 AppMeasurement.js를 로드하고 s 개체(예: s.eVar1)를 사용하여 Adobe에 데이터를 전송하는 JavaScript 구현입니다.</li><li>**Adobe Analytics 확장 기능(태그):** <br/>Adobe Experience Platform 데이터 수집(이전 Launch)을 로드하는 태그 구현입니다. 이 태그에는 Adobe Analytics 확장 기능이 설치되어 있습니다.</li><li>**Experience Platform Web SDK 확장 기능(태그):**<br/> Adobe Experience Platform 데이터 수집(이전 Launch)을 로드하는 태그 구현입니다. 이 태그에는 Web SDK 확장 기능이 설치되어 있습니다.</li><li>**Experience Platform Web SDK(alloy.js):** 페이지에 Web SDK 라이브러리(alloy.js)를 로드하고 JSON 페이로드를 사용하여 Adobe에 데이터를 보내는 JavaScript 구현입니다.</li><li>**대량 데이터 삽입 API:**<br/> 데이터 삽입 API 또는 대량 데이터 삽입 API를 사용하는 구현입니다.</li><li>**Experience Platform Mobile SDK:**<br/> Adobe Experience Platform Mobile SDK을 사용하는 구현입니다.</li><li>**타사 태그 관리 도구를 사용하는 AppMeasurement:**<br/> 타사 태그 관리 도구를 사용하는 구현입니다.</li><li>**Adobe Analytics 이외의 제품:**<br/> Google Analytics과 같은 Adobe Analytics 이외의 제품에 대한 데이터를 수집하는 구현입니다. 이 옵션을 선택하면 Adobe Analytics가 아닌 제품에서 Customer Journey Analytics로 업그레이드할 때 적용되지 않는 업그레이드 안내서의 여러 옵션이 비활성화됩니다. </li><li>**알 수 없음:**<br/> 구현을 관리하는 사람이 아닌 경우 이 옵션을 일시적으로 선택할 수 있습니다.</li></ul><p>해당하는 경우 선택:<ul><li>**현재 구현에서는 Analytics 소스 커넥터를 사용합니다.**<br/> Analytics 소스 커넥터를 사용하면 Customer Journey Analytics에서 쉽게 가치를 얻을 수 있지만 Adobe Analytics과 Customer Journey Analytics 모두에 대해 비용을 지불해야 합니다. 이 안내서는 독립적인 Web SDK 구현으로 전환하는 방법을 설명합니다.</li></ul></p> | <ul><li>[Adobe Analytics 구현 및 Customer Journey Analytics 업그레이드에 미치는 영향을 이해합니다](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[Analytics 소스 커넥터에서 Customer Journey Analytics용 웹 SDK으로 전환](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | 대부분의 Adobe Analytics 기능은 Customer Journey Analytics에서 바로 사용할 수 있습니다. 그러나 다음 기능은 업그레이드 프로세스에서 고려해야 합니다. 사용하려는 기능을 선택하십시오. | 해당되는 모든 항목 선택:<ul><li>**Adobe Analytics의 이전 데이터:**</br>&#x200B;이전 Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform 및 Customer Journey Analytics으로 가져옵니다.</li><li>**Adobe Analytics의 구성 요소 및 프로젝트:**</br> Adobe Analytics의 구성 요소에는 프로젝트(관련 자유 형식 테이블 및 시각화 포함), 세그먼트 및 계산된 지표가 포함됩니다.</li><li>**Activity Map 오버레이 및 링크 추적:**</br>&#x200B;링크 추적 데이터를 사이트에 오버레이로 볼 수 있는 브라우저 확장 기능입니다.</li><li>**분류 데이터:**</br>&#x200B;데이터를 별도의 차원으로 그룹화하거나 분류합니다.</li><li>**마케팅 채널:**</br>&#x200B;고객이 사이트에 도착하는 방식을 분류하는 규칙을 만듭니다.</li><li>**Data Warehouse:**</br>&#x200B;처리된 데이터를 Adobe Analytics에서 스프레드시트 형식으로 내보냅니다.</li><li>**데이터 피드:**Customer Journey Analytics에서는 데이터 피드에 대한 정확한 대체 요소를 아직 사용할 수 없습니다. 그러나 전체 테이블 내보내기, Platform 데이터 세트 내보내기, BI 도구 통합 및 보고 API와 같은 기능을 사용하여 유사한 기능을 수행할 수 있습니다.</br></li><li>**스트리밍 미디어 데이터:**</br>&#x200B;오디오, 비디오 또는 스트리밍된 콘텐츠와 같은 미디어의 데이터 수집을 전문으로 하는 Adobe Analytics 및 Customer Journey Analytics의 추가 기능입니다.</li></ul> | <ul><li>[Customer Journey Analytics으로 업그레이드할 때 Adobe Analytics 기능 지원 이해](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | 대부분의 새로운 기능은 Customer Journey Analytics에서 바로 사용할 수 있습니다. 그러나 다음 기능은 업그레이드 프로세스에서 고려해야 합니다. 사용하려는 기능을 선택하십시오. | 해당되는 모든 항목 선택:<ul><li>**수집된 데이터를 다른 소스의 데이터와 연결(예: 연락처 센터 데이터):**</br>(권장) 다양한 웹, 모바일 및 오프라인 속성의 데이터를 연결하여 고객 행동에 대한 통합된 단일 보기를 만듭니다. 다른 채널의 분석 데이터를 결합하는 이 기능은 Customer Journey Analytics의 기본 사용 사례입니다.</li><li>**사용자 지정 차원을 사용하여 다른 데이터 세트의 히트를 연결합니다.**<br/>&#x200B;데이터 세트에서 기본 식별자(예: Experience Cloud ID)를 공유하지 않는 경우 로그인 사용자 이름 또는 이메일 주소와 같은 다른 차원을 사용하여 해당 데이터를 함께 연결할 수 있습니다.</li><li>**Adobe Journey Optimizer과 통합:**<br/>&#x200B;고객에게 연관성 있고 상황에 맞는 개인화된 경험을 제공합니다.</li><li>**Adobe Real-Time CDP과 통합:**<br/>&#x200B;여러 소스의 프로필 데이터를 결합하여 사용자 트레이트에 따라 대상 및 세그먼트를 생성합니다.</li><li>**Adobe Target(A4T)와 통합:**<br/> Adobe에서는 개인화 사용 사례를 위해 Adobe Journey Optimizer과 통합하는 것이 좋습니다. Adobe Target과 통합하는 것은 가능하지만 단기적인 솔루션일 뿐입니다.</li><li>**Adobe Audience Manager과 통합:**<br/> Adobe에서는 대상 기반 사용 사례를 위해 Adobe Real-time CDP와 통합하는 것이 좋습니다. Audience Manager와 통합하는 것은 가능하지만 단기적인 솔루션일 뿐입니다.</li></ul> | [Customer Journey Analytics의 고유한 기능 이해](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | Adobe Analytics와 Customer Journey Analytics를 궁극적으로 어떻게 사용할 것인지 선택: | 하나 선택: <ul><li>**Adobe Analytics에서 Customer Journey Analytics으로 완전히 이동하려고 합니다.**<br/>(권장) Adobe에서는 Adobe Analytics에서 Customer Journey Analytics으로 완전히 전환할 것을 권장합니다. 전환 기간 동안 Customer Journey Analytics와 함께 Adobe Analytics를 실행하여 데이터를 나란히 비교하는 계획을 세워야 합니다. 데이터에 익숙해지면 Adobe Analytics를 비활성화할 수 있습니다.</li><li>**두 Analytics 제품을 모두 보관하려고 합니다.**<br/>(권장되지 않음) 이 옵션을 선택하면 Adobe과의 계약에 Adobe Analytics과 Customer Journey Analytics이 모두 포함되어 있으므로 시간이 지남에 따라 조직에 더 많은 비용이 들 수 있습니다.</li></ul> | [Customer Journey Analytics으로 업그레이드한 후 Adobe Analytics을 비활성화할 시기를 평가합니다](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | Customer Journey Analytics 스키마를 설정하는 방법 선택: | 하나 선택: <ul><li>**조직에 맞는 스키마를 사용하고 싶습니다.**</br>(권장) 스키마를 사용자 지정하면 조직에서 필요한 것만 추적하고 지저분하고 불필요한 필드에 연결된 오버헤드를 방지할 수 있습니다. 이 옵션에는 Web SDK가 추가한 필드 그룹과 조직에 맞게 사용자 정의된 필드 그룹이 포함됩니다.</li><li>**기본 Adobe Analytics 스키마를 사용하려고 합니다.**</br>(권장되지 않음) Adobe Analytics 스키마에 1,000개 이상의 필드가 포함되어 있어 스키마가 복잡하고 복잡할 수 있습니다. 귀하의 조직이 Customer Journey Analytics에서 사용되지 않는 기존 개념인 Prop 및 eVars 개념을 계속 고수해야 합니다. 다른 Adobe Experience Platform 서비스와 통합하는 것은 더 어렵습니다.</li></ul> | [Customer Journey Analytics에 대한 스키마 선택](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | Customer Journey Analytics를 구현하는 데 선호하는 방식 선택: | <ul><li>**수동 구현(alloy.js):**<br/>&#x200B;사이트의 각 페이지에 웹 SDK 라이브러리(alloy.js)를 포함하십시오.</li><li>**태그:**<br/>(권장) 태그를 아직 사용하지 않는 경우 사이트에 태그 로더를 설치하십시오. 이미 태그를 사용 중인 경우 태그 속성에 Web SDK 확장 기능을 추가할 수 있습니다. 이 옵션에는 Adobe Experience Platform 데이터 수집 및 서드파티 태그 관리 시스템 내 태그를 사용한 구현이 포함됩니다.</li><li>**API:**<br/>&#x200B;데이터 수집 API를 사용하여 데이터스트림으로 직접 데이터를 전송합니다. 인증되지 않은 유형(클라이언트-서버)과 인증된 유형(서버-서버)이 모두 지원됩니다.</li></ul> | [Customer Journey Analytics으로 업그레이드할 때 웹 SDK 구현 옵션 이해](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | (선택 사항) 대체 업그레이드 방법을 선택합니다 | <ul><li>**Analytics 소스 커넥터 사용:**<br/>(권장되지 않음) Analytics 소스 커넥터를 Customer Journey Analytics의 유일한 구현 경로로 사용할 수 있습니다.<p>이 옵션을 사용하면 데이터를 Customer Journey Analytics으로 빠르게 전송하여 구현 시간을 절약할 수 있습니다. 그러나 이 솔루션은 지연 시간이 길고 향후 Adobe Analytics에서 이동하기 어려운 등 다양한 단점을 가지고 있습니다.</p></li><li>**Web SDK에서 내 AppMeasurement 논리를 사용하려고 합니다.**<br/> XDM 개체를 통해 데이터를 보내는 대신 데이터 개체를 통해 AppMeasurement 형식으로 모든 변수를 보냅니다.<p>이 옵션을 사용하면 처음부터 XDM 개체를 채우는 대신 AppMeasurement 논리를 XDM에 매핑할 수 있으므로 구현 시간을 절약할 수 있습니다. 그러나 나중에 추가하는 모든 필드를 데이터스트림의 XDM에 매핑해야 하므로 시간이 지남에 따라 복잡성이 증가합니다.</p></li><li>**추가 구성 없이 데이터 레이어를 Adobe으로 전송하려고 합니다.**<br/> XDM 개체를 통해 데이터를 전송하는 대신 데이터 개체를 통해 전체 데이터 레이어를 Adobe으로 전송할 수 있습니다.<p>이 옵션을 사용하면 처음부터 XDM 개체를 채우는 대신 데이터 레이어를 XDM에 매핑할 수 있으므로 구현 시간이 절약됩니다. 그러나 Adobe가 즉시 해석할 수 없는 상당한 양의 데이터가 전송되므로, 이러한 매핑에는 많은 작업이 필요합니다. 또한 이 옵션을 선택하면 나중에 데이터에 추가하는 모든 필드를 데이터스트림의 XDM에 매핑해야 하므로 시간이 지남에 따라 복잡성이 증가합니다.</p></li></ul> | <ul><li>[대체 업그레이드: Customer Journey Analytics으로 업그레이드하려면 Analytics 소스 커넥터만 사용하십시오](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[대체 요소 업그레이드: Experience Platform Web SDK 및 Customer Journey Analytics에서 AppMeasurement 데이터 수집 사용](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[대체 요소 업그레이드: 데이터 레이어를 Customer Journey Analytics으로 보내기](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   Adobe 계정 팀과 함께 이 업그레이드 가이드를 완료하면 질문, 답변 및 기존 Adobe Analytics 환경과 Customer Journey Analytics에 대한 목표에 가장 잘 부합하는 동적으로 생성된 업그레이드 단계가 포함된 .csv 파일이 제공됩니다.

1. .csv 파일에서 생성된 단계별 지침에 따라 Customer Journey Analytics으로 업그레이드하십시오.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->
