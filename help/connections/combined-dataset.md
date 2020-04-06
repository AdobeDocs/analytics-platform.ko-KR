---
title: 데이터 세트 결합
description: CJA에서 데이터 세트를 결합하여 연결을 만드는 방법을 알아봅니다.
translation-type: tm+mt
source-git-commit: 2dab33dca173fcc0eab657b810e85e4740e5d7e0

---


# 데이터 세트 결합

연결을 만들 때 CJA는 모든 스키마와 데이터 집합을 단일 데이터 집합으로 결합합니다. 이 &#39;결합된 데이터 집합&#39;은 CJA가 보고에 사용하는 데이터입니다. 연결에 여러 스키마 또는 데이터 세트를 포함하는 경우:

* 스키마가 결합됩니다. 중복된 스키마 필드가 병합됩니다.
* 각 데이터 집합의 &#39;개인 ID&#39; 열은 이름과 상관없이 단일 열로 병합됩니다. 이 열은 CJA에서 고유 방문자를 식별하는 기반입니다.
* 행은 타임스탬프를 기반으로 처리됩니다.

## 예

다음 예를 고려하십시오. 데이터 집합이 두 개 있는데, 각각 다른 데이터가 들어 있는 필드가 다릅니다.

>[!NOTE] Adobe Experience Platform은 일반적으로 타임스탬프를 Unix 밀리초 단위로 저장합니다. 이 예에서 가독성을 위해 날짜 및 시간이 사용됩니다.

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

이 두 데이터 집합을 사용하여 연결을 만들 때 다음 표를 보고에 사용합니다.

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

이 결합된 데이터 집합은 보고에 사용되는 데이터 집합입니다. 행의 데이터 집합은 중요하지 않습니다.CJA는 모든 데이터를 동일한 데이터 세트에 있는 것처럼 처리합니다. 일치하는 사람 ID가 두 데이터 세트에 모두 나타나면 동일한 고유 방문자로 간주됩니다. 30분 이내에 타임스탬프가 있는 데이터 세트 모두에 일치하는 사람 ID가 나타나면 동일한 세션의 일부로 간주됩니다.

이 개념은 기여도에 적용됩니다. 행의 데이터 집합은 중요하지 않습니다.기여도 분석은 모든 이벤트가 단일 데이터 세트에서 온 것처럼 정확히 작동합니다. 위의 표를 예로 사용:

연결에 첫 번째 테이블만 포함되고 두 번째 테이블이 아닌 경우 마지막 터치 속성을 사용하여 `string_color` 차원 및 `metric_a` 지표를 사용하여 보고서를 가져오면 다음이 표시됩니다.

| string_color | metric_a |
| --- | --- |
| 파란색 | 5 |
| 지정되지 않음 | 6 |
| 빨간색 | 2 |

하지만 두 테이블을 모두 연결에 포함하면 두 데이터 세트에 있기 때문에 속성이 `user_847` 변경됩니다. 두 번째 데이터 집합 속성에서 이전에 지정되지 `metric_a` 않은 &#39;노란색&#39;으로의 행:

| string_color | metric_a |
| --- | --- |
| 노란색 | 6 |
| 빨간색 | 2 |
| 파란색 | 3 |
