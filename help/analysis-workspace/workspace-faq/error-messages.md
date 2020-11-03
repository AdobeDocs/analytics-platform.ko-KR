---
description: Analysis Workspace 및 관련 구성 요소의 오류 메시지 목록
title: 오류 메시지
translation-type: tm+mt
source-git-commit: a991dce6abaf90cbca06de75606a2517cb5b6484
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 35%

---


# 오류 메시지

Analysis Workspace과 상호 작용할 때 오류가 발생할 수 있으며 이는 성과에도 영향을 줍니다. 다음은 가장 일반적인 오류 유형, 오류 발생 이유 및 최적화할 수 있는 최적화 유형입니다.

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 계십니다. 이 기능은 [기존 Adobe Analytics의 Analysis Workspace](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html)와 약간 다릅니다. [추가 정보...](/help/getting-started/cja-aa.md)

| 오류 메시지 | 왜 이 오류가 발생하는가? | 최적화 |
| --- | --- | --- |
| [!UICONTROL 시스템 오류가 발생했습니다. 고객 지원 센터 요청을 **[!UICONTROL 도움말 > 지원 티켓 제출]** 및 오류 코드를 포함합니다.] | Adobe에서 해결해야 하는 문제가 발생했습니다. | 오류 코드를 고객 지원 센터에 제출합니다. |
| [!UICONTROL 오류 500:페이지를 로드하지 못했습니다.] | 회사 등의 로컬 네트워크 문제 [방화벽 설정](https://docs.adobe.com/content/help/en/analytics/technotes/ip-addresses.html), is a contributing factor to this error. 또한 Adobe에 해결해야 하는 문제가 발생할 수 있습니다. | 몇 분 후에 다시 로그인하십시오. 문제가 지속되면 EIM 인스턴스 ID 코드를 고객 지원 센터에 제출합니다. |
| [!UICONTROL 세그먼트 중 하나 또는 이 시각화의 검색에는 너무 많은 결과를 반환하는 텍스트 검색이 포함되어 있습니다.] | 세그먼트 기준이나 보고서 필터가 너무 넓습니다. | 검색 텍스트 기준을 좁히고 요청을 다시 시도하십시오. |
| [!UICONTROL 보고서 세트에 비정상적으로 많은 보고가 발생했습니다. 나중에 다시 시도하십시오.] | 조직에서 특정 보고서 세트에 대해 너무 많은 동시 요청을 실행하려고 합니다. 이 오류에 기여하는 요소는 API 요청, 예약된 프로젝트, 예약된 보고서, 예약된 경고 및 보고 요청을 수행하는 동시 사용자입니다. | 보고서 세트에 대한 요청과 일정을 하루 종일 더 균등하게 분산합니다. |
| [!UICONTROL 요청이 너무 복잡합니다.] | 보고 요청이 너무 커서 실행할 수 없습니다. 이 오류에 기여하는 요소는 요청의 크기로 인한 시간 초과, 세그먼트 또는 검색 필터에 일치하는 항목이 너무 많음, 포함된 지표가 너무 많음, 호환되지 않는 차원과 지표 조합 등입니다. | 테이블의 일부 열 또는 행을 제거하여 요청을 단순화하거나 테이블을 별도의 요청으로 분할하는 것을 고려해 보십시오. |
| [!UICONTROL 이 차원은 현재 기본이 아닌 속성 모델을 지원하지 않습니다.] | 사용 중인 차원에 대해 기본이 아닌 속성이 지원되지 않습니다. | 테이블의 차원을 [Attribution IQ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL 너무 많은 열 또는 사전 구성된 행으로 인해 요청이 실패했습니다.] | 표에 자유 형식 셀이 너무 많습니다(행 * 열). | 테이블에서 열 또는 행을 제거하거나 표를 별도의 요청으로 분할하는 것을 고려해 보십시오. |