---
title: 가이드 분석 FAQ
description: 가이드 분석에 대해 자주 묻는 질문입니다.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: 제품 분석
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 96%

---

# 가이드 분석 FAQ

가이드 분석에 대해 자주 묻는 질문입니다.

+++**조직은 가이드 분석에 액세스할 수 있습니까?**

가이드 분석 보기는 모든 Customer Journey Analytics 패키지에 포함됩니다. CJA 패키지가 활용하는 보기에 대한 자세한 내용은 개요 페이지의 [프로비저닝](overview.md#provisioning) 섹션을 참조하십시오.

+++

+++**가이드 분석을 사용하는 데 필요한 구현 변경은 무엇입니까?**

현재 이미 Customer Journey Analytics를 사용하고 있다면 추가적인 구현 변경이 필요하지 않습니다. 가이드 분석은 [Analysis Workspace](../analysis-workspace/home.md) 등 다른 CJA 인터페이스와 동일한 [데이터 보기](../data-views/data-views.md) 및 [연결](../connections/overview.md)을 사용합니다.

최종 사용자가 가이드 분석을 통해 가장 성공적인 결과를 얻을 수 있도록 하려면 Adobe Experience Platform 및 [데이터 보기](../data-views/data-views.md)에 강력한 이벤트 스키마와 관리 전략을 마련하는 것이 좋습니다.

+++

+++**가이드 분석이나 Analysis Workspace를 사용해야 하는 때는 언제입니까?**

**가이드 분석**&#x200B;을 사용하면 사용자가 고품질 인사이트를 빠르게 얻을 수 있습니다. 제품 팀, 더 자신 있게 데이터 작업을 하려는 사용자, 나아가 심층 분석을 시작하는 분석가에게도 유용합니다.

**[Analysis Workspace](../analysis-workspace/home.md)**&#x200B;는 더 많은 인사이트를 확보하기 위해 데이터를 심층적으로 살펴볼 수 있도록 한층 더 자유로운 형식을 취하는 공간입니다. 데이터를 잘 이해하고 심층적으로 분석하려는 분석가와 고급 사용자에게 유용합니다.

+++

+++**가이드 분석과 Analysis Workspace 간의 용어를 비교하면 어떻습니까?**

가이드 분석 및 [Analysis Workspace](../analysis-workspace/home.md)는 몇 가지 작은 차이점을 제외하고는 대부분의 주요 용어가 일치합니다.

| 가이드 분석 용어 | Analysis Workspace 용어 |
| --- | --- |
| 이벤트(바이너리 1/0 지표) | 지표 |
| 사용자 | 사용자 |
| 차원 | 차원 |
| 차원 항목 | 차원 항목 |
| 세그먼트 | 세그먼트 |
| 필터링 | 보고서 필터 |
| 계산된 지표, 지표 | 계산된 지표 |

{style="table-layout:auto"}

+++

+++**가이드 분석과 Analysis Workspace 보고 접근 방식에는 어떤 차이점이 있습니까?**

[Analysis Workspace](../analysis-workspace/home.md)와 가이드 분석은 동일한 기본 데이터를 사용하지만 각 도구를 사용하여 해당 데이터에 대한 쿼리를 구성하는 방식은 다릅니다.

* **Analysis Workspace는 차원 중심의 경험입니다.** 테이블은 일반적으로 차원 행으로 구성되는 반면 열은 일반적으로 지표로 구성됩니다. 원하는 데이터를 얻기 위해 세그먼트를 행과 열 모두에 적용할 수 있습니다.

* **가이드 분석은 이벤트 및 사용자 중심 경험입니다.** 각 분석은 이벤트 선택으로 시작되며, 차원과 세그먼트를 추가하여 해당 이벤트 데이터를 세분화할 수 있습니다.

![Analysis Workspace 및 가이드 분석 보기](assets/structure.png){style="border:1px solid gray"}

웹 사이트 홈 페이지와 관련된 데이터에 초점을 맞춘 다음 예를 고려해 보십시오. 팀은 비슷한 질문을 하지만 분석 접근 방식은 다를 수 있습니다.

* 일반적인 차원 중심의 Analysis Workspace 접근 방식은 “홈 페이지를 보고 페이지 조회수가 얼마나 되는지 살펴본다”입니다.

  ![차원 중심](assets/dimension-centered.png){style="border:1px solid gray"}

* 대표적인 이벤트 및 사용자 중심 가이드 분석 접근 방식은 “홈 페이지를 방문한 사용자 수에 대한 질문”입니다.

  ![이벤트 중심](assets/event-centered.png){style="border:1px solid gray"}

+++
