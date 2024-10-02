---
description: 특정 차원에 대한 다음 또는 이전 차원 항목을 표시하는 패널입니다.
title: 다음 또는 이전 항목 패널
feature: Panels
role: User, Admin
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# 다음 또는 이전 항목 패널 {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_button"
>title="다음 또는 이전 항목"
>abstract="사람들이 속한 이전 차원 또는 사람들이 속한 다음 차원을 이해하기 위한 패널을 만듭니다."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_panel"
>title="중첩 또는 이전 항목"
>abstract="방문자가 이전에 어디에서 왔거나 다음으로 이동했던 가장 일반적인 위치를 분석합니다.<br/><br/>**Dimension**: 차원을 선택합니다. 예: **Page**.<br/>**Dimension 항목**: 특정 차원 항목을 선택하십시오. 예: **홈 페이지**.<br/>**방향**: 선택한 차원 항목 바로 다음에 차원 항목을 표시하려면 **다음**&#x200B;을 선택합니다. 선택한 차원 항목으로 이어지는 차원 항목을 보려면 **이전**&#x200B;을(를) 선택하십시오.<br/>**컨테이너**: 같은 세션 내에서 다음/이전 차원 항목을 보려면 **세션**&#x200B;을 선택하고, 같은 사람의 다음/이전 차원 항목을 보려면 **사람**&#x200B;을 선택하십시오."

<!-- markdownlint-enable MD034 -->



**[!UICONTROL 다음 또는 이전 항목]** 패널에는 특정 차원에 대한 다음 또는 이전 차원 항목을 식별하는 많은 표와 시각화가 포함되어 있습니다. 예를 들어 고객이 홈 페이지를 방문한 후 가장 자주 방문한 페이지를 탐색할 수 있습니다.

## Use

**[!UICONTROL 다음 또는 이전 항목]** 패널을 사용하려면:

1. **[!UICONTROL 다음 또는 이전 항목]** 패널을 만듭니다. 패널을 만드는 방법에 대한 자세한 내용은 [패널 만들기](panels.md#create-a-panel)를 참조하십시오.

1. 패널에 대한 [입력](#panel-input)을(를) 지정하십시오.

1. 패널의 [output](#panel-output)을(를) 확인합니다.

### 패널 입력

다음 입력 설정을 사용하여 [!UICONTROL 다음 또는 이전 항목] 패널을 구성할 수 있습니다.

![다음 또는 이전 항목 패널](assets/next-or-previous-item.png)

| 입력 | 설명 |
| --- | --- |
| **[!UICONTROL 차원]** | 다음 또는 이전 항목을 탐색할 차원을 선택합니다. |
| **[!UICONTROL 차원 항목]** | 다음/이전 조회의 중심에 있는 특정 차원 항목을 선택합니다. |
| **[!UICONTROL 방향]** | [!UICONTROL 다음] 또는 [!UICONTROL 이전] 차원 항목을 찾고 있는지 여부를 지정하십시오. |
| **[!UICONTROL 컨테이너]** | 컨테이너 [!UICONTROL 세션] 또는 [!UICONTROL 개인](기본값)을 선택하여 문의 범위를 결정합니다. |

{style="table-layout:auto"}

패널을 빌드하려면 **[!UICONTROL 빌드]**&#x200B;를 선택하십시오.

### 패널 출력

[!UICONTROL 다음 또는 이전 항목] 패널은 특정 차원 항목의 다음 또는 이전 발생 횟수를 더 잘 이해할 수 있도록 풍부한 데이터 및 시각화를 반환합니다.


![다음/이전 패널 출력](assets/next-or-previous-item-output.png)


| 시각화 | 설명 |
| --- | --- |
| **[!UICONTROL 가로 막대형]** | 선택한 차원 항목을 기반으로 다음(또는 이전) 항목을 나열합니다. 개별 막대에 마우스를 가져다 대면 자유 형식 테이블에서 해당 항목이 강조 표시됩니다. |
| **[!UICONTROL 요약 번호]** | 현재 월에 대한 모든 다음 또는 이전 차원 항목 발생의 높은 수준 요약 번호(현재까지)입니다. |
| **[!UICONTROL 자유 형식 테이블]** | 선택한 차원 항목을 기반으로 다음(또는 이전) 항목을 테이블 형식으로 나열합니다. 예를 들어, 사람들이 홈 페이지 또는 작업 영역 페이지 뒤(또는 이전)로 이동한 가장 방문 빈도가 높은 페이지(발생 횟수별)입니다. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[패널 만들기](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>