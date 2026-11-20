---
title: Adobe Analytics와의 비교
description: Customer Journey Analytics와 Adobe Analytics의 비교 개요입니다.
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
autotag-review: '2026-05-19T09:13:47.721Z'
TQID: 'https://experienceleague.adobe.com/MU9ywSyInHtsdzqvxO3yxTSY5bcDvdhnTUkhAgDHmZ4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1f480cda20e0b2d54dd42b909bfa8bf8a2bc0c95
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 52%
---
# Adobe Analytics와의 비교

이 설명서 섹션에서는 Adobe Customer Journey Analytics와 Adobe Analytics의 차이점을 비교하고 이해하는 방법을 설명합니다.

두 솔루션의 기본적인 차이점은 보고서 및 분석을 작성할 때 고려할 수 있는 데이터의 폭입니다.

Customer Journey Analytics에서는 *모든* 데이터 소스가 보고 및 분석에 사용하는 데이터의 일부가 될 수 있습니다. Adobe Analytics은 주로 웹 사이트 및 모바일 앱에서 수집된 온라인 데이터를 대상으로 합니다. Adobe Analytics은 다른 소스에서 데이터를 가져오는 기능을 제공하지만, 이 기능의 주요 목적은 이전에 언급된 온라인 데이터에 대한 추가 컨텍스트를 제공하는 것입니다.

## 데이터 수집

Customer Journey Analytics는 Adobe Experience Platform 데이터 세트에 저장된 데이터를 사용합니다. Experience Platform에서는 몇 가지 옵션을 사용하여 이러한 데이터 세트의 데이터를 수집할 수 있습니다. 이러한 옵션은 [데이터 수집 개요](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-data-ingestion/data-ingestion)에 자세히 설명되어 있습니다.

Adobe Analytics는 최종적으로 솔루션 자체 내에서 데이터를 수집합니다. 이러한 데이터를 수집할 수 있는 몇 가지 옵션이 있습니다. 자세한 내용은 [Adobe Analytics 구현 안내서](https://experienceleague.adobe.com/ko/docs/analytics/implementation/home)를 참조하세요.

Customer Journey Analytics에서 [Analytics 소스 커넥터](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)를 통해 Adobe Analytics 보고서 세트 데이터를 사용할 수 있습니다. 이 커넥터는 Adobe Analytics에서 수집된 데이터를 Experience Platform으로 수집합니다. 그런 다음 Customer Journey Analytics에서 이 데이터 세트에 대한 연결을 생성할 수 있습니다. 자세한 내용은 [Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 사용](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja)을 참조하십시오.

Adobe Analytics 보고서 세트의 데이터는 Customer Journey Analytics 연결을 구성하는 Adobe Experience Platform 데이터 세트에 저장된 데이터와 독립적입니다. 따라서 Adobe에서는 두 플랫폼 모두 동일한 값을 반영할 것으로 예상하는 대신 각 플랫폼의 데이터를 개별적으로 평가할 것을 권장합니다.

## 데이터 처리

데이터에 대해 보고하기 전에 데이터가 보고를 위해 사용될 수 있도록 해당 데이터를 처리해야 하는 경우가 많습니다. 데이터 처리는 수집 시간과 보고 시간에 발생할 수 있습니다.

일반적으로 Customer Journey Analytics은 보고서 시간에 Experience Platform 데이터 세트에서 수집 및 저장된 데이터로 작업하도록 설계되었습니다. Customer Journey Analytics는 강력한 보고 시 처리 기능을 제공하여 보고 및 분석할 수 있도록 데이터를 준비합니다. [파생 필드](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-dataviews/derived-fields) 및 [구성 요소 설정](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview)을(를) 수정하고 이전 데이터에 소급하여 적용할 수 있습니다. Experience Platform에서 수집되기 전에 데이터를 매핑, 변환 및 유효성 검사를 수행해야 하는 경우 Experience Platform의 [데이터 준비](https://experienceleague.adobe.com/ko/docs/experience-platform/data-prep/home) 기능을 사용할 수 있습니다.

Adobe Analytics에서 데이터 처리는 대부분 데이터가 수집되면 발생합니다. 마케팅 채널 규칙, 처리 규칙, eVar 지속성 및 기타 사후 처리 로직은 현재 적용되며 보고서 세트에 영구적으로 적용됩니다. 이러한 구성에 대한 변경 사항은 해당 시점부터 새로 들어오는 데이터에만 영향을 줍니다.

자세한 내용은 [Adobe Analytics 및 Customer Journey Analytics 보고 기능 간의 데이터 처리 비교](data-processing-comparisons.md) 및 [처리 규칙, VISTA 및 분류 대 데이터 준비](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep)을 참조하십시오.


## 용어

Customer Journey Analytics는 기본 XDM(경험 데이터 모델) 기반의 스키마에 갖춰진 유연성을 통해 차원과 지표를 유연하게 정의합니다. 예를 들어 Adobe Analytics에서 방문자, 방문 횟수 및 히트 수를 사용하고 Customer Journey Analytics에서 사람, 세션 및 이벤트를 사용하는 경우(필요에 따라 이름을 변경할 수 있음)

용어 차이에 대한 자세한 내용은 [Analytics 소스 커넥터를 통해 전달되는 Analytics 데이터의 용어 비교](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology)를 참조하십시오.


## 가상 보고 환경 및 샌드박스

Adobe Analytics에는 수집된 데이터를 세그먼트화하고 세그먼트화된 데이터에 대한 액세스를 제어할 수 있는 가상 보고서 세트라는 개념이 있습니다.

Customer Journey Analytics에는 데이터 보기라는 유사한 개념이 있습니다. 데이터 보기는 연결에서 데이터를 해석하는 방법을 결정할 수 있는 컨테이너입니다. 보고 및 분석을 준비할 때 차원 및 지표를 지정하고 구성할 수 있는 뛰어난 유연성을 지원합니다.

Experience Platform은 주어진 환경에 대한 데이터 및 애플리케이션을 저장하는 컨테이너로 작동하는 샌드박스를 제공합니다. 샌드박스 기능은 Adobe Analytics 가상 보고서 세트 또는 Customer Journey Analytics 데이터 보기와 관련이 없습니다. Adobe Analytics 자체에는 Experience Platform 샌드박스에 대한 종속성 또는 관계가 없습니다. Customer Journey Analytics는 Experience Platform 샌드박스를 지원하지만, 몇 가지 중요한 고려 사항이 있습니다.

자세한 내용은 [가상 보고서 세트, 데이터 보기, Adobe Experience Platform 샌드박스 및 Analytics 소스 커넥터](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc)를 참조하십시오.


## ID

Customer Journey Analytics는 데이터가 포함된 데이터 세트가 준수하는 스키마의 일부로 정의되는 ID를 지원합니다. 따라서, ID는 Experience Platform의 기본 개념으로, 이는 [연결](../../connections/overview.md)을 설정(각 데이터 세트에 대한 개인 ID 정의)하고 크로스 채널 분석 시 [결합](../../stitching/overview.md)을 적용할 때 Customer Journey Analytics에서 사용합니다. Experience Platform SDK 및 API에서 사용하는 중요한 ID는 ECID입니다.

Adobe Analytics는 Adobe Analytics ID(AAID)와 같은 보다 명확한 ID 필드 세트를 사용합니다. Analytics 소스 커넥터를 사용하는 경우 이러한 Adobe Analytics ID 필드에 특별한 처리가 부여됩니다. 자세한 내용은 [AAID, ECID, AACUSTOMID 및 Analytics 소스 커넥터](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc)를 참조하십시오.


## 높은 카디널리티 차원

Customer Journey Analytics은 전체 차원 값을 저장하며 차원이 포함할 수 있는 고유 값 수에는 제한이 없습니다. 반면 Adobe Analytics에서는 보고 및 저장을 최적화하기 위해 32비트 해시를 사용하여 차원 값을 매핑합니다. 이 동작을 수행하면 보고에서 [해시 충돌](https://experienceleague.adobe.com/en/docs/analytics/implementation/validate/hash-collisions)이 발생할 수 있습니다. Adobe Analytics은 고유 제한 임계값에 도달하면 값을 [낮은 트래픽](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic) 라인 항목에 버킷팅합니다. 이러한 차원을 사용하는 세그먼트는 Adobe Analytics 보고서와 Customer Journey Analytics 보고서 간의 불일치를 보여줄 수 있습니다.

## 지원되는 기능

Adobe Analytics 기능에 대한 개요와 Customer Journey Analytics에서 지원하는 방법은 [Customer Journey Analytics 기능 지원](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa)에서 확인할 수 있습니다.
