---
title: 속성 구성 요소 설정
description: 지표에 대한 기본 속성을 설정할 수 있습니다.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 2fd79da264d60bb90e1193ead2eee67602404b4c
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 63%

---

# 속성 구성 요소 설정 {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="속성"
>abstract="보고서의 지표에 적용되는 기본 속성 모델을 구성합니다."

<!-- markdownlint-enable MD034 -->


속성을 통해 차원 항목이 성공 이벤트에 대한 크레딧을 얻는 방식을 맞춤화할 수 있습니다.

예:

1. 사이트 방문자가 제품 페이지 중 하나에 대한 유료 검색 링크를 클릭합니다. 장바구니에 제품을 추가하지만 구매하지 않습니다.
2. 다음 날, 친구 중 한 명이 소셜 미디어에 올린 게시물을 봅니다. 링크를 클릭한 후 구매를 완료합니다.

일부 보고서에서는 유료 검색으로 인한 주문을 원할 수 있습니다. 다른 보고서에서는 Social에 속하는 순서를 원할 수도 있습니다. 속성을 사용하면 보고의 이러한 측면을 제어할 수 있습니다.

## 구성 요소의 속성 모델 설정

데이터 보기에서 구성 요소의 설정을 업데이트하여 주어진 구성 요소에 대한 기본 속성 모델을 변경할 수 있습니다. 이렇게 하면 Analysis Workspace에서 사용되는 언제든지 구성 요소의 속성 모델을 재정의합니다.

>[!NOTE]
>
>지표에 대해 기본이 아닌 속성 모델을 활성화할 때 다음 사항을 고려하십시오.
>
>* **보고서에서 지표를 *단일 차원과 함께 사용하는 경우*:** 지표의 속성은 차원에 설정된 할당 모델을 재정의합니다. 예를 들어 &quot;첫 번째 터치&quot; 속성이 있는 지표는 &quot;가장 최근&quot; 차원 할당을 무시합니다.
>
>* **보고서에서 지표를 *여러 차원과 함께 사용할 때*:** 지표의 속성은 각 차원의 할당 모델 위에 적용됩니다. 예를 들어 &quot;첫 번째 터치&quot; 속성이 있는 지표는 &quot;가장 최근&quot; 차원 할당 위에 적용됩니다.
>
> 배분에 대한 자세한 내용은 [지속성 구성 요소 설정](/help/data-views/component-settings/persistence.md)을 참조하십시오.

구성 요소의 기본 속성 모델을 업데이트하는 방법:

1. 업데이트하려는 기본 속성 모델이 포함된 데이터 보기로 이동합니다.

1. 구성 요소를 선택한 다음 화면 오른쪽의 **[!UICONTROL 속성]** 섹션을 확장합니다.

   ![속성 설정 옵션을 강조 표시한 데이터 보기 창](../assets/attribution-settings.png)

1. [!UICONTROL **속성 설정**]&#x200B;을 선택한 다음 [속성 모델](#attribution-models), [컨테이너](#container) 및 [전환 확인](#lookback-window) 창을 선택합니다.



1. [!UICONTROL **저장 후 계속**]&#x200B;을 선택합니다.

>[!TIP]
>
>조직에서 지표에 여러 속성 설정이 필요한 경우 다음 중 하나를 수행할 수 있습니다.
>
> * 데이터 보기에서 원하는 각각의 속성 설정에 따라 지표를 복사합니다. 데이터 보기에 동일한 지표를 여러 번 포함하여 각 지표에 다른 설정을 부여할 수 있습니다. 보고서를 생성할 때 분석가들이 이러한 지표들 간의 차이를 이해할 수 있도록 각 지표에 적절하게 레이블을 지정해야 합니다.
>
> * Analysis Workspace에서 지표를 재정의합니다. 지표의 [열 설정](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)에서 **[!UICONTROL 비기본 속성 모델 사용]**&#x200B;을 선택해 특정 보고서에 대한 지표의 속성 모델과 전환 확인 기간을 변경합니다.

## 속성 모델 {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="모델"
>abstract="지표에 대한 속성 모델을 선택합니다."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}

## 컨테이너

{{attribution-container}}

## 전환 확인 기간

{{attribution-lookback-window}}

## 예

{{attribution-example}}
