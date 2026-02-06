---
title: 필드 기반 결합
description: 필드 기반 결합의 개념 및 작업에 대해 설명합니다.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: b5afcfe2cac8aa12d7f4d0cf98658149707123e3
workflow-type: tm+mt
source-wordcount: '1797'
ht-degree: 81%

---

# 필드 기반 결합

필드 기반 결합에서는 이벤트 데이터 세트와 해당 데이터 세트에 대한 영구 ID(쿠키) 및 개인 ID를 지정합니다. 필드 기반 결합은 특정 영구 ID와 함께 제공되는 모든 익명 이벤트에서 Customer Journey Analytics 데이터 분석에 개인 ID 정보를 사용할 수 있도록 하려고 합니다.  해당 정보는 특정 영구 ID에 대한 개인 ID가 있는 행에서 검색됩니다.

이벤트에 대한 개인 ID 정보를 검색할 수 없는 경우 해당 *연결되지 않은* 이벤트에 대해 영구 ID가 대신 사용됩니다. 결과적으로, 결합을 위해 활성화된 데이터 세트가 포함된 [연결](/help/data-views/data-views.md)과(와) 연결된 [데이터 보기](/help/connections/overview.md)에서 개인 ID 구성 요소는 이벤트 수준에서 개인 ID 값 또는 영구 ID 값을 포함합니다.

Customer Journey Analytics을 독립 실행형 솔루션으로 사용할 때(Experience Platform Identity 서비스 및 관련 ID 그래프에 대한 액세스 권한이 없음) 필드 기반 결합을 사용할 수 있습니다. 사용 가능한 ID 그래프를 사용하지 않으려는 경우도 마찬가지입니다.

![필드 기반 결합](/help/stitching/assets/fbs.png)


## IdentityMap

필드 기반 결합은 다음 시나리오에서 [`identityMap` 필드 그룹](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/schema/composition#identity)의 사용을 지원합니다.

- `identityMap` 네임스페이스에서 기본 ID를 사용하여 persistentID를 정의합니다.
   - 서로 다른 네임스페이스에 여러 개의 기본 ID가 있는 경우 네임스페이스의 ID가 사전순으로 정렬되고 첫 번째 ID가 선택됩니다.
   - 단일 네임스페이스에 여러 개의 기본 ID가 있는 경우, 알파벳순으로 첫 번째 가용 기본 ID가 선택됩니다.

  아래 예시에서 네임스페이스 및 ID는 정렬된 기본 ID 목록과 마지막으로 선택한 ID를 생성합니다.

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
   - `identityMap` 네임스페이스에 영구 ID 또는 개인 ID에 대한 값이 여러 개 있는 경우, 알파벳순으로 첫 번째 가용 값이 사용됩니다.
   - 영구 ID와 개인 ID의 네임스페이스는 상호 배타적이어야 합니다.

  아래 예제에서는 사용할 네임스페이스로 ECID를 선택했습니다. 이렇게 하면 정렬된 ID 목록이 생성되고 선택한 ID가 표시됩니다.

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

## 필드 기반 결합의 작동 방식

결합은 주어진 데이터 세트의 데이터에 대해 최소 2개의 전달을 만듭니다.

- **라이브 결합**: 각 히트(이벤트)가 들어올 때 히트를 결합하려고 합니다. 데이터 세트에 *새롭게 표시*&#x200B;되며 인증되지 않은 디바이스의 히트는 일반적으로 이 레벨에서 결합되지 않습니다. 이미 인식된 디바이스의 히트는 즉시 결합됩니다.

- **재생 결합**: 고유 식별자(개인 ID)를 기반으로 하는 데이터를 *재생*&#x200B;합니다. 이 단계에서 이전에 알려지지 않은 디바이스(영구 ID)의 히트가 개인 ID에 결합됩니다. 두 매개 변수가 재생을 결정합니다. **빈도** 및 **전환 확인 기간**. Adobe는 다음과 같은 매개 변수 조합을 제공합니다.
   - **일별 빈도에 대한 일별 전환 확인**: 데이터는 매일 24시간 전환 확인 기간으로 재생됩니다. 이 옵션은 재생이 훨씬 빈번한 이점이 있지만 인증되지 않은 프로필은 사이트를 방문하는 당일 인증해야 합니다.
   - **주별 빈도에 대한 주별 전환 확인**: 주별 전환 확인 기간으로 일주일에 한 번 데이터를 재생합니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 하지만 1주 미만의 미결합 데이터는 다음 주별 재생 시점까지 재처리되지 않습니다.
   - **주별 빈도에 대한 격주 전환 확인**: 격주 전환 확인 기간으로 일주일에 한 번 데이터를 재생합니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 하지만 2주 미만의 미결합 데이터는 다음 주별 재생 시점까지 재처리되지 않습니다.
   - **주별 빈도에 대한 월별 전환 확인**: 월별 전환 확인 기간으로 일주일에 한 번 데이터를 재생합니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 하지만 1개월 미만의 미결합 데이터는 다음 주별 재생 시점까지 재처리되지 않습니다.

- **개인정보**: 개인정보 보호 관련 요청이 수신되면 요청된 ID를 제거할 뿐 아니라 인증되지 않은 이벤트에서 해당 ID의 모든 결합을 실행 취소해야 합니다.

  >[!IMPORTANT]
  >
  >개인정보 보호 요청의 일부인 결합 해제 프로세스는 2025년 초에 변경됩니다. 현재의 결합 해제 프로세스는 알려진 ID의 최신 버전을 사용하여 이벤트를 다시 결합합니다. 이벤트를 다른 ID로 재할당하는 경우, 원하지 않은 법적 결과가 발생할 수 있습니다. 이러한 문제를 해결하기 위해 새로운 결합 해제 프로세스는 2025년부터 영구 ID로 개인정보 보호 요청의 대상인 이벤트를 업데이트합니다.
  > 


조회 창을 벗어난 데이터는 재생되지 않습니다. 인증되지 않은 방문과 인증된 방문을 함께 식별하려면 주어진 전환 확인 기간 내에서 프로필이 인증되어야 합니다. 디바이스가 인식되면 해당 지점부터 디바이스가 라이브 결합됩니다.

### 1단계: 라이브 결합

라이브 결합은 수집 시 개별 이벤트를 알려진 디바이스와 채널에 결합하려고 합니다.

+++ 세부 사항

Bob이 다른 이벤트를 이벤트 데이터 세트의 일부로 기록하는 다음 예제를 고려해 보겠습니다.

*수집된 날짜에 나타난 데이터:*

| 이벤트 | 타임스탬프 | 영구 ID(쿠키 ID) | 개인 ID | 결과 ID(라이브 결합 후) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **디바이스 3개** | | **4명**:<br/>`246`, `Bob`, `3579`, `81911` |

새 디바이스에서 인증되지 않은 이벤트와 인증된 이벤트는 모두 별도의 사람(일시적으로)으로 계산됩니다. 인식된 장치의 인증되지 않은 이벤트는 라이브 결합됩니다.

속성은 식별 사용자 정의 변수가 디바이스에 연결되면 작동합니다. 위의 예에서 이벤트 1, 8, 9, 10을 제외한 모든 이벤트는 라이브로 결합됩니다(모두 `Bob` 식별자를 사용). 라이브 결합은 이벤트 4, 6 및 12의 결과 ID를 &quot;확인&quot;합니다.

타임스탬프가 24시간 이상 된 데이터인 지연된 데이터는 최선의 노력으로 처리되며, 최상의 품질을 위해 현재 데이터를 우선 결합합니다.

+++ 

### 2단계: 재생 결합

정기적으로(선택한 전환 확인 기간에 따라 주 1회 또는 매일 한 번) 결합 재생은 현재 인식되는 디바이스를 기준으로 내역 데이터를 다시 계산합니다. 디바이스가 인증되지 않은 상태에서 처음에 데이터를 보낸 다음 로그인하는 경우 결합 재생은 인증되지 않은 이벤트를 올바른 사용자에게 연결합니다.

+++ 세부 사항

다음 테이블은 위와 동일한 데이터를 나타내지만 데이터 재생에 따라 다른 숫자를 표시합니다.

*재생 후 동일한 데이터:*

| 이벤트 | 타임스탬프 | 영구 ID(쿠키 ID) | 개인 ID | 결과 ID(라이브 결합 후) | 결과 ID(재생 후) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **디바이스 3개** | | **4명**:<br/>`246`, `Bob`, `3579`, `81911` | **2명**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

속성은 식별 사용자 정의 변수가 디바이스에 연결되면 작동합니다. 위의 예제에서 이벤트 1과 10은 재생의 결과로 결합되고 이벤트 8과 9만 결합되지 않습니다. 또한 인원 지표(누적)가 2로 줄어듭니다.

+++ 

### 3단계: 개인정보 보호 요청

개인 정보 보호 요청을 수신하면 개인 ID 값에 대한 결합 프로세스에서 설정된 모든 식별자 정보는 모든 레코드에서 개인 정보 보호 요청의 사용자 주체에 대한 영구 ID 값으로 업데이트됩니다.

+++ 세부 사항

다음 테이블은 위와 동일한 데이터를 나타내지만, Bob에 대한 개인정보 보호 요청이 요청 처리 후 데이터에 미치는 영향을 보여 줍니다. Bob이 인증된 행은 다른 행의 개인 ID로 Bob을 제거할 때 함께 제거됩니다(2, 3, 5, 7 및 11).

*Bob에 대한 개인정보 보호 요청 후의 동일한 데이터:*

| 이벤트 | 타임스탬프 | 영구 ID(쿠키 ID) | 개인 ID | 결과 ID(라이브 결합 후) | 결과 ID(재생 후) | 개인 ID | 결과 ID(개인 정보 보호 요청 이후) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Arrow Up](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **디바이스 3개** | | **4명**:<br/>246, `Bob`, `3579`, `81911` | **2명**:<br/>Bob, `3579` |  | **3명**:<br/>`246`, `3579`, `81911` |

+++ 

## 사전 요구 사항

다음 사전 요구 사항은 특히 필드 기반 결합에 적용됩니다.

- 결합을 적용할 Adobe Experience Platform의 이벤트 데이터 세트에는 프로필을 식별하는 데 도움이 되는 두 개의 열이 있어야 합니다.

   - 모든 행에서 사용 가능한 식별자인 **영구 ID**. 예를 들면 Adobe Analytics AppMeasurement 라이브러리에서 생성된 방문자 ID 또는 Adobe Experience Platform ID 서비스에서 생성된 ECID입니다.
   - **개인 ID**&#x200B;는 일부 행에서만 사용할 수 있는 식별자입니다. 예를 들어 프로필이 인증을 받은 후 해시된 사용자 이름 또는 이메일 주소입니다. 원하는 식별자를 거의 모두 사용할 수 있습니다. 결합에서는 이 필드를 실제 개인 ID 정보로 간주합니다. 최상의 결합 결과를 위해 개인 ID는 각 영구 ID에 대해 데이터 세트의 이벤트 내에서 한 번 이상 전송되어야 합니다. 이 데이터 세트를 Customer Journey Analytics 연결 내에 포함하려는 경우, 다른 데이터 세트에도 유사한 공통 식별자가 있는 것이 좋습니다.

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## 제한 사항

다음 제한 사항은 특히 필드 기반 결합에 적용됩니다.

- 현재 재입력 기능은 한 단계로 제한됩니다(영구 ID를 개인 ID로). 여러 단계의 키 재입력(예: 영구 ID를 개인 ID로, 그다음 다른 개인 ID로 변경)은 지원되지 않습니다.
- 여러 사람이 디바이스를 공유하고 사용자 간 총 전환 수가 50,000개를 초과하는 경우 Customer Journey Analytics은 해당 디바이스에 대한 데이터 결합을 중지합니다.
- 조직에서 사용한 사용자 정의 ID 맵은 지원되지 않습니다.
- 결합은 대/소문자를 구분합니다. Analytics 소스 커넥터를 통해 생성된 데이터 세트의 경우, Adobe는 개인 ID 필드에 적용되는 VISTA 규칙 또는 처리 규칙을 검토할 것을 권장합니다. 이러한 검토를 통해 동일한 ID의 새로운 형식을 도입하는 규칙이 없는지 확인할 수 있습니다. 예를 들어 VISTA 또는 처리 규칙이 이벤트의 일부에서만 개인 ID 필드에 소문자를 도입하지 않는지 확인해 보아야 합니다.
- 결합은 필드를 결합하거나 연결하지 않습니다.
- 개인 ID 필드는 단일 유형의 ID(단일 네임스페이스의 ID)를 포함해야 합니다. 예를 들어 개인 ID 필드는 로그인 ID와 이메일 ID의 조합을 포함해서는 안 됩니다.
- 동일한 영구 ID에 대해 동일한 타임스탬프에서 여러 이벤트가 발생하지만 개인 ID 필드의 값이 다른 경우, 결합은 알파벳 순서를 기반으로 ID를 선택하게 됩니다. 따라서 영구 ID A에 동일한 타임스탬프를 가진 두 개의 이벤트가 있고 이벤트 중 하나가 Bob을 지정하고 다른 하나는 Ann을 지정한다면 결합은 Ann을 선택합니다.
- 개인 ID에 자리 표시자 값이 포함된 시나리오(예: `Undefined`)에 주의하시기 바랍니다. 자세한 내용은 [FAQ](faq.md)를 참조하십시오.
- 영구 ID와 개인 ID 모두에 동일한 네임스페이스를 사용할 수 없습니다. 네임스페이스는 상호 배타적이어야 합니다.
