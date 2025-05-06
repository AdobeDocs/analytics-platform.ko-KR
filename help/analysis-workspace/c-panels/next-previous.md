---
description: 특정 차원에 대한 다음 또는 이전 차원 항목을 표시하는 패널.
title: 다음 또는 이전 항목 패널
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: ht
source-wordcount: '457'
ht-degree: 100%

---

# 다음 또는 이전 항목 패널 {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="다음 또는 이전 항목"
>abstract="사용자의 이전 차원과 사용자의 다음 차원을 파악할 수 있는 패널을 만듭니다."

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="다음 또는 이전 항목"
>abstract="방문자들이 이전에 왔거나 다음으로 이동하는 가장 일반적인 장소를 분석합니다. 시각화에 사용할 차원, 차원 항목, 방향 및 컨테이너를 지정합니다."



<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_이 문서에서는_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_&#x200B;의 다음 또는 이전 항목 패널에 대해 설명합니다.<br/>_이 문서의_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 버전은 [다음 또는 이전 항목 패널](https://experienceleague.adobe.com/ko/docs/analytics/analyze/analysis-workspace/panels/next-previous)을 참조하십시오._

>[!ENDSHADEBOX]

**[!UICONTROL 다음 또는 이전 항목]** 패널에는 특정 차원의 다음 또는 이전 차원 항목을 식별하기 위한 여러 표와 시각화가 포함되어 있습니다. 예를 들어 고객이 홈 페이지를 방문한 후 가장 자주 방문한 페이지를 살펴볼 수 있습니다.

## 사용 {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="컨테이너"
>abstract="컨테이너를 선택하여 문의의 범위를 지정합니다."

**[!UICONTROL 다음 또는 이전 항목]** 패널 사용 방법:

1. **[!UICONTROL 다음 또는 이전 항목]** 패널을 만듭니다. 패널을 만드는 방법에 대한 자세한 내용은 [패널 만들기](panels.md#create-a-panel)를 참조하십시오.

1. 패널의 [입력](#panel-input)을 지정합니다.

1. 패널의 [출력](#panel-output)을 확인합니다.

### 패널 입력

다음 입력 설정을 사용하여 [!UICONTROL 다음 또는 이전 항목] 패널을 구성할 수 있습니다.

![다음 또는 이전 항목 패널](assets/next-or-previous-item.png)

| 입력 | 설명 |
| --- | --- |
| **[!UICONTROL 차원]** | 다음 또는 이전 항목을 탐색할 차원을 선택합니다. |
| **[!UICONTROL 차원 항목]** | 다음 / 이전 문의의 가운데에서 특정 차원 항목을 선택합니다. |
| **[!UICONTROL 방향]** | [!UICONTROL 다음] 또는 [!UICONTROL 이전] 차원 항목 중 무엇을 찾고 있는지 지정합니다. |
| **[!UICONTROL 컨테이너]** | **[!UICONTROL 글로벌 계정]**[!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}, **[!UICONTROL 계정]**[!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}, **[!UICONTROL 구매 그룹]**[!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}, **[!UICONTROL 기회]**([!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}, **[!UICONTROL 세션]** 또는 **[!UICONTROL 사용자]** 컨테이너 중 하나를 선택하여 문의의 범위를 지정합니다. |

{style="table-layout:auto"}

패널을 빌드하려면 **[!UICONTROL 빌드]**&#x200B;를 선택합니다.

### 패널 출력

[!UICONTROL 다음 또는 이전 항목] 패널은 특정 차원 항목 뒤나 앞에 오는 현상을 더 잘 이해할 수 있도록 풍부한 데이터와 시각화 세트를 제공합니다.


![다음/이전 패널 출력](assets/next-or-previous-item-output.png)


| 시각화 | 설명 |
| --- | --- |
| **[!UICONTROL 가로 막대]** | 선택한 차원 항목에 따라 다음 (또는 이전) 항목을 나열합니다. 개별 막대에 마우스를 가져다 대면 자유 형식 테이블에서 해당 항목이 강조 표시됩니다. |
| **[!UICONTROL 요약 숫자]** | 현재 달 동안(지금까지)의 모든 다음 또는 이전 차원 항목 발생 횟수를 요약한 상위 수준 숫자입니다. |
| **[!UICONTROL 자유 형식 테이블]** | 선택한 차원 항목을 기준으로 다음 (또는 이전) 항목을 테이블 형식으로 나열합니다. 예를 들어 사람들이 홈 페이지나 작업 영역 페이지 다음(또는 그 이전)으로 가장 방문 빈도가 높은 페이지들이었습니다. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[패널 만들기](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
