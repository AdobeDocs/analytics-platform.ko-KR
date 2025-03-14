---
description: Customer Journey Analytics 실험 패널의 A/B 테스트 결과를 분석할 수 있는 방법에 대해 알아봅니다.
title: 실험 패널
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '2141'
ht-degree: 18%

---

# 실험 패널 {#experimentation-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_experimentation_button"
>title="실험"
>abstract="다양한 사용자 경험, 마케팅 또는 메시징의 변화를 비교하는 패널을 만듭니다. 그리고 어떤 변화가 특정 결과를 도출하는 데 가장 적합한지 판단합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_experimentation_panel"
>title="실험"
>abstract="다양한 사용자 경험, 마케팅 또는 메시지의 변화를 비교하여 어떤 것이 특정 결과를 도출하는 데 가장 적합한지 판단합니다. 실험, 비교할 제어 변형, 성공 지표 및 표준화 지표를 지정합니다. 필요한 경우 신뢰성을 위해 상한과 하한을 설정합니다."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_이 문서에서는_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;의 실험 패널을 설명합니다._<br/>_Analytics for Target 패널](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/a4t-panel)에서 Adobe Target 활동 및 경험을 분석하는 방법에 대한 자세한 내용을 보려면_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;을 참조하세요._[

>[!ENDSHADEBOX]


**[!UICONTROL 실험]** 패널을 통해 다양한 사용자 경험, 마케팅 또는 메시징의 변화를 비교하여 어떤 것이 특정 결과를 도출하는 데 가장 적합한지 판단할 수 있습니다. 온라인, 오프라인, Target 또는 Journey Optimizer과 같은 Adobe 솔루션 및 BYO(Bring Your Own) 데이터 등 모든 실험 플랫폼에서 A/B 실험의 상승도와 신뢰도를 평가할 수 있습니다.

Adobe Customer Journey Analytics과 Adobe Target 간의 [통합에 대해 자세히 알아보세요](https://experienceleague.adobe.com/ko/docs/target/using/integrate/cja/target-reporting-in-cja).

## 액세스 제어 {#access}

실험 패널은 모든 Customer Journey Analytics 사용자가 사용할 수 있습니다. 다른 관리자 권한이나 사용 권한이 필요하지 않습니다. 그러나 사전 요구 사항에는 관리자만 수행할 수 있는 작업이 필요합니다.

## 계산된 지표의 함수

상승도와 신뢰도의 두 가지 고급 기능을 사용할 수 있습니다. 자세한 내용은 [참조 - 고급 함수](/help/components/calc-metrics/cm-adv-functions.md)를 참조하십시오.

## 사전 요구 사항

실험 패널을 사용하려면 다음 전제 조건을 따라야 합니다.

### 실험 데이터 세트에 대한 연결 만들기

권장되는 데이터 스키마는 실험 데이터가 두 개의 개별 차원에서 실험 및 변형 데이터를 포함하는 [개체 배열](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/array)에 있는 것입니다. 두 차원은 **single** 개체 배열에 있어야 합니다. 실험 데이터와 변형 데이터가 구분된 문자열에 있는 단일 차원의 실험 데이터가 있는 경우 데이터 보기의 [하위 문자열](/help/data-views/component-settings/substring.md) 설정을 사용하여 패널에서 사용할 수 있도록 차원을 두 개로 분할할 수 있습니다.


실험 데이터가 Adobe Experience Platform으로 [수집](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)되면 하나 이상의 실험 데이터 세트에 대해 [Customer Journey Analytics에서 연결을 만듭니다](/help/connections/create-connection.md).

### 데이터 보기에서 컨텍스트 레이블 추가

Customer Journey Analytics 데이터 보기 설정에서 관리자는 차원 또는 지표에 [컨텍스트 레이블](/help/data-views/component-settings/overview.md)을(를) 추가할 수 있으며 [!UICONTROL 실험] 패널과 같은 Customer Journey Analytics 서비스에서는 이러한 레이블을 목적에 사용할 수 있습니다. 실험 패널에는 두 가지의 미리 정의된 레이블이 사용됩니다.

* [!UICONTROL 실험]
* [!UICONTROL 실험 변형]

실험 데이터가 포함된 데이터 보기에서 실험 데이터가 있는 차원 하나와 변형 데이터가 있는 차원 하나를 선택합니다. 그런 다음 **[!UICONTROL 실험]** 및 **[!UICONTROL 실험 변형]** 레이블을 사용하여 해당 차원에 레이블을 지정합니다.

![실험 및 실험 변형에 대한 컨텍스트 레이블 옵션](assets/context-label.png)

이 레이블이 없으면 함께 작동할 실험이 없어 실험 패널이 작동하지 않습니다.

## 사용

**[!UICONTROL 실험]** 패널을 사용하려면:

1. **[!UICONTROL 실험]** 패널을 만듭니다. 패널을 만드는 방법에 대한 자세한 내용은 [패널 만들기](panels.md#create-a-panel)를 참조하십시오.


1. 패널의 [입력](#panel-input)을 지정합니다.

1. 패널의 [출력](#panel-output)을 확인합니다.

   >[!IMPORTANT]
   >
   >Customer Journey Analytics 데이터 보기에서 필요한 설정이 완료되지 않은 경우 진행하기 전에 다음 메시지를 받게 됩니다. [!UICONTROL 데이터 보기에서 실험 및 변형 차원을 구성하십시오].
   >

### 패널 입력

실험 패널을 사용하려면:

1. 패널 입력 설정을 구성합니다.

   ![실험 패널이 프로젝트로 드래그되었습니다.](assets/experiment-input.png)

   | 설정 | 정의 |
   | --- | --- |
   | **[!UICONTROL 날짜 범위]** | 실험 패널의 날짜 범위는 선택한 실험에 대해 Customer Journey Analytics에서 받은 첫 번째 이벤트를 기반으로 자동으로 설정됩니다. 필요한 경우 더 구체적인 시간대로 날짜 범위를 제한하거나 확장할 수 있습니다. |
   | **[!UICONTROL 실험]** | 어떤 것을 영구적으로 유지하는 것이 최선인지 판단하기 위해 최종 사용자에게 공개된 경험의 변형 세트. 실험은 두 개 이상의 변형으로 구성되며, 그 중 하나는 제어 변형으로 간주됩니다. 이 설정은 데이터 보기에서 **[!UICONTROL 실험]** 레이블로 레이블 지정된 차원과 최근 3개월의 실험 데이터로 미리 채워집니다. |
   | **[!UICONTROL 제어 변형]** | 최종 사용자 경험에서 두 가지 이상의 변경 중 하나로, 최선의 대안을 식별하기 위해 비교됩니다. 하나의 변형을 제어로 선택해야 하며, 하나의 변형만 제어 변형으로 간주될 수 있습니다. 이 설정은 데이터 보기에서 **[!UICONTROL Variant]** 레이블로 레이블 지정된 차원으로 미리 채워집니다. 이 설정은 이 실험과 관련된 변형 데이터를 가져옵니다. |
   | **[!UICONTROL 성공 지표]**➊ | 사용자가 변형을 비교하는 지표입니다. 전환 지표에 대해 가장 바람직한 결과를 나타내는 변형(최고 또는 최저)이 실험의 *가장 성과가 좋은 변형*&#x200B;으로 선언됩니다. 최대 5개의 지표를 추가할 수 있습니다. |
   | **[!UICONTROL 지표 정규화{1➋}]** | 테스트가 실행되는 기준([!UICONTROL 사람], [!UICONTROL 세션] 또는 [!UICONTROL 이벤트])입니다. 예를 들어 테스트에서는 **[!UICONTROL 전환율]**&#x200B;이 페이지 보기로 계산된 여러 변형의 전환율을 비교할 수 있습니다 |
   | **[!UICONTROL 신뢰도 상한/하한 포함]** | 신뢰 수준에 대한 상한과 하한을 표시하려면 이 옵션을 활성화하십시오. |


1. **[!UICONTROL 빌드]**&#x200B;를 선택합니다.

### 패널 출력

실험 패널은 실험의 성과를 더 잘 이해할 수 있도록 풍부한 데이터 및 시각화를 반환합니다. 패널 맨 위에는 선택한 패널 설정을 알려 주는 [요약 변경](../visualizations/summary-number-change.md) 시각화가 제공됩니다. 언제든지 오른쪽 상단의 연필 편집을 선택하여 패널을 편집할 수 있습니다.

또한 실험이 결정적인지 여부와 결과를 정리한 텍스트 요약을 얻을 수 있습니다. 결정성은 통계적 중요도를 기반으로 합니다([통계적 방법론](#adobes-statistical-methodology) 참조). 상승도와 신뢰도가 가장 높은 최상의 성능 변형에 대한 요약 번호를 볼 수 있습니다.

선택한 각 성공 지표에 대해 [자유 형식 테이블](../visualizations/freeform-table/freeform-table.md) 시각화 및 전환율 [선](../visualizations/line.md) 시각화가 표시됩니다.

![자유 형식 테이블 하나와 전환율 트렌드를 보여 주는 실험 출력입니다.](assets/experiment-output.png)


>[!NOTE]
>
>이 패널은 현재 A/A 테스트 분석을 지원하지 않습니다.

#### 결과 해석

1. **실험에 결론이 존재합니다**: 실험 보고서를 볼 때마다 이 시점까지 실험에 누적된 데이터가 분석됩니다. 분석은 *anytime* 유효한 신뢰도가 *하나 이상의* 변형에 대해 임계값 95%를 넘으면 실험이 결정적이라고 선언합니다. 두 개 이상의 팔로 Benjamini-Hochberg 보정을 적용하여 다중 가설 테스트를 수정합니다.

2. **최고 성과의 변형**: 실험이 결정적이라고 선언되면 전환율이 가장 높은 변형을 최고 성과의 변형으로 레이블 지정합니다. 이 변형은 제어 또는 기준선 변형이거나, 95% *항상* 유효 신뢰 임계값을 초과하는 변형 중 하나여야 합니다(Benjamini-Hochberg 수정 적용).

3. **전환율**: 표시되는 전환율은 표준화 지표 값에 대한 성공 지표 ➊ 값의 비율입니다➋. 지표가 이진수(실험의 각 단위당 1 또는 0)가 아닌 경우 이 값은 1보다 클 수 있습니다

4. **상승도**: 실험 보고서 요약에는 기준선 상승도가 표시되며, 이는 기준선에 대한 해당 변형의 전환율 개선 비율을 측정한 것입니다. 정확하게 정의하면 해당 변형과 기준선 간의 성과 차이를 기준선의 성과로 나눈 값이 백분율로 표시됩니다.

5. **신뢰도**: 표시된 항시 유효한 신뢰도는 해당 변형이 제어 변형과 동일하다는 증거가 얼마나 있는지에 대한 확률론적 척도입니다. 신뢰도가 높을수록 제어 변형과 비제어 변형의 성과가 동일하다는 가정의 증거가 적다는 것을 나타냅니다. 신뢰도는 주어진 변형과 제어 간의 전환율 차이가 더 작음을 관찰했을 확률(백분율로 표시)입니다. 그러나 실제로 실제 기본 전환율에는 차이가 없습니다. *p*-값의 경우 표시되는 신뢰도는 1-*p*-값입니다.

>[!NOTE]
>
>결과에 대한 전체 설명은 결정적 여부에 대한 선언뿐만 아니라 사용 가능한 모든 증거(예: 실험 설계, 표본 크기, 전환율, 신뢰도 등)를 고려해야 합니다. 결과가 아직 결정적이지 않더라도 한 변형이 다른 변형과 다르다는 강력한 증거가 있을 수 있습니다(예: 신뢰 구간이 거의 겹치지 않음). 이상적으로 연속 스펙트럼으로 해석되는 모든 통계적 증거는 의사 결정에 정보를 제공해야 합니다.

## Adobe의 통계 방법 {#statistics}

쉽게 해석이 가능하고 안전한 통계 추측을 제공하기 위해 Adobe는 [항시 유효한 신뢰 시퀀스](https://arxiv.org/abs/2103.06476) 기반의 통계 방법을 채택합니다.

신뢰 시퀀스가 신뢰 구간의 *순차적* 아날로그입니다. 신뢰 시퀀스가 무엇인지 이해하기 위해 실험을 백 번 반복한다고 상상해 보십시오. 실험에 참여하는 *모든 새 사용자*&#x200B;에 대한 평균 비즈니스 지표(예: 이메일 열람율) 및 관련 95% 신뢰 시퀀스의 추정치를 계산합니다.

95% 신뢰 시퀀스에는 100개의 실험 중 95개의 비즈니스 지표의 &quot;참&quot; 값이 포함됩니다. (95% 신뢰 구간은 모든 신규 사용자가 아닌 동일한 95% 적용 범위를 보장하기 위해 실험당 한 번만 계산할 수 있습니다.) 따라서 신뢰 시퀀스를 사용하면 거짓 양성 오류율을 증가시키지 않고 실험을 지속적으로 모니터링할 수 있습니다. 즉, 결과를 &quot;엿볼&quot; 수 있습니다.

## 비임의 차원 해석 {#non-randomized}

Customer Journey Analytics을 통해 분석가는 모든 차원을 실험으로 선택할 수 있습니다. 하지만 당신은 실험으로 선택된 차원이 무작위화된 사람이 아닌 분석을 어떻게 해석할 것인가?

예를 들어, 한 사람이 보는 광고를 생각해 보십시오. *광고 A* 대신 *광고 B*&#x200B;을(를) 표시하기로 결정한 경우 일부 지표(예: 평균 매출)의 변화를 측정하는 데 관심이 있을 수 있습니다. 광고 A 대신 광고 B를 보여주는 인과적 효과는 마케팅 의사 결정에 도달하는데 있어서 핵심적으로 중요하다. 광고 A의 상태 quo를 광고 B의 대체 전략으로 대체한 경우, 이 인과 효과는 전체 모집단에 대한 평균 매출로 측정될 수 있습니다.

A/B 테스트는 이러한 개입의 효과를 객관적으로 측정하기 위한 업계 내 Gold 표준입니다. A/B 테스트가 인과적 추정치를 발생시키는 중요한 이유는 가능한 변형 중 하나를 수신하기 위한 사람의 무작위 지정 때문입니다.

이제 무작위화에 의해 달성되지 않은 차원, 예를 들어 개인의 미국 상태를 고려하자. 사람들은 주로 뉴욕과 캘리포니아 두 개 주에서 옵니다. 한 겨울 의류 브랜드의 평균 매출액은 지역 날씨의 차이로 인해 두 주에서 차이가 날 수 있다. 이런 상황에서 날씨는 사람들의 지리적 상태가 다르다는 사실이 아니라 겨울 의류 판매의 진정한 인과 요인이 될 수 있다.

Customer Journey Analytics의 실험 패널을 사용하면 데이터를 개인의 상태에 따른 평균 수익 차이로 분석할 수 있습니다. 이와 같은 상황에서 산출물은 인과적 해석을 하지 않는다. 그러나 이러한 분석은 여전히 관심의 대상일 수 있습니다. 이는 인원의 주별 평균 수익 차이에 대한 추정치(불확실성 측정치와 함께)를 제공한다.  이 값을 *통계적 가설 테스트*&#x200B;라고도 합니다. 이러한 분석의 결과는 흥미로울 수 있지만, 반드시 실행 가능한 것은 아니다. 단순히 무작위화하지 않았기 때문에 그리고 때때로 사람들을 차원의 가능한 값 중 하나로 무작위화할 수 없다.

다음 그림은 이러한 상황을 대비합니다.

![관찰 데이터와 임의 실험을 보여 주는 다이어그램입니다.](assets/randomize.png)

중재 X가 결과 Y에 미치는 영향을 측정하고자 할 때, 양자의 진짜 원인은 교란 요인 C일 가능성이 있다. 만약 X에 대한 사람을 무작위화함으로써 데이터가 달성되지 않는다면, 그 영향은 측정하기 더 어렵고, 분석은 C에 대한 X의 의존성을 명백하게 설명한다. 무작위화는 C에 대한 X의 의존성을 깨뜨려서, 우리가 다른 변수에 대해 걱정할 필요 없이 Y에 대한 X의 영향을 측정할 수 있게 한다.

## 실험에서 계산된 지표 사용 {#use-in-experimentation}

>[!NOTE]
>
>Customer Journey Analytics과 Adobe Journey Optimizer을 모두 사용하는 조직의 경우 이 섹션의 정보는 Journey Optimizer 내의 실험 기능에도 적용됩니다.

일부 계산된 지표가 실험 패널과 호환되는 것은 아닙니다.

다음 지표 또는 상수를 포함하는 계산된 지표는 실험 패널과 호환되지 않습니다.

* [요약 데이터 집합](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/summary-data)의 기본 지표
* 서로 나누거나 함께 곱하는 기본 지표(예: `Revenue`/`Orders`)
* 기본 지표에 더하거나 빼는 상수(예: `Revenue+50`)
* 다음 기본 지표 중 하나:
   * 사용자

실험 패널과 호환되지 않는 계산된 지표는 계산된 지표를 만들 때 [!UICONTROL **제품 호환성**] 필드의 값이 [!UICONTROL **Customer Journey Analytics의 모든 곳(실험 제외)**]&#x200B;입니다. 계산된 지표를 만드는 방법에 대한 자세한 내용은 [지표 작성](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)을 참조하십시오.

## 실험 패널에서 계산된 지표 사용

[실험 패널에서 계산된 지표를 사용](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119)하는 방법에 대한 자세한 내용은 이 블로그 게시물을 참조하세요.

>[!MORELIKETHIS]
>[Adobe Customer Journey Analytics 실험 마스터링](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/mastering-adobe-customer-journey-analytics-experimentation-your/ba-p/732338)
>
