---
title: Content Analytics 데이터 수집
description: Content Analytics에서 데이터를 수집하는 방법에 대한 개요
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: 981cd0c01d775acbd71cada7efed4911b4bcb157
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 1%

---

# Content Analytics 데이터 수집

{{release-limited-testing}}

이 문서에서는 Content Analytics에서 데이터를 수집하는 방법에 대해 자세히 설명합니다


## 정의

이 문서의 컨텍스트에서는 다음 정의가 사용됩니다.

* **경험**: 경험이 전체 웹 페이지의 텍스트 콘텐츠로 정의됩니다. 데이터 수집의 경우 Content Analytics은 페이지 URL을 기반으로 하는 경험 ID를 기록합니다. 나중에 페이지의 텍스트는 검색 서비스를 통해 캡처됩니다.
* **경험 ID**: 관련 URL(기본 URL과 페이지의 콘텐츠를 유도하는 모든 매개 변수)과 [경험 버전](manual.md#versioning)의 고유한 조합입니다.
   * 지정된 전체 URL과 관련된 매개 변수를 [configuration](configuration.md)의 일부로 지정합니다.
   * 사용할 [버전 식별자](manual.md#versioning)을(를) 정의했으므로 경험에 대한 변경 내용을 올바르게 수집합니다.
* **자산**: 이미지입니다. Content Analytics은 에셋 URL을 기록합니다.
* **자산 ID**: 자산의 URL입니다.
* **관련 URL**: 기본 URL과 페이지의 콘텐츠를 유도하는 모든 매개 변수.


## 기능

Content Analytics 라이브러리는 다음과 같은 경우에 데이터를 수집합니다.

* Content Analytics은 페이지에 로드되는 태그 라이브러리에 포함됩니다.
* 페이지 URL은 포함된 Tags 라이브러리의 일부인 [Content Analytics 확장](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}에 구성되어 있습니다.


## Content Analytics 이벤트

Content Analytics 이벤트는 다음과 같이 구성됩니다.

* 표준 필드
   * 타임스탬프
   * ID
* 경험 보기(있는 경우 및 구성된 경우)
* 경험 클릭수(있는 경우 및 구성된 경우)
* 자산 보기(있는 경우 및 구성된 경우)
* 자산 클릭 수(있는 경우 및 구성된 경우)


Content Analytics 이벤트는 다음과 같은 순서로 수집됩니다.

1. [기록된 보기 또는 클릭](#recorded-view-or-click)입니다.
1. [정기적 또는 특정(행동) 이벤트](#regular-or-specific-behaviorial-event)입니다.

Content Analytics은 보기 또는 클릭 바로 다음에 발생하는 이벤트를 수집하지 않고 보기 또는 클릭을 별도로 수집하는 대신 해당 시퀀스를 반영하도록 데이터를 수집합니다. 이러한 컨텐츠 분석 데이터 수집 방법은 수집된 데이터의 양도 줄입니다.

### 기록된 보기 또는 클릭

다음과 같은 경우 에셋 보기가 기록됩니다.

* Content Analytics 확장 구성에 따라 자산이 제외되지 않았습니다.
* 자산이 조회수 75%입니다.
* 해당 자산은 이 페이지에 대해 이미 기록되지 않았습니다.

다음과 같은 경우 에셋 클릭이 기록됩니다.

* 자산을 조회했습니다.
* Content Analytics 확장 구성에 따라 자산이 제외되지 않았습니다.
* 다른 페이지로 연결되는 링크인 에셋을 직접 클릭합니다.

다음과 같은 경우 경험 보기가 기록됩니다.

* 경험은 Content Analytics 구성에서 활성화됩니다.

다음과 같은 경우 경험 클릭이 기록됩니다.

* 경험이 활성화된 페이지의 링크를 클릭합니다.


### 정기 또는 특정(행동) 이벤트

Content Analytics 컨텍스트에서 정기적 또는 특정(행동) 이벤트를 실행하는 트리거는 다음과 같습니다.

* Web SDK 또는 AppMeasurement에서 이벤트를 보냅니다.
* 가시성이 숨김으로 변경됩니다. 예를 들면 다음과 같습니다.
   * 페이지 언로드
   * 탭 전환
   * 브라우저 최소화
   * 브라우저 닫기
   * 잠금 화면
* URL이 변경되어 관련 URL이 수정됩니다.
* 기록되고 전송할 준비가 된 자산 보기가 32개를 초과했습니다.


## 스키마

Content Analytics 데이터는 특정 Content Analytics 스키마를 기준으로 Experience Platform의 데이터 세트에 수집됩니다. 참조 스키마를 공개적으로 사용할 수 있습니다.

* [디지털 자산 스키마](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [디지털 경험 스키마](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [경험 이벤트 콘텐츠 스키마](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
