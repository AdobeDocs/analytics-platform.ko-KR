---
title: Adobe Analytics 사용자를 위한 CJA 사용 안내서
description: 회사가 데이터를 Adobe Analytics에서 Customer Journey Analytics으로 이동할 때 사용자의 관점에서 고려해야 할 사항
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 3af757fd311d7a92e56aa9ce5939dc3db8dcf6fa
workflow-type: tm+mt
source-wordcount: '1051'
ht-degree: 18%

---

# Adobe Analytics 사용자를 위한 CJA 사용 안내서

귀사에서 Customer Journey Analytics을 채용하기 시작했습니다. Adobe Analytics에 익숙한 사용자라면 이미 멋진 시작을 보입니다. Customer Journey Analytics을 사용할 때, 몇 가지 유사성과 몇 가지 큰 차이점을 발견할 것입니다. 이 페이지는 변경되지 않은 부분과 몇 가지 주요 차이점을 설명하기 위한 것입니다. 또한 새로운 개념에 대한 자세한 정보를 얻는 방법과 고객 여정을 보다 쉽고 성공적으로 만드는 추가 단계를 알려드리겠습니다.

기존 Adobe Analytics과 비교하여 업계 표준에 맞게 CJA의 여러 기능이 이름을 바꾸고 재설계되었습니다. 업데이트된 용어 중 일부는 세그먼트, 가상 보고서 세트, 분류, 고객 속성 및 컨테이너 이름을 포함합니다. eVar 및 prop과 같은 친숙한 개념이 제한 사항과 함께 더 이상 존재하지 않습니다.

## 변경되지 않은 사항

보고 측면에 익숙한 많은 것이 변경되지 않았습니다.

* 여전히 의 기능을 사용할 수 있습니다. [Analysis Workspace](/help/analysis-workspace/home.md) 를 입력하여 데이터를 분석할 수 있습니다. 작업 공간은 기존 Adobe Analytics에서와 동일한 방식으로 작동합니다.
* 또한 동일한 버전의 [Adobe Analytics 대시보드](/help/mobile-app/home.md) 마음대로 하세요. 대시보드(Mobile 앱이라고도 함)는 기존 Adobe Analytics에서와 동일하게 작동합니다.
* [Report Builder](/help/report-builder/report-buider-overview.md) 에는 새로운 인터페이스가 있고 이제 PC, Mac 및 Excel 웹 버전에서 실행됩니다.

보고와 관련하여 **다른 기능** 분석할 훨씬 더 많은 크로스 채널 데이터에 액세스할 수 있다는 것입니다. 다음은 크로스 채널 데이터 소스를 포함하는 일부 시각화의 예입니다.

![다중 채널 시각화](assets/cross-channel.png)

## 새로운 아키텍처 {#architecture}

Customer Journey Analytics은 Adobe Experience Platform에서 데이터를 가져옵니다. Experience Platform을 사용하면 모든 시스템 또는 채널의 고객 데이터와 컨텐츠를 중앙 집중화 및 표준화하고 데이터 과학 및 시스템 학습을 적용하여 개인화된 경험의 디자인과 전달을 향상시킬 수 있습니다.

플랫폼의 고객 데이터는 스키마 및 데이터 배치로 구성된 데이터 세트로 저장됩니다. 플랫폼에 대한 자세한 내용은 [Adobe Experience Platform 아키텍처 개요](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=ko)를 참조하십시오.

CJA 관리자가 설정함 [연결](/help/connections/create-connection.md) Platform에서 데이터 세트를 가져올 수 있습니다. 그런 다음 빌드되었습니다 [데이터 보기](/help/data-views/data-views.md) 해당 연결 내에서 사용할 수 있습니다. 데이터 보기는 가상 보고서 세트와 유사하다고 생각하십시오. 데이터 보기는 Customer Journey Analytics에서 보고의 기반입니다. 보고서 세트의 개념이 더 이상 존재하지 않습니다.

## 보고서 세트 {#report-suites}

보고서 세트 데이터는 Adobe Analytics 소스 커넥터 또는 웹 SDK를 통해 Experience Platform으로 가져올 수 있습니다. 특히 조직이 Adobe Analytics 플랫폼에 있고 CJA/AEP를 추가하는 경우 그러합니다. 일반적으로 Analytics 스키마를 사용하여 보고서 세트별로 지정된 데이터 세트를 소스를 만듭니다.

## (가상) 보고서 세트가 이제 &#39;데이터 보기&#39;입니다 {#data-views}

[!UICONTROL 데이터 보기] 가상 보고서 세트의 개념을 가져와 을(를) [데이터에 대한 추가 제어 사용](/help/data-views/create-dataview.md) 연결에서 사용할 수 있습니다. 이를 통해 시간대 및 세션 시간 초과 간격을 구성할 수 있습니다. 개별 차원에 대한 속성 및 만료 속성을 동적으로 적용할 수도 있습니다. 이러한 권한은 모든 데이터에 소급하여 적용됩니다.

**필요한 작업**:

* Workspace에서 사용하는 보고서 세트 선택기를 사용하면 관리자가 사용자와 공유한 데이터 보기 중에서 선택할 수 있습니다.

   ![data-view-selector](assets/data-views.png)

* 많은 것들을 숙지하세요 [데이터 보기에 대한 사용 사례](/help/data-views/data-views-usecases.md).

## eVar 및 prop

기존 Adobe Analytics 센스의 [!UICONTROL eVar], [!UICONTROL prop], [!UICONTROL 이벤트]는 [!UICONTROL Customer Journey Analytics]에 더 이상 존재하지 않습니다. 무제한 스키마 요소(차원, 지표, 목록 필드)가 있습니다. 따라서 이제 데이터 수집 프로세스 동안 적용했던 모든 속성 설정이 쿼리 시간에 적용됩니다. CJA 관리자는 데이터 보기를 만듭니다

**필요한 작업**:

* 이러한 스키마 요소를 사용하여 데이터를 드릴다운할 수 있는 다양한 방법을 숙지하십시오.

## 이제 세그먼트가 &#39;필터&#39;입니다

[!UICONTROL Customer Journey Analytics]는 더 이상 eVar, prop, 이벤트를 사용하지 않으며 대신 AEP 스키마를 사용합니다. 즉, 기존 세그먼트가 [!UICONTROL Customer Journey Analytics]. 또한 &quot;세그먼트&quot;의 이름이 &quot;필터&quot;로 변경되었습니다.

당분간 공유/게시할 수 없습니다 [!UICONTROL 필터] ([!UICONTROL 세그먼트])에서 ) [!DNL Customer Journey Analytics] 통합 Experience Platform 또는 기타 Experience Cloud 응용 프로그램 이 기능은 현재 개발 중입니다.

**필요한 작업**:

* 기존 Adobe Analytics 세그먼트를 Customer Journey Analytics으로 이동하려면 다음을 봅니다. [이 비디오](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=ko).
* 그렇지 않으면 Customer Journey Analytics에서 필터를 다시 만듭니다.

## 계산된 지표

[!UICONTROL Customer Journey Analytics]는 더 이상 eVar, prop, 이벤트를 사용하지 않으며 대신 AEP 스키마를 사용합니다. 즉, 기존의 계산된 지표가 [!UICONTROL Customer Journey Analytics].

**필요한 작업**:

* Adobe Analytics 계산된 지표를 Customer Journey Analytics으로 이동하려면 다음을 봅니다. [이 비디오](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=ko).
* 그렇지 않으면 Customer Journey Analytics에서 계산된 지표를 다시 만듭니다.


## 크로스 보고서 세트 데이터

여러 데이터 세트의 기존 구현을 Experience Platform에 결합할 수 있습니다. 이러한 데이터 세트를 기반으로 하는 연결 및 데이터 보기는 별도의 보고서 세트에 이전에 존재했던 데이터를 결합할 수 있습니다.

**필요한 작업**:

## 세션 및 변수 지속성 설정

[!UICONTROL Customer Journey Analytics] 이러한 설정은 보고서 시간에 적용되며, 이제 [데이터 보기](/help/data-views/component-settings/persistence.md). 이제 이러한 설정을 변경하면 소급 적용되며, 여러 데이터 보기를 사용하여 여러 버전을 보유할 수 있습니다.

**필요한 작업**:

## 이제 분류는 &#39;조회 데이터 세트&#39;입니다



## 이제 고객 속성이 &#39;프로필 데이터 세트&#39;입니다


## 컨테이너의 이름이 변경되었습니다

컨테이너를 지정합니다 [만드는 모든 데이터 보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers).
* **이제 히트 컨테이너가 &#39;이벤트&#39; 컨테이너입니다.**. [!UICONTROL 개인] 컨테이너에는 지정된 시간대 내의 방문자에 대한 모든 세션 및 이벤트가 포함됩니다.
* **이제 방문 컨테이너가 &#39;세션&#39; 컨테이너입니다.**. [!UICONTROL 세션] 컨테이너에서 특정 세션에 대한 페이지 상호 작용, 캠페인 또는 대화를 식별할 수 있습니다.
* **이제 방문자 컨테이너가 있습니다. [!UICONTROL 개인] 컨테이너**. [!UICONTROL 개인] 컨테이너에는 지정된 시간대 내의 방문자에 대한 모든 세션 및 이벤트가 포함됩니다.

**필요한 작업**:

조직의 요구 사항에 맞게 컨테이너 이름을 변경할 수 있는 옵션이 있습니다.


## `Uniques Exceeded` 제한 사항

[!UICONTROL Customer Journey Analytics에는 고유 값 제한이 없으므로 걱정할 필요가 없습니다.]
