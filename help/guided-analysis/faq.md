---
title: 안내식 분석 FAQ
description: 안내식 분석에 대해 자주 묻는 질문입니다.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: 제품 분석
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 64%

---

# 안내식 분석 FAQ

가이드 분석에 대한 FAQ.

+++**내 조직에 가이드 분석을 위한 프로비저닝은 어떻게 수행할 수 있습니까?**

안내식 분석은 Customer Journey Analytics의 유료 추가 기능인 Adobe Product Analytics의 일부입니다. 이 추가 기능을 사용하려면 Adobe 계정 팀에 문의하십시오.

+++

+++**가이드 분석을 사용하려면 어떤 구현 변경이 필요합니까?**

현재 이미 Customer Journey Analytics를 사용하고 있다면 추가적인 구현 변경이 필요하지 않습니다. 안내식 분석은 [Analysis Workspace](../analysis-workspace/home.md) 등 다른 CJA 인터페이스와 동일한 [데이터 보기](../data-views/data-views.md) 및 [연결](../connections/overview.md)을 사용합니다.

안내식 분석을 통해 최종 사용자가 가장 성공할 수 있도록 Adobe Experience Platform 및 의 강력한 이벤트 스키마 및 관리 전략을 사용하는 것이 좋습니다. [데이터 보기](../data-views/data-views.md).

+++

+++**언제 가이드 분석 또는 Analysis Workspace을 사용해야 합니까?**

**안내식 분석**&#x200B;을 사용하면 사용자가 고품질 인사이트를 빠르게 얻을 수 있습니다. 제품 팀, 더 자신 있게 데이터 작업을 하려는 사용자, 나아가 심층 분석을 시작하는 분석가에게도 유용합니다.

**[Analysis Workspace](../analysis-workspace/home.md)**&#x200B;는 더 많은 인사이트를 확보하기 위해 데이터를 심층적으로 살펴볼 수 있도록 한층 더 자유로운 형식을 취하는 공간입니다. 데이터를 잘 이해하고 심층적으로 분석하려는 분석가와 고급 사용자에게 유용합니다.

+++

+++**안내식 분석과 Analysis Workspace 간의 용어 비교는 어떻게 합니까?**

안내식 분석은 제품 팀에서 더 자주 사용되는 용어를 사용합니다. 안내식 분석과 간에 전환할 때 이 표를 참조할 수 있습니다 [Analysis Workspace](../analysis-workspace/home.md).

| 안내식 분석 용어 | Analysis Workspace 용어 |
| --- | --- |
| 이벤트 | 지표 |
| 사용자 | 사용자 |
| 속성 | 차원 |
| 값 | 차원 항목 |
| 세그먼트 | 필터 |

{style="table-layout:auto"}

+++

+++**가이드 분석 및 Analysis Workspace 접근 방식 보고에 대한 차이점은 무엇입니까?**

While [Analysis Workspace](../analysis-workspace/home.md) 안내식 분석에서는 동일한 기본 데이터를 사용하므로 각 도구에서 해당 데이터의 쿼리를 구성할 수 있는 방식이 다릅니다.

* **Analysis Workspace는 차원 중심의 경험입니다.** 테이블은 일반적으로 차원 행으로 구성되는 반면 열은 일반적으로 지표로 구성됩니다. 원하는 데이터를 얻기 위해 행과 열 모두에 필터를 적용할 수 있습니다.

* **안내식 분석은 이벤트 및 사용자 중심 경험입니다.** 각 분석은 이벤트 선택으로 시작되며, 차원과 필터를 추가하여 해당 이벤트 데이터를 세분화할 수 있습니다.

![Analysis Workspace 및 안내식 분석 보기](assets/structure.png){style="border:1px solid gray"}

웹 사이트 홈 페이지와 관련된 데이터에 초점을 맞춘 다음 예를 고려해 보십시오. 팀은 비슷한 질문을 하지만 분석 접근 방식은 다를 수 있습니다.

* 일반적인 차원 중심의 Analysis Workspace 접근 방식은 “홈 페이지를 보고 페이지 조회수가 얼마나 되는지 살펴본다”입니다.

  ![차원 중심](assets/dimension-centered.png){style="border:1px solid gray"}

* 일반적인 이벤트 및 사용자 중심의 안내식 분석 접근 방식은 &quot;몇 명의 사용자가 우리 홈 페이지를 방문했습니까?&quot;일 수 있습니다.

  ![이벤트 중심](assets/event-centered.png){style="border:1px solid gray"}

+++
