---
title: 유지 분석
description: 제품을 계속해서 사용하는 사용자의 수를 측정합니다.
feature: Adobe Product Analytics, Guided Analysis
keywords: 제품 분석
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '1259'
ht-degree: 3%

---

# 유지 분석 {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="유지"
>abstract="제품을 계속해서 사용하는 사용자의 수를 측정합니다."

<!-- markdownlint-enable MD034 -->

![유지](/help/assets/icons/Retention.svg) **[!UICONTROL 유지]** 분석은 사용자가 시간이 지남에 따라 제품을 계속 사용하는 방법을 측정하므로 제품 시장 적합도를 이해하는 데 도움이 됩니다. 분석은 다음 두 가지 중요한 이벤트를 기반으로 사용자를 계산합니다.

* 시작 이벤트: 사용자가 분석에 포함될 수 있는 자격을 부여하는 데 사용되는 이벤트입니다.
* 재방문 이벤트: 분석에서 재방문 사용자로 계산되기 위해 사용자가 관여해야 하는 하나 이상의 이벤트.

이 분석에서 차트의 x축은 사용자의 초기 시작 이벤트 이후의 시간을 나타내고, y축은 하나 이상의 반환 이벤트에 참여하는 사용자의 비율을 나타냅니다. 기간 간 유지 및 이탈을 모두 볼 수 있으며, 표시되는 기간은 쿼리 설정을 통해 사용자 지정할 수 있습니다. 차트 아래에 있는 테이블은 동일한 날짜에 시작 이벤트를 수행한 사용자 그룹인 개별 집단을 표시하는 옵션과 함께 집계된 데이터를 제공합니다.

>[!VIDEO](https://video.tv.adobe.com/v/3430503/?quality=12&learn=on)


## 사용 사례

이 분석의 사용 사례는 다음과 같습니다.

* **집단 분석**: 등록 또는 구매 등 사용자가 수행하는 작업을 기준으로 사용자를 집단으로 그룹화합니다. 이러한 그룹이 얼마나 잘 유지되는지 비교하고 각 그룹의 사용자 경험을 개선하는 접근 방법을 결정할 수 있습니다.
* **제품 시장 적합성**: 제품의 일반 사용량을 측정하고 유지 곡선으로 시각화합니다. 유지율이 높으면 제품 시장 적합도가 높아지고 곡선이 병합되는 곳에 따라 적합도에 도달하는 데 걸리는 시간이 표시됩니다. 이 분석을 전체 수준에서 보거나 개별 제품 기능별로 분류하여 보다 심층적인 통찰력을 얻을 수 있습니다.
* **구독 서비스 분석**: 제품에 구독 또는 다른 유형의 되풀이 매출 모델이 사용되는 경우 제품을 최대한 활용하는 사용자의 비율을 확인할 수 있습니다. 이러한 사용자가 나타내는 특정 특성과 행동을 식별할 수 있습니다.
* **사용자 참여**: 특정 유형의 사용자가 제품에 참여하는 방법을 평가하고, 돌아오는 빈도를 나란히 비교합니다. 다른 세그먼트보다 보존이 낮은 특정 세그먼트는 보유하고 있을 수 있는 잠재적인 하위 경험 개선에 대한 통찰력을 제공할 수 있습니다.

## 인터페이스

안내식 분석 인터페이스에 대한 개요는 [인터페이스](../overview.md#interface)를 참조하십시오. 다음 설정은 이 분석과 관련이 있습니다.

### 쿼리 레일

쿼리 레일을 사용하면 다음 구성 요소를 구성할 수 있습니다.

* **[!UICONTROL 이벤트 시작]**: 사용자가 분석에 포함할 수 있는 이벤트 기준입니다. 시작 이벤트에 참여하는 사용자는 테이블의 &quot;사용자&quot; 열에서 계산됩니다. 이 이벤트는 표시된 유지율에 대한 분모 역할을 합니다. 하나의 이벤트가 지원되며, 필요에 따라 속성 필터를 적용할 수 있습니다. 기본적으로 시작 및 반환 이벤트가 연결되어 있습니다. 즉, 사용자는 선택한 이벤트를 한 번 수행해야 집단에 포함되고, 반환 사용자로 계산되어야 합니다. 추가 메뉴에서 반환 작업을 포함 작업과 다르게 하려면 시작 및 반환 이벤트의 연결을 해제할 수 있습니다.
* **[!UICONTROL 이벤트 반환]**: 기간 버킷에서 재방문 사용자로 계산되기 위해 사용자가 관여해야 하는 이벤트 기준입니다. 최대 3개의 반환 이벤트를 선택하여 보존 기간을 비교할 수 있습니다.
* **[!UICONTROL 다음 값으로 계산]**: 유지된 사용자에게 적용할 계산 메서드입니다. 옵션은 다음과 같습니다.
   * **[!UICONTROL 지표]**: [!UICONTROL 사용자]의 수 또는 [!UICONTROL 사용자 비율]을 유지합니다. 유지된 비율 사용자의 분모는 집단에 포함된 사용자이며 모든 기간 버킷에서 동일합니다.
   * **[!UICONTROL 재방문]**: 재방문 사용자를 계산하는 방법을 제어할 수 있습니다. 옵션은 다음과 같습니다.
      * **[!UICONTROL 다음 날짜 또는 다음 날짜]**: &quot;제한 없는&quot; 보존이라고도 하며, 이 옵션은 지정된 기간 또는 이후에 반환되는 사용자를 계산합니다. 예를 들어 7일에 또는 7일 이후 언제든지 이 옵션은 사용자가 계속 참여하는 방법을 보여 주고 결과적으로 더 부드러운 유지 곡선을 생성하는 데 유용합니다.
      * **[!UICONTROL 정확히]**: &quot;경계&quot; 보존이라고도 하는 이 옵션은 사용자가 지정된 기간에 정확히 반환되는 경우 사용자를 계산합니다. 예를 들어 정확히 7일에 이 옵션은 사용자가 특정 기간 내에 어떻게 반환하고 그 결과 더 많은 언듈레이션이 있는 유지 커브를 생성하는지를 보여주는 데 유용합니다. 참고: Analysis Workspace의 집단 분석은 분석 기준으로 &quot;정확히&quot; 계산을 사용합니다.
   * **[!UICONTROL 각]**: 각 기간 버킷을 지정할 기간입니다. 옵션은 다음과 같습니다.
      * **[!UICONTROL 일/주/월]**: 사용 가능한 옵션은 선택한 날짜 범위에 따라 다릅니다. 이러한 옵션은 날짜 범위를 선택할 때의 **[!UICONTROL 간격]** 설정과 동일하며 해당 설정을 자동으로 업데이트합니다.
      * **[!UICONTROL 사용자 지정 대괄호]**: 이 옵션은 &quot;각&quot; 설정에서만 사용할 수 있습니다. 이를 통해 더 큰 기간에 걸쳐 사용자를 카운트할 수 있습니다(예: 7일차가 아닌 7-10일).
   * **[!UICONTROL 기간 설정]**: 차트 및 표에 표시되는 기간 버킷을 제어할 수 있습니다. 기간은 시작 이벤트 후 반환 이벤트가 발생한 기간입니다. 참고: 기간 버킷에 적합한 사용자는 달력일이 아닌 경과 시간을 기반으로 합니다. 예를 들어, 사용자가 9월 6일 오후 11시 55분에 이벤트 자격을 얻은 후 9월 7일 오전 12시 5분에 반환 이벤트 자격을 얻은 경우 1일 기간 버킷에 표시되지 않습니다. 사용자가 1일 기간 버킷에 대한 자격을 얻으려면 전체 24시간이 경과해야 합니다. 사용 가능한 기간 버킷은 설정한 날짜 범위에 따라 다릅니다.
      * **[!UICONTROL 자동 기간]**&#x200B;은(는) 날짜 범위 길이와 날짜 범위가 현재 날짜와 얼마나 가까운지 기준으로 기간 버킷을 자동으로 정의합니다.
      * **[!UICONTROL 사용자 지정 기간]**&#x200B;을 사용하면 차트 및 표에 표시되는 4개의 기간 버킷을 사용자 지정할 수 있습니다.
* **[!UICONTROL 세그먼트]**: 측정하려는 세그먼트입니다. 선택한 각 세그먼트는 집단 테이블에 행을 추가합니다. 최대 3개의 세그먼트를 포함할 수 있습니다.

### 차트 설정

[!UICONTROL 유지] 분석에서는 차트 위의 메뉴에서 조정할 수 있는 다음과 같은 차트 설정을 제공합니다.

* **[!UICONTROL 차트 종류]**: 사용할 시각화 형식입니다. 옵션에는 [!UICONTROL Bar] 및 [!UICONTROL Line]이 있습니다.

### 날짜 범위

분석에 필요한 날짜 범위입니다. 이 설정에는 두 가지 구성 요소가 있습니다.

* **[!UICONTROL 간격]**: 보존 데이터를 보려는 날짜 세부 기간입니다. 유효한 옵션에는 일별, 주별 및 월별 옵션이 포함됩니다. 동일한 날짜 범위에는 다른 간격이 있을 수 있으며, 이는 기간 버킷 옵션에 영향을 줍니다.
* **[!UICONTROL 날짜]**: 시작 및 종료 날짜입니다. 롤링 날짜 범위 사전 설정 및 이전에 저장된 사용자 지정 범위는 편의상 사용하거나, 달력 선택기를 사용하여 고정 날짜 범위를 선택할 수 있습니다.

현재 날짜에 가까운 날짜 범위를 선택하면 처음에 현재 날짜에 너무 가깝게 참여하는 사용자는 포함되지 않습니다. 이 분석은 항상 모든 사용자에게 모든 기간 버킷에 포함될 수 있는 기회를 제공합니다. 달력 선택기 아래의 메시지는 사용자가 참여하는 날짜 범위와 재방문 사용자에게만 예약된 간격에 대한 정보를 제공합니다.

* **[!UICONTROL [날짜 간격]]**&#x200B;에서 이벤트를 시작한 사용자 분석: 사용자가 이 날짜 범위 내에서 이벤트를 사용하면 분석에 포함됩니다. 이 날짜 범위는 모든 사용자가 모든 기간 버킷을 사용할 수 있는 충분한 시간을 보장합니다. 이 날짜 범위는 현재 날짜에 근접한 경우 선택한 날짜 범위와 다를 수 있습니다.
* **[!UICONTROL 분석을 완료하기 위해 [날짜 간격]의 데이터가 예약되어 있습니다]**: 사용자가 이 기간 내에 처음 참여하는 경우 분석에 포함되지 않는 **데이터는**&#x200B;입니다. 최근 날짜 범위의 경우 이러한 사용자는 모든 기간 버킷에 대한 자격이 없습니다. 지난 날짜 범위의 경우 이러한 사용자는 선택한 날짜 범위를 벗어나서 활성화되었습니다.

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->