---
description: Adobe은 사용할 수 있는 다양한 계산된 지표를 제공합니다. 이 페이지에는 이러한 지표와 그 사용 용도가 나열됩니다.
title: 기본 계산된 지표
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 28%

---

# 기본 계산된 지표

Customer Journey Analytics은 가장 일반적인 사용 사례를 다루기 위해 다음과 같은 계산된 지표를 제공합니다.

| 계산된 지표 이름 | 설명 | 공식 |
|---------|----------|---------|
| 세션 시작 비율 | 세션의 첫 번째 이벤트에서 차원 항목이 발생한 비율입니다.<p>이 계산된 지표는 [데이터 보기](/help/data-views/create-dataview.md)에 `[Session Starts]` [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 Workspace에 자동으로 추가됩니다.</p> | `[Session Starts] / [Sessions]` |
| 사용자당 소비한 시간 | 주어진 차원 항목에서 한 사용자가 소비한 평균 시간입니다.<p>이 계산된 지표는 [데이터 보기](/help/data-views/create-dataview.md)에 `[Time Spent (seconds)]` [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 Workspace에 자동으로 추가됩니다.</p> | `[Time Spent (seconds)] / [Users]` |
| 사용자당 세션 수 | 사용자당 평균 세션 수입니다. | `[Sessions] / [Users]` |
| 세션당 소비한 시간 | 주어진 차원 항목에서 세션당 한 사용자가 소비한 평균 시간입니다.<p>이 계산된 지표는 [데이터 보기](/help/data-views/create-dataview.md)에 `[Time Spent (seconds)]` [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 Workspace에 자동으로 추가됩니다.</p> | `[Time Spent (seconds)] / [Sessions]` |
| 세션 종료 비율 | 세션의 마지막 이벤트에서 차원 항목이 발생한 비율입니다. <p>이 계산된 지표는 [데이터 보기](/help/data-views/create-dataview.md)에 `[Session Ends]` [표준 구성 요소](/help/data-views/component-reference.md)를 포함할 때 Workspace에 자동으로 추가됩니다.</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
