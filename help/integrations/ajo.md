---
title: Customer Journey Analytics와 Adobe Journey Optimizer 통합
description: AJO에서 생성된 데이터를 가져오고 CJA 내에서 Analysis Workspace를 사용하여 가져온 데이터를 분석하십시오.
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 100%

---


# Customer Journey Analytics와 Adobe Journey Optimizer 통합

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html)를 사용하여 연관성 있고 상황에 맞는 개인화된 경험을 제공할 수 있습니다. 이를 사용하여 고객에게 고객 여정의 다음 단계를 안내할 수 있습니다.

다음 단계를 수행하여 Journey Optimizer에서 생성된 데이터를 가져와 Customer Journey Analytics에서 고급 분석을 수행할 수 있습니다.

## Journey Optimizer의 데이터를 Adobe Experience Platform에 전송

Adobe Experience Platform은 Journey Optimizer와 Customer Journey Analytics 사이를 연결하는 중앙 데이터 소스의 역할을 합니다. Journey Optimizer 데이터를 플랫폼에 데이터 세트로 전송하는 방법에 대한 절차는 Journey Optimizer 사용 안내서의 [데이터 세트 시작하기](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html)를 참조하십시오.

## Customer Journey Analytics에 연결 만들기

Journey Optimizer 데이터를 Adobe Experience Platform으로 가져온 다음에는 Journey Optimizer 데이터 세트를 기반으로 [연결을 만들](/help/connections/create-connection.md) 수 있습니다. 플랫폼으로 전송한 데이터 세트를 선택합니다.

## Journey Optimizer 차원 및 지표를 포함하도록 데이터 보기 구성

연결을 만든 다음에는 하나 이상의 [데이터 보기](/help/data-views/create-dataview.md)를 만들어 Customer Journey Analytics에서 사용할 수 있는 차원 및 지표를 구성할 수 있습니다.

데이터 보기에서 다음 지표를 만들어 Journey Optimizer에 있는 유사한 지표와 거의 정확한 동등성을 달성할 수 있습니다. 차원 및 지표 맞춤화 방법에 대한 자세한 내용은 데이터 보기 관리자의 [구성 요소 설정](/help/data-views/component-settings/overview.md)을 참조하십시오.

| 지표 | 설명 | 데이터 보기 설정 |
| --- | --- | --- |
| 반송 | 반송된 메시지 수 | `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 스키마 문자열 요소를 다음 설정과 함께 사용하십시오.<br>구성 요소 유형: 지표<br>포함/제외 값: 모든 기준이 충족되는 경우<br>다음과 같음: `bounce`<br>다음과 같음: `denylist` |
| 오류 | 오류가 발생한 메시지 수 | `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 스키마 문자열 요소를 다음 설정과 함께 사용하십시오.<br>구성 요소 유형: 지표<br>포함/제외 값: `error`와 같음 |
| 제외 | 제외된 메시지 수 | `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 스키마 문자열 요소를 다음 설정과 함께 사용하십시오.<br>구성 요소 유형: 지표<br>포함/제외 값: `exclude`와 같음 |
| 구독 취소 | 구독 취소 수 | `_experience.customerJourneyManagement.messageInteraction.interactionType` 스키마 문자열 요소를 다음 설정과 함께 사용하십시오.<br>구성 요소 유형: 지표<br>포함/제외 값: `unsubscribe`와 같음 |
| 클릭 수 | 메시지 내 클릭 수 | `_experience.customerJourneyManagement.messageInteraction.interactionType` 스키마 문자열 요소를 다음 설정과 함께 사용하십시오.<br>구성 요소 유형: 지표<br>포함/제외 값: `click`와 같음 |
| 열림 | 열린 메시지 수 | `_experience.customerJourneyManagement.messageInteraction.interactionType` 스키마 문자열 요소를 다음 설정과 함께 사용하십시오.<br>구성 요소 유형: 지표<br>포함/제외 값: `open`와 같음 |
| 스팸 불만 사항 | 접수된 스팸 불만 사항 수 | `_experience.customerJourneyManagement.messageInteraction.interactionType` 스키마 문자열 요소를 다음 설정과 함께 사용하십시오.<br>구성 요소 유형: 지표<br>포함/제외 값: `spam_complaint`와 같음 |
| 정상적으로 전송된 메시지 | 정상적으로 전송된 메시지 수 | `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 스키마 문자열 요소를 다음 설정과 함께 사용하십시오.<br>구성 요소 유형: 지표<br>포함/제외 값: `sent`와 같음 |
| 동기화 실패 | 동기화에 실패한 총 메시지 수 | `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` 스키마 문자열 요소를 다음 설정과 함께 사용하십시오.<br>구성 요소 유형: 지표<br>포함/제외 값: `sync`와 같음 |

{style=&quot;table-layout:auto&quot;}

## Journey Optimizer 지표를 사용하여 계산된 지표 구성

Journey Optimizer 데이터 세트에 대해 원하는 차원 및 지표를 구성했으면 해당 데이터에 대한 추가적인 인사이트를 위해 [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md)를 구성할 수도 있습니다. 이러한 계산된 지표는 데이터 보기 관리자에서 생성된 위 지표를 기반으로 합니다.

| 계산된 지표 | 설명 | 공식 |
| --- | --- | --- |
| 전송된 총 메시지 | 전송된 총 메시지 수 (완료 및 실패 모두 포함) | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Journey Optimizer 및 Customer Journey Analytics 간의 보고 차이점

일반적으로 제품 간 데이터 불일치율은 1~2%입니다. 다음과 같은 이유로 인해 제품 간 불일치가 더 커질 수 있습니다.

* 수신 데이터(특히 최근 2시간 이내에 수집된 데이터) 처리 시간은 제품별로 약간 다를 수 있습니다. 오늘을 제외한 날짜 범위를 사용하여 처리 시간을 포함한 불일치를 완화할 수 있습니다.
* “전송된 총 메시지” 계산된 지표에는 “다시 시도” 지표가 포함되지 않습니다. “다시 시도” 지표의 데이터는 데이터 세트에 포함되지 않으며 즉, AJO 보고 대비 CJA 보고의 수치가 더 낮을 수 있습니다. 그러나 다시 시도 데이터는 “정상적으로 전송된 메시지” 또는 “반송” 지표에 포함됩니다. 일주일 이상의 날짜 범위를 사용하여 제품 간 “전송된 총 메시지” 지표의 불일치를 완화할 수 있습니다.
