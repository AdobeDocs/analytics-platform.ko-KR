---
title: 공유 디바이스
description: 결합 및 기타 기술을 사용하여 공유 장치를 처리하는 방법에 대한 설명입니다.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: f45a457d251767634e28984d7c75158dac6e51e8
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 6%

---

# 공유 디바이스

이 문서에서는 공유 장치에 대한 컨텍스트, [결합](/help/stitching/overview.md)을 사용하여 공유 장치의 데이터를 처리하고 완화하는 방법, 쿼리 서비스를 사용하여 데이터의 공유 장치 노출을 이해하는 방법에 대해 설명합니다.

## 공유 디바이스란?

공유 디바이스는 두 명 이상의 사용자가 사용하는 디바이스입니다. 일반적인 시나리오는 태블릿과 같은 장치, 키오스크에서 사용되는 장치 또는 콜 센터의 에이전트가 공유하는 컴퓨터 장비입니다.

두 사람이 동일한 장치를 사용하고 둘 다 인증된 구매를 수행하면 샘플 이벤트 데이터가 다음과 같을 수 있습니다.

| 이벤트 | 타임스탬프 | 페이지 이름 | 장치 ID | 이메일 |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | 홈 페이지 | `1234` | |
| 2 | 2023-05-12 12:02 | 제품 페이지 | `1234` | |
| 3 | 2023-05-12 12:03 | 주문 성공 | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | 제품 페이지 | `1234` | |
| 5 | 2023-05-12 12:08 | 주문 성공 | `1234` | `cassidy@a.com` |

이 표에서 알 수 있듯이 이벤트 3과 5에서 인증이 발생하면 장치 ID와 개인 ID 간에 링크가 형성되기 시작합니다. 개인 수준에 대한 마케팅 노력의 영향을 이해하려면 이러한 인증되지 않은 이벤트가 적합한 사람에게 귀속되어야 합니다.

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## 사용자 중심 분석 개선

결합 프로세스를 통해 선택한 개인 식별자(예: 데이터, 이메일)를 해당 식별자가 없는 이벤트에 추가하여 이 속성 문제를 해결할 수 있습니다. 결합은 장치 ID와 개인 ID 간의 매핑을 활용하여 인증된 트래픽과 인증되지 않은 트래픽을 모두 분석에 사용하여 개인 중심의 상태를 유지합니다. 자세한 내용은 [결합](/help/stitching/overview.md)을 참조하십시오.

결합은 마지막 인증 속성 또는 디바이스 분할 속성을 사용하여 공유 디바이스 데이터를 속성 지정할 수 있습니다. 인증되지 않은 이벤트를 알려진 사용자에게 연결하려는 모든 시도는 비결정적입니다.


### 마지막 인증 속성

Last-auth는 공유 장치에서 마지막으로 인증된 사용자에게 알 수 없는 모든 활동을 연결합니다. Experience Platform ID 서비스는 마지막 인증 속성을 기반으로 그래프를 작성하며, 따라서 그래프 기반 결합에 사용됩니다. 자세한 내용은 [ID 그래프 연결 규칙](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/identity-graph-linking-rules/identity-optimization-algorithm#identity-optimization-algorithm-details)을 참조하십시오.

결합에 마지막 인증 속성이 사용되면 아래 표에 표시된 대로 결합된 ID가 확인됩니다.

| 타임스탬프 | 페이지 이름 | 장치 ID | 이메일 | 결합된 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 홈 페이지 | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | 제품 페이지 | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | 주문 성공 | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | 제품 페이지 | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | 주문 성공 | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | 홈 페이지 | `1234` | | `cassidy@a.com` |


### Device-split

장치 분할 속성은 과거를 기준으로 공유 장치에서 가장 최근에 알려진 사용자로의 익명 활동을 지정합니다. 장치 분할은 현재 필드 기반 결합에 사용됩니다.

결합에 디바이스 분할 속성이 사용되는 경우 결합된 ID는 아래 표와 같이 확인됩니다.

| 타임스탬프 | 페이지 이름 | 장치 ID | 이메일 | 결합된 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 홈 페이지 | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | 제품 페이지 | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | 주문 성공 | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | 제품 페이지 | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | 주문 성공 | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | 홈 페이지 | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`| 
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` | 
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` | 
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## 공유된 디바이스 노출

조직에 광범위한 공유 장치가 있는 방식을 올바로 이해하려면 몇 가지 요소를 고려하십시오. 또한 공유 장치에서 발생하는 이벤트의 전체 기여도를 이해하면 분석에 사용되는 전체 이벤트 데이터에 미치는 영향을 이해하는 데 도움이 될 수 있습니다.

공유된 디바이스 노출을 이해하기 위해 다음 쿼리를 수행하는 것에 대해 생각해 볼 수 있습니다.

1. **공유 장치 식별**

   공유된 디바이스의 수를 이해하려면, 연결된 개인 ID가 2개 이상인 디바이스 ID를 계산하는 쿼리를 수행하십시오. 이는 여러 개인이 사용하는 디바이스를 식별하는 데 도움이 됩니다.

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. **공유 장치에 대한 이벤트 속성**

   식별된 공유 장치의 경우, 총 이벤트 수 중 해당 장치가 원인이 될 수 있는 이벤트를 결정합니다. 이 속성은 insight을 통해 공유 디바이스가 데이터에 미치는 영향 및 분석에 대한 영향을 제공합니다.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. **공유 장치에서 익명 이벤트 식별**

   공유 디바이스로 인한 이벤트 중에서 익명 이벤트를 나타내는 개인 ID가 없는 이벤트 수를 식별합니다. 데이터 품질을 개선하기 위해 선택한 알고리즘(예: last-auth, device-split 또는 ECID-reset)은 이러한 익명 이벤트에 영향을 줍니다.

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. **잘못된 이벤트로 노출 계산**

   마지막으로, 이벤트 분류 오류로 인해 각 고객이 직면할 수 있는 노출을 평가합니다. 각 공유 장치에 대한 총 이벤트에 대한 익명 이벤트의 비율을 계산합니다. 이를 통해 고객 데이터 정확도에 미칠 수 있는 영향을 이해할 수 있습니다.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```
