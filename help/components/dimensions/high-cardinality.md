---
title: 높은 카디널리티 차원
description: Customer Journey Analytics에서 고유한 값이 많은 차원을 처리하는 방법을 설명합니다.
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
role: User
TQID: https://experienceleague.adobe.com/cDOJq7Dc6x301enIo7h-cm8pGphmnvQAihnLoYGIr-A
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 622
ht-degree: 11%

---

# 높은 카디널리티 차원

고유 값이 많은 차원을 사용하는 경우 결과 보고서에 표시하거나 계산할 고유 차원 항목이 너무 많이 포함될 수 있습니다. 가장 중요하지 않은 것으로 간주되는 차원 항목을 제거하여 결과가 잘립니다. 이러한 최적화는 프로젝트 및 제품 성능을 유지하기 위해 수행됩니다.

고유 값이 너무 많은 차원이 포함된 보고서를 요청하면 Analysis Workspace는 차원 헤더에 모든 차원 항목이 포함되지 않았음을 알리는 표시기를 표시합니다. 예를 들어 **[!UICONTROL 행: 22,343,156]**&#x200B;을 초과하는 1~50개 **[!UICONTROL more]** 키워드는 가장 중요한 차원 항목을 반환하기 위해 일부 최적화가 보고서에 적용되었음을 나타냅니다.

![22,343,156 이상 중 1~50개를 표시하는 &quot;초과&quot; 키워드를 표시하는 Workspace의 자유 형식 테이블](assets/high-cardinality.png)

## 표시할 차원 항목 결정

Customer Journey Analytics은 보고서가 실행될 때 보고서를 처리하여 결합된 데이터 세트를 여러 서버에 배포합니다. 데이터 요청의 크기와 사용 가능한 Adobe 하드웨어의 양은 보고서를 처리하기 위해 할당된 서버 수를 결정하는 데 도움이 되는 많은 요소 중 두 가지입니다. 서버는 동적으로 할당되고 인터페이스에 표시되지 않으므로 보고서를 처리하는 서버 수를 보거나 제어할 수 있는 방법이 없습니다.

처리 서버당 데이터는 개인 ID별로 그룹화됩니다. 즉, 단일 처리 서버에 지정된 사용자에 대한 모든 데이터가 포함됩니다. 서버가 처리를 완료하면 처리된 데이터의 하위 집합을 애그리게이터 서버에 전달합니다. 처리된 데이터의 모든 하위 집합이 결합되어 작업 영역 보고서 형식으로 반환됩니다.

개별 서버가 고유한 임계값을 초과하는 데이터를 처리하는 경우 처리된 데이터 하위 집합을 반환하기 전에 결과를 자릅니다. 정렬에 사용되는 지표를 기반으로 잘린 차원 항목이 결정됩니다.

정렬 지표가 계산된 지표인 경우 서버는 계산된 지표 내의 지표를 사용하여 자를 차원 항목을 결정합니다. 계산된 지표는 다양한 중요도의 여러 지표를 포함할 수 있으므로 결과의 정확도가 떨어질 수 있습니다. 예를 들어 &quot;1인당 수익&quot;을 계산할 때 총 수익 금액과 총 인원수는 분할을 수행하기 전에 반환되고 집계됩니다. 그 결과, 각 개별 처리 서버는 결과가 전체 정렬에 어떤 영향을 미치는지 모른 채 제거할 항목을 선택합니다.

높은 카디널리티 보고서에서 일부 개별 차원 항목이 누락될 수 있지만 열 합계는 정확하며 잘린 데이터를 기반으로 하지 않습니다. [[!UICONTROL 근사 고유 개수]](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) 계산된 지표 함수도 잘린 차원 항목의 영향을 받지 않습니다.

## 높은 카디널리티 차원에 대한 우수 사례

높은 카디널리티 차원을 수용하는 가장 좋은 방법은 보고서가 처리하는 차원 항목의 수를 제한하는 것입니다. 모든 보고서는 요청된 시간에 처리되므로 즉각적인 결과를 위해 보고서 매개 변수를 조정할 수 있습니다. Adobe은 높은 카디널리티 차원에 대해 다음 최적화 중 하나를 권장합니다.

* [세그먼트](/help/components/segments/seg-create.md)를 사용합니다. 세그먼트는 각 서버가 데이터의 하위 집합을 처리할 때 적용됩니다.
* 검색을 사용합니다. 검색어에서 제외된 Dimension 항목은 보고서 결과에서 제거되므로 원하는 차원 항목을 볼 가능성이 높아집니다.
* 조회 데이터 세트 차원을 사용합니다. 조회 데이터 세트 차원은 이벤트 데이터 세트 차원 항목을 결합하여 반환되는 고유 값의 수를 제한합니다.
* 데이터 보기 관리자의 [포함/제외](/help/data-views/component-settings/include-exclude-values.md) 구성 요소 설정을 사용하십시오.
* 요청의 날짜 범위를 줄입니다. 시간이 지남에 따라 많은 고유 값이 누적되는 경우 Workspace 보고서의 날짜 범위를 줄이면 처리할 서버의 고유 값 수를 제한할 수 있습니다.
* 테이블의 모든 행을 반환하려면 [전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md)를 사용하는 것이 좋습니다.
* 고유 값의 수가 기본 포커스인 경우 [[!UICONTROL 근사 고유 개수]](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) 계산된 지표 함수를 사용하십시오.
