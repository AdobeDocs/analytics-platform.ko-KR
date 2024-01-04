---
title: 안내식 분석 FAQ
description: 가이드 분석에 대한 FAQ.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: 제품 분석
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# 안내식 분석 FAQ

가이드 분석에 대한 FAQ.

+++**내 조직에 가이드 분석을 위한 프로비저닝은 어떻게 수행할 수 있습니까?**

안내식 분석은 Customer Journey Analytics에 대한 유료 추가 기능인 Adobe Product Analytics의 일부입니다. 이 추가 기능을 사용하려면 Adobe 계정 팀에 문의하십시오.

+++

+++**안내식 분석을 사용하기 위해 어떤 구현 변경이 필요합니까?**

현재 이미 Customer Journey Analytics을 사용 중인 경우 추가적인 구현 변경 사항이 필요하지 않습니다. 안내식 분석에서는 동일한 방법을 사용합니다 [데이터 보기](../data-views/data-views.md) 및 [연결](../connections/overview.md) 과 같은 기타 CJA 인터페이스로 [Analysis Workspace](../analysis-workspace/home.md).

안내식 분석을 통해 최종 사용자가 가장 성공할 수 있도록 Adobe Experience Platform 및 의 강력한 이벤트 스키마 및 관리 전략을 사용하는 것이 좋습니다. [데이터 보기](../data-views/data-views.md).

+++

+++**언제 Guided Analysis 또는 Analysis Workspace을 사용해야 합니까?**

**안내식 분석** 는 사용자가 고품질 통찰력을 신속하게 얻을 수 있도록 지원합니다. 이 기능은 제품 팀, 데이터를 보다 자신 있게 작업하려는 사용자 및 분석가가 심층적인 분석을 시작하는 데 유용합니다.

**[Analysis Workspace](../analysis-workspace/home.md)** 는 더 많은 통찰력을 발견하기 위해 데이터를 더 깊이 탐색할 수 있는 더 많은 자유 형식 공간입니다. 데이터를 잘 이해하고 깊이 파고들고자 하는 분석가 및 고급 사용자에게 유용합니다.

+++

+++**안내식 분석과 Analysis Workspace 간의 용어 비교는 어떻게 합니까?**

안내식 분석에서는 제품 팀 간에 더 자주 사용되는 용어를 사용합니다. 안내식 분석과 간 전환할 때 이 표를 참조할 수 있습니다 [Analysis Workspace](../analysis-workspace/home.md).

| 안내식 분석 용어 | Analysis Workspace 용어 |
| --- | --- |
| 이벤트 | 지표 |
| 사용자 | 사용자 |
| 속성 | 차원 |
| 값 | Dimension 항목 |
| 세그먼트 | 필터 |

{style="table-layout:auto"}

+++

+++**가이드 분석 및 Analysis Workspace의 보고 접근 방식에 대한 차이점은 무엇입니까?**

While [Analysis Workspace](../analysis-workspace/home.md) 및 안내식 분석에서는 동일한 기본 데이터를 사용하므로 각 도구에서 해당 데이터의 쿼리를 구성할 수 있는 방식이 다릅니다.

* **Analysis Workspace은 차원 중심 경험입니다.** 테이블은 일반적으로 차원 행으로 구성되는 반면 열은 일반적으로 지표입니다. 필터를 행과 열 모두에 적용하여 원하는 데이터를 얻을 수 있습니다.

* **안내식 분석은 이벤트 및 사용자 중심의 경험입니다.** 각 분석은 이벤트를 선택하여 시작한 다음 차원과 필터를 추가하여 해당 이벤트 데이터를 구체화할 수 있습니다.

![Analysis Workspace 및 안내식 분석 보기](assets/structure.png)

웹 사이트의 홈 페이지 관련 데이터에 중점을 두는 다음 예를 생각해 보십시오. 팀은 유사한 질문을 하지만 분석 접근 방식이 다를 수 있습니다.

* 일반적인 차원 중심 Analysis Workspace 접근 방식은 &quot;홈 페이지를 살펴보고 받은 페이지 보기 수를 살펴보겠습니다.&quot;

  ![Dimension 중심](assets/dimension-centered.png)

* 일반적인 이벤트 및 사용자 중심의 안내식 분석 접근 방식은 &quot;몇 명의 사용자가 우리 홈 페이지를 방문했습니까?&quot;일 수 있습니다.

  ![이벤트 중심](assets/event-centered.png)

+++
