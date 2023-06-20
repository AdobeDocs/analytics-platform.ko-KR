---
title: 포맷 구성 요소 설정
description: 지표의 형식이 지정되는 방식을 구성합니다.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 32%

---

# 포맷 구성 요소 설정

포맷을 통해 특정 지표가 표시되는 방법을 결정할 수 있습니다.

![포맷 설정](../assets/format-settings.png)

| 설정 | 설명 |
| --- | --- |
| **[!UICONTROL 포맷]** | 지표의 형식을 십진수, 시간, 백분율 또는 통화로 지정할 수 있습니다. |
| **[!UICONTROL 소수점 이하 자리 수]** | Integer 스키마 데이터 유형에 표시되지 않습니다. 지표가 표시하는 소수점 이하 자리 수를 지정할 수 있습니다. |
| **[!UICONTROL 날짜]** | 보고에서 차원으로 사용하는 경우 날짜-시간 필드가 표시되는 방법을 결정할 수 있습니다. [자세히 알아보기](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL 날짜-시간]** | 보고에서 차원으로 사용하는 경우 날짜-시간 필드가 표시되는 방법을 결정할 수 있습니다. [자세히 알아보기](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL 통화]** | 지표에 표시하려는 통화를 결정할 수 있도록 해 줍니다. 다음을 참조하십시오 [통화](#currency) 추가 세부 정보. |
| **[!UICONTROL 증가 트렌드를 다음으로 표시]** | 이 지표의 증가 트렌드를 양호(녹색) 또는 불량(빨간색)인지 여부를 지정할 수 있습니다. |
| **[!UICONTROL True 값]** 및 **[!UICONTROL False 값]** | 부울 스키마 데이터 유형에만 표시됩니다. `true` 및 `false` 값에 대한 차원 항목 라벨을 사용자 정의할 수 있습니다. |

{style="table-layout:auto"}


## 통화

다음을 선택할 때 **[!UICONTROL 통화]** (으)로 [!UICONTROL 형식] 지표의 경우, 통화를 표시하고 변환하는 방법을 결정할 수 있습니다.

### 통화 표시

지표에 대한 통화를 표시하려면:

1. 다음 수를 입력합니다. **[!UICONTROL 소수점 이하 자리 수]**.

2. 다음에서 통화 선택: **[!UICONTROL 통화 표시 위치]** 목록을 표시합니다.


### 통화 변환 및 표시

[!BADGE 새로운 기능]{type=Positive}

{{release-limited-testing-section}}

지표에 대한 통화 변환을 활성화하려면 다음을 수행합니다.

- 통화 지표를 포함하는 모든 이벤트에 대해 통화 코드 차원을 포함하는 이벤트 데이터 세트를 하나 이상 포함하도록 Customer Journey Analytics 연결을 설정합니다. 해당 통화 코드 차원은 다음을 준수하는 알파벳 통화 코드를 사용합니다. [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 통화를 나타내는 표준입니다. 예를 들어 USD는 $, EUR은 €, GBP는 파운드에 해당합니다.

- 다음을 (선택 사항) 적용했습니다. [!UICONTROL 통화 코드] 컨텍스트 레이블을 데이터 세트에서 사용할 수 있는 통화 코드를 정의하는 하나 이상의 차원에 추가합니다.

  를 적용하려면 [!UICONTROL 통화 코드] 컨텍스트 레이블, [!UICONTROL 구성 요소] 데이터 보기의 탭:

  <!--![Currency Context Label](../assets/currency-context-label.png)-->

   1. 통화 코드를 포함하는 데이터 세트 중 하나에서 차원을 선택합니다. 예를 들어, [!UICONTROL 통화 코드].

   2. 선택 **[!UICONTROL 통화 코드]** 다음에서 [!UICONTROL 컨텍스트 레이블] 목록을 표시합니다.

  통화 변환에 사용할 통화 코드를 포함하는 차원이 더 있는 경우 이 단계를 반복합니다.

>[!NOTE]
>
>통화 변환을 위해 선택하는 지표는 숫자 유형(더블, 롱, 정수, 쇼트, 바이트)이어야 합니다.


지표에 대한 통화를 변환하고 표시하는 방법을 정의하려면 다음을 수행합니다.

1. 다음 수를 입력합니다. **[!UICONTROL 소수점 이하 자리 수]**.

2. 선택 **[!UICONTROL 동시 실행 전환]**.

3. 적용된 컨텍스트 레이블을 기반으로 **[!UICONTROL 통화 코드 차원]** 목록이 자동으로 선택됩니다. 통화 코드 컨텍스트 레이블을 추가로 적용한 차원을 포함하여 다른 차원을 선택할 수 있습니다.

4. 다음에서 통화 선택: **[!UICONTROL 통화 변환 및 표시 위치]** 목록을 표시합니다.

### 자주 묻는 질문

+++ 통화 전환은 어떻게 실행됩니까?

보고 시 지표 및 원래 통화 코드의 값이 USD로 변환된 다음 표시되도록 구성된 통화로 변환됩니다. 이 전환을 위해 이벤트 시간에 적용할 수 있는 일일 통화 환율이 사용됩니다.

+++

