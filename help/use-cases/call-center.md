---
title: 콜 센터 및 웹 데이터 가져오기
description: 콜 센터 및 웹 사이트 데이터를 연결하는 데이터 세트를 만드는 방법을 알아봅니다.
translation-type: tm+mt
source-git-commit: 8d2f70ad47dcf9b97808da3a04d32d3412a1f0c8
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 3%

---


# 콜 센터 및 웹 데이터 가져오기

Customer Journey Analytics은 다양한 소스의 데이터 세트를 하나의 작업 공간 프로젝트로 결합하는 강력하고 중요한 기능을 제공합니다. 조직에서 웹 사이트의 데이터를 콜 센터에서 생성된 데이터로 연결하는 방법을 이해하려면 이 안내서를 사용합니다.

## 전제 조건

* 이러한 두 데이터 세트를 결합하는 데 가장 중요한 구성 요소는 각 데이터 소스 간에 공통적인 식별자입니다. 고객 ID, 해시된 이메일, 로그인 사용자 이름 또는 전화 번호를 예로 들 수 있습니다.
* Adobe Experience Platform 및 Customer Journey Analytics에 모두 액세스
* 데이터 세트에 대화형 음성 응답 시스템의 로그가 포함되어 있는 경우 Adobe은 데이터를 플랫폼으로 가져오기 전에 프롬프트 상호 작용만 포함하도록 데이터를 처리하는 것이 좋습니다.
* 데이터 세트에 호출 로그가 포함되어 있으면 Adobe은 다음 열을 포함하는 것이 좋습니다.
   * 호출이 시작된 날짜/시간
   * 호출 이유
   * 콜 센터 ID
   * 콜 센터 에이전트 ID
   * 호출 기간
   * 호출 결과
   * 통화 비용(가능한 경우)
   * 조직에서 포함할 추가 호출 메타 데이터

## 웹 및 콜 센터 데이터를 플랫폼으로 가져오기

Adobe Experience Platform으로 데이터 가져오기를 시작합니다. Adobe Experience Platform 문서에서 [스키마 만들기](https://docs.adobe.com/content/help/ko-KR/experience-platform/xdm/tutorials/create-schema-ui.html) 및 [데이터 인제스트](https://docs.adobe.com/content/help/ko-KR/experience-platform/ingestion/home.html)를 참조하십시오.

데이터를 플랫폼으로 가져올 때 다음 팁을 통해 결과 보고서의 통찰력을 높일 수 있습니다.

* 콜 센터와 웹 데이터를 함께 연결하는 데 사용되는 식별자의 형식이 유사한지 확인합니다.
* 각 데이터 세트에 데이터 소스를 포함합니다. 예를 들어 각 스키마에 `data_source` 열을 포함하고 모든 이벤트의 값을 각각 `"Web"` 또는 `"Call center"`로 설정합니다.<!--mapper-->

## 사람 ID 연결

CJA에는 [결합된 데이터 집합](../connections/combined-dataset.md)을(를) 생성하려면 공통 식별자가 필요합니다.

* 데이터 세트에 이미 데이터 세트 모두에 모든 이벤트에 대한 공통 식별자가 있는 경우 이 단계를 건너뛰고 연결을 만들 수 있습니다.
* 데이터 세트 중 하나에 일부 이벤트에만 공통 식별자가 있으면 크로스 채널 분석을 사용하여 데이터를 결합할 수 있습니다. 이러한 두 데이터 세트에 대해 CCA를 활성화하는 단계는 [크로스채널 분석 개요](/help/connections/cca/overview.md)를 참조하십시오.

## CJA에서 연결 만들기

[CJA](/help/connections/create-connection.md) 에서 연결을 만듭니다.

* CCA를 사용하는 경우 새 연결된 데이터 세트를 사용할 수 있습니다. 새로 만든 스티칭된 ID 필드를 사람 ID로 사용합니다.
* 그렇지 않으면 연결에서 사용할 원본 웹 데이터 세트와 콜 센터 데이터 세트를 모두 선택할 수 있습니다.

## 데이터 보기 만들기

연결을 만든 후 Analysis Workspace에서 사용할 [데이터 보기](/help/data-views/create-dataview.md)를 만들 수 있습니다.<!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## 시각화 만들기

다음 시각화는 연결된 데이터세트에서 통찰력을 얻는 데 사용할 수 있습니다.

### 데이터 세트 겹치기

이 시각화는 CCA가 데이터를 얼마나 잘 결합하는지 이해하는 데 도움이 됩니다.

1. 2개의 필터를 만듭니다. 이 두 필터에 사용되는 변수는 각 이벤트의 데이터 소스를 반영하는 것과 동일한 변수입니다. 자세한 내용은 [필터](/help/components/filters/create-filters.md) 만들기를 참조하십시오.
   * 데이터 세트 ID가 웹 데이터와 동일한 개인 컨테이너
   * 데이터 세트 ID가 콜 센터 데이터와 같은 개인 컨테이너
2. Analysis Workspace에서 [벤](/help/analysis-workspace/visualizations/venn.md) 시각화를 작업 영역 캔버스로 드래그합니다.
3. 새로 만든 필터 2개를 **[!UICONTROL 필터 추가]** 영역으로 드래그하고 사람 지표를 **[!UICONTROL 지표 추가]** 영역으로 드래그합니다.

결과 벤 시각화는 웹 데이터와 콜 센터 데이터를 모두 포함하는 데이터 세트에 있는 사람 수를 보여줍니다. 겹치기가 클수록 성공적으로 봉합된 사람이 많아진다. 겹치지 않는 영역은 하나의 데이터 세트 또는 다른 데이터 세트에만 거주하는 사람을 나타냅니다.

### 웹 페이지에 콜 센터 이벤트 특성

이 자유 형식 테이블을 사용하면 콜 센터 이벤트에 기여하는 상위 페이지를 볼 수 있습니다. 먼저 원하는 차원과 지표에 올바른 속성 모델이 있는지 확인합니다.

1. 웹 페이지 이름을 포함하는 차원을 자유 형식 테이블 시각화로 드래그합니다.
1. 지표를 전환을 측정하려는 원하는 콜 센터 지표로 바꿉니다.
1. 지표 헤더 근처에 있는 톱니바퀴 아이콘을 클릭합니다. **[!UICONTROL 기본이 아닌 속성 모델 사용]**&#x200B;을 클릭합니다.
1. 원하는 [속성 모델](/help/data-views/configure-dataviews.md#Attribution-model)을 설정합니다.

결과 보고서는 콜 센터 데이터의 상위 지표를 보여줍니다.<!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: -->

<!--  use target (AB testing) to test new versions of these pages so they reduce calls (using an eVar to determine A/B?)
  filter by specific call reason using workspace dropdowns
  visualize flow of pages > call reason 
-->