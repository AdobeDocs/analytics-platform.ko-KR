---
title: Customer Journey Analytics의 제품 분석
description: Customer Journey Analytics 내에서 제품 분석을 효과적으로 수행하기 위해 사용할 수 있는 기능에 대해 알아봅니다.
exl-id: b185a2ed-18c8-4fb3-8c69-693d5fee0e67
source-git-commit: 40e6fbd49a92690253855e314e9999da28a7d2f6
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 1%

---

# Customer Journey Analytics의 제품 분석

제품 분석은 사용자가 여정의 모든 단계에서 제품과 상호 작용하는 방법을 이해하는 프로세스입니다. 여기에는 사용자 행동, 제품 성과 및 성장 기회에 대한 통찰력을 발견하기 위한 데이터 분석이 포함됩니다. 효과적인 제품 분석을 통해 팀은 정보에 입각한 결정을 내려 사용자 경험을 개선하고 참여를 유도하며 비즈니스 목표를 달성할 수 있습니다.

Customer Journey Analytics은 다음과 같은 기능을 통해 제품 경험을 분석하고 최적화할 수 있는 도구를 팀에 제공합니다.

* **규모에 맞게 제품 데이터 관리**: 비즈니스 요구 사항에 맞게 제품 데이터를 손쉽게 수집, 변환 및 관리하여 신뢰할 수 있는 통찰력을 보장합니다.
* **획득 및 활성화 측정**: 새 사용자가 제품을 발견하고 첫 번째 가치 창출 이벤트에 참여하는 방법을 추적합니다.
* **참여 및 채택 측정**: 사용자가 제품 단계를 통해 어떻게 진행되는지 이해하고, 마찰 지점을 식별하고, 주요 기능의 채택을 추적합니다.
* **유지 및 이탈 측정**: 시간 경과에 따른 사용자 유지를 분석하고 이탈의 지표를 식별하며 이탈을 줄이고 충성도를 높이기 위한 전략을 개발합니다.
* **작업 제품 인사이트**: 데이터 기반 인사이트를 실행 가능한 전략으로 전환하여 사용자 경험을 개선하고 지속적인 제품 성장을 촉진합니다.
* **조직과 통찰력 공유**: 팀 간에 주요 결과를 전달하여 노력을 조정하고, 공동 작업을 촉진하고, 모든 사람이 공유된 제품 및 비즈니스 목표를 향해 나아가도록 합니다.

Customer Journey Analytics은 이러한 기능을 활용하여 제품의 잠재력을 최대한 활용하고 원활한 데이터 기반 접근 방식을 통해 사용자 및 비즈니스 성공을 이끌어낼 수 있도록 지원합니다.

## 규모에 맞게 제품 데이터 관리

정확한 제품 데이터는 효과적인 제품 분석의 초석입니다. 데이터 수집은 제품 데이터를 계측하고 수집하는 프로세스를 의미하며, 데이터 관리에는 분석 요구 사항을 충족하기 위해 이 데이터를 변환하고 유지 관리하는 프로세스가 포함됩니다.

Adobe Experience Platform 및 Customer Journey Analytics의 다음 기능을 통해 제품 데이터를 규모에 맞게 수집 및 관리할 수 있습니다.

* Adobe Experience Platform
   * [데이터 &#x200B; 세트](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)
   * [데이터 &#x200B; 준비](https://experienceleague.adobe.com/ko/docs/experience-platform/data-prep/home)
   * [데이터 Distiller{&#x200B;1}](https://experienceleague.adobe.com/en/docs/experience-platform/query/data-distiller/overview)
* Customer Journey Analytics
   * [연결 &#x200B;](/help/connections/overview.md)
   * [파생 필드](/help/data-views/derived-fields/derived-fields.md)을(를) 포함한 [데이터 &#x200B; 보기](/help/data-views/data-views.md)
   * [세그먼트 &#x200B;](/help/components/filters/filters-overview.md)
   * [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md)
   * [안내식 분석&#x200B;: 타임라인 &#x200B;](/help/guided-analysis/types/timeline.md)

## 획득 및 활성화 측정

제품 성장은 새로운 사용자를 유치하고, 전환 경로를 공개하며, 여정에서 발생하는 마찰을 제거하는 실행 가능한 깔때기형 통찰력에 달려 있습니다.

* 고객 확보 기능은 도착 방법, 가장 효과적이거나 가장 낮은 노력 등 제품에 들어오는 신규 사용자를 추적합니다.
* 활성화 는 특정 목표에 따라 정의된 첫 번째 값 이벤트에 참여하는 신규 사용자를 모니터링합니다.

![활성 증가](/help/guided-analysis/assets/active.png)

![참여 분석](/help/guided-analysis/assets/feature-matrix.png)

Customer Journey Analytics의 다음 기능을 사용하면 획득과 활성화를 모두 효과적으로 측정할 수 있습니다.

* [가이드 분석&#x200B;: 적극적인 성장](/help/guided-analysis/types/active-growth.md)
* [가이드 분석: 순 성장](/help/guided-analysis/types/net-growth.md)
* [안내식 분석: 트렌드](/help/guided-analysis//types/trends.md)
* [속성 패널&#x200B;](/help/analysis-workspace/c-panels/attribution.md)
* 마케팅 채널 차원을 포함하는 [자유 형식 테이블](/help/analysis-workspace/c-panels/freeform-panel.md)([파생 필드](/help/data-views/derived-fields/derived-fields.md)을(를) 사용하여 만들기)

## 참여 및 채택 측정

새 사용자를 획득하면 제품 단계의 맨 위가 확장됩니다. 참여는 이러한 사용자를 단계를 더 아래로 안내하고 성공에 대한 장애물을 제거하는 데 중점을 둡니다. 그들의 성공은 직접적으로 귀사의 비즈니스 성공을 이끈다.

Customer Journey Analytics의 다음 기능을 통해 제품 참여 및 채택을 추적할 수 있습니다.

* [가이드 분석: 참여](/help/guided-analysis/types/engagement.md)
* [안내식 분석: 트렌드](/help/guided-analysis/types/trends.md)
* [안내식 분석: 빈도](/help/guided-analysis/types/frequency.md)
* [안내식 분석: 단계](/help/guided-analysis/types/funnel.md)
* [안내식 분석: 전환 트렌드](/help/guided-analysis/types/conversion-trends.md)
* [가이드 분석: 릴리스 영향](/help/guided-analysis/types/release-impact.md)
* [안내식 분석: 첫 번째 사용 &#x200B; 영향](/help/guided-analysis/types/first-use-impact.md)
* [안내식 분석: 타임라인](/help/guided-analysis/types/timeline.md)
* [자유 양식 표&#x200B;.](/help/analysis-workspace/c-panels/freeform-panel.md)
* [플로우](/help/analysis-workspace/visualizations/c-flow/flow.md)

## 유지 및 이탈 측정

유지는 초기 획득 및 활성화 이후 제품과 계속 소통하는 사용자 수를 측정합니다. 고성능 제품은 지속적인 사용과 가장 밀접한 상관 관계가 있는 기능과의 상호 작용을 극대화하여 안정적이고 충실한 사용자 기반을 유지합니다. 보존된 사용자는 시간이 지남에 따라 제품을 반환하고 제품과 상호 작용하지만, 이탈된 사용자는 그렇지 않습니다. 제품 팀은 보존을 추적하여 지속적인 참여를 유도하는 기능을 정확하게 파악하고, 이탈된 사용자를 보존된 사용자 비헤이비어로 전환하는 중재를 설계합니다.

![유지 분석](/help/guided-analysis/assets/retention.png)

Customer Journey Analytics의 다음 기능을 사용하여 유지 및 이탈을 효과적으로 추적할 수 있습니다.

* [안내식 분석: 유지{1&#x200B;}](/help/guided-analysis/types/retention.md)
* [가이드 분석: 적극적인 성장](/help/guided-analysis/types/active-growth.md)
* [가이드 분석: 순 성장](/help/guided-analysis/types/net-growth.md)
* [집단 &#x200B; 테이블](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)

## 실행 가능한 제품 인사이트

인사이트는 작업을 추진할 때만 가치를 제공합니다. 분석 결과를 사용자 경험을 개선하고 장기적인 제품 성장을 지원하는 작업으로 변환합니다.

Experience Cloud 내의 다음 기능을 사용하면 통찰력에 효과적으로 대처할 수 있습니다.

* Customer Journey Analytics 활성화를 위해 [대상 만들기 및 게시{&#x200B;1}](/help/components/audiences/publish.md)
* Experience Cloud 제품을 통해 대상자 활성화:
   * AJO 및 Adobe Target에서 [실험을 실행](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/content-management/content-experiment/get-started-experiment)하고 [실험 패널](/help/analysis-workspace/c-panels/experimentation.md)을 사용하여 Customer Journey Analytics의 변형의 영향을 측정합니다.
   * AJO의 사용자에게 [인앱 참여 제공](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/in-app/get-started-in-app)
* Adobe Real-time CDP를 사용하여 외부 대상에 대해 [대상자 활성화](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activation-overview)&#x200B;

## 조직에 인사이트 &#x200B; 공유

팀 간의 주요 결과를 전달하여 노력을 조정하고, 협업을 촉진하고, 모든 사람이 공유된 제품 및 비즈니스 목표를 향해 작동하도록 합니다.

![Workspace의 가이드 분석](assets/guided-analysis-workspace.png)

Customer Journey Analytics의 다음 기능을 통해 통찰력을 효과적으로 공유할 수 있습니다.

* 특정 비즈니스 질문에 맞는 가이드 분석 보기를 [공유](/help/analysis-workspace/curate-share/share-projects.md)하여 소비자가 다음 질문을 셀프서비스할 수 있도록 합니다.
* 가이드 분석, 패널 및 시각화를 [Analysis Workspace](/help/analysis-workspace/home.md)의 포괄적인 대시보드에 결합합니다.
* 이동 중인 경영진 및 기타 소비자를 위한 주요 제품 인사이트가 포함된 [모바일 스코어카드](/help/mobile-app/home.md)를 만드십시오
