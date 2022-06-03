---
title: CJA 대상 게시 개요
description: Customer Journey Analytics의 대상 게시 개념에 대해 알아봅니다
source-git-commit: 9d19e1ea55a6c2de701d38cb417d6d39e753c640
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 3%

---


# CJA Audience 게시 개요

>[!NOTE]
>
>이 기능은 현재 [제한된 테스트](/help/release-notes/releases.md).

이제 Customer Journey Analytics(CJA)에서 검색된 대상을 [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=kr) Adobe Experience Platform에서 고객 타깃팅 및 개인화를 확인하십시오. 실시간 고객 프로필을 사용하면 온라인, 오프라인, CRM 및 타사 등 여러 채널의 데이터를 결합하여 각 개별 고객을 전체적으로 볼 수 있습니다. 프로필 을 사용하면 고객 데이터를 모든 고객 상호 작용을 실행 가능하고 타임스탬프가 지정된 계정을 제공하는 통합 보기에 통합할 수 있습니다.

게시 대상을 사용하면 CJA 내에서 제공되는 인사이트에 대해 조치를 취할 수 있습니다. 이러한 작업에는 다음이 포함될 수 있습니다.

* 이 대상자에게 이메일을 보내는 중입니다.
* 이 대상에게 푸시 메시지 보내기.
* Adobe Journey Optimizer에서 여정에 대상 사용.
* Experience Platform 대상을 통해 타사에 대상 내보내기.

## 주요 용어

**Audience**: 네임스페이스와 해당 네임스페이스와 관련된 특정 ID가 모두 있는 ID 집합 또는 목록입니다. 대상은 Adobe Experience Platform에서 전송하고 맨 위에 있는 애플리케이션(예: CJA)입니다. 대상에는 혼합 네임스페이스가 포함될 수 있습니다.

**필터**: 일정 기간 동안의 데이터 집합 위에서 평가될 때 데이터 하위 집합을 생성하는 규칙 집합입니다. 필터를 사용하면 다른 지원 서비스와 결합할 때 대상자를 만드는 과정에서 사용할 수 있습니다. 필터는 CJA에서 정의 및 유지됩니다.

**필터** 비교 **세그먼트**: CJA는 &quot;세그먼트&quot;의 개념을 사용하지 않습니다. 대신 &quot;필터&quot;를 사용합니다. 둘 다 유사한 논리를 포함할 수 있는 규칙 세트인 반면, 다른 출력을 생성합니다. 필터는 분석 목적으로 데이터 집합 범위를 좁히는 데 사용됩니다. 세그먼트는 활성화에 사용할 수 있는 ID 목록을 만드는 데 사용됩니다. 세그먼트는 실시간 고객 프로필에서 대상을 생성하지만 필터(단독)는 대상을 생성하지 않습니다. CJA 대상 게시는 CJA 필터를 사용하여 실시간 고객 프로필에서 사용할 수 있는 대상을 만드는 프로세스입니다.

## 권한

관리자는 자동으로 [!UICONTROL 대상 게시] Adobe Admin Console의 권한. 개별 사용자에게 이 권한을 부여할 수 있습니다.

## 다음 단계

* [대상자 만들기 및 게시](/help/components/audiences/publish.md)
* [대상자 관리](/help/components/audiences/manage.md)


