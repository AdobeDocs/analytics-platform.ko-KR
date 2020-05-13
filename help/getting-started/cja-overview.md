---
title: Customer Journey Analytics 개요
description: 고객 경로 분석 소개
translation-type: tm+mt
source-git-commit: 6f5c3c073069ca7f428d971515342c1a636795e3
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 2%

---


# Customer Journey Analytics 개요

고객 경로 분석은 분석 작업 공간의 강력한 기능을 Adobe Experience Platform의 데이터와 함께 사용할 수 있는 분석 기능입니다. 데이터 분류, 필터링, 쿼리 및 시각화 작업을 할 수 있으며 모든 종류의 데이터 스키마와 유형을 보유할 수 있는 플랫폼의 기능과 결합됩니다. XDM( **Experience Data Model)을 사용하여**&#x200B;데이터를 조합과 탐색을 위해 필요에 맞게 일관되게 표시하고 구성할 수 있습니다. **Experience Query Services** 를 사용하면 SQL 호환 도구와 프레임워크를 사용하여 모든 데이터를 쿼리하고 조작할 수 있습니다.

## CJA와 기존 Adobe Analytics 비교

고객 경로 분석은 사용하기 쉬운 크로스 채널 기능을 제공하고 이전 버전의 Adobe Analytics에서 제한 사항을 제거함으로써 Analytics의 범위를 확장합니다. 몇 가지 주목할 만한 개선 사항은 다음과 같습니다.

* **제한 없는 변수 및 이벤트**: eVar, prop 및 이벤트의 개념이 더 이상 존재하지 않습니다. 데이터는 주로 차원과 지표에 중점을 둡니다. 데이터 세트는 고유한 차원과 지표를 무제한으로 가질 수 있습니다.
* **무제한 고유 값**: Adobe Experience Platform은 기존 보고서 세트의 500k 고유 값과 같은 고유한 제한 사항으로 제한되지 않습니다.
* **내역 데이터**&#x200B;변경: Adobe Experience Platform을 사용하면 데이터를 제거하거나 수정할 수 있습니다.
* **보고서 세트 간 데이터**: 여러 데이터 세트의 기존 구현은 플랫폼에서 결합할 수 있습니다.

고객 경로 분석의 초기 릴리스에는 분석 작업 공간에 포함된 많은 기능이 포함되어 있습니다. 전체 목록은 [고객 경로 분석 기능 지원을 참조하십시오](cja-aa.md).

## CJA와 크로스 디바이스 분석 비교

[크로스 디바이스 분석](https://docs.adobe.com/content/help/ko-KR/analytics/components/cda/cda-home.html) (Cross-Device Analytics)은 Co-op Graph 또는 Private Graph를 활용하여 디지털 디바이스가 어떻게 사람들에게 매핑되는지 확인하는 Adobe Experience Platform Identity Service와 통합됩니다. Adobe Analytics Ultimate 고객이 사용할 수 있습니다.

CJA는 Adobe Experience Platform 데이터 세트와 통합되어 분석 작업 공간에서 크로스 채널 분석을 지원합니다. CJA는 Co-op 또는 Private ID 그래프와 아직 통합되지 않았지만 &quot;고유한 ID를 가져올 수 있습니다&quot;로 데이터 세트를 함께 결합할 수 있으며 이러한 데이터 세트는 디지털 데이터를 넘어 온라인 및 오프라인 접점을 모두 포함할 수 있습니다. CJA 사전 요구 사항은 아래에 자세히 설명되어 있습니다.

## 주요 활용 사례

고객 여정 분석을 통해 다음과 같은 이점을 얻을 수 있습니다.

* **고객 여정 상황**&#x200B;파악: 여러 채널에 걸쳐 데이터를 순차적으로 보고 분석할 수 있습니다. 콜 센터, POS 시스템 및 온라인 속성의 데이터를 하나의 보고 보기로 결합할 수 있습니다.
* **모든 사람이 이용할 수 있는 통찰력**: 데이터 액세스 기능을 간소화하고 더 많은 사람들이 데이터를 기반으로 한 통찰력으로 비즈니스 의사 결정을 내릴 수 있도록 합니다. 조직 내에서 고객 경험의 모든 측면에 대한 책임을 지는 사람은 보다 완벽한 데이터를 기반으로 보다 신속하게 실제 의사 결정을 내릴 수 있습니다.
* **분석가를 위한 데이터 과학의 강점**: 고객 여정 분석을 통해 일반 사용자는 데이터 과학을 사용하여 심도 있는 인사이트와 분석을 수행할 수 있습니다.
* **애드혹 보고를 사용하여 데이터 세트를 시각화하고 인터랙션할 수 있습니다**. 작업 공간은 일부 기본 규칙을 준수하는 Adobe Experience Platform의 모든 데이터 세트를 사용할 수 있습니다.
* **비웹 데이터**&#x200B;보기: 작업 영역은 더 이상 &#39;히트&#39; 또는 &#39;이벤트&#39;의 엄격한 정의로 제한되지 않습니다. 사용자 정의 스키마를 사용하여 데이터 및 정의를 완벽하게 제어할 수 있습니다.
* **데이터 조작을 보다 정확하게 제어할 수 있습니다**. 업로드한 데이터를 변경하고, 새 데이터 세트를 만들고, 이를 작업 공간으로 가져옵니다. Adobe Experience Platform은 Experience Cloud 쿼리 서비스를 통해 쿼리, 추출, 변환 및 로드 도구를 제공합니다.

## 전제 조건

고객 경로 분석 사용을 시작하려면 먼저 다음 전제 조건을 충족해야 합니다.

* 조직은 고객 경로 분석 추가 기능과 Select, Prime 또는 Ultimate를 위한 Adobe Analytics와 계약을 맺고 있습니다. 어떤 유형의 계약서를 보유하고 있는지 모르거나 CJA Add-On이 있는지 확실하지 않은 경우 조직의 계정 관리자에게 문의하십시오.
* 조직이 Adobe Experience Platform을 사용하도록 프로비저닝되었습니다.

## 사용자 액세스 권한

연결을 만들고 데이터 세트를 추가하려면 관리 콘솔에서 다음 권한이 [필요합니다](https://adminconsole.adobe.com/enterprise/).

* 경험 플랫폼에서 데이터 세트를 관리하려면 &quot;데이터 집합 관리&quot; 권한을 제공하는 플랫폼 제품 프로필의 일부여야 합니다. 자세한 내용은 Adobe Experience [Platform의 액세스 제어를 참조하십시오](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* 플랫폼 데이터 세트에 대한 연결을 만들려면 다음 권한을 제공하는 플랫폼 제품 프로필의 일부여야 합니다.
   * 스키마 보기
   * 데이터 집합 보기
   * ID 네임스페이스 관리
   * 샌드박스 보기
* 고객 여정 분석에 액세스하거나 연결을 하려면 [관리 콘솔에서 고객 여정 분석 제품 프로필에 추가해야 합니다](https://adminconsole.adobe.com/enterprise/).

### 용어 업데이트

업계 표준에 맞게 CJA의 여러 기능이 이름이 변경되었습니다. 업데이트된 일부 이름은 다음과 같습니다.

* 세그먼트는 이제 &#39;필터&#39;라고 합니다.
* 가상 보고서 세트를 이제 &#39;보기&#39;라고 합니다.
* 이제 분류는 &#39;데이터 집합 조회&#39;라고 합니다.
* 이제 고객 속성을 &#39;프로필 데이터 집합&#39;이라고 합니다.
* 이제 히트 컨테이너를 &#39;이벤트&#39; 컨테이너라고 합니다.
* 이제 방문 컨테이너를 &#39;세션&#39; 컨테이너라고 합니다.
* 이제 방문자 컨테이너를 &#39;사람&#39; 컨테이너라고 합니다.

## Adobe Experience Platform 기반의 기타 기능

고객 여정 분석은 Adobe Experience Platform을 사용하는 많은 기능 중 하나입니다. Platform(플랫폼)을 기반으로 구축된 다양한 기능을 통해 데이터를 최대한 활용할 수 있습니다.

Adobe Experience Platform을 사용하면 모든 시스템의 고객 데이터와 콘텐츠를 통합 관리하고 표준화할 수 있으며 데이터 과학 및 머신 러닝을 적용하여 개인화된 경험의 디자인과 전달을 향상시킬 수 있습니다. 플랫폼의 고객 데이터는 스키마 및 데이터 배치로 구성된 데이터 세트로 저장됩니다. 플랫폼에 대한 자세한 내용은 [Adobe Experience Platform 아키텍처 개요를 참조하십시오](https://www.adobe.io/apis/experienceplatform/home/overview.html).

데이터 통합에서 SQL 액세스를 위한 데이터 통합, 경험 플랫폼의 몇 가지 구성 요소는 고객 여정 분석의 핵심이며, 이와 함께 작동합니다.

* [쿼리 서비스](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html): 표준 SQL을 사용하여 Adobe 솔루션 데이터, 고객 자사 데이터 또는 기타 플랫폼 데이터와 같은 Adobe Experience Platform에서 데이터를 검색할 수 있습니다. 데이터 집합에 참여하고 쿼리 결과를 보고, 데이터 과학 작업 공간 또는 프로필 서비스에 수집하기 위한 새로운 데이터 세트로 캡처할 수 있는 서버를 사용하지 않는 도구입니다. Query Service를 사용하여 데이터 분석 환경을 구축하고 다양한 상호 작용 채널에서 소비자의 그림을 그릴 수 있습니다. 이러한 채널에는 판매 시점(POS) 시스템, 웹, 모바일, CRM 시스템 등이 포함될 수 있습니다.
* [실시간 고객 프로필](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [ID 서비스](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [&quot;개발자&quot; 옵션의](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) 데이터 과학 작업 공간: Adobe Experience Platform에서 미리 만들어진 인공 지능(AI) 및 머신 러닝 모델을 사용하여 고객 여정의 다양한 부분에 영향을 줄 수 있습니다. 숨겨진 통찰력을 도출하여 고객 여정 전반에서 보다 나은 예측을 도출하고, 다음 단계에 가장 권장되는 단계를 제안하거나, 번거로운 프로세스를 자동화할 수 있습니다.
