---
title: 세션 설정
description: 데이터 보기에서 세션 길이를 정의하고 트리거를 사용하여 새 세션을 시작할 수 있는 설정입니다
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: bb2061f9119b8391bf3cedce4029685537d1e239
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 38%

---


# 세션 설정

데이터 보기의 세션 설정은 Customer Journey Analytics이 연결의 데이터에서 세션을 계산하는 방식을 변경합니다.

데이터 보기의 **[!UICONTROL 설정]** 탭에서 사람들이 디지털 경험과 상호 작용하는 방식과 일치하는 방식으로 세션을 정의할 수 있습니다. 세션 설정 정의는 비파괴적이며 기본 데이터를 변경하지 않습니다. 작업 영역 프로젝트의 기반으로 여러 데이터 보기(각각 고유한 세션 설정 정의가 있음)를 설정할 수 있습니다.

데이터 보기에 대한 세션 컨텍스트를 정의하려면 다음 작업을 수행하십시오.

1. Customer Journey Analytics UI에서 **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.

2. 새 데이터 보기를 만들거나 기존 데이터 보기를 편집합니다. 자세한 내용은 [데이터 보기 만들기 또는 편집](create-dataview.md)을 참조하십시오.

3. **[!UICONTROL 설정]** 탭을 선택합니다. [!UICONTROL 세션 설정] 아래에서 다음 작업을 수행합니다.

   1. **[!UICONTROL 세션 시간 제한]**&#x200B;의 값을 [!UICONTROL 분], [!UICONTROL 시간], [!UICONTROL 일] 또는 [!UICONTROL 주] 단위로 입력합니다. 세션 시간 제한은 새 세션을 시작하기 전에 세션이 유휴 상태(이벤트 발생 없음)일 수 있는 시간을 결정합니다.

      주로 온라인 상호 작용을 분석하려는 경우 짧은 세션 시간 제한(예: 30분)을 사용합니다. 예를 들어 온라인 스토어 제품 페이지를 방문한 프로필이 장바구니에 제품을 추가했는지 또는 온라인으로 구매했는지를 분석합니다.

      온라인 및 오프라인 데이터를 결합하고 하나 이상의 제품을 구매한 고객이 구매 후 첫 3개월 이내에 연락 센터에 전화했는지 여부를 분석하려는 경우 긴 세션 시간 제한(예: 3개월)을 사용합니다.


   2. **[!UICONTROL 지표를 사용하여 새 세션 시작]** 아래의 **[!UICONTROL 여기에 지표 놓기]** 목록에서 지표를 선택합니다. 또는 **[!UICONTROL 지표 필드 놓기]**&#x200B;의 왼쪽 창에서 지표를 드래그 앤 드롭할 수 있습니다. 선택한 지표는 새 세션의 시작을 정의합니다. 지표를 여러 개 정의할 수 있습니다.

      모든 종류의 지표를 사용하여 새 세션을 정의할 수 있습니다. 예를 들어 프로필이 모바일 앱을 시작할 때마다 새 세션을 정의하려고 한다고 가정해 보겠습니다. 위치 **[!UICONTROL 데이터 보기]** > **[!UICONTROL 구성 요소]**, 이라는 유형 지표의 구성 요소를 정의합니다. **[!UICONTROL 론치]**, 기준 **[!UICONTROL appInteraction]** **[!UICONTROL 이름]** 스키마 필드. 다음을 추가로 지정합니다. **[!UICONTROL 론치]** 값이 일치할 때만 값을 카운트하는 지표 구성 요소 `launch`.

      ![앱 상호 작용 지표 구성 요소 실행](assets/component-launches.png)

      그런 다음 을(를) 끌어서 놓거나 **[!UICONTROL 론치]** 지표를 지표로 사용하여 새 세션을 정의합니다.

      ![세션 설정 실행](assets/session-settings-launches-metric.png)



4. 선택 **[!UICONTROL 저장]** 또는 **[!UICONTROL 저장 및 마침]** 세션 설정 정의를 저장합니다.
