---
description: 경고를 사용하면 알림을 세밀하게 제어하고 예외 항목 탐지와 통합할 수 있습니다.
title: 경고 개요
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 27%

---

# 경고 개요

Customer Journey Analytics의 경고를 사용하면 변경된 백분율이나 특정 데이터 포인트에 따라 알림을 받을 수 있습니다.

Customer Journey Analytics 패키지에 따라 예외 항목 임계값에 따라 트리거할 경고를 사용할 수도 있습니다. 이러한 경고(&quot;지능형 경고&quot;라고도 함)는 [예외 항목 탐지](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)와 통합되어 가장 필요할 때 트리거되는 세분화된 제어를 제공합니다.

경고를 사용하면 다음 작업을 수행할 수 있습니다.

* 경고가 트리거되는 빈도를 미리 봅니다.
* 자동 생성된 Analysis Workspace 프로젝트에 대한 링크가 있는 이메일 또는 SMS로 경고를 보냅니다.
* 하나의 경고에서 여러 지표를 캡처하는 &quot;누적된&quot; 경고를 생성합니다.
* 예외 항목을 기반으로 한 경고를 만듭니다 (90%, 95%, 99%, 99.75%, 및 99.9% 임계값, % 변경률, 초과/미만) (Select, Prime 또는 Ultimate 패키지를 보유한 Customer Journey Analytics 고객에게만 제공)

다음 비디오 자습서에서는 경고에 대한 기본 개요를 제공합니다. [경고](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=ko-KR)(5:34)

## 경고가 Adobe Analytics과 어떻게 Customer Journey Analytics이 다른지 이해합니다.

Customer Journey Analytics에서 경고를 사용하는 프로세스는 Adobe Analytics에서 경고를 사용하는 프로세스와 거의 동일합니다. 그러나 중요한 차이점이 있습니다.

자세한 내용은 [경고 기능 비교: Customer Journey Analytics 및 Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)를 참조하십시오.

## 경고 예외 항목 살펴보기

>[!NOTE]
>
>예외 항목 탐지를 사용하는 경고(_지능형 경고_&#x200B;라고도 함)는 Customer Journey Analytics Select, Prime 또는 Ultimate 패키지가 있는 조직에서만 사용할 수 있습니다.

경고에서 예외 항목 탐지를 사용하는 경우 교육 기간은 경고에 대해 선택한 세부기간에 따라 달라집니다.

* 월별 세부기간: 15개월 + 지난해와 동일한 범위
* 주별 세부기간: 15주 + 지난해와 동일한 범위
* 일별 세부기간: 35일 + 지난해와 동일한 범위
* 시간 세부기간: 336시간

자세한 내용은 [예외 항목 탐지에서 사용되는 통계 기법](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)을 참조하십시오.

## 경고 만들기

Customer Journey Analytics에서 경고를 만드는 방법에 대한 자세한 내용은 [경고 만들기](/help/components/c-intelligent-alerts/alert-builder.md)를 참조하십시오.

>[!IMPORTANT]
>
>경고를 생성하는 타임스탬프가 지정된 데이터를 사용하면 경고가 잘못 표시될 수 있습니다. Adobe 경고에는 타임스탬프가 지정되지 않은 데이터를 사용하는 것이 좋습니다.

## 경고 관리

경고 관리자에서 기존 경고를 관리할 수 있습니다. 태그 지정, 이름 변경, 삭제 등과 같은 경고에 대한 다양한 관리 작업을 수행할 수 있습니다.

Customer Journey Analytics에서 기존 경고를 관리하는 방법에 대한 자세한 내용은 [경고 관리](/help/components/c-intelligent-alerts/alert-manager.md)를 참조하십시오.

