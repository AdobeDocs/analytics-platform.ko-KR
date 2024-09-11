---
description: 새로운 지능형 경고 시스템에서는 경고를 더욱 세밀하게 제어할 수 있으며 예외 항목 탐지 기능이 경고 시스템과 통합됩니다.
title: 지능형 경고 개요
feature: Workspace Basics
role: User, Admin
source-git-commit: 74ad39f6ccc6436f7c8540b7d8b69b20b93d2b5c
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 56%

---

# 지능형 경고 개요

{{release-limited-testing}}

Customer Journey Analytics의 지능형 경고(또는 &quot;경고&quot;)를 사용하면 데이터에서 비정상적인 이벤트가 발생하는 경우 알림을 받을 수 있습니다.

예외 항목 임계값, 백분율 변경 또는 특정 데이터 포인트를 기준으로 지능형 경고가 트리거되도록 설정할 수 있습니다. 경고는 [예외 항목 탐지](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)와 통합되는 세분화된 제어를 제공하여 가장 필요할 때 트리거됩니다.

지능형 경고를 사용하면 다음 작업을 수행할 수 있습니다.

* 예외 항목을 기반으로 한 경고를 만듭니다(90%, 95%, 99%, 99.75%, 및 99.9% 임계값, % 변경률, 초과/미만)
* 경고가 트리거되는 빈도를 미리 봅니다.
* 자동 생성된 Analysis Workspace 프로젝트에 대한 링크가 있는 이메일 또는 SMS로 경고를 보냅니다.
* 하나의 경고에서 여러 지표를 캡처하는 &quot;누적된&quot; 경고를 생성합니다.

다음 비디오 자습서에서는 경고에 대한 기본 개요를 제공합니다. [지능형 경고](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=ko-KR)(5:34)

## 경고가 Adobe Analytics과 어떻게 Customer Journey Analytics이 다른지 이해합니다.

Customer Journey Analytics에서 지능형 경고의 사용 프로세스는 Adobe Analytics에서 지능형 경고의 사용 프로세스와 거의 동일합니다. 그러나 중요한 차이점이 있습니다.

자세한 내용은 [지능형 경고 기능 비교: Customer Journey Analytics 및 Adobe Analytics](/help/analysis-workspace/c-intelligent-alerts/alerts-feature-comparison.md)를 참조하십시오.

## 경고 예외 항목 살펴보기

경고에서 예외 항목 탐지를 사용하는 경우 교육 기간은 경고에 대해 선택한 세부기간에 따라 달라집니다.

* 월별 세부기간: 15개월 + 지난해와 동일한 범위
* 주별 세부기간: 15주 + 지난해와 동일한 범위
* 일별 세부기간: 35일 + 지난해와 동일한 범위
* 시간 세부기간: 336시간

자세한 내용은 [예외 항목 탐지에서 사용되는 통계 기법](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)을 참조하십시오.

## 경고 만들기

Customer Journey Analytics에서 경고를 만드는 방법에 대한 자세한 내용은 [경고 만들기](/help/analysis-workspace/c-intelligent-alerts/alert-builder.md)를 참조하십시오.

>[!IMPORTANT]
>
>경고를 생성하는 타임스탬프가 지정된 데이터를 사용하면 경고가 잘못 표시될 수 있습니다. 지능형 경고에는 타임스탬프가 지정되지 않은 데이터를 사용하는 것이 좋습니다.

## 경고 관리

경고 관리자에서 기존 경고를 관리할 수 있습니다. 태그 지정, 이름 변경, 삭제 등과 같은 경고에 대한 다양한 관리 작업을 수행할 수 있습니다.

Customer Journey Analytics에서 기존 경고를 관리하는 방법에 대한 자세한 내용은 [경고 관리](/help/analysis-workspace/c-intelligent-alerts/alert-manager.md)를 참조하십시오.

