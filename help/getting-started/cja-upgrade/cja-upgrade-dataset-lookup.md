---
title: Customer Journey Analytics을 위한 스키마 만들기
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# 조회 데이터 세트를 만들어 Customer Journey Analytics에서 데이터 분류

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

Adobe Analytics의 분류 데이터와 마찬가지로 조회 데이터 세트는 Customer Journey Analytics에서 데이터를 분류하는 방법입니다.

Analytics 소스 커넥터를 사용하는 경우 일부 표준 조회 데이터 세트가 보고서 시간에 자동으로 적용됩니다. 자세한 내용은 [데이터 세트에 표준 조회 추가](/help/connections/standard-lookups.md)를 참조하십시오.

Experience Platform Web SDK의 새로운 구현으로 데이터를 분류하려면 분류할 데이터가 포함된 각 차원에 대한 조회 데이터 세트를 만들어야 합니다.

Customer Journey Analytics에서 사용할 조회 데이터 세트를 만들려면:

1. AEP에서 새 스키마를 만듭니다. 조회 데이터 세트에 고유한 새 스키마입니다. 기존 스키마를 사용할 수 없습니다.

1. 조회에 대한 새 스키마 클래스를 생성해야 합니다.

1. 이 데이터 세트에서 조회 데이터 세트를 만듭니다.

1. [권장된 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 [동적으로 생성된 업그레이드 단계](https://gigazelle.github.io/cja-ttv/)를 계속 따릅니다.
