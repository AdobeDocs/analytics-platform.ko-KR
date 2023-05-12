---
description: AEP Customer AI 데이터가 CJA의 작업 영역과 어떻게 통합되는지 알아보십시오.
title: CJA와 Customer AI 데이터 통합
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: b56dd36d85cd34179166ad9a6bc45f3f641e9697
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 72%

---

# CJA와 Customer AI 데이터 통합

{{release-limited-testing}}

Adobe Experience Platform Intelligent Services의 일부인 [Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=ko-KR)는 마케터에게 개별 수준에서 고객 예측을 생성할 수 있는 권한을 제공합니다.

영향력 있는 요소를 통해 Customer AI는 고객이 무엇을 할 수 있고 왜 하는지 알려 줄 수 있습니다. 또한 마케터는 Customer AI 예측 및 통찰력을 활용하여 가장 적절한 오퍼와 메시지를 제공함으로써 고객 경험을 개인화할 수 있습니다.

Customer AI는 성향 점수에 대해 개인 행동 데이터와 프로필 데이터에 의존합니다. Customer AI는 Adobe Analytics, Adobe Audience Manager, 소비자 경험 이벤트 데이터 및 경험 이벤트 데이터를 비롯한 여러 데이터 소스를 가져올 수 있어 유연하게 사용할 수 있습니다. Experience Platform 소스 커넥터를 사용하여 Adobe Audience Manager 및 Adobe Analytics 데이터를 가져오는 경우 모델은 자동으로 표준 이벤트 유형을 선택하여 모델을 교육하고 평가합니다. 표준 이벤트 유형 없이 고유한 경험 이벤트 데이터 세트를 가져오는 경우 해당 모델에서 사용하려면 모든 관련 필드를 사용자 정의 이벤트 또는 프로필 속성으로 매핑해야 합니다. 이는 Experience Platform의 Customer AI 구성 단계에서 수행할 수 있습니다.

고객 AI는 CJA의 데이터 보기 및 보고에서 고객 AI 지원 데이터 세트를 활용할 수 있는 범위 내에서 CJA(Customer Journey Analytics)과 통합할 수 있습니다. :

* **시간 경과에 따른 사용자 세그먼트의 성향 점수를 추적합니다**.
   * 사용 사례: 특정 세그먼트에서 고객이 전환할 가능성을 파악합니다.
   * 예: 호텔 체인의 마케팅 담당자는 호텔 콘서트장에서 공연 티켓을 구매할 가능성이 있는지 알고 싶어합니다.
* **성향 점수와 관련된 성공 이벤트 또는 속성을 분석합니다**.
   * 사용 사례: 성향 점수와 연관된 속성 또는 성공 이벤트를 이해합니다.
   * 예: 호텔 체인의 한 마케터는 호텔의 콘서트 장소에서 티켓 구매를 하는 것이 성향 점수와 어떻게 관련이 있는지 알고 싶어한다.
* **다양한 스코어링 실행에 대한 고객 성향에 대한 입력 플로우를 따르십시오**.
   * 사용 사례: 처음에는 성향 사용자가 낮았고 시간이 지나면서 성향 사용자가 높은 사용자를 이해합니다.
   * 예: 호텔 체인의 마케팅 담당자는 처음에 어느 호텔 고객이 쇼 티켓을 구매하려는 경향이 적은 고객으로 식별되었는지 알고 싶어하지만 시간이 지나면서 쇼 티켓을 구매하려는 경향이 높은 고객이 되었다.
* **성향 분포를 살펴봅니다**.
   * 사용 사례: 세그먼트를 정의할 때 더 정확하게 성향 점수의 분포를 이해합니다.
   * 예: 한 소매업체는 제품 하나에 50달러에 대해 특정 판촉을 실행하려고 합니다. 이 업체는 예산 등의 이유로 인해 매우 제한적인 프로모션만 진행하기를 원할 수 있습니다. 데이터를 분석하고 상위 80% 이상의 고객만을 대상으로 합니다.
* **시간의 흐름에 따라 특정 집단에 대한 작업을 수행하는 경향을 살펴봅니다**.
   * 사용 사례: 시간에 따라 특정 집단을 추적합니다.
   * 예: 호텔 체인의 마케터는 시간이 지남에 따라 자신의 청동기 대 실버 계층이나 실버 계층과 골드 등급을 비교하려고 한다. 따라서 그들은 시간이 지남에 따라 호텔을 예약하는 각 집단의 성향을 볼 수 있습니다.

Customer AI 데이터를 CJA와 실제로 통합하려면 다음 단계를 수행합니다.

>[!NOTE]
>
>일부 단계는 CJA에서 출력 작업을 수행하기 전에 Adobe Experience Platform에서 수행됩니다.


## 1단계: Customer AI 인스턴스 구성

데이터를 준비하고 모든 자격 증명 및 스키마를 준비한 후에는 Adobe Experience Platform의 [Customer AI 인스턴스 구성](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=ko-KR) 안내서를 따라 시작합니다.

## 2단계: Customer AI 데이터 세트에 대한 CJA 연결 설정

CJA에서는 이제 Customer AI용으로 계측된 Experience Platform 데이터 세트에 대한 [하나 이상의 연결을 생성](/help/connections/create-connection.md)할 수 있습니다. “계정 업그레이드 가능성”과 같은 각 예측은 하나의 데이터 세트와 동일합니다. 이러한 데이터 세트에는 “EE Format – name_of_application의 Customer AI 스코어” 접두어가 붙습니다.

>[!IMPORTANT]
>
>1단계에서 구성하는 동안 CJA에 대한 점수를 활성화하기 위한 토글이 켜져 있는 경우 각 Customer AI 인스턴스에는 두 개의 출력 데이터 세트가 있습니다. 하나의 출력 데이터 세트는 프로필 XDM 형식으로 표시되고 다른 하나는 Experience Event XDM 형식으로 표시됩니다.

![CAI 스코어](assets/cai-scores.png)

![연결 생성](assets/create-conn.png)

다음은 CJA가 기존 또는 새 데이터 세트의 일부로 가져올 XDM 스키마의 예입니다.

![CAI 스키마](assets/cai-schema.png)

(예제는 프로필 데이터 세트이며 동일한 스키마 오브젝트 세트는 CJA가 가져올 경험 이벤트 데이터 세트의 일부입니다. 경험 이벤트 데이터 세트에는 점수 날짜로 타임스탬프가 포함됩니다.) 이 모델에서 득점한 모든 고객은 점수, 점수 날짜 등을 갖게 됩니다. 연관되어 있습니다.

## 3단계: 연결을 기반으로 데이터 보기 만들기

CJA에서는 이제 설정한 연결의 일부로 가져온 차원(점수, 점수 날짜, 확률 등) 및 지표를 사용하여 [데이터 보기를 생성](/help/data-views/create-dataview.md)할 수 있습니다.

![데이터 보기 만들기](assets/create-dataview.png)

## 4단계: 작업 영역에서 CAI 점수 보고

CJA 작업 영역에서 새 프로젝트를 만들고 시각화를 가져올 수 있습니다.

### 트렌드 성향 점수

다음은 스택 막대 차트에서 시간 경과에 따른 사용자 세그먼트의 성향 점수 추세를 나타내는 CAI 데이터가 있는 작업 영역 프로젝트의 예입니다.

![스코어 버킷](assets/workspace-scores.png)

### 이유 코드가 있는 표

다음은 세그먼트의 성향이 높거나 낮은 이유의 코드가 표시되는 표입니다.

![이유 코드](assets/reason-codes.png)

### 고객 성향 항목 플로우

이 플로우는 다양한 스코어링 실행에 대한 고객 성향에 대한 입력 플로우를 보여 줍니다.

![항목 플로우](assets/flow.png)

### 성향 점수 분포

이 막대 차트는 성향 점수 분포를 보여 줍니다.

![배포](assets/distribution.png)

### 성향 겹침

이 벤 다이어그램은 여러 점수 실행에 대한 성향 겹침을 보여 줍니다.

![성향 겹침](assets/venn.png)
