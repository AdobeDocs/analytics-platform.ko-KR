---
title: Customer Journey Analytics B2B edition 개념 및 기능
description: Customer Journey Analytics B2B edition에 대한 개념 및 기능입니다.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B 에디션"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: 68f2fe684f6eb9590ab047e893fb04b1cbe1a8cd
workflow-type: tm+mt
source-wordcount: '1469'
ht-degree: 2%

---


# B2B edition 개념 및 기능

이 문서에서는 Customer Journey Analytics에서 일반적으로 사용되는 연결, 식별자, 컨테이너 및 데이터 세트와 같은 개념에 대해 설명합니다. 그리고 Customer Journey Analytics B2B edition이 이러한 개념에 추가 기능을 추가하는 방법입니다.


## 연결 및 식별자

Customer Journey Analytics에서 개인 ID라고 하는 공통 식별자를 선택하여 이벤트 데이터를 프로필 데이터 세트 및 조회 데이터 세트와 같은 다른 데이터 세트와 연결합니다. 이러한 유형의 연결은 사람 기반 보고 및 분석을 용이하게 하는 사람 기반 연결로 알려져 있습니다.

Customer Journey Analytics B2B edition에서 사용자 기반 연결 또는 계정 기반 연결 중에서 선택할 수 있습니다. 계정 기반 연결을 통해 계정 기반 보고 및 분석을 용이하게 할 수 있습니다.

* 사용자 기반 연결의 경우 기본 식별자로 개인을 선택합니다. 그런 다음 사용자 기반 보고를 위해 연결, 데이터 보기 및 작업 공간 프로젝트를 구성하고 설정할 수 있습니다.
* 계정 기반 연결의 경우 계정 을 기본 식별자로 선택합니다. 그런 다음 선택적으로 글로벌 계정, 구매 그룹 및 기회에 대한 컨테이너를 추가할 수 있습니다. 글로벌 계정 추가 여부에 따라 기본 식별자는 계정 식별자 또는 글로벌 계정 식별자입니다.


## 컨테이너

Customer Journey Analytics에서 컨테이너는 연결 및 데이터 보기 구성의 일부로 생성되며 데이터 구조 및 범위를 제공합니다. 컨테이너는 식별자 그룹을 저장하여 고유 식별자별로 모든 이벤트 타임스탬프의 순서를 지정합니다. 이 스토리지를 사용하면 세분화, 속성 및 시각화와 같은 기능을 빠르고 원활하게 실행할 수 있습니다.

### 표준 컨테이너

Customer Journey Analytics은 개인, 세션 및 이벤트의 세 가지 컨테이너 개념을 기반으로 구축됩니다. 구성하는 동안 이러한 컨테이너는 암시적으로 생성됩니다.

데이터 보기를 구성할 때 이러한 컨테이너의 이름을 재정의할 수 있지만 컨테이너 간의 계층 구조 및 관계는 미리 정해져 있습니다. 세션 컨테이너는 데이터 보기의 [세션 설정](/help/data-views/session-settings.md)에서 세션을 정의하는 방법을 기반으로 생성됩니다.

![B2C](assets/b2c-containers.svg){zoomable="yes"}


### B2B 컨테이너

Customer Journey Analytics B2B edition에서 계정 컨테이너가 생성된 컨테이너 목록에 추가됩니다. 또한 Global Account, Purchasing Group 및 Opportunity 와 같은 추가 컨테이너 생성을 구성할 수 있습니다.

컨테이너 간의 계층 구조 및 관계는 미리 결정되어 있습니다. 영업 기회, 구매 그룹 및 개인은 모두 계정 컨테이너의 형제 컨테이너입니다. 해당 계층에서 개인 컨테이너와 이벤트 컨테이너 사이의 세션 컨테이너는 데이터 보기의 [세션 설정](/help/data-views/session-settings.md)에서 세션을 정의하는 방법을 기반으로 생성됩니다. 추가 세션 컨테이너(예: 계정 컨테이너와 이벤트 컨테이너 사이)는 현재 생성되지 않으며 지원되지 않습니다. B2B 컨테이너에 대한 설명 및 기본 용도는 아래 표를 참조하십시오.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

| B2B 컨테이너 | 설명<br/>기본 사용 사례 |
|---|---|
| 계정 | 귀사의 고객 또는 잠재 고객인 회사. 그 회사는 더 큰 조직의 자회사 또는 사업부일 수 있다. 계정은 판매 중이며 해당 조직 수준에서 추적하려는 조직을 나타냅니다. |
| 글로벌 계정(선택 사항) | 관련 회사 그룹의 최상위 상위 회사입니다. 글로벌 계정에는 모회사가 없지만, 글로벌 계정에 속하는 자회사 또는 사업부가 있을 수 있습니다. 연결에 글로벌 계정 컨테이너를 구성하면 상위 또는 자회사가 없는 계정이 계정 필드와 글로벌 계정 필드 모두에 나열되어야 합니다. |
| 영업 기회(선택 사항) | 함께 판매되는 제품 및 서비스의 컬렉션입니다. 영업 종료 직전까지 영업 주기의 여러 단계가 절정에 이른 경우가 많았다.<br>데이터를 사용하여 판매 단계를 통한 기회 진행률을 측정합니다. 예를 들어 3단계에서 4단계로 이동한 상위 기회에 대한 세부 정보를 제공하는 보고서입니다. |
| 구매 그룹(선택 사항) | 제품 또는 서비스 구매를 위한 의사 결정 프로세스와 관련된 조직 내 직원의 컬렉션입니다. <br/>구매 그룹 데이터를 사용하여 캠페인 관리를 통해 구매 그룹을 추적합니다. 예를 들어 주요 구매 그룹의 대상 세그먼트를 만듭니다.<br/> 구매 그룹의 사람들에 대해 보고할 수 있도록 구매 그룹에서 프로필 데이터에 대한 조회를 원할 수 있습니다. |
| 개인 | 회사와 상호 작용한 고유한 이메일 주소로 식별되는 개인. <br/>프로필 데이터를 사용하여 계정 직원을 식별합니다. 예를 들어, 전화 회의에 등록한 계정의 모든 사용자를 타겟팅할 수 있습니다. |

>[!IMPORTANT]
>
>* 계정 기반 연결에 전역 계정 컨테이너를 **사용**&#x200B;한 경우 이벤트 데이터 세트의 모든 레코드에는 계정 ID와 전역 계정 ID가 포함되어야 합니다. 그렇지 않으면 레코드가 생략됩니다.
>* 계정 기반 연결에 전역 계정 컨테이너를 **활성화하지 않음**&#x200B;한 경우 이벤트 데이터 세트의 모든 레코드에는 계정 ID가 있어야 합니다. 그렇지 않으면 레코드가 생략됩니다.

Analysis Workspace에서 특정 B2B 기능에 B2B 컨테이너를 사용할 수 있습니다.

* **세그먼테이션**: [B2B 세그먼트 컨테이너](/help/components/segments/seg-overview.md#b2b-containers)를 사용하면 개인, 세션 또는 이벤트 이상의 컨테이너 범위를 가진 세그먼트를 만들 수 있습니다. 예를 들어 이벤트 등록 세그먼트가 있는 계정 또는 구매 그룹 및 5단계 기회 세그먼트가 있는 미국 계정이 있습니다.

  >[!NOTE]
  >
  >Customer Journey Analytics B2B edition의 계정 기반 설정에 있는 B2B 이벤트 데이터에는 개인 또는 세션이 없는 데이터 행이 포함될 수 있습니다. 영업 기회 단계 진행률을 자세히 설명하는 행 등을 예로 들 수 있습니다. 세그먼트를 평가할 때는 더 이상 사람과 세션이 올바른 기준이 아닐 수 있다는 점을 유의하십시오.
  >

* **속성**: [속성 패널](/help/analysis-workspace/c-panels/attribution.md), [속성 구성 요소 설정](/help/data-views/component-settings/attribution.md), [계산된 지표](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) 또는 [자유 형식 테이블의 열](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)에서 새 B2B 컨테이너를 사용할 수 있습니다. 계정 회신은 13개월로 연장됩니다.

* **시각화**: [폴아웃](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), [흐름](/help/analysis-workspace/visualizations/c-flow/flow.md), [여정 캔버스](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) 및 [집단 테이블](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) 시각화는 새 B2B 컨테이너를 지원합니다. 예를 들어 새 컨테이너를 사용하여 구매 그룹이 콘텐츠를 소비하는 방법 또는 영업 기회 집단이 판매 종료로 이동하는 방법을 이해할 수 있습니다.
[사용자 환경 설정](/help/analysis-workspace/user-preferences.md#visualizations-preferences)에서 이러한 시각화에 대한 기본 컨테이너를 설정할 수도 있습니다.

B2B 컨테이너와 함께 세그먼트, 속성 및 시각화는 딥 B2B 분석 및 통찰력에서 지원합니다.


## 데이터 세트

Customer Journey Analytics B2B는 다음 데이터 유형과 데이터 세트를 구별합니다.

| 데이터 유형 | 시계열 | 컨테이너 레코드 | 필드 레코드 |
|---|---|---|---|
| **데이터 세트** | **이벤트 데이터 세트**<br/>&#x200B;예:<ul><li>디지털 분석</li><li>CRM 이벤트</li><li>대면 이벤트</li><li>콜 센터 데이터</li></ul> | **프로필 데이터 세트**<br/>&#x200B;예:<ul><li>CRM 레코드</li><li>AJO B2B 레코드</li><li>CDP 레코드</li><ul> | **클래스**<br/>&#x200B;예:<ul><li>캠페인 레코드</li><li>마케팅 목록 레코드</li><li>컨텐츠 메타데이터</li><li>제품 레코드</li></ul> |
| 요구 사항 | **타임스탬프**<br>&#x200B;모든 레코드에 필요한 시간:<ul><li>계정 ID</li><li>글로벌 계정 ID</li><li>개인 ID</li></ul> | **계정 ID**<br>&#x200B;레코드에 다음과 같은 컨테이너 ID가 필요합니다.<ul><li>계정</li><li>개인</li><li>기회</li><li>구매 그룹</li></ul> | **일치하는 키**<br>&#x200B;레코드에는 다음과 같은 컨테이너 또는 이벤트 데이터 집합에 포함된 ID가 필요합니다.<ul><li>캠페인 ID</li><li>콘텐츠 ID</li><li>제품 ID</li></ul> |

{style="table-layout:fixed"}

Customer Journey Analytics B2B edition의 계정 기반 연결 예:

![계정 기반 연결 예제](assets/b2b-datasets.svg)

Customer Journey Analytics B2B edition은 [연결 맵](/help/connections/create-connection.md#connection-map) 인터페이스를 제공하여 연결에 있는 데이터 세트 간의 관계에 대한 개요를 제공합니다.


Customer Journey Analytics과 마찬가지로 이벤트 기반 시계열 데이터는 Customer Journey Analytics B2B edition의 핵심입니다. 계정 기반 연결의 주요 차이점은 이벤트 데이터 세트에 있는 모든 레코드에 개인 ID 대신 계정 ID가 필요하다는 것입니다.

Customer Journey Analytics B2B edition에서 계정 기반 연결에 대해 [데이터 세트 설정](/help/connections/create-connection.md#dataset-settings)을 구성할 때 일부 설정에 사용할 수 있는 옵션은 [데이터 세트 유형](/help/connections/create-connection.md#dataset-types)에 따라 다릅니다. 예를 들어 다음을 수행해야 합니다.

* 이벤트 데이터 세트에 대해 구성한 각 컨테이너에 대한 식별자를 지정합니다.
* 프로필 데이터 세트에 대한 계정 필드 또는 글로벌 계정 필드를 정의합니다.
* 조회 데이터 세트에 대해 키 및 이러한 키(필드의 컨테이너별)를 일치시키는 방법을 정의합니다.

## 컨테이너 또는 필드별 일치

필드별 또는 컨테이너별로 데이터 세트와 일치하는지 여부에 관계없이 각 조회 데이터 세트에 대해 정의할 수 있습니다.

### 컨테이너별 일치

레코드 데이터 세트가 컨테이너별 일치를 사용하는 경우 레코드 데이터 세트는 사용자 인터페이스에서 프로필 데이터 세트 유형 및 프로필 데이터 세트로 처리됩니다. 컨테이너 레코드를 포함하고 구성된 컨테이너를 지원하는 데이터 세트에 대해 컨테이너별 일치를 사용합니다. 예를 들어 구매 그룹 데이터 세트가 있습니다.

### 필드별 일치

레코드 데이터 세트가 필드별 일치를 사용하는 경우 레코드 데이터 세트는 사용자 인터페이스에서 조회 데이터 세트 유형 및 조회 데이터 세트로 처리됩니다. 조회를 통해 추가 분류 세부 사항이 포함된 데이터 세트에서 필드별 일치 를 사용하십시오. 예를 들어 마케팅 목록 멤버 데이터 세트 또는 제품 세부 사항 데이터 세트가 있습니다.


## 개인 및 계정 기반 데이터 보고

사용자 기반 컨테이너(및 개인 ID)와 계정 기반 컨테이너(및 계정 ID)에 대해 보고하려면 Customer Journey Analytics 내에서 두 개의 개별 연결을 설정해야 합니다. 개인을 기본 ID로 선택하는 연결 하나와 계정을 기본 ID로 선택하는 연결 하나. Customer Journey Analytics은 단일 컨테이너 계층에서 개인 기반 및 계정 기반 보고를 지원하지 않습니다.

