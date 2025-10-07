---
title: Content Analytics 구성
description: Content Analytics를 구성하는 방법에 대한 개요
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: f149a2bd7f184f4e8f6e67979649e2d9f609d603
workflow-type: ht
source-wordcount: '599'
ht-degree: 100%

---

# Content Analytics 구성

이 문서에서는 Content Analytics 구성 방법에 대해 자세히 설명합니다.

Content Analytics를 구성하기 전에 [전제 조건](#prerequisites)이 충족되었는지, 필요한 [액세스 제어 권한](#access-control)을 갖고 있는지, [제한 사항](#limitations)을 알고 있는지 확인해야 합니다.


상위 수준 단계

![Content Analytics 구성](../assets/aca-configuration.svg){zoomable="yes"}

1. Content Analytics [가이드 구성](guided.md) 마법사를 사용하여 Content Analytics의 구성을 위한 필수 조건을 설정하는 데 필요한 모든 단계를 안내합니다. 언제든지 구성을 저장하고 나중에 다시 돌아올 수 있습니다.
1. 구성 값에 익숙해지면 구성을 구현할 수 있습니다. 이 구현은 마법사에서 구성한 내용을 기반으로 필요한 모든 아티팩트를 생성합니다.
1. 태그 속성을 [수동으로 게시](manual.md)할 때만 Content Analytics 구성이 효과적으로 배포되고 데이터 수집이 시작됩니다.

1. [가이드 구성](guided.md) 마법사를 사용하여 구현된 구성을 약간만 변경할 수도 있습니다. 예를 들어 [데이터 보기](/help/data-views/data-views.md)를 변경할 수 있습니다.
1. 연결된 태그 속성에서 [Adobe Content Analytics 확장 기능](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview)을 사용하여 구현된 구성에 기타 변경 사항을 적용할 수 있습니다.
1. 태그 속성을 [수동으로 다시 게시](manual.md)할 때만 구성 수정 사항이 효과적으로 배포되고 변경 사항에 따라 데이터 수집이 시작됩니다.


## 사전 요구 사항

Content Analytics를 구성하기 전에 다음 사전 요구 사항이 충족되었는지 확인하십시오.

* Content Analytics에서 사용되는 기능화 서비스에 대해 사용자 에이전트와 IP 주소를 허용 목록에 추가했습니다. 구성할 사용자 에이전트 문자열은 다음과 같습니다. <code>AdobeFeaturization/1.0</code>.
* 일반적 동작 데이터 수집에 대해 [JavaScript를 사용한 Web SDK](https://experienceleague.adobe.com/ko/docs/experience-platform/web-sdk/install/library){target="_blank"}를 구현한 경우, JavaScript 라이브러리에 기본 이름인 <code>alloy</code> 를 사용하고 있는지 확인했습니다.
* Customer Journey Analytics 제품 관리자 역할이 있으며, 연결과 데이터 보기를 관리할 수 있는 추가 권한이 있습니다.
* Content Analytics 경험을 수집하려는 경우, 웹 페이지의 변경 사항에 따라 [Content Analytics 버전 관리](manual.md#versioning)를 설정하고 업데이트했습니다.
* 다음 [데이터 수집 권한](https://experienceleague.adobe.com/ko/docs/experience-platform/collection/permissions){target="_blank"}을 보유하고 있습니다.
   * [Experience Platform 권한](https://experienceleague.adobe.com/ko/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Experience Platform 데이터 수집 권한](https://experienceleague.adobe.com/ko/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* 다음 중요한 구성 옵션을 신중하게 고려했습니다.

   * 사이트가 경험 보고에 적합합니다. 적절한 경험 보고는 다음 조건이 충족될 때에만 가능합니다.
      * 사이트의 페이지는 페이지 URL을 사용하여 재현될 수 있어야 합니다.
      * 특정 사용자가 보는 텍스트 콘텐츠는 페이지 URL을 사용하여 재생산될 수 있으며, 쿠키나 기타 개인화 메커니즘에 의존하지 않아야 합니다.
   * 어떤 페이지에서 콘텐츠 참여 분석과 인사이트를 확보하고 싶은지 명확하게 이해하고 있어야 합니다.
   * 어떤 유형의 자산에서 콘텐츠 참여 분석과 인사이트를 확보하고 싶은지 명확하게 이해하고 있어야 합니다.


## 액세스 제어

>[!IMPORTANT]
>
>개별 사용자 또는 사용자 그룹에 대해 Content Analytics 액세스를 활성화하거나 비활성화하기 위해 구성할 수 있는 Content Analytics 권한은 제공되지 않습니다.
>

사용자 또는 사용자 그룹에 Content Analytics에 대한 액세스 권한을 제공하려면 사용자 또는 사용자 그룹에 하나 이상의 [Content Analytics에 대해 구성된 데이터 보기](guided.md#data-view)에 대한 액세스 권한을 제공해야 합니다.

이 액세스 권한은 다음을 의미합니다.

1. Content Analytics가 활성화된 데이터 보기는 특정 Customer Journey Analytics 제품 프로필에 대한 데이터 보기 권한의 일부로 포함됩니다.
1. 해당 Customer Journey Analytics 제품 프로필은 사용자 또는 사용자 그룹에 할당된 제품 프로필 중 하나입니다.

## 제한 사항

Content Analytics 이벤트 데이터에 사용되는 스키마는 시스템 소유입니다. 시스템 소유 스키마는 수정할 수 없습니다. 이는 다음을 의미합니다.

* 지리적 위치, 봇 감지 또는 디바이스 조회와 같은 기능 지원을 위한 필드 그룹을 포함할 수 없습니다.
* [필드 기반 결합](/help/stitching/fbs.md)을 지원하도록 특정 식별자를 추가할 수 없습니다.

>[!MORELIKETHIS]
>
>* [가이드 구성](guided.md)
>* [수동 구성](manual.md)
>* [액세스 제어](/help/technotes/access-control.md)
>
