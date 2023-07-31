---
title: 컨텍스트 인식 세션
description: 컨텍스트 인식 세션을 정의하는 데 사용할 수 있는 데이터 보기의 설정입니다.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 83%

---


# 컨텍스트 인식 세션

데이터 보기의 컨텍스트 인식 세션은 Customer Journey Analytics가 연결의 데이터에서 세션을 계산하는 방식을 변경합니다.

데이터 보기의 [!UICONTROL 설정] 탭에서 사람들이 디지털 경험과 상호 작용하는 방식과 일치하는 방식으로 세션을 정의할 수 있습니다. 컨텍스트 인식 세션 정의는 비파괴적이며 기본 데이터를 변경하지 않습니다. 작업 영역 프로젝트의 기반으로 여러 데이터 보기(각 데이터 보기에 특정 컨텍스트 인식 세션 정의가 있음)를 설정할 수 있습니다.

데이터 보기에 대한 세션 컨텍스트를 정의하려면 다음 작업을 수행하십시오.

1. Customer Journey Analytics UI에서 **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.

1. 새 데이터 보기를 만들거나 기존 데이터 보기를 편집합니다. 자세한 내용은 [데이터 보기 만들기 또는 편집](create-dataview.md)을 참조하십시오.

1. **[!UICONTROL 설정]** 탭을 선택합니다. [!UICONTROL 세션 설정] 아래에서 다음 작업을 수행합니다.

   1. **[!UICONTROL 세션 시간 제한]**&#x200B;의 값을 [!UICONTROL 분], [!UICONTROL 시간], [!UICONTROL 일] 또는 [!UICONTROL 주] 단위로 입력합니다. 세션 시간 제한은 새 세션을 시작하기 전에 세션이 유휴 상태(이벤트 발생 없음)일 수 있는 시간을 결정합니다.

   2. [!UICONTROL 지표를 사용하여 새 세션 시작] 아래의 **[!UICONTROL 여기에 지표 놓기]** 목록에서 지표를 선택합니다. 또는 의 왼쪽 창에서 지표를 드래그하여 놓을 수 있습니다. **[!UICONTROL 지표 필드 놓기]**. 선택한 지표는 새 세션의 시작을 정의합니다. 지표를 여러 개 정의할 수 있습니다.

1. **[!UICONTROL 저장]** 또는 **[!UICONTROL 저장 후 마침]**&#x200B;을 선택하여 컨텍스트 인식 세션 정의를 저장합니다.

