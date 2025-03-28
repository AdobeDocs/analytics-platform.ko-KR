---
title: Content Analytics 수동 구성
description: Content Analytics를 수동으로 구성하는 방법
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: bb9b9850368796fe6cf2c4945ff3ef93b881b363
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Content Analytics 수동 구성

{{release-limited-testing}}

이 문서에서는 Content Analytics 구성의 데이터 수집을 시작 또는 중지하거나 Content Analytics 구현을 편집하는 데 필요한 수동 작업에 대해 자세히 설명합니다.

다음과 같은 수동 구성 작업을 사용할 수 있습니다.

## 데이터 수집 시작

구현된 Content Analytics 구성에 대한 데이터 수집을 시작하려면 다음을 수행하십시오.

1. [게시 흐름](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}을(를) 따릅니다. Content Analytics 구성이 포함된 Tags 속성에 대한 라이브러리를 게시했습니다.

1. 개발, 스테이징 또는 게시 환경에 있는 페이지의 `<head>` 요소에 포함된 코드를 Content Analytics에 따라 [설치](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation)합니다.


## 데이터 수집 중지

구현된 Content Analytics 구성에 대한 데이터 수집을 중지하려면 다음을 수행하십시오.

1. 개발, 스테이징 또는 프로덕션 환경에서 Content Analytics에 따라 페이지의 `<head>` 요소에서 [포함된 코드](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments)을(를) 제거합니다.
1. Content Analytics 구성에 연결된 태그 속성을 [삭제](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)합니다.



## 데이터 수집 수정

[안내가 있는 구성 마법사](guided.md)를 사용하여 구현한 구성을 약간 변경할 수 있습니다. 예를 들어 데이터 보기를 변경하거나 경험을 활성화 또는 비활성화합니다.

Content Analytics 구성과 연결된 Tags 속성에서 [Adobe Content Analytics 확장](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)을 사용하여 다음 아티팩트를 변경합니다.

* [샌드박스 및 데이터스트림](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Adobe Content Analytics 확장에서 구성하는 샌드박스 및 데이터스트림이 이전 단계에서 [안내 구성](guided.md)을 사용하여 Content Analytics에 대해 이미 구성되어 있는지 확인합니다. 이 구성은 필요한 모든 아티팩트를 사용할 수 있도록 합니다.<br/><br/>또한 샌드박스 또는 데이터스트림의 업데이트가 동일한 샌드박스 또는 데이터스트림을 사용하도록 구성된 다른 Content Analytics 구성과 충돌하지 않는지 확인하십시오.
  >

* [경험 캡처 및 정의](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  경험을 활성화 또는 비활성화하고 정규 표현식과 쿼리 매개 변수의 조합을 편집하여 웹 사이트에서 콘텐츠가 렌더링되는 방식을 결정할 수 있습니다.

* [이벤트 필터링](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  정규 표현식을 편집하여 페이지 및 에셋을 필터링하는 방법을 수정할 수 있습니다.


Adobe Content Analytics 확장을 변경한 후 [게시 흐름](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}을 사용하여 변경 내용에 따라 데이터 수집을 시작하십시오.



>[!MORELIKETHIS]
>
>[구성 가이드](guided.md)
>[데이터 수집 태그 게시 개요](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## 버전 매기기

Content Analytics 경험의 버전을 관리해야 하는 경우 분석할 경험으로 간주되는 페이지에 전역 `adobe.getContentExperienceVersion` 함수를 추가해야 합니다.

`adobe.getContentExperienceVersion` 함수는 문자열을 값으로 반환해야 합니다. 이 값은 버전을 식별하기 위해 선택하는 모든 것일 수 있습니다. 버전이 [경험 ID URL](/help/content-analytics/report/components.md#experience-metadata)에 추가됩니다.

함수가 없거나 함수에서 값이 반환되지 않으면 `NoVersion` 값이 기본값으로 사용됩니다.

### 예

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
