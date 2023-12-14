---
title: 결합 작동 방식
description: 결합 개념 이해
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 506838a0-0fe3-4b5b-bb9e-2ff20feea8bc
source-git-commit: 8ca11b37ebda952d95ae38473a9c0d62be007e79
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 21%

---

# 결합 작동 방식

결합은 주어진 데이터 세트의 데이터에 대해 최소 2개의 전달을 만듭니다.

* **라이브 결합**: 히트가 들어올 때 각 히트(이벤트)를 결합하려고 합니다. 데이터 세트에 &quot;신규&quot;(인증되지 않음)인 디바이스의 히트는 일반적으로 이 수준에서 결합되지 않습니다. 이미 인식된 디바이스의 히트는 즉시 결합됩니다.

* **재생 결합**: 학습한 고유 식별자(임시 ID)를 기반으로 데이터를 &quot;재생&quot;합니다. 이 단계에서 이전에 알 수 없었던 장치(영구 ID)의 히트가 임시 ID에 결합됩니다. Adobe에서는 두 개의 재생 간격을 제공합니다.
   * **매일**: 데이터는 매일 24시간 전환 확인 기간으로 재생됩니다. 이 옵션은 재생이 훨씬 빈번한 이점이 있지만 인증되지 않은 방문자는 사이트를 방문하는 당일 인증해야 합니다.
   * **매주**: 데이터는 일주일에 한 번, 7일 전환 확인 기간으로 재생됩니다. 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 그러나 1주일 미만의 연결되지 않은 데이터는 다음 주간 재생까지 재처리되지 않습니다.

* **개인 정보(선택 사항)**: 개인 정보 보호 관련 요청이 수신되면 요청된 ID를 제거하는 것 외에도 인증되지 않은 이벤트에서 해당 ID의 결합을 실행 취소해야 합니다.

조회 창을 벗어난 데이터는 재생되지 않습니다. 방문자는 인증되지 않은 방문과 인증된 방문을 함께 식별하기 위해 주어진 전환 확인 창에서 인증해야 합니다. 디바이스가 인식되면 해당 시점부터 라이브로 결합됩니다.

## 1단계: 라이브 결합

라이브 결합은 수집 시 각 이벤트를 알려진 디바이스와 채널에 결합하려고 합니다. Bob이 다른 이벤트를 이벤트 데이터 세트의 일부로 기록하는 다음 예를 생각해봅시다.

*수집된 날짜에 나타나는 데이터:*

| 이벤트 | 타임스탬프 | 영구 ID (쿠키 ID) | 임시 ID (로그인 ID) | 결합된 ID(라이브 결합 후) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **246** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 3 | 2023-05-12 12:03 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** |
| 5 | 2023-05-12 12:05 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | |
| 7 | 2023-05-12 12:07 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **81911** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** |
| | | **장치 3개** | | **4명**:<br/>246, Bob, 3579, 81911 |

새 디바이스에서 인증되지 않은 이벤트와 인증된 이벤트는 모두 별도의 사람(일시적으로)으로 계산됩니다. 인식된 디바이스의 인증되지 않은 이벤트는 라이브 결합됩니다.

속성은 식별 사용자 지정 변수가 디바이스에 연결되어 있을 때 작동합니다. 위의 예에서 이벤트 1, 8, 9 및 10을 제외한 모든 이벤트는 라이브로 결합됩니다(모두 `Bob` 식별자). 라이브 결합은 이벤트 4, 6 및 12에 대해 결합된 ID를 &quot;확인&quot;합니다.


<!--

### Delayed data

When incoming data for 'Live' stitching is delayed and over 24 hours old, and when no identities in that delayed data can be matched against identities already considered for 'Live' stitching, that delayed data is not added to the data considered for 'Live' stitching.

In the example below, the data in event 2 is delayed but will be part of 'Live' stitching.

| Event | Timestamp | Persistent ID (Cookie ID) | Transient ID (Login ID) | Stitched ID (after live stitch) | 
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| - | **246** |
| 2 | 2023-05-14 12:02 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |

In the example below, the data in event 2 is delayed and will NOT become part of 'Live' stitching.

| Event | Timestamp | Persistent ID (Cookie ID) | Transient ID (Login ID) | Stitched ID (after live stitch) | 
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| - | **246** |
| ~~2~~ | ~~2023-05-14 12:02~~ | ~~891~~ |  | (not considered for 'Live' stitching) |

-->


## 2단계: 재생 결합

정기적으로(선택한 전환 확인 기간에 따라 주 1회 또는 매일 한 번) 재생 결합은 현재 인식되는 디바이스를 기반으로 내역 데이터를 다시 계산합니다. 디바이스가 인증되지 않은 상태에서 처음에 데이터를 보낸 다음 로그인하는 경우 재생 결합은 인증되지 않은 이벤트를 올바른 사용자에게 연결합니다. 다음 테이블은 위와 동일한 데이터를 나타내지만 데이터 재생에 따라 다른 숫자를 표시합니다.

*재생 후 동일한 데이터:*

| 이벤트 | 타임스탬프 | 영구 ID (쿠키 ID) | 임시 ID (로그인 ID) | 결합된 ID(라이브 결합 후) | 결합된 ID(재생 후) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![위쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob |
| 5 | 2023-05-12 12:05 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob |
| 7 | 2023-05-12 12:07 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![위쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob |
| | | **장치 3개** | | **4명**:<br/>246, Bob, 3579, 81911 | **2명**:<br/>Bob, 3579 |

{style="table-layout:auto"}

속성은 식별 사용자 지정 변수가 디바이스에 연결되어 있을 때 작동합니다. 위의 예에서, 이벤트 1과 10은 재생의 결과로서 결합되며, 이벤트 8과 9만 결합되지 않는다. 사람 지표(누적)를 2로 줄입니다.

## 3단계: 개인 정보 보호 요청

개인 정보 보호 요청을 받으면 원래 사용자 정보가 포함된 행이 이 동일한 사용자 정보가 포함된 결합된 ID와 함께 제거됩니다. 다음 테이블은 위와 동일한 데이터를 나타내지만, Bob에 대한 개인 정보 보호 요청이 처리 후 데이터에 미치는 영향을 보여 줍니다. Bob이 인증된 행은 다른 행에 대한 임시 ID로 Bob을 제거함과 함께 제거(2, 3, 5, 7 및 11)됩니다.

*Bob에 대한 개인 정보 보호 요청 후 동일한 데이터:*

| 이벤트 | 타임스탬프 | 영구 ID (쿠키 ID) | 임시 ID (로그인 ID) | 결합된 ID(라이브 결합 후) | 결합된 ID(재생 후) | 임시 ID (로그인 ID) | 결합된 ID(개인 정보 보호 요청 후) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** | - | 246 |
| 2 | 2023-05-12 12:02 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![위쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 12:03 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob | - | 246 |
| 5 | 2023-05-12 12:05 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob | - | 246 |
| 7 | 2023-05-12 12:07 | 246 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 12:03 | 3579 ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 9 | 2023-05-12 12:09 | 3579 ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** | - | 81911 |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![위쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob | - | 81911 |
| | | **장치 3개** | | **4명**:<br/>246, Bob, 3579, 81911 | **2명**:<br/>Bob, 3579 |  | **3명**:<br/>246,3579,81911 |


<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used (stitched ID) | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on a desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on a mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `1` (Bob) |
-->

## 요약

* 스티칭을 사용하면 알려진 장치에서 이벤트가 즉시 결합되지만, 새 장치나 인식할 수 없는 장치에서 이벤트가 즉시 결합되지는 않습니다.
* 데이터는 정기적으로 재생되며 식별하도록 인식된 디바이스에 따라 연결의 내역 데이터를 변경합니다.
* 라이브 결합 및 재생 결합은 하나의 데이터 세트에 대해 수행됩니다. 따라서 크로스 채널 분석을 수행하기 위해 다른 데이터 세트(예: 콜 센터 데이터)와 결합할 때 사용하는 것이 더 적합한 새로운 고급 데이터 세트가 생성됩니다.
* 개인 정보 보호 요청은 인증되지 않은 행으로 퍼진 ID를 제거합니다.
