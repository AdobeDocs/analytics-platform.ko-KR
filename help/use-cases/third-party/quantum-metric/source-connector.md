---
title: Customer Journey Analytics에 양자 지표 데이터 추가
description: 사용자 여정 및 동작의 데이터 수집에 Quantum 지표를 사용한 다음 수집된 데이터에서 CJA을 강화하여 더 풍부한 통찰력을 얻을 수 있습니다.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 1%

---

# Customer Journey Analytics에 양자 지표 데이터 추가

>[!IMPORTANT]
>
>현재 Quantum Metric 소스 커넥터를 아직 사용할 수 없습니다.

CJA은 QM 데이터, 순차적 데이터 분석, 풍부한 속성 및 기타 고급 보고의 보고서 시간 제어를 해제합니다.  QM 소스 커넥터 또는 Quantum Metrics Tags 확장을 사용하여 QM을 AEP으로 보낼 수 있습니다.

## 1단계: 양자 지표 소스 커넥터 만들기

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. [!UICONTROL Experience Platform] > [!UICONTROL 연결] > [!UICONTROL 소스]&#x200B;(으)로 이동합니다.
1. Quantum Metric 소스 커넥터를 추가하고 프롬프트에 따라 을 완료합니다.

자세한 내용은 [Adobe Experience Platform 소스 커넥터](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/home)를 참조하십시오.

## 2단계: Customer Journey Analytics에서 연결 만들기

Quantum 지표 데이터에 대한 소스 커넥터를 만들면 Adobe Experience Platform에서 데이터 세트가 자동으로 만들어집니다. 이 데이터 세트를 Customer Journey Analytics의 새 또는 기존 [연결](/help/connections/overview.md)에 추가합니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하고 상단 메뉴에서 **[!UICONTROL 연결]**(선택 사항: **[!UICONTROL 데이터 관리]**)을 선택합니다.
1. 연결에 이름을 지정하고 연결에 양자 지표 데이터 세트를 추가합니다.
1. **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

>[!NOTE]
>양자 지표 데이터를 나머지 Customer Journey Analytics 데이터와 동일한 연결에 추가할 수 있지만, 두 데이터 세트 간에 공통 개인 ID가 없으면 해당 데이터를 함께 결합할 수 없습니다. 이 동작을 원하는 경우 Adobe에서는 소스 커넥터 대신 [Tag 확장](https://experienceleague.adobe.com/ko/docs/experience-platform/destinations/catalog/analytics/quantum-metric)을 사용하는 것이 좋습니다.

## 3단계: Customer Journey Analytics에서 데이터 보기 만들기

[데이터 보기](/help/data-views/data-views.md)를 만들어 차원 및 지표 설정을 구성하십시오.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하여 상단 메뉴에서 **[!UICONTROL 데이터 보기]**(선택 사항: **[!UICONTROL 데이터 관리]**)을(를) 선택합니다.
1. 원하는 데이터 보기를 선택하거나 데이터 보기를 만듭니다.
1. 오른쪽의 스키마 필드 목록에서 원하는 양자 지표 차원 및 지표를 찾아 가운데에 있는 차원 및 지표 영역으로 끌어서 놓습니다.
1. 오른쪽 창을 사용하여 원하는 각 차원 및 지표를 구성합니다.

## 4단계: Customer Journey Analytics에서 보고 및 분석 시작

이제 Customer Journey Analytics에서 데이터를 사용할 수 있으므로 데이터에 대한 보고를 시작할 수 있습니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하고 상단 메뉴에서 **[!UICONTROL Workspace]**&#x200B;을(를) 선택합니다.
1. 기존 프로젝트를 선택하거나 프로젝트를 만듭니다.
1. 원하는 양자 지표 차원 또는 지표를 Workspace 캔버스로 드래그하여 데이터를 분석합니다.
