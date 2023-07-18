---
title: 결과가 잘린 차원 항목
description: 차원 항목 "결과가 잘림"과 보고에 표시되는 이유를 설명합니다.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: cf3c451cbefa7d6f9d5ea326c69fc2e5944881ff
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 13%

---

# 결과가 잘린 차원 항목

많은 고유 값이 포함된 차원을 사용할 때 보고서는 레이블이 지정된 차원 항목을 반환할 수 있습니다 **[!UICONTROL 결과가 잘림]**. 이 차원 항목은 요청된 보고서에 효율적으로 처리할 수 있는 고유 값이 너무 많이 포함되어 있음을 의미합니다. 그 결과, 가장 중요하지 않은 것으로 간주되는 항목을 제거합니다.

## Customer Journey Analytics 처리 아키텍처 및 고유 값

Customer Journey Analytics은 보고서가 실행될 때 보고서를 처리하여 결합된 데이터 세트를 여러 서버에 배포합니다. 처리 서버당 데이터는 사용자 ID별로 그룹화되며, 이는 단일 처리 서버에 지정된 사용자에 대한 모든 데이터가 포함되어 있음을 의미합니다. 서버가 처리를 완료하면 처리된 데이터의 하위 집합을 애그리게이터 서버에 전달합니다. 처리된 데이터의 모든 하위 집합이 결합되어 작업 영역 보고서 형식으로 반환됩니다.

개별 서버가 크기 임계값을 초과하는 결과 세트를 집계하면 결과를 반환하기 전에 잘립니다. 이 최적화를 통해 네트워크 트래픽과 집계를 경계 이내로 유지하여 신속한 보고를 수행할 수 있습니다. 각 처리 서버는 자체 데이터 보기에서만 결과를 자르기 때문에 Analysis Workspace에 표시된 항목에 약간 벗어난 지표 값이 있을 수 있습니다.

서버는 정렬에 사용되는 지표를 기반으로 삭제할 차원 항목을 선택합니다. 정렬 지표가 계산된 지표인 경우 서버는 계산된 지표 내의 지표를 사용하여 자를 차원 항목을 결정합니다. 계산된 지표는 다양한 중요도의 여러 지표를 포함할 수 있으므로 결과의 정확도가 떨어질 수 있습니다. 예를 들어 &quot;1인당 수익&quot;을 계산할 때 총 수익 금액과 총 인원수는 분할을 수행하기 전에 반환되고 집계됩니다. 그 결과, 각 노드는 결과가 전체 정렬에 어떤 영향을 미치는지 모른 채 제거할 항목을 선택합니다.

## &#39;결과가 잘림&#39;과 &#39;낮은 트래픽&#39;의 차이점

이전 버전의 Adobe Analytics에서는 다른 처리 아키텍처가 사용되었습니다. 데이터는 수집된 시점에 처리되었습니다. Dimension 항목은 차원이 50만 개의 고유 값에 도달한 후 &quot;낮은 트래픽&quot;에 배치되었으며, 100만 개의 고유 값에서 보다 적극적인 필터링을 적용했습니다. &quot;고유 값&quot; 카운트는 매월 초에 재설정되었습니다. 처리된 데이터는 영구적이어서 “낮은 트래픽”에서 기존 데이터를 가져올 수 없습니다.

Customer Journey Analytics에서 차원 항목은 보고서 결과가 너무 큰 경우에만 잘립니다. 처리된 데이터는 영구적이지 않으므로 보고서를 수정하여 잘림을 줄이거나 제거할 수 있습니다.

## &#39;결과가 잘림&#39; 차원 항목 감소

&#39;결과가 잘림&#39; 차원 항목의 이벤트 수를 줄이려면 Adobe은 다음 중 하나를 권장합니다.

* 사용 [필터](/help/components/filters/create-filters.md). 필터는 각 서버가 데이터의 하위 집합을 처리할 때 적용됩니다. 반환되는 고유 값의 수를 제한하면 &#39;결과가 잘림&#39; 차원 항목이 줄어듭니다.
* 검색을 사용합니다. 검색을 사용하면 검색과 일치하지 않는 항목이 보고서 결과에서 제거되어 원하는 항목이 표시될 가능성이 높아집니다.
* 조회 데이터 세트 차원을 사용합니다. 조회 데이터 세트 차원은 이벤트 데이터 세트 차원 항목을 결합하여 반환되는 고유 값의 수를 제한합니다.