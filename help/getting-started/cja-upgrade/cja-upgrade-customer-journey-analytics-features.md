---
title: Customer Journey Analytics의 고유한 기능 이해
description: Customer Journey Analytics의 고유한 기능에 대해 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: f4440148d26e81938d029d4a077cd787c868f1be
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 54%

---

# Customer Journey Analytics의 고유한 기능 이해 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="다양한 출처의 데이터 연결"
>abstract="(권장) 다른 채널의 분석 데이터를 결합하는 기능은 Customer Journey Analytics의 기본 사용 사례입니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="여러 데이터 세트에서 히트 결합"
>abstract="데이터 세트 중 하나라도 기본 식별자(예: Experience Cloud ID)를 공유하지 않는 경우에도 로그인 사용자 이름이나 이메일 주소와 같은 다른 차원을 사용하여 해당 데이터를 연결할 수 있습니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analytics 업그레이드 확인 목록](https://gigazelle.github.io/cja-ttv/)의 질문에 답변할 때 이 페이지의 정보를 사용하십시오.

다음 목록은 업그레이드 프로세스 중에 고려해야 하는 Customer Journey Analytics 기능만 보여 줍니다. Customer Journey Analytics에서 완전히 지원되거나, 부분적으로 지원되거나, 지원되지 않는 Adobe Analytics 기능을 보여 주는 포괄적인 목록을 보려면 [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)을 참조하십시오.

Customer Journey Analytics으로 업그레이드할 때 다음 Customer Journey Analytics 기능 중 채택할 기능을 고려하십시오.

| Customer Journey Analytics 기능 | 함수 |
|---------|----------|
| [웹 데이터를 콜 센터 데이터와 같은 다른 채널의 데이터와 연결](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics는 모든 종류의 데이터 스키마와 유형을 보유할 수 있는 Experience Platform의 기능과 결합되어 있습니다. [경험 데이터 모델(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)을 사용하여 데이터를 조합하고 탐색할 수 있도록 균일하게 나타내고 구성할 수 있습니다. Adobe Analytics는 일부 [데이터 가져오기](https://experienceleague.adobe.com/docs/analytics/import/home.html) 기능을 사용하여 주로 웹 및 모바일 분석 데이터에 중점을 둡니다. |
| [사용자 지정 차원을 사용하여 다른 데이터 세트의 히트를 연결합니다](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics를 사용하면 여러 보고서 세트의 데이터를 마치 Adobe Analytics의 단일 보고서 세트인 것처럼 [결합](/help/connections/combined-dataset.md)할 수 있습니다. |
| Adobe Real-time CDP와 통합 |  |
| [Adobe Journey Optimizer과 통합](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) |  |


