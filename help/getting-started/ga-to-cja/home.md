---
title: Google Analytics 4에서 Customer Journey Analytics으로 전환
description: Google Analytics 4에 익숙한 분석가에 초점을 맞춰 Customer Journey Analytics에서 보고서를 가져오기 위한 주요 개념을 알아봅니다.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 3d7c8b91-f2a4-4e6b-9c1d-5f8e3a720469
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 3%

---


# Google Analytics 4에서 Customer Journey Analytics으로 전환

이 안내서는 Google Analytics 4에 익숙한 분석가가 Adobe Customer Journey Analytics에서 동일한 개념과 보고서를 학습할 수 있도록 도와줍니다. 보고하지 않고 기술 구현을 담당할 경우 Web SDK 설정 및 데이터 수집에 대한 지침을 보려면 [타사 분석 솔루션에서 Customer Journey Analytics으로 업그레이드](../cja-upgrade/cja-upgrade-third-party-solution.md)를 참조하십시오. 조직에서 여전히 기존 Google Analytics 데이터를 Adobe Experience Platform으로 마이그레이션해야 하는 경우 [Google Analytics에서 데이터 마이그레이션](/help/use-cases/third-party/ga/overview.md)을 참조하세요.

## GA4와 Customer Journey Analytics 간의 주요 차이점

GA4와 Customer Journey Analytics은 동일한 기본 철학을 공유합니다. 모든 사용자 상호 작용은 이벤트이며, 차원 및 지표를 드래그하여 놓는 빈 캔버스 도구에서 분석을 수행하여 사용자 정의 보기를 빌드합니다. GA4 Explore에 익숙한 경우 Analysis Workspace을 즉시 인식할 수 있습니다.

가장 중요한 차이점은 Customer Journey Analytics이 GA4를 넘어서는 위치입니다.

* **크로스 채널 데이터**: Customer Journey Analytics은 동일한 분석에서 웹 분석을 오프라인 데이터 소스(예: 콜 센터 레코드, CRM 활동, 로열티 프로그램 또는 이메일 참여)와 결합할 수 있습니다. GA4는 SDK을 통해 수집된 디지털 상호 작용으로 제한됩니다.
* **보고서 처리 시간**: Customer Journey Analytics은 수집 시간이 아닌 쿼리 시간에 속성 모델, 세션 정의 및 세그먼트 규칙과 같은 논리를 적용합니다. 세션 정의 또는 기여도 분석 모델에 대한 변경 사항은 재처리 없이 모든 내역 데이터에 소급하여 적용됩니다.
* **유연한 세션 정의**: 세션 시간 제한 기간, 세션 시작 이벤트 및 세션 종료 이벤트는 모두 Customer Journey Analytics의 데이터 보기별로 구성할 수 있습니다. GA4의 세션 시간 제한은 조정 가능하지만(기본값 30분, 최대 7시간 55분) 속성 전체에 적용되며 세션 시작 및 세션 종료 동작이 수정됩니다.
* **ID 결합**: Customer Journey Analytics의 결합 기능은 동일한 사용자에게 크로스 디바이스 및 크로스 채널 상호 작용을 연결하여 GA4의 혼합 ID 모델보다 더 정확한 사용자 수를 산출할 수 있습니다.

## 계정 및 데이터 구조

GA4와 Customer Journey Analytics은 플랫폼 수준에서 데이터를 다르게 구성합니다.

| GA4 | Customer Journey Analytics |
|---|---|
| Google 계정 | Adobe IMS 조직 |
| 속성 | 연결 + 데이터 보기 |
| 데이터 스트림 | 플랫폼의 [!UICONTROL 이벤트 데이터 세트] |
| 데이터 필터 | 데이터 보기 구성 요소 필터 |
| 하위 속성 | 필터가 적용된 개별 데이터 보기 |
| 롤업 속성 | 여러 데이터 세트를 결합하는 연결 |

가장 중요한 구조적 차이점은 GA4 속성이 데이터 배선과 보고를 단일 객체로 처리한다는 것입니다. Customer Journey Analytics은 이러한 개념을 두 개의 개별 레이어로 구분합니다.

* **연결**&#x200B;은(는) 하나 이상의 Adobe Experience Platform 데이터 세트를 Customer Journey Analytics에 연결합니다. 이 단계에서는 보고에 최적화된 형식으로 Customer Journey Analytics에 데이터를 수집합니다.
* **데이터 보기**&#x200B;는 연결을 기반으로 만들어지며 보고에 사용할 수 있는 차원, 지표 및 설정을 정의합니다. 보고 구성 계층입니다.

Customer Journey Analytics에서 데이터를 분석하려면 두 가지가 모두 있어야 합니다. Customer Journey Analytics에 보고서 세트가 없습니다.

## Analysis Workspace에서 시작하기

GA4 탐색과 Analysis Workspace은 모두 빈 캔버스, 드래그 앤 드롭 분석 도구입니다. 상호 작용 모델은 동일합니다. 용어는 약간 다릅니다.

| GA4 탐색 | Analysis Workspace |
|---|---|
| 탐색 캔버스 | 패널 |
| 차트 또는 시각화 유형 | 시각화 |
| 차원 | 차원 |
| 지표 | 지표 |
| 세그먼트 또는 필터 | 세그먼트 |
| 이벤트 수 | [!UICONTROL 이벤트] |
| 사용자 | [!UICONTROL 사용자] |
| 세션 | [!UICONTROL 세션] |

>[!TIP]
>
>GA4 세그먼트 컨테이너의 이름은 사용자, 세션 및 이벤트로 지정됩니다. Customer Journey Analytics에서 이와 동등한 컨테이너는 **[!UICONTROL 개인]**, **[!UICONTROL 세션]** 및 **[!UICONTROL 이벤트]**&#x200B;입니다. 범위 논리는 동일합니다.

>[!MORELIKETHIS]
>
>* [Google Analytics에서 데이터 마이그레이션](/help/use-cases/third-party/ga/overview.md)
