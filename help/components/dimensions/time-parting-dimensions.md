---
description: 시간 분할은 수집한 히트의 타임스탬프를 가져와서 "시간" 또는 "요일"과 같은 더 의미 있는 차원으로 나눕니다.
title: 차원 시간 분할
uuid: c9fa7921-aa57-483c-b2f9-da55013ada17
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 100%

---


# 차원 시간 분할

시간 분할은 수집한 히트의 타임스탬프를 가져와서 &quot;시간&quot; 또는 &quot;요일&quot;과 같은 더 의미 있는 차원으로 나눕니다.

시간 분할 차원은 보고서 세트 또는 가상 보고서 세트의 시간대를 기반으로 합니다. 이러한 차원은 Analysis Workspace에서 사용할 수 있으며, 다음 질문에 대한 답변을 제공하는 데 도움을 줄 수 있습니다.

* 넓은 날짜 범위에서 방문자가 내 사이트나 앱에 가장 많이 오는 시간은 언제입니까?
* 내 사이트 또는 앱에서 전환율이 더 높은 요일이나 시간대가 있습니까?
* 평일 판매와 주말 판매를 비교하면 어떻습니까?
* 아침 또는 오후에 특히 전환이 높게 생성되는 특정 마케팅 캠페인이 있습니까?

>[!NOTE]
>
>시간 분할 차원은 Analysis Workspace에서만 사용할 수 있습니다. 다른 분석 솔루션에서 시간 분할 차원을 사용하려면 [getTimeParting 플러그인](https://docs.adobe.com/content/help/ko-KR/analytics/implementation/vars/plugins/gettimeparting.html)을 구현할 수 있습니다.

Analysis Workspace의 시간 분할 차원에는 다음 항목이 포함됩니다.

| 차원 | 예제 값 |
|--- |--- |
| 시간 | 0-23 |
| 오전/오후 | 오전, 오후 |
| 요일 | 월요일, 화요일, 수요일, 목요일, 금요일, 토요일, 일요일 |
| 주말/평일 | 주말, 평일 |
| 날짜 | 1-31 |
| 월 | 1월~12월 |
| 일 | 1-366 |
| 사분기 | Q1, Q2, Q3, Q4 |
