---
description: Adobe은 사용할 수 있는 다양한 계산된 지표를 제공합니다. 이 페이지에는 이러한 지표와 그 사용 용도가 나열됩니다.
title: 기본 계산된 지표
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: a507417c945f827ebb8bc92f7b5f54a9c4e6faa0
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 9%

---

# 기본 계산된 지표

Customer Journey Analytics은 가장 일반적인 사용 사례를 다루기 위해 다음과 같은 기본 계산된 지표를 제공합니다. 이러한 Adobe 정의 기본 계산된 지표는 작은 ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) 로고로 식별됩니다. 이러한 지표를 빠르게 필터링하려면 [구성 요소 필터](/help/components/overview.md#filter)에서 ![레이블](/help/assets/icons/Label.svg) **[!UICONTROL Adobe 템플릿]**&#x200B;을(를) 선택하십시오.

| 계산된 지표 이름 | 설명<br/>수식 |
|---------|----------|
| **[!UICONTROL 세션 시작 비율]** | 세션의 첫 번째 이벤트에서 차원 항목이 발생한 비율입니다.<p>이 계산된 지표는 [데이터 보기](/help/data-views/create-dataview.md)에 [!UICONTROL 세션 시작] [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 Workspace에 자동으로 추가됩니다.</p>요약: **(** ![이벤트](/help/assets/icons/Event.svg) **세션 시작** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **세션** **)** |
| **[!UICONTROL 사용자당 체류 시간]** | 주어진 차원 항목에서 한 사용자가 소비한 평균 시간입니다.<p>이 계산된 지표는 [데이터 보기](/help/data-views/create-dataview.md)에서 [!UICONTROL 체류 시간(초)] [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 Workspace에 자동으로 추가됩니다. 세션의 마지막 이벤트 제외 필터가 사람 지표에 적용됩니다. 필터는 데이터 집합에 있는 각 세션의 마지막 이벤트를 제외합니다. 이 제외는 최종 작업 자체를 제외하면서 구매 또는 양식 제출과 같은 이벤트 또는 작업으로 이어지는 사용자 동작을 분석하는 데 도움이 될 수 있습니다.</p>요약: **(** ![이벤트](/help/assets/icons/Event.svg) **체류 시간(초)** ![나누기](/help/assets/icons/Divide.svg) ![세분화](/help/assets/icons/Segmentation.svg) **세션의 마지막 이벤트 제외(** ![이벤트](/help/assets/icons/Event.svg) **사람 )** |
| 사용자당 **[!UICONTROL 세션]** | 사용자당 평균 세션 수입니다.<p>요약: **(** ![이벤트](/help/assets/icons/Event.svg) **세션** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **사람** **)** |
| **[!UICONTROL 세션당 소비한 시간]** | 주어진 차원 항목에서 세션당 한 사용자가 소비한 평균 시간입니다.<p>이 계산된 지표는 [데이터 보기](/help/data-views/create-dataview.md)에서 [!UICONTROL 체류 시간(초)] [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 Workspace에 자동으로 추가됩니다. 세션의 마지막 이벤트 제외 필터가 세션 지표에 적용됩니다. 필터는 데이터 집합에 있는 각 세션의 마지막 이벤트를 제외합니다. 이 제외는 최종 작업 자체를 제외하면서 구매 또는 양식 제출과 같은 이벤트 또는 작업으로 이어지는 사용자 동작을 분석하는 데 도움이 될 수 있습니다.</p>요약: **(** ![이벤트](/help/assets/icons/Event.svg) **체류 시간(초)** ![나누기](/help/assets/icons/Divide.svg) ![세분화](/help/assets/icons/Segmentation.svg) **세션의 마지막 이벤트 제외(** ![이벤트](/help/assets/icons/Event.svg) **세션 )** |
| **[!UICONTROL 세션 종료 비율]** | 세션의 마지막 이벤트에서 차원 항목이 발생한 비율입니다. <p>이 계산된 지표는 [데이터 보기](/help/data-views/create-dataview.md)에 [!UICONTROL 세션 종료] [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 Workspace에 자동으로 추가됩니다.</p>요약: **(** ![이벤트](/help/assets/icons/Event.svg) **세션 종료** ![나누기](/help/assets/icons/Divide.svg) ![이벤트](/help/assets/icons/Event.svg) **세션** **)** |

{style="table-layout:auto"}
