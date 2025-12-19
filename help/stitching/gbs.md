---
title: 그래프 기반 결합
description: 그래프 기반 결합의 개념 및 작업에 대해 설명합니다.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: 90a285fcd96866974087c53d402e85b4a2d83ccf
workflow-type: tm+mt
source-wordcount: '1512'
ht-degree: 5%

---

# 그래프 기반 결합

그래프 기반 결합에서는 이벤트 데이터 세트와 함께 영구 ID(쿠키) 및 해당 데이터 세트에 대한 개인 ID의 네임스페이스를 지정합니다. 그래프 기반 결합은 결합된 ID의 새 열을 이벤트 데이터 세트에 추가합니다. 그런 다음 영구 ID를 사용하여 지정된 네임스페이스를 사용하여 Experience Platform ID 서비스에서 ID 그래프를 쿼리하고 결합된 ID를 업데이트합니다.

>[!NOTE]
>
>ID 서비스에 대해 데이터 집합이 [활성화되었는지](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)해야 합니다.
>


![그래프 기반 결합](/help/stitching/assets/gbs.png)

## IdentityMap

그래프 기반 결합은 다음 시나리오에서 [`identityMap` 필드 그룹](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/schema/composition#identity)의 사용을 지원합니다.

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

- `identityMap` 네임스페이스를 사용하여 persistentID 정의:
   - `identityMap` 네임스페이스에 persistentID에 대한 여러 값이 있는 경우 사용 가능한 첫 번째 사전 ID가 사용됩니다.

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


## 그래프 기반 결합 작동 방식

결합은 주어진 데이터 세트의 데이터에 대해 최소 2개의 전달을 만듭니다.

- **라이브 결합**: ID 그래프를 쿼리하여 선택한 네임스페이스에 대한 개인 ID를 조회하기 위해 영구 ID를 사용하여 각 히트(이벤트)를 들어오는 대로 결합하려고 합니다. 조회에서 개인 ID를 사용할 수 있는 경우 이 개인 ID가 즉시 결합됩니다.

- **재생 결합**: ID 그래프에서 업데이트된 ID를 기반으로 하는 *재생* 데이터. 이 단계에서 ID 그래프가 네임스페이스에 대한 ID를 해결함으로써 이전에 알 수 없었던 디바이스(영구 ID)의 히트가 결합됩니다. 재생은 **빈도** 및 **전환 확인 기간**&#x200B;의 두 매개 변수로 결정됩니다. Adobe은 다음과 같은 매개 변수의 조합을 제공합니다.
   - **일별 빈도에 대한 일별 전환 확인**: 데이터는 매일 24시간 전환 확인 기간으로 재생됩니다. 이 옵션은 재생이 훨씬 빈번한 이점이 있지만 인증되지 않은 프로필은 사이트를 방문하는 당일 인증해야 합니다.
   - **주별 빈도에 대한 주별 전환**: 매주 전환 확인 기간으로 일주일에 한 번 데이터를 재생합니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 그러나 1주일 미만의 연결되지 않은 데이터는 다음 주간 재생까지 재처리되지 않습니다.
   - **주별 전환 확인**: 데이터는 주별 전환 확인 기간을 사용하여 매주 한 번 재생됩니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 그러나 2주 미만의 연결되지 않은 데이터는 다음 주간 재생까지 재처리되지 않습니다.
   - **주별 빈도에 대한 월별 전환**: 매주 데이터는 월별 전환 확인 기간으로 재생됩니다([옵션](#options) 참조). 이 옵션은 인증되지 않은 세션을 인증하는 데 보다 관대한 시간을 주는 이점이 있습니다. 그러나 1개월 미만의 연결되지 않은 데이터는 다음 주간 재생까지 재처리되지 않습니다.

- **개인 정보**: 개인 정보 관련 요청이 수신되면 소스 데이터 집합에서 요청된 ID를 제거하는 것 외에도 인증되지 않은 이벤트에서 해당 ID의 모든 결합을 실행 취소해야 합니다. 또한 특정 ID에 대한 향후 그래프 기반 결합을 방지하려면 ID 그래프에서 ID를 제거해야 합니다.

  >[!IMPORTANT]
  >
  >개인 정보 보호 요청의 일부로서 결합 해제 프로세스는 2025년 초에 변경됩니다. 현재 결합 해제 프로세스는 알려진 최신 버전의 ID를 사용하여 이벤트를 다시 지정합니다. 이벤트를 다른 정체성으로 재지정하는 것은 바람직하지 않은 법적 결과를 가져올 수 있습니다. 이러한 문제를 해결하기 위해 2025년부터 새로운 결합 해제 프로세스는 영구 ID로 개인 정보 보호 요청의 대상인 이벤트를 업데이트합니다.
  > 

조회 창을 벗어난 데이터는 재생되지 않습니다. 프로필은 인증되지 않은 방문과 인증된 방문을 함께 식별하기 위해 주어진 전환 확인 기간 내에서 인증해야 합니다. 디바이스가 인식되면 해당 시점부터 라이브로 결합됩니다.

방문자 A(영구 ID `246` 사용)와 방문자 B(영구 ID `3579` 사용)에 대한 시간 경과에 따른 다음 두 가지 ID 그래프 업데이트와 이러한 업데이트가 그래프 기반 결합의 단계에 미치는 영향을 고려하십시오.

![ID 그래프 3579](assets/identity-graphs.svg)

[ID 그래프 뷰어](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/identity-graph-viewer)를 사용하여 특정 프로필에 대한 시간에 따른 ID 그래프를 볼 수 있습니다. ID를 연결할 때 사용되는 논리를 더 잘 이해하려면 [ID 서비스 연결 논리](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/identity-linking-logic)도 참조하세요.

### 1단계: 라이브 결합

라이브 결합은 수집 시 각 이벤트를 ID 그래프에서 해당 시점의 알려진 정보에 결합하려고 합니다.

+++ 세부 사항

| | 시간 | 영구 ID<br/>`ECID` | 네임스페이스<br/>`Email` ![데이터 매핑](/help/assets/icons/DataMapping.svg) | 결합된 ID(라이브 결합 후) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) *정의되지 않음* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![분기1](/help/assets/icons/Branch1.svg) *정의되지 않음* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![분기1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![분기1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

각 이벤트에 대해 결합된 ID가 어떻게 해결되는지 볼 수 있습니다. 시간, 영구 ID 및 지정된 네임스페이스에 대한 ID 그래프의 조회를 기반으로 합니다(동시에).
조회가 둘 이상의 결합된 ID로 확인되는 경우(예: 이벤트 7의 경우) ID 그래프에서 반환되는 사전 편집기 첫 번째 ID가 선택됩니다(이 예제의 경우 `a.b@yahoo.co.uk`).

+++

### 2단계: 재생 결합

정기적으로(선택한 전환 확인 기간에 따라) 재생 결합은 간격 시 ID 그래프의 최신 버전을 기반으로 내역 데이터를 다시 계산합니다.

+++ 세부 사항

2023-05-13 16:30에 재생 결합이 발생하고 24시간 전환 확인 기간이 구성되면 샘플의 일부 이벤트가 다시 결합됩니다(![재생](/help/assets/icons/Replay.svg)(으)로 표시됨).

| | 시간 | 영구 ID<br/>`ECID` | 네임스페이스<br/>`Email` ![데이터 매핑](/help/assets/icons/DataMapping.svg) | 결합된 ID<br/>(live stitch 후) | 결합된 ID<br/>(재생 24시간 후) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![재생](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![링크](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![재생](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![링크](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![재생](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![링크](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![재생](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![분기1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


2023-05-13 16:30에 재생 결합이 발생하고 7일 전환 확인 기간이 구성되면 샘플의 모든 이벤트가 다시 결합됩니다.


| | 시간 | 영구 ID<br/>`ECID` | 네임스페이스<br/>`Email` ![데이터 매핑](/help/assets/icons/DataMapping.svg) | 결합된 ID<br/>(live stitch 후) | 결합된 ID<br/>(재생 7일 후) |
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

### 3단계: 개인 정보 보호 요청

개인 정보 보호 요청을 받으면 결합된 ID가 개인 정보 보호 요청의 사용자 주제에 대한 모든 레코드에서 삭제됩니다.

+++ 세부 사항

다음 테이블은 위와 동일한 데이터를 나타내지만 개인 정보 보호 요청(예: 2023-05-13 18:00)이 샘플 이벤트에 미치는 영향을 보여 줍니다.

| | 시간 | 영구 ID<br/>`ECID` | 네임스페이스<br/>`Email` ![데이터 매핑](/help/assets/icons/DataMapping.svg) | 결합된 ID(개인 정보 보호 요청 후) |
|--:|---|---|---|---|
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 2 | 2023-05-12 14:00 | `246` | `246`![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![분기1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![분기1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![분기1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![분기1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## 사전 요구 사항

다음 사전 요구 사항은 그래프 기반 결합에 특히 적용됩니다.

- 결합을 적용하려는 Adobe Experience Platform의 이벤트 데이터 세트에는 모든 행에서 프로필을 식별하는 하나의 열(**영구 ID**)이 있어야 합니다. 예를 들어 Adobe Analytics AppMeasurement 라이브러리에서 생성된 방문자 ID 또는 Experience Platform ID 서비스에서 생성된 ECID입니다.
- 영구 ID는 스키마에서 [ID로 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/ui/fields/identity)되어야 합니다.
- Experience Platform Identity Service의 ID 그래프에는 `Email`개인 ID`Phone`을(를) 확인하기 위해 결합하는 동안 사용할 네임스페이스(예: **또는**)가 있어야 합니다. 자세한 내용은 [Experience Platform ID 서비스](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/home)를 참조하십시오.

>[!NOTE]
>
>그래프 기반 결합을 위해 Real-time Customer Data Platform 라이선스가 필요 **없습니다**. Customer Journey Analytics의 **Prime** 패키지 이상에 필요한 Experience Platform Identity 서비스 권한이 포함되어 있습니다.


## 제한 사항

다음 제한 사항은 특히 그래프 기반 결합에 적용됩니다.

- 지정된 네임스페이스를 사용하여 개인 ID를 쿼리할 때 타임스탬프는 고려되지 않습니다. 따라서 영구 ID가 타임스탬프가 더 이른 레코드의 개인 ID와 결합될 수 있습니다.
- 그래프의 네임스페이스에 여러 ID가 포함된 공유 장치 시나리오에서는 첫 번째 사전 그래픽 ID가 사용됩니다. 네임스페이스 제한 및 우선순위가 그래프 연결 규칙 릴리스의 일부로 구성된 경우 마지막으로 인증된 사용자의 ID가 사용됩니다. 자세한 내용은 [공유 장치](/help/use-cases/stitching/shared-devices.md)를 참조하십시오.
- ID를 ID 그래프에 다시 채우는 데에는 3개월이라는 엄격한 제한이 있습니다. Real-time Customer Data Platform과 같은 Experience Platform 애플리케이션을 사용하여 ID 그래프를 채우지 않는 경우 ID 채우기 기능을 사용합니다.
- [ID 서비스 보호](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/guardrails)가 적용됩니다. 예를 들어, 다음 [정적 제한](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/guardrails#static-limits)을(를) 참조하십시오.
   - 그래프의 최대 ID 수: 50.
   - 단일 배치 수집을 위한 ID에 대한 최대 링크 수는 50개입니다.
   - 그래프 수집을 위한 XDM 레코드의 최대 ID 수: 20.
   - 그래프 수집을 위한 XDM 레코드의 최소 ID 수: 2개.
