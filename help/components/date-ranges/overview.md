---
description: 달력 및 데이터 범위를 사용하여 Analysis Workspace에서 날짜 범위를 지정합니다.
title: 날짜 범위 개요
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 96%

---

# 날짜 범위 개요

Workspace 프로젝트에서는 일반적으로 [패널의 캘린더](/help/analysis-workspace/c-panels/panels.md#calendar)를 사용하여 해당 패널의 시각화 날짜 범위를 지정합니다.

날짜 범위 구성 요소를 사용하면 패널의 캘린더 설정을 정의할 수 있습니다.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## 날짜 범위 사용

날짜 범위 구성 요소를 사용하여 패널의 캘린더를 다시 정의할 수 있습니다.

또는 자유 형식 테이블의 날짜 범위를 지표나 차원으로 사용할 수 있습니다.

![날짜 범위 사용](/help/components/date-ranges/assets/date-ranges-usage.png)

- **지표**. 예를 들어 특정 지표에 대해 두 달 간의 차원을 비교합니다.
- **차원**. 날짜 범위 차원에 대해 다양한 차원 항목의 지표를 비교합니다.

>[!NOTE]
>
>자유 형식 테이블에서 날짜 범위를 사용하는 경우, 해당 날짜 범위는 자유 형식 테이블이 속한 패널에 지정된 캘린더보다 우선합니다.
>

날짜 범위는 [모든 구성 요소를 사용](/help/components/overview.md#analysis-workspace-components)하는 것과 같은 방식으로 사용합니다. ![캘린더](/help/assets/icons/Calendar.svg) **[!UICONTROL 날짜 범위]** 구성 요소 패널에서 날짜 범위를 끌어서 다음 위치에 구성 요소를 놓습니다.

- **[!UICONTROL 캘린더]**: 현재 캘린더 구성을 날짜 범위로 ![전환](/help/assets/icons/Switch.svg) **[!UICONTROL 대체]**&#x200B;합니다.
- **지표 열 머리글**: 지표를 ![전환](/help/assets/icons/Switch.svg) **[!UICONTROL 대체]**&#x200B;하거나 지표로 날짜 범위를 ![추가](/help/assets/icons/Add.svg)**[!UICONTROL 추가&#x200B;]**하거나 지표를 날짜 범위 구성 요소를 사용하여 지표를 ![필터](/help/assets/icons/Filter.svg)**[!UICONTROL &#x200B;필터링&#x200B;]**합니다.
- **차원 열 머리글**: 현재 차원을 ![전환](/help/assets/icons/Switch.svg) **[!UICONTROL 대체]**&#x200B;합니다. 새로운 차원은 이제 **[!UICONTROL 날짜 범위]**&#x200B;입니다. 차원이 날짜 범위이면 차원 항목으로 날짜 범위를 ![추가](/help/assets/icons/Add.svg)**[!UICONTROL 추가&#x200B;]**할 수 있습니다.
- **차원 항목**: 날짜 범위에 따라 특정 차원 항목을 ![분류](/help/assets/icons/Breakdown.svg) **[!UICONTROL 분류]**&#x200B;합니다.

자유 형식 테이블 시각화에 날짜 범위 열을 직접 추가할 수도 있습니다.

1. 지표 열의 컨텍스트 메뉴에서 선택합니다.

   - **[!UICONTROL 기간 열 추가]**. 현재 캘린더를 기반으로 제안된 옵션 중에서 선택하거나 [사용자 정의 날짜 범위](#custom-date-ranges)를 만들 수 있습니다.
   - **[!UICONTROL 기간 비교]**. 현재 캘린더를 기반으로 제안된 옵션 중에서 선택하거나 [사용자 정의 날짜 범위](#custom-date-ranges)를 만들 수 있습니다.

1. 선택에 따라 날짜 범위 열이 자유 형식 테이블에 추가됩니다.

## 기본 날짜 범위

Analysis Workspace는 다양한 기본 날짜 범위를 제공합니다.


| 일 | 주 | 월 | 분기 | 년 |
|---|---|---|---|---|
| 오늘 | 이번 주 | 이번 달 | 이번 분기 | 올해 |
| 어제 | 이번 주 (오늘 제외) | 이번 달 (오늘 제외) | 이번 분기 (오늘 제외) | 올해 (오늘 제외) |
| 2일 전 | 2주 전 | 2개월 전 |   |  |
| 3일 전 | 3주 전 | 3개월 전 |  | |
| 지난 7일 | 지난주 | 지난 달 | 지난 분기 | 지난 해 |
| 지난 14일 | 최근 2주 전체 | 최근 2개월 전체 | 지난 4분기 전체 | |
| 지난 30일 | 최근 3주 전체 | 최근 3개월 전체 | | |
| 지난 60일 | 최근 4주 전체 | 최근 6개월 전체 | | |
| 지난 90일 | 최근 12주 전체 | 최근 12개월 전체 | | |
| 지난 7일 전체 | 최근 52주 전체 | 최근 13개월 전체 | | |
| 지난 14일 전체 | | | | |
| 지난 30일 전체 | | | | |
| 지난 90일 전체 | | | | |

<table style="table-layout:fixed">

## 사용자 정의 날짜 범위

고유한 사용자 정의 날짜 범위를 만들 수 있습니다. 날짜 범위를 만들 수 있는 다양한 옵션은 [날짜 범위 만들기](/help/components/date-ranges/create.md)를 참조하십시오. 그런 다음 [날짜 범위 빌더](create.md#date-range-builder)에 날짜 범위를 작성, 수정 및 저장합니다.

[날짜 범위 관리자](manage.md)를 사용하여 날짜 범위를 관리합니다.
