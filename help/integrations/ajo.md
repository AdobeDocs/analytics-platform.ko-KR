---
title: Adobe Journey Optimizer과 Customer Journey Analytics 통합
description: AJO에서 생성한 데이터를 가져와 CJA 내에서 Analysis Workspace을 사용하여 분석합니다.
source-git-commit: 28bc99a7f5ec7b280fd26a7a45dc076e67f652dc
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 2%

---


# Adobe Journey Optimizer과 Customer Journey Analytics 통합

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=ko) 은 연관성이 있고 상황에 맞는 개인화된 경험을 제공합니다. 고객 여정의 다음 단계로 고객을 노출하는 데 도움이 됩니다.

다음 단계를 수행하여 Journey Optimizer에서 생성한 데이터를 가져와서 Customer Journey Analytics에서 고급 분석을 수행할 수 있습니다.

## Journey Optimizer에서 Adobe Experience Platform으로 데이터 보내기

Adobe Experience Platform은 Journey Optimizer과 Customer Journey Analytics 간의 중앙 데이터 소스 및 링크 역할을 합니다. 자세한 내용은 [데이터 세트 시작](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) Journey Optimizer 사용 안내서에서 Journey Optimizer 데이터를 데이터 집합으로 Platform에 전송하는 방법에 대한 단계를 설명합니다.

## Customer Journey Analytics에서 연결 만들기

Journey Optimizer 데이터가 Adobe Experience Platform에 있으면 다음을 수행할 수 있습니다 [연결 만들기](/help/connections/create-connection.md) Journey Optimizer 데이터 세트 기반. Platform으로 보낸 데이터 세트를 선택합니다.

## Journey Optimizer 차원 및 지표를 수용하도록 데이터 보기 구성

연결이 만들어지면 하나 이상의 연결을 만들 수 있습니다 [데이터 보기](/help/data-views/create-dataview.md) Customer Journey Analytics에서 사용할 수 있는 원하는 차원 및 지표를 구성하려면 다음을 수행하십시오.

데이터 보기에서 다음 지표를 만들어 Journey Optimizer의 유사한 지표와 대략적인 패리티를 달성할 수 있습니다. 자세한 내용은 [구성 요소 설정](/help/data-views/component-settings/overview.md) 를 참조하십시오.

| 지표 | 설명 | 데이터 보기 설정 |
| --- | --- | --- |
| 바운스 수 | 바운스된 메시지 수 | 스키마 문자열 요소 사용 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 다음 설정으로 변경합니다.<br>구성 요소 유형: 지표<br>제외 값 포함: 기준이 충족되는 경우<br>다음과 같음: `bounce`<br>다음과 같음: `denylist` |
| 오류 | 오류가 발생한 메시지 수 | 스키마 문자열 요소 사용 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 다음 설정으로 변경합니다.<br>구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `error` |
| Excludes | 제외된 메시지 수 | 스키마 문자열 요소 사용 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 다음 설정으로 변경합니다.<br>구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `exclude` |
| 가입 해지됨 | 구독 취소 수 | 스키마 문자열 요소 사용 `_experience.customerJourneyManagement.messageInteraction.interactionType` 다음 설정으로 변경합니다.<br>구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `unsubscribe` |
| 클릭 수 | 메시지 내 클릭 수 | 스키마 문자열 요소 사용 `_experience.customerJourneyManagement.messageInteraction.interactionType` 다음 설정으로 변경합니다.<br>구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `click` |
| 열림 | 열린 메시지 수 | 스키마 문자열 요소 사용 `_experience.customerJourneyManagement.messageInteraction.interactionType` 다음 설정으로 변경합니다.<br>구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `open` |
| 스팸 불만 | 스팸 불만 수 | 스키마 문자열 요소 사용 `_experience.customerJourneyManagement.messageInteraction.interactionType` 다음 설정으로 변경합니다.<br>구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `spam_complaint` |
| 메시지를 보냈습니다. | 성공적으로 보낸 메시지 수 | 스키마 문자열 요소 사용 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 다음 설정으로 변경합니다.<br>구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `sent` |
| 동기화 실패 | 동기화하지 못한 총 메시지 수 | 스키마 문자열 요소 사용 `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` 다음 설정으로 변경합니다.<br>구성 요소 유형: 지표<br>제외 값 포함: 다음과 같음 `sync` |

## Journey Optimizer 지표를 사용하여 계산된 지표 구성

Journey Optimizer 데이터 세트에 대해 원하는 차원 및 지표를 구성했으면 다음을 구성할 수도 있습니다 [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md) 를 참조하십시오. 이러한 계산된 지표는 데이터 보기 관리자에서 만든 위의 지표를 기반으로 합니다.

| 계산된 지표 | 설명 | 공식 |
| --- | --- | --- |
| 보낸 총 메시지 수 | 전송, 성공 또는 실패한 총 메시지 수 | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

## Journey Optimizer과 Customer Journey Analytics 간의 보고 차이점

제품 간의 데이터 불일치는 일반적으로 1~2% 사이에서 발생합니다. 제품 간의 불일치가 크면 다음과 같은 결과가 발생할 수 있습니다.

* 들어오는 데이터의 처리 시간은 제품 간에, 특히 지난 2시간 내에 수집된 데이터의 경우 약간 다를 수 있습니다. 오늘 제외 날짜 범위를 사용하여 처리 시간과 관련된 불일치를 줄이십시오.
* 계산된 지표 &#39;보낸 총 메시지 수&#39;에는 &#39;다시 시도&#39; 지표가 포함되지 않습니다. &#39;다시 시도&#39; 지표에 대한 데이터는 데이터 집합에 포함되지 않으므로 CJA 보고와 AJO 보고에서는 잠재적으로 낮은 숫자가 표시됩니다. 하지만 다시 시도 데이터는 &#39;메시지를 성공적으로 보냈음&#39; 또는 &#39;바운스 수&#39; 지표에 수렴됩니다. 제품 간 &#39;보낸 총 메시지&#39; 지표와의 불일치를 줄이려면 1주일 이상의 날짜 범위를 사용하십시오.
