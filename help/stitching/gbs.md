---
title: 그래프 기반 결합
description: 그래프 기반 결합의 개념과 작업에 대해 설명합니다.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: 4c5376171afe7ee830c52cc1066d0645a1adbc5d
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 69%

---

# 그래프 기반 결합

그래프 기반 결합에서는 이벤트 데이터 세트, 해당 데이터 세트에 대한 영구 ID(쿠키) 및 ID 그래프에서 원하는 개인 ID 네임스페이스를 지정합니다. 그래프 기반 결합은 모든 이벤트에 대한 Customer Journey Analytics 데이터 분석에 개인 ID 정보를 사용할 수 있도록 합니다. 영구 ID는 Experience Platform ID 서비스에서 ID 그래프를 쿼리하여 지정된 네임스페이스에서 개인 ID를 얻는 데 사용됩니다.

이벤트에 대한 개인 ID 정보를 검색할 수 없는 경우 해당 *연결되지 않은* 이벤트에 대해 영구 ID가 대신 사용됩니다. 따라서 결합용으로 활성화된 데이터 세트가 포함된 [연결](/help/data-views/data-views.md)과(와) 연결된 [데이터 보기](/help/connections/overview.md)에서 개인 ID 데이터 보기 구성 요소는 이벤트 수준에서 개인 ID 값 또는 영구 ID 값을 포함합니다.


![그래프 기반 결합](/help/stitching/assets/gbs.svg)

## IdentityMap

그래프 기반 결합은 다음 시나리오에서 [`identityMap` 필드 그룹](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/schema/composition#identity)의 사용을 지원합니다.

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

- `identityMap` 네임스페이스를 사용하여 persistentID를 정의합니다.
   - `identityMap` 네임스페이스에 persistentID에 대한 값이 여러 개인 경우, 알파벳순으로 첫 번째 가용 ID가 사용됩니다.

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


## 그래프 기반 결합 작동 방식

결합은 주어진 데이터 세트의 데이터에 대해 최소 2개의 전달을 만듭니다.

- **라이브 결합**: ID 그래프를 쿼리하여 선택한 네임스페이스에 대한 개인 ID를 조회하기 위해 영구 ID를 사용하여 각 히트(이벤트)를 들어오는 대로 결합하려고 시도합니다. 조회에서 개인 ID를 사용할 수 있는 경우, 이 개인 ID가 즉시 결합됩니다.

- **재생 결합**: ID 그래프에서 업데이트된 ID를 기반으로 하는 *재생* 데이터입니다. 이 단계에서 ID 그래프가 네임스페이스에 대한 ID를 해결함으로써 이전에 알 수 없었던 디바이스(영구 ID)의 히트가 결합됩니다. 두 매개 변수가 재생을 결정합니다. **빈도** 및 **전환 확인 기간**. Adobe는 다음과 같은 매개 변수 조합을 제공합니다.
   - **일별 빈도에 대한 일별 전환 확인**: 데이터는 매일 24시간 전환 확인 기간으로 재생됩니다. 이 옵션은 재생이 훨씬 빈번한 이점이 있지만 인증되지 않은 프로필은 사이트를 방문하는 당일 인증해야 합니다.
   - **주별 빈도에 대한 주별 전환 확인**: 주별 전환 확인 기간으로 일주일에 한 번 데이터를 재생합니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 하지만 1주 미만의 미결합 데이터는 다음 주별 재생 시점까지 재처리되지 않습니다.
   - **주별 빈도에 대한 격주 전환 확인**: 격주 전환 확인 기간으로 일주일에 한 번 데이터를 재생합니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 하지만 2주 미만의 미결합 데이터는 다음 주별 재생 시점까지 재처리되지 않습니다.
   - **주별 빈도에 대한 월별 전환 확인**: 월별 전환 확인 기간으로 일주일에 한 번 데이터를 재생합니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 하지만 1개월 미만의 미결합 데이터는 다음 주별 재생 시점까지 재처리되지 않습니다.

- **개인정보**: 개인정보 보호 관련 요청이 수신되면 소스 데이터 세트에서 요청된 ID를 제거할 뿐 아니라 인증되지 않은 이벤트에서 해당 ID의 모든 결합을 실행 취소해야 합니다. 또한 특정 ID에 대한 향후 그래프 기반 결합을 방지하려면 ID 그래프에서 ID를 제거해야 합니다.

  >[!IMPORTANT]
  >
  >개인정보 보호 요청의 일부인 결합 해제 프로세스는 2025년 초에 변경됩니다. 현재의 결합 해제 프로세스는 알려진 ID의 최신 버전을 사용하여 이벤트를 다시 결합합니다. 이벤트를 다른 ID로 재할당하는 경우, 원하지 않은 법적 결과가 발생할 수 있습니다. 이러한 문제를 해결하기 위해 새로운 결합 해제 프로세스는 2025년부터 영구 ID로 개인정보 보호 요청의 대상인 이벤트를 업데이트합니다.
  > 

조회 창을 벗어난 데이터는 재생되지 않습니다. 인증되지 않은 방문과 인증된 방문을 함께 식별하려면 주어진 전환 확인 기간 내에서 프로필이 인증되어야 합니다. 디바이스가 인식되면 해당 지점부터 라이브 결합됩니다.

방문자 A(영구 ID: `246`) 및 방문자 B(영구 ID: `3579`)에 대하여, 시간 경과에 따라 발생하는 다음 두 가지 ID 그래프의 업데이트와 이러한 업데이트가 그래프 기반 결합의 단계에 미치는 영향을 고려합니다.

![ID 그래프 3579](assets/identity-graphs.svg)

[ID 그래프 뷰어](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/identity-graph-viewer)를 사용하여 특정 프로필에 대한 시간 경과 기반 ID 그래프를 볼 수 있습니다. ID를 연결할 때 사용되는 논리를 더 잘 이해하려면 [ID 서비스 연결 논리](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/identity-linking-logic)를 참조하십시오.

### 1단계: 라이브 결합

라이브 결합은 이벤트 수집 시 각 이벤트를 ID 그래프에서 해당 시점의 알려진 정보에 결합하려고 합니다.

+++ 세부 사항

| | 시간 | 영구 ID<br/>`ECID` | 네임스페이스<br/>`Email` ![데이터 매핑](/help/assets/icons/DataMapping.svg) | 결과 ID(라이브 결합 후) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) *정의되지 않음* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![분기1](/help/assets/icons/Branch1.svg) *정의되지 않음* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![분기1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![분기1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

각 이벤트에 대해 결과 ID가 어떻게 확인되는지 확인할 수 있습니다. 시간, 영구 ID 및 지정된 개인 ID 네임스페이스에 대한 ID 그래프 조회를 기반으로 합니다.
조회가 둘 이상의 결과 ID로 확인되는 경우(예: 이벤트 7의 경우) ID 그래프에서 반환되는 사전 편집기 첫 번째 ID가 선택됩니다(이 예제의 경우 `a.b@yahoo.co.uk`).

+++

### 2단계: 재생 결합

재생 결합은 선택한 전환 확인 기간에 따라 정기적인 간격으로 간격 시점의 최신 버전 ID 그래프를 기반으로 하여 내역 데이터를 다시 계산합니다.

+++ 세부 사항

2023-05-13 16:30에 재생 결합이 발생하고 24시간 전환 확인 기간이 구성되면 샘플의 일부 이벤트가 다시 결합됩니다(![재생](/help/assets/icons/Replay.svg)으로 표시됨).

| | 시간 | 영구 ID<br/>`ECID` | 네임스페이스<br/>`Email` ![데이터 매핑](/help/assets/icons/DataMapping.svg) | 결과 ID<br/>(live stitch 후) | 결과 ID<br/>(재생 24시간 후) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![재생](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![링크](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![재생](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![링크](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![재생](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![링크](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![재생](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![분기1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


2023-05-13 16:30에 재생 결합이 발생하고 7일 전환 확인 기간이 구성되면 샘플의 모든 이벤트가 다시 결합됩니다.


| | 시간 | 영구 ID<br/>`ECID` | 네임스페이스<br/>`Email` ![데이터 매핑](/help/assets/icons/DataMapping.svg) | 결과 ID<br/>(live stitch 후) | 결과 ID<br/>(재생 7일 후) |
|---|---|---|---|---|---|
| ![재생](/help/assets/icons/Replay.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) *정의되지 않음* | `246` | `a.b@yahoo.co.uk` |
| ![재생](/help/assets/icons/Replay.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![재생](/help/assets/icons/Replay.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![재생](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![분기1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![재생](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![분기1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![재생](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![재생](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![분기1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### 3단계: 개인정보 보호 요청

개인 정보 보호 요청을 받으면 결과 ID가 개인 정보 보호 요청의 사용자 주제에 대한 모든 레코드에서 삭제됩니다.

+++ 세부 사항

다음 테이블은 위와 동일한 데이터를 나타내나, 개인정보 보호 요청(예: 2023-05-13 18:00)이 샘플 이벤트에 미치는 영향을 보여 줍니다.

| | 시간 | 영구 ID<br/>`ECID` | 네임스페이스<br/>`Email` ![데이터 매핑](/help/assets/icons/DataMapping.svg) | 결과 ID(개인 정보 보호 요청 이후) |
|--:|---|---|---|---|
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 2 | 2023-05-12 14:00 | `246` | `246`![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 3 | 2023-05-12 15:00 | `246` | `246`  ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![분기1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![분기1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![분기1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## 사전 요구 사항

다음 사전 요구 사항은 특히 그래프 기반 결합에 적용됩니다.

- 결합을 적용하려는 Adobe Experience Platform의 이벤트 데이터 세트에는 모든 행에서 프로필을 식별하는 하나의 열인 **영구 ID**&#x200B;가 있어야 합니다. 예를 들면 Adobe Analytics AppMeasurement 라이브러리에서 생성된 방문자 ID 또는 Experience Platform ID 서비스에서 생성된 ECID입니다.
- 그래프 기반 결합을 활성화하기 전에 Experience Platform Identity 서비스의 ID 그래프를 샌드박스 수준에서 설정해야 합니다.
   - ID 그래프에는 결합 중에 개인 ID를 확인하는 데 사용할 네임스페이스(예: `Email` 또는 `Phone`)가 있어야 합니다.
   - ID 그래프는 관련 데이터 세트(*event* 또는 *profile* 유형이고 ID 값이 있는 유용한 네임스페이스가 두 개 이상 포함된)의 ID 정보로 채워야 합니다.
   - 이러한 관련 ID를 포함하는 모든 데이터 세트는 ID 그래프 데이터 수집에 대해 [활성화됨](faq.md#enable-a-dataset-for-the-identity-service)이어야 합니다. 이 기능을 사용하면 시간이 지남에 따라 필요한 모든 소스에서 들어오는 ID를 그래프에 추가할 수 있습니다.
   - 이미 잠시 동안 실시간 고객 데이터 프로필 또는 Adobe Journey Optimizer을 사용하는 경우 그래프가 이미 특정 범위로 설정되어야 합니다.<br/>그래프 기반 결합으로 활성화된 데이터 세트에 내역 결합 채우기도 필요한 경우 원하는 결합 결과를 얻으려면 그래프에 전체 기간에 대한 내역 ID가 이미 포함되어 있어야 합니다.
- 그래프 기반 결합을 사용하고 이벤트 데이터 세트가 ID 그래프에 기여할 것으로 예상되면 [ID 서비스에 대한 데이터 세트를 활성화](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)해야 합니다.
- 영구 ID 및 개인 ID는 [identityMap](#identitymap)과 함께 사용할 수 있습니다. 또는 영구 ID 및 개인 ID는 XDM 스키마의 필드일 수 있습니다. 이 경우 필드는 스키마에서 [ID로 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/ui/fields/identity?lang=en)되어야 합니다.

>[!NOTE]
>
>그래프 기반 결합은 Real-time Customer Data Platform 라이선스가 필요하지 **않습니다**. Customer Journey Analytics의 **Prime** 패키지 이상에 필요한 Experience Platform Identity 서비스 권한이 포함되어 있습니다.


## 제한 사항

다음 제한 사항은 특히 그래프 기반 결합에 적용됩니다.

- 지정된 네임스페이스를 사용하여 개인 ID를 쿼리할 때 타임스탬프는 고려되지 않습니다. 따라서 영구 ID가 타임스탬프가 이전 레코드의 개인 ID와 결합될 수 있습니다.
- 그래프의 네임스페이스에 여러 ID가 포함된 공유 디바이스 시나리오에서는 알파벳순으로 첫 번째 그래픽 ID가 사용됩니다. 네임스페이스 제한 사항 및 우선순위가 그래프 연결 규칙 릴리스의 일부로 구성된 경우, 마지막으로 인증된 사용자의 ID가 사용됩니다. 자세한 내용은 [공유 디바이스](/help/use-cases/stitching/shared-devices.md)를 참조하십시오.
- ID를 ID 그래프에 다시 채우는 데에는 3개월이라는 엄격한 제한 사항이 적용됩니다. ID 그래프 채우기에 Real-time Customer Data Platform 등의 Experience Platform 애플리케이션을 사용하지 않는 경우, ID 다시 채우기를 사용할 수 있습니다.
- [ID 서비스 가드레일](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/guardrails)이 적용됩니다. 이와 관련하여 다음 [정적 제한](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/guardrails#static-limits) 등을 참조하십시오.
   - 그래프의 최대 ID 수: 50
   - 단일 배치 수집을 위해 ID에 연결할 수 있는 최대 링크 수는 50개입니다.
   - 그래프 수집을 위한 XDM 레코드의 최대 ID 수: 20
   - 그래프 수집을 위한 XDM 레코드의 최소 ID 수: 2
