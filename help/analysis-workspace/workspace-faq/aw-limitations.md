---
description: Adobe Analysis Workspace 및 관련 구성 요소의 알려진 제한 사항 목록
title: Analysis Workspace의 알려진 제한 사항
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 69%

---

# Analysis Workspace의 알려진 제한 사항

다음은 Analysis Workspace 및 관련 구성 요소의 알려진 제한 사항 목록입니다.

## 표

* 날짜 범위 또는 지표를 테이블의 행으로 사용하는 경우 날짜 비교 열을 추가할 수 없습니다.
* 필터가 표의 행으로 사용될 때 선택 항목에서 지표 만들기를 사용할 수 없습니다. 또한 선택 내용에서 지표 생성은 날짜 정렬 열에는 적용하지 않아야 합니다.
* 분류 행에 대한 조건부 서식은 사용자 지정 범위를 사용할 수 없습니다.
* 행 값을 합하여 합계 계산 설정이 적용될 때(일반적으로 정적 행 항목과 함께 사용) 테이블 합계 행에는 트렌드를 표시할 수 없습니다.
* [!UICONTROL 기여도 분석]은 [!UICONTROL 일별] 세부기간에서&#x200B;_만_ 실행할 수 있습니다. [!UICONTROL 시간별], [!UICONTROL 주별] 등 데이터에 대해서는 실행할 수 없습니다.

## 시각화

* [!UICONTROL 폴아웃], [!UICONTROL 흐름], [!UICONTROL 집단] 및 [!UICONTROL 막대 그래프]와 같은 필터를 활용하는 시각화는 계산된 지표를 입력으로 사용할 수 없습니다.
* [!UICONTROL 흐름]: 시작/종료 차원(예: [!UICONTROL 시작 페이지])은 흐름에서 사용할 수 없습니다.
* [!UICONTROL 집단]: 정수가 아닌 항목은 집단 기준으로 사용할 수 없습니다.

## 구성 요소 > 필터

* [!UICONTROL 발생], [!UICONTROL 고유 방문자] 등과 같이 특정 지표 및 차원을 필터링할 수 없습니다.
* [패널 드롭존](/help/analysis-workspace/c-panels/panels.md)에서 만든 임시 필터는 공개되지 않는 한 작업 공간 또는 필터 구성 요소 관리자의 왼쪽 레일에 나타나지 않습니다. 이 작업은 필터를 편집하고 **[!UICONTROL 이 필터를 공개하도록 선택합니다]**.

## 구성 요소 > 계산된 지표

* 계산된 지표는 특정 시각화에 사용할 수 없습니다. 위의 &#39;시각화&#39;를 참조하십시오.
* 계산된 지표 자체가 별도의 속성 모델을 포함할 수 있으므로 계산된 지표는 [!UICONTROL 속성] 패널에서 사용할 수 없습니다.
* 작업 공간에서 계산된 지표를 만드는 경우 특정 구성 요소 및 연산자를 사용할 수 없습니다(대신 [!UICONTROL 구성 요소 > 필터]에서 만드는 경우). 예를 들어 [!UICONTROL IP 주소]가 그렇습니다.

## 구성 요소 > 날짜 범위

* 사용자 지정 날짜 범위는 [!UICONTROL 지난해 이날], [!UICONTROL 지난달 이날] 등을 지원하지 않습니다.


## 구성 요소 > 보고서 설정

* [!UICONTROL 보고서 설정] 페이지의 일부 설정은 적용되지 않습니다. Analysis Workspace는 맨 아래에 있는 [!UICONTROL 언어/통화/인코딩] 설정인 [!UICONTROL 천 단위 구분 문자], [!UICONTROL 예약된 보고서 인코딩] 및 [!UICONTROL CSV 구분 문자]만 사용합니다.

## 속성 IQ

* 지표의 하위 세트는 [!UICONTROL 속성 IQ]에서 지원되지 않습니다. 전체 목록이 필요하면 [속성 IQ FAQ](../attribution/faq.md)를 참조하십시오.
