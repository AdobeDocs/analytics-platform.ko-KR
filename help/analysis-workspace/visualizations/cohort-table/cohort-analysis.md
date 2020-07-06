---
title: 집단 분석이란?
description: Analysis Workspace의 집단 분석에 대한 자세한 내용
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 45%

---


# What is [!UICONTROL Cohort Analysis]?

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 있습니다. 이 기능은 기존 Adobe Analytics의 [Analysis Workspace과 약간 다릅니다](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html). [추가 정보...](/help/getting-started/cja-aa.md)

*`cohort`*&#x200B;은 지정된 기간 동안 공통적인 특성을 공유하는 사람들의 그룹입니다. [!UICONTROL 집단 분석은 예를 들어 집단이 브랜드에 어떻게 참여하는지를 알려고 할 때 유용합니다. ] 트렌드 변경 사항을 쉽게 찾아 응답할 수 있습니다. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

집단 보고서를 만들면 그 구성 요소(특정 차원, 지표 및 세그먼트)를 조정한 다음, 모든 사람과 집단 보고서를 공유할 수 있습니다. [큐레이션 및 공유](/help/analysis-workspace/curate-share/curate.md)를 참조하십시오.

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* 원하는 작업에 박차를 가할 수 있도록 설계된 캠페인 시작.
* 고객 라이프사이클에서 적시에 마케팅 예산 전환.
* 가치를 최대화하기 위해 시험버전 또는 오퍼를 종료해야 하는 시기를 확인합니다.
* 가격 책정, 업그레이드 경로 등과 같은 분야에서 A/B 테스트를 하기 위한 아이디어 얻기.
* View a [!UICONTROL Cohort Analysis] report within a Guided Analysis report.

[!UICONTROL 집단 분석] 기능은 [!UICONTROL Analysis Workspace에 대한 액세스 권한이 있는 모든 Adobe Analytics 고객이 사용할 수 있습니다].

[집단 분석 - YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)(4:36)

>[!IMPORTANT]
>
>[!UICONTROL 집단 분석]
>
>은 필터링 가능한 지표가 아닌 지표(계산된 지표 포함), 정수가 아닌 지표(매출액 등) 또는 발생을 지원하지 않습니다. 세그먼트에서 사용할 수 있는 지표만
>[!UICONTROL 집단 분석], 한 번에 1씩만 증분할 수 있습니다.

## 집단 분석 기능

다음 기능을 통해 구축 중인 집단에 대해 세밀하게 제어할 수 있습니다.

### [!UICONTROL 유지 테이블]

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. 최대 3개의 지표와 10개의 세그먼트를 포함할 수 있습니다.

![](assets/retention-report.png)

### [!UICONTROL 이탈 테이블]

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. 최대 3개의 지표와 10개의 세그먼트를 포함할 수 있습니다.

![](assets/churn-report.png)

### [!UICONTROL 순환 계산]

포함된 열이 아니라 이전 열에 따라 유지 또는 이탈을 계산할 수 있습니다.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL 지연 테이블]

포함 이벤트가 발생한 이전 및 이후에 경과한 시간을 측정합니다. 이것은 이전/이후 분석을 위한 훌륭한 도구입니다. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL 사용자 지정 차원 집단]

기본값인 시간 기반 집단이 아닌 선택된 차원에 따라 집단을 생성합니다. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

집단 보고서를 설정하고 실행하는 방법에 대한 지침은 집단 분석 보고서 [구성으로 이동합니다](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

