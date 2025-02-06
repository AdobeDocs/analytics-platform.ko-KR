---
title: 콘텐츠 분석 개요
description: 콘텐츠 분석 개요
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: c63fa8f776fcf3390d312fb44ae6c422e7fa7222
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 0%

---

# 콘텐츠 분석 개요

<!-- 
This is a placeholder article for upcoming Content Analytics documentation. Currently used to set up contextual help entries for developer working on onboarding UI and workspace UI 
-->

>[!WARNING]
>
>이 문서는 예정된 최종 버전의 임시 비공식 초안 버전이며 Content Analytics 설명서의 일부입니다. 모든 내용은 변경될 수 있으며 이 문서의 현재 버전에서 파생될 수 있는 법적 의무는 없습니다.
>

{#release-limited-testing}

콘텐츠 분석은 마케터가 콘텐츠가 비즈니스가 정의한 주요 성능 지표에 미치는 영향을 이해할 수 있도록 도와줍니다. 콘텐츠 조각을 테스트하기 위한 기존의 마이크로 수준 기반 기능(예: A/B 테스트) 외에도 Content Analytics는 콘텐츠가 매크로 수준에서 어떻게 영향을 미치고 있는지에 대한 통찰력을 제공합니다. 예를 들어, 고객이 특정 톤의 목소리, 특정 색상 팔레트 또는 특정 테마에 더 잘 반응합니까?

콘텐츠 분석은 AI 및 머신 러닝 기반 **기능 서비스**&#x200B;를 사용하여 콘텐츠를 구성 요소와 특성으로 분류합니다. 모든 콘텐츠에 대해 구조화된 메타데이터 프로필을 만들어 해당 콘텐츠의 어떤 콘텐츠와 어떤 속성이 비즈니스 결과를 도출하는지 분석할 수 있습니다.

이 구조화된 메타데이터 프로필을 만드는 것 외에도 Content Analytics에서는 단일 식별자를 사용하여 에셋 및 경험을 식별하는 **ID 서비스**&#x200B;를 제공합니다. ID 서비스는 에셋(예: 에셋)의 크기가 조정되었는지, 잘렸는지 또는 다른 파일 형식으로 저장되었는지 여부를 파악합니다. 서비스는 해당 에셋의 모든 변형을 동일한 단일 식별자에 할당합니다. 따라서 ID 서비스를 사용하면 다양한 양식 및 배치를 기반으로 에셋의 성과를 집계할 수 있습니다.

## 값

Content Analytics는 증가하는 수준에서 가치를 제공합니다.

1. 콘텐츠 **사용량**: 콘텐츠 분석을 사용하면 어떤 에셋이 노출 횟수를 수신하는지, 어떤 에셋이 노출 횟수를 수신하는지 파악할 수 있습니다. 이러한 통찰력을 통해 웹 속성에서 에셋이 과소 사용되는지 또는 과다 사용되는지를 확인할 수 있습니다.
1. 컨텐츠 **참여**: 컨텐츠 분석에서는 특정 특성이 있는 자산에 대한 평균 클릭스루 비율과 같은 참여 인사이트를 제공할 수 있습니다. 이러한 통찰력을 통해 특정 유형의 경험이 여전히 효과적인지 여부를 확인할 수 있습니다.
1. 컨텐츠 **여정**: 또한 Experience Platform에서 사용할 수 있는 다른 모든 데이터와 결합하면 컨텐츠 여정에 대한 추가적인 통찰력을 얻을 수 있습니다. 예를 들어 특정 콘텐츠가 참여 위에서 전환으로 연결되는지 여부입니다. 또한 이러한 지식을 바탕으로 콘텐츠 유형에 대한 ROI를 판단할 수 있습니다.
1. 콘텐츠 **개인화**: 궁극적으로 콘텐츠 분석을 통해 통찰력을 기반으로 이러한 통찰력을 사용하여 콘텐츠에 돈을 지출하는 방법을 결정할 수 있습니다. 예를 들어 특정 유형의 콘텐츠를 특정 대상에게 보내야 합니까? 어떤 콘텐츠가 높은 개인화 기회를 제공합니까?

## 용어

Content Analytics에서는 다음 주요 용어를 사용합니다.

![Assets 및 경험](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **경험**: 경험은 해당 웹 페이지를 방문하는 초기 사용자가 사용한 URL을 사용하여 재현할 수 있는 웹 페이지의 모든 텍스트입니다. 각 경험은 고유한 식별자를 가져옵니다.
* **에셋**: 에셋은 이미지와 같은 개별적이고 고유한 콘텐츠입니다. 각 에셋은 고유 식별자도 가져옵니다.
* **특성**: 특성은 경험 또는 자산과 연결된 설명 메타데이터 요소입니다. 속성의 예로는 사진 스타일, 가독성, 설득 전략, 개체 색상, 배경색이 있습니다.

## 작동 방식

Content Analytics는 Experience Platform의 이벤트 데이터 세트에 수집된 웹 이미지 보기 데이터를 사용합니다. 이 데이터는 Experience Platform Edge Network(웹 SDK, 서버 API) 또는 Analytics 소스 커넥터 등 다양한 방법을 통해 수집할 수 있습니다.

![콘텐츠 분석 - 작동 방식](assets/how-it-works.png)


1. 기능 서비스의 검색 부분은 Content Analytics가 활성화된 이벤트 데이터 세트에 도착하는 데이터의 새로운 스냅샷에 따라 트리거됩니다.
1. 기능 감지 서비스는 해당 스냅샷에서 콘텐츠 분석과 관련된 데이터를 확인하고 이러한 웹 이미지 보기의 경험 및 에셋을 재방문합니다.
1. 재방문 시 Experience Platform 웹 SDK 및 Experience Platform Edge Network의 적절한 구성을 통해 특정 컨텐츠 분석 데이터가 수집됩니다. 그런 다음 전용 콘텐츠 분석 데이터 세트 및 관련 조회 데이터 세트로 데이터가 전송됩니다.
1. 피쳐화 어셈블러 서비스와 ID 서비스는 재방문한 데이터를 처리합니다.
1. 이러한 서비스의 결과(구성 요소, 속성 및 ID)는 Experience Platform에서 관련된 특정 콘텐츠 분석 데이터 세트를 업데이트하는 데 사용됩니다.
1. 그런 다음 행동 데이터 및 기타 조회 데이터 세트와 함께 컨텐츠 분석 데이터를 Customer Journey Analytics 구성(연결, 데이터 보기 및 Workspace)에서 사용할 수 있습니다. 이 구성은 콘텐츠에 대한 고유한 매크로 수준 인사이트를 제공하는 기반을 제공합니다.

>[!MORELIKETHIS]
>
>[콘텐츠 분석 사용(t.b.d.)](#value)
>[콘텐츠 분석 구성](config/configuration.md)
