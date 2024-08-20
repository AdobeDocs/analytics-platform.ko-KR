---
title: 공유 장치
description: 결합 및 기타 기술을 사용하여 공유 장치를 처리하는 방법에 대한 설명입니다.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hide-from-toc: true
role: Admin
source-git-commit: f17d2ebdf9a45ebb3a4e923a34c4b9b3d629f038
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 6%

---

# 공유 장치

이 문서에서는 공유 장치에 대한 컨텍스트, 결합을 사용하여 공유 장치의 데이터를 처리하고 완화하는 방법, 쿼리 서비스를 사용하여 데이터의 공유 장치 노출을 이해하는 방법에 대해 설명합니다.

## 공유 디바이스란?

공유 디바이스는 두 명 이상의 사용자가 사용하는 디바이스입니다. 일반적인 시나리오는 태블릿과 같은 장치, 키오스크에서 사용되는 장치 또는 콜 센터의 에이전트가 공유하는 컴퓨터 장비입니다.

두 사람이 동일한 장치를 사용하고 둘 다 구매하는 경우 샘플 이벤트 데이터는 다음과 같을 수 있습니다.

| 타임스탬프 | 페이지 이름 | 장치 ID | 이메일 |
|---|---|---|---|
| 2023-05-12 12:01 | 홈 페이지 | 1234 | |
| 2023-05-12 12:02 | 제품 페이지 | 1234 | |
| 2023-05-12 12:03 | 주문 성공 | 1234 | <ryan@a.com> |
| 2023-05-12 12:07 | 제품 페이지 | 1234 | |
| 2023-05-12 12:08 | 주문 성공 | 1234 | <cassidy@a.com> |

주문 성공(구매) 이벤트는 올바른 이메일에 데이터를 정확하게 할당합니다. 이 할당이 분석에 미치는 영향은 분석을 수행하는 방법에 따라 달라집니다.

- 장치 중심 접근 방식: 장치 ID를 사용하여 수행된 분석입니다. 이 접근 방식에서는 인증된 데이터와 인증되지 않은 데이터가 모두 분석에 포함됩니다. 그러나 이 접근 방식에서는 더 많은 사용자를 기반으로 한 분석을 허용하지 않습니다.
- 사용자 중심 접근 방식: 이메일 주소 또는 다른 사용자 식별자를 사용하여 수행되는 분석입니다. 이 접근 방식에서는 인증된 이벤트만 분석에 포함됩니다. 이 방법에서는 고객 확보를 포함한 고객 여정에 대한 전체 그림을 제공하지는 않습니다

## 사용자 중심 분석 개선

공유 장치의 개인 중심 분석을 개선하기 위해 두 가지 옵션이 있습니다. 스티칭을 사용하거나 ECID 재설정 기능을 구현할 수 있습니다. 두 접근 방식 모두 아래 섹션에서 보다 자세히 설명합니다.

### 결합

결합 프로세스는 사람 중심 접근법의 단점을 해결합니다. 결합은 선택한 개인 식별자(예제 데이터의 이메일)를 해당 식별자가 없는 이벤트에 추가합니다. 결합은 장치 ID와 개인 ID 간의 매핑을 활용하여 인증된 트래픽과 인증되지 않은 트래픽을 모두 분석에 사용하여 개인 중심의 상태를 유지합니다. 자세한 내용은 [결합](/help/stitching/overview.md)을 참조하십시오.

결합은 마지막 인증 속성 또는 디바이스 분할 속성을 사용하여 공유 디바이스 데이터를 속성 지정할 수 있습니다. 그러나 ECID 재설정을 통한 구현 변경은 공유 디바이스를 해결할 수도 있습니다.


#### 마지막 인증 속성

Last-auth는 공유 장치에서 마지막으로 인증된 사용자에게 알 수 없는 모든 활동을 연결합니다. Last-auth는 Audience Manager에서 사용되며 실시간 고객 데이터 프로필 사용 사례에 선호되는 방법입니다. Experience Platform ID 서비스는 마지막 인증 속성을 기반으로 그래프를 작성하며, 따라서 그래프 기반 결합에 사용됩니다. 자세한 내용은 [ID 그래프 연결 규칙 개요](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview)를 참조하십시오.

결합에 마지막 인증 속성을 사용할 때 결합된 ID는 아래 표와 같이 해결됩니다.

| 타임스탬프 | 페이지 이름 | 장치 ID | 이메일 | 결합된 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 홈 페이지 | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:02 | 제품 페이지 | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:03 | 주문 성공 | 1234 | <ryan@a.com> | <cassidy@a.com> |
| 2023-05-12 12:07 | 제품 페이지 | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:08 | 주문 성공 | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | 홈 페이지 | 1234 | | <cassidy@a.com> |


#### Device-split

장치 분할은 익명 활동과 가장 가까운 거리에 있는 사용자에게 공유 장치의 익명 활동을 특성화합니다. 장치 분할은 현재 필드 기반 결합에 사용됩니다. Device-split은 가장 가까운 사람에게 인증되지 않은 활동과 인증된 활동 모두에 대한 크레딧을 제공하기 때문에 Device-split은 분석 사용 사례에 선호되는 접근법입니다. 장치 분할은 현재 필드 기반 결합에 사용됩니다.

결합에 디바이스 분할 속성을 사용할 때 결합된 ID는 아래 표와 같이 확인됩니다.

| 타임스탬프 | 페이지 이름 | 장치 ID | 이메일 | 결합된 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 홈 페이지 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | 제품 페이지 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | 주문 성공 | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | 제품 페이지 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:08 | 주문 성공 | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | 홈 페이지 | 1234 | | <cassidy@a.com> |


### ECID 재설정

이름에서 알 수 있듯이 ECID 재설정은 미리 결정된 트리거(대부분의 경우 로그인 또는 로그아웃 이벤트)에서 ECID를 재설정하는 기능을 구현합니다. 이 구현에서는 사전 결정된 트리거가 실행될 때마다 단일 장치가 새 ECID를 받습니다. 기본적으로 이 재설정으로 인해 데이터 관점에서 계속해서 장치가 *새 장치*&#x200B;가 됩니다. ECID 재설정을 사용하면 공유 장치가 데이터에 표시되지 않을 수도 있습니다. 추가 알고리즘은 필요하지 않지만 Adobe 데이터 수집 구현의 일부로서 ECID 재설정 신호를 구현할 책임이 있습니다.


ECID 재설정을 사용할 때 결합된 ID는 아래 표에 표시된 대로 해결됩니다.

| 타임스탬프 | 페이지 이름 | 장치 ID | 이메일 | 결합된 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 홈 페이지 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | 제품 페이지 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | 주문 성공 | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | 제품 페이지 | 5678 | | <cassidy@a.com> |
| 2023-05-12 12:08 | 주문 성공 | 5678 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | 홈 페이지 | 5678 | | <cassidy@a.com> |

## 공유된 디바이스 노출

조직에 광범위한 공유 장치가 있는 방식을 올바로 이해하려면 몇 가지 요소를 고려하십시오. 또한 공유 장치에서 발생하는 이벤트의 전체 기여도를 이해하면 분석에 사용되는 전체 이벤트 데이터에 미치는 영향을 이해하는 데 도움이 될 수 있습니다.

공유된 디바이스 노출을 이해하기 위해 다음 쿼리를 수행하는 것에 대해 생각해 볼 수 있습니다.

1. 공유된 디바이스의 수를 파악합니다. 장치 ID와 연결된 개인 ID가 두 개 이상 있는 장치 ID를 계산하는 쿼리를 사용할 수 있습니다. 샘플 쿼리는 다음과 같이 표시될 수 있습니다.

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


2. 공유 장치의 경우, 첫 번째 쿼리에서 비롯되므로 이러한 공유 장치에 귀속될 수 있는 총 이벤트 수를 이해해야 합니다. 이 속성을 사용하면 공유 장치가 데이터에 미치는 영향과 분석을 수행할 때의 영향을 더 잘 파악할 수 있습니다. 샘플 쿼리는 다음과 같이 표시될 수 있습니다.

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

3. 공유 장치로 인한 이벤트(두 번째 쿼리 결과)의 경우, 개인 ID가 없는 이러한 이벤트의 수를 이해해야 합니다. 달리 말하면, 공유된 디바이스 이벤트 중 몇 개가 익명 이벤트입니까? 궁극적으로 데이터 품질을 개선하기 위해 선택하는 알고리즘(last-auth, device-split, ECID-reset)은 이러한 익명 공유 장치 이벤트에 영향을 줍니다. 샘플 쿼리는 다음과 같이 표시될 수 있습니다.

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

4. 마지막으로, 이벤트 분류가 잘못되어 각 고객이 겪게 되는 노출을 이해하려고 합니다. 이 노출을 가져오려면 각 공유 장치에 대해 총 이벤트 수와 관련된 익명 이벤트의 비율을 계산해야 합니다. 샘플 쿼리는 다음과 같이 표시될 수 있습니다.

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


