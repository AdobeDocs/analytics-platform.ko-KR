---
title: 결합된 이벤트 데이터 세트
description: CJA가 데이터 세트를 결합하여 연결을 만드는 방법을 알아봅니다.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
source-git-commit: 6b5f4659e9bae02e2665db3c0ee02d143dbc7ea0
workflow-type: ht
source-wordcount: '337'
ht-degree: 100%

---


# 결합된 이벤트 데이터 세트

연결을 만들면 CJA(Customer Journey Analytics)는 모든 스키마와 데이터 세트를 단일 데이터 세트에 결합합니다. 이 &#39;결합된 이벤트 데이터 세트&#39;는 CJA가 보고에 사용하는 것입니다. 연결에 여러 개의 스키마나 데이터 세트를 포함하는 경우:

* 스키마가 결합됩니다. 중복된 스키마 필드가 병합됩니다.
* 각 데이터 세트의 &#39;개인 ID&#39; 열은 이름과 관계없이 하나의 열에 병합됩니다. 이 열은 CJA에서 고유한 방문자를 식별하는 기반입니다.
* 행은 타임스탬프를 기반으로 처리됩니다.
* 이벤트는 밀리초 수준까지 해결됩니다.

## 예

다음과 같은 예를 살펴보십시오. 각각 다른 필드에 다른 데이터가 들어 있는 이벤트 데이터 세트가 두 개 있습니다.

>[!NOTE]
>
>Adobe Experience Platform은 일반적으로 타임스탬프를 Unix 밀리초 단위로 저장합니다. 이 예에서 가독성을 위해 날짜 및 시간이 사용됩니다.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |
| `user_310` | `1 Jan 7:04 AM` |  |  | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  | `3` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` |  |  | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  | `Triangle` | `3.1` |

이 두 이벤트 데이터 세트를 사용하여 연결을 만들 때 다음 표를 보고에 사용합니다.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |  |  |
| `user_310` | `1 Jan 7:04 AM` |  |  |  | `2` |  |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  |  | `3` |  |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` |  | `Circle` |  | `8.5` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` |  | `4` |  |
| `user_847` | `2 Jan 12:44 PM` |  |  |  | `2` |  |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` |  | `Square` |  | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  |  | `Triangle` |  | `3.1` |

이 결합된 이벤트 데이터 세트는 보고에서 사용되는 것입니다. 행이 어느 데이터 세트에 포함되어 있든 상관없습니다. CJA는 모든 데이터를 동일한 데이터 세트에 있는 것처럼 처리합니다. 일치하는 개인 ID가 두 데이터 세트에 표시되면 동일한 고유 방문자로 간주됩니다. 30분 내에 타임스탬프가 있는 두 데이터 세트에 일치하는 개인 ID가 표시되면 동일한 세션의 일부로 간주됩니다.

이 개념은 속성에도 적용됩니다. 행이 어느 데이터 세트에 포함되어 있든 상관없습니다. 속성은 모든 이벤트가 단일 데이터 세트에 포함된 것처럼 정확하게 작동합니다. 위의 표를 예로 사용합니다.

연결에 첫 번째 표만 포함되고 두 번째 표는 포함되지 않은 경우 `string_color` 차원을 사용하여 보고서를 가져오고 마지막 터치 속성을 사용하여 `metric_a` 지표를 가져오면 다음이 표시됩니다.

| string_color | metric_a |
| --- | --- |
| 지정되지 않음 | 6 |
| 파란색 | 3 |
| 빨간색 | 2 |

하지만 두 표를 모두 연결에 포함한 경우 `user_847`이 두 데이터 세트에 있으므로 속성 변경됩니다. 두 번째 데이터 세트 속성의 한 행 `metric_a`가 이전에 지정되지 않은 &#39;노란색&#39;이면 다음이 표시됩니다.

| string_color | metric_a |
| --- | --- |
| 노란색 | 6 |
| 파란색 | 3 |
| 빨간색 | 2 |
