---
description: Adobe는 다양한 계산된 지표를 사용할 수 있도록 제공합니다. 이 페이지에는 해당 지표와 그 용도가 나열되어 있습니다.
title: 계산된 지표 템플릿
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: c183a5013cbc5ff3765cc4926a308d0c4563a097
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 85%

---

# 계산된 지표 템플릿

Customer Journey Analytics은 가장 일반적인 사용 사례를 다루기 위해 다음과 같은 계산된 지표 템플릿을 제공합니다. Adobe에서 정의한 이러한 계산된 지표는 작은 ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) 로고로 식별할 수 있습니다. 이러한 지표를 빠르게 필터링하려면 ![구성 요소 필터](/help/assets/icons/Label.svg)에서 **[!UICONTROL 레이블]** [Adobe 템플릿](/help/components/overview.md#filter)을(를) 선택하십시오.

| 계산된 지표 이름 | 설명<br/>수식 |
|---------|----------|
| **[!UICONTROL 세션 시작 비율]** | 세션의 첫 번째 이벤트에서 차원 항목이 발생한 비율.<p>[데이터 보기](/help/data-views/create-dataview.md)에 [!UICONTROL 세션 시작] [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 자동으로 이 계산된 지표가 Workspace에 추가됩니다.</p>요약: **(** ![이벤트](/help/assets/icons/Event.svg) **세션 시작** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **세션** **)** |
| **[!UICONTROL 사용자당 소비한 시간]** | 주어진 차원 항목에서 한 사용자가 소비한 평균 시간.<p>[데이터 보기](/help/data-views/create-dataview.md)에 [!UICONTROL 소비한 시간(초)] [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 자동으로 이 계산된 지표가 Workspace에 추가됩니다. 세션의 마지막 이벤트 제외 세그먼트가 사람 지표에 적용됩니다. 세그먼트는 데이터 세트에 있는 각 세션의 마지막 이벤트를 제외합니다. 이렇게 하면 구매 또는 양식 제출과 같은 이벤트나 작업으로 이어지는 사용자 행동을 마지막 작업은 제외하고 분석할 수 있습니다.</p>요약: **(** ![이벤트](/help/assets/icons/Event.svg) **소비한 시간(초)** ![나누기](/help/assets/icons/Divide.svg) ![세분화](/help/assets/icons/Segmentation.svg) **세션의 마지막 이벤트 제외(** ![이벤트](/help/assets/icons/Event.svg) **사용자)** |
| **[!UICONTROL 사용자당 세션 수]** | 사용자당 평균 세션 수.<p>요약: **(** ![이벤트](/help/assets/icons/Event.svg) **세션** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **사용자** **)** |
| **[!UICONTROL 세션당 소비한 시간]** | 주어진 차원 항목에서 세션당 한 사용자가 소비한 평균 시간.<p>[데이터 보기](/help/data-views/create-dataview.md)에 [!UICONTROL 소비한 시간(초)] [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 자동으로 이 계산된 지표가 Workspace에 추가됩니다. 세션의 마지막 이벤트 제외 세그먼트가 세션 지표에 적용됩니다. 세그먼트는 데이터 세트에 있는 각 세션의 마지막 이벤트를 제외합니다. 이렇게 하면 구매 또는 양식 제출과 같은 이벤트나 작업으로 이어지는 사용자 행동을 마지막 작업은 제외하고 분석할 수 있습니다.</p>요약: **(** ![이벤트](/help/assets/icons/Event.svg) **소비한 시간(초)** ![나누기](/help/assets/icons/Divide.svg) ![세분화](/help/assets/icons/Segmentation.svg) **세션의 마지막 이벤트 제외(** ![이벤트](/help/assets/icons/Event.svg) **세션)** |
| **[!UICONTROL 세션 종료 비율]** | 세션의 마지막 이벤트에서 차원 항목이 발생한 비율. <p>[데이터 보기](/help/data-views/create-dataview.md)에 [!UICONTROL 세션 종료] [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 자동으로 이 계산된 지표가 Workspace에 추가됩니다.</p>요약: **(** ![이벤트](/help/assets/icons/Event.svg) **세션 종료** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **세션** **)** |
| **[!UICONTROL 웹 세션]** | 웹 사이트에서 발생한 세션의 수. |
| **[!UICONTROL 설문 조사 완료율]** | 설문 조사를 시작한 후 사람들이 이를 완료한 비율. |
| **[!UICONTROL 멀티 채널 세션 비율]** | 여러 채널(예: 웹 트래픽, 모바일 트래픽)이 포함된 세션과 단일 채널만 포함된 세션의 비율. |
| **[!UICONTROL 멀티 채널 사용자율]** | 여러 채널에 참여한 사람들과 단일 채널에만 참여한 사람들의 비율. |
| **[!UICONTROL 모바일 앱 세션]** | 모바일 앱에서 발생한 세션의 수. |
| **[!UICONTROL 웹+앱 교차 채널 세션]** | 웹 트래픽과 모바일 트래픽을 모두 포함하여 발생한 세션의 수. |
| **[!UICONTROL 통화 비용]** | 콜센터 통화에 드는 총 비용. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL 평균 통화 시간]** | 콜센터에 걸려온 전화 통화의 평균 시간. |
| **[!UICONTROL 통화당 평균 비용]** | 콜센터에 걸려온 전화 통화의 평균 비용. |
| **[!UICONTROL 평균 통화 설문 조사 점수]** | 콜센터에 걸려온 전화에 대한 평균 설문 조사 점수. |

{style="table-layout:auto"}
