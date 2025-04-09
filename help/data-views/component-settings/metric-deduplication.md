---
title: 지표 중복 제거 구성 요소 설정
description: 보고서에서 첫 번째 지표 발생 횟수만 계산합니다.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: af88be97f303095129177b2132c6711c648cea34
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 82%

---

# 지표 중복 제거 구성 요소 설정 {#metric-deduplication-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_deduplication"
>title="지표 중복 제거"
>abstract="반복되지 않는 값만 계산하도록 지표를 구성하십시오."

<!-- markdownlint-enable MD034 -->


지표 중복 제거를 통해 반복되지 않는 값만 계산하도록 지표를 구성할 수 있습니다.

![Metric deduplication](../assets/metric-deduplication.png)

| 설정 | 설명 |
| --- | --- |
| [!UICONTROL 지표 중복 제거] | 지표 중복 제거를 활성화할 수 있는 확인란입니다. 기본적으로 비활성화되어 있습니다. |
| [!UICONTROL 중복 제거 범위] | 각 확인이 뒤로 이동하는 거리를 결정할 수 있습니다.<br/>**[!UICONTROL 전역 계정&#x200B;]**: 보고 기간의 첫 번째 지표 발생 횟수만을 계산합니다.<br/>**[!UICONTROL 계정]**: 보고 기간의 첫 번째 지표 발생 횟수만을 계산합니다.<br/>**[!UICONTROL 기회&#x200B;]**: 보고 기간의 첫 번째 지표 발생 횟수만을 계산합니다.<br/>**[!UICONTROL 구매 그룹]**: 보고 기간의 첫 번째 지표 발생 횟수만을 계산합니다.<br/>**[!UICONTROL 개인&#x200B;]**: 보고 기간의 첫 번째 지표 발생 횟수만 계산합니다.<br>**[!UICONTROL 세션]**: 세션의 첫 번째 지표 발생 횟수만 계산됩니다.<br> |
| [!UICONTROL 중복 제거 ID] | 지표 자체의 중복 제거를 적용하는 대신 차원을 기반으로 지표 중복 제거를 적용할 수 있습니다. 중복 제거를 적용하는 구매 ID와 같은 차원에 유용합니다. |
| [!UICONTROL 유지할 값] | <ul><li>**첫 번째 인스턴스 유지**: 지표의 초기 인스턴스가 유효한 경우에 사용합니다. 가장 일반적인 것은 구매 확인입니다. 사용자가 의도치 않게 페이지를 다시 로드하고 다른 구매 확인 인스턴스를 받더라도 초기 이벤트는 유효합니다.</li><li>**마지막 인스턴스 유지**: 마지막 인스턴스를 수집하는 것이 보다 적합한 상황에서 사용합니다. 예: 사용자가 자신의 온라인 프로필을 업데이트합니다. 세션당 이러한 업데이트 중 하나만 카운트됩니다. 그러나 사용자가 세션 중에 프로필을 여러 번 업데이트할 수 있습니다. 첫 번째 인스턴스를 유지하는 경우 이벤트와 연결되지 않는 활동이 있을 수 있습니다. 이 경우 마지막 인스턴스를 유지하는 것이 보다 합리적입니다.</li></ul> |

{style="table-layout:auto"}

>[!CAUTION]
>
>_개인_ 범위의 중복 제거는 UTC 시간으로 전체 월 단위로 평가됩니다. 첫 번째 또는 마지막 인스턴스가 전체 월 이내이지만 보고 일자 외에 발생한 경우 모든 첫 번째 또는 마지막 인스턴스가 부분 월 보고 기간에 표시되지 않을 수 있습니다.
