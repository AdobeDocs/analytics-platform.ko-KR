---
title: 세션 설정
description: 세션의 길이와 새 세션을 시작하는 트리거를 정의하는 데 사용할 수 있는 데이터 보기의 설정
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: ht
source-wordcount: '462'
ht-degree: 100%

---

# 세션 설정 {#session-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_settings_datapreview"
>title="데이터 미리보기"
>abstract="이 데이터 보기의 데이터를 연결의 데이터와 비교합니다. 미리보기 비율은 **지난 90일** 동안의 연결 총 수를 기준으로 합니다.<br><br/>미리보기가 로드되지 않는다면 연결이 아직 다시 채우는 중일 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-enable MD034 -->


Customer Journey Analytics에서 사람들이 디지털 경험과 상호 작용하는 방식과 일치하는 방식으로 세션을 정의할 수 있습니다. 데이터 보기 내에서 세션 설정을 구성합니다.

세션 설정 정의는 비파괴적이며 기본 데이터를 변경하지 않습니다. Workspace 프로젝트의 기반으로 특정 세션 설정 정의를 사용하여 각각 여러 데이터 보기를 설정할 수 있습니다.

데이터 보기 내에서 세션 컨텍스트를 정의하려면 다음 작업을 수행하십시오.

1. Customer Journey Analytics UI의 메인 탐색에서, **[!UICONTROL 데이터 관리]**&#x200B;에서(선택 사항) **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.

2. 새 데이터 보기를 만들거나 기존 데이터 보기를 편집합니다. 자세한 내용은 [데이터 보기 만들기 또는 편집](create-dataview.md)을 참조하십시오.

3. **[!UICONTROL 설정]** 탭을 선택합니다. [!UICONTROL 세션 설정] 아래에서 다음 작업을 수행합니다.

   1. **[!UICONTROL 세션 시간 제한]**&#x200B;의 값을 [!UICONTROL 분], [!UICONTROL 시간], [!UICONTROL 일] 또는 [!UICONTROL 주] 단위로 입력합니다. 세션 시간 제한은 새 세션을 시작하기 전에 세션이 유휴 상태(이벤트 발생 없음)일 수 있는 시간을 결정합니다.

      주로 온라인 상호 작용을 분석하는 것이 목적인 경우 짧은 세션 제한 시간(예: 30분)을 사용하십시오. 예를 들어 온라인 스토어 제품 페이지를 방문하는 프로필이 장바구니에 제품을 추가했는지나 온라인으로 구매했는지 여부를 분석합니다.

      온라인 데이터와 오프라인 데이터를 결합하고 하나 이상의 제품을 구매한 고객이 구매 후 첫 3개월 이내에 콜센터에 전화했는지 여부를 분석하려는 경우 긴 세션 제한 시간(예: 3개월)을 사용하십시오.


   2. **[!UICONTROL 지표를 사용하여 새 세션 시작]** 아래의 **[!UICONTROL 여기에 지표 놓기]** 목록에서 지표를 선택합니다. 또는 **[!UICONTROL 지표 필드 놓기]**&#x200B;의 왼쪽 창에서 지표를 드래그 앤 드롭할 수 있습니다. 선택한 지표는 새 세션의 시작을 정의합니다. 지표를 여러 개 정의할 수 있습니다.

      모든 종류의 지표를 사용하여 새 세션을 정의할 수 있습니다. 예를 들어 프로필이 모바일 앱을 시작할 때마다 새 세션을 정의한다고 가정해 보십시오. **[!UICONTROL 데이터 보기]** > **[!UICONTROL 구성 요소]**&#x200B;에서 이름이 **[!UICONTROL 론치]**&#x200B;로 지정되고 **[!UICONTROL 앱 인터랙션]** **[!UICONTROL 이름]** 스키마 필드에 기반한 지표 유형의 구성 요소를 정의합니다. **[!UICONTROL 론치]** 지표 구성 요소를 추가로 지정하여 값이 `launch`와(과) 일치할 때만 값을 계산하도록 합니다.

      ![앱 인터랙션 지표 구성 요소 론치](assets/component-launches.png)

      그런 다음 드래그 앤 드롭하거나 **[!UICONTROL 론치]** 지표를 새 세션을 정의하는 지표로 선택합니다.

      ![세션 설정 론치](assets/session-settings-launches-metric.png)



4. **[!UICONTROL 저장]** 또는 **[!UICONTROL 저장 후 마침]**&#x200B;을 선택하여 세션 설정 정의를 저장합니다.
