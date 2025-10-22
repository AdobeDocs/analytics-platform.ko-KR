---
title: Adobe Analytics에서 Customer Journey Analytics로 업그레이드
description: Adobe Analytics에서 Customer Journey Analytics로 업그레이드할 때 권장되는 단계 자세히 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 7c0342a68f75774fd7b29979d3ce610f22d047ae
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 8%

---

# Customer Journey Analytics으로 업그레이드할 조직 준비

[Adobe Analytics에서 Customer Journey Analytics으로 업그레이드](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)에 설명된 대로 성공적인 업그레이드의 일부는 특정 운영 고려 사항에 초점을 맞추어 조직을 준비하는 것입니다. 조직을 준비하려면 다음 작업을 수행하는 것이 좋습니다.

* 주요 이해 관계자로부터 구매 및 정렬 받기

* 목표 정의 및 문서화

* 현실적이고 사려 깊은 타임라인 설정

* 기여자에 대한 명확한 책임 정의

## 이해 당사자 구매 및 정렬

조직의 주요 관련자와 의사 결정권자는 Customer Journey Analytics으로의 업그레이드에 동의해야 합니다.

다음 섹션에서는 관련자 정렬을 얻을 수 있는 방법에 대해 설명합니다.

### 가치에 초점

Customer Journey Analytics이 조직에 제공하는 가치와 이를 통해 비즈니스 목표 달성을 가속화하는 방법에 대해 중점적으로 살펴보십시오.

다음 표에는 강조할 몇 가지 주요 기능이 나와 있습니다.

| 기능 | 이점 | 예 |
|---------|----------|---------|
| **[모든 종류의 데이터를 위한 숙박](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/home)** | Customer Journey Analytics에는 모든 종류의 데이터 스키마와 유형을 보유할 수 있는 Experience Platform의 기능이 결합되어 있습니다. | 소매 조직은 다음 종류의 데이터를 단일 보기에 통합하여 전체 고객 여정에 대한 가시성을 제공할 수 있습니다. <ul><li>웹 클릭스트림 트랜잭션</li><li>모바일 앱 트랜잭션</li><li>매장 내 거래</li><li>CRM 및 충성도 데이터</li></ul> |
| **[크로스 채널 분석](/help/use-cases/cross-channel/cross-channel.md)** | 다양한 웹, 모바일 및 오프라인 속성에서 데이터를 통합하여 다양한 채널에서 고객 행동에 대한 통합된 단일 보기를 활성화합니다. | 여러 채널에서 데이터를 수집하는 소매 조직은 다음과 같은 종류의 분석을 수행할 수 있습니다.<p>쇼핑객이 유료 검색 광고를 클릭하고 온라인에서 청바지를 탐색한 후 푸시 알림을 받은 다음 이틀 후 매장에서 구매합니다. 이러한 통합된 관점을 통해 정확한 크로스 채널 속성을 구현하여 디지털 접점이 매장 내 판매에 어떻게 기여하는지 보여 줍니다. 또한 맞춤형 오퍼를 통해 &quot;온라인에서 검색하고 스토어에서 구매한&quot; 고객을 타겟팅하는 것과 같이 보다 정밀한 세그먼테이션을 지원합니다. 또한 하나의 대시보드에서 명확하고 모든 채널 매출 보고를 제공하여 단편화되고 고립된 인사이트를 고객 행동에 대한 전체적인 이해로 바꿉니다. |
| **[보고서 처리 시간](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | 기본 데이터 수집 방법을 변경할 필요 없이 소급 설정을 적용하고 여러 버전의 변수 지속성을 생성합니다. | Customer Journey Analytics을 사용하면 데이터를 다시 가져오거나 처리하지 않고도 신속하게 지표, 차원 및 속성 모델을 만들고 조정할 수 있으므로 소매 조직은 엔지니어링에게 데이터 세트를 다시 빌드하도록 요청할 필요 없이 최근 소셜 캠페인이 온라인 및 매장 내 판매 모두에 어떤 영향을 미쳤는지 확인할 수 있습니다. 속성 모델을 마지막 터치에서 첫 번째 터치 또는 사용자 지정 규칙 기반 속성으로 즉시 변경할 수 있습니다. |
| **[Content Analytics](/help/content-analytics/content-analytics.md)** | 콘텐츠가 비즈니스가 정의한 주요 성능 지표에 미치는 영향을 마케터가 이해할 수 있도록 도와줍니다. Content Analytics는 동작 데이터 외에 콘텐츠가 어떻게 소비되는지, 콘텐츠가 어떤 영향을 미치는지에 대한 데이터를 수집합니다. | 소매 조직은 웹, 앱, 이메일 및 매장 내 데이터를 통합하여 만든 각 디지털 콘텐츠가 고객 여정 및 전환에 어떻게 기여하는지 정확하게 파악할 수 있습니다. <p>소매 조직은 인기 있는 소셜 미디어 플랫폼에 있는 &quot;여름 데님 스타일 가이드&quot;가 충성도 회원들 간의 높은 참여를 유도하며, 이러한 회원들이 일주일 이내에 매장에서 데님을 구매할 가능성이 40% 더 높다는 것을 확인할 수 있었다.</p> |

### 경영 스폰서 지정

조직 내에서 경영 스폰서를 찾아 지정합니다. 이 경영진 스폰서는 Customer Journey Analytics이 비즈니스 목표 달성을 가속화하는 방법을 이해해야 합니다.

경영진 스폰서는 다음과 같이 매우 중요합니다.

* 조직 내 Customer Journey Analytics 챔피언

* 장애물 제거

* 리소스 승인

### 조직 전체의 주요 리더로부터 지원을 받을 수 있습니다.

경영진 스폰서의 도움을 받아 조직 전체의 다른 주요 리더로부터 지원을 확보하십시오. 조직의 다음 영역 리더가 Customer Journey Analytics의 이점을 이해하고 성공적인 구현에 기여할 의지가 있는 것이 중요합니다.

* Analytics

* 마케팅

* IT

* 법률 및 규정 준수

* 개별 사업 단위

## 업그레이드 및 커뮤니케이션 계획 개발

### 업그레이드 계획을 수립하여 이해 당사자에게 배포합니다.

업그레이드 계획에는 다음 정보가 포함될 수 있습니다.

* 업그레이드가 발생하는 이유에 대한 명확한 설명. 예를 들어, 사용자와 조직 또는 비즈니스 전체에 대한 이점을 설명합니다. 이점에 대한 자세한 내용은 [값에 집중](#focus-on-value)을 참조하십시오.

* 업그레이드가 시작될 예정이고 주요 이정표의 개요와 업그레이드가 완료될 것으로 예상되는 시기 등의 일반적인 타임라인.

* 사용자가 Customer Journey Analytics 사용 방법을 배우기 위한 공식 교육을 받을 수 있는 시기를 나타냅니다. 자세한 내용은 [조직 전체에서 최종 사용자 교육](#train-end-users-throughout-your-organization)을 참조하세요.

* 업그레이드를 주도하고 있는 사용자와 사용자가 질문을 할 수 있는 방법 또는 시기에 대한 정보입니다.

### 커뮤니케이션 계획 만들기

통신 계획에는 다음 고려 사항이 포함될 수 있습니다.

* 커뮤니케이션이 관련자 및 사용자에게 전송되는 시기에 대한 정의된 케이던스

* 보낼 정보 유형의 개요

* 커뮤니케이션을 전송할 사용자에 대한 플랜

* 관련자와 사용자가 질문을 하거나 피드백을 제공할 수 있도록 피드백 루프 정의

## Adobe Analytics 구현 평가 및 감사

다음 주요 영역을 중심으로 Adobe Analytics 구현에 대한 철저한 평가 및 감사를 수행합니다.

* 현재 사용자

* 사용자 액세스

* 프로젝트

* 비즈니스 프로세스

* 사용자 지정 구성 요소

이 정보를 수집하는 데 도움이 되는 다음 리소스를 참조하십시오.

* [Analytics 인벤토리](https://experienceleague.adobe.com/ko/docs/analytics/admin/admin-tools/analytics-inventory)

  조직 내의 프로젝트, 세그먼트, 계산된 지표, 보고서 세트 및 사용자 수에 대한 정보를 제공합니다.

* [Adobe Analytics에서 Customer Journey Analytics으로 구성 요소 및 프로젝트 마이그레이션 준비](https://experienceleague.adobe.com/ko/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  구성 요소, 프로젝트 및 사용자 마이그레이션을 준비하는 방법에 대한 정보를 제공합니다.

## 챔피언 및 얼리어답터 식별

조직 전체에서 챔피언을 식별합니다. 이러한 챔피언은 다음과 같아야 합니다.

* Adobe Analytics 고급 사용자

* Customer Journey Analytics에서 빠르게 능숙해질 수 있음

* Customer Journey Analytics이 보다 광범위하게 출시됨에 따라 다른 사용자에게 도움과 코치가 될 수 있습니다

## 조직 전체의 최종 사용자 교육

* 데이터 모델, 보고 패러다임 및 Customer Journey Analytics 내의 새로운 기능의 차이점에 중점을 둔 실습 교육을 제공합니다.

* 라이브 세션(워크숍 또는 운영 시간)과 온디맨드 리소스(비디오 튜토리얼, 동적 wiki 페이지 및 내부 문서)를 모두 제공합니다.

* Experience League의 관련 교육, 튜토리얼 및 설명서를 사용자에게 안내합니다.

  시작하는 데 도움이 되는 리소스는 다음과 같습니다.

   * [Customer Journey Analytics 자습서](https://experienceleague.adobe.com/ko/docs/customer-journey-analytics-learn/tutorials/overview)

   * [Customer Journey Analytics란?](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Customer Journey Analytics 소개](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)

## 권장되는 업그레이드 단계 수행

업그레이드 프로세스를 시작할 준비가 되면 Customer Journey Analytics 업그레이드 가이드의 [권장 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 동적으로 생성된 업그레이드 단계를 따릅니다. Customer Journey Analytics에서 안내서에 액세스하려면 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics로 업그레이드]**&#x200B;를 선택하십시오. 화면에 표시되는 안내를 따르십시오.

