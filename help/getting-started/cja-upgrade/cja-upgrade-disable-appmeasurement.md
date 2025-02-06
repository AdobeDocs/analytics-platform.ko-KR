---
title: 연결에 Analytics 소스 커넥터 데이터 세트 추가
description: Analytics 소스 커넥터 데이터 세트를 연결에 추가하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 9%

---

# AppMeasurement 데이터 수집 비활성화 {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="AppMeasurement 데이터 수집 비활성화"
>abstract="웹 SDK 데이터가 완전히 작동하면 개발자 팀과 함께 웹 사이트 또는 속성에서 AppMeasurement.js를 제거합니다.<br><br>웹 사이트에서 AppMeasurement을 제거하는 작업은 몇 분 밖에 걸리지 않지만 엔지니어링 팀에서 완료하는 데 시간이 필요합니다. 단, Analytics 사용자가 Adobe Analytics이 아닌 Customer Journey Analytics을 사용하고 있는지 확인하십시오. 아직 사용하지 않았다면 모든 사람을 이동하는 이 공지 프로세스는 훨씬 더 오래 걸릴 수 있습니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

<!-- need to work on this -->

* **태그:** Adobe Analytics 확장 사용 안 함

* **AppMeasurement:** AppMeasurement.js 라이브러리 s=newobject 바꾸기
