---
title: Content Analytics 데이터 수집
description: Content Analytics에서 데이터가 수집되는 방식에 대한 개요
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 79%

---

# Content Analytics 데이터 수집

이 문서에서는 Content Analytics가 데이터를 수집하는 방법을 자세히 설명합니다.

## 정의

이 문서의 컨텍스트에서는 다음 정의가 사용됩니다.

* **경험**: 경험은 전체 웹 페이지의 텍스트 콘텐츠로 정의됩니다. 데이터 수집을 위해 Content Analytics는 페이지 URL을 기반으로 경험 ID를 기록합니다. 나중에 해당 페이지의 텍스트는 검색 서비스를 통해 캡처됩니다.
* **경험 ID**: 관련 URL(URL을 URL과 페이지의 콘텐츠를 구동하는 매개변수)과 [경험 버전](manual.md#versioning)의 고유한 조합입니다.
   * [구성](configuration.md)의 일부로 주어진 전체 URL에 관련된 매개변수를 지정합니다.
   * 사용할 [버전 식별자](manual.md#versioning)를 정의하면 환경의 변경 사항을 적절하게 수집할 수 있습니다.
* **자산**: 이미지입니다. Content Analytics는 에셋 URL을 기록합니다.
* **자산 ID**: 자산의 URL입니다.
* **관련 URL**: 기본 URL과 페이지의 콘텐츠를 구동하는 모든 매개변수입니다.


## 기능

Content Analytics는 콘텐츠 이벤트 데이터를 수집하기 위해 Experience Platform Edge Network Web SDK를 필요로 합니다. 해당 이벤트 데이터 수집은 Experience Platform Edge Network(웹 SDK, 서버 API) 또는 Analytics 소스 커넥터(예: AppMeasurement 사용)와 같은 메커니즘을 통해 동작 이벤트 데이터의 (기존) 데이터 수집과 결합됩니다.

Content Analytics 라이브러리는 다음과 같은 경우 데이터를 수집합니다.

* Content Analytics가 페이지에 로드되는 태그 라이브러리에 포함되는 경우
* 페이지 URL이 태그 라이브러리의 일부로 포함된 [Content Analytics 확장 기능](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}에서 구성된 경우


## Content Analytics 이벤트

Content Analytics 이벤트는 다음으로 구성됩니다.

* 표준 필드
   * 타임스탬프
   * ID
* 경험 보기(있는 경우 및 구성된 경우)
* 경험 클릭 수(있는 경우 및 구성된 경우)
* 자산 조회수(있는 경우 및 구성된 경우)
* 자산 클릭 수(있는 경우 및 구성된 경우)

Content Analytics 이벤트는 다음의 시퀀스로 수집됩니다.

1. [기록된 보기 또는 클릭](#recorded-view-or-click).
1. [Content Analytics 이벤트를 보내는 트리거](#trigger-to-send-a-content-analytics-event).

Content Analytics는 이벤트를 바로 다음에 수집하는 것이 아니라, 보기 또는 클릭을 별도로 수집하여 해당 보기 또는 클릭 직후의 이벤트를 수집하는 방식으로 데이터를 수집하여 그 순서를 반영합니다. 이러한 Content Analytics 데이터 수집 방법은 수집된 데이터의 양도 줄입니다.

### 기록된 보기 또는 클릭

자산 보기는 다음과 같은 경우 기록됩니다.

* Content Analytics 확장 기능 구성에 따라 에셋이 제외되지 않았습니다.
* 자산이 75% 정도 검토 중입니다.
* 해당 자산이 아직 이 페이지에 기록되지 않았습니다.

자산 클릭은 다음과 같은 경우 기록됩니다.

* 자산이 조회되었습니다.
* Content Analytics 확장 기능 구성에 따라 에셋이 제외되지 않았습니다.
* 다른 페이지로 연결되는 링크인 자산을 직접 클릭했습니다.

경험 보기는 다음과 같은 경우 기록됩니다.

* Content Analytics 구성에서 경험이 활성화되었습니다.

경험 클릭은 다음과 같은 경우 기록됩니다.

* 클릭이 경험이 활성화된 페이지의 링크에서 발생했습니다.


### Content Analytics 이벤트 보내기 트리거

페이지를 나가는 호출 수를 줄이기 위해 Content Analytics은 정보를 수집하지만 해당 정보를 즉시 보내지는 않습니다. 컨텐츠 상호 작용 정보가 수집되고 해당 정보를 포함하는 이벤트는 다음 트리거 중 하나가 발생할 때만 전송됩니다.

* Web SDK 또는 AppMeasurements가 이벤트를 보냅니다.
* 표시 여부가 숨김으로 변경되었습니다. 예:
   * 페이지 언로드
   * 탭 전환
   * 브라우저 최소화
   * 브라우저 닫기
   * 화면 잠금
* URL이 변경되어 관련 URL도 수정되었습니다.
* 기록되어 전송 준비가 된 자산 조회수가 32개를 초과했습니다.

>[!NOTE]
>
>추가 Content Analytics 이벤트는 세션 또는 페이지의 이벤트 수를 기반으로 하는 바운스 비율 정의에 영향을 줄 수 있습니다.
>


## 스키마

Content Analytics 데이터는 특정 Content Analytics 스키마를 기반으로 Experience Platform의 데이터 세트에 수집됩니다. 참조 스키마는 공개적으로 사용 가능합니다.

* [디지털 자산 스키마](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [디지털 경험 스키마](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [경험 이벤트 콘텐츠 스키마](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
