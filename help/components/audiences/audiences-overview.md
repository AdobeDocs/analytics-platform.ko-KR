---
title: Customer Journey Analytics 대상 게시 개요
description: Customer Journey Analytics의 대상자 게시 개념에 대해 알아보기
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
source-git-commit: 3a3122934e0fb3d89ac94cc8be8799d43dd1c987
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 54%

---

# Customer Journey Analytics 대상 게시 개요

이제 Customer Journey Analytics에서 검색된 대상자를 만들어 게시할 수 있습니다. [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) 고객 타겟팅 및 개인화를 위한 Adobe Experience Platform에서.

대상자 게시는 Customer Journey Analytics 내에서 발견된 통찰력을 활성화하고 조치를 취하는 명확한 방법을 제공합니다. 이러한 조치에는 다음이 포함될 수 있습니다.

* Adobe Journey Optimizer에서 대상자를 여정에 활용
* Experience Platform 대상을 통해 서드파티에 대상자 내보내기
* Customer Journey Analytics의 이벤트 기반 데이터에서 파생된 유용한 속성으로 실시간 고객 프로필 강화
* 대상자를 게시한 후 대기 시간을 최소화하면서 이 모든 작업을 수행할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=en#latency)
* 일회성 대상자 또는 반복 대상자 게시.

프로필에서 만드는 대상은 Customer Journey Analytics에 대해 활성화된 데이터 세트를 기반으로 할 필요가 없습니다. 프로필에 연결된 데이터 세트 및 스키마를 활성화하지 않고 내역 데이터를 Experience Platform으로 수집할 수 있습니다. 그런 다음 이러한 데이터 세트를 사용하여 Customer Journey Analytics에서 관련 대상을 검색하고 활성화 목적을 위해 Experience Platform에서 실시간 고객 프로필에 게시할 수 있습니다.

## 주요 용어

**대상자**: 네임스페이스 및 해당 네임스페이스와 관련된 특정 ID가 모두 있는 ID 집합 또는 목록입니다. 대상은 Adobe Experience Platform 및 상위 애플리케이션(예: Customer Journey Analytics)에서 이동할 수 있습니다. 대상자에는 혼합 네임스페이스가 포함될 수 있습니다.

**필터**: 일정 기간 동안 데이터의 집합을 평가할 때 데이터 하위 집합을 생성하는 규칙 집합입니다. 필터는 다른 지원 서비스와 결합할 때 대상자를 만드는 과정에서 사용할 수 있습니다. 필터는 Customer Journey Analytics에서 정의되고 유지됩니다.

**필터** 및 **세그먼트**: Customer Journey Analytics은 &quot;세그먼트&quot; 개념을 사용하지 않고 대신 &quot;필터&quot;를 사용합니다. 둘 다 유사한 논리를 포함할 수 있는 규칙 세트이지만 서로 다른 출력을 생성합니다. 필터는 분석 목적으로 데이터 세트의 범위를 좁히는 데 사용됩니다. 세그먼트는 활성화에 사용할 수 있는 ID 목록을 생성하는 데 사용됩니다. 세그먼트는 실시간 고객 프로필에 대상자를 생성하지만 필터(단독으로)는 생성하지 않습니다. Customer Journey Analytics 대상 게시는 Customer Journey Analytics 필터를 사용하여 실시간 고객 프로필에서 사용할 수 있는 대상을 만드는 프로세스입니다.

## 권한

* 관리자는 Adobe Admin Console에서 **[!UICONTROL 대상자 게시]** 권한이 자동으로 부여됩니다.

* 관리자는 개인 사용자에게 이 권한을 부여할 수 있습니다.

* 관리자는 또한 Adobe Experience Platform에서 **[!UICONTROL 프로필 관리]** 권한이 필요합니다.

## 데이터 거버넌스 및 동의

Customer Journey Analytics에서 대상자를 게시하면 대상자에서 사용되는 필드에 연결된 데이터 거버넌스 레이블 및 정책이 기록됩니다.  Adobe Experience 앱에서 대상자가 활성화되면 해당 대상자에 대해 연결된 모든 데이터 거버넌스 레이블 및 정책을 사용할 수 있으며 적절한 시행이 적용될 수 있습니다. [동의에 대해 자세히 알아보기](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=ko-KR#consent-policy).

## 다음 단계

* [대상자 생성 및 게시](/help/components/audiences/publish.md)
* [대상자 관리](/help/components/audiences/manage.md)
