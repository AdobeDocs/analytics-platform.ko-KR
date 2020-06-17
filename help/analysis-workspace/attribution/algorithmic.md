---
title: 알고리즘 속성
description: 알고리즘 속성 모델에 대한 세부 사항.
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 7%

---


# 알고리즘 속성

>[!NOTE] Customer Journey Analytics의 Analysis Workspace 설명서를 보고 있습니다. 이 기능은 기존 Adobe Analytics의 [Analysis Workspace과 약간 다릅니다](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html). [추가 정보...](/help/getting-started/cja-aa.md)

>[!NOTE] **[!UICONTROL 알고리즘]** 어트리뷰션은 현재 제한된 테스트 중입니다. 자세한 내용은 [Adobe Analytics 기능 릴리스를](https://docs.adobe.com/content/help/ko-KR/analytics/landing/an-releases.html) 참조하십시오.

Analysis Workspace의 알고리즘 [속성 모델](models.md) 은 통계적 기법을 사용하여 보고서나 자유 형식 테이블의 차원 값에 크레디트를 할당한다는 점에서 다른 모델과 다릅니다. Analysis Workspace의 다른 모든 기여도 모델과 마찬가지로 모든 차원이나 지표에서 사용할 수 있으며 무제한 세그먼테이션 및 분류를 지원하고 테이블의 차원에 대한 100% 전환(&quot;분수&quot; 기여도)을 분배합니다.

기여도에 사용되는 알고리즘은 협업 게임 이론의 Harsanyi 배당을 기반으로 합니다. Harsanyi 배당은 결과에 불평등한 기여와 함께 플레이어들 간의 크레딧을 분배하기 위해 Shapley 값 솔루션(노벨 경제학상 수상자인 Lloyd Shapley의 이름을 따서 이름 지었습니다)의 일반화입니다.

높은 수준에서, 각 터치포인트에 대한 전환 크레딧의 어트리뷰션 계산에서는 룩백 창 내의 각 마케팅 접점을 잉여금이 균등하게 분배되어야 하는 선수들의 연합으로 간주합니다. 각 연합의 잉여금은 각 하위 연합(또는 이전에 참가한 차원 값)에 의해 이전에 생성된 잉여금에 따라 재귀적으로 결정됩니다. 자세한 내용은 John Harsanyi&#39;s and Lloyd Shapley의 원본 논문을 참조하십시오.

* 사플리, 로이드 S. (1953). N-Person 게임에 대한 값. *게임이론에 대한 공헌, 2 (28)*, 307-317.
* 하산이, 존 C. (1963). 1인 협력게임을 위한 간소화된 협상 모델. *International Economic Review 4(2)*, 194-220.

>[!NOTE] 주어진 조회 창 내에 여러 터치포인트가 있을 때 알고리즘 속성의 결과는 다른 모델과 다릅니다. 단일 터치포인트를 사용하는 전환은 기여도 모델에 상관없이 100% 크레딧을 받습니다.
