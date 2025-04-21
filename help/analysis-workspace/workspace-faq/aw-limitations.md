---
description: Adobe Analysis Workspace 및 관련 구성 요소의 알려진 제한 사항에 대해 알아보기
title: Analysis Workspace의 알려진 제한 사항
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
source-git-commit: b14bc43a0cdf4901c5df171a116943beb2124991
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 73%

---

# Analysis Workspace의 알려진 제한 사항

다음은 Analysis Workspace 및 관련 구성 요소의 알려진 제한 사항 목록입니다.

## 테이블

* 날짜 범위 또는 지표를 테이블의 행으로 사용하는 경우 날짜 비교 열을 추가할 수 없습니다.
* 세그먼트가 테이블의 행으로 사용되는 경우 선택 내용에서 지표 생성이 비활성화됩니다. 또한 선택 내용에서 지표 생성은 날짜 정렬 열에는 적용하지 않아야 합니다.
* 분류 행에 대한 조건부 서식은 사용자 정의 범위를 사용할 수 없습니다.
* 행 값을 합하여 합계 계산 설정이 적용될 때(일반적으로 정적 행 항목과 함께 사용) 테이블 합계 행에는 트렌드를 표시할 수 없습니다.

## 시각화

* [!UICONTROL 폴아웃], [!UICONTROL 흐름], [!UICONTROL 집단] 및 [!UICONTROL 히스토그램]과 같이 세그먼트를 활용하는 시각화는 계산된 지표를 입력으로 허용할 수 없습니다.
* [!UICONTROL 흐름]: 시작/종료 차원(예: [!UICONTROL 시작 페이지])은 흐름에서 사용할 수 없습니다.
* [!UICONTROL 코호트]: 정수가 아닌 항목은 코호트 기준으로 사용할 수 없습니다.

## 세그먼트

* 특정 지표 및 차원은 세그먼트화할 수 없습니다(예: [!UICONTROL 이벤트], [!UICONTROL 개인] 등).
* [패널 드롭 영역](/help/analysis-workspace/c-panels/panels.md)에서 만든 임시 세그먼트는 빠른 세그먼트의 유형입니다. 이러한 구성 요소는 공개하지 않으면 Workspace 또는 세그먼트 관리자의 왼쪽 패널에 표시되지 않습니다. 자세한 내용은 [빠른 세그먼트](/help/components/filters/quick-filters.md)를 참조하십시오.

## 계산된 지표

* 계산된 지표는 특정 시각화에 사용할 수 없습니다. [시각화](#visualizations)를 참조하십시오.
* 계산된 지표 자체가 별도의 속성 모델을 포함할 수 있으므로 계산된 지표는 [!UICONTROL 속성] 패널에서 사용할 수 없습니다.
* 계산된 지표가 Workspace에서 만들어지는 경우([!UICONTROL 구성 요소 > 세그먼트]에서 만드는 것이 아니라) 특정 구성 요소 및 연산자를 사용할 수 없습니다. 예를 들어 [!UICONTROL IP 주소]가 그렇습니다.

## 날짜 범위

* 사용자 정의 날짜 범위는 [!UICONTROL 지난해 이날], [!UICONTROL 지난달 이날] 등을 지원하지 않습니다.


## 보고서 설정

* [!UICONTROL 보고서 설정] 페이지의 일부 설정은 적용되지 않습니다. Analysis Workspace는 맨 아래에 있는 [!UICONTROL 언어/통화/인코딩] 설정인 [!UICONTROL 천 단위 구분자], [!UICONTROL 예약된 보고서 인코딩] 및 [!UICONTROL CSV 구분자]만 사용합니다.

