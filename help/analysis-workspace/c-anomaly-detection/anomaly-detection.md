---
description: Analysis Workspace의 데이터 예외 항목 탐지에 대해 알아봅니다.
title: 예외 항목 탐지 작동 방식
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 100%

---

# 예외 항목 탐지 개요

Analysis Workspace 내에서 데이터 예외 항목을 컨텍스트에 따라 보고 분석할 수 있습니다.

[예외 항목 탐지 비디오 튜토리얼](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=ko)(4:53)

예외 항목 탐지는 이전 데이터에 관해 주어진 지표가 변경되는 방법을 결정하는 통계적 방법을 제공합니다.

예외 항목 탐지 기능을 사용하면 &quot;노이즈&quot;에서 &quot;진짜 신호&quot;를 구분한 다음, 이러한 신호 또는 이상 현상에 기여한 잠재적 요인을 식별하는 데 도움이 됩니다. 다시 말해, 통계적 변동이 문제가 되는지 여부를 식별하게 해 줍니다. 그러면 진짜 예외 현상의 근본 원인을 식별할 수 있습니다. 또한 신뢰할 수 있는 지표(KPI) 예측이 가능합니다.

조사할 수 있는 이상 현상의 예에는 다음 내용이 포함됩니다.

* 평균 주문 가격의 급격한 하락
* 매출액이 낮은 주문의 급등
* 체험판 등록 급등 또는 하락
* 랜딩 페이지 조회수의 하락
* 비디오 버퍼 이벤트의 스파이크
* 낮은 비디오 비트율의 스파이크

Analysis Workspace의 예외 항목 탐지 알고리즘에 포함된 기능은 다음과 같습니다.

* 기존의 일별 세부 기간 이외에 시간별, 주별 및 월별 세부 기간 지원.
* 계절적 영향(예: &quot;블랙 프라이데이&quot;) 및 휴일 인식.
