---
title: Content Analytics 구성(독립 실행형)
description: Content Analytics(독립 실행형)을 구성하는 데 필요한 단계를 안내합니다.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 44fa4385faf2e41f90c6bce3648a4890d4a70442
workflow-type: tm+mt
source-wordcount: '2517'
ht-degree: 6%

---


# 독립형 구성

>[!IMPORTANT]
>
>이 구성 안내서는 독립형 Adobe Content Analytics 패키지에 라이센스를 부여한 고객을 위한 것입니다. 이 안내서에서는 사용자가 Customer Journey Analytics 또는 Content Analytics 기능 이외의 다른 Experience Platform 애플리케이션을 사용하지 않았거나 사용할 계획이 없다고 가정합니다. 기존 Content Analytics 구현의 일부로 Content Analytics을 구성하고 사용하려면 [Customer Journey Analytics 구성](configuration.md)을 참조하십시오.
>

Content Analytics은 독립 실행형 제품으로 라이선스가 부여되지만 구성은 Experience Platform 및 Customer Journey Analytics 내에서 수행됩니다. 이러한 플랫폼은 Content Analytics이 필요로 하고 사용하는 데이터 수집 및 분석 인프라를 제공합니다. 이 안내서에서는 Experience Platform 및 Customer Journey Analytics을 처음 사용하는 경우에도 필요한 모든 특정 지침을 제공합니다.

독립형 Content Analytics 설정을 시작하기 전에 다음을 수행해야 합니다.

* 웹 분석 개념에 대한 기본 이해, 태그 관리 시스템에 대한 친숙도 및 기본 JavaScript 지식을 갖추고 있습니다.
* 초기 설정에 대해 4~6시간을 계획하고 설정을 테스트하고 확인하는 추가 시간을 계획하십시오.

## 용어

이 안내서에서는 익숙하지 않을 수 있는 Experience Platform 및 Customer Journey Analytics의 여러 기술 용어를 사용합니다. 다음은 Content Analytics의 컨텍스트에서 이러한 용어(참조 링크 포함)에 대한 설명입니다.

| 용어 | 설명 |
|---|---|
| **스키마** | [스키마](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/schema/composition)은(는) 데이터의 구조와 형식을 나타내고 유효성을 검사하는 규칙 집합입니다. 스키마는 높은 수준에서 클릭과 같이 웹 사이트에서 발생하는 이벤트와 같은 실제 개체에 대한 추상적인 정의를 제공합니다. 그리고 해당 객체의 각 인스턴스에 포함되어야 하는 데이터에 대해 간략히 설명합니다. |
| **데이터 세트** | [dataset](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)은(는) 스키마(열) 및 필드(행)를 포함하는 데이터 컬렉션(일반적으로 테이블)에 대한 저장소 및 관리 구성입니다. 데이터 집합은 각 행이 웹 사이트의 이벤트인 데이터베이스 테이블과 같습니다. |
| **데이터스트림** | [데이터스트림](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview)은(는) 웹 사이트에서 Adobe Experience Platform의 올바른 데이터 세트로 데이터를 라우팅하는 서버측 구성을 나타냅니다. 데이터 스트림은 사이트를 스토리지에 연결하는 데이터 하이웨이 역할을 합니다. |
| **태그** | Experience Platform의 [태그](https://experienceleague.adobe.com/en/docs/experience-platform/tags/home)은(는) Adobe의 차세대 태그 관리 기능입니다. 태그는 관련 고객 환경을 향상하는 데 필요한 분석, 마케팅 및 광고 태그를 배포하고 관리하는 간단한 방법을 고객에게 제공합니다. Content Analytics에서는 Adobe의 태그 관리 시스템을 사용하여 모든 페이지를 유사하게 편집할 필요 없이 웹 사이트에 추적 코드를 배포할 수 있습니다. 태그 기능은 Google 태그 관리자에서 알 수 있는 기능과 유사합니다. |
| **샌드박스** | Experience Platform은 디지털 경험 애플리케이션을 개발하고 발전시키는 데 도움이 되는 단일 Experience Platform 인스턴스를 별도의 가상 환경으로 분할하는 [샌드박스](https://experienceleague.adobe.com/ko/docs/experience-platform/sandbox/home)를 제공합니다. Content Analytics은 일반적으로 *프로덕션* 샌드박스를 사용합니다. |
| **연결** | [연결](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview)은(는) 수집되는 Experience Platform 데이터 세트를 정의합니다. 연결은 데이터 세트(AEP에 데이터가 저장되는 데이터 세트)와 Customer Journey Analytics(데이터를 분석하는 데이터 세트) 간의 링크를 정의합니다. 연결을 통해 수집된 데이터를 보고에 사용할 수 있습니다. |
| **데이터 보기** | [데이터 보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/data-views)는 연결에서 데이터를 해석하는 방법을 결정할 수 있는 컨테이너입니다. 데이터 보기는 사용자가 보고할 수 있는 모든 차원과 지표를 지정합니다. 데이터 보기는 분석에 사용할 수 있는 행과 열을 결정하는 구성과 같습니다. |
| **Analysis Workspace** | [Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/home)은(는) Content Analytics 보고서와 분석을 작성하는 데 사용하는 드래그 앤 드롭 브라우저 인터페이스입니다. |
| **경험** | Content Analytics에서 [경험](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics#terminology)은(는) 페이지 URL을 기반으로 캡처하고 분석할 수 있는 웹 페이지의 모든 텍스트 콘텐츠를 참조합니다. |
| **자산** | Content Analytics에서 [asset](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics#terminology)은(는) 이미지와 같은 개별적이고 고유한 콘텐츠입니다. |


## 설정 개요

이 구성은 작동 중인 **독립 실행형** Content Analytics 구현이 필요한 모든 응용 프로그램의 설정을 안내합니다. 설정을 세 단계로 나눌 수 있으며, 여기서 각 단계는 이전 단계를 기반으로 합니다.

**1단계** - [환경 준비](#prepare-your-environment). 이 단계에서는 사용자 권한을 설정하고 데이터 인프라를 확인합니다. 이러한 적절한 권한과 데이터 구조가 없으면 나머지 단계를 완료할 수 없습니다. 관련 단계는 다음과 같습니다.

1. Content Analytics 구성 및 구현을 지원하려면 **액세스 제어 및 권한을 구성**&#x200B;하십시오.
1. **스키마 및 데이터 집합을 설정**&#x200B;하여 콘텐츠 분석 인사이트를 수집할 데이터의 모델(스키마)과 해당 데이터(데이터 집합)를 수집할 위치를 정의합니다.

**2단계** - [데이터 수집 구성](#configure-data-collection). 이 단계에서는 웹 사이트의 콘텐츠 데이터를 캡처하는 파이프라인을 만듭니다. 따라서 Content Analytics은 방문자가 콘텐츠에 참여하는 콘텐츠를 알고 있습니다.

1. 수집된 데이터가 데이터 집합으로 라우팅되는 방법을 구성하려면 **데이터 스트림을 설정**&#x200B;합니다.
1. **웹 사이트 태그를 사용하여** 웹 사이트의 데이터 레이어에 있는 데이터에 대해 규칙과 데이터 요소를 구성하고 데이터가 구성된 데이터 스트림으로 전송되는지 확인하십시오.
1. 프로덕션 환경에 게시하기 전에 테스트 환경에 **배포**&#x200B;하고 데이터 수집을 확인&#x200B;**합니다**.

**3단계** - [보고 설정](#set-up-reporting). 이 단계에서는 수집된 데이터를 보고서에서 분석할 수 있도록 합니다. 따라서 Content Analytics에서 얻고자 하는 콘텐츠 성능 인사이트를 실제로 얻을 수 있습니다.

1. 데이터 집합에 대해 **연결을 설정**&#x200B;합니다.
1. 지표 및 차원을 정의하려면 **데이터 보기를 설정합니다**.
1. **Content Analytics 구성 및 구현**.
1. **프로젝트를 설정하여** Content Analytics 보고서와 시각화를 빌드합니다.


## 환경 준비

이 단계에서는 사용자 권한을 설정하고 데이터 인프라를 확인합니다.

### 액세스 제어 및 권한 구성

이 섹션에서는 제품, 제품 프로필에 필요한 액세스 권한과 독립형 Content Analytics을 구성하고 설정하는 데 필요한 권한에 대해 설명합니다. Content Analytics의 기능에만 관심이 있지만 해당 기능이 제대로 작동하려면 다른 Experience Platform 제품에 대한 액세스 및 권한이 필요합니다.

#### 액세스 제어

액세스 제어는 Experience Platform 제품에 대한 액세스가 허용되는지 여부를 결정합니다.

시스템 관리자나 제품 관리자가 사용자를 제품 또는 제품 프로필의 관리자로 추가해야 합니다. 제품 관리자는 관리 제품(프로필)에 대한 관리자로만 사용자를 추가할 수 있으며, 시스템 관리자는 제품(프로필)에 제품 관리자를 추가할 수 있습니다.

>[!BEGINSHADEBOX]

데모 비디오는 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [제품 프로필에 대한 사용자 관리](https://video.tv.adobe.com/v/333860/?quality=12&learn=on){target="_blank"}를 참조하십시오.


>[!ENDSHADEBOX]

독립형 Content Analytics을 사용하려면 다음 제품 및 제품 프로필에 대한 제품 관리자여야 합니다.

* Adobe Experience Platform
   * AEP-Default-All-Users(프로덕션 샌드박스에 액세스하기 위한 기본 프로필)

* Adobe Experience Platform 데이터 수집
   * 기본 데이터 수집 모든 액세스

* Adobe Experience Platform Privacy Service

* Customer Journey Analytics (사용자 지정)
   * Customer Journey Analytics(또는 기타 기본 제공된 제품 프로필)

Admin Console을 통해 제품 관리자 액세스 권한을 정의합니다.

1. [Admin Console](https://adminconsole.adobe.com)에 액세스합니다.
1. **[!UICONTROL 제품]**&#x200B;을 선택하세요.
1. 특정 제품을 선택합니다.
1. **[!UICONTROL 관리자]** 탭을 선택합니다.
1. 제품에 관리자를 추가하려면 **[!UICONTROL 관리자 추가]**&#x200B;를 선택하십시오.
1. **[!UICONTROL 제품 관리자 추가]** 대화 상자에 전자 메일 또는 사용자 이름을 하나 이상 입력하십시오. 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.


Admin Console을 통해 제품 프로필 관리자 액세스 권한을 정의합니다.

1. [Admin Console](https://adminconsole.adobe.com)에 액세스합니다.
1. **[!UICONTROL 제품]**&#x200B;을 선택하세요.
1. 특정 제품을 선택합니다. 이미 제품 관리자 액세스 권한이 있는지 확인합니다.
1. **[!UICONTROL 제품 프로필]**&#x200B;을 선택하세요.
1. 특정 제품 프로필을 선택합니다.
1. **[!UICONTROL 관리자]** 탭을 선택합니다.
1. 제품 프로필에 관리자를 추가하려면 **[!UICONTROL 관리자 추가]**&#x200B;를 선택하십시오.
1. **[!UICONTROL 제품 프로필 관리자 추가]** 대화 상자에 전자 메일 또는 사용자 이름을 하나 이상 입력하십시오. 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.


#### 권한

권한은 제품에 대한 액세스 권한이 있는 경우 제품 내에서 수행할 수 있는 작업을 정의합니다.

[!UICONTROL 권한] 인터페이스에서 Experience Platform에 대한 권한을 정의하고 특성 기반 액세스 제어를 사용합니다. Customer Journey Analytics의 경우 [!UICONTROL Admin Console]을(를) 통해 권한을 정의합니다.

##### Experience Platform

Experience Platform의 [!UICONTROL 권한] 인터페이스는 역할 정의를 기반으로 합니다. 역할은 리소스 기반 권한의 컬렉션입니다. 프로비저닝된 새 환경에서는 **[!UICONTROL 기본 프로덕션 모든 액세스]** 및 **[!UICONTROL 샌드박스 관리자]**&#x200B;의 두 가지 기본 역할을 사용할 수 있습니다.

Content Analytics의 경우 다음 리소스 및 관련 권한이 이러한 역할에 추가되었는지 확인해야 합니다.

* 기본 프로덕션 모든 액세스 역할

   * 데이터 수집
      * 데이터스트림 보기
      * 데이터 스트림 관리

   * 데이터 관리
      * 데이터 세트 보기
      * 데이터 세트 관리

   * 데이터 모델링
      * 스키마 보기
      * 스키마 관리
      * ID 메타데이터 관리


* 샌드박스 관리자 역할

   * 샌드박스
      * Prod
      * (Content Analytics에 사용할 다른 모든 샌드박스)

   * 샌드박스 관리
      * 패키지 관리
      * 샌드박스 관리
      * 샌드박스 재설정
      * 샌드박스 보기


권한 인터페이스에서 역할과 관련 권한을 모두 확인할 수 있습니다. 역할에 속하는 사용자를 지정합니다.

1. 조직의 Experience Platform에 액세스합니다.
1. 시작 화면의 **[!UICONTROL 빠른 액세스]**&#x200B;에서 **[!UICONTROL 모두 보기]**&#x200B;를 선택합니다.
1. ![사용 권한](/help/assets/icons/PinOn.svg)에 대해 **[!UICONTROL PinOn]** 핀을 사용하도록 설정하세요. **[!UICONTROL 사용 권한]**&#x200B;은(는) 나중에 사용할 수 있도록 **[!UICONTROL 빠른 액세스]** 내에서 사용할 수 있습니다.
1. **[!UICONTROL 권한]**&#x200B;을 선택하세요.
1. ![사용자](/help/assets/icons/User.svg) **[!UICONTROL 역할]**&#x200B;을(를) 선택하십시오.
1. 확인할 특정 역할을 선택합니다(예: **[!UICONTROL 기본 프로덕션 모든 액세스]**). 모든 권한을 보려면 **[!UICONTROL 모두 보기]**&#x200B;를 선택하십시오.
1. **[!UICONTROL 세부 정보]** 화면:
   1. **[!UICONTROL 권한]**&#x200B;에 나열된 **[!UICONTROL 리소스]**&#x200B;을(를) 확인하십시오.
   1. **[!UICONTROL 샌드박스]**&#x200B;에서 샌드박스 이름을 확인하십시오.

   업데이트하려면 ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]**&#x200B;을 선택하세요.
   1. 누락된 리소스를 추가하려면 **[!UICONTROL 리소스]** > ![Adobe Experience Platform](/help/assets/icons/Add.svg) 왼쪽 레일에서 **[!UICONTROL 리소스 이름]** **[!UICONTROL 추가]**&#x200B;를 선택하십시오.
   1. 누락된 권한을 추가하려면 기본 패널에서 해당 권한이 누락된 리소스 내에서 ![V자형 화살표](/help/assets/icons/ChevronDown.svg)를 선택하고 누락된 권한을 선택합니다.

      ![권한 인터페이스](/help/content-analytics/assets/aep-permissions-ui.png)

   업데이트를 저장하려면 **[!UICONTROL 저장]**&#x200B;을(를) 선택하십시오.

1. 사용자 또는 사용자 그룹 화면에서 다음을 수행합니다.
   1. 올바른 개인 사용자 또는 사용자 그룹이 이 역할에 속하는지 확인하십시오.
      1. Admin Console에서 정의한 개별 사용자를 추가하려면 ![사용자추가](/help/assets/icons/UserAdd.svg) 사용자에서 사용자 추가를 선택하십시오.
      1. ![사용자 그룹에 그룹 추가](/help/assets/icons/Add.svg)를 선택하여 Admin Console에서 정의한 사용자 그룹을 추가합니다.


##### Customer Journey Analytics

Customer Journey Analytics은 속성 기반 액세스 제어를 지원하지 않습니다. 권한을 지정하려면 Admin Console을 사용합니다.

Content Analytics의 경우 다음 Customer Journey Analytics 제품 프로필 권한이 포함되어 있는지 확인해야 합니다.

* 데이터 보기
   * 사용 가능한 모든 데이터 보기.

* 보고 도구
   * 분석 액세스 가이드?
   * 계산된 지표 만들기
   * 세그먼트 생성
   * Labs 액세스?
   * 주석 작성
   * 대상자 만들기?
   * 대상 보기?
   * 감사 로그 액세스
   * 모든 사용자와 프로젝트 링크 공유
   * 예측
   * AI 어시스턴트: 제품 지식
   * Data Insights 에이전트
   * 지능형 캡션
   * 데이터 Storytelling?

* 데이터 보기 도구
   * 전체 테이블 내보내기?
   * CJA BI 확장?

Customer Journey Analytics에 대한 이러한 권한을 확인하고 업데이트하려면 다음을 수행하십시오.

1. [Admin Console](https://adminconsole.adobe.com)에 액세스합니다.
1. **[!UICONTROL 제품]**&#x200B;을 선택하세요.
1. **[!UICONTROL Customer Journey Analytics]** 제품을 선택하십시오.
1. **[!UICONTROL 제품 프로필]**&#x200B;을 선택하세요.
1. Customer Journey Analytics에 사용할 수 있는 기본 프로비저닝된 제품 프로필을 선택합니다. 예: **[!UICONTROL Customer Journey Analytics]**.
1. 제품 프로필 화면에서 **[!UICONTROL 권한]**&#x200B;을 선택합니다.
1. ![편집](/help/assets/icons/Edit.svg) 버튼을 선택하여 권한을 편집합니다. **[!UICONTROL Customer Journey Analytics에 대한 권한 편집]** 대화 상자에서 다음 작업을 수행합니다.

   ![CJA 권한 UI](../assets/cja-permissions-ui.png)

   1. **[!UICONTROL 데이터 보기]**&#x200B;를 선택하고 **[!UICONTROL 자동 포함: 켜짐]**&#x200B;을 사용하도록 설정합니다. 이 토글을 수행하면 모든 데이터 보기가 자동으로 **[!UICONTROL 포함된 권한 항목]**&#x200B;의 일부가 됩니다.
   1. **[!UICONTROL 보고 도구]**&#x200B;를 선택하고 위에 나열된 모든 권한이 **[!UICONTROL 포함된 권한 항목]**&#x200B;의 일부인지 확인하십시오.
   1. **[!UICONTROL 데이터 보기 도구]**&#x200B;를 선택하고 위에 나열된 모든 권한이 **[!UICONTROL 포함된 권한 항목]**&#x200B;의 일부인지 확인하십시오.

   **[!UICONTROL 저장]**&#x200B;을 선택합니다.


### 스키마 및 데이터 세트 설정

Content Analytics 인사이트에 따라 웹 사이트에서 데이터를 수집하려면 먼저 수집하려는 데이터 종류를 정의해야 합니다. 또한 데이터가 저장되는 방법도 살펴봅니다. 두 개념 모두 [Adobe Experience Platform Web SDK을 통해 데이터 수집](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset) 빠른 시작 안내서의 [스키마 및 데이터 집합 설정](/help/data-ingestion/aepwebsdk.md)에서 설명합니다.


## 데이터 수집 구성

이 단계에서는 웹 사이트의 콘텐츠 데이터를 캡처하는 파이프라인을 만듭니다.

### 데이터스트림 설정

수집할 데이터 및 해당 데이터를 저장하는 방법을 정의했습니다. 다음 단계는 웹 사이트에서 수집된 데이터가 데이터 세트로 라우팅되도록 하는 것입니다. 데이터 스트림을 설정하고 구성해야 합니다. 데이터 스트림은 [Adobe Experience Platform Web SDK을 통한 데이터 수집](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream) 빠른 시작 안내서의 [데이터 스트림 설정](/help/data-ingestion/aepwebsdk.md)에 설명되어 있습니다.


### 태그 사용

수집할 데이터(스키마), 해당 데이터를 저장하는 방법(데이터 세트) 및 웹 사이트에서 수집한 데이터가 데이터 세트(데이터 스트림)로 라우팅되는 방법을 정의했습니다. 다음 단계로, 웹 사이트에 태그를 지정하여 웹 사이트의 데이터 레이어에 있는 데이터에 대해 규칙 및 데이터 요소를 구성해야 합니다. 웹 사이트에 태그를 지정하면 구성된 데이터 스트림으로 데이터가 전송됩니다. Tags를 통한 웹 사이트의 태그 지정은 [Adobe Experience Platform Web SDK을 통한 데이터 수집](/help/data-ingestion/aepwebsdk.md#use-tags) 빠른 시작 안내서의 [태그 사용](/help/data-ingestion/aepwebsdk.md)에 설명되어 있습니다.


### 배포 및 검증

이제 `<head>` 태그 내에 있는 웹 사이트 개발 버전에 코드를 배포할 수 있습니다. 배포되면 웹 사이트에서 Adobe Experience Platform으로 데이터 수집을 시작합니다. 그런 다음 해당 데이터는 Content Analytics의 적용을 받습니다.

구현의 유효성을 검사하고, 필요한 경우 수정한 다음, 태그가 제공하는 게시 작업 과정 기능을 사용하여 스테이징 및 프로덕션 환경에 배포합니다


## 보고 설정

이 단계에서는 수집된 데이터를 보고서에서 분석할 수 있도록 합니다.

### 데이터 세트에 대한 연결 설정

수집된 데이터에 대해 보고하고 Content Analytics에 대해 해당 데이터를 구성하려면 Customer Journey Analytics에서 연결을 설정해야 합니다. 연결은 수집된 데이터를 포함하는 데이터 세트에 연결합니다. 연결 설정 방법은 [Adobe Experience Platform Web SDK을 통해 데이터 수집](../../data-ingestion/aepwebsdk.md#set-up-a-connection) 빠른 시작 안내서의 [연결 설정](/help/data-ingestion/aepwebsdk.md)에 설명되어 있습니다.


### 데이터 보기 설정

Content Analytics을 구성하기 전의 마지막 단계는 데이터 보기를 정의하는 것입니다. 데이터 보기는 Customer Journey Analytics와 관련된 컨테이너입니다. 이를 통해 연결에서 데이터를 해석하는 방법을 결정할 수 있습니다. 데이터 보기를 사용하면 Customer Journey Analytics이 연결된 하나 이상의 데이터 세트의 데이터에서 지표와 차원을 정의할 수 있습니다. 데이터 보기를 설정하는 방법은 [Adobe Experience Platform Web SDK을 통해 데이터 수집](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view) 빠른 시작 안내서의 [데이터 보기 설정](/help/data-ingestion/aepwebsdk.md)에 설명되어 있습니다.


### Content Analytics 구성

이제 Content Analytics을 구성할 수 있는 모든 것이 준비되었습니다.

#### 안내식 구성

[안내가 있는 구성 마법사](guided.md)를 사용하고 [데이터 보기 설정](#set-up-a-data-view) 단계의 일부로 만든 데이터 보기를 선택하십시오. 이 옵션을 선택하면 웹 사이트에서 수집한 데이터 위에 Content Analytics이 구성 및 구현됩니다.

안내식 구성 마법사는 다음과 같은 추가적인 특정 Content Analytics 개체를 구성합니다.

* Content Analytics 이벤트에 대해 자동으로 설정되는 **데이터 집합**. 이 데이터 세트는 이미 생성되고 사용 가능한 특정 Content Analytics 스키마를 사용합니다.
* Content Analytics 이벤트를 Content Analytics 데이터 세트로 스트리밍하도록 자동으로 설정된 **데이터 스트림**.
* **Tags 속성**, 자동으로 설정되며 Content Analytics 확장으로 구성됩니다. 이 Tags 속성은 웹 사이트에서 Content Analytics 데이터를 Content Analytics 데이터 스트림 및 Content Analytics 데이터 세트로 전송하도록 합니다.

  >[!IMPORTANT]
  >
  >마법사의 [데이터 수집](guided.md#new-configuration-1) 단계의 일부로 새 태그 속성을 만드는 옵션을 선택하십시오.
  >


#### 수동 구성

웹 사이트에 Content Analytics을 구현하려면 Content Analytics Tags 속성을 [수동으로](manual.md)게시해야 합니다.


### 프로젝트 설정

Customer Journey Analytics에서 프로젝트를 설정하여 [Content Analytics 보고서 및 시각화](/help/content-analytics/report/report.md)를 빌드합니다. 또는 [Content Analytics 템플릿](/help/content-analytics/report/report.md#template)을 사용하여 시작할 수 있습니다.

