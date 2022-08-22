---
title: 속성 구성 요소 설정
description: 지표에 대한 기본 속성을 설정할 수 있습니다.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: b353983b13cbbfb4c846e75aecc1b78da26ddeb2
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---

# 속성 구성 요소 설정

속성을 통해 지표에 대한 기본 속성 모델을 설정할 수 있습니다. Analysis Workspace에서 작업하는 동안 특정 지표의 속성 모델을 재정의할 수 있습니다.

![속성](../assets/attribution-settings.png)

| 설정 | 설명/사용 사례 |
| --- | --- |
| [!UICONTROL 속성 설정] | 이 지표를 사용할 때 기본 속성 모델을 활성화합니다. 이 기본값은 [!UICONTROL 자유 형식 테이블] 또는 계산된 지표에서 재정의할 수 있습니다. |
| [!UICONTROL 속성 모델] | 사용할 기본 [속성 모델](/help/analysis-workspace/attribution/models.md)을 지정할 수 있습니다. 기본값은 [!UICONTROL 마지막 터치]입니다. 옵션은 마지막 터치, 첫 번째 터치, 선형, 참여, 동일한 터치, U자형, J 곡선, 역방향 J, 시간 지연, 맞춤형, 알고리즘입니다. 이러한 옵션 중 일부는 맞춤형 또는 시간 지연과 같이 채워야 하는 추가 필드를 만듭니다. 동일한 필드를 사용하여 여러 지표를 생성할 수 있습니다. 즉, [!UICONTROL 마지막 터치] 매출 지표 하나와 [!UICONTROL 첫 번째 터치] 매출 지표 하나를 가질 수 있지만 스키마의 매출 필드를 기준으로 합니다. |
| [!UICONTROL 전환 확인 기간] | 지표에 대한 기본 전환 확인 기간을 지정할 수 있습니다. 옵션은 [!UICONTROL 개인] (보고 기간), [!UICONTROL 세션], [!UICONTROL 사용자 지정]입니다. [!UICONTROL 사용자 지정]을 선택하면 [!UICONTROL Attribution IQ]와 마찬가지로 일/주/개월/등의 수(최대 90일)를 선택할 수 있는 옵션도 제공됩니다. 동일한 스키마 필드를 사용하여 여러 지표를 가질 수 있지만 각 지표에는 별도의 전환 확인 기간이 있습니다. |

{style=&quot;table-layout:auto&quot;}
