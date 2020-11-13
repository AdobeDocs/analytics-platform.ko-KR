---
title: Analytics 데이터 커넥터를 사용하여 마케팅 채널을 CJA로 가져오기
description: 올바른 Analytics 데이터 커넥터 설정을 사용하여 마케팅 채널 처리 규칙을 Adobe Experience Platform으로 가져옵니다.
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 7%

---


# Analytics 데이터 커넥터를 사용하여 마케팅 채널을 CJA로 가져오기

조직에서 [Analytics 데이터 커넥터](https://docs.adobe.com/content/help/ko-KR/experience-platform/sources/connectors/adobe-applications/analytics.html)를 사용하여 보고서 세트 데이터를 CJA로 가져오는 경우 CJA에서 연결을 구성하여 마케팅 채널 차원에 대해 보고할 수 있습니다.

## 전제 조건

* 보고서 세트 데이터는 이미 [분석 데이터 커넥터](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html)를 사용하여 Adobe Experience Platform으로 가져와야 합니다.
* 마케팅 채널 처리 규칙을 이미 설정해야 합니다. 기존 Analytics 구성 요소 안내서의 [마케팅 채널에 대한 처리 규칙](https://docs.adobe.com/content/help/ko-KR/analytics/components/marketing-channels/c-rules.html)을 참조하십시오.

## 마케팅 채널 스키마 요소

원하는 보고서 세트에서 Analytics 데이터 커넥터를 사용하면 XDM 스키마가 만들어집니다. 이 스키마에는 모든 Analytics 차원과 지표가 원시 데이터로 포함됩니다. 이 원시 데이터는 기여도 또는 지속성을 포함하지 않습니다. 대신, 각 히트는 마케팅 채널 처리 규칙을 통해 실행되고 일치하는 첫 번째 규칙을 기록합니다. CJA에서 데이터 보기를 만들 때 속성 및 지속성을 지정합니다.

1. [Analytics 데이터 ](/help/connections/create-connection.md) 커넥터를 기반으로 데이터 세트를 포함하는 연결을 만듭니다.
2. [다음 차원을 포함하는 데이터 ](/help/data-views/create-dataview.md) 보기를 만듭니다.
   * **`channel.typeAtSource`**:마케팅 채널측 [과 ](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) 같습니다.
   * **`channel._id`**:마케팅  [채널 세부 정보에 해당합니다.](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. 각 차원에 원하는 속성 모델과 지속성을 지정합니다. 첫 번째 및 마지막 터치 차원을 모두 사용하려면 각 마케팅 채널 차원을 구성 요소 영역으로 여러 번 드래그합니다. 각 차원에 원하는 속성 모델과 지속성을 지정합니다. 또한 Adobe에서는 작업 공간에서 보다 쉽게 사용할 수 있도록 각 차원에 표시 이름을 지정하는 것이 좋습니다.
4. 데이터 보기를 만듭니다.

이제 마케팅 채널 차원을 Analysis Workspace에서 사용할 수 있습니다.

## 처리 및 아키텍처 차이

>[!IMPORTANT]
>
>보고서 세트 데이터와 플랫폼 데이터에는 몇 가지 기본적인 데이터 차이점이 있습니다. Adobe은 플랫폼에서 적절한 데이터 수집을 용이하게 하려면 보고서 세트의 마케팅 채널 처리 규칙을 조정하는 것이 좋습니다.


첫 번째 및 마지막 접촉 채널 차원은 기본적으로 서로 다른 속성 모델을 사용하는 동일한 차원이므로 데이터 보기[를 만들 때 비슷한 차원을 다시 만들 수 있습니다. ](/help/data-views/create-dataview.md) 동일한 스키마 요소를 기반으로 여러 차원을 만들 수 있으므로 다른 속성 모델과 지속성을 제공할 수 있습니다.

## 차이점

