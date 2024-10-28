---
title: Customer Journey Analytics에 사용할 스키마 설계
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Customer Journey Analytics에 사용할 스키마 설계

>[!NOTE]
>
>Adobe Analytics 이 설명서는 [업그레이드 Customer Journey Analytics 설문지](https://gigazelle.github.io/cja-ttv/)를 작성한 후 사용해야 합니다.
> 
>조직에 대해 동적으로 생성된 단계의 일부로 이 페이지의 정보를 사용하십시오.
>
>이 페이지의 단계를 완료한 후 [Adobe Analytics에서 조직에 대해 동적으로 생성된 업그레이드 단계를 계속 수행하여 업그레이드 질문을 Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/)하십시오.

Adobe은 Customer Journey Analytics으로 업그레이드할 때 XDM(Experience Data Model) 스키마를 생성할 것을 권장합니다. XDM 스키마를 사용하면 조직의 요구 사항과 사용하는 특정 Platform 애플리케이션에 맞게 조정된 간소화된 스키마를 사용할 수 있습니다. 스키마를 변경해야 하는 경우, 업데이트가 필요한 필드를 찾기 위해 사용하지 않는 수천 개의 필드를 검색하지 않아도 됩니다.

XDM 스키마 만들기를 시작하기 전에:

1. 조직 전체에서 데이터 팀 및 기타 이해 당사자를 식별합니다.

1. 조직에서 사용하는 다른 Adobe Experience Platform 애플리케이션을 고려하면서 Customer Journey Analytics에 대한 조직의 이상적인 스키마 디자인을 결정합니다.

1. [Adobe Analytics에서 업그레이드 Customer Journey Analytics 설문 조사](https://gigazelle.github.io/cja-ttv/)로 조직에 대해 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

