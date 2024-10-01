---
title: 날짜 범위 개요
description: 날짜 범위가 무엇인지, 보고 시 사용할 수 있는 방법을 알아봅니다.
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 12%

---

# 날짜 범위 개요

Workspace 프로젝트에서는 일반적으로 패널의 [달력](/help/analysis-workspace/c-panels/panels.md#calendar)을 사용하여 해당 패널의 시각화에 대한 날짜 범위를 지정합니다.

날짜 범위 구성 요소를 사용하여 패널의 달력 설정을 정의하고 재정의할 수 있습니다.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## 날짜 범위 사용

날짜 범위 구성 요소를 사용하여 패널의 달력을 재정의할 수 있습니다.

또는 자유 형식 테이블의 날짜 범위를 지표 또는 차원으로 사용할 수 있습니다.

![날짜 범위 사용](/help/components/date-ranges/assets/date-ranges-usage.png)

- **지표**. 예를 들어 특정 지표에 대해 서로 다른 두 달의 차원을 비교하려면 다음 작업을 수행하십시오.
- **Dimension**. 날짜 범위 차원에 대한 다른 차원 항목에서 지표를 비교하려면 다음 작업을 수행하십시오.

>[!NOTE]
>
>자유 형식 테이블에서 날짜 범위를 사용하는 경우 날짜 범위는 자유 형식 테이블이 속한 패널에 지정된 달력보다 우선 적용됩니다.
>

[모든 구성 요소를 사용](/help/components/overview.md#analysis-workspace-components)하는 것처럼 날짜 범위를 사용합니다. ![캘린더](/help/assets/icons/Calendar.svg) **[!UICONTROL 날짜 범위]** 구성 요소 패널에서 날짜 범위를 드래그하고 다음 위치에 구성 요소를 놓습니다.

- **[!UICONTROL 일정]**: 현재 일정 구성을 날짜 범위로 ![전환](/help/assets/icons/Switch.svg) **[!UICONTROL 바꾸기]**&#x200B;합니다.
- **지표 열 헤더**: 지표를 ![전환](/help/assets/icons/Switch.svg) **[!UICONTROL 바꾸기]**, 날짜 범위를 지표로 ![추가](/help/assets/icons/Add.svg)**[!UICONTROL 추가&#x200B;]**또는 날짜 범위 구성 요소를 사용하여 지표를 ![필터링](/help/assets/icons/Filter.svg)**[!UICONTROL &#x200B;필터링&#x200B;]**합니다.
- **Dimension 열 헤더**: 현재 차원을 ![전환](/help/assets/icons/Switch.svg) **[!UICONTROL 바꾸기]**&#x200B;합니다. 이제 새 차원이 **[!UICONTROL 날짜 범위]**&#x200B;입니다. 차원이 날짜 범위이면 차원 항목으로 ![추가](/help/assets/icons/Add.svg)**[!UICONTROL 추가&#x200B;]**할 수 있습니다.
- **Dimension 항목**: 날짜 범위별로 특정 차원 항목을 ![분류](/help/assets/icons/Breakdown.svg) **[!UICONTROL 분류]**&#x200B;합니다.

자유 형식 테이블 시각화에서 직접 날짜 범위 열을 추가할 수도 있습니다.

1. 지표 열의 컨텍스트 메뉴에서 을(를) 선택합니다.

   - **[!UICONTROL 기간 열 추가]**. 현재 달력을 기반으로 하는 권장 옵션 중에서 선택하거나 [사용자 지정 날짜 범위](#custom-date-ranges)를 만들 수 있습니다.
   - **[!UICONTROL 기간 비교]**. 현재 달력을 기반으로 하는 권장 옵션 중에서 선택하거나 [사용자 지정 날짜 범위](#custom-date-ranges)를 만들 수 있습니다.

1. 선택한 항목에 따라 추가 날짜 범위 열이 자유 형식 테이블에 추가됩니다.

## 기본 날짜 범위

Analysis Workspace은 다양한 기본 날짜 범위를 제공합니다.


| 일 | 주 | 월 | 분기 | 년 |
|---|---|---|---|---|
| 오늘 | 이번 주 | 이번 달 | 이번 분기 | 올해 |
| 어제 | 이번 주 (오늘 제외) | 이번 달 (오늘 제외) | 이번 분기 (오늘 제외) | 올해 (오늘 제외) |
| 2일 전 | 2주 전 | 2개월 전 |   |  |
| 3일 전 | 3주 전 | 3개월 전 |  | |
| 지난 7일 | 지난주 | 지난 달 | 지난 분기 | 작년 |
| 지난 14일 | 지난 2주 전체 | 지난 2달 | 지난 4분기 | |
| 지난 30일 | 지난 3주 | 지난 3달 | | |
| 지난 60일 | 지난 4주 | 지난 6개월 | | |
| 지난 90일 | 지난 12주 | 지난 12달 | | |
| 지난 7일 전체 | 지난 52주 전체 | 지난 13개월 | | |
| 지난 14일 전체 | | | | |
| 지난 30일 전체 | | | | |
| 지난 90일 전체 | | | | |

<table style="table-layout:fixed">

## 사용자 정의 날짜 범위

사용자 지정 날짜 범위를 만들 수 있습니다. 날짜 범위를 만드는 데 사용할 수 있는 다양한 옵션은 [날짜 범위 만들기](/help/components/date-ranges/create.md)를 참조하십시오. 그런 다음 [날짜 범위 빌더](create.md#date-range-builder)에서 날짜 범위를 빌드, 수정 및 저장합니다.

날짜 범위를 관리하려면 [날짜 범위 관리자](manage.md)를 사용합니다.
