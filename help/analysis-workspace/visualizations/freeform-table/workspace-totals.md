---
description: Analysis Workspace에서 자유 형식 테이블의 합계를 계산하는 방법을 알아봅니다.
title: 총계
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 91%

---

# 총계 {#workspace-totals}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="총 합계"
>abstract="정적 행이 있는 테이블 또는 분류에서는 총 합계가 지원되지 않습니다."


자유 형식 테이블에서 합계 행은 각 분류 수준에 나타나고 두 개의 합계를 표시할 수 있습니다.

![총 합계와 테이블 합계를 강조 표시한 자유 형식 테이블.](assets/total-row.png)

* **[!UICONTROL 테이블 합계]** ➊ - 이 합계는 일반적으로 [!UICONTROL 총계]와 같거나 그 하위 집합입니다. 합계는 [!UICONTROL 포함 내용 없음] 선택 사항을 포함하여 자유 형식 테이블 내에 적용된 테이블 세그먼트를 반영합니다.
* **[!UICONTROL 총계]**(**개 중**&#x200B;개 *개* 중 개) ➋ - 이 합계는 수집된 모든 이벤트를 나타냅니다. 세그먼트가 패널 수준에서 또는 자유 형식 테이블 내에서 적용되면 이 합계는 세그먼트 기준과 일치하는 모든 이벤트를 반영하도록 조정됩니다.




## 합계 표시

![설정](/help/assets/icons/Setting.svg) **[!UICONTROL 열 설정]** 아래에는 **[!UICONTROL 합계 표시]** 및 **[!UICONTROL 총 합계 표시]** 선택 사항이 있습니다. 이러한 설정을 선택하지 않으면 합계가 테이블에서 제거되어 합계가 의미가 없는 경우에 유용할 수 있습니다.


[정적 행](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) 합계는 별도로 동작하며 ![설정](/help/assets/icons/Setting.svg) **[!UICONTROL 행 설정]**&#x200B;을 사용하여 제어합니다.

| 옵션 | 설명 |
|---|---|
| **[!UICONTROL 현재 행의 합계를 총계로 표시]** | 테이블의 행에 대한 클라이언트측 합계를 표시합니다. 이 합계는 세션이나 개인 등의 지표를 중복 제거하지 **않습니다**. |
| **[!UICONTROL 총 합계 표시]** | 서버측 합계를 표시합니다. 이 합계는 세션이나 개인 등의 지표를 중복 제거합니다. |

[자유 형식 테이블의 동적 차원 항목과 정적 차원 항목 비교](column-row-settings/manual-vs-dynamic-rows.md)를 참조하십시오.


## 자주 묻는 질문

| 질문 | 답변 |
|---|---|
| 회색 열 비율은 어느 *합계*&#x200B;를 기반으로 합니까? | 이 *합계*&#x200B;는 **[!UICONTROL 행 설정]**&#x200B;의 **[!UICONTROL 백분율]** 설정 선택 사항에 따라 달라집니다.<ul><li>열별 백분율 계산 - 기본 설정입니다. 백분율은 테이블 합계를 기반으로 합니다.</li><li>행별 백분율 계산 - 백분율이 총계를 기반으로 합니다.</li></ul> |
| **[!UICONTROL “값 없음” 포함]** 설정은 합계에 어떤 영향을 줍니까? | **[!UICONTROL “값 없음” 포함]** 설정이 선택 취소되면 **[!UICONTROL 값 없음]** 행이 테이블, 테이블 합계에서 제거되고, [*합계* 지표 유형](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)을 사용하는 임의의 계산된 지표로 전달됩니다. |
| 사용자 정의 테이블 세그먼트가 자유 형식 테이블에 적용되는 경우 모든 계산된 지표 및 조건부 서식이 세그먼트를 처리합니까? | 현재 처리하지 않습니다. **[!UICONTROL “값 없음” 포함]**&#x200B;은 처리되지만 사용자 정의 테이블 세그먼트는 다음 항목에 영향을 미치지 않습니다.<ul><li>조건부 서식에서 사용하는 열 최대 / 최소 범위는 모든 데이터에 적용됩니다.</li><li>**[!UICONTROL 총 합계]** 지표 유형을 활용하는 계산된 지표.</li><li>자유 형식 테이블의 행들 간에 계산되는 열 합계, 열 최대값, 열 최소값, 카운트, 평균, 중간값, 백분위수, 사분위, 행 수, 표준 편차, 분산, 누적, 누적 평균, 회귀 변형, T 점수, T 테스트, Z 점수 및 Z 테스트와 같은 함수를 사용하는 계산된 지표.</li></ul> |
| 계산된 지표에서 **[!UICONTROL 총 합계]** 지표 유형은 무엇을 반영합니까? | **[!UICONTROL 총 합계]**&#x200B;는 **[!UICONTROL 총 합계]**&#x200B;를 계속 지칭하며 테이블이나 **[!UICONTROL 테이블 합계]**&#x200B;에 적용된 세그먼트를 반영하지 않습니다. |
| 데이터를 자유 형식 테이블에서 복사하여 붙여넣거나 CSV를 통해 다운로드할 때에는 어떤 합계가 표시됩니까? | 합계 행은 **[!UICONTROL 테이블 합계]**&#x200B;만 반영하며 **[!UICONTROL 합계 표시]** 열 설정을 준수합니다. |
