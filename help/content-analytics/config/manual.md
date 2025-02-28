---
title: Content Analytics 수동 구성
description: Content Analytics를 수동으로 구성하는 방법
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Content Analytics 수동 구성

>[!WARNING]
>
>이 문서는 예정된 최종 버전의 임시 비공식 초안 버전이며 Content Analytics 설명서의 일부입니다. 모든 내용은 변경될 수 있으며 이 문서의 현재 버전에서 파생될 수 있는 법적 의무는 없습니다.
>

{{release-limited-testing}}

이 문서에서는 Content Analytics 구성을 활성화 또는 비활성화하거나 Content Analytics 구현을 편집하는 데 필요한 수동 작업에 대해 자세히 설명합니다.

다음과 같은 수동 구성 작업을 사용할 수 있습니다.

## 활성화

새 구성 또는 기존 구성에 대한 변경 내용을 활성화하려면 연결된 Tag 속성을 [게시](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}해야 합니다. Content Analytics 태그 속성을 게시하는 경우에만 사용자가 구성한 도메인, 경험 및 에셋에 대해 Content Analytics 데이터가 수집됩니다.


## 비활성화

콘텐츠 분석 데이터 수집을 비활성화하려면 콘텐츠 분석 구성에 대해 연결된 태그 속성을 [게시 취소](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}하십시오.



## 수정

일반적으로 구현을 변경하려면 [안내 구성 마법사](guided.md)를 사용해야 합니다.

또는 Content Analytics 구성과 연결된 태그 속성에서 Adobe Content Analytics 확장 을 사용하여 다음 아티팩트를 변경할 수 있습니다.

* [샌드박스 및 데이터스트림](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Adobe Content Analytics 확장에서 구성하는 샌드박스 및 데이터스트림이 이전 단계에서 [안내가 있는 구성](guided.md)을 사용하여 Content Analytics에 대해 이미 구성되어 있는지 확인해야 합니다. 이 구성은 필요한 모든 아티팩트를 사용할 수 있도록 합니다.<br/><br/>또한 샌드박스 또는 데이터스트림의 업데이트가 동일한 샌드박스 또는 데이터스트림을 사용하도록 구성된 다른 Content Analytics 구성을 방해하지 않는지 확인해야 합니다.
  >

* [이벤트 필터링](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}.

  정규 표현식을 편집하여 페이지 및 에셋을 필터링하는 방법을 수정할 수 있습니다.


Adobe Content Analytics 확장을 변경한 후 변경 내용을 [활성화](#activate)합니다.



>[!MORELIKETHIS]
>
>[구성 가이드](guided.md)
>[데이터 수집 태그 게시 개요](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>