---
title: 연결에 Analytics 소스 커넥터 데이터 세트 추가
description: Analytics 소스 커넥터 데이터 세트를 연결에 추가하는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 9cfe89aef069d777424eb8a5d9ef8ae03a9d0486
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 43%

---

# Adobe Analytics 비활성화 {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="AppMeasurement 데이터 수집 비활성화"
>abstract="Web SDK 데이터가 완벽하게 작동하려면 개발자 팀과 협력하여 웹 사이트나 속성에서 AppMeasurement.js를 제거합니다.<br><br>웹 사이트에서 AppMeasurement를 제거하는 작업은 몇 분밖에 걸리지 않지만 엔지니어링 팀에서 완료하는 데는 시간이 좀 걸릴 수 있습니다. 단, Analytics 사용자가 Adobe Analytics가 아닌 Customer Journey Analytics를 사용하고 있는지 확인하십시오. 아직 이 작업을 수행하지 않았다면 모든 사용자를 이동시키기 위한 공지 프로세스가 훨씬 더 오래 걸릴 수 있습니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나 [Adobe Analytics-Customer Journey Analytics 업그레이드 설문지](https://gigazelle.github.io/cja-ttv/)를 통해 조직에 대해 동적으로 생성된 업그레이드 단계를 따를 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

Adobe Analytics을 사용하지 않도록 설정하기 전에 [Customer Journey Analytics으로 업그레이드한 후 Adobe Analytics을 사용하지 않도록 설정할 시기 평가](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)의 정보를 검토하십시오.

* **태그:** Adobe Analytics 확장 사용 안 함

* **AppMeasurement:** AppMeasurement.js 라이브러리 s=newobject 바꾸기
