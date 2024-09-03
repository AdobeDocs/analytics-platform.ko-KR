---
description: 요약 번호 및 변경 시각화를 사용하여 프로젝트의 중요 데이터 포인트를 표시할 수 있습니다.
title: 요약 번호 및 요약 변경 사항
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 61c1fe48ebe8ebff5b7104cebae1ce7b62289b7d
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 94%

---

# 요약 번호 및 요약 변경 사항

## 요약 번호 시각화 {#summary-number}

프로젝트에서 중요한 큰 숫자를 강조 표시하려면 요약 번호 시각화를 사용하십시오. 이 시각화는 다음과 같은 방식으로 동작합니다.

* 셀을 선택하지 않은 경우 열의 합계를 선택합니다.
* 단일 셀을 선택하면 해당 셀의 요약이 표시됩니다.
* 두 개 이상의 셀을 선택하면 선택한 첫 번째 셀이 표시됩니다.
* 열을 선택하면 열의 첫 번째 셀 값이 선택됩니다.

오른쪽 위에 있는 **시각화 설정** 톱니바퀴를 클릭하여 요약 번호 설정을 구성합니다.

| 설정 | 정의 |
|--- |--- |
| 백분율 | 숫자 대신 백분율을 표시합니다. |
| 범례 표시 | 표시된 지표에 대한 정보를 표시합니다. |
| 값 생략 | 값들을 축약하고 소수점 이하 최대 3자리를 표시하도록 선택합니다. |
| 다음을 기준으로 값 요약 | 선택한 데이터의 최대, 최소, 평균, 중간값 또는 합계를 표시하도록 선택합니다. |

{style="table-layout:auto"}

## 요약 변경 시각화 {#summary-change}

요약 변경 시각화를 사용하여 두 숫자 간의 델타(변화량)를 표시합니다.

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

이 시각화는 다음과 같은 방식으로 동작합니다.

* 셀을 선택하지 않으면 열의 처음 두 셀 값을 비교합니다.
* 하나의 셀을 선택하면 셀 값을 자신과 비교하기 때문에 0을 표시합니다.
* 두 개의 셀을 선택하면 처음 선택한 셀을 분자로, 두 번째 셀을 분모로 취합니다.
* 세 개 이상의 셀을 선택하면 처음 두 개만 비교합니다.
* 셀 범위를 선택하면 범위에서 선택한 첫 번째 셀과 마지막 셀을 비교합니다.
* 열을 선택하면 첫 번째 값과 자신을 비교하여 0이 표시됩니다.


![두 숫자 간의 델타를 보여 주는 요약 변경 시각화](assets/summary-change.png)


오른쪽 위에 있는 **시각화 설정** 톱니바퀴를 클릭하여 요약 변경 설정을 구성합니다.

| 설정 | 정의 |
|--- |--- |
| 백분율 | 숫자 대신 백분율을 표시합니다. |
| 범례 표시 | 표시된 지표에 대한 정보를 표시합니다. |
| 백분율 변경 표시 | 두 숫자 사이의 퍼센트 변화량을 표시합니다. |
| 원시 차이 표시 | 두 숫자 사이의 원시 차이를 표시합니다. 이 옵션을 사용하여 값들을 축약하고 소수점 이하 최대 3자리를 표시할 수도 있습니다. |
