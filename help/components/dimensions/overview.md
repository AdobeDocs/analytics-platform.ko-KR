---
title: 차원 개요
description: 차원의 의미와 Customer Journey Analytics에서 차원을 사용하는 방법을 알아봅니다
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 36%

---

# 차원 개요

Dimension은 데이터를 분석하는 데 사용되는 Customer Journey Analytics의 구성 요소 유형입니다. 예를 들어 [Analysis Workspace](/help/analysis-workspace/home.md) 또는 [Report Builder](/help/report-builder/report-buider-overview.md)에서 보고서를 작성할 때 차원을 사용합니다.

Customer Journey Analytics 차원은 무제한 유형입니다. 값은 숫자, 텍스트, 객체, 목록 또는 모든 것의 조합일 수 있습니다.

Customer Journey Analytics의 기본 보고서는 지표 열(일반적으로 숫자 값)에 대해 차원의 행(일반적으로 문자열 값)을 보여줍니다.

예를 들어 페이지 차원을 사람 지표와 결합하면 사람들이 가장 많이 방문한 페이지를 보여주는 등급 보고서가 만들어집니다.

| 페이지 | 사용자 |
| --- | ---: |
| 홈 페이지 | 800 |
| 제품 페이지 | 500 |
| 구매 페이지 | 100 |

{style="table-layout:fixed"}

각 차원은 사이트의 다른 부분 또는 측면을 나타냅니다. 이러한 차원 중 하나 이상을 하나 이상의 지표와 결합하여 원하는 보고서를 만들 수 있습니다.


## 차원 만들기

Customer Journey Analytics 관리자는 [데이터 보기 내에서 차원을 만들 수 있습니다](/help/data-views/create-dataview.md#components).

## 기본 차원

데이터 보기를 생성하면 기본적으로 다음 시간 기반 구성 요소가 데이터 보기에 차원으로 추가됩니다.

- 15분
- 30분
- 5분
- 일
- 날짜(월 기준)
- 요일
- 일(한 해 기준)
- 시간
- 시간 (일 기준)
- 분
- 분/시간
- 월
- 월 (연 기준)
- 분기
- 사분기
- 초
- 주(한 해 기준)
- 년

## 차원 설명 추가

Customer Journey Analytics 관리자는 데이터 보기 내에서 또는 Analysis Workspace 내에서 직접 차원 및 기타 구성 요소에 대한 설명을 추가할 수 있습니다. 차원에 설명을 추가하는 방법에 대한 자세한 내용은 [구성 요소 설명 추가](/help/components/add-component-descriptions.md)를 참조하십시오.
