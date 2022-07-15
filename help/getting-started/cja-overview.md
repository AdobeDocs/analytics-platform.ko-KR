---
title: Customer Journey Analytics 개요
description: Customer Journey Analytics를 통해 Experience Platform의 데이터와 함께 Analysis Workspace를 사용하는 방법을 알아봅니다.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 64cd3983f58f1f0de1d8639e5cb1e705dd72ef44
workflow-type: tm+mt
source-wordcount: '1149'
ht-degree: 100%

---

# Customer Journey Analytics 개요

Customer Journey Analytics는 Analysis Workspace의 강력한 기능을 Adobe Experience Platform의 데이터에 사용할 수 있는 Analytics 기능입니다. 데이터 분류, 필터링, 쿼리 및 시각화 작업을 할 수 있으며, 모든 종류의 데이터 스키마와 유형을 보유할 수 있는 플랫폼의 기능과 결합되어 있습니다. **XDM(Experience Data Model)**&#x200B;을 사용하여 데이터를 조합하고 탐색할 수 있도록 균일하게 나타내고 구성할 수 있습니다. **Experience Query Services**&#x200B;를 사용하면 SQL 호환 도구와 프레임워크를 사용하여 모든 데이터를 쿼리하고 조작할 수 있습니다.

다음은 고차원 CJA 아키텍처입니다.

![아키텍처](assets/cja-architecture.png)

다음은 Customer Journey Analytics 구성에 대한 비디오 개요입니다.

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## CJA와 기존 Adobe Analytics 비교하기

Customer Journey Analytics는 사용하기 쉬운 크로스 채널 기능을 제공하고 이전 버전의 Adobe Analytics에서 제한 사항을 제거하여 Adobe Analytics의 범위를 확장합니다. 몇 가지 주목할 만한 개선 사항은 다음과 같습니다.

* **제한 없는 변수 및 이벤트**: eVar, 속성 및 이벤트에 대한 개념이 더 이상 없습니다. 데이터는 주로 차원과 지표에 중점을 둡니다. 데이터 세트의 고유한 차원과 지표 수는 제한이 없습니다.
* **무제한 고유 값**: Adobe Experience Platform은 고유한 제한 사항으로 제한되지 않습니다.
* **이전 데이터 변경**: Adobe Experience Platform을 사용하여 데이터를 제거하거나 수정할 수 있습니다.
* **크로스 보고서 세트 데이터**: 여러 데이터 세트의 기존 구현을 Platform에 결합할 수 있습니다.

Customer Journey Analytics의 초기 릴리스에는 Analysis Workspace에 포함된 많은 기능이 포함되어 있습니다. 전체 목록에 대해서는 [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)을 참조하십시오.

## 주요 사용 사례

Customer Journey Analytics을 통해 다음과 같은 작업을 수행할 수 있습니다.

* **여정 컨텍스트에서 고객 보기**: 여러 채널에 걸쳐 데이터를 순차적으로 보고 분석할 수 있습니다. 콜 센터, POS 시스템 및 온라인 속성의 데이터를 하나의 보고 보기에 결합할 수 있습니다.
* **모든 사람이 이용할 수 있는 인사이트 만들기**: 데이터 액세스 기능을 대중화하고 더 많은 사람들이 데이터를 기반으로 한 인사이트로 비즈니스 의사 결정을 내리도록 할 수 있습니다. 조직 내에서 고객 경험의 모든 측면에 대한 책임을 지는 사람은 보다 완전한 데이터를 기반으로 하여 보다 신속하게 실제 의사 결정을 내릴 수 있습니다.
* **분석가를 위한 데이터 과학의 강점 활용**: Customer Journey Analytics에서 일반 사용자는 데이터 과학을 사용하여 심도 있는 인사이트와 분석을 수행할 수 있습니다.
* **온디맨드 보고를 사용하여 데이터 세트 시각화 및 상호 작용**: Analysis Workspace에서 몇 가지 기본 규칙을 준수하는 Adobe Experience Platform의 모든 데이터 세트를 사용할 수 있습니다.
* **웹이 아닌 데이터 보기**: Analysis Workspace는 더 이상 &#39;히트&#39; 또는 &#39;이벤트&#39;에 대한 엄격한 정의로 제한되지 않습니다. 사용자 정의 스키마를 사용하여 데이터 및 정의를 완벽하게 제어할 수 있습니다.
* **데이터 조작을 통해 정확하게 제어**: 업로드한 데이터를 변경하고, 데이터 세트를 만들고, 이를 Analysis Workspace로 가져옵니다. Adobe Experience Platform은 Experience Cloud Query Service를 통해 쿼리, 추출, 변환 및 로드 도구를 제공합니다.

## 사전 요구 사항

Customer Journey Analytics 사용을 시작하려면 먼저 다음과 같은 사전 요구 사항을 충족해야 합니다.

* 조직은 Customer Journey Analytics 추가 기능이 포함된 Adobe Analytics for Select, Prime 또는 Ultimate와 계약을 맺고 있습니다. 어떤 유형의 계약을 맺고 있는지 모르거나 CJA 추가 기능이 있는지 확실하지 않은 경우 조직의 계정 관리자에게 문의하십시오.
* 조직에 Adobe Experience Platform이 프로비저닝되었습니다.

## 관리자 액세스 권한

연결 만들기, 데이터 세트 추가 등을 수행하려면 [Admin Console](https://adminconsole.adobe.com/enterprise/)에서 다음 권한이 필요합니다.

* Customer Journey Analytics에 액세스하거나 연결을 만들려면 [Admin Console](https://adminconsole.adobe.com/enterprise/)에서 **Customer Journey Analytics 제품**&#x200B;에 관리자로 추가되어 있어야 합니다. 제품 관리자에게는 다음 권한이 부여됩니다.
   * 연결 또는 데이터 보기 만들기/업데이트/삭제
   * 다른 사용자가 만든 프로젝트, 필터, 계산된 지표 또는 필터 업데이트/삭제
   * 모든 사용자에게 작업 영역 프로젝트 공유
* Customer Journey Analytics 내에서 제품 관리자가 되는 것만으로는 연결을 생성, 업데이트 또는 삭제할 수 없습니다. Experience Platform 데이터 세트에 대한 연결을 만들려면 Experience Platform 권한도 필요합니다. 특히 다음 권한을 부여하는 **Experience Platform 제품 프로필**&#x200B;의 일부여야 합니다.
   * 스키마 보기
   * 스키마 관리
   * ID 네임스페이스 보기
   * 데이터 세트 보기

Experience Platform 권한에 대한 자세한 내용은 [Adobe Experience Platform의 액세스 제어](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ko)를 참조하십시오.

>[!NOTE]
>
>Customer Journey Analytics에서는 기존의 Adobe Analytics에서와 같이 개별 지표 또는 차원을 거부하거나 허용할 수 없습니다. 지표와 차원은 [데이터 보기](/help/data-views/data-views.md)에서 변경할 수 있으므로 보고도 소급 변경하는 CJA의 변경으로부터 영향을 받습니다.

### 사용자 액세스

Customer Journey Analytics의 제품 관리자가 아닌 사용자(사용자)는 데이터 보기 또는 연결을 볼 수 없지만 필터, 프로젝트 및 계산된 지표를 만들 수 있습니다.

## 용어 업데이트

기존 Adobe Analytics과 비교하여 업계 표준에 맞게 CJA의 여러 기능이 이름이 변경되었습니다. 업데이트된 용어 중 일부는 다음과 같습니다.

* 이제 세그먼트를 &#39;필터&#39;라고 합니다.
* 이제 가상 보고서 세트를 &#39;데이터 보기&#39;라고 합니다
* 이제 분류를 &#39;조회 데이터 세트&#39;라고 합니다.
* 이제 고객 속성을 &#39;프로필 데이터 세트&#39;라고 합니다.
* 이제 히트 컨테이너를 &#39;이벤트&#39; 컨테이너라고 합니다.
* 이제 방문 컨테이너를 &#39;세션&#39; 컨테이너라고 합니다.
* 이제 방문자 컨테이너를 &#39;개인&#39; 컨테이너라고 합니다.

## Adobe Experience Platform에 구축된 기타 기능

Customer Journey Analytics는 Adobe Experience Platform을 사용하는 많은 기능 중 하나입니다. Experience Platform에 구축된 다양한 기능을 통해 데이터를 최대한 활용할 수 있습니다.

Adobe Experience Platform을 사용하면 모든 시스템의 고객 데이터와 콘텐츠를 중앙 집중화 및 표준화하고, 데이터 과학 및 시스템 학습을 적용하여 개인화된 경험의 디자인과 전달을 향상시킬 수 있습니다. 플랫폼의 고객 데이터는 스키마 및 데이터 배치로 구성된 데이터 세트로 저장됩니다. 플랫폼에 대한 자세한 내용은 [Adobe Experience Platform 아키텍처 개요](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html)를 참조하십시오.

데이터 수집에서 직접 SQL 액세스를 위해 Experience Platform의 여러 구성 요소는 Customer Journey Analytics에 중요하며, 이를 보완합니다.

* [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ko): 표준 SQL을 사용하여 Adobe 솔루션 데이터, 고객 자사 데이터 또는 기타 Platform 데이터와 같은 데이터를 Adobe Experience Platform에서 검색할 수 있습니다. 데이터 세트에 참여하고 쿼리 결과를 보고 또는 Data Science Workspace에 사용하거나 프로필 서비스에 수집하기 위한 새 데이터 세트로 캡처할 수 있는 서버를 사용하지 않는 도구입니다. Query Service를 사용하여 데이터 분석 에코시스템을 구축하고 다양한 상호 작용 채널에서 소비자의 그림을 그릴 수 있습니다. 이러한 채널에는 판매 지점 시스템, 웹, 모바일, CRM 시스템 등이 포함될 수 있습니다.
* [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko):
* [ID 서비스](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ko):
* 개발자 옵션의 [Data Science Workspace](https://experienceleague.adobe.com/docs/experience-platform/data-science-workspace/home.html): Adobe Experience Platform에 사전 설치된 AI(인공 지능) 및 시스템 학습 모델을 사용하여 고객 여정의 다양한 부분에 영향을 줄 수 있습니다. 숨겨진 인사이트를 도출하여 고객 여정 전반에서 더 나은 예측을 하고, 가장 권장되는 다음 단계를 제안하거나 번거로운 프로세스를 자동화할 수 있습니다.

## 비디오

* Customer Journey Analytics에서 데이터 작업:

   >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Customer Journey Analytics의 아키텍처 및 통합:

   >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

