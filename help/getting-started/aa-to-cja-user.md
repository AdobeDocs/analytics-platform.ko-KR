---
title: Adobe Analytics 사용자를 위한 CJA 사용 안내서
description: 회사가 데이터를 Adobe Analytics에서 Customer Journey Analytics으로 이동할 때 사용자의 관점에서 고려해야 할 사항
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: d31f07d8b26ea4d60481c040a0ca1ba491d4ecf0
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 26%

---


# Adobe Analytics 사용자를 위한 CJA 사용 안내서

>[!NOTE]
>
>이 페이지는 현재 개발 중입니다.

축하합니다. 귀사는 Customer Journey Analytics과 함께 일하기 시작합니다. Adobe Analytics에 익숙한 사용자라면 이미 멋진 시작을 보입니다. Customer Journey Analytics을 사용할 때, 몇 가지 큰 차이점과 몇 가지 유사점을 볼 수 있습니다. 이 페이지는 변경되지 않은 부분과 몇 가지 주요 차이점을 설명하기 위한 것입니다. 또한 새로운 개념에 대한 자세한 정보를 얻는 방법과 고객 여정을 보다 쉽고 성공적으로 만드는 추가 단계를 알려드리겠습니다.

## 변경되지 않은 사항

보고 측면에 익숙한 많은 것이 변경되지 않았습니다. Analysis Workspace의 강력한 기능을 사용하여 데이터를 분석할 수 있습니다. 또한 동일한 버전의 Adobe Analytics 대시보드를 원하는 대로 사용할 수 있습니다. 작업 공간 및 대시보드는 기존 Adobe Analytics에서 했던 것과 기본적으로 동일합니다. Report Builder은 새로운 인터페이스를 갖추고 있으며 이제 PC, Mac 컴퓨터 및 웹 버전의 Excel에서 실행됩니다. 보고에 따라 다른 점은 분석할 훨씬 더 많은 크로스 채널 데이터에 액세스할 수 있다는 것입니다. 다음은 몇 가지 다중 채널 시각화의 예입니다.

![다중 채널](assets/cross-channel.png)

## 새로운 아키텍처

Customer Journey Analytics은 Adobe Experience Platform에서 데이터를 가져옵니다. Experience Platform을 사용하면 모든 시스템 또는 채널의 고객 데이터와 컨텐츠를 중앙 집중화 및 표준화하고 데이터 과학 및 시스템 학습을 적용하여 개인화된 경험의 디자인과 전달을 향상시킬 수 있습니다.

플랫폼의 고객 데이터는 스키마 및 데이터 배치로 구성된 데이터 세트로 저장됩니다. 플랫폼에 대한 자세한 내용은 [Adobe Experience Platform 아키텍처 개요](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=ko)를 참조하십시오.

CJA 관리자가 설정함 [연결](/help/connections/create-connection.md) Platform에서 데이터 세트를 가져올 수 있습니다. 그런 다음 빌드되었습니다 [데이터 보기](/help/data-views/data-views.md) 해당 연결 내에서 사용할 수 있습니다. 데이터 보기는 가상 보고서 세트와 유사하다고 생각하십시오. 데이터 보기는 Customer Journey Analytics에서 보고의 기반입니다.

## 새로운 개념 및 용어

기존 Adobe Analytics과 비교하여 업계 표준에 맞게 CJA의 여러 기능이 이름을 바꾸고 재설계되었습니다. 업데이트된 용어 중 일부는 세그먼트, 가상 보고서 세트, 분류, 고객 속성 및 컨테이너 이름을 포함합니다. eVar 및 prop과 같은 친숙한 개념이 제한 사항과 함께 더 이상 존재하지 않습니다.

### eVar 및 prop

기존 Adobe Analytics 센스의 [!UICONTROL eVar], [!UICONTROL prop], [!UICONTROL 이벤트]는 [!UICONTROL Customer Journey Analytics]에 더 이상 존재하지 않습니다. 무제한 스키마 요소(차원, 지표, 목록 필드)가 있습니다. 따라서 이제 데이터 수집 프로세스 동안 적용했던 모든 속성 설정이 쿼리 시간에 적용됩니다.

### 이제 세그먼트가 &#39;필터&#39;입니다

[!UICONTROL Customer Journey Analytics]는 더 이상 eVar, prop, 이벤트를 사용하지 않으며 대신 AEP 스키마를 사용합니다. 즉, 기존 세그먼트가 [!UICONTROL Customer Journey Analytics]. 또한 &quot;세그먼트&quot;의 이름이 &quot;필터&quot;로 변경되었습니다.

당분간 공유/게시할 수 없습니다 [!UICONTROL 필터] ([!UICONTROL 세그먼트])에서 ) [!DNL Customer Journey Analytics] 통합 Experience Platform 또는 기타 Experience Cloud 응용 프로그램 이 기능은 현재 개발 중입니다.

### 계산된 지표

[!UICONTROL Customer Journey Analytics]는 더 이상 eVar, prop, 이벤트를 사용하지 않으며 대신 AEP 스키마를 사용합니다. 즉, 기존의 계산된 지표가 [!UICONTROL Customer Journey Analytics].

### 세션 및 변수 지속성 설정

[!UICONTROL Customer Journey Analytics]의 경우 이러한 모든 설정은 보고서 시간에 적용되며 데이터 보기에 있습니다. 이제 이러한 설정을 변경하면 소급 적용되며, 여러 데이터 보기를 사용하여 여러 버전을 보유할 수 있습니다.

### 이제 가상 보고서 세트가 &#39;데이터 보기&#39;입니다



### 이제 분류는 &#39;조회 데이터 세트&#39;입니다

### 이제 고객 속성이 &#39;프로필 데이터 세트&#39;입니다


### 이제 히트 컨테이너가 &#39;이벤트&#39; 컨테이너입니다.

### 이제 방문 컨테이너가 &#39;세션&#39; 컨테이너입니다.

### 이제 방문자 컨테이너가 &#39;개인&#39; 컨테이너입니다

### `Uniques Exceeded` 제한 사항

[!UICONTROL Customer Journey Analytics에는 고유 값 제한이 없으므로 걱정할 필요가 없습니다.]