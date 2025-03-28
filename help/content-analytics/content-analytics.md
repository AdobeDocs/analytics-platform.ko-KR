---
title: 콘텐츠 분석 개요
description: 콘텐츠 분석 개요
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 177def4edce1908a099627e96ed159b0154c3715
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 0%

---

# 콘텐츠 분석 개요

{{release-limited-testing}}

콘텐츠 분석은 마케터가 콘텐츠가 비즈니스가 정의한 주요 성능 지표에 미치는 영향을 이해할 수 있도록 도와줍니다. 동작 데이터 위에 Content Analytics은 컨텐츠가 사용되는 방식과 컨텐츠가 영향을 미치는 방식에 대한 데이터를 수집합니다. 예를 들어 고객이 특정 음색, 특정 색상 팔레트 또는 특정 테마에 더 잘 반응합니까? 이 정보는 특별히 설계된 보고 워크플로우 및 템플릿과 함께 Customer Journey Analytics의 고객 여정 데이터에 대해 보다 나은 분석을 수행하고 보다 심층적인 통찰력을 얻는 데 도움이 될 수 있습니다.

콘텐츠 분석은 AI 및 머신 러닝 기반 **기능 서비스**&#x200B;를 사용하여 콘텐츠를 구성 요소와 특성으로 분류합니다. 모든 콘텐츠에 대해 구조화된 메타데이터 프로필을 만들어 해당 콘텐츠의 어떤 콘텐츠와 어떤 속성이 비즈니스 결과를 도출하는지 분석할 수 있습니다.

이 구조화된 메타데이터 프로필을 만드는 것 외에도 Content Analytics에서는 단일 식별자를 사용하여 에셋 및 경험을 식별하는 **ID 서비스**&#x200B;를 제공합니다. ID 서비스는 정확히 동일한 에셋이 두 개 이상의 위치에 나타나는 경우를 인식할 수 있습니다. 이렇게 되면 이 에셋의 인스턴스가 동일한 에셋으로 처리되어 콘텐츠 사용 및 소비를 보다 전체적으로 확인할 수 있습니다.

## 값

Content Analytics은 증가하는 수준에서 가치를 제공합니다.

1. 콘텐츠 **사용량**: 콘텐츠 분석을 사용하면 어떤 에셋이 노출 횟수를 수신하는지, 어떤 에셋이 노출 횟수를 수신하는지 파악할 수 있습니다. 이러한 통찰력을 통해 웹 속성에서 에셋이 과소 사용되는지 또는 과다 사용되는지를 확인할 수 있습니다.
1. 컨텐츠 **참여**: 컨텐츠 분석에서는 특정 특성이 있는 자산에 대한 평균 클릭스루 비율과 같은 참여 인사이트를 제공할 수 있습니다. 이러한 통찰력을 통해 특정 유형의 경험이 여전히 효과적인지 여부를 확인할 수 있습니다.
1. 컨텐츠 **여정**: 또한 Experience Platform에서 사용할 수 있는 다른 모든 데이터와 결합하면 컨텐츠 여정에 대한 추가적인 통찰력을 얻을 수 있습니다. 예를 들어 특정 콘텐츠가 참여 위에서 전환으로 연결되는지 여부입니다. 또한 이러한 지식을 바탕으로 콘텐츠 유형에 대한 ROI를 판단할 수 있습니다.
1. 콘텐츠 **개인화**: 궁극적으로 콘텐츠 분석을 통해 통찰력을 기반으로 이러한 통찰력을 사용하여 콘텐츠에 돈을 지출하는 방법을 결정할 수 있습니다. 예를 들어 특정 유형의 콘텐츠를 특정 대상에게 보내야 합니까? 어떤 콘텐츠가 높은 개인화 기회를 제공합니까?

## 용어

Content Analytics에서는 다음 주요 용어를 사용합니다.

![Assets 및 경험](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **경험**: 경험은 웹 페이지를 방문한 초기 사용자가 사용하는 URL을 사용하여 재현할 수 있는 웹 페이지의 모든 텍스트입니다. 각 경험은 고유한 식별자를 가져옵니다. 페이지를 변경하면 페이지의 HTML이 변경되어 새로운 경험이 생성됩니다.
* **에셋**: 에셋은 이미지와 같은 개별적이고 고유한 콘텐츠입니다. 각 에셋은 고유 식별자 및 가시 범위 ID도 가져옵니다. 가시 범위 ID는 시각적으로 동일한 에셋과 공유되는 식별자입니다. 가시 범위 ID는 서로 다른 에셋 URL 및 이에 대한 서로 다른 에셋 ID를 가질 수 있지만 지각 적으로는 동일한 에셋을 중복 제거하는 데 도움이 됩니다.
* **특성**: 특성은 경험 또는 자산과 연결된 설명 메타데이터 요소입니다. 속성의 예로는 사진 스타일, 가독성, 설득 전략, 개체 색상, 배경색이 있습니다.

## 작동 방식

Content Analytics은 Experience Platform의 이벤트 데이터 세트에 수집된 웹 이미지 보기 데이터를 사용합니다. 이 데이터는 Experience Platform Edge Network(웹 SDK, 서버 API) 또는 Analytics 소스 커넥터 등 다양한 방법을 통해 수집할 수 있습니다.

![콘텐츠 분석 - 작동 방식](assets/aca-overview.gif)


1. 사용자가 Content Analytics에 대해 구성된 [사이트](config/configuration.md)를 방문하면 Experience Platform Web SDK은 노출 횟수 및 콘텐츠와의 상호 작용을 기록합니다.
1. ID 및 기능 서비스는 이러한 상호 작용을 처리합니다. 이 프로세스는 상호 작용을 정의하는 구성된 URL의 공개 버전을 다시 방문하는 검색 서비스로 구성됩니다. 이렇게 검색된 모든 URL에 대해 ID 서비스는 경험 및 에셋을 고유하게 식별합니다. 또한 기능 서비스는 AI/ML 서비스를 적용하여 경험과 에셋 메타데이터 및 속성을 검색합니다.
1. 이러한 서비스의 결과([구성 요소, 특성 및 ID](/help/content-analytics/report/components.md))는 Experience Platform에서 관련된 특정 콘텐츠 분석 데이터 세트를 업데이트하는 데 사용됩니다.
1. 컨텐츠 분석 데이터는 동작 데이터 및 기타 조회 데이터와 함께 Customer Journey Analytics 설정([연결](/help/connections/overview.md), [데이터 보기](/help/data-views/data-views.md) 및 [Workspace](/help/analysis-workspace/home.md))에서 사용할 수 있습니다. 해당 설정은 콘텐츠에 대한 고유한 매크로 수준 인사이트를 제공하는 기반을 제공합니다. <br/>[Content Analytics 템플릿](/help/content-analytics/report/report.md#template)을 사용하여 Content Analytics 보고서 및 분석을 바로 시작할 수 있습니다.

>[!NOTE]
>
>Content Analytics은 부정확하거나 오해의 소지가 있는 결과를 생성할 수 있는 AI/ML 서비스를 활용합니다. 따라서 AI/ML에서 생성된 출력을 검토하고 유효성을 검사하려면 판단을 사용하십시오.
>
>기본 인터페이스의 ![InfoOutline](/help/assets/icons/InfoOutline.svg)에서 제공되는 **[!UICONTROL 피드백]** 탭을 사용하여 AI/ML 생성 출력에 대한 피드백을 제공할 수 있습니다.
>

>[!NOTE]
>
>Privacy 및 Security Shield 추가 기능에 라이선스를 부여한 경우 Content Analytics의 적용을 받는 (에서 생성된 모든 데이터) 경험 및 자산은 DULE 레이블 지정 또는 고객 관리 키의 적용을 받지 않습니다.
>


>[!MORELIKETHIS]
>
>[콘텐츠 분석 보고](report/report.md)
>[콘텐츠 분석 구성](config/configuration.md)
>
