---
description: 여정 캔버스 개요
title: 여정 캔버스
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: tm+mt
source-wordcount: '1988'
ht-degree: 90%

---

# 여정 캔버스 개요 {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="여정 캔버스"
>abstract="사람들이 일련의 터치포인트를 어떻게 진행하거나 이탈하는지 보여 줍니다. 여러 진입점과 경로가 있는 여정에 사용하거나 Journey Optimizer에서 생성된 여정을 분석하는 데 사용합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="여정 캔버스"
>abstract="사람들이 정의된 여정을 어떻게 진행하거나 이탈하는지 분석합니다. 이벤트, 차원 항목, 세그먼트의 조합을 나타내는 유연한 노드 및 화살표 그래프를 만들어 사용자 여성 분석을 빌드합니다. 캔버스에서 노드를 드래그하여 여정의 이벤트와 조건을 재배열합니다. 데이터가 이에 따라 업데이트됩니다. <br/><br/>Adobe Journey Optimizer 이용이 가능한 고객은 기존 Journey Optimizer 여정을 분석할 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button"
>title="여정 캔버스"
>abstract="사람들이 일련의 터치포인트를 어떻게 진행하거나 이탈하는지 보여 줍니다. 여러 진입점과 경로가 있는 여정에 사용하거나 Journey Optimizer에서 생성된 여정을 분석하는 데 사용합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel"
>title="여정 캔버스"
>abstract="사람들이 정의된 여정을 어떻게 진행하거나 이탈하는지 분석합니다. 이벤트, 차원 항목, 세그먼트의 조합을 나타내는 유연한 노드 및 화살표 그래프를 만들어 사용자 여성 분석을 빌드합니다. 캔버스에서 노드를 드래그하여 여정의 이벤트와 조건을 재배열합니다. 데이터가 이에 따라 업데이트됩니다. <br/><br/>Adobe Journey Optimizer 이용이 가능한 고객은 기존 Journey Optimizer 여정을 분석할 수 있습니다."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_이 문서에서는_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;의 여정 캔버스 시각화를 설명합니다.<br/>**Adobe Analytics**&#x200B;에 동일한 시각화가 없습니다._

>[!ENDSHADEBOX]

여정 캔버스 시각화는 사용자와 고객에게 제공하는 여정을 분석하고 깊이 있는 인사이트를 얻을 수 있습니다. 이를 통해 여정을 처음부터 정의하거나 Journey Optimizer에서 여정을 본 다음 사람들이 어떻게 여정을 떠나거나(폴아웃) 따라가는지(폴스루) 확인할 수 있습니다.

이벤트, 차원 항목, 세그먼트 및 날짜 범위의 조합을 사용하여 [사용자 여정의 분석을 빌드](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)하여 여정 노드를 만들 수 있습니다. 노드를 연결하여 여정의 흐름을 만들고, 여러 경로와 결정 지점을 포함합니다. 캔버스에서 노드를 드래그하여 여정의 이벤트와 조건을 재배열합니다. 데이터를 변경하면 실시간으로 업데이트합니다.

[노드는](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) “최종 경로”로 연결되어 있으며, 이는 두 노드 간에 발생하는 이벤트와 상관없이 결국 한 노드에서 다른 노드로 이동하는 한 방문자 수가 계산된다는 것을 의미합니다. 사용자가 경로를 따라 이동할 수 있는 시간은 컨테이너 설정에 따라 결정됩니다.

![여정 캔버스](assets/journey-canvas.png)

## 주요 기능

여정 캔버스 시각화의 주요 기능은 다음과 같습니다.

* 가장 복잡한 사용자 여정에 맞춰 폴아웃과 폴스루에 대한 심층 분석.

* 사용자 여정의 다양한 진입점, 노드 및 경로를 매핑하고 시각화하는 캔버스.

* 캔버스에 구성 요소를 추가하고 기존 노드를 재배치하기 위한 끌어다 놓기 상호 작용.

* 여정 캔버스 내에서 사용자 여정 분석을 구축하거나 Journey Optimizer 여정을 기반해 자동으로 생성할 수 있는 옵션.

## 잠재적 인사이트

여정 캔버스는 가장 복잡한 여정에 대한 실행 가능한 인사이트를 제공합니다.

### 전환율이 가장 높은 경로 {#conversion-rate-caption}

여정 캔버스에서 가장 눈에 띄는 인사이트는 캔버스 상단에 캡션으로 표시되어 있습니다.

이 캡션은 여정의 모든 경로 중 전환율이 가장 높았던 경로를 요약한 것입니다.

여정에 여러 시작 노드가 포함된 경우 캡션은 다음과 같이 표시됩니다.

![여정 캔버스 인사이트 캡션](assets/journey-canvas-caption.png)

여정에 단일 시작 노드가 포함된 경우 캡션은 다음과 같이 표시됩니다.

![여정 캔버스 인사이트 캡션 단일 시작 노드](assets/journey-canvas-caption-singlestart.png)

이 캡션을 해석할 때 다음 사항을 고려해야 합니다.

* _경로_&#x200B;는 화살표로 연결된 시작 노드로 정의되며, 그 사이에는 여러 개의 노드가 연결되어 있습니다.

* 전환율 계산은 여정의 유형(여정에 포함된 시작 노드와 끝 노드의 수, 그리고 경로가 교차하는지 여부)에 따라 달라집니다.

  다음 테이블은 여정 유형에 따라 전환율을 계산하는 방법을 설명합니다.

  | 여정 유형 | 전환율 계산 | 예 |
  |---------|----------|---------|
  | **단일 시작 노드와 단일 종료 노드** | 전환율은 종료 노드의 수를 시작 노드의 수로 나누어 계산됩니다. | ![여러 시작점이 공통 노드로 수렴되는 여정](assets/journey-canvas-single-path.png) |
  | **단일 시작 노드와 여러 종료 노드** | 전환율은 가장 높은 수를 가진 종료 노드를 찾아서 그 수를 시작 노드의 수로 나누어 계산됩니다. | ![여러 시작점이 공통 노드로 수렴되는 여정](assets/journey-canvas-singlestart-multiend.png) |
  | **각 경로에는 단일 시작 노드와 단일 종료 노드가 포함된 여러 개의 독립 실행형 경로** | 전환율은 종료 노드의 수를 시작 노드의 수로 나누어 계산됩니다. 전환율이 가장 높은 경로는 캡션에 설명되어 있습니다. | ![여러 시작점이 공통 노드로 수렴되는 여정](assets/journey-canvas-multi-start-separate.png) |
  | **여정의 어느 지점에서든 공통 노드로 수렴하는 여러 시작 노드** | 전환율은 가장 높은 수를 가진 끝 노드를 찾아서 그 수를 가장 낮은 수를 가진 시작 노드의 수로 나누어 계산됩니다. | ![여러 시작점이 공통 노드로 수렴되는 여정](assets/journey-canvas-multi-start-converge.png) |

### 폴스루, 폴아웃 등

다음은 여정 캔버스가 제공할 수 있는 기타 인사이트의 몇 가지 예입니다. 이러한 인사이트가 데이터 보기에 있는 모든 사람, 여정을 시작한 모든 사람 또는 여정의 이전 노드에 있는 모든 사람을 기반으로 하는지 선택할 수 있습니다.

#### 폴스루

* 여정을 완료한 사람(종료 노드에 방문한 사람)의 수와 백분율

* 여정의 특정 노드에 방문한 사람들의 수와 비율

* 여정의 특정 노드 이후 또는 이전에 이루어진 가장 일반적인 단계

#### 폴아웃

* 사람들이 여정에서 가장 흔히 이탈하는 노드(직후 노드에 방문하지 못하는 노드)

#### 각 노드에 대한 추가 데이터

* 여정의 모든 노드에 분류 차원을 추가하여 해당 노드에 대한 추가 데이터 확인

## 여정 캔버스, 폴아웃 또는 플로우 시각화 중에서 선택

여정 캔버스 시각화는 [폴아웃 시각화](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) 및 [플로우 시각화](/help/analysis-workspace/visualizations/c-flow/flow.md)와 유사하지만 중요한 차이점이 있습니다.

### 차이점 이해

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 여정 캔버스 사용 시기

여정 캔버스는 다음의 경우에 필수적입니다.

* 여러 진입점과 경로가 있는 여정을 포함한 폴아웃 분석.

* 사전 정의된 페이지 시퀀스를 갖춘 여러 진입점과 경로가 있는 비선형 여정.

* 사전 정의된 여정을 기반으로 한 탐색적 애드혹 분석.

* 세션, 개인 또는 발생 횟수 외의 기본 지표가 필요한 분석.

* Adobe Journey Optimizer에서 시작된 여정에 대한 심층 분석.

[위의 테이블](#understand-the-differences)을 사용하여 여정 캔버스, 폴아웃, 플로우 시각화의 차이점을 이해하십시오.

## Journey Optimizer 여정 분석

>[!NOTE]
>
>조직에서 Journey Optimizer에 액세스할 수 없는 경우에도 [여정 캔버스에 분석을 구축](#build-analyses-in-customer-journey-analytics)할 수 있습니다.

여정 캔버스에서 Journey Optimizer 여정 분석은 사람들이 여정과 어떻게 상호작용하는지에 대한 깊고 실행 가능한 인사이트를 제공합니다.

Journey Optimizer 여정을 여정 캔버스에서 분석할 때 여정은 Journey Optimizer에서와 동일한 순서, 시퀀스, 구조로 표시됩니다. 여정 캔버스 내에서 여정을 크게 변경하면 [Journey Optimizer에서 더 이상 변경 사항이 동기화되지 않습니다](#synchronization-between-journey-optimizer-and-journey-canvas).

### 여정 캔버스를 사용하여 Journey Optimizer 여정을 분석하는 것의 이점

여정 캔버스는 Journey Optimizer에서는 불가능한 심층적이고 철저한 분석을 제공합니다.

Journey Optimizer에서 생성된 여정을 분석하기 위해 여정 캔버스를 사용하면 다양한 이점이 있습니다.

* Customer Journey Analytics 차원, 지표, 세그먼트 또는 날짜 범위를 사용하여 이벤트를 만듭니다.

  Journey Optimizer에서 기술 사용자는 이벤트를 먼저 생성한 후에 여정에 이벤트를 추가할 수 있습니다.

* 사용자가 만든 사용자 정의 노드를 기반으로 대상자를 만듭니다(Customer Journey Analytics 대상자 빌더 실행).

  Journey Optimizer에서는 미리 정의된 활동에 대해서만 대상자를 만들 수 있습니다.

* 폴스루와 폴아웃 분석

* 모든 차원의 이벤트 분류

* 이벤트 결합

* 이벤트 연결

* 이벤트 이름 변경 및 삭제

* 자세히

### Journey Optimizer와 여정 캔버스 간 동기화

Journey Optimizer과 여정 캔버스 간의 동기화를 이해하려면 다음 동작을 고려하십시오.

* **데이터 동기화는 단방향입니다**

  여정 캔버스에서 Journey Optimizer 여정에 대한 분석을 만든 후에 데이터가 Journey Optimizer에서 여정 캔버스로만 단방향으로 동기화됩니다. 즉, 여정 캔버스에서 여정에 적용된 변경 사항은 Journey Optimizer에 반영되지 않습니다.

* **여정 캔버스에서 여정을 수정하면 동기화가 중지됨**

  여정 캔버스에서 여정이 크게 수정되지 않은 경우에만 [여정 캔버스와 동기화되는 Journey Optimizer의 여정 변경](#differences-after-modifying-a-journey-in-journey-canvas). 여정 캔버스에서 여정을 수정한 후에는 Journey Optimizer에서 여정에 적용한 변경 사항이 여정 캔버스에 반영되지 않습니다. 여정 캔버스에 반영된 변경 사항을 보기 위해 [여정 캔버스에서 여정을 삭제하고 다시 만들 수 있습니다](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

* **&quot;모든 사람과 공유&quot; 링크를 사용하려면 Journey Optimizer에서 변경한 후 프로젝트가 Customer Journey Analytics에 저장되어야 합니다.**

  &quot;모든 사람과 공유&quot; 링크를 사용하는 경우 프로젝트가 Customer Journey Analytics에 저장될 때까지 Journey Optimizer에서 변경한 내용이 여정 캔버스에 반영되지 않습니다.

  &quot;모든 사람과 공유&quot; 링크에 대한 자세한 내용은 [프로젝트 공유](/help/analysis-workspace/curate-share/share-projects.md)에서 [모든 사람과 프로젝트 공유(더 이상 필요하지 않음)](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)를 참조하십시오.

### 여정 캔버스에서 여정을 수정한 후의 차이점 {#differences-after-modifying}

여정 캔버스에서 Journey Optimizer 여정을 수정한 후 데이터 처리, 사용 가능한 기능 및 동기화 동작이 변경될 수 있습니다.

여정 캔버스에서 Journey Optimizer 여정에 중요한 수정 사항이 있으면 데이터 처리, 사용 가능한 기능 및 동기화 동작에 변경이 발생할 수 있습니다. 중요한 수정 사항에는 다음 중 하나가 포함됩니다.

* 노드 추가 또는 제거

* 노드 사이에 화살표 추가 또는 제거

* 노드의 구성 요소 변경

여정 캔버스에서 Journey Optimizer 여정에 노드를 끌거나 분류를 추가하는 등 다른 변경 작업을 수행하는 경우 다음 섹션에서 설명하는 차이점은 적용되지 않습니다.

>[!NOTE]
>
>여정을 원래 상태로 되돌리려면 여정 캔버스에서 첫 번째 변경을 한 후 Ctrl+z를 누르면 됩니다. 또는 [여정 캔버스에서 여정을 삭제하고 다시 만들 수 있습니다.](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### 데이터 처리 차이점

여정 캔버스에서 Journey Optimizer 여정을 수정한 후 여정에 비기본 속성 모델이 있는 지표가 포함된 경우 데이터에 변경 사항이 있을 수 있습니다.

이는 Journey Optimizer와 달리 여정 캔버스를 사용하면 단일 여정 내에 여러 차원을 적용할 수 있기 때문입니다. 이 기능은 [지표 속성](/help/data-views/component-settings/attribution.md)이 지원되지 않음을 의미합니다.

#### 기능 차이점

여정 캔버스에서 Journey Optimizer 여정을 수정한 후 수정 사항에 따라 [!UICONTROL **화살표 설정**] 드롭다운 필드에서 사용할 수 있는 옵션이 변경됩니다. 자세한 내용은 [설정 구성](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)을 참조하십시오.

[!UICONTROL **노드 유형**] 필드는 Journey Optimizer에서만 사용할 수 있습니다. 여정 캔버스에서 Journey Optimizer 여정을 볼 때는 여정 캔버스에서 여정을 수정하든 상관없이 사용할 수 없습니다.

#### 동기화 차이점

Journey Optimizer에서 여정의 변경 사항은 여정 캔버스에서 수정되지 않은 상태로 남아 있는 경우에만 여정 캔버스와 동기화됩니다.

여정 캔버스에서 Journey Optimizer 여정을 수정한 후에는 Journey Optimizer에서 여정에 적용한 변경 사항이 여정 캔버스에 반영되지 않습니다. 여정 캔버스에 반영된 변경 사항을 보기 위해 [여정 캔버스에서 여정을 삭제하고 다시 만들 수 있습니다](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Journey Optimizer 및 Customer Journey Analytics 간의 용어 차이

Journey Optimizer에서 한 가지 의미를 갖는 특정 용어는 Customer Journey Analytics에서 다른 의미를 갖습니다. 여정 캔버스를 사용할 때 Customer Journey Analytics 용어가 사용됩니다.

| 용어 | 여정 캔버스 | Journey Optimizer |
|---------|----------|---------|
| **이벤트** | Customer Journey Analytics에서 사용할 수 있는 여러 가지 표준 지표 중 하나입니다. 이 지표는 생성된 매출, 구독 또는 리드와 같은 것을 계산합니다. | 온라인 구매와 같은 개인화된 여정을 촉발하는 활동 카테고리. |

### 여정 캔버스에서 Journey Optimizer 여정 분석

여정 캔버스에서 Journey Optimizer 여정 분석에 대한 정보는 [여정 캔버스 시각화 구성](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)을 참조하십시오.

## 여정 캔버스에서 분석 구축

Analysis Workspace에서 사용할 수 있는 모든 차원이나 지표를 기반으로 한 분석을 여정 캔버스에 구축할 수 있습니다. 또는 Journey Optimizer에서 생성된 여정을 분석할 수 있습니다. 자세한 내용은 [여정 캔버스 시각화 구성](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)을 참조하십시오.


>[!MORELIKETHIS]
>
> * [Adobe Customer Journey Analytics의 여정 캔버스 시각화 가이드](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857?profile.language=ko)

