---
description: AEP Customer AI가 CJA에서 Workspace와 통합되는 방법을 알아봅니다.
title: CJA와 고객 AI 통합
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 77b253390dafb27228995f339d138eb9f4fa2c56
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# CJA와 고객 AI 통합

>[!NOTE]
>
>이 기능은 2022년 5월 25일에 릴리스됩니다.

[고객 AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en)는 Adobe Experience Platform Intelligent Services의 일부로 마케터에게 개별 수준에서 고객 예측을 생성할 수 있는 기능을 제공합니다.

고객 AI는 영향력 있는 요소의 도움을 받아 고객이 수행해야 하는 작업과 그 이유를 파악할 수 있습니다. 또한 마케터는 가장 적합한 오퍼 및 메시지를 제공하여 고객 경험을 개인화할 수 있도록 Customer AI 예측 및 인사이트를 활용할 수 있습니다.

고객 AI는 다음 데이터 세트 중 하나를 분석하여 이탈이나 전환 성향 점수를 예측합니다.

* Analytics 소스 커넥터를 사용하는 Adobe Analytics 데이터
* Audience Manager 소스 커넥터를 사용하는 Adobe Audience Manager 데이터
* 경험 이벤트(EE) 데이터 세트
* CEE(소비자 경험 이벤트) 데이터 세트

Customer AI는 CJA의 데이터 보기 및 보고에서 고객 AI 지원 데이터 세트를 활용할 수 있을 정도로 CJA(Customer Journey Analytics)과 통합됩니다.

## 워크플로

일부 단계는 CJA에서 출력을 사용하기 전에 Adobe Experience Platform에서 수행됩니다.

### 1단계: Customer AI 점수 다운로드

설명된 대로 Experience Platform API 호출 조합을 통해 Customer AI 점수를 다운로드합니다 [여기](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/getting-started.html?lang=en#downloading-customer-ai-scores).

### 2단계: 고객 AI 입력 및 출력 정의

이 프로세스는 [고객 AI의 입력 및 출력](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/input-output.html?lang=en) 설명서.

### 3단계: 고객 AI 인스턴스 구성

데이터를 준비하고 모든 자격 증명과 스키마를 준비했으면 다음을 수행하여 시작하십시오 [고객 AI 인스턴스 구성](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) 안내서.

### 4단계: 고객 AI 데이터 세트에 CJA 연결 설정

CJA에서 이제 다음을 수행할 수 있습니다 [하나 이상의 연결 만들기](/help/connections/create-connection.md) 고객 AI용으로 구현된 데이터 세트를 Experience Platform 할 수 있습니다. 이러한 데이터 세트는 다음과 같이 &quot;고객 AI 점수&quot; 접두사와 함께 표시됩니다.

![차이점수](assets/cai-scores.png)

&quot;계정 업그레이드 가능성&quot;과 같은 각 예측은 하나의 데이터 세트와 같습니다.

다음은 CJA가 기존 또는 새 데이터 세트의 일부로 가져오는 XDM 스키마의 예입니다.

![CAI 스키마](assets/cai-schema.png)

(예제에서는 프로필 데이터 세트를 사용합니다. 동일한 스키마 개체 세트는 CJA가 가져오는 경험 이벤트 데이터 세트에 포함됩니다. Experience Event 데이터 세트에는 점수 날짜로 타임스탬프가 포함됩니다.) 이 모델에서 점수가 매겨지는 모든 고객은 점수, scoreDate 등이 있습니다. 관련 항목.

### 5단계: 이러한 연결을 기반으로 데이터 보기 만들기

이제 CJA에서 다음을 수행할 수 있습니다 [데이터 보기 만들기](/help/data-views/create-dataview.md) 설정한 연결의 일부로 가져온 차원(예: 점수, 점수 날짜, 확률 등)과 함께.

### 6단계: Workspace에서 CAI 점수 보고

다음은 누적 막대 차트에 점수 날짜를 표시하는 CAI 데이터가 있는 작업 공간 프로젝트의 예입니다.

![점수 버킷](assets/workspace-scores.png)

