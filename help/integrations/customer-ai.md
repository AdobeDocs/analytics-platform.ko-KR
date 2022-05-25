---
description: AEP Customer AI가 CJA에서 Workspace와 통합되는 방법을 알아봅니다.
title: CJA와 고객 AI 통합
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: c1e9fdb0e6d62da91b2b5c81eb21462890945b62
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# CJA와 고객 AI 통합

[고객 AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en)는 Adobe Experience Platform Intelligent Services의 일부로 마케터에게 개별 수준에서 고객 예측을 생성할 수 있는 기능을 제공합니다.

고객 AI는 영향력 있는 요소의 도움을 받아 고객이 수행해야 하는 작업과 그 이유를 파악할 수 있습니다. 또한 마케터는 가장 적합한 오퍼 및 메시지를 제공하여 고객 경험을 개인화할 수 있도록 Customer AI 예측 및 인사이트를 활용할 수 있습니다.

고객 AI는 성향 점수에 대한 개별 행동 데이터와 프로필 데이터를 사용합니다. Customer AI는 Adobe Analytics, Adobe Audience Manager, Consumer Experience 이벤트 데이터 및 Experience Event 데이터를 비롯한 여러 데이터 소스를 이용할 수 있다는 점에서 유연합니다. AEP Data Connector를 사용하여 Adobe Audience Manager 및 Adobe Analytics 데이터를 가져오는 경우 모델은 표준 이벤트 유형을 자동으로 선택하여 모델을 교육하고 점수를 매깁니다. 표준 이벤트 유형 없이 고유한 경험 이벤트 데이터 세트를 가져오는 경우, 모델에서 해당 필드를 사용하려면 관련 필드를 사용자 지정 이벤트 또는 프로필 속성으로 매핑해야 합니다. 이 작업은 고객 AI 구성 단계에서 수행할 수 있습니다. &#x200B;

Customer AI는 CJA의 데이터 보기 및 보고에서 고객 AI 지원 데이터 세트를 활용할 수 있을 정도로 CJA(Customer Journey Analytics)과 통합됩니다. 이 통합을 통해 다음을 수행할 수 있습니다

* **시간에 따라 사용자 세그먼트에 대한 성향 점수를 추적합니다**. 사용 사례 예: 호텔 고객이 호텔 콘서트장에서 공연 티켓을 구매할 가능성은 얼마나 됩니까?
* **성향 점수와 관련된 성공 이벤트 또는 속성을 분석합니다**. &#x200B;사용 사례 예: 성향 점수와 연관된 속성 또는 성공 이벤트를 이해하려고 합니다.
* **다양한 점수 실행에서 고객 성향을 파악하기 위한 입력 흐름을 따릅니다**. 사용 사례 예: 처음에는 성향 사용자가 낮았고 시간이 지남에 따라 성향 사용자가 높은 사용자를 &#x200B; 이해하고 싶습니다.
* **성향 분포에 대해 살펴보십시오**. 사용 사례: 세그먼트에 대한 성향 점수의 분포를 이해하려고 합니다. &#x200B;예: 한 소매업체에서 한 제품의 50달러에 대해 특정 판촉을 경영하려고 합니다.  그들은 예산 등으로 인해 매우 제한된 승진만을 실행할 수 있습니다. 데이터를 분석하고 상위 80% &#x200B; 이상의 고객만 타겟팅하기로 합니다.
* **시간에 따라 특정 집단에 대한 작업을 수행하는 경향을 보십시오**. 사용 사례: 시간이 지남에 따라 특정 집단을 추적하고 싶습니다. 첫 번째 집단이 비슷하지만 시간이 지남에 따라 특정 집단을 추적할 수 &#x200B; 있습니다. 숙박 예: 마케터는 시간이 지남에 따라 청동기 대비 실버 계층이나 은 계층과 골드 등급을 추적할 수 있습니다. 시간이 지남에 따라 호텔을 예약하는 각 집단의 성향을 볼 수 있습니다. &#x200B;

## 워크플로

일부 단계는 CJA에서 출력을 사용하기 전에 Adobe Experience Platform에서 수행됩니다.

### 1단계: 고객 AI 인스턴스 구성

데이터를 준비하고 모든 자격 증명과 스키마를 준비했으면 다음을 수행하여 시작하십시오 [고객 AI 인스턴스 구성](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) 안내서.

### 2단계: 고객 AI 데이터 세트에 CJA 연결 설정

CJA에서 이제 다음을 수행할 수 있습니다 [하나 이상의 연결 만들기](/help/connections/create-connection.md) 고객 AI용으로 구현된 데이터 세트를 Experience Platform 할 수 있습니다. &quot;계정 업그레이드 가능성&quot;과 같은 각 예측은 하나의 데이터 세트에 해당합니다. 이러한 데이터 세트는 &quot;Customer AI Score in EE Format - name_of_application&quot; 접두사와 함께 나타납니다.

>[!IMPORTANT]
>
>1단계의 구성 중에 CJA에 대한 점수를 활성화하기 위해 토글이 설정된 경우 각 Customer AI 인스턴스에는 두 개의 출력 데이터 세트가 있습니다. 하나의 출력 데이터 세트가 프로필 XDM 형식과 Experience Event XDM 형식으로 표시됩니다.

![차이점수](assets/cai-scores.png)

![연결 생성](assets/create-conn.png)

다음은 CJA가 기존 또는 새 데이터 세트의 일부로 가져오는 XDM 스키마의 예입니다.

![CAI 스키마](assets/cai-schema.png)

(예제에서는 프로필 데이터 세트를 사용합니다. 동일한 스키마 개체 세트는 CJA가 가져오는 경험 이벤트 데이터 세트에 포함됩니다. Experience Event 데이터 세트에는 점수 날짜로 타임스탬프가 포함됩니다.) 이 모델에서 점수가 매겨지는 모든 고객은 점수, scoreDate 등이 있습니다. 관련 항목.

### 3단계: 이러한 연결을 기반으로 데이터 보기 만들기

이제 CJA에서 다음을 수행할 수 있습니다 [데이터 보기 만들기](/help/data-views/create-dataview.md) 설정 연결의 일부로 가져온 차원(점수, 점수 날짜, 확률 등)과 지표를 사용할 수 있습니다.

![데이터 뷰 만들기](assets/create-dataview.png)

### 4단계: Workspace에서 CAI 점수 보고

이제 CJA Workspace에서 새 프로젝트를 만들고 시각화를 가져올 수 있습니다.

다음은 누적 막대 차트에서 시간에 따른 사용자 세그먼트에 대한 성향 점수를 트렌드화하는 CAI 데이터가 있는 작업 공간 프로젝트&#x200B;의 예입니다.

![점수 버킷](assets/workspace-scores.png)

다음은 세그먼트에 높은 성향 또는 낮은 성향 코드가 있는 이유 코드를 보여주는 &#x200B; 표입니다.

![이유 코드](assets/reason-codes.png)

이 흐름 다이어그램은 다양한 점수 실행에서 고객 성향&#x200B;에 대한 입력 흐름을 보여줍니다.

![시작 흐름](assets/flow.png)

이 막대 차트는 성향 점수의 분포를 보여줍니다&#x200B;.

![배포](assets/distribution.png)

이 벤 다이어그램은 다른 점수 실행에서 겹치는 성향을 보여줍니다.

![성향 겹침](assets/venn.png)
