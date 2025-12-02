---
title: 필드 기반 결합
description: 필드 기반 결합의 개념 및 작업에 대한 설명
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1776'
ht-degree: 9%

---

# 필드 기반 결합

필드 기반 결합에서는 이벤트 데이터 세트와 해당 데이터 세트에 대한 영구 ID(쿠키) 및 개인 ID를 지정합니다. 필드 기반 결합은 결합된 새 ID 열을 이벤트 데이터 세트에 추가하고 특정 영구 ID에 대한 개인 ID가 있는 행을 기반으로 이 결합된 ID를 업데이트합니다. <br/>Customer Journey Analytics을 독립 실행형 솔루션으로 사용할 때(Experience Platform Identity 서비스 및 관련 ID 그래프에 대한 액세스 권한이 없음) 필드 기반 결합을 사용할 수 있습니다. 또는 사용 가능한 ID 그래프를 사용하지 않으려는 경우입니다.

![필드 기반 결합](/help/stitching/assets/fbs.png)


## IdentityMap

필드 기반 결합은 다음 시나리오에서 [`identityMap` 필드 그룹](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)의 사용을 지원합니다.

- `identityMap` 네임스페이스에서 기본 ID를 사용하여 persistentID를 정의합니다.
   - 서로 다른 네임스페이스에 여러 개의 기본 ID가 있는 경우 네임스페이스의 ID가 탄력적으로 정렬되고 첫 번째 ID가 선택됩니다.
   - 단일 네임스페이스에 여러 개의 기본 ID가 있는 경우 사용 가능한 첫 번째 사전식 기본 ID가 선택됩니다.

  아래 예에서 네임스페이스 및 ID는 정렬된 기본 ID 목록과 마지막으로 선택한 ID를 생성합니다.

  <table style="table-layout:auto">
     <tr>
       <th>네임스페이스</th>
       <th>ID 목록</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>정렬된 ID 목록</th>
      <th>선택한 ID</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>


- `identityMap` 네임스페이스를 사용하여 영구 ID나 개인 ID 중 하나 또는 둘 다 정의합니다.
   - `identityMap` 네임스페이스에 영구 ID 또는 개인 ID에 대한 여러 값이 있는 경우 사용 가능한 첫 번째 사전 편집기가 사용됩니다.
   - 영구 ID와 개인 ID의 네임스페이스는 함께 사용할 수 없습니다.

  아래 예에서는 사용할 네임스페이스로 ECID를 선택했습니다. 이렇게 하면 정렬된 ID 목록이 표시되고 최종적으로 선택한 ID가 표시됩니다.

  <table style="table-layout:auto">
     <tr>
       <th>네임스페이스</th>
       <th>ID 목록</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>정렬된 ID 목록</th>
      <th>선택한 ID</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>

## 필드 기반 결합 작동 방식

결합은 주어진 데이터 세트의 데이터에 대해 최소 2개의 전달을 만듭니다.

- **라이브 결합**: 히트가 들어올 때 각 히트(이벤트)를 결합하려고 합니다. 데이터 집합에 대한 *new*(인증되지 않음)인 장치의 히트는 일반적으로 이 수준에서 결합되지 않습니다. 이미 인식된 디바이스의 히트는 즉시 결합됩니다.

- **재생 결합**: *재생* 고유 식별자(개인 ID)를 기반으로 하는 데이터입니다. 이 단계에서 이전에 알 수 없었던 디바이스(영구 ID)의 히트가 개인 ID에 결합됩니다. 재생은 **빈도** 및 **전환 확인 기간**&#x200B;의 두 매개 변수로 결정됩니다. Adobe은 다음과 같은 매개 변수의 조합을 제공합니다.
   - **일별 빈도에 대한 일별 전환 확인**: 데이터는 매일 24시간 전환 확인 기간으로 재생됩니다. 이 옵션은 재생이 훨씬 빈번한 이점이 있지만 인증되지 않은 프로필은 사이트를 방문하는 당일 인증해야 합니다.
   - **주별 빈도에 대한 주별 전환**: 매주 전환 확인 기간으로 일주일에 한 번 데이터를 재생합니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 그러나 1주일 미만의 연결되지 않은 데이터는 다음 주간 재생까지 재처리되지 않습니다.
   - **주별 전환 확인**: 데이터는 주별 전환 확인 기간을 사용하여 매주 한 번 재생됩니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 그러나 2주 미만의 연결되지 않은 데이터는 다음 주간 재생까지 재처리되지 않습니다.
   - **주별 빈도에 대한 월별 전환**: 매주 데이터는 월별 전환 확인 기간으로 재생됩니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 그러나 1개월 미만의 연결되지 않은 데이터는 다음 주간 재생까지 재처리되지 않습니다.

- **개인 정보 보호**: 개인 정보 보호 관련 요청이 수신되면 요청된 ID를 제거하는 것 외에도 인증되지 않은 이벤트에서 해당 ID의 모든 결합을 실행 취소해야 합니다.

  >[!IMPORTANT]
  >
  >개인 정보 보호 요청의 일부로서 결합 해제 프로세스는 2025년 초에 변경됩니다. 현재 결합 해제 프로세스는 알려진 최신 버전의 ID를 사용하여 이벤트를 다시 지정합니다. 이벤트를 다른 정체성으로 재지정하는 것은 바람직하지 않은 법적 결과를 가져올 수 있습니다. 이러한 문제를 해결하기 위해 2025년부터 새로운 결합 해제 프로세스는 영구 ID로 개인 정보 보호 요청의 대상인 이벤트를 업데이트합니다.
  > 


조회 창을 벗어난 데이터는 재생되지 않습니다. 프로필은 인증되지 않은 방문과 인증된 방문을 함께 식별하기 위해 주어진 전환 확인 기간 내에서 인증해야 합니다. 장치가 인식되면 해당 장치는 해당 시점부터 라이브로 결합됩니다.

### 1단계: 라이브 결합

라이브 결합은 수집 시 각 이벤트를 알려진 디바이스와 채널에 결합하려고 합니다.

+++ 세부 사항

Bob이 다른 이벤트를 이벤트 데이터 세트의 일부로 기록하는 다음 예를 생각해봅시다.

*수집된 날짜에 표시된 데이터:*

| 이벤트 | 타임스탬프 | 영구 ID (쿠키 ID) | 개인 ID | 결합된 ID(라이브 결합 후) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **장치 3개** | | **4명**:<br/>`246`, `Bob`, `3579`, `81911` |

새 디바이스에서 인증되지 않은 이벤트와 인증된 이벤트는 모두 별도의 사람(일시적으로)으로 계산됩니다. 인식된 디바이스의 인증되지 않은 이벤트는 라이브 결합됩니다.

속성은 식별 사용자 지정 변수가 디바이스에 연결되어 있을 때 작동합니다. 위의 예에서 이벤트 1, 8, 9 및 10을 제외한 모든 이벤트는 라이브로 결합됩니다(모두 `Bob` 식별자를 사용). 라이브 결합은 이벤트 4, 6 및 12에 대해 결합된 ID를 &quot;확인&quot;합니다.

지연된 데이터(타임스탬프가 24시간 이상 된 데이터)는 가장 높은 품질을 위해 현재 데이터 결합의 우선 순위를 지정하면서 &#39;최상&#39;으로 처리됩니다.

+++ 

### 2단계: 재생 결합

정기적으로(선택한 전환 확인 기간에 따라 주 1회 또는 매일 한 번) 재생 결합은 현재 인식되는 디바이스를 기반으로 내역 데이터를 다시 계산합니다. 디바이스가 인증되지 않은 상태에서 처음에 데이터를 보낸 다음 로그인하는 경우 재생 결합은 인증되지 않은 이벤트를 올바른 사용자에게 연결합니다.

+++ 세부 사항

다음 테이블은 위와 동일한 데이터를 나타내지만 데이터 재생에 따라 다른 숫자를 표시합니다.

*재생 후 동일한 데이터:*

| 이벤트 | 타임스탬프 | 영구 ID (쿠키 ID) | 개인 ID | 결합된 ID(라이브 결합 후) | 결합된 ID(재생 후) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![위쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![위쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **장치 3개** | | **4명**:<br/>`246`, `Bob`, `3579`, `81911` | **2명**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

속성은 식별 사용자 지정 변수가 디바이스에 연결되어 있을 때 작동합니다. 위의 예에서, 이벤트 1과 10은 재생의 결과로서 결합되며, 이벤트 8과 9만 결합되지 않는다. 사람 지표(누적)를 2로 줄입니다.

+++ 

### 3단계: 개인 정보 보호 요청

개인 정보 보호 요청을 받으면 결합된 ID가 개인 정보 보호 요청의 사용자 주제에 대한 모든 레코드에서 삭제됩니다.

+++ 세부 사항

다음 테이블은 위와 동일한 데이터를 나타내지만, Bob에 대한 개인 정보 보호 요청이 처리 후 데이터에 미치는 영향을 보여 줍니다. Bob이 인증된 행은 다른 행의 개인 ID로 Bob을 제거할 때 함께 제거(2, 3, 5, 7 및 11)됩니다.

*Bob에 대한 개인 정보 보호 요청 후의 동일한 데이터:*

| 이벤트 | 타임스탬프 | 영구 ID (쿠키 ID) | 개인 ID | 결합된 ID(라이브 결합 후) | 결합된 ID(재생 후) | 개인 ID | 결합된 ID(개인 정보 보호 요청 후) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![위쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![오른쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![아래쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![위쪽 화살표](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **장치 3개** | | **4명**:<br/>246, `Bob`, `3579`, `81911` | **2명**:<br/>Bob, `3579` |  | **3명**:<br/>`246`, `3579`, `81911` |

+++ 

## 사전 요구 사항

다음 사전 요구 사항은 필드 기반 결합에 특별히 적용됩니다.

- 결합을 적용할 Adobe Experience Platform의 이벤트 데이터 세트에는 프로필을 식별하는 데 도움이 되는 두 개의 열이 있어야 합니다.

   - 모든 행에서 사용할 수 있는 식별자인 **영구 ID**. 예를 들어 Adobe Analytics AppMeasurement 라이브러리에서 생성된 방문자 ID 또는 Adobe Experience Platform ID 서비스에서 생성된 ECID입니다.
   - 일부 행에서만 사용할 수 있는 식별자인 **개인 ID**. 예를 들어 프로필이 인증되면 해시된 사용자 이름 또는 이메일 주소입니다. 원하는 거의 모든 식별자를 사용할 수 있습니다. 결합에서는 이 필드를 실제 개인 ID 정보로 간주합니다. 최상의 결합 결과를 위해 개인 ID는 각 영구 ID에 대해 데이터 세트의 이벤트 내에서 한 번 이상 전송되어야 합니다. 이 데이터 세트를 Customer Journey Analytics 연결 내에 포함하려는 경우 다른 데이터 세트에도 유사한 공통 식별자가 있는 것이 좋습니다.

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## 제한 사항

다음 제한 사항은 특히 필드 기반 결합에 적용됩니다.

- 현재 재입력 기능은 한 단계로 제한됩니다(영구 ID를 개인 ID로). 여러 단계의 키 재입력(예: 영구 ID를 개인 ID로, 그 다음 다른 개인 ID로 변경)은 지원되지 않습니다.
- 디바이스를 여러 사용자가 공유하고 사용자 간 총 전환 수가 50,000개를 초과하는 경우 Customer Journey Analytics은 해당 디바이스에 대한 데이터 결합을 중지합니다.
- 조직에서 사용한 사용자 정의 ID 맵은 지원되지 않습니다.
- 결합은 대소문자를 구분합니다. Analytics 소스 커넥터를 통해 생성된 데이터 세트의 경우 Adobe은 개인 ID 필드에 적용되는 VISTA 규칙 또는 처리 규칙을 검토할 것을 권장합니다. 이 검토를 통해 이러한 규칙 중 동일한 ID의 새로운 형식을 도입하는 규칙이 없는지 확인합니다. 예를 들어 VISTA 또는 처리 규칙이 이벤트의 일부에서만 개인 ID 필드에 소문자를 도입하지 않는지 확인해야 합니다.
- 결합은 필드를 결합하거나 연결하지 않습니다.
- 개인 ID 필드에는 단일 유형의 ID(단일 네임스페이스의 ID)가 포함되어야 합니다. 예를 들어 개인 ID 필드는 로그인 ID와 이메일 ID의 조합을 포함해서는 안 됩니다.
- 동일한 영구 ID에 대해 동일한 타임스탬프에서 여러 이벤트가 발생하지만 개인 ID 필드에 다른 값이 있는 경우 결합을 통해 알파벳 순서를 기반으로 ID가 선택됩니다. 따라서 영구 ID A에 동일한 타임스탬프를 가진 두 개의 이벤트가 있고 이벤트 중 하나가 &quot;Bob&quot;을 지정하고 다른 하나는 &quot;Ann&quot;을 지정하는 경우 결합은 &quot;Ann&quot;을 선택합니다.
- 개인 ID에 자리 표시자 값이 포함된 시나리오(예: `Undefined`)에 주의하십시오. 자세한 내용은 [FAQ](faq.md)를 참조하십시오.
- 영구 ID와 개인 ID 모두에서 동일한 네임스페이스를 사용할 수 없습니다. 네임스페이스는 상호 배타적이어야 합니다.
