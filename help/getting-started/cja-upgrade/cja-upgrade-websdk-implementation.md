---
title: Customer Journey Analytics으로 업그레이드할 때 웹 SDK 구현 옵션 이해
description: Customer Journey Analytics으로 업그레이드할 때의 웹 SDK 구현 옵션에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Customer Journey Analytics으로 업그레이드할 때 웹 SDK 구현 옵션 이해 {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="웹 SDK JavaScript 라이브러리(alloy.js)"
>abstract="사이트의 각 페이지에 웹 SDK 라이브러리(alloy.js)를 포함합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="웹 SDK 태그 확장"
>abstract="(권장) 태그를 아직 사용하지 않는 경우 사이트에 태그 로더를 설치합니다. 이미 태그를 사용 중인 경우 태그 속성에 Web SDK 확장 기능을 추가할 수 있습니다. 이 옵션에는 Adobe Experience Platform 데이터 수집 및 서드파티 태그 관리 시스템 내의 태그를 사용하는 구현이 포함됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM 패키지"
>abstract="데이터 수집 API를 사용하여 데이터를 데이터스트림으로 직접 전송합니다. 인증되지 않은(클라이언트-서버) 유형과 인증된(서버-서버) 유형이 모두 지원됩니다."

<!-- markdownlint-enable MD034 -->

Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 권장 프로세스는 Customer Journey Analytics에 기본 데이터 수집 방법인 Experience Platform 웹 SDK의 새로운 구현입니다.

Adobe Experience Platform Web SDK을 사용하는 방법에는 세 가지가 있습니다.

* [웹 SDK Adobe 태그 확장](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension): 이 메서드를 사용하는 것이 좋습니다. 사이트에 태그 로더를 설치한 다음 Adobe Experience Platform 데이터 수집 UI를 사용하여 구현을 구성합니다.

* [Web SDK JavaScript 라이브러리](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): CDN에서 호스팅하는 라이브러리 파일을 참조하거나 자체 인프라를 사용하여 라이브러리 파일을 호스팅합니다. 사이트의 코드 내에서 라이브러리를 호출합니다.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): NPM 패키지 관리자를 사용하여 웹 SDK을 사이트에 설치합니다.

자세한 내용은 Experience Platform 웹 SDK 안내서의 [웹 SDK 설치 개요](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview)를 참조하십시오.



