---
title: 주석 개요
description: Analysis Workspace에서 주석을 사용하는 방법
solution: Customer Journey Analytics
feature: Components
exl-id: a87f6968-27a5-4595-be4f-0a38e03b9398
role: User
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 97%

---

# 주석 개요

주석을 사용하면 상황별 데이터 뉘앙스와 인사이트를 효과적으로 조직의 다른 관련자에게 전달할 수 있습니다. 주석을 사용하면 캘린더 이벤트를 특정 차원 및 지표에 연결할 수 있습니다. 알려진 데이터 문제, 공휴일, 캠페인 시작 등으로 날짜 또는 날짜 범위에 주석을 달아 그런 다음 이벤트를 그래픽으로 표시하고 캠페인이나 다른 이벤트가 사이트 트래픽, 모바일 앱 사용량, 매출 또는 기타 지표에 영향을 미치는지 여부를 확인할 수 있습니다.

예를 들어 조직과 프로젝트를 공유하고 있습니다. 오퍼 수락에 큰 문제가 발생한 경우 **잘못된 오퍼** 주석을 만들고 범위를 전체 데이터 보기로 지정할 수 있습니다. 사용자가 해당 날짜가 포함된 데이터 세트를 볼 때 데이터와 함께 프로젝트 내의 주석을 볼 수 있습니다.

![Line chart with annotation highlighted.](assets/annotation-example.png)

주석이 다음에 적용될 수 있습니다.

* 단일 날짜 또는 날짜 범위.

* 전체 데이터 세트 또는 특정 지표, 차원 또는 세그먼트.

* 주석이 만들어지는 프로젝트(기본값) 또는 모든 프로젝트.

* 주석이 만들어지는 데이터 보기(기본값) 또는 모든 데이터 보기.

주석을 만들 수 있는 다양한 옵션은 [주석 만들기](/help/components/annotations/create-annotations.md)를 참조하십시오. 그런 다음 [주석 빌더](create-annotations.md#annotation-builder)에서 주석을 빌드, 수정 및 저장합니다.

[주석 관리자](manage-annotations.md) 를 사용하여 주석을 관리합니다.

## 주석 켜기 또는 끄기

다음과 같은 다양한 수준에서 주석을 켜거나 끌 수 있습니다.

| 레벨 | 방법... |
|---|---|
| **시각화** | ![Setting](/help/assets/icons/Setting.svg) > **[!UICONTROL 설정]** >  **[!UICONTROL 주석 표시]**&#x200B;를 활성화 또는 비활성화합니다.<br/>![Enable disable annotations for a visualization](/help/components/annotations/assets/annotations-visualization.png) |
| **프로젝트** | Workspace 프로젝트 메뉴에서 **[!UICONTROL 프로젝트]** > **[!UICONTROL 프로젝트 정보 및 설정]**&#x200B;을 선택하고 **[!UICONTROL 주석 표시]**&#x200B;를 활성화 또는 비활성화합니다.<br/>![Enable disable annotations for a project](/help/components/annotations/assets/annotations-project.png) |
| **사용자** | **[!UICONTROL 구성 요소]** 탭에서 **[!UICONTROL 환경 설정]**&#x200B;을 선택하거나, Workspace 프로젝트 메뉴에서 **[!UICONTROL 프로젝트]** > **[!UICONTROL 사용자 환경 설정]**&#x200B;을 선택합니다. <br/> **[!UICONTROL 환경 설정]**&#x200B;에서 **[!UICONTROL 프로젝트 및 분석]**&#x200B;을 선택합니다. 왼쪽 탭 막대에서 **[!UICONTROL 데이터]**&#x200B;를 선택합니다. 하단에서 **[!UICONTROL 자유 형식 테이블]** 제목 아래의 **[!UICONTROL 주석 표시]**&#x200B;를 활성화하거나 비활성화합니다.<br/>![Enable disable annotations for a user](/help/components/annotations/assets/annotations-user.png) |
