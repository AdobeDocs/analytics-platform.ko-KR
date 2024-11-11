---
title: 태그에 XDM 데이터 수집 논리 추가
description: 태그에 XDM 데이터 수집 논리를 추가하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ccc6df56771cd9f83bbd7a8570e32d7ed63a0ced
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 48%

---

# 태그에 XDM 데이터 수집 논리 추가

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

[태그를 만들어 Web SDK 확장을 추가](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)한 후에는 사이트를 추적하고 데이터를 Adobe Experience Platform으로 보내는 방법에 따라 데이터 요소와 규칙을 사용하여 태그를 구성해야 합니다. 태그에 대한 데이터 요소 및 규칙을 구성한 후 빌드하고 게시할 수 있습니다.

## 데이터 요소 구성

데이터 요소는 데이터 사전(또는 데이터 맵)의 기본 구성단위입니다. 데이터 요소를 사용하여 마케팅 및 광고 기술 전반에서 데이터를 수집, 구성 및 전달합니다. 데이터 레이어에서 읽고 데이터를 Adobe Experience Platform으로 전달하는 데 사용할 수 있는 데이터 요소를 태그에 설정합니다.

데이터 요소에는 세 가지 유형이 있습니다. 먼저 데이터 요소를 설정하여 사이트에서 사람들이 보고 있는 페이지 이름을 캡처합니다. 그런 다음 Experience Cloud ID를 참조하는 데이터 요소를 설정합니다. 마지막으로 XDM 개체 데이터 요소를 정의합니다.

### 페이지 이름 데이터 요소

페이지 이름 데이터 요소를 정의하는 경우:

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. [!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 데이터 요소]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 요소 추가]**&#x200B;를 선택합니다.

1. [!UICONTROL 데이터 요소 만들기] 대화 상자에서 다음 정보를 지정합니다.

   * **[!UICONTROL 이름]**: 데이터 요소의 이름입니다. 예 `Page Name`.

   * **[!UICONTROL 확장]**: 목록에서 **[!UICONTROL 코어]**&#x200B;을(를) 선택하십시오.

   * **[!UICONTROL 데이터 요소 형식]**: 목록에서 **[!UICONTROL 페이지 정보]**&#x200B;를 선택합니다.

   * **[!UICONTROL 특성]**: 목록에서 **[!UICONTROL 제목]**&#x200B;을 선택합니다.

     ![페이지 정보를 사용하여 날짜 요소 만들기](assets/create-dataelement-1.png)

     또는 데이터 레이어의 변수 값(예: `pageName` 및 [!UICONTROL JavaScript 변수] 데이터 요소 유형)을 사용하여 데이터 요소를 정의할 수 있습니다.

     ![JavaScript 변수를 사용하여 데이터 요소 만들기](assets/create-dataelement-2.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

   이제 Adobe Experience Platform Web SDK에서 자동으로 제공되고 Experience Cloud ID 서비스 확장을 통해 사용할 수 있는 Experience Cloud ID를 참조하는 데이터 요소를 설정하려고 합니다.

1. [ECID 데이터 요소](#ecid-data-element)를 사용하여 계속합니다.

### ECID 데이터 요소

ECID 데이터 요소를 정의하는 경우:

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. [!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 데이터 요소]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 요소 추가]**&#x200B;를 선택합니다.

1. [!UICONTROL 데이터 요소 만들기] 대화 상자에서 다음 정보를 지정합니다.

   * **[!UICONTROL 이름]**: 데이터 요소의 이름입니다. 예 `ECID`.

   * **[!UICONTROL 확장]**: 목록에서 **[!UICONTROL Experience Cloud ID 서비스]**&#x200B;를 선택합니다.

   * **[!UICONTROL 데이터 요소 형식]**: 목록에서 **[!UICONTROL ECID]**&#x200B;을(를) 선택하십시오.

     ![ECID 데이터 요소](assets/ecid-dataelement.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

1. [XDM 개체 데이터 요소](#xdm-object-data-element)를 계속합니다.

### XDM 개체 데이터 요소

이제 마지막으로 특정 데이터 요소를 이전에 정의한 스키마에 매핑하려고 합니다. XDM 스키마를 나타내는 다른 데이터 요소를 정의합니다.

XDM 오브젝트 데이터 요소를 정의하는 경우:

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. [!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 데이터 요소]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 요소 추가]**&#x200B;를 선택합니다.

1. [!UICONTROL 데이터 요소 만들기] 대화 상자에서 다음 정보를 지정합니다.

   * **[!UICONTROL 이름]**: 데이터 요소의 이름입니다. 예 `XDM - Page View`.

   * **[!UICONTROL 확장]**: 목록에서 **[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;를 선택합니다.

   * **[!UICONTROL 데이터 요소 형식]**: 목록에서 **[!UICONTROL XDM 개체]**&#x200B;를 선택합니다.

   * **[!UICONTROL 샌드박스]**: 목록에서 샌드박스를 선택합니다.

   * **[!UICONTROL 스키마]**: 목록에서 스키마를 선택합니다.

1. 스키마에 정의된 `identification > core > ecid` 속성을 ECID 데이터 요소에 매핑합니다. 원통 아이콘을 선택하여 데이터 요소 목록에서 ECID 데이터 요소를 쉽게 선택합니다.

   ![ECID 데이터 요소 선택](assets/pick-ecid-dataelement.png)

   ![ECID 데이터 요소 매핑](assets/map-ecid.png)


1. 스키마에 정의된 `web > webPageDetails > name` 속성을 페이지 이름 데이터 요소에 매핑합니다.

   ![페이지 이름 데이터 요소 매핑](assets/map-pagename.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

1. [규칙 구성](#configure-rules)을 계속합니다.

## **규칙 구성**

Adobe Experience Platform의 태그는 규칙 기반 시스템을 따릅니다. 사용자 상호 작용과 관련 데이터를 찾습니다. 규칙에 요약된 기준이 충족되면 규칙이 정의한 확장, 스크립트 또는 클라이언트측 코드를 트리거합니다. Adobe Experience Platform Web SDK 확장을 통해 규칙을 사용하여 데이터(예: XDM 오브젝트)를 Adobe Experience Platform에 전송할 수 있습니다.

규칙을 정의하는 경우:

>[!NOTE]
>
>다음 단계는 다른 데이터 요소의 값이 포함된 XDM 데이터를 Adobe Experience Platform으로 보내는 규칙을 정의하는 예입니다.
>
>태그에서 다양한 방식으로 규칙을 사용하여 변수를 조작할 수 있습니다(데이터 요소 사용).
>
>자세한 내용은 [규칙](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html)을 참조하십시오.

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. [!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 규칙]**&#x200B;을 선택합니다.

1. **[!UICONTROL 새 규칙 만들기]**&#x200B;를 선택합니다.

1. [!UICONTROL 규칙 만들기] 대화 상자에서 다음 정보를 지정합니다.

   * **[!UICONTROL 이름]**: 규칙의 이름입니다. 예 `Page View`.

   * **[!UICONTROL 이벤트]**: **[!UICONTROL + 추가]**&#x200B;를 선택합니다. 그런 다음 [!UICONTROL 이벤트 구성] 대화 상자에서 다음 정보를 지정합니다. 완료되면 **[!UICONTROL 변경 내용 유지]**&#x200B;를 선택합니다.

      * **[!UICONTROL 확장]**: 목록에서 **[!UICONTROL 코어]**&#x200B;을(를) 선택하십시오.

      * **[!UICONTROL 이벤트 유형]**: 목록에서 **[!UICONTROL 로드된 창]**&#x200B;을 선택합니다.

        ![규칙 - 이벤트 구성](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL 작업]**: **[!UICONTROL + 추가]**&#x200B;를 선택합니다. 그런 다음 [!UICONTROL 작업 구성] 대화 상자에서 다음 정보를 지정합니다. 완료되면 **[!UICONTROL 변경 내용 유지]**&#x200B;를 선택합니다.

      * **[!UICONTROL 확장]**: 목록에서 **[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;를 선택합니다.

      * **[!UICONTROL 작업 유형]**: 목록에서 **[!UICONTROL 이벤트 보내기]**&#x200B;를 선택합니다.

      * **[!UICONTROL 유형]**: 목록에서 **[!UICONTROL web.webpagedetails.pageViews]**&#x200B;을(를) 선택합니다.

      * **[!UICONTROL XDM 데이터]**: 원통 아이콘을 선택한 다음 데이터 요소 목록에서 **[!UICONTROL XDM - 페이지 보기]**&#x200B;를 선택합니다.

        ![규칙 - 액션 구성](assets/action-pageview-xdm.png)

        규칙은 다음과 같습니다.

        ![규칙 만들기](assets/rule-pageview.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

## 태그 빌드 및 게시

데이터 요소와 규칙을 정의한 후에는 태그를 빌드하고 게시해야 합니다. 라이브러리 빌드를 만들면 이를 환경에 지정해야 합니다. 그런 다음 빌드의 확장, 규칙 및 데이터 요소를 컴파일하여 지정된 환경에 배치합니다. 각 환경에서는 지정된 빌드를 사이트에 통합할 수 있는 고유한 임베드 코드를 제공합니다.

Adobe Experience Platform 태그는 Adobe Experience Platform Web SDK 배포에 적합한 간단하고 복잡한 게시 워크플로우를 지원합니다. 자세한 내용은 [게시 개요](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html)를 참조하십시오.

태그를 빌드하고 게시하는 경우:

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. [!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 흐름 게시]**&#x200B;를 선택합니다.

1. **[!UICONTROL 작업 중인 라이브러리 선택]**&#x200B;을 선택한 다음 **[!UICONTROL 라이브러리 추가...]**&#x200B;를 선택합니다.

1. [!UICONTROL 라이브러리 만들기] 대화 상자에서 다음 정보를 지정합니다.

   * **[!UICONTROL 이름]**: 라이브러리의 이름입니다.

   * **[!UICONTROL 환경]**: 목록에서 **[!UICONTROL 개발(개발)]**&#x200B;을 선택합니다.

1. **[!UICONTROL 변경된 모든 리소스 추가]**&#x200B;를 선택합니다.

   ![게시 - 라이브러리 만들기](assets/create-library-aep.png)

1. **[!UICONTROL 개발에 저장 및 빌드]**&#x200B;을 선택합니다.

   태그가 저장되고 개발 환경에 맞게 빌드됩니다. 녹색 점은 개발 환경에서 태그의 빌드가 완료되었음을 나타냅니다.

1. **[!UICONTROL ...]**&#x200B;를 선택하여 라이브러리를 다시 빌드하거나 라이브러리를 스테이징 또는 프로덕션 환경으로 이동할 수 있습니다.

   ![게시 - 라이브러리 빌드](assets/build-library.png)

