---
title: 태그를 사용하여 Customer Journey Analytics용 웹 SDK 구현
description: 태그를 사용하여 Customer Journey Analytics용 웹 SDK를 구현하는 방법에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '1320'
ht-degree: 76%

---

# 태그를 사용하여 Customer Journey Analytics용 웹 SDK 구현

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

Adobe Experience Platform 내의 태그 기능을 사용하여 사이트에서 코드를 구현하여 데이터를 수집할 수 있습니다. 이는 다른 태그 지정 요구 사항과 함께 코드를 배포할 수 있도록 해 주는 태그 관리 솔루션입니다. 태그는 Adobe Experience Platform Web SDK 확장을 사용하여 Adobe Experience Platform과 원활하게 통합할 수 있도록 해 줍니다.

## 태그 만들기

1. 왼쪽 레일의 Adobe Experience Platform UI에서 [!UICONTROL 데이터 수집] 에 있는 **[!UICONTROL 태그]**&#x200B;를 선택합니다.

2. **[!UICONTROL 새 속성]**&#x200B;을 선택합니다.

   태그 이름을 지정하고 **[!UICONTROL 웹]**&#x200B;을 선택한 다음 도메인 이름을 입력합니다. 계속하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

   ![속성 만들기](assets/create-property.png)

## 태그 구성

태그를 만든 후에는 올바른 확장으로 태그를 구성하고 사이트를 추적하고 데이터를 Adobe Experience Platform에 보내는 방법에 따라 데이터 요소와 규칙을 구성해야 합니다.

[!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.


### **확장**

데이터 스트림을 통해 Adobe Experience Platform으로 데이터를 보낼 수 있도록 Adobe 플랫폼 웹 SDK 확장을 태그에 추가합니다.

Adobe Experience Platform Web SDK 확장을 만들고 구성하는 경우:

1. 왼쪽 레일에서 **[!UICONTROL 확장]**&#x200B;을 선택합니다.

1. 상단 막대에서 **[!UICONTROL 카탈로그]**&#x200B;를 선택합니다.

1. Adobe Experience Platform Web SDK 확장을 검색하거나 스크롤하고 **[!UICONTROL 설치]**&#x200B;를 선택하여 설치합니다.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. [!UICONTROL 프로덕션 환경], (선택 사항) [!UICONTROL 스테이징 환경] 및 [!UICONTROL 개발 환경]에 대해 샌드박스와 이전에 만든 데이터스트림을 선택합니다.

   ![AEP Web SDK 확장 구성](assets/aepwebsk-extension-datastreams.png)

   **[!UICONTROL 저장]**&#x200B;을 선택합니다.

자세한 내용은 [Adobe Experience Platform Web SDK 확장 구성](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html)을 참조하십시오.

Web SDK에는 기본적으로 [!UICONTROL Adobe Experience Cloud ID 서비스]가 포함되어 있으므로 ID 서비스 확장을 태그에 추가할 필요가 없습니다.

### **데이터 요소**

데이터 요소는 데이터 사전(또는 데이터 맵)의 기본 구성단위입니다. 데이터 요소를 사용하여 마케팅 및 광고 기술 전반에서 데이터를 수집, 구성 및 전달합니다. 데이터 레이어에서 읽고 데이터를 Adobe Experience Platform으로 전달하는 데 사용할 수 있는 데이터 요소를 태그에 설정합니다.

데이터 요소에는 세 가지 유형이 있습니다. 먼저 데이터 요소를 설정하여 사이트에서 사람들이 보고 있는 페이지 이름을 캡처합니다.

페이지 이름 데이터 요소를 정의하는 경우:

1. 왼쪽 레일에서 **[!UICONTROL 데이터 요소]**&#x200B;를 선택합니다.

2. **[!UICONTROL 데이터 요소 추가]**&#x200B;를 선택합니다.

3. [!UICONTROL 데이터 요소 만들기] 대화 상자에서:

   - 데이터 요소의 이름을 지정합니다(예: `Page Name`).

   - **[!UICONTROL 확장]** 목록에서 [!UICONTROL 코어]를 선택합니다.

   - [!UICONTROL 데이터 요소 유형] 목록에서 **[!UICONTROL 페이지 정보]**&#x200B;를 선택합니다.

   - [!UICONTROL 속성] 목록에서 **[!UICONTROL 제목]**&#x200B;을 선택합니다.

     ![페이지 정보를 사용하여 날짜 요소 만들기](assets/create-dataelement-1.png)

     또는 데이터 레이어의 변수 값(예: `pageName` 및 [!UICONTROL JavaScript 변수] 데이터 요소 유형)을 사용하여 데이터 요소를 정의할 수 있습니다.

     ![JavaScript 변수를 사용하여 데이터 요소 만들기](assets/create-dataelement-2.png)

   - **[!UICONTROL 저장]**&#x200B;을 선택합니다.

이제 Adobe Experience Platform Web SDK에서 자동으로 제공되고 Experience Cloud ID 서비스 확장을 통해 사용할 수 있는 Experience Cloud ID를 참조하는 데이터 요소를 설정하려고 합니다.

ECID 데이터 요소를 정의하는 경우:

1. 왼쪽 레일에서 **[!UICONTROL 데이터 요소]**&#x200B;를 선택합니다.

2. **[!UICONTROL 데이터 요소 추가]**&#x200B;를 선택합니다.

3. [!UICONTROL 데이터 요소 만들기] 대화 상자에서:

   - 데이터 요소의 이름을 지정합니다(예: `ECID`).

   - [!UICONTROL 확장] 목록에서 **[!UICONTROL Experience Cloud ID 서비스]**&#x200B;를 선택합니다.

   - [!UICONTROL 데이터 요소 유형] 목록에서 **[!UICONTROL ECID]**&#x200B;를 선택합니다.

     ![ECID 데이터 요소](assets/ecid-dataelement.png)

   - **[!UICONTROL 저장]**&#x200B;을 선택합니다.

이제 마지막으로 특정 데이터 요소를 이전에 정의한 스키마에 매핑하려고 합니다. XDM 스키마를 나타내는 다른 데이터 요소를 정의합니다.

XDM 오브젝트 데이터 요소를 정의하는 경우:

1. 왼쪽 레일에서 **[!UICONTROL 데이터 요소]**&#x200B;를 선택합니다.

2. **[!UICONTROL 데이터 요소 추가]**&#x200B;를 선택합니다.

3. [!UICONTROL 데이터 요소 만들기] 대화 상자에서:

   - 데이터 요소의 이름을 지정합니다(예: `XDM - Page View`).

   - [!UICONTROL 확장] 목록에서 **[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;를 선택합니다.

   - [!UICONTROL 데이터 요소 유형] 목록에서 **[!UICONTROL XDM 오브젝트]**&#x200B;를 선택합니다.

   - [!UICONTROL 샌드박스] 목록에서 샌드박스를 선택합니다.

   - [!UICONTROL 스키마] 목록에서 스키마를 선택합니다.

   - 스키마에 정의된 `identification > core > ecid` 속성을 ECID 데이터 요소에 매핑합니다. 원통 아이콘을 선택하여 데이터 요소 목록에서 ECID 데이터 요소를 쉽게 선택합니다.

     ![ECID 데이터 요소 선택](assets/pick-ecid-dataelement.png)

     ![ECID 데이터 요소 매핑](assets/map-ecid.png)


   - 스키마에 정의된 `web > webPageDetails > name` 속성을 페이지 이름 데이터 요소에 매핑합니다.

     ![페이지 이름 데이터 요소 매핑](assets/map-pagename.png)

   - **[!UICONTROL 저장]**&#x200B;을 선택합니다.


### **규칙**

Adobe Experience Platform의 태그는 규칙 기반 시스템을 따릅니다. 사용자 상호 작용과 관련 데이터를 찾습니다. 규칙에 요약된 기준이 충족되면 규칙이 정의한 확장, 스크립트 또는 클라이언트측 코드를 트리거합니다. Adobe Experience Platform Web SDK 확장을 통해 규칙을 사용하여 데이터(예: XDM 오브젝트)를 Adobe Experience Platform에 전송할 수 있습니다.

규칙을 정의하는 경우:

1. 왼쪽 레일에서 **[!UICONTROL 규칙]**&#x200B;을 선택합니다.

1. **[!UICONTROL 새 규칙 만들기]**&#x200B;를 선택합니다.

1. [!UICONTROL 규칙 만들기] 대화 상자에서:

   - 규칙의 이름을 지정합니다(예: `Page View`).

   - [!UICONTROL 이벤트] 아래의 **[!UICONTROL 더하기 추가]**&#x200B;를 선택합니다.

   - [!UICONTROL 이벤트 구성] 대화 상자에서:

      - **[!UICONTROL 확장]** 목록에서 [!UICONTROL 코어]를 선택합니다.

      - [!UICONTROL 이벤트 유형] 목록에서 **[!UICONTROL 로드된 창]**&#x200B;을 선택합니다.

        ![규칙 - 이벤트 구성](assets/event-windowloaded-pageview.png)

      - **[!UICONTROL 변경사항 유지]**&#x200B;를 선택합니다.



   - [!UICONTROL 액션] 아래의 **[!UICONTROL 더하기 추가]**&#x200B;를 선택합니다.

   - [!UICONTROL 액션 구성] 대화 상자에서:

      - [!UICONTROL 확장] 목록에서 **[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;를 선택합니다.

      - [!UICONTROL 액션 유형] 목록에서 **[!UICONTROL 이벤트 전송]**&#x200B;을 선택합니다.

      - [!UICONTROL 유형] 목록에서 **[!UICONTROL web.webpagedetails.pageViews]**&#x200B;를 선택합니다.

      - [!UICONTROL XDM 데이터] 옆의 원통 아이콘을 선택하고 데이터 요소 목록에서 **[!UICONTROL XDM - 페이지 조회수]**&#x200B;를 선택합니다.

     ![규칙 - 액션 구성](assets/action-pageview-xdm.png)

      - **[!UICONTROL 변경사항 유지]**&#x200B;를 선택합니다.

   - 규칙은 다음과 같습니다.

     ![규칙 만들기](assets/rule-pageview.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

위의 예는 다른 데이터 요소의 값이 포함된 XDM 데이터를 Adobe Experience Platform으로 보내는 규칙을 정의하는 예제입니다.

태그에서 다양한 방식으로 규칙을 사용하여 변수를 조작할 수 있습니다(데이터 요소 사용).

자세한 내용은 [규칙](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html)을 참조하십시오.

## 태그 빌드 및 게시

데이터 요소와 규칙을 정의한 후에는 태그를 빌드하고 게시해야 합니다. 라이브러리 빌드를 만들면 이를 환경에 지정해야 합니다. 그런 다음 빌드의 확장, 규칙 및 데이터 요소를 컴파일하여 지정된 환경에 배치합니다. 각 환경에서는 지정된 빌드를 사이트에 통합할 수 있는 고유한 임베드 코드를 제공합니다.

태그를 빌드하고 게시하는 경우:

1. 왼쪽 레일에서 **[!UICONTROL 흐름 게시]**&#x200B;를 선택합니다.

2. **[!UICONTROL 작업 중인 라이브러리 선택]**&#x200B;을 선택한 다음 **[!UICONTROL 라이브러리 추가...]**&#x200B;를 선택합니다.

3. [!UICONTROL 라이브러리 만들기] 대화 상자에서:

   - 라이브러리 이름을 지정합니다.

   - **[!UICONTROL 환경]** 목록에서 [!UICONTROL 개발(개발)]을 선택합니다.

   - **[!UICONTROL 변경된 모든 리소스 추가]**&#x200B;를 선택합니다.

     ![게시 - 라이브러리 만들기](assets/create-library-aep.png)

   - **[!UICONTROL 개발에 저장 및 빌드]**&#x200B;을 선택합니다.

   태그가 저장되고 개발 환경에 맞게 빌드됩니다. 녹색 점은 개발 환경에서 태그의 빌드가 완료되었음을 나타냅니다.

4. **[!UICONTROL ...]**&#x200B;를 선택하여 라이브러리를 다시 빌드하거나 라이브러리를 스테이징 또는 프로덕션 환경으로 이동할 수 있습니다.

   ![게시 - 라이브러리 빌드](assets/build-library.png)

Adobe Experience Platform 태그는 Adobe Experience Platform Web SDK 배포를 수용해야 하는 간단하면서 복잡한 게시 워크플로를 지원합니다.

자세한 내용은 [게시 개요](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html)를 참조하십시오.


## 태그 코드 검색

마지막으로 추적할 웹 사이트에 태그를 설치해야 합니다. 이는 웹 사이트 템플릿의 헤더 태그에 코드를 배치함을 의미합니다.

태그를 참조하는 코드를 가져오는 경우:

1. 왼쪽 레일에서 **[!UICONTROL 환경]**&#x200B;을 선택합니다.

1. 환경 목록에서 올바른 설치(상자) 버튼을 선택합니다.

   [!UICONTROL 웹 설치 지침] 대화 상자에서 다음과 유사한 스크립트 코드 옆에 있는 복사 버튼을 선택합니다.

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![환경](assets/environment.png)

1. **[!UICONTROL 닫기]**&#x200B;를 선택합니다.

   개발 환경의 코드 대신 Adobe Experience Platform Web SDK 배포 과정을 기준으로 다른 환경(스테이징, 프로덕션)을 선택할 수 있습니다.

   자세한 내용은 [환경](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?)을 참조하십시오.

1. [권장된 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 [동적으로 생성된 업그레이드 단계](https://gigazelle.github.io/cja-ttv/)를 계속 따릅니다.
