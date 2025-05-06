---
title: Customer Journey Analytics의 대상자 게시 개요에 대해 자세히 알아보기
description: Customer Journey Analytics의 대상자 게시 개념에 대해 알아보기
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 9393be88ab7320adb5bd046701667f638673af5e
workflow-type: ht
source-wordcount: '404'
ht-degree: 100%

---

# 대상자 게시 개요

이제 고객 타기팅 및 맞춤화를 위해 Customer Journey Analytics에서 발견된 대상자를 Adobe Experience Platform의 [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)을 만들어 게시할 수 있습니다.

대상자 게시는 Customer Journey Analytics 내에서 발견된 인사이트를 활성화하고 조치를 취하는 명확한 방법을 제공합니다. 이러한 조치에는 다음이 포함될 수 있습니다.

* Adobe Journey Optimizer에서 대상자를 여정에 활용
* Experience Platform 대상을 통해 서드파티에 대상자 내보내기
* Customer Journey Analytics의 이벤트 기반 데이터에서 파생된 유용한 속성으로 실시간 고객 프로필 강화
* 대상자를 게시한 후 대기 시간을 최소화하면서 이 모든 작업을 수행할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)
* 일회성 대상자 또는 반복 대상자 게시.

Customer Journey Analytics에서 만드는 대상자는 프로필을 위해 활성화된 데이터 세트를 기반으로 할 필요가 없습니다. 프로필에 대한 관련 데이터 세트와 스키마를 활성화하지 않고도 내역 데이터를 Experience Platform으로 가져올 수 있습니다. 그런 다음 이러한 데이터 세트를 사용하여 Customer Journey Analytics에서 관련 대상자를 발견하고 활성화를 위해 이러한 대상자를 Experience Platform의 실시간 고객 프로필에 게시합니다.

## 주요 용어

**대상자**: 네임스페이스 및 해당 네임스페이스와 관련된 특정 ID가 모두 있는 ID 집합 또는 목록입니다. 대상자는 Adobe Experience Platform 및 상위 애플리케이션(예: Customer Journey Analytics)에서 이동할 수 있습니다. 대상자에는 혼합 네임스페이스가 포함될 수 있습니다.

**세그먼트**: 일정 기간 동안 데이터의 집합을 평가할 때 데이터 하위 집합을 생성하는 규칙 집합입니다. 세그먼트는 다른 지원 서비스와 결합할 때 대상자를 만드는 과정에서 사용할 수 있습니다. 세그먼트는 Customer Journey Analytics에서 정의되고 유지 관리됩니다.

## 권한

* 관리자는 Adobe Admin Console에서 **[!UICONTROL 대상자 게시]** 권한이 자동으로 부여됩니다.

* 관리자와 제품 프로필 관리자는 개별 사용자에게 **[!UICONTROL 대상자 생성]** 및 **[!UICONTROL 대상자 보기]** 권한을 부여할 수 있습니다. 자세한 내용은 [사용자 수준 액세스 제어](/help/technotes/access-control.md#user-level-access)를 참조하십시오.

* 관리자는 또한 Adobe Experience Platform에서 **[!UICONTROL 프로필 관리]** 권한이 필요합니다.

## 데이터 거버넌스 및 동의

Customer Journey Analytics에서 대상자를 게시하면 해당 대상자에서 사용되는 필드에 연결된 데이터 거버넌스 레이블 및 정책이 기록됩니다. Adobe Experience 앱에서 대상자가 활성화되면 해당 대상자에 대해 연결된 모든 데이터 거버넌스 레이블 및 정책을 사용할 수 있으며 적절한 시행이 적용될 수 있습니다. [동의에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html#consent-policy).

## 다음 단계

* [대상자 생성 및 게시](/help/components/audiences/publish.md)
* [대상자 관리](/help/components/audiences/manage.md)
