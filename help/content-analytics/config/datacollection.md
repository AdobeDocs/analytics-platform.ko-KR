---
title: Content Analytics 데이터 수집
description: Content Analytics에서 데이터를 수집하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: b8b0237a092b37d28bec56bba05c30a853097d4f
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 52%

---


# Content Analytics 데이터 수집

이 문서에서는 Content Analytics가 데이터를 수집하는 방법을 자세히 설명합니다.

## 정의

이 문서의 컨텍스트에서는 다음 정의가 사용됩니다.

* **경험**:
   * **web** 채널의 경우 경험은 전체 웹 페이지에서 텍스트 콘텐츠로 정의됩니다. 데이터 수집의 경우 Content Analytics은 페이지 URL을 기반으로 하는 경험 ID를 기록합니다. 나중에 해당 페이지의 텍스트는 검색 서비스를 통해 캡처됩니다.
   * **mobile** 채널의 경우 Adobe Experience Platform Mobile SDK용 Content Analytics 확장을 사용하여 모바일 앱에서 경험을 정의하고 추적합니다.
* **경험 ID**:
   * 웹 채널의 경우 경험 ID는 관련 URL(기본 URL과 페이지의 콘텐츠를 유도하는 모든 매개 변수)과 [경험 버전](manual.md#versioning)의 고유한 조합입니다.
      * [구성](configuration.md)의 일부로 주어진 전체 URL에 관련된 매개변수를 지정합니다.
      * 사용할 [버전 식별자](manual.md#versioning)를 정의하면 환경의 변경 사항을 적절하게 수집할 수 있습니다.
   * **mobile** 채널의 경우 경험 ID는 `registerExperience` API 호출을 사용한 반환 값입니다.
* **자산**: 이미지입니다. Content Analytics는 자산 URL을 기록합니다.
* **자산 ID**: 자산의 URL입니다.
* **관련 URL**: 기본 URL과 페이지의 콘텐츠를 구동하는 모든 매개변수입니다.


## 기능

Content Analytics을 사용하려면 컨텐츠 이벤트 데이터를 수집하려면 Experience Platform Edge Network Web SDK(웹 채널용) 및 Experience Platform Edge Network Mobile SDK(모바일 채널용)가 필요합니다. 이 이벤트 데이터는 Experience Platform Edge Network(Web SDK, Mobile SDK 또는 Server API) 또는 Analytics 소스 커넥터(예: Adobe AppMeasurement)를 사용하여 기존 동작 데이터와 결합됩니다.

Content Analytics 라이브러리는 다음과 같은 경우 데이터를 수집합니다.

* Content Analytics은 페이지에 로드되거나 모바일 앱 내에서 사용되는 태그 라이브러리에 포함되어 있습니다.
* 페이지 URL 및 자산 URL은 포함된 Tags 라이브러리의 일부인 [Content Analytics 웹 확장](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}에 구성되어 있습니다.
* 자산 URL, 자산 위치 또는 경험 위치는 [Content Analytics 모바일 확장](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)에서 제외되지 않습니다.


## Content Analytics 이벤트

이 섹션에서는 웹 Content Analytics 이벤트에 대한 세부 사항을 자세히 설명합니다. 모바일 Content Analytics 이벤트에 대한 자세한 내용은 [경험 추적](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/experience-tracking/)을 참조하세요.
Content Analytics 이벤트는 다음으로 구성됩니다.

* 표준 필드
   * 타임스탬프
   * ID
* 경험 보기(있는 경우 및 구성된 경우)
* 경험 클릭 수(있는 경우 및 구성된 경우)
* 자산 조회수(있는 경우 및 구성된 경우)
* 자산 클릭 수(있는 경우 및 구성된 경우)

Content Analytics 이벤트는 다음의 시퀀스로 수집됩니다.

1. [기록된 보기 또는 클릭](#recorded-view-or-click)입니다.
1. Content Analytics 이벤트를 보내기 위한 [트리거](#trigger-to-send-a-content-analytics-event).

Content Analytics는 이벤트를 바로 다음에 수집하는 것이 아니라, 보기 또는 클릭을 별도로 수집하여 해당 보기 또는 클릭 직후의 이벤트를 수집하는 방식으로 데이터를 수집하여 그 순서를 반영합니다. 이러한 방식을 사용하여 Content Analytics 데이터를 수집하면 수집되는 데이터 양도 줄어듭니다.

### 기록된 보기 또는 클릭

자산 보기는 다음과 같은 경우 기록됩니다.

* Content Analytics 확장 기능 구성에 따라 자산이 제외되지 않았습니다.
* 자산이 75% 정도 검토 중입니다.
* 해당 자산이 아직 이 페이지에 기록되지 않았습니다.

자산 클릭은 다음과 같은 경우 기록됩니다.

* 자산이 조회되었습니다.
* Content Analytics 확장 기능 구성에 따라 자산이 제외되지 않았습니다.
* 링크인 에셋을 바로 클릭하면 다른 페이지로 연결됩니다.

경험 보기는 다음과 같은 경우 기록됩니다.

* Content Analytics 구성에서 경험이 활성화되었습니다.

경험 클릭은 다음과 같은 경우 기록됩니다.

* 활성화된 링크를 클릭하면 경험이 트리거됩니다.


### Content Analytics 이벤트를 전송하는 트리거

페이지에서 전송된 네트워크 요청 수를 줄이기 위해 Content Analytics은 정보를 수집하지만 해당 정보를 즉시 보내지는 않습니다. 콘텐츠 상호 작용 정보가 수집되며, 해당 정보를 포함하는 이벤트는 다음 트리거 중 하나가 발생할 때만 전송됩니다.

* 웹 SDK 또는 Adobe AppMeasurement에서 이벤트를 전송합니다.
* 표시 여부가 숨김으로 변경되었습니다. 예:
   * 페이지 언로드
   * 탭 전환
   * 브라우저 최소화
   * 브라우저 닫기
   * 화면 잠금
* URL이 변경되어 관련 URL도 수정되었습니다.
* 기록된 자산 보기 및 전송할 준비가 32개를 초과했습니다.

>[!NOTE]
>
>추가 Content Analytics 이벤트는 세션 또는 페이지의 이벤트 수를 기반으로 하는 바운스 비율 정의에 영향을 미칠 가능성이 가장 높습니다.
>

## ID

이 섹션에서는 Content Analytics에서 ID를 처리하는 방법을 설명합니다.

### 웹

Content Analytics은 다음과 같은 방식으로 웹 채널에 대한 ID를 처리합니다.

* ECID는 Content Analytics 스키마의 `identityMap` 부분에 자동으로 채워집니다.
* `identityMap`에 다른 ID 값이 필요한 경우 Web SDK 확장 내의 `onBeforeEventSend` 콜백에서 이러한 값을 설정해야 합니다.
* 스키마는 시스템 소유이므로 필드 기반 결합은 지원되지 않습니다. 따라서 필드 기반 결합을 지원하기 위해 스키마에 다른 필드를 추가할 수 없습니다


Content Analytics ID 데이터와 Web SDK 데이터 ID 데이터가 필드 수준에서 올바르게 결합되는지 확인하려면 이벤트 보내기 ](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/onbeforeeventsend){target="_blank"} 콜백 전에 Web SDK [on을(를) 수정하십시오.

1. Adobe Experience Platform Web SDK 확장 및 Adobe Content Analytics 확장이 포함된 **[!UICONTROL 태그]** 속성으로 이동합니다.
1. ![플러그](/help/assets/icons/Plug.svg) **[!UICONTROL 확장]**&#x200B;을 선택합니다.
1. **[!UICONTROL Adobe Experience Platform Web SDK]** 확장을 선택합니다.
1. **[!UICONTROL 구성]**&#x200B;을 선택합니다.
1. **[!UICONTROL SDK 인스턴스]** 섹션에서 아래로 스크롤하여 **[!UICONTROL 데이터 수집]** - **[!UICONTROL On before event send 콜백]**&#x200B;로 이동합니다.

   ![On before event send 콜백](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. **[!UICONTROL &lt;/> On before event send 콜백 코드 제공]**&#x200B;을 선택합니다.
1. 다음 코드를 추가합니다.

   ```JavaScript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![On before event send 콜백](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. 코드를 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.
1. 확장을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.
1. 태그 속성에 대한 업데이트를 [게시](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/publish/overview)합니다.


### 모바일

모바일 앱에서 ID를 사용하여 작업하는 방법에 대한 자세한 내용은 [Experience Cloud ID 서비스 확장에 대한 ID](https://developer.adobe.com/client-sdks/home/base/mobile-core/identity/) 및 [Edge Network 모바일 확장에 대한 ID](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)를 참조하십시오.

모바일 앱에서 ID가 바뀌자마자 Content Analytics 데이터의 현재 [batch](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/#batching-settings)이(가) 재설정되어 새 ID에 대한 Content Analytics 데이터의 새 컬렉션을 시작합니다.

## 스키마

Experience Platform은 특정 Content Analytics 스키마를 기준으로 Content Analytics 데이터를 데이터 세트에 수집합니다. 참조 스키마는 공개적으로 사용 가능합니다.

* [디지털 자산 스키마](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Digital Experience 스키마](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [경험 이벤트 컨텐츠 스키마](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
