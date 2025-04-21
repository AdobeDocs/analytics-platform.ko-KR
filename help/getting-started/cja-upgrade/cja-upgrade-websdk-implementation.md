---
title: Customer Journey Analytics로 업그레이드할 때 Web SDK 구현 옵션 이해
description: Customer Journey Analytics로 업그레이드할 때 Web SDK 구현 옵션에 대해 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 100%

---

# Customer Journey Analytics로 업그레이드할 때 Web SDK 구현 옵션 이해 {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web SDK JavaScript 라이브러리(alloy.js)"
>abstract="사이트의 각 페이지에 Web SDK 라이브러리(alloy.js)를 포함합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Web SDK 태그 확장 기능"
>abstract="(권장) 아직 태그를 사용하지 않는 경우, 귀하의 사이트에 태그 로더를 설치해야 합니다. 이미 태그를 사용 중인 경우 태그 속성에 Web SDK 확장 기능을 추가할 수 있습니다. 이 옵션에는 Adobe Experience Platform 데이터 수집 및 서드파티 태그 관리 시스템 내 태그를 사용한 구현이 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM 패키지"
>abstract="데이터 수집 API를 사용하여 데이터를 데이터스트림으로 직접 전송합니다. 인증되지 않은 유형(클라이언트-서버)과 인증된 유형(서버-서버)이 모두 지원됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="주어진 속성에 대한 Web SDK 구현"
>abstract="업그레이드 안내서에서 원하는 구현 유형을 선택하여 자세한 지침을 확인하십시오."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="서드파티 태그 관리 시스템에 Web SDK 라이브러리 추가"
>abstract="태그 관리 시스템 관리자와 협력하여 Web SDK 라이브러리를 사이트에 추가합니다.<br><br>이 작업을 완료하는 데 소요되는 시간은 태그 관리 시스템을 담당하는 개인의 응답성에 따라 크게 달라집니다. Web SDK 라이브러리를 추가하면 관련 구현 논리가 함께 번들로 제공되어 조직의 표준 릴리스 주기 동안 배포될 수 있습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics에서 Customer Journey Analytics로 업그레이드하는 데 권장되는 프로세스는 Customer Journey Analytics를 위한 기본 데이터 수집 방법인 Experience Platform Web SDK의 새로운 구현입니다.

Adobe Experience Platform Web SDK를 사용하는 데 지원되는 방법은 세 가지가 있습니다.

* [Web SDK 태그 확장 기능](https://experienceleague.adobe.com/ko/docs/experience-platform/web-sdk/install/extension): Adobe는 이 방법을 사용하는 것을 권장합니다. 사이트에 태그 로더를 설치한 다음 Adobe Experience Platform 데이터 수집 UI를 사용하여 구현을 구성합니다.

* [Web SDK JavaScript 라이브러리](https://experienceleague.adobe.com/ko/docs/experience-platform/web-sdk/install/library): CDN 호스팅 라이브러리 파일을 참조하거나 자체 인프라를 사용하여 라이브러리 파일을 호스팅합니다. 사이트의 코드 내에서 라이브러리를 호출합니다.

* [NPM](https://experienceleague.adobe.com/ko/docs/experience-platform/web-sdk/install/npm): NPM 패키지 관리자를 사용하여 사이트에 Web SDK를 설치합니다.

자세한 내용은 Experience Platform Web SDK 가이드의 [Web SDK 설치 개요](https://experienceleague.adobe.com/ko/docs/experience-platform/web-sdk/install/overview)를 참조하십시오.
