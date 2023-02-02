---
title: 지표 중복 제거 구성 요소 설정
description: 보고서에서 첫 번째 지표 발생 횟수만을 계산합니다.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e2ebda486eae7740351370f48bdf104c90494ae3
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 75%

---

# 지표 중복 제거 구성 요소 설정

지표 중복 제거를 통해 지표가 값만을 비반복적으로 계산하도록 구성할 수 있습니다.

| 설정 | 설명 |
| --- | --- |
| [!UICONTROL 지표 중복 제거] | 지표 중복 제거를 활성화할 수 있는 확인란입니다. 기본적으로 비활성화되어 있습니다. |
| [!UICONTROL 중복 제거 범위] | 각 확인이 뒤로 이동하는 거리를 결정할 수 있습니다.<br>**세션**: 첫 번째 지표 발생 횟수만을 계산합니다.<br>**개인**: 보고 기간의 첫 번째 지표 발생 횟수만을 계산합니다. |
| [!UICONTROL 중복 제거 ID] | 지표 자체의 중복 제거를 적용하는 대신 차원을 기반으로 지표 중복 제거를 적용할 수 있습니다. 중복 제거를 적용하는 구매 ID와 같은 차원에 유용합니다. |

{style=&quot;table-layout:auto&quot;}

>[!CAUTION]
>
>   데이터 중복 제거 _개인_ 범위는 UTC 시간으로 전체 월별로 평가됩니다. 일부 인스턴스가 전체 달 내 및 보고 날짜 외부에서 발생한 경우 부분적인 달 보고 기간 내에 모든 첫 번째 또는 마지막 인스턴스를 표시하지 않을 수 있습니다.
