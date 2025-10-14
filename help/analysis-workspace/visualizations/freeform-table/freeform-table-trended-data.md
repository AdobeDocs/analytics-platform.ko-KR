---
description: Analysis Workspace에서 자유 형식 테이블에 대한 트렌드 데이터를 보는 방법에 대해 알아봅니다.
title: 자유 형식 테이블에 대한 트렌드 데이터 보기
feature: Freeform Tables
role: User, Admin
source-git-commit: 6ffc02c537a5e0b24edab34c87866d5c8413ae6f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# 자유 형식 테이블에 대한 트렌드 데이터 보기

자유 형식 테이블에 포함된 데이터의 추세를 볼 수 있습니다. 이 트렌드 데이터는 Analysis Workspace의 다음 영역에 표시됩니다.

* [스파크라인](#use-sparklines-to-view-trended-data)

* [선 시각화](#use-line-visualizations-to-view-trended-data)

## 스파크라인을 사용하여 트렌드 데이터 보기

스파크라인은 자유 형식 테이블의 지표 열 헤더에 표시됩니다.

자유 형식 테이블의 ![스파크라인](assets/table-sparkline.png)

스파크라인에는 항상 다음이 포함됩니다.

* 열의 모든 데이터에 대한 트렌드 데이터

* 테이블 차원에 적용되는 모든 검색 필터 조건

  자세한 내용은 [필터링 및 정렬](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)을 참조하세요.

## 라인 시각화를 사용하여 트렌드 데이터 보기

[줄](/help/analysis-workspace/visualizations/line.md) 시각화는 연결되어 있는 자유 형식 테이블의 데이터를 표시합니다.

### 자유 형식 테이블에 선 시각화 연결

선 시각화가 프로젝트에 추가된 방법 및 시기에 따라 원하는 자유 형식 테이블에 이미 연결되어 있을 수 있습니다. 다음 단계를 사용하여 확인하거나 수동으로 연결합니다.

1. Analysis Workspace 프로젝트에 라인 시각화를 추가합니다.

1. 시각화 이름 옆에 있는 점을 선택하고 **[!UICONTROL 데이터 소스]** 탭을 선택한 다음 선 시각화에 연결할 자유 형식 테이블의 이름을 선택합니다.

   ![자유 형식 테이블에 연결된 선 시각화](assets/table-line-viz.png)

### 선 시각화에 포함된 데이터 선택

자유 형식 테이블에서 선택한 셀에 따라 연결된 선 시각화에 포함된 데이터가 달라집니다.

자유 형식 테이블의 모든 데이터 추세를 보려면 자유 형식 테이블에서 스파크라인 셀을 선택합니다.

스파크라인 셀을 선택하면 셀이 진한 회색으로 표시됩니다.

![스파크라인 선택됨](assets/table-sparkline-selected.png)

연결된 테이블의 스파크라인 셀을 선택하면 선 시각화에 다음이 포함됩니다.

* 열의 모든 데이터에 대한 트렌드 데이터

* 테이블 차원에 적용되는 모든 검색 필터 조건

  자세한 내용은 [필터링 및 정렬](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)을 참조하세요.

연결된 테이블의 스파크라인을 선택하지 않으면 선 시각화는 다음을 포함합니다.

* 연결된 테이블에서 선택된 행의 데이터입니다. 행을 선택하지 않으면 연결된 테이블의 첫 번째 차원에 대한 데이터만 표시됩니다.

* 테이블 차원에 적용된 모든 검색 필터 기준은 무시됩니다

  자세한 내용은 [필터링 및 정렬](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)을 참조하세요.


## 연결된 라인 시각화에 필터 기준 포함

연결된 선 시각화에 필터 기준이 포함되는 시기에 대한 자세한 내용은 [스파크라인 및 선 시각화의 트렌드 데이터에 필터 기준 포함](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#include-filter-criteria-in-trended-data-in-sparklines-and-line-visualizations)을 참조하십시오.

