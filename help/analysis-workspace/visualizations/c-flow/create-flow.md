---
description: Workspace 프로젝트에서 플로우 시각화를 사용하는 방법에 대해 알아봅니다.
title: 플로우 시각화 구성 방법
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 90%

---

# 플로우 시각화 구성 {#configure-a-flow-visualization}

>[!CONTEXTUALHELP]
>id="workspace_flow_container"
>title="흐름 컨테이너"
>abstract="경로 지정(번호)을 표시하는 데 사용할 컨테이너를 선택하십시오."


플로우 시각화는 웹 사이트 또는 앱의 특정 전환 이벤트에서 발생하는 여정을 이해하는 데 도움이 됩니다. 또는 특정 전환 이벤트로 이어질 수 있습니다. 시각화는 차원(및 차원 항목) 또는 지표를 통해 경로를 추적합니다.

원하는 경로의 시작 또는 끝을 구성할 수 있습니다. 또는 차원 또는 차원 항목을 통과하는 모든 경로를 분석합니다.

![다음으로 시작, 포함, 다음으로 끝남 필드를 표시하는 흐름 구성 화면입니다.](assets/new-flow.png)

## 사용

1. ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 플로우]** 시각화를 추가합니다. [패널 내에 시각화 추가](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)를 참조하십시오.

1. 다음 옵션 중 하나를 사용하여 플로우 시각화를 고정합니다.

   * [!UICONTROL **다음으로 시작**] (지표, 차원 또는 항목)
   * [!UICONTROL **포함**] (차원 또는 항목)
   * [!UICONTROL **다음으로 끝남**] (지표, 차원 또는 항목)

   이러한 각각의 카테고리는 화면에 *드롭 영역*&#x200B;으로 표시됩니다. 세 가지 방법으로 드롭 영역을 채울 수 있습니다.

   * 드롭다운 메뉴를 사용하여 지표 또는 차원을 선택합니다.
   * 왼쪽 패널에서 차원 또는 지표를 드래그합니다.
   * 차원 또는 지표의 이름을 입력하기 시작한 다음 드롭다운 목록에 표시되면 선택합니다.

   >[!IMPORTANT]
   >
   >계산된 지표를 **[!UICONTROL 다음으로 시작]** 또는 **[!UICONTROL 다음으로 끝남]** 필드에 사용할 수 없습니다.

1. 지표를 선택하는 경우 여기에 표시된 대로 선택한 구성 요소로 연결되거나 연결되는 경로로 사용할 [!UICONTROL **경로 지정 차원**]&#x200B;도 제공해야 합니다. 기본값은 [!UICONTROL **페이지**]&#x200B;입니다.

   ![플로우 구성](assets/flow-configure.png)

1. (선택 사항) **[!UICONTROL 고급 설정 표시]**&#x200B;를 선택하여 다음 옵션 중 하나를 구성합니다.


   | 설정 | 설명 |
   | --- | --- |
   | **[!UICONTROL 줄 바꿈 레이블]** | 대개 흐름 요소의 레이블은 화면 공간을 절약하기 위해 잘리지만 이 상자를 선택하여 전체 레이블을 표시할 수 있습니다.  기본값 = 선택 해제. |
   | **[!UICONTROL 반복 인스턴스 포함]** | 플로우 시각화는 차원의 인스턴스를 기반으로 합니다. 이 설정은 반복된 인스턴스(예: 페이지 다시 로드)를 포함하거나 제외하는 옵션을 제공합니다. 하지만 listVars, listProp, s.product, 머천다이징 eVar 등과 같이 여러 값을 갖는 차원을 포함하는 플로우 시각화에서는 반복을 제거할 수 없습니다. <p>이 옵션은 기본적으로 비활성화되어 있습니다.</p> |
   | **[!UICONTROL 처음/마지막 발생으로 제한]** | 차원, 항목 또는 지표의 처음 또는 마지막 발생으로 진입 또는 종료하는 경로로 경로를 제한합니다. 자세한 설명은 [처음/마지막 발생으로 제한](#example-scenario-for-limit-to-firstlast-occurrence)을 참조하십시오. |
   | **[!UICONTROL 열 수]** | 플로우 다이어그램에 원하는 열 수입니다. 최대 5개의 열을 지정할 수 있습니다. |
   | **[!UICONTROL 열당 항목 확장됨]** | 각 열에 원하는 항목 수입니다. 열당 확장된 최대 10개의 항목을 지정할 수 있습니다. |
   | **[!UICONTROL 플로우 컨테이너]** | **[!UICONTROL 글로벌 계정]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL 계정]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL 기회]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL 구매 그룹]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL 세션]** 및 **[!UICONTROL 개인]** 간에 전환하여 경로 지정을 분석할 수 있습니다. 이 설정은 세션들에 대해 사용자 수준에서 사용자 참여를 이해하거나 분석을 단일 세션으로 제한하는 데 도움이 됩니다. |

   >[!IMPORTANT]
   >
   >**[!UICONTROL 열 수]**&#x200B;와 **[!UICONTROL 열당 확장된 항목]**&#x200B;의 조합에 따라 플로우 시각화를 만드는 데 필요한 기본 요청 수를 결정합니다. 열 수가 높을수록 시각화를 렌더링하는 데 시간이 오래 걸립니다.


1. **[!UICONTROL 빌드]**&#x200B;를 선택합니다.


### 예

사용자가 사이트의 가장 방문 빈도가 높은 페이지를 오가는 경로를 추적한다고 가정합니다.

1. 위에서 설명한 대로 플로우 시각화 만듭니다.
1. [!UICONTROL **페이지**] 차원을 **[!UICONTROL 포함]** 필드로 끌어온 다음 [!UICONTROL **빌드**]&#x200B;를 선택합니다.
1. 플로우 시각화는 시각화 중앙의 포커스 노드에 표시되는 가장 많이 본 페이지로 빌드됩니다. 또한 해당 페이지로 연결되는 상위 페이지(포커스 노드 왼쪽)와 해당 페이지에서 시작되는 상위 페이지(포커스 노드 오른쪽)를 확인할 수 있습니다.
1. [구성](#configure)에 설명된 대로 플로우에서 데이터를 분석합니다.


## 구성

플로우 구성의 요약이 시각화의 맨 위에 나타납니다. 다이어그램의 경로들은 비례합니다. 활동이 많은 경로일수록 더 두껍게 표시됩니다.

![방문 횟수로 끝남, 경로 지정 차원: 페이지 및 플로우 컨테이너: 방문자를 보여 주는 플로우 출력 예.](assets/flow-output.png)

데이터를 추가 드릴다운하려면 다음과 같은 몇 가지 옵션이 있습니다.

* 흐름 다이어그램은 대화형입니다. 표시되는 세부 사항을 변경하려면 마우스를 다이어그램 위에 놓습니다.

* 다이어그램에 있는 노드를 선택하면 해당 노드에 대한 세부 사항이 표시됩니다. 축소하려면 노드를 다시 선택합니다.

  ![노드 세부 정보를 보여 주는 대화형 플로우 다이어그램의 예.](assets/node-details.png)

* 포함 및 제외, 기준 지정 등과 같은 특정 결과만 표시하도록 열을 필터링할 수 있습니다.

* 열을 확장하려면 왼쪽이나 오른쪽에 있는 ![AddCircle](/help/assets/icons/AddCircle.svg)을 선택합니다.

* 출력을 사용자 정의하려면 [컨텍스트 메뉴](#context-menu) 옵션을 사용합니다.

* 플로우를 편집하거나 다른 옵션으로 다시 빌드하려면 구성 요약 옆에 있는 ![편집](/help/assets/icons/Edit.svg)을 선택합니다.

## 필터링

각 열 위에 마우스를 가져다 대면 필터 ![필터](/help/assets/icons/Filter.svg)가 나타납니다. 필터를 선택하면 자유 형식 테이블에 있는 것과 동일한 필터 대화 상자가 나타납니다. [필터링 및 정렬](freeform-table/../../freeform-table/filter-and-sort.md)을 참조하십시오.

* **[!UICONTROL 고급 표시]**&#x200B;를 사용하면 연산자 목록을 사용하여 특정 기준을 포함하거나 제외하는 고급 설정을 구성할 수 있습니다. 자세한 내용은 [필터링 및 정렬](../freeform-table/filter-and-sort.md)을 참조하십시오.
* 열을 필터링하면 해당 열에 필터링이 반영됩니다. 파란색 ![필터](/help/assets/icons/FilterColored.svg)는 열이 필터링되었음을 나타냅니다.  필터는 열을 줄여서 필터에서 허용된 항목만 표시합니다. 또는 필터에 원하는 항목 하나만 제외하고 모든 항목을 제거합니다.
* 나머지 노드로 데이터가 유입되는 한 모든 다운스트림 및 업스트림 열은 지속됩니다.
* 필터를 제거하려면 ![필터](/help/assets/icons/Filter.svg)를 선택하여 필터 메뉴를 엽니다. 적용된 필터를 제거한 다음 **[!UICONTROL 저장]**&#x200B;을 선택합니다. 플로우를 필터링되지 않은 이전 상태로 돌아가야 합니다.

## 컨텍스트 메뉴

다음 옵션을 사용하여 플로우 시각화의 모든 노드에서 컨텍스트 메뉴를 사용합니다.

| 옵션 | 설명 |
|--- |--- |
| **[!UICONTROL 이 노드에 대한 포커스]** | 포커스를 선택된 노드로 변경합니다. 플로우 다이어그램의 중앙에 포커스 노드가 표시됩니다. |
| **[!UICONTROL 시작]** | 새 플로우 다이어그램을 빌드할 수 있는 자유 형식 다이어그램 빌더로 돌아갑니다. |
| **[!UICONTROL 이 경로에 대한 필터 만들기]** | 필터를 만듭니다. 필터 빌더로 이동하여 새 필터를 구성할 수 있습니다. |
| **[!UICONTROL 분류]** | 사용할 수 있는 차원, 지표 또는 시간으로 노드를 분석합니다. |
| **[!UICONTROL 필터 열]** | 자유 형식 테이블에서 사용 가능한 것과 동일한 필터 옵션이 나타납니다. 사용 가능한 옵션에 대한 자세한 내용은 [테이블 필터 및 정렬](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)의 “테이블에 단순 또는 고급 필터 적용” 섹션을 참조하십시오. |
| **[!UICONTROL 항목 제외]** 또는 **[!UICONTROL 제외된 항목 복원]** | 열에서 특정 노드를 제거하고 열 맨 위에 필터로 자동으로 만듭니다. 제외된 항목을 복원하려면 컨텍스트 메뉴에서 **[!UICONTROL 제외된 항목 복원]**&#x200B;을 선택합니다. 또한 열의 맨 위에 있는 필터를 열고 방금 제외한 항목이 있는 필박스를 제거할 수도 있습니다. |
| **[!UICONTROL 트렌드]** | 노드에 대한 트렌드 다이어그램을 만듭니다. |
| **[!UICONTROL 다음 열 표시]** / **[!UICONTROL 이전 열 표시]** | 시각화의 다음(오른쪽) 또는 이전(왼쪽) 열을 표시합니다. |
| **[!UICONTROL 열 숨기기]**n | 시각화에서 선택한 열을 숨깁니다. |
| **[!UICONTROL 전체 열 확장]** | 모든 노드를 표시하도록 열을 확장합니다. 기본적으로 상위 5개의 노드만 표시됩니다. |
| **[!UICONTROL 선택 항목으로 대상자 만들기]** | 선택된 열에 따라 대상자를 만듭니다. |
| **[!UICONTROL 전체 열 축소]** | 열에 있는 모든 노드를 숨깁니다. |

## 처음/마지막 발생으로 제한

이 옵션을 사용할 때는 다음 사항에 유의하십시오.

* **[!UICONTROL 처음/마지막 발생으로 제한]**&#x200B;은 시리즈의 처음/마지막 발생만 카운트합니다. **[!UICONTROL 다음으로 시작]** 또는 **[!UICONTROL 다음으로 끝남]** 기준의 다른 모든 발생은 삭제됩니다.
* **[!UICONTROL 다음으로 시작]** 플로우와 함께 사용할 경우, 시작 기준과 일치하는 처음 발생만 포함됩니다.
아래 예시에서는 플로우의 각 단계에서 *장바구니에 추가* 및 *제품 주요 카테고리*&#x200B;가 **모든** 발생에 포함되어 있습니다.
  ![제한 없음, 처음](assets/limitofffirst.png)

  아래 예시에서는 플로우의 각 단계에서 *장바구니에 추가* 및 *제품 주요 카테고리*&#x200B;가 **처음** 발생에만 포함되어 있습니다.
  ![Lint, 시작](assets/limitonfirst.png)
* **[!UICONTROL 다음으로 끝남]** 플로우와 함께 사용할 경우, 종료 기준과 일치하는 마지막 발생만 포함됩니다.
아래 예시에서는 플로우의 각 단계에서 *제품 주요 카테고리* 및 *장바구니에 추가*&#x200B;가 **모든** 발생에 포함되어 있습니다.
  ![제한 없음, 처음](assets/limitofflast.png)

  아래 예시에서는 플로우의 각 단계에서 *제품 주요 카테고리* 및 *장바구니에 추가*&#x200B;가 **마지막** 발생에만 포함되어 있습니다.
  ![Lint, 시작](assets/limitonlast.png)
* 사용된 시리즈는 컨테이너에 따라 다릅니다. **[!UICONTROL 개인]** 컨테이너를 사용하는 경우 일련의 이벤트가 세션이 됩니다. **[!UICONTROL 세션]** 컨테이너를 사용하는 경우, 일련의 모든 이벤트가 제공된 날짜 범위에서 지정된 사용자의 모든 이벤트 수가 됩니다.
* **[!UICONTROL 다음으로 시작]** 또는 **[!UICONTROL 다음으로 끝남]** 필드에서 지표 또는 차원 항목을 사용할 때 고급 설정에서 **[!UICONTROL 처음/마지막 발생으로 제한]** 옵션을 구성할 수 있습니다.


>[!MORELIKETHIS]
>
>[패널 내에 시각화 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[시각화 설정](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[시각화 컨텍스트 메뉴](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

