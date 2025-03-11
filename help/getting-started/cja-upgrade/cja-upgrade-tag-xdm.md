---
title: 태그에 XDM 데이터 수집 논리 추가
description: 태그에 XDM 데이터 수집 논리를 추가하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc6c7568-8bd2-4ee1-ab1b-9fa1f6138811
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1631'
ht-degree: 37%

---

# 태그에 XDM 데이터 수집 논리 추가 {#upgrade-tag-xdm}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-xdm"
>title="태그에 XDM 데이터 수집 논리 추가"
>abstract="로더 태그를 사이트에 설치하면 규칙과 데이터 요소를 추가하여 Adobe로 보낼 XDM 오브젝트를 채울 수 있습니다. Adobe는 태그 구성 방식을 추적하기 위해 솔루션 설계 문서를 유지 관리할 것을 권장합니다.<br><br>이 단계는 모든 속성에 대한 모든 분석 논리를 설정하는 것을 포함하기 때문에 많은 작업이 필요합니다. 올바른 태그 규칙을 설정하고 테스트한 후 사이트에 배포하는 데 한 달 이상 소요될 것으로 예상됩니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

[태그를 만들고 웹 SDK 확장을 추가한](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md) 후에는 사이트를 추적하고 Adobe Experience Platform에 데이터를 보내는 방법에 따라 데이터 요소와 규칙을 사용하여 태그를 구성해야 합니다. 태그에 대한 데이터 요소 및 규칙을 구성한 후 빌드하고 게시할 수 있습니다.

## 데이터 요소 구성

데이터 요소는 데이터 사전(또는 데이터 맵)의 기본 구성단위입니다. 데이터 요소를 사용하여 마케팅 및 광고 기술 전반에서 데이터를 수집, 구성 및 전달합니다. 태그에서 데이터 레이어에서 읽어 Adobe Experience Platform으로 데이터를 전달하는 데 사용할 수 있는 데이터 요소를 설정합니다. 데이터 요소에 대한 자세한 내용은 태그 설명서의 [데이터 요소](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/data-elements)를 참조하십시오.

다음 섹션에서는 제안되는 데이터 요소 및 구성할 수 있는 기타 일반적인 데이터 요소에 대해 설명합니다.

데이터 요소에는 다양한 유형이 있습니다. 구성할 수 있는 두 가지 일반적인 데이터 요소는 사람이 사이트에서 보고 있는 페이지 이름을 캡처하는 요소와 사이트를 방문하는 각 사람의 Experience Cloud ID를 캡처하는 요소입니다.

이 두 데이터 요소를 구성한 후 캡처할 특정 데이터에 대해 추가 데이터 요소를 구성할 수 있습니다.

마지막으로, 원하는 데이터 요소를 모두 정의한 후에는 이전에 만든 [스키마](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)에 데이터 요소를 할당해야 합니다. 이를 위해 XDM 스키마 표현을 제공하는 XDM 데이터 요소를 정의합니다.

<!-- Assigning data elements to an XDM object. All of the available XDM objects are based on the schema -->

### 제안된 데이터 요소 만들기

다음 섹션에서는 대부분의 조직에 적용되는 공통 데이터 요소를 생성하는 방법에 대해 설명합니다.

#### 페이지 이름 데이터 요소

대부분의 조직에 적용되는 공통 데이터 요소는 개인이 보고 있는 페이지 이름을 캡처하는 데이터 요소입니다.

페이지 이름 데이터 요소를 만들려면 다음 작업을 수행하십시오.

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. **[!UICONTROL 태그 속성]** 페이지의 속성 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 데이터 요소]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 요소 추가]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 요소 만들기]** 대화 상자에서 다음 정보를 지정합니다.

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

#### ECID 데이터 요소

대부분의 조직에 적용되는 일반적인 데이터 요소는 사이트를 방문하는 각 사용자의 Experience Cloud ID를 캡처하는 데이터 요소입니다.

ECID 데이터 요소를 만들려면 다음을 수행하십시오.

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. [!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.

1. (조건부) Experience Cloud ID 서비스 확장이 아직 설치되지 않은 경우 설치합니다.

   1. 왼쪽 레일에서 **[!UICONTROL 확장]**&#x200B;을 선택합니다.

   1. 기본적으로 **[!UICONTROL 설치됨]** 탭이 선택됩니다. **[!UICONTROL Experience Cloud ID 서비스]** 타일이 나열되면 5단계로 건너뜁니다.

   1. **[!UICONTROL Experience Cloud ID 서비스]** 타일이 나열되지 않으면 **[!UICONTROL 카탈로그]** 탭을 선택하십시오.

   1. 검색 필드에서 **[!UICONTROL Experience Cloud ID 서비스]**&#x200B;를 검색한 다음 표시될 때 타일을 선택합니다

   1. **[!UICONTROL 설치]** > **[!UICONTROL 저장]**&#x200B;을 선택합니다.

1. 왼쪽 레일에서 **[!UICONTROL 데이터 요소]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 요소 추가]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 요소 만들기]** 대화 상자에서 다음 정보를 지정합니다.

   * **[!UICONTROL 이름]**: 데이터 요소의 이름입니다. 예 `ECID`.

   * **[!UICONTROL 확장]**: 목록에서 **[!UICONTROL Experience Cloud ID 서비스]**&#x200B;를 선택합니다.

   * **[!UICONTROL 데이터 요소 형식]**: 목록에서 **[!UICONTROL ECID]**&#x200B;을(를) 선택하십시오.

     ![ECID 데이터 요소](assets/ecid-dataelement.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

1. [추가 데이터 요소 만들기](#create-additional-data-elements)를 계속합니다.

### 추가 데이터 요소 만들기

수집하려는 각 데이터 유형에 대한 데이터 요소를 만듭니다. [페이지 이름 데이터 요소](#page-name-data-element) 및 [ECID 데이터 요소](#ecid-data-element)에 설명된 것과 동일한 프로세스를 사용하여 각 추가 데이터 요소를 만듭니다.

생성하는 데이터 요소에는 스키마에 상관 관계가 있는 필드가 있어야 합니다.

일반적인 데이터 요소는 업계 및 비즈니스 요구 사항에 따라 다릅니다. 다음 산업별로 구성된 공통 데이터 요소를 고려하십시오.

**소매 데이터 요소**

* 제품

* 장바구니 추가

* 체크아웃

**재무 데이터 요소**

* 거래 ID

* 트랜잭션 날짜

* 서비스 유형

**의료 데이터 요소**

* 공급자 ID

* 방문 날짜

* 치료 유형

조직에서 구현에 필요한 모든 데이터 요소를 만든 후 [XDM 개체 데이터 요소](#xdm-object-data-element)를 계속 사용하십시오.

### XDM 개체 데이터 요소

마지막으로 만든 데이터 요소를 이전에 만든 [스키마](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)에 매핑합니다. 이렇게 하려면 XDM 스키마의 표현을 제공하는 XDM 개체 데이터 요소를 정의합니다.

XDM 오브젝트 데이터 요소를 정의하는 경우:

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. [!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 데이터 요소]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 요소 추가]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 요소 만들기]** 대화 상자에서 다음 정보를 지정합니다.

   * **[!UICONTROL 이름]**: 데이터 요소의 이름입니다. 예 `XDM - Page View`.

   * **[!UICONTROL 확장]**: 목록에서 **[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;을(를) 선택합니다.

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

1. **[!UICONTROL 규칙 추가]**&#x200B;를 선택합니다.

1. **[!UICONTROL 규칙 만들기]** 대화 상자에서 다음 정보를 지정합니다.

   * **[!UICONTROL 이름]**: 규칙의 이름입니다. 예 `Page View`.

   * **[!UICONTROL 이벤트]**: **[!UICONTROL + 추가]**&#x200B;를 선택합니다. 그런 다음 **[!UICONTROL 이벤트 구성]** 대화 상자에서 다음 정보를 지정합니다. 완료되면 **[!UICONTROL 변경 내용 유지]**&#x200B;를 선택합니다.

      * **[!UICONTROL 확장]**: 목록에서 **[!UICONTROL 코어]**&#x200B;을(를) 선택하십시오.

      * **[!UICONTROL 이벤트 유형]**: 목록에서 **[!UICONTROL 로드된 창]**&#x200B;을 선택합니다.

        ![규칙 - 이벤트 구성](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL 작업]**: **[!UICONTROL + 추가]**&#x200B;를 선택합니다. 그런 다음 [!UICONTROL 작업 구성] 대화 상자에서 다음 정보를 지정합니다. 완료되면 **[!UICONTROL 변경 내용 유지]**&#x200B;를 선택합니다.

      * **[!UICONTROL 확장]**: 목록에서 **[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;을(를) 선택합니다.

      * **[!UICONTROL 작업 유형]**: 목록에서 **[!UICONTROL 이벤트 보내기]**&#x200B;를 선택합니다.

      * **[!UICONTROL 유형]**: 목록에서 **[!UICONTROL 웹 Webpagedetails 페이지 보기]**&#x200B;를 선택합니다.

      * **[!UICONTROL XDM 데이터]**: 원통 아이콘을 선택한 다음 데이터 요소 목록에서 **[!UICONTROL XDM - 페이지 보기]**&#x200B;를 선택합니다.

        ![규칙 - 액션 구성](assets/action-pageview-xdm.png)

        규칙은 다음과 같습니다.

        ![규칙 만들기](assets/rule-pageview.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

1. 사이트에 추가하려는 각 규칙에 대해 이 프로세스를 반복합니다.

   규칙에 대한 자세한 내용은 태그 설명서의 [규칙](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/rules)을 참조하십시오.

1. [태그를 빌드하고 게시합니다](#build-and-publish-your-tag).

## 태그 빌드 및 게시

데이터 요소와 규칙을 정의한 후에는 태그를 빌드하고 게시해야 합니다. 라이브러리 빌드를 만들면 이를 환경에 지정해야 합니다. 그런 다음 빌드의 확장, 규칙 및 데이터 요소를 컴파일하여 지정된 환경에 배치합니다. 각 환경에서는 지정된 빌드를 사이트에 통합할 수 있는 고유한 임베드 코드를 제공합니다.

Adobe Experience Platform 태그는 Adobe Experience Platform Web SDK 배포에 적합한 간단하고 복잡한 게시 워크플로우를 지원합니다. 자세한 내용은 [게시 개요](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html)를 참조하십시오.

태그를 빌드하고 게시하는 경우:

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.

1. [!UICONTROL 태그 속성] 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 흐름 게시]**&#x200B;를 선택합니다.

1. **[!UICONTROL 라이브러리 추가]**&#x200B;를 선택합니다.

1. **[!UICONTROL 라이브러리 만들기]** 대화 상자에서 다음 정보를 지정합니다.

   * **[!UICONTROL 이름]**: 라이브러리의 이름입니다.

   * **[!UICONTROL 환경]**: 목록에서 **[!UICONTROL 개발(개발)]**&#x200B;을 선택합니다.

1. **[!UICONTROL 변경된 모든 리소스 추가]**&#x200B;를 선택합니다.

   ![게시 - 라이브러리 만들기](assets/create-library-aep.png)

1. **[!UICONTROL 개발에 저장 및 빌드]**&#x200B;을 선택합니다.

   태그가 저장되고 개발 환경용으로 빌드되었습니다. 녹색 점은 개발 환경에서 태그의 빌드가 완료되었음을 나타냅니다.

1. **[!UICONTROL ...]**&#x200B;를 선택하여 라이브러리를 다시 빌드하거나 라이브러리를 스테이징 또는 프로덕션 환경으로 이동할 수 있습니다.

   ![게시 - 라이브러리 빌드](assets/build-library.png)

{{upgrade-final-step}}

