---
title: 크로스 채널 여정 분석
description: 고객 여정 전반에 걸친 고객 상호 작용에서 통찰력을 분석하고 추출합니다.
source-git-commit: a6c6620a4f4118755509e534d7d6a12bf08b4b67
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 6%

---


# 크로스 채널 여정 분석

다양한 웹, 모바일 및 오프라인 속성의 데이터를 통합하여 다양한 채널에서 고객 행동을 통합된 방식으로 파악할 수 있습니다. 예를 들어 이 통합 보기를 사용하여 데스크탑 및 모바일에서 고객 상호 작용을 분석하여 고객 행동을 파악하고 통찰력을 추출하여 디지털 고객 경험을 최적화할 수 있습니다. 또한 지원 상호 작용 및 매장 내 구매와 같은 디지털 및 오프라인 채널을 포함하여 채널 전반에서 고객 상호 작용을 분석하여 고객 여정을 더 잘 이해하고 최적화할 수 있습니다.

## 아키텍처

![크로스 채널 아키텍처](assets/cross-channel-architecture.svg)

## 구현 절차

1. [수집할 ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ko-KR) 데이터에 대한 스키마를 만듭니다.
1. [수집할 ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) 데이터에 대한 데이터 세트를 만듭니다.
1. [Experience Platform에 데이터 수집](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html).
1. 데이터 세트에서 공통 네임스페이스 ID를 사용하거나 [크로스 채널 분석](/help/connections/cca/overview.md)을 사용하여 사용자를 서로 연결합니다. Customer Journey Analytics은 현재 결합에 Experience Platform 프로필 또는 ID 서비스를 사용하지 않습니다.
1. 모든 사용자 지정 데이터 준비를 수행하여 Customer Journey Analytics에 수집할 시계열 데이터 세트에 대한 공통 키를 확인합니다.
1. 이벤트 데이터의 필드에 조인할 수 있는 기본 ID를 조회 데이터에 제공합니다. 라이선스에서 행으로 카운트됩니다.
1. 프로필 데이터의 기본 ID를 이벤트 데이터의 기본 ID와 동일하게 설정합니다.
1. Experience Platform에서 Customer Journey Analytics으로 데이터를 수집하도록 데이터 연결을 구성합니다.
1. [연결에 ](/help/data-views/create-dataview.md) 표시된 데이터를 만들어 보기에 포함할 특정 차원 및 지표를 선택합니다. 속성 및 할당 설정도 데이터 보기에서 구성됩니다. 이러한 설정은 보고서 시간에 계산됩니다.
1. Analysis Workspace 내에서 대시보드 및 보고서를 구성하는 프로젝트를 만듭니다.

## 고려 사항

이 워크플로우를 설정할 때는 다음 사항을 고려해야 합니다.

* 채널 간 데이터를 분석하려면 모든 레코드에 동일한 ID 네임스페이스가 필요합니다.
* 서로 다른 데이터 세트를 통합하는 결합 프로세스에는 데이터 세트 간에 공통 기본 개인/엔티티 키가 필요합니다.
* 보조 키 기반 조합은 현재 지원되지 않습니다.
* 필드 기반 ID 결합 프로세스를 사용하면 인증 ID와 같은 후속 임시 ID 레코드를 기반으로 행에서 ID를 재입력할 수 있습니다. 이렇게 하면 장치 또는 쿠키 수준이 아닌 개인 수준에서 분석을 위해 서로 다른 레코드를 단일 ID로 해결할 수 있습니다.
* 동일한 XDM 필드의 개체 및 속성은 Customer Journey Analytics의 한 차원으로 병합됩니다. 여러 데이터 세트의 여러 속성을 동일한 Customer Journey Analytics 차원으로 병합하려면 데이터 세트가 동일한 XDM 필드 또는 스키마를 참조해야 합니다.
