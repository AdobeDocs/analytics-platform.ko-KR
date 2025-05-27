---
title: 포맷 구성 요소 설정
description: 지표의 형식이 지정되는 방식을 구성합니다.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 6fdb6cbd6f12a0417f513565b02e3ad60c8df6cb
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 88%

---

# 포맷 구성 요소 설정 {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="포맷"
>abstract="보고서에서 사용될 때 구성 요소가 표시되는 방법을 결정합니다."

<!-- markdownlint-enable MD034 -->


형식을 사용하여 보고서에 사용할 때 주어진 구성 요소가 표시되는 방법을 결정할 수 있습니다.

## 구성 요소에 대한 형식 설정 구성

형식 설정을 조정하여 주어진 구성 요소가 표시되는 방식을 결정할 수 있습니다.

1. Customer Journey Analytics에서 [!UICONTROL **데이터 보기**] 탭을 선택합니다.

1. 구성하려는 포맷 설정이 있는 구성 요소의 데이터 보기를 선택합니다.

1. [!UICONTROL **구성 요소**] 탭을 선택합니다.

1. 구성하려는 구성 요소를 선택한 다음 페이지 오른쪽 섹션에 있는 [!UICONTROL **포맷**] 섹션을 확장합니다.

   ![포맷 설정](../assets/format-settings.png)

1. 다음 정보를 지정합니다.

   | 설정 | 설명 |
   | --- | --- |
   | **[!UICONTROL 포맷]** | 구성 요소의 서식을 십진수, 시간, 백분율 또는 통화로 지정할 수 있습니다. |
   | **[!UICONTROL 소수점]** | Integer 스키마 데이터 유형에 표시되지 않습니다. 구성 요소에 표시되는 소수점 이하 자리 수를 지정할 수 있습니다. |
   | **[!UICONTROL 날짜]** | 보고에서 차원으로 사용하는 경우 날짜-시간 필드가 표시되는 방법을 결정할 수 있습니다. [자세히 알아보기](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 날짜-시간]** | 보고에서 차원으로 사용하는 경우 날짜-시간 필드가 표시되는 방법을 결정할 수 있습니다. [자세히 알아보기](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 통화]** | 구성 요소에 표시할 통화를 결정할 수 있습니다. <p>다양한 통화로 거래가 발생하는 글로벌 데이터를 분석하는 경우 [통화 전환 사용](#use-currency-conversion)을 참조하십시오.</p> |
   | **[!UICONTROL 증가 트렌드를 다음으로 표시]** | 이 구성 요소의 증가 트렌드가 양호(녹색) 또는 불량(빨간색)인지 여부를 지정할 수 있습니다. |
   | **[!UICONTROL True 값]** 및 **[!UICONTROL False 값]** | 부울 스키마 데이터 유형에만 표시됩니다. `true` 및 `false` 값에 대한 차원 항목 라벨을 사용자 정의할 수 있습니다. |

   {style="table-layout:auto"}

## 통화 전환 사용 {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="통화 전환"
>abstract="선택한 통화 유형으로 통화를 구성하고 표시하려면 통화 코드 차원을 선택하십시오."

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics에서 통화 전환은 국제적으로 운영되는 비즈니스에 매우 유용할 수 있습니다. 수동 통화 변환의 복잡성을 제거함으로써 Customer Journey Analytics에서 통화 변환은 재무 데이터에 일관성과 명확성을 높여 줍니다. 통화 변환은 일일 과거 환율을 추적하고 해당 일일 환율을 4년 동안 유지합니다.

예를 들어 미국, 영국, EU에서 전자상거래 사업을 운영하는 경우 판매 데이터를 자동으로 미국 달러로 변환할 수 있어 비교가 용이하고 성과에 대한 전체적인 이해가 가능합니다.

>[!NOTE]
>
>통화 변환을 위해 지표를 구성하기 전에 다음 사항을 고려해야 합니다.
>
>* 통화 변환을 위해 선택한 지표는 숫자 유형(Double, Long, Integer, Short, Byte)이어야 합니다.
>* Customer Journey Analytics 연결을 설정하여 통화 지표를 포함하는 모든 이벤트에 대해 통화 코드 차원을 포함하는 이벤트 데이터 세트를 하나 이상 포함하도록 합니다. 해당 통화 코드 차원은 통화를 나타내는 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 표준에 따른 알파벳 통화 코드를 사용합니다. 이러한 값은 USD($), EUR(€), GBP(£)와 같이 대문자로 표시해야 합니다.

주어진 지표에 대해 통화가 표시되고 변환하는 방법을 확인하는 방법:

1. 위에서 설명한 대로 [지표에 대한 포맷 설정 구성](#configure-format-settings-for-a-metric)에서 통화를 포맷으로 사용하려는 지표 구성을 시작합니다.

1. 선택한 지표를 사용하여 페이지 오른쪽 섹션의 [!UICONTROL **포맷**] 섹션에서 다음을 선택합니다.

   * [!UICONTROL **포맷**] 필드에서 [!UICONTROL **통화**]&#x200B;를 선택합니다.

   * [!UICONTROL **소수 자릿수**] 필드에서 지표에 표시되는 소수 자릿수를 선택합니다.

     이 옵션은 지표의 숫자 유형이 “Double”인 경우에만 사용할 수 있습니다.

   * [!UICONTROL **통화 변환**] 옵션을 선택합니다.

   * [!UICONTROL **통화 코드 차원 선택**] 필드에서 변환하려는 통화를 나타내는 차원을 선택합니다(데이터의 기반이 되는 통화). 예를 들어 [!UICONTROL **통화 코드**]&#x200B;라 불리는 차원을 선택합니다.

     통화 코드 필드가 포함된 현재 데이터 스키마에 차원이 없는 경우 [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html) 또는 [파생 필드](/help/data-views/derived-fields/derived-fields.md)를 사용하여 새 통화 코드 필드를 만들 수 있습니다. 데이터 준비는 앞으로만 진행되기 때문에 새로운 구현에만 적합합니다. 조직의 설정에 따라 Data Distiller와 파생 필드를 사용하여 과거 통화 코드 값에 액세스할 수 있습니다.

   * [!UICONTROL **통화 변환 및 표시**] 필드에서 데이터를 변환할 통화를 선택합니다.

1. 추가적인 지표에 통화 변환을 적용하려면 이 단계를 반복합니다.



### 자주 묻는 질문

+++ 통화 변환은 어떻게 실행됩니까?

보고 시점에 지표 및 원래 통화 코드의 값이 USD로 변환된 다음 표시를 위해 구성된 통화로 변환됩니다. 이러한 변환에는 이벤트 당시의 일일 환율이 사용됩니다.

+++

