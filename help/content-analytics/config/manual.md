---
title: 콘텐츠 분석 수동 구성
description: 콘텐츠 분석을 수동으로 구성하는 방법
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a3d974733eef42050b0ba8dcce4ebcccf649faa7
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 70%

---

# 콘텐츠 분석 수동 구성

이 문서에서는 콘텐츠 분석 구성의 데이터 수집을 시작 또는 중지하거나 콘텐츠 분석 구현을 편집하는 데 필요한 수동 작업에 대해 자세히 설명합니다.

다음 수동 구성 작업을 사용할 수 있습니다.

## 데이터 수집 시작

구현된 콘텐츠 분석 구성에 대한 데이터 수집을 시작하려면 다음을 수행합니다.

1. [게시 흐름](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/publish/overview){target="_blank"}을 따릅니다. 콘텐츠 분석 구성이 포함된 태그 속성에 대한 라이브러리를 정상적으로 게시합니다.

1. 콘텐츠 분석에 따라 개발, 스테이징 또는 게시 환경의 페이지 `<head>` 요소에 임베드된 코드를 [설치](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/publish/environments/environments#installation)합니다.


## 데이터 수집 중지

구현된 콘텐츠 분석 구성에 대한 데이터 수집을 중지하려면 다음을 수행합니다.

1. 콘텐츠 분석에 따라 개발, 스테이징 또는 프로덕션 환경의 페이지 `<head>` 요소에서 [임베드된 코드](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/publish/environments/environments)를 제거합니다.
1. 콘텐츠 분석 구성과 연결된 태그 속성을 [삭제](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/publish/overview)합니다.



## 데이터 수집 수정

[가이드 구성 마법사](guided.md)를 사용하여 구현된 구성을 약간 변경할 수 있습니다. 예를 들어 데이터 보기를 변경하거나 경험을 활성화 또는 비활성화할 수 있습니다.

콘텐츠 분석 구성과 연결된 태그 속성에서 [Adobe Content Analytics 확장 기능](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview)을 사용하여 다음 아티팩트를 변경할 수 있습니다.

* [샌드박스 및 데이터스트림](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}

  >[!CAUTION]
  >
  >Adobe Content Analytics 확장 기능에서 구성한 샌드박스 및 데이터스트림이 [가이드 구성](guided.md) 초기 단계에서 콘텐츠 분석에 대해 구성되어 있는지 확인하십시오. 이 구성을 사용하면 필요한 모든 아티팩트를 사용할 수 있습니다.<br/><br/>또한 샌드박스 또는 데이터스트림에 대한 업데이트가 동일한 샌드박스 또는 데이터스트림을 사용하도록 구성된 다른 콘텐츠 분석 구성을 방해하지 않는지도 확인하십시오.
  >

* [경험 캡처 및 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  경험을 활성화하거나 비활성화하고 정규 표현식과 쿼리 매개변수의 조합을 편집하여 웹 사이트에서 콘텐츠가 렌더링되는 방식을 결정할 수 있습니다.

* [이벤트 세그먼트화](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  정규 표현식을 편집하여 페이지와 자산을 세그먼트화하는 방법을 수정할 수 있습니다.


Adobe Content Analytics 확장 기능에서 변경 사항을 적용한 후에는 [게시 흐름](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/publish/overview){target="_blank"}을 사용하여 적용한 변경 사항에 따라 데이터 수집을 시작해야 합니다.



>[!MORELIKETHIS]
>
>[가이드 구성](guided.md)
>&#x200B;>[데이터 수집 태그 게시 개요](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/publish/overview)
>


## 버전 관리

콘텐츠 분석 경험을 수집하려면 버전 관리를 구현하여 새로운 경험(웹 페이지 변경 사항)이 적절하게 수집되도록 해야 합니다.

버전 관리를 구현하려면 분석하려는 경험에 대한 페이지에 글로벌 `adobe.getContentExperienceVersion` 함수를 추가합니다.

`adobe.getContentExperienceVersion` 함수는 버전을 식별하기 위해 임의로 선택한 문자열 값을 반환해야 합니다. 버전은 [경험 ID URL](/help/content-analytics/report/components.md#experience-metadata)에 추가됩니다.

함수가 존재하지 않거나 함수에서 값이 반환되지 않으면 `NoVersion` 값이 기본값으로 사용됩니다.

### 예

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```

## ID

Content Analytics은 다음과 같은 방식으로 ID를 처리합니다.

* ECID는 Content Analytics 스키마의 `identityMap` 부분에 자동으로 채워집니다.
* `identityMap`에 다른 ID 값이 필요한 경우 Web SDK 확장 내의 `onBeforeEventSend` 콜백에서 이러한 값을 설정해야 합니다.
* 스키마가 시스템 소유이므로 필드 기반 결합은 지원되지 않습니다. 따라서 필드 기반 결합을 지원하기 위해 스키마에 다른 필드를 추가할 수 없습니다


Content Analytics ID 데이터와 Adobe Experience Platform Web SDK 데이터 ID 데이터가 필드 수준에서 올바르게 결합되는지 확인하려면 이벤트를 보내기 [&#128279;](https://experienceleague.adobe.com/ko/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"} 콜백 전에 웹 SDK on을(를) 수정해야 합니다.

1. Adobe Experience Platform Web SDK 확장 및 Adobe Content Analytics 확장이 포함된 **[!UICONTROL 태그]** 속성으로 이동합니다.
1. ![플러그](/help/assets/icons/Plug.svg) **[!UICONTROL 확장]**&#x200B;을 선택합니다.
1. **[!UICONTROL Adobe Experience Platform Web SDK]** 확장을 선택하십시오.
1. **[!UICONTROL 구성]**&#x200B;을 선택합니다.
1. **[!UICONTROL SDK 인스턴스]** 섹션에서 아래로 스크롤하여 **[!UICONTROL 데이터 수집]** - **[!UICONTROL 이벤트 전송 콜백 전 켜기]**&#x200B;로 이동합니다.

   ![이벤트 전송 콜백 전 ](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. 이벤트 전송 콜백 코드&#x200B;**전에**&lt;/> 제공 기능을 선택합니다.
1. 다음 코드를 추가합니다.

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![이벤트 전송 콜백 전 ](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택하여 코드를 저장합니다.
1. 확장을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.
1. 태그 속성에 대한 업데이트를 [게시](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/publish/overview)합니다.





