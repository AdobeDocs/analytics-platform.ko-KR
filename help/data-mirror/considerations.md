---
title: Data Mirror 고려 사항
description: Data Warehouse 기본 솔루션과 Customer Journey Analytics 간에 데이터를 동기화하려는 경우 고려해야 할 추가 사항을 이해합니다.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
autotag-review: '2026-05-19T06:55:09.938Z'
TQID: 'https://experienceleague.adobe.com/uZjXZUKUMeXLxxpTRrkCZrPsGhxseSxOtJ9X0ZjG5wU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: df1ab1af7757ef012b4c233e6206ee6c6cde6686
workflow-type: tm+mt
source-wordcount: 889
ht-degree: 1%

---

# Experience Platform Data Mirror 고려 사항

이 문서에서는 Data Mirror 데이터 세트를 설정할 때 고려해야 하는 요소에 대해 설명합니다.

## 소스 테이블에 새 열 추가

CDC를 사용할 수 있는 데이터 미러링된 데이터 세트의 소스 테이블에 새 열이 추가되면 해당 변경 사항이 기존의 모든 행에 대한 업데이트를 트리거할 수 있습니다. 이러한 업데이트는 다음과 같은 CDC를 통해 변경 사항으로 처리됩니다.

* 진행 중인 관점에서 전체 테이블 다시 작성처럼 작동할 수 있습니다.
* 는 수집 볼륨을 크게 증가시켜 업데이트가 수집 권한을 초과할 수 있습니다.

소스 테이블의 열에 권장되는 전략은 다음과 같습니다.

* 모든 관련 열이 초기에 정의되었는지 확인합니다.
* 처음에 필요하다고 생각할 수 있는 모든 열을 매핑합니다.

새 열을 추가하려면 소급 채우기 필요 여부에 따라 다음 두 가지 옵션이 있습니다.

* 소급 채우기:

   * 현재 데이터 세트를 제거합니다.
   * 업데이트된 열로 커넥터를 다시 구성합니다.

  이렇게 하면 데이터가 보다 효율적이고 시기 적절하게 채워집니다.

* 소급 채우기 없음:

   * 소스 테이블에 열을 추가합니다.
   * 대상 데이터 세트 스키마에 열을 추가합니다.
   * 소스 테이블의 새 필드(열)를 대상 데이터 세트에 포함하도록 매핑을 업데이트합니다.

이 전략은

* 나중에 비용이 많이 드는 스키마 변경(열을 추가할 때 대량 업데이트)을 방지합니다.
* 열을 나중에 추가하거나 수정하는 경우보다 변경 볼륨을 예측 가능하게 유지합니다.
* Data Warehouse가 새 열을 모든 행에 대한 업데이트로 해석할 수 있으므로 외부 데이터베이스 측의 잠재적 계산 비용을 제한하는 데 도움이 됩니다.


## Privacy Service

개인 정보 보호 요청은 데이터 구성 방식에 무관하므로 오늘날 비관계형 스키마에 대해 개인 정보 보호 요청이 처리되는 것과 동일한 방식으로 수행해야 합니다.

외부 관계형 스키마에서 미러된 데이터는 Adobe 생태계의 일부가 되며 Customer Journey Analytics 대상 게시를 통해서와 같이 해당 생태계 전체에서 공유할 수 있습니다. 개인 정보 보호 요청을 제출하면 Adobe 에코시스템 전체에서 ID 및 관련 데이터가 제대로 처리됩니다.

따라서 개인 정보 보호 요청은 미러링된 데이터 세트로 제한되지 않고 외부 데이터베이스의 소스 데이터에 대한 업데이트도 포함되어야 합니다.

## 위생 행동

위생 서비스는 *기본 ID*&#x200B;에서 작동하지만 미러링된 외부 데이터베이스의 테이블에는 기본 ID가 아닌 *기본 키*&#x200B;가 있습니다.

기본 ID와 기본 키 간의 차이로 인해 이러한 관계 테이블에 대해 직접 위생 삭제를 실행할 수 없다는 결과가 발생합니다. 따라서 다음을 수행해야 합니다.

* Data Warehouse 솔루션 내의 자체 소스 테이블에서 데이터를 삭제하고 삭제 작업이 CDC(또는 수동 변경 열)를 통과하는지 확인합니다.
* ID 정보가 있는 다운스트림 XDM 기반 데이터 세트(예: Customer Journey Analytics 보기, Real-Time Customer Data Platform 데이터 세트, Adobe Journey Optimizer 특정 데이터 세트 등)에 대해 Adobe에 위생 및 개인 정보 보호 요청을 제출합니다.

기본 ID와 기본 키의 차이점은 공유 권한 모델을 도입합니다.

* Adobe은 ID가 있는 곳에서 위생을 처리합니다.
* 고객은 소스 데이터베이스의 자체 위생 프로세스를 Adobe에 제출된 위생 요청에 맞춰 조정할 책임이 있습니다.

## 거버넌스 차이점

XDM [스키마](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/schema/composition) 및 [필드 그룹](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/schema/composition#field-group)과(와) 같은 기본 개념에서 필드 그룹 내의 정의된 [필드](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/schema/composition#field)은(는) 필드 그룹이 사용되는 모든 데이터 세트에서 해당 레이블을 전파합니다. 예를 들어 필드 그룹 `identities`의 전자 메일 필드 `emailID`은(는) 필드 그룹 `identities`이(가) 사용되는 모든 데이터 세트에서 동일하게 레이블이 지정됩니다.

관계형 스키마에서 열 이름은 독립적입니다. `customers` 테이블의 `email` 열은 `prospects` 테이블의 `email` 열과 독립적이며 서로 다릅니다. 이 동작은 레이블(예: DULE 사용 레이블, 정책)이 미러된 데이터 세트의 필드에 개별적으로 적용되어야 함을 의미합니다. 위의 예제를 기반으로 `customers` 데이터 세트의 `email` 필드와 `prospects` 데이터 세트의 `email` 필드 모두에 레이블을 적용해야 합니다.

거버넌스 차이는 다음과 같은 영향을 줍니다.

* 고객은 보다 수동적인 거버넌스 및 구성을 사용할 수 있습니다.
* 명시적인 지침이 필요할 수 있으므로 필드 그룹을 통한 일회성 레이블 지정이 적절한 거버넌스에 충분하다고 가정하지 마십시오.

## 결합

관계형 스키마에는 결합과 관련하여 다음과 같은 고려 사항이 있습니다.

* 그래프 기반 결합은 부분적으로 지원됩니다. 그래프에 기여하는 프로필/관계에 대해 관계형 스키마를 활성화할 수 없습니다.
* 필드 기반 결합은 완전히 지원됩니다.


## 시스템 키 및 필드

다음 고려 사항은 시스템 키 및 필드에 적용됩니다.

* 기본 키, 버전 설명자 및 타임스탬프 설명자는 관계형 XDM 스키마의 루트 레벨 필드여야 합니다. 이 요구 사항을 지원하려면 수집 중에 [필드 매핑](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema)을(를) 사용하십시오.
* [매핑 단계](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema) 동안 적절한 소스 필드를 생략할 수 있습니다.

## 미러링된 데이터의 배치 크기

연결의 일부로 구성된 모든 미러된 데이터 세트의 경우, 미러된 데이터 세트에 대한 데이터를 수집하기 위한 각 배치가 100GB를 초과하지 않도록 해야 합니다. 자세한 내용은 [일괄 처리 수집을 위한 보호](https://experienceleague.adobe.com/ko/docs/experience-platform/ingestion/guardrails#guardrails-for-batch-ingestion){target="_blank"}를 참조하십시오.
