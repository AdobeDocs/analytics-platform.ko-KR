---
description: Analysis Workspace에서 집단을 만들고 집단 분석 보고서를 실행해 보십시오.
keywords: Analysis Workspace
title: 집단 분석 보고서 실행
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 73%

---


# Configure a [!UICONTROL Cohort Analysis] report

>[!NOTE] Customer Journey Analytics의 Analysis Workspace 설명서를 보고 있습니다. 이 기능은 기존 Adobe Analytics의 [Analysis Workspace과 약간 다릅니다](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html). [추가 정보...](/help/getting-started/cja-aa.md)

Create a cohort and run a [!UICONTROL Cohort Analysis] report in Analysis Workspace.

1. Analysis Workspace에서 왼쪽 레일의 **[!UICONTROL 시각화]** 아이콘을 클릭하고 **[!UICONTROL 집단 테이블]**&#x200B;을 캔버스로 드래그합니다.

   ![](assets/cohort-table.png)

1. 아래 표에 정의된 대로 **[!UICONTROL 포함 기준]**, **[!UICONTROL 반환 기준]**, **[!UICONTROL 집단 유형]** 및 **[!UICONTROL 설정]**&#x200B;을 정의합니다.

| 요소 | 설명 |
|--- |--- |
| **[!UICONTROL 포함 기준]** | 최대 10개의 포함 세그먼트와 3개의 포함 지표를 적용할 수 있습니다. 지표는 사용자를 집단에 배치하는 항목을 지정합니다. 예를 들어, 포함 지표가 주문이면, 집단 분석의 시간 범위 동안 주한 사용자는 초기 집단에 포함됩니다.<br>지표 간의 기본 연산자는 AND이지만 OR로 변경할 수 있습니다. 또한 이러한 지표에 숫자 필터링을 추가할 수 있습니다. 예를 들어, &quot;방문수 >= 1&quot;입니다.</br> |
| **[!UICONTROL 반환 기준]** | 최대 10개의 반환 세그먼트와 3개의 반환 지표를 적용할 수 있습니다. 지표는 사용자의 유지 또는 이탈 여부를 표시합니다. 예를 들어, 반환 지표가 [비디오 보기 횟수]일 경우, 그 다음 기간 동안 비디오를 본 사용자만(집단에 추가된 기간 후) [보존]으로 표현됩니다. 보존을 수량화하는 다른 지표는 [방문 횟수]입니다. |
| **[!UICONTROL 세부기간]** | 시간 세부기간 일, 주, 월, 분기 또는 년입니다. |
| **[!UICONTROL 유형]** | **[!UICONTROL 유지]**(기본값): 유지 집단은 방문자 집단이 시간이 지남에 따라 사용자의 자산으로 어떻게 반환되는지 측정합니다. 이것은 당사가 항상 보유하고 있는 표준 집단이며 사용자 행동의 반환과 반복을 나타냅니다. A [!UICONTROL Retention] Cohort is indicated by the color green in the table.<br>**[!UICONTROL 이탈&#x200B;]**: 이탈 집단은 방문자 집단이 시간이 지남에 따라 사용자의 자산에서 어떻게 이탈하는지 측정합니다. &quot;감소&quot; 또는 &quot;폴아웃&quot;이라고도 합니다. 이탈 = 1 - 유지입니다.[!UICONTROL 이탈은 고객이 다시 돌아오지 않는 빈도를 제시하여 기회와 고착성을 측정하는 좋은 방법입니다.]이탈을 사용하여 주안점을 두어야 할 영역을 분석 및 식별하여 어떤 집단군에 좀 더 주의를 기울여야 하는지 파악할 수 있습니다. A[!UICONTROL Churn]Cohort is indicated by the color red in the table (similar to fallout in our**[!UICONTROL  Flow ]**visualization).</br> |
| **[!UICONTROL 설정]** | **[!UICONTROL 순환 계산]**: 포함된 열(기본값)이 아닌 이전 열을 기준으로 보존 또는 이탈을 계산합니다. [!UICONTROL 롤링 계산은 &quot;반환&quot; 기간에 대한 계산 방법을 변경합니다. ] 일반적인 계산은 이전 기간 동안 해당 집단에 있었는지 여부에 관계없이 &quot;반환&quot; 기준을 충족하고 포함 기간에 해당하는 사용자를 개별적으로 찾습니다. Instead, [!UICONTROL Rolling Calculation] finds users who meet &quot;return&quot; criteria and were part of the previous period. Therefore, [!UICONTROL Rolling Calculation] filters and funnels the users who continually meet the &quot;return&quot; criteria period over period. [!UICONTROL 선택한 기간까지 이어지는 각 기간에 대해 반환 기준이 적용됩니다. ] </br><br>**[!UICONTROL 지연 표&#x200B;]**: 대기[!UICONTROL 시간]테이블은 포함 이벤트가 발생하기 전후의 경과 시간을 측정합니다.[!UICONTROL 지연은 이전/이후 분석 시 유용한 도구입니다.]For example, if you have an upcoming product or campaign launch and you want to track behavior before as well as see how it performs after, the[!UICONTROL Latency]table will display the pre and post behavior side by side to see the direct impact. The pre-inclusion cells in the[!UICONTROL Latency]Table are calculated by users who meet the[!UICONTROL Inclusion]criteria on the inclusion period and then meet the[!UICONTROL Return]criteria in the periods before the inclusion period. Note that[!UICONTROL Latency]tables and[!UICONTROL Custom Dimension]Cohort cannot be used together.</br><br>**[!UICONTROL 사용자 지정 차원 집단]**: 시간 기반 집단(기본값)이 아니라 선택한 차원을 기반으로 그룹을 생성합니다. 많은 고객이 시간 이외의 다른 항목으로 집단을 분석하기를 원하며 새로운 사용자 지정 차원 집단 기능은 자신이 선택한 차원을 기준으로 집단을 구축할 수 있는 유연성을 제공합니다. 마케팅 채널, 캠페인, 제품, 페이지, 영역 또는 Adobe Analytics의 다른 차원과 같은 차원을 사용하여 차원의 다양한 값을 기준으로 유지 변경 방법을 보여 줍니다. The [!UICONTROL Custom Dimension] Cohort segment definition applies the dimension item only as part of the inclusion period, not as part of the return definition.</br><br>[!UICONTROL 사용자 지정 차원 집단 선택 사항을 선택한 후 원하는 영역으로 차원을 드래그할 수 있습니다. ] 이를 통해 동일한 기간에 유사한 차원 항목을 비교할 수 있습니다. 예를 들어 도시의 성능, 상품, 캠페인 등을 나란히 비교할 수 있으며 이때 상위 14개의 차원 항목을 반환합니다. 그러나 필터(끌어다 놓은 차원의 오른쪽으로 마우스를 가져가면 액세스할 수 있음)를 사용하여 원하는 차원 항목만 표시할 수 있습니다. A [!UICONTROL Custom Dimension] Cohort cannot be used with the [!UICONTROL Latency] Table feature.</br> |

1. 톱니바퀴 아이콘을 클릭하여 **[!UICONTROL 집단 테이블 설정]**&#x200B;을 조정합니다.

| 설정 | 설명 |
| 백분율만 표시 | 숫자 값을 제거하고 백분율만 표시합니다. |
| 백분율 반올림 | 백분율 값을 소수 값으로 표시하지 않고 가장 가까운 정수로 반올림합니다. |
| 평균 백분율 행 표시 | 테이블의 맨 위에 새 행을 삽입한 다음 각 열 내의 값에 대한 평균을 추가합니다. |

## Build the [!UICONTROL Cohort Analysis] report

1. **[!UICONTROL 작성을 클릭합니다]**.

   ![단계 결과](assets/cohort-report.png)

   이 보고서는 주문(*`Included`* 열)을 수행한 방문자와 이후 방문 시 사이트로 돌아온 방문자를 보여줍니다. 시간이 지나면서 방문 횟수가 감소하면 문제를 발견하고 조치를 취할 수 있습니다.
1. (선택 사항) 선택 내용에서 세그먼트를 만듭니다.

   셀들(연속 또는 불연속)을 선택한 다음, 마우스 오른쪽 단추를 클릭 > **[!UICONTROL 선택 항목으로 세그먼트 만들기를 클릭합니다]**.

1. In the [Filter Builder](https://docs.adobe.com/content/help/ko-KR/analytics/components/segmentation/segmentation-workflow/seg-build.html), further edit the segment, then click **[!UICONTROL Save]**.

   저장된 세그먼트는 Analysis Workspace의 [!UICONTROL 세그먼트][!UICONTROL  패널에서 사용할 수 있습니다].
1. 집단 프로젝트에 이름을 지정하고 저장합니다.
1. (선택 사항) 프로젝트 구성 요소를 [큐레이션 및 공유](/help/analysis-workspace/curate-share/curate.md)합니다.

   >[!NOTE]
   >
   >큐레이션을 사용할 수 있으려면 먼저 프로젝트를 저장해야 합니다.

