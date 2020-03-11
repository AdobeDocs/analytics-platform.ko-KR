---
title: 고객 여정 분석 시작하기
description: 고객 여정 분석 시작
translation-type: tm+mt
source-git-commit: 12ab54b09caea3b7bb5fbc345ba5e396c198a36c

---


# 고객 여정 분석 시작하기

고객 여정 분석을 구현하려면 이 워크플로우를 따라야 합니다. 일부 초기 작업은 Adobe Experience Platform에서, 일부는 고객 여정 분석에서 수행됩니다.

| 작업 | 장소 performed | 세부 사항 |
|---|---|---|
| **1단계:Adobe Experience Platform에 데이터 통합** | Adobe Experience Platform |  |
| **2단계:데이터 스키마 준비** | Adobe Experience Platform | XDM( [Adobe Experience Data Model)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) 을 사용하여 고객 경험 데이터를 표준화하고 고객 경험 관리를 위한 스키마를 정의할 수 있습니다. |
| **3단계:스키마를 기반으로 데이터 집합 만들기** | Adobe Experience Platform | 플랫폼의 데이터는 이메일 데이터 세트, CRM 데이터 세트, POS 데이터 세트, Adobe Analytics 데이터 세트 등과 같은 데이터 세트로 구성됩니다. 각 데이터 세트는 스키마와 일련의 데이터로 구성됩니다. Experience Platform [에서 데이터 세트를 만들 수 있습니다](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>Customer Journey Analytics로 가져올 수 있는 데이터 세트에 대한 스키마는 유연하지만 일부 기본 규칙을 준수해야 합니다. 데이터를 플랫폼에 업로드하기 전에 이러한 요구 사항을 충족하는지 확인하는 것이 가장 좋습니다. 스키마에는 지표와 차원이 모두 포함됩니다.<br>고객 여정 분석과 호환되는 세 가지 유형의 데이터가 있습니다.<ul><li>**이벤트 데이터**:시간(예: 웹 방문, 상호 작용, 거래, POS 데이터, 설문 조사 데이터, 광고 노출 데이터 등)으로 이벤트를 나타내는 데이터 고객 ID 또는 쿠키 ID와 타임스탬프가 있는 일반적인 클릭스트림 데이터입니다. 이벤트 데이터를 사용하면 원하는 ID를 사용할 수 있습니다.</li><li>**조회 데이터**:이 데이터는 이벤트 또는 프로필 데이터에 있는 값이나 키를 조회하는 데 사용됩니다. 예를 들어 이벤트 데이터의 숫자 ID를 제품 이름으로 매핑하는 조회 데이터를 업로드할 수 있습니다.</li><li>**프로필 데이터**:이벤트 데이터의 방문자, 사용자 또는 고객에게 적용되는 데이터입니다. 예를 들어 고객에 대한 CRM 데이터를 업로드할 수 있습니다.</li></ul> |
| **3단계: 플랫폼 데이터 세트와 고객 경로 분석 간의 연결 만들기** | 고객 여정 분석 | 연결 [만들기를](/help/connections/create-connection.md)참조하십시오. |
| **4단계:데이터 뷰 만들기** | 고객 여정 분석 | See [Create a data view](/help/data-views/create-dataview.md). |
| **5단계:작업 공간에서 크로스채널 데이터 보고** | 고객 여정 분석 | 기본 [분석](/help/projects/perform-basic-analysis.md) 수행 및 [고급 분석](/help/projects/perform-adv-analysis.md)수행을 참조하십시오. |

## 전제 조건

고객 여정 분석은

* Adobe Analytics [Select, Prime 또는 Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) 고객입니까,
* Adobe Experience [Platform에](https://www.adobe.com/experience-platform.html)대한
* 고객 경로 분석 SKU를 구입했습니다.

## 데이터 스키마 준비

[스키마 편집기를 사용하여 스키마 만들기](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## 1단계:Adobe Experience Platform에 데이터 통합

CJA에서 경험 플랫폼 데이터를 활용하려면 먼저 해당 데이터를 플랫폼에 인제스트해야 합니다. 다음과 같은 여러 가지 방법이 있습니다.

* 기존 Adobe Analytics 데이터를 가져오려면 Adobe Analytics Platform 커넥터를 사용하십시오.
* 다른 데이터를 가져오려면 .csv 또는 Components 형식으로 파일을 사용하여


## 1a 단계:기존 Analytics 데이터를 Adobe Experience Platform으로 가져오기

Adobe Analytics Platform Connector를 사용하여 기존 Analytics 데이터를 플랫폼으로 가져올 수 있습니다. 보고서 세트당 하나의 소스 연결을 만들 수 있습니다. Adobe [Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) 설명서에서 Adobe Analytics로 소스 연결 만들기를 참조하십시오.

연결이 만들어지면 들어오는 데이터를 포함하도록 대상 스키마와 데이터 세트가 자동으로 생성됩니다. 또한 데이터 다시 채우기가 발생하고 최대 13개월 동안의 내역 데이터를 인제스트합니다. 초기 인제스트가 완료되면 x단계로 진행하여 이 Analytics 데이터 세트와 고객 경로 분석 간의 연결을 만들 수 있습니다.

## 1단계 b:스키마 만들기




