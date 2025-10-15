---
title: 알고리즘 기여도 분석
description: 알고리즘 속성 모델의 세부 사항을 이해합니다.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 42%

---

# 알고리즘 속성

Analysis Workspace의 알고리즘 [속성 모델](models.md)은 통계적 기법을 사용하여 보고서나 자유 형식 테이블의 차원 항목에 크레딧을 할당한다는 점에서 다른 모델과 다릅니다. Analysis Workspace의 다른 모든 속성 모델과 마찬가지로 모든 차원 또는 지표에서 알고리즘 속성을 사용할 수 있습니다. 알고리즘 속성은 무제한 세그먼테이션 및 분류를 지원하고, 테이블의 하나 이상의 차원에 100% 전환을 분배합니다(&quot;분수&quot; 속성이라고도 함).


>[!BEGINSHADEBOX]

데모 비디오는 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [알고리즘 속성](https://video.tv.adobe.com/v/36205?quality=12&learn=on){target="_blank"}을 참조하십시오.

>[!ENDSHADEBOX]


속성에 사용되는 알고리즘은 협업 게임 이론의 Harsanyi 배당을 기반으로 합니다. Harsanyi 배당은 결과에 불평등한 기여와 함께 플레이어들 간의 크레딧을 분배하기 위해 Shapley 값 솔루션(노벨 경제학상 수상자인 Lloyd Shapley의 이름을 따서 이름이 지어짐)의 일반화입니다.

높은 수준에서 각 접점에 대한 전환 크레딧의 속성 계산은 전환 창 내의 각 마케팅 접점을 플레이어의 연합으로 간주합니다. 이런 연대에는 흑자가 균등하게 분배돼야 한다. 각 연합의 잉여금은 각 하위 연합이 이전에 재귀적으로 만든 잉여금에서 결정됩니다.

자세한 내용은 John Harsanyi 및 Lloyd Shapley의 원본 논문을 참조하십시오.

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2 (28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4 (2)*, 194-220.

>[!NOTE]
>
>주어진 전환 창 내에 여러 접점이 있을 때 알고리즘 속성의 결과는 다른 모델과 다릅니다. 단일 접점을 사용하는 전환은 속성 모델에 상관없이 100% 크레딧을 받습니다.
