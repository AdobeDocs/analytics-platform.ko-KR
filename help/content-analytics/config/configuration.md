---
title: 콘텐츠 분석 구성
description: 콘텐츠 분석 구성 방법에 대한 개요
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: d4803af9b71ec245f6c4b20e92a4a4c99f235f00
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 0%

---

# 콘텐츠 분석 구성

{{release-limited-testing}}


Content Analytics의 구성은 다음 단계로 구성됩니다.

![콘텐츠 분석 구성](../assets/aca-configuration.svg){zoomable="yes"}

1. Content Analytics [구성 가이드](guided.md) 마법사를 사용하여 Content Analytics 구성에 대한 필수 구성 요소를 설정하는 데 필요한 모든 단계를 안내합니다. 언제든지 구성을 저장하고 나중에 돌아갈 수 있습니다.
1. 구성 값에 익숙해지면 구성을 구현할 수 있습니다. 이 구현은 마법사에서 구성한 내용을 기반으로 필요한 모든 아티팩트를 만듭니다.
1. Tags 속성을 [수동으로 게시](manual.md)하는 경우에만 Content Analytics 구성이 효과적으로 배포되고 데이터 수집이 시작됩니다.

1. [안내가 있는 구성](guided.md) 마법사를 사용하여 구현된 구성에 일부 부분만 변경할 수 있습니다. 예를들어 [데이터 보기](/help/data-views/data-views.md)를 변경합니다.
1. 연결된 Tags 속성에서 [Adobe Content Analytics 확장](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)을 사용하여 구현된 구성에 다른 변경 작업을 수행할 수 있습니다.
1. Tags 속성을 [수동으로 다시 게시](manual.md)하는 경우에만 구성 수정 사항이 효과적으로 배포되고 변경 사항에 따른 데이터 수집이 시작됩니다.


## 사전 요구 사항

Content Analytics을 구성하기 전에 다음 전제 조건이 충족되는지 확인하십시오.

* 콘텐츠 분석에 사용되는 기능 서비스에 대한 사용자 에이전트 및 IP 주소를 허용 목록에 추가했습니다. 구성할 사용자 에이전트 문자열: <code>AdobeFeatuization/1.0</code>.
* 일반 동작 데이터 수집을 위해 [Javascript를 사용하여 웹 SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library){target="_blank"}을(를) 구현한 경우 기본 이름 <code>alloy를 사용하고 있는지 확인하십시오</code> Javascript 라이브러리용.
* 연결을 관리하고 데이터 보기를 관리할 수 있는 추가 권한이 있는 Customer Journey Analytics 제품 관리자 역할이 있습니다.
* 데이터 수집에 대한 [권한](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions){target="_blank"}이 있어야 합니다. 이러한 권한은 다음으로 구성됩니다.
   * [Experience Platform 권한](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Experience Platform 데이터 수집 권한](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank" }
* 다음과 같은 중요한 구성 옵션을 신중하게 고려했습니다.

   * 사이트가 경험 보고에 적합합니다. 적절한 경험 보고는 다음 조건이 충족될 때만 가능합니다.
      * 사이트의 페이지는 페이지 URL을 사용하여 재현할 수 있어야 합니다.
      * 지정된 사용자가 보는 텍스트 콘텐츠는 페이지 URL을 사용하여 재현할 수 있으며 쿠키 또는 기타 개인화 메커니즘에 따라 달라지지 않습니다.
   * 컨텐츠 참여 분석 및 통찰력을 캡처할 페이지를 명확하게 이해하고 있습니다.
   * 컨텐츠 참여 분석 및 통찰력을 캡처할 (유형) 에셋을 명확히 이해하고 있습니다.


## 액세스 제어

>[!IMPORTANT]
>
>개별 사용자 또는 사용자 그룹에 대해 Content Analytics 액세스를 활성화하거나 비활성화하도록 구성할 수 있는 Content Analytics 권한은 없습니다.
>

사용자 또는 사용자 그룹에 Content Analytics에 대한 액세스 권한을 제공하려면 Content Analytics에 대해 구성된 하나 이상의 [데이터 보기에 대한 액세스 권한을 사용자 또는 사용자 그룹에 제공해야 합니다](guided.md#data-view).

이 액세스는 다음을 의미합니다.

1. Content Analytics 활성화 데이터 보기는 특정 Customer Journey Analytics 제품 프로필에 대한 데이터 보기 권한의 일부로 포함됩니다.
1. 해당 특정 Customer Journey Analytics 제품 프로필은 사용자 또는 사용자 그룹에 할당된 제품 프로필 중 하나입니다.

>[!MORELIKETHIS]
>
>* [구성 가이드](guided.md)
>* [수동 구성](manual.md)
>* [액세스 제어](/help/technotes/access-control.md)
>
