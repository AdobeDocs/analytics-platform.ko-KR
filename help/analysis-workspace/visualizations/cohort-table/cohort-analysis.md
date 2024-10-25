---
title: 코호트 테이블 개요
description: Analysis Workspace에서 집단 분석에 집단 테이블을 사용하는 방법을 알아봅니다
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 590a3ddbe988d27341fe96a3fa866960d1641e24
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 37%

---

# 코호트 테이블 개요 {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_cohorttable_button"
>title="코호트 테이블"
>abstract="이벤트 완료를 기반으로 사용자를 그룹화하고 진행 중인 참여와 시간에 따른 이탈을 분석하는 코호트 시각화를 만듭니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_cohorttable_panel"
>title="코호트 테이블"
>abstract="이벤트 완료를 기반으로 사용자를 그룹화한 다음, 진행 중인 참여와 시간에 따른 이탈을 분석합니다.<br/><br/>**매개변수&#x200B;**<br/>**포함 기준**: 초기 방문자 코호트를 정의하는 데 사용되는 구성 요소입니다.<br/>**재방문 기준**: 방문자가 돌아왔는지 결정하는 데 사용되는 구성 요소입니다."

<!-- markdownlint-enable MD034 -->


*집단*&#x200B;은(는) 지정된 기간 동안 공통적인 특성을 공유하는 사람들의 그룹입니다. ![텍스트 번호](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 집단 테이블]** 시각화는 예를 들어 집단이 브랜드에 어떻게 참여하는지를 알려고 할 때 유용합니다. 트렌드 변경 사항을 쉽게 찾아 응답할 수 있습니다. ([!UICONTROL 집단 분석]에 대한 설명은 [집단 분석 101](https://ko.wikipedia.org/wiki/Cohort_analysis)에서와 같이 웹에서 사용할 수 있습니다.)

집단 보고서를 만들면 그 구성 요소(특정 차원, 지표 및 필터)를 조정한 다음, 모든 사람과 집단 보고서를 공유할 수 있습니다. [큐레이션 및 공유](/help/analysis-workspace/curate-share/curate.md)를 참조하십시오.

[!UICONTROL 집단 테이블]로 수행할 수 있는 작업의 예:

* 원하는 작업에 박차를 가할 수 있도록 설계된 캠페인 시작.
* 고객 라이프사이클에서 적시에 마케팅 예산 전환.
* 체험판이나 오퍼를 종료하여 가치를 극대화할 시점 인식.
* 가격 책정, 업그레이드 경로 등과 같은 분야에서 A/B 테스트를 하기 위한 아이디어 얻기.

[!UICONTROL 집단 테이블]은(는) [!UICONTROL Analysis Workspace]에 대한 액세스 권한이 있는 모든 Customer Journey Analytics 고객에 대해 사용할 수 있습니다.

+++ 코호트 테이블의 비디오 데모를 봅니다.

>[!VIDEO](https://video.tv.adobe.com/v/23990/?quality=12)

{{videoaa}}

+++

>[!IMPORTANT]
>
>[!UICONTROL 집단 분석]에서는 필터링할 수 없는 지표(계산된 지표 포함), 정수가 아닌 지표(매출액 등) 또는 발생 횟수를 지원하지 않습니다. 필터에 사용할 수 있는 지표만 [!UICONTROL 집단 분석]에서 사용할 수 있으며 한 번에 1씩만 증분할 수 있습니다.

## 집단 테이블 기능

다음 기능을 통해 생성 중인 집단에 대해 세밀하게 제어할 수 있습니다.

### [!UICONTROL 유지] 테이블

[!UICONTROL 유지] 집단 테이블은 개인을 반환합니다. 각 데이터 셀에는 해당 기간 동안 작업을 수행한 집단에 있는 사람들의 원시 수와 백분율 보여줍니다. 최대 3개의 지표와 10개의 필터를 포함할 수 있습니다.

![집단에 있는 사람의 수 및 비율을 보여 주는 Rention 집단 보고서.](assets/retention-report.png)

### [!UICONTROL 이탈] 테이블

[!UICONTROL Churn] 집단 테이블은 유지 테이블의 역버전이며 시간 경과에 따라 집단에 대한 반환 기준을 충족하지 않은 사람을 표시합니다. 최대 3개의 지표와 10개의 필터를 포함할 수 있습니다.

![집단에 대한 반환 기준을 충족하지 못한 사람의 수와 비율을 보여 주는 이탈 테이블입니다.](assets/churn-report.png)

### [!UICONTROL 순환 계산]

포함된 열이 아닌 이전 열을 기준으로 유지 또는 이탈을 계산할 수 있으며, 이를 순환 계산이라고 합니다.

![이전 데이터 열을 기반으로 한 계산을 보여 주는 집단 유지 보고서](assets/retention-report-rolling.png)

### [!UICONTROL 대기 시간] 테이블

지연 테이블은 포함 이벤트가 발생하기 전후에 경과된 시간을 측정합니다. 지연 시간 측정은 사전 및 사후 분석을 위한 탁월한 도구입니다. **[!UICONTROL 포함]** 열은 테이블의 중앙에 있으며 포함 이벤트 전후의 기간이 양쪽에 표시됩니다.

![이벤트 전후의 경과 시간을 표시하는 집단 보고서입니다.](assets/retention-report-latency.png)

### [!UICONTROL 사용자 지정 차원] 집단

(기본값인) 시간 기반 집단이 아니라 선택한 차원을 기반으로 집단을 생성할 수 있습니다. [!UICONTROL 도시 지역], [!UICONTROL 마케팅 채널], [!UICONTROL 캠페인], [!UICONTROL 제품], [!UICONTROL 페이지], [!UICONTROL 지역] 또는 다른 차원과 같은 차원을 사용하여 유지 변경 방법을 표시하십시오. 이러한 차원의 다양한 값을 기반으로 합니다.

![선택한 차원이 기본 시간 기반 집단이 아닌 사용자 지정된 보고서를 표시하는 집단 보고서.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[집단 테이블 구성](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>

