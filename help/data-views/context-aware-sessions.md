---
title: 컨텍스트 인식 세션
description: 데이터 보기에서 컨텍스트 인식 세션을 정의하는 데 사용할 수 있는 설정입니다.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 3%

---


# 컨텍스트 인식 세션

데이터 보기의 컨텍스트 인식 세션은 Customer Journey Analytics이 연결의 데이터에서 세션을 계산하는 방식을 변경합니다.

다음 범위 내 [!UICONTROL 설정] 데이터 보기 탭에서 개인이 디지털 경험과 상호 작용하는 방식과 일치하는 방식으로 세션을 정의할 수 있습니다. 컨텍스트 인식 세션 정의는 비파괴적이며 기본 데이터를 변경하지 않습니다. 작업 영역 프로젝트의 기반으로 여러 데이터 보기(각 데이터 보기에 특정 컨텍스트 인식 세션 정의가 있음)를 설정할 수 있습니다.

데이터 보기에 대한 세션 컨텍스트를 정의하려면 다음을 수행합니다.

1. 선택 **[!UICONTROL 데이터 보기]** Customer Journey Analytics UI에서

1. 새 데이터 보기를 만들거나 기존 데이터 보기를 편집합니다. 다음을 참조하십시오 [데이터 보기 만들기 또는 편집](create-dataview.md) 추가 정보.

1. **[!UICONTROL 설정]** 탭을 선택합니다. 아래 [!UICONTROL 세션 설정]:

   1. 다음에 대한 값 입력 **[!UICONTROL 세션 시간 초과]** 위치: [!UICONTROL 분], [!UICONTROL 시간], [!UICONTROL 일], 또는 [!UICONTROL 주]. 세션 시간 제한은 새 세션을 시작하기 전에 세션이 유휴 상태(이벤트 발생 없음)일 수 있는 시간을 결정합니다.

   2. 다음에서 지표 선택 **[!UICONTROL 여기에 지표 놓기]** 아래에 나열 [!UICONTROL 지표로 새 세션 시작]. 또는 의 왼쪽 창에서 지표를 드래그하여 놓을 수 있습니다. **[!UICONTROL 지표 필드 놓기]**. 선택한 지표는 새 세션의 시작을 정의합니다. 두 개 이상의 지표를 정의할 수 있습니다.

1. 선택 **[!UICONTROL 저장]** 또는 **[!UICONTROL 저장 및 마침]** 컨텍스트 인식 세션 정의를 저장합니다.

