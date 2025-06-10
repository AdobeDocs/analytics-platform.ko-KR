---
title: 콜센터 및 웹 데이터 가져오기
description: 콜센터와 웹 사이트 데이터를 연결하는 데이터 세트를 만드는 방법을 알아봅니다.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 88%

---

# 콜센터 및 웹 데이터 가져오기

Customer Journey Analytics는 다양한 소스의 데이터 세트를 하나의 Analysis Workspace 프로젝트로 결합하는 강력하고 중요한 기능을 제공합니다. 조직에서 웹 사이트 데이터를 콜센터 데이터와 결합하는 방법을 이해하려면 이 안내서를 사용합니다. 예를 들어, 고객 지원에 문의하기 전에 고객이 취한 조치, 고객이 조회한 콘텐츠와 검색한 약관을 이해할 수 있습니다. 그런 다음 콜센터에 호출하지 않고도 고객이 스스로 문제를 효율적으로 해결할 수 있도록 콘텐츠와 셀프서비스 도구를 개선하고 결정할 수 있습니다.

## 사전 요구 사항

* 이러한 두 데이터 세트를 결합하는 데 가장 중요한 구성 요소는 각 데이터 소스 간의 공통 식별자입니다. 고객 ID, 해시된 이메일, 로그인 사용자 이름 또는 전화 번호를 예로 들 수 있습니다.
* Adobe Experience Platform 및 Customer Journey Analytics에 모두 액세스
* 데이터 세트에 대화형 음성 응답 시스템의 로그가 포함되어 있는 경우 Adobe에서는 데이터를 플랫폼으로 가져오기 전에 프롬프트 상호 작용만 포함하도록 데이터를 처리할 것을 권장합니다.
* 데이터 세트에 통화 로그가 포함되어 있으면 Adobe에서는 다음 열을 포함할 것을 권장합니다.
   * 통화가 시작된 날짜/시간
   * 통화 이유
   * 콜센터 ID
   * 콜센터 상담사 ID
   * 통화 기간
   * 통화 결과
   * 통화 비용(가능한 경우)
   * 조직에서 포함할 추가 통화 메타데이터

## 웹 및 콜센터 데이터를 플랫폼으로 가져오기

데이터를 Adobe Experience Platform으로 가져옵니다. Adobe Experience Platform 문서에서 [스키마 만들기](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ko-KR) 및 [데이터 수집](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ko-KR)을 참조하십시오.

데이터를 플랫폼으로 가져올 때 다음 팁을 통해 결과 보고서의 통찰력을 높일 수 있습니다.

* 콜센터와 웹 데이터를 함께 연결하는 데 사용되는 식별자의 형식이 유사한지 확인합니다.
* 각 데이터 세트에 데이터 소스를 포함합니다. 예를 들어 `data_source`각 스키마에 열을 포함하고 모든 이벤트의 값을 각각 `"Web"` 또는 `"Call center"`로 설정합니다.<!--mapper-->

## 개인 ID 결합

Customer Journey Analytics에서 [결합된 데이터 세트](/help/connections/combined-dataset.md)를 생성하려면 공통 식별자가 필요합니다.

* 이미 데이터 세트 모두에 모든 이벤트에 대한 공통 식별자가 있는 경우 이 단계를 건너뛰고 연결을 만들 수 있습니다.
* 데이터 세트 중 하나에 일부 이벤트에만 적용되는 공통 식별자가 있으면 이 두 데이터 세트에 대해 크로스 채널 분석을 활성화하는 단계에 대해 [결합](/help/stitching/overview.md)을 사용하여 데이터를 결합할 수 있습니다.

## Customer Journey Analytics에 연결 만들기

Customer Journey Analytics에서 [연결을 만듭니다](/help/connections/create-connection.md).

* CCA를 사용하는 경우 결합된 새 데이터 세트를 사용할 수 있습니다. 새로 만든 결합된 ID 필드를 개인 ID로 사용합니다.
* 그렇지 않으면 연결에서 사용할 원본 웹 데이터 세트와 콜센터 데이터 세트를 모두 선택할 수 있습니다.

## 데이터 보기 만들기

연결을 만든 후 Analysis Workspace에서 사용할 [데이터 보기를 만들 수](/help/data-views/create-dataview.md) 있습니다. 유용한 구성 요소에 포함되는 사항:

* 마지막 터치와 세션 지속성이 적용되는 페이지 차원. 호출하기 전에 고객이 조회한 콜센터 지표와 마지막 페이지를 연결할 수 있습니다.
* 호출 지표는 ‘콜센터 사유’ 스키마 필드를 사용하여 발생 항목을 늘릴 수 있습니다. 세션당 한 번만 늘어나도록 [지표 중복 제거](/help/data-views/component-settings/metric-deduplication.md)를 사용합니다.

## 시각화 만들기

다음 시각화는 결합된 데이터 세트에서 통찰력을 얻는 데 사용할 수 있습니다.

### 데이터 세트 겹치기

이 시각화는 CCA가 데이터를 얼마나 잘 결합하는지 이해하는 데 도움이 됩니다.

1. 두 개의 세그먼트를 만듭니다. 이 두 세그먼트에 사용된 변수는 각 이벤트의 데이터 소스를 반영하는 데 사용한 것과 동일한 변수입니다. 자세한 내용은 [세그먼트 만들기](/help/components/segments/seg-create.md)를 참조하십시오.
   * 데이터 세트 ID가 웹 데이터와 동일한 개인 컨테이너
   * 데이터 세트 ID가 콜센터 데이터와 같은 개인 컨테이너
2. Analysis Workspace에서 [벤](/help/analysis-workspace/visualizations/venn.md) 시각화를 작업 영역 캔버스로 드래그합니다.
3. 새로 만든 두 개의 세그먼트를 **[!UICONTROL 세그먼트 추가]** 영역으로 드래그하고 사람 지표를 **[!UICONTROL 지표 추가]** 영역으로 드래그합니다.

결과 벤 시각화는 웹 데이터와 콜센터 데이터를 모두 포함하는 데이터 세트에 있는 사람 수를 보여 줍니다. 겹치는 부분이 클수록 결합된 사람이 많습니다. 겹치지 않는 영역은 하나의 데이터 세트 또는 다른 데이터 세트에만 있는 사람을 나타냅니다.

### 웹 페이지에 콜센터 이벤트 속성 지정

이 자유 형식 테이블을 사용하면 콜센터 이벤트에 기여하는 상위 페이지를 볼 수 있습니다. 먼저 원하는 차원과 지표에 올바른 속성 모델이 있는지 확인합니다.

1. 웹 페이지 이름을 포함하는 차원을 자유 형식 테이블 시각화로 드래그합니다.
1. 지표를 측정하려는 원하는 콜센터 지표로 바꿉니다.
1. 지표 헤더 근처에 있는 톱니바퀴 아이콘을 클릭합니다. **[!UICONTROL 비기본 속성 모델 사용]**&#x200B;을 클릭합니다.
1. 원하는 [속성 모델](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)을 설정합니다. 예: 반감기가 15분인 시간 감소 모델 및 세션의 전환 확인 기간. 이 속성 모델은 콜센터에 접수되는 호출을 유도하는 페이지에 크레딧을 제공합니다.

결과 보고서는 콜센터에 접수되는 호출을 유도하는 상위 페이지를 보여 줍니다. <!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

이 테이블과 함께 사유 또는 범주를 기준으로 호출을 분할하여 통찰력을 추가로 높일 수 있습니다.

1. 구성 요소 목록의 ‘호출 사유’ 차원 아래에 있는 오른쪽 V자 버튼을 클릭합니다. 이 작업을 수행하면 개별 차원 값이 표시됩니다.
2. &#39;호출&#39; 지표 아래에 있는 원하는 차원 값을 드래그합니다. 지표는 각 호출 사유를 기준으로 해당 지표를 세그먼트화합니다.
3. 자세히 들여다 보려는 각 호출 사유에 대해 이 작업을 반복합니다. &#39;모든 세션&#39; 세그먼트를 사용하여 총계를 조회합니다.

<!-- screenshot -->

### 플로우 시각화

콜센터 채널을 사용하기 전에 고객이 수행할 작업에 대한 통찰력을 얻을 수 있습니다. 이 플로우 시각화를 통해 콜센터 문의 시 고객이 가장 자주 사용하는 여정을 이해할 수 있습니다. 이 통찰력을 사용하면 가장 효과적인 개선 사항을 결정하여 고객의 호출 가능성을 줄일 수 있습니다.

1. 왼쪽의 **[!UICONTROL 시각화]** 탭을 클릭하고 플로우 시각화를 작업 영역 캔버스로 드래그합니다.
2. 왼쪽의 **[!UICONTROL 구성 요소]** 탭을 클릭하고 ‘호출 사유’ 차원을 찾습니다.
3. 이 차원 옆의 오른쪽 V자 버튼을 클릭합니다. 이 작업을 수행하면 개별 차원 값이 표시됩니다.
4. 원하는 호출 사유 차원 항목을 플로우 시각화의 가운데 위치로 드래그합니다.
5. 플로우 시각화는 이전 및 다음 호출 사유를 자동으로 입력합니다. 이전 호출 사유를 웹 사이트 페이지 차원으로 대체합니다.
6. 플로우 시각화 오른쪽 상단의 톱니바퀴 아이콘을 클릭하고 플로우 컨테이너를 **[!UICONTROL 세션]**&#x200B;으로 변경합니다.

### 히스토그램

1회, 2회 또는 6회 이상 호출한 고객 수는 얼마나 됩니까? 이들 고객 중 일부는 웹 사이트를 방문하지 않습니다. 히스토그램 시각화를 사용하여 각 버킷에 해당되는 고객의 수를 결정합니다. 고객이 웹 사이트를 방문하지 않는 경우 셀프서비스를 권장하는 방법을 참조하십시오.

1. 왼쪽의 **[!UICONTROL 시각화]** 탭을 클릭하고 히스토그램 시각화를 작업 영역 캔버스로 드래그합니다.
2. 왼쪽의 **[!UICONTROL 구성 요소]** 탭을 클릭하고 호출 지표를 히스토그램 시각화로 드래그합니다.
3. 시각화 중앙에 있는 **[!UICONTROL 고급 설정 표시]**&#x200B;를 클릭하고 원하는 버킷을 사용자 지정합니다.
4. **[!UICONTROL 빌드]**&#x200B;를 클릭합니다.

<!--
### Web to call, call to web

### Fallout

Fallout sessions - session

All sessions > page views metric > calls metric

All sessions > calls metric > page views

Orrr we could also use dataset ID

step 1: all sessions
step 2: 


### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of segments - facets to their business. Segments were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really segments)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential segments, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
