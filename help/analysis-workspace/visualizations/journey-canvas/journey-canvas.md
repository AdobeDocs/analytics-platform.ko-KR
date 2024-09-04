---
description: 여정 캔버스 개요
title: 여정 캔버스
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 2f42c64443cc5798388287e6f84b125fb8694812
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 3%

---

# 여정 캔버스 개요

{{release-limited-testing}}

여정 캔버스 시각화를 사용하면 사용자와 고객에게 제공하는 여정을 분석하고 심도 있는 통찰력을 얻을 수 있습니다. 이를 통해 여정을 처음부터 정의하거나 Journey Optimizer에서 하나를 본 다음, 사람들이 여정을 어떻게 떠나고(빠짐) 계속 지나가는지를 확인할 수 있습니다.

이벤트, 차원 항목, 필터 및 날짜 범위의 조합을 사용하여 [사용자 여정 분석을 빌드](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)하여 여정 노드를 만들 수 있습니다. 노드를 연결하여 여정의 흐름을 만들고, 여러 경로와 의사 결정 지점을 포함합니다. 캔버스에서 노드를 드래그하여 여정의 이벤트 및 조건을 재배열합니다. 데이터를 변경할 때 실시간으로 업데이트됩니다.

## 주요 기능

여정 캔버스 시각화의 주요 기능은 다음과 같습니다.

* 가장 복잡한 사용자 여정을 수용하는 폴아웃 및 폴스루에 대한 심층 분석.

* 사용자 여정의 다양한 진입점, 노드 및 경로를 매핑하고 시각화하기 위한 캔버스입니다.

* 캔버스에 구성 요소를 추가하고 기존 노드의 위치를 변경하기 위한 드래그 앤 드롭 상호 작용

* 여정 캔버스 내에서 사용자 여정 분석을 작성하거나 Journey Optimizer 여정을 기반으로 자동으로 생성하는 옵션입니다.

## 잠재적 인사이트

다음은 여정 캔버스에서 제공하는 데 도움이 되는 통찰력 유형의 몇 가지 예입니다. 이러한 인사이트가 데이터 보기의 모든 사람을 기반으로 하는지 또는 여정을 시작한 모든 사람을 기반으로 하는지 선택할 수 있습니다.

**폴스루**

* 여정을 완료한(종료 노드에 도착한) 사람의 수와 백분율

* 여정의 특정 지점(노드)에 도착한 사람의 수와 백분율

* 여정의 지정된 지점(노드) 이후 또는 이전에 발생한 가장 일반적인 단계

**폴아웃**

* 사람들이 가장 일반적으로 여정에서 떨어진 여정 지점(노드)

**기타**

* (노드에 대한 분류 차원을 추가하여) 여정의 모든 노드에 대한 추가 데이터


## 여정 캔버스와 폴아웃 시각화 중 선택

여정 캔버스 시각화는 사용자가 페이지의 사전 정의된 순서를 떠나고(폴아웃) 계속 따라가는(폴스루) 위치를 표시한다는 점에서 [폴아웃 시각화](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)와 유사합니다.

그러나 중요한 차이점이 있습니다.

### 차이점 이해

다음 표는 여정 캔버스 시각화 및 폴아웃 시각화에서 지원되는 분석 유형을 보여 줍니다.

| 함수 | 여정 캔버스 시각화 | 폴아웃 시각화 |
|---------|----------|---------|
| 선형 여정 | 예 | 예 |
| 여러 진입점 및 경로가 있는 비선형 여정 | 예 | 아니요 |
| Adobe Journey Optimizer 여정 | 예 | 아니요 |
| 기본 지표 | 계산된 지표를 포함한 모든 지표 | 세션 또는 사용자 지표만 사용할 수 있습니다. |
| 보조 지표 | 예<p>계산된 지표를 포함한 모든 지표</p> | 아니요 |
| 필터 비교 | 아니요 | 예<p>[무제한 필터 비교](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#compare-filters-in-fallout)</p> |

### 사용할 시각화 선택

여정 캔버스 사용과 폴아웃 중 하나를 선택하기 전에 [둘 사이의 차이점을 파악하십시오](#understand-the-differences).

여정 폴아웃 분석에 시작과 끝이 모두 알려진 선형 분석만 포함된 경우 이러한 보다 간단한 사용자 여정을 위해 [폴아웃 시각화](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)를 더 간단한 옵션으로 사용하는 것이 좋습니다.

여정 캔버스는 여러 진입점 및 경로가 있는 여정을 포함하는 폴아웃 분석이나 Journey Optimizer에서 생성된 여정을 분석하는 데 필수적입니다.

## Journey Optimizer 여정 분석

>[!NOTE]
>
>조직에 Journey Optimizer에 대한 액세스 권한이 없는 경우에도 [여정 캔버스에서 분석을 빌드](#build-analyses-in-customer-journey-analytics)할 수 있습니다.

여정 캔버스에서 Journey Optimizer 여정을 분석하면 사람들이 여정과 상호 작용하는 방법에 대한 깊고 실행 가능한 통찰력을 제공합니다.

여정 캔버스에서 Journey Optimizer 여정을 분석할 때 여정은 Journey Optimizer에서와 동일한 순서, 시퀀스 및 구조로 표시됩니다. 여정 캔버스 내에서 여정을 변경할 수 있는 경우 [변경 내용이 더 이상 Journey Optimizer에서 동기화되지 않습니다](#synchronization-between-journey-optimizer-and-journey-canvas).

### 여정 캔버스로 Journey Optimizer 여정 분석의 이점

여정 캔버스는 Journey Optimizer에서 가능하지 않은 심층적이고 철저한 분석을 제공합니다.

여정 캔버스를 사용하여 Journey Optimizer에서 생성된 여정을 분석하면 다양한 이점이 있습니다.

* Customer Journey Analytics 차원, 지표, 필터 또는 날짜 범위를 사용하여 이벤트를 만듭니다.

  Journey Optimizer에서 기술 사용자는 이벤트를 만든 후에 여정에 추가해야 합니다.

* 생성하는 사용자 지정 노드를 기반으로 대상을 만듭니다(Customer Journey Analytics 대상 빌더 시작).

  Journey Optimizer에서는 사전 정의된 활동에 대해서만 대상을 만들 수 있습니다.

* 폴스루 및 폴아웃 분석

* 모든 차원으로 이벤트 분류

* 이벤트 결합

* 이벤트 연결

* 이벤트 이름 변경 및 삭제

* 훨씬 더

### Journey Optimizer과 여정 캔버스 간 동기화

여정 캔버스에서 Journey Optimizer 여정 분석을 만들면 데이터가 Journey Optimizer에서 여정 캔버스에 이르기까지 한 방향으로만 동기화됩니다. 즉, 여정 캔버스에서 여정에 수행된 변경 사항이 Journey Optimizer에 반영되지 않습니다.

또한, Journey Optimizer의 여정에 대한 변경 사항은 여정이 여정 캔버스에서 수정되지 않은 상태로 유지되는 경우에만 여정 캔버스와 동기화됩니다. 여정 캔버스에서 여정을 수정한 후에는 Journey Optimizer의 여정에 대한 모든 변경 사항이 여정 캔버스에 반영되지 않습니다. 여정 캔버스에 반영된 변경 내용을 보려면 여정 캔버스에서 여정을 삭제하고 [다시 만들 수 있습니다](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### 여정 캔버스에서 여정 수정 후의 차이점 {#differences-after-modifying}

여정 캔버스에서 Journey Optimizer 여정을 수정한 후에는 데이터 처리, 사용 가능한 기능 및 동기화 동작이 변경될 수 있습니다.

>[!NOTE]
>
>여정을 원래 상태로 되돌리려면 여정 캔버스에서 첫 번째 변경 작업을 수행한 후 Ctrl+z를 누를 수 있습니다. 또는 여정 캔버스에서 여정을 삭제하고 [다시 만들 수 있습니다](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### 데이터 처리 차이

여정 캔버스에서 Journey Optimizer 여정을 수정한 후 여정에 기본값이 아닌 속성 모델이 있는 지표가 포함된 경우 데이터가 변경되는 것을 볼 수 있습니다.

이는 Journey Optimizer과 달리 여정 캔버스를 사용하면 단일 여정 내에서 여러 차원을 적용할 수 있기 때문입니다. 이 기능은 [지표 속성](/help/data-views/component-settings/attribution.md)이 지원되지 않음을 의미합니다.

#### 기능 차이점

여정 캔버스에서 Journey Optimizer 여정을 수정한 후에는 [!UICONTROL **노드 유형**] 드롭다운 필드를 더 이상 사용할 수 없습니다.

이 필드에 대한 자세한 내용은 [설정 구성](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)을 참조하십시오.

#### 동기화 차이점

Journey Optimizer의 여정에 대한 변경 사항은 여정이 여정 캔버스에서 수정되지 않은 상태로 유지되는 경우에만 여정 캔버스와 동기화됩니다.

여정 캔버스에서 Journey Optimizer 여정을 수정한 후에는 Journey Optimizer의 여정에 대한 모든 변경 사항이 여정 캔버스에 반영되지 않습니다. 여정 캔버스에 반영된 변경 내용을 보려면 여정 캔버스에서 여정을 삭제하고 [다시 만들 수 있습니다](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Journey Optimizer과 Customer Journey Analytics 간의 용어 차이점

Journey Optimizer에서 한 가지를 의미하는 특정 용어는 Customer Journey Analytics에서 다른 의미를 갖습니다. 여정 캔버스를 사용할 때는 Customer Journey Analytics 용어가 사용됩니다.

| 용어 | 여정 캔버스 | Journey Optimizer |
|---------|----------|---------|
| **이벤트** | Customer Journey Analytics에서 사용할 수 있는 여러 표준 지표 중 하나입니다. 이 지표는 생성된 매출, 구독 또는 리드와 같은 것을 계산합니다. | 온라인 구매와 같이 개인화된 여정을 트리거하는 활동의 카테고리입니다. |

### 여정 캔버스에서 Journey Optimizer 여정 분석

여정 캔버스에서 Journey Optimizer 여정을 분석하는 방법에 대한 자세한 내용은 [여정 캔버스 시각화 구성](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)을 참조하십시오.

## 여정 캔버스에서 분석 빌드

Analysis Workspace에서 사용할 수 있는 차원 또는 지표를 기반으로 하는 여정 캔버스에서 분석을 빌드할 수 있습니다. 또는 Journey Optimizer에서 생성된 여정을 분석할 수 있습니다. 자세한 내용은 [여정 캔버스 시각화 구성](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)을 참조하십시오.
