---
description: 행 설정은 테이블로 드래그한 구성 요소에 따라 다릅니다.
title: 행 설정
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 89%

---


# 행 설정

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 있습니다. 이 기능은 기존 Adobe Analytics의 [Analysis Workspace과 약간 다릅니다](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html). [추가 정보...](/help/getting-started/cja-aa.md)

행 설정은 테이블로 드래그한 구성 요소에 따라 다릅니다.

[테이블에서 작업을 마우스 오른쪽 단추로 클릭](/help/analysis-workspace/visualizations/freeform-table.md)하여 선택한 행을 관리할 수도 있습니다.

테이블 행 설정에 액세스하려면 이러한 각 항목 내에서 차원, 세그먼트, 지표, 기간 또는 분류 옆에 있는 [설정] 아이콘을 클릭합니다.

![](assets/row-settings.png)

| 행 설정 | 설명 |
|--- |--- |
| 날짜 비교 | 각 열의 날짜가 같은 행에서 모두 시작하도록 맞춥니다.   예: 날짜를 맞추도록 선택하면, 예를 들어, 2016년 10월과 9월 간에 월별 비교를 수행하는 경우 왼쪽 열이 10월 1일로 시작되고 오른쪽 열이 9월 1일로 시작됩니다.<br>기본적으로 비활성화되어 있습니다. |
| 백분율 | 행별 백분율 계산을 사용하면 자유 형식 테이블이 열 방향이 아니라 행 방향으로 셀 백분율을 계산합니다. 이 기능은 특히 트렌드 백분율에 유용하며, <br>시각화 아이콘을 사용할 때 기본적으로 사용됩니다. |
| 열 합계 | 이러한 설정은 [static rows](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL 현재 행의 합계를 합계로 표시]** - 테이블에서 행의 클라이언트측 합계를 보여 주므로 이것은 합계가 방문 또는 방문자와 같은 지표에 대한 중복 제거를 수행하지 **않음**&#x200B;을 의미합니다.</li><li>**[!UICONTROL 총계 표시]** - 서버측 합계를 보여 줍니다. 이것은 합계가 방문 또는 방문자와 같은 지표에 대한 중복 제거를 수행함을 의미합니다.</li></ul> |
| 분류 | **[!UICONTROL 위치별 분석]**: 자유 형식 테이블에서 고정 위치를 기반으로 분류를 수행할 수 있습니다. 예를 들어, 상위 7개 행이 항상 분류되도록 지정할 수 있습니다.<br>이전에는 분류에 있는 값 목록이 &quot;잠겨&quot;있었습니다. 이에 따라 페이지로 날짜를 분류한 경우 선택한 날짜 범위에 대해 상위 50페이지 목록이 표시되었습니다. 해당 보기를 저장하고 한 달 후 실행한 경우, 상위 50페이지가 변경되었을 것입니다. 하지만 Analysis Workspace에서는 원래의 분류로 인한 결과를 사용하여 동일한 페이지를 반환하긴 했지만, 현재 달을 날짜 범위로 사용했습니다.)<br>고정된 위치에 기반을 두고 분류를 수행하려면 다음을 수행합니다. 1. 테이블에서 행 일부를 분류합니다. 2. 고정된 위치에 지정할 테이블 행 옆에 있는 설정 (톱니바퀴) 아이콘을 클릭합니다. 3. [위치별 분류] 옆에 있는 확인란을 선택합니다. 4. 정렬 순서 또는 날짜 범위를 변경하고 분류가 하드코딩된 행이 아닌 행 위치에 연결되었는지 확인합니다.<br>기본적으로 비활성화되어 있습니다. |