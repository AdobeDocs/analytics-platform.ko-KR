---
description: Analysis Workspace 내에서 데이터 예외 항목을 컨텍스트에 따라 보고 분석할 수 있습니다.
title: 예외 항목 탐지 개요
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 96%

---


# 예외 항목 탐지 개요

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 계십니다. 이 기능은 [기존 Adobe Analytics의 Analysis Workspace](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html)와 약간 다릅니다. [추가 정보...](/help/getting-started/cja-aa.md)

Analysis Workspace 내에서 데이터 예외 항목을 컨텍스트에 따라 보고 분석할 수 있습니다.

[예외 항목 탐지 - YouTube](https://www.youtube.com/watch?v=krXyQCjXoeU&amp;index=63&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)(4:53)

예외 항목 탐지는 이전 데이터에 관해 주어진 지표가 변경되는 방법을 결정하는 통계적 방법을 제공합니다.

예외 항목 탐지 기능을 사용하면 &quot;노이즈&quot;에서 &quot;진짜 신호&quot;를 구분한 다음, 이러한 신호 또는 이상 현상에 기여한 잠재적 요인을 식별하는 데 도움이 됩니다. 다시 말해, 통계적 변동이 문제가 되는지 여부를 식별하게 해줍니다. 그러면 진짜 예외 현상의 근본 원인을 식별할 수 있습니다. 또한 신뢰할 수 있는 지표(KPI) 예측이 가능합니다.

조사할 수 있는 이상 현상의 예에는 다음 내용이 포함됩니다.

* 평균 주문 가격의 급격한 하락
* 매출액이 낮은 주문의 급등
* 평가판 등록 급등 또는 하락
* 랜딩 페이지 보기 수의 하락
* 비디오 버퍼 이벤트의 스파이크
* 낮은 비디오 비트율의 스파이크

Analysis Workspace에서 예외 항목 탐지 및 [기여도 분석](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) 기능은 모두 핵심 워크플로우입니다. 매일 발생하는 임의의 예외 항목에 대해 [기여도 분석]을 실행하고 Analysis Workspace 프로젝트에 그 결과를 포함할 수 있습니다.

>[!IMPORTANT]
>
>기여도 분석은 아직 Customer Journey Analytics에서 사용할 수 없습니다.

Analysis Workspace의 예외 항목 탐지 알고리즘에 포함된 기능은 다음과 같습니다.

* 기존의 일별 세부 기간 이외에 시간별, 주별 및 월별 세부 기간 지원.
* 계절적 영향(예: &quot;블랙 프라이데이&quot;) 및 휴일 인식.

## 예외 항목 탐지 해제

열 설정으로 이동하고 **[!UICONTROL 예외 항목]**&#x200B;을 선택 취소하여 열 수준에서 예외 항목 탐지를 해제할 수 있습니다.

![](assets/turnoff_anomalies.png)
