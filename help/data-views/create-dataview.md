---
title: 데이터 보기 만들기 또는 편집
description: 데이터 보기를 만들거나 편집할 때 구성할 수 있는 모든 설정에 대해 알아봅니다.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
role: Admin
TQID: https://experienceleague.adobe.com/EXiKrWVfmMRgZ4GF0OR410Mr2-P5IEjPy3Hf0FmRDJ8
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 3152
ht-degree: 74%

---

# 데이터 보기 만들기 또는 편집

데이터 보기 만들기에는 스키마 요소에서 지표와 차원을 생성하거나 표준 구성 요소를 사용하는 작업이 포함됩니다. 비즈니스 요구 사항에 따라 대부분의 스키마 요소는 차원이나 지표 중 하나가 될 수 있습니다. 스키마 요소를 데이터 보기로 드래그하면 Customer Journey Analytics에서 차원 또는 지표가 작동하는 방법을 조정할 수 있는 옵션이 오른쪽에 나타납니다.


>[!BEGINSHADEBOX]

데모 비디오를 보려면 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [데이터 보기 만들기 또는 편집](https://experienceleague.adobe.com/ko/docs/customer-journey-analytics-learn/tutorials/data-views/overview-of-configuring-data-views-for-cja){target="_blank"}를 확인하십시오.

>[!ENDSHADEBOX]


데이터 보기를 만들거나 편집하는 경우:

1. [Customer Journey Analytics](https://analytics.adobe.com)에 로그인하고 상단 메뉴의 **[!UICONTROL 데이터 관리]**&#x200B;에서(선택 사항) **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.
1. 데이터 보기를 만들려면 **[!UICONTROL 새 데이터 보기 만들기]**&#x200B;를 선택합니다. 또는 데이터 보기 목록에서 기존 데이터 보기를 선택하여 편집할 수 있습니다.


## 구성 {#configure}

신규 또는 기존 데이터 보기를 구성하는 경우:

![개별 컨테이너 탭으로 데이터 보기 구성](assets/data-view-configure-containers.png)



1. **[!UICONTROL 구성]** 탭을 선택합니다(아직 활성화되지 않은 경우).
1. **[!UICONTROL 설정]**, **[!UICONTROL 호환성]**, **[!UICONTROL AI 설정]** 및 **[!UICONTROL 일정]** 세부 정보를 지정하십시오(아래 참조).
1. 신규 또는 기존 데이터 보기 구성을 계속하려면 **[!UICONTROL 저장 후 계속]**&#x200B;을 선택합니다. 기존 데이터 보기 구성을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.


### 설정 {#configure-settings}

>[!CONTEXTUALHELP]
>id="dataview_externalid"
>title="외부 ID"
>abstract="외부 ID를 변경하면 데이터 보기 이름이 비즈니스 인텔리전스 도구와 같은 외부 소스에 표시되는 방식에 영향을 줍니다."


데이터 보기에 중요한 설정을 제공합니다.

| 설정 | 설명 |
| --- | --- |
| **[!UICONTROL 연결]** | 이 필드는 하나 이상의 Adobe Experience Platform 데이터 세트가 포함되어 있으며 이전에 설정한 연결에 데이터 보기를 연결합니다. |
| **[!UICONTROL 이름]** | 필수. 데이터 이름 보기. Analysis Workspace의 오른쪽 드롭다운 메뉴에 이 값이 표시됩니다. |
| **[!UICONTROL 외부 ID]** | 필수. 비즈니스 인텔리전스 도구와 같은 외부 소스에서 사용할 수 있는 데이터 보기의 이름입니다. 기본값은 `unspecified`입니다. 외부 ID를 지정하지 않으면 데이터 보기의 이름에서 이름이 생성되며 공백은 밑줄로 대체됩니다. |
| **[!UICONTROL 설명]** | 선택 사항. Adobe는 사용자가 데이터 보기가 존재하는 이유와 설계 대상을 이해할 수 있도록 자세한 설명을 권장합니다. |

{style="table-layout:auto"}

### 호환성 {#compatibility}


>[!CONTEXTUALHELP]
>id="dataview_dataviewsinadobejourneyoptimizer"
>title="Journey Optimizer의 데이터 보기"
>abstract="Customer Journey Analytics에는 Adobe Journey Optimizer과 호환되는 연결 및 데이터 보기가 필요합니다. 기본적으로 연결 및 데이터 보기가 만들어집니다. 또는 이 옵션을 활성화하여 데이터 보기에 필요한 구성 요소를 추가하고 연결에 데이터 세트를 추가하는 Adobe Journey Optimizer 보고를 위한 기본 데이터 보기로 설정하십시오."
>additional-url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/integrations/ajo#connection" text="어떤 구성 요소와 데이터 세트가 추가되는지 알아봅니다."


Customer Journey Analytics 외에 Adobe Journey Optimizer를 사용할 때 적용할 수 있는 설정을 제공합니다.

이 섹션은 Journey Optimizer로 프로비저닝된 관리자에게만 표시됩니다.

| 설정 | 설명 |
| --- | --- |
| [!UICONTROL **Adobe Journey Optimizer에서 기본 데이터 보기로 설정**] | 이 구성 옵션을 사용하면 Journey Optimizer 및 Customer Journey Analytics 전반에 걸쳐 보고를 표준화할 수 있습니다. 또한 Journey Optimizer에서 ![열기](https://spectrum.adobe.com/static/icons/workflow_18/Smock_OpenInLight_18_N.svg) [!UICONTROL **CJA에서 분석**]&#x200B;을 선택하여 Customer Journey Analytics에서 Adobe Journey Optimizer 데이터에 대한 고급 분석을 수행할 수 있습니다.<p>이러한 유형의 분석을 수행하려면 Journey Optimizer에서 Customer Journey Analytics 데이터 보기에 액세스해야 합니다.<p>사용자의 샌드박스를 위한 Journey Optimizer 보고에 사용되는 기본 데이터 보기로 설정하려면 이 옵션을 활성화하십시오.</p><p>이 구성 옵션은 자동으로 다음 작업을 수행합니다.</p><ul><li>Journey Optimizer와 함께 사용할, Customer Journey Analytics의 관련 연결에 포함된 모든 Journey Optimizer 데이터 세트를 구성합니다.</li><li>데이터 보기에서 Journey Optimizer 지표 및 차원 세트를 생성합니다(파생 필드 및 계산된 지표 포함). 컨텍스트 레이블은 이러한 모든 지표와 차원에 자동으로 설정됩니다.</li><li>이 데이터 보기와 연결된 연결에서 **[!UICONTROL CJA에서 사용]** 옵션을 자동 사용하도록 설정합니다. (이 옵션에 대한 자세한 내용은 [Customer Journey Analytics에서 Journey Optimizer 연결 사용](/help/connections/manage-connections.md)을 참조하십시오.)<p>이 설정을 활성화한 후 수동으로 비활성화하면 연결 및 연결된 데이터 보기가 기본 상태로 다시 설정됩니다. 이로 인해 보고서에 내 데이터가 변경될 수 있습니다.</p></li></ul><p><p>이 옵션을 활성화할 때 다음 사항을 고려하십시오. <ul><li>나중에 기본 데이터 보기를 변경할 수 있지만 그렇게 하면 Journey Optimizer 보고 데이터가 변경될 수 있습니다. 이 옵션을 활성화한 후 비활성화하면 새 기본 데이터 보기를 선택하라는 메시지가 표시됩니다.</li><li>Customer Journey Analytics 데이터 보기에서 데이터 세트, 차원 또는 지표를 이미 수동 사용자 정의한 경우 이 구성 옵션을 활성화해도 수동 사용자 정의는 그대로 유지됩니다. 이 옵션은 Journey Optimizer 및 Customer Journey Analytics 전반에서 보고를 더욱 표준화하여 주는 추가 사용자 정의를 만듭니다. 이 옵션을 활성화한 후 수동 사용자 정의할 수도 있습니다.</li><li>이 옵션을 선택하면 데이터 보기와 관련된 연결을 삭제할 수 없습니다.</li></ul>자세한 정보는 [Adobe Customer Journey Analytics와 Adobe Journey Optimizer 통합](/help/integrations/ajo.md)을 참조하시기 바랍니다. |

{style="table-layout:auto"}


### AI 설정

[Data Insights Agent](/help/data-analysis-ai.md)에 대한 데이터 보기를 사용하려면 **[!UICONTROL Data Insights Agent에 대해 사용]**&#x200B;을 선택하십시오. Data Insights Agent은 Customer Journey Analytics의 AI Assistant에서 액세스할 수 있는 생성 AI 대화 에이전트입니다. 이 에이전트는 텍스트 프롬프트를 통해 데이터를 빠르게 분석하는 데 도움이 됩니다. 에이전트는 데이터 보기의 구성 요소를 사용하고 실제 데이터를 사용하여 Analysis Workspace에서 관련 시각화를 빌드합니다.


### 캘린더

데이터 보기를 따르는 캘린더 형식을 보여 줍니다. 동일한 [연결](/help/connections/create-connection.md)을 기반으로 여러 데이터 보기를 소유하고 서로 다른 캘린더 유형 또는 시간대를 제공할 수 있습니다. 이러한 데이터 보기를 통해 서로 다른 캘린더 유형을 사용하는 팀들은 동일한 기본 데이터와 함께 해당하는 요구 사항을 수용할 수 있습니다.

| 설정 | 설명 |
| --- | --- |
| [!UICONTROL **시간대**] | 데이터를 표시할 시간대를 선택합니다. 일광 절약 시간에 작동하는 시간대를 선택하는 경우 데이터를 자동으로 조정하여 이러한 내용을 반영합니다. 한 시간 앞당겨 시간을 조정하는 봄철에는 한 시간의 차이가 존재합니다. 한 시간 늦춰 시간을 조정하는 가을철에는 DST 전환 시 한 시간이 반복됩니다. |
| [!UICONTROL **캘린더 유형**] | 주수를 그룹화하는 방법을 결정합니다.<br>**양력:** 표준 달력 형식. 분기는 월별로 그룹화됩니다.<br>**4-5-4 소매:** 표준화된 4-5-4 소매 달력. 분기의 첫째 달과 마지막 달에는 4주가 포함되지만 분기의 둘째 달은 5주로 구성됩니다.<br>**사용자 정의(4-5-4):** 4-5-4 캘린더와 유사하지만 예외적으로 한 해의 첫째 날과 주가 ‘추가’되는 년도를 선택할 수 있습니다.<br>**사용자 정의(4-4-5):** 각 분기의 첫째, 둘째 달에는 4주가 포함되지만 각 분기의 마지막 주는 5주로 구성됩니다.<br>**사용자 정의(5-4-4):** 각 분기의 첫째 달에는 5주가 포함되지만 각 분기의 둘째, 셋째 달은 4주로 구성됩니다. |
| [!UICONTROL **한 해의 첫째 달**] 및 [!UICONTROL **한 주의 첫째 날**] | 그레고리력 유형의 경우 표시. 연도가 시작할 월과 각 주가 시작할 요일을 지정합니다. |
| [!UICONTROL **올해 첫째 날**] | 사용자 정의 캘린더 유형의 경우 표시. 올해가 시작할 날짜를 지정합니다. 이 값에 따라 캘린더는 각 주의 첫 번째 요일을 자동으로 지정합니다. |
| [!UICONTROL **“추가 주”가 발생하는 연도**] | 364일 캘린더(주 7일 52주)를 사용하면 매년 남은 날들이 추가 주가 추가될 때까지 누적됩니다. 이 추가 주가 해당 해의 마지막 달에 추가됩니다. 주를 별도로 추가하는 년도를 지정합니다.<br><br/>**추가 주 및 윤년**<br/>&#x200B;사용자 정의 **[!UICONTROL 달력 유형]**(**[!UICONTROL 사용자 정의(4‑5‑4)]**, **[!UICONTROL 사용자 정의(4‑4‑5)]** 또는 **[!UICONTROL 사용자 정의(4‑4‑5)]**)을 선택하는 경우, 총 1주일(7일)이 될 때까지 남은 일수가 누적됩니다. 이 추가 주는 **[!UICONTROL &#39;추가&#39; 주가 발생하는 연도]**&#x200B;에서 선택한 연도에 추가됩니다.<br/><br/>윤년은 **[!UICONTROL &#39;추가&#39; 주가 발생하는 연도]**&#x200B;에 의도적으로 표시되지 않습니다. 그러나 윤년에는 여전히 53주가 포함될 수 있습니다. 윤년에 53주가 포함되도록 하려면 **[!UICONTROL &#39;추가&#39; 주가 발생하는 연도]**&#x200B;에서 평년을 선택하여 누적 날짜 오차가 목표 윤년에 대해 최대 총 7일이 되도록 합니다. 예를 들어, 2024년에 53주를 포함하려면 **[!UICONTROL 2019]**&#x200B;를 선택합니다. 2019년부터 2024년까지 총 날짜 변동은 7일(2020(+2), 2021(+1), 2022(+1), 2023(+1) 및 2024(+2))이며, 그 결과 2024년에는 53번째 주가 됩니다.<br/><br/>**[!UICONTROL 현재 연도의 첫째 날]**&#x200B;에 대한 선택은 추가 주가 도래하는 위치에 영향을 줍니다. 캘린더 미리 보기를 사용하여 구성을 확인합니다. |

{style="table-layout:auto"}

## 컨테이너

{{release-limited-testing-section}}


>[!BEGINTABS]

>[!TAB 표준]

![데이터 보기 구성](assets/data-view-containers-b2c.png)

>[!TAB B2B Edition]

![데이터 보기 구성 B2B](assets/data-view-containers-b2b.png)

>[!ENDTABS]

**[!UICONTROL 컨테이너]** 탭에서 시스템 컨테이너의 이름을 바꾸고 사용자 지정 컨테이너를 추가할 수 있습니다.

### 시스템 컨테이너

데이터 보기의 컨테이너 이름을 지정합니다. 컨테이너 이름은 [세그먼트](/help/components/segments/seg-overview.md#containers)에서 자주 사용됩니다.

| 컨테이너 이름 | 표시 이름(기본값) | 설명 |
| --- | --- | --- |
| globalAccount | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 글로벌 계정&#x200B;]** | [!UICONTROL 글로벌 계정] 컨테이너에는 지정된 시간대 내의 글로벌 계정에 대한 모든 세션 및 이벤트가 포함됩니다. 조직에서 다른 용어를 사용하는 경우 여기에서 컨테이너 이름을 바꿀 수 있습니다. |
| 사람 | **[!UICONTROL 개인]** | [!UICONTROL 개인] 컨테이너에는 지정된 시간대 내의 개인에 대한 모든 세션 및 이벤트가 포함됩니다. 조직이 서로 다른 용어(예: “방문자” 또는 “사용자”)를 사용하는 경우 여기서 컨테이너 이름을 변경할 수 있습니다. |
| session | **[!UICONTROL 세션]** | [!UICONTROL 세션] 컨테이너에서 특정 세션에 대한 페이지 상호 작용, 캠페인 또는 대화를 식별할 수 있습니다. 이 컨테이너의 이름을 ‘방문’ 또는 조직이 원하는 다른 용어로 바꿀 수 있습니다. |
| 기회 | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 기회&#x200B;]** | [!UICONTROL 기회] 컨테이너에는 지정된 시간대 내의 기회에 대한 모든 세션 및 이벤트가 포함됩니다. 조직에서 다른 용어를 사용하는 경우 여기에서 컨테이너 이름을 바꿀 수 있습니다. |
| 구매 그룹 | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 구매 그룹&#x200B;]** | [!UICONTROL 구매 그룹] 컨테이너에는 지정된 시간대 내의 구매 그룹에 대한 모든 세션 및 이벤트가 포함됩니다. 조직에서 다른 용어를 사용하는 경우 여기에서 컨테이너 이름을 바꿀 수 있습니다. |
| 이벤트 | **[!UICONTROL 이벤트]** | [!UICONTROL 이벤트] 컨테이너는 데이터 세트의 개별 이벤트를 정의합니다. 조직이 서로 다른 용어(예: “히트” 또는 “페이지 조회수”)를 사용하는 경우 여기서 컨테이너 이름을 변경할 수 있습니다. |
| account | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 계정&#x200B;]** | [!UICONTROL 계정] 컨테이너에는 지정된 시간대 내의 계정에 대한 모든 세션 및 이벤트가 포함됩니다. 조직에서 다른 용어를 사용하는 경우 여기에서 컨테이너 이름을 바꿀 수 있습니다. |

시스템 컨테이너의 이름을 변경하려면:

1. 컨테이너의 **[!UICONTROL 표시 이름]**&#x200B;을(를) 편집하려면 ![편집](/help/assets/icons/Edit.svg)을(를) 선택하십시오.
1. 컨테이너의 새 이름을 정의합니다.
1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.


### 사용자 정의 컨테이너

사용자 지정 컨테이너를 데이터 보기에 추가하여 [하위 이벤트 분석](/help/components/segments/sub-event.md)에 사용할 수 있습니다. 사용자 지정 컨테이너는 다음 위치에서 정의할 수 있습니다.

* 연결의 일부인 데이터 세트 내에서 사용할 수 있는 개체 또는 배열입니다. 예: **[!UICONTROL productListItems]**, **[!UICONTROL content_assets]** 또는 **[!UICONTROL placeContext.activePOIs]**.
* [Split](/help/data-views/derived-fields/derived-fields.md#split) 함수를 사용하여 배열을 반환하는 파생 필드입니다.
* [구분 기호](/help/data-views/component-settings/substring.md#delimiter) 옵션과 함께 [하위 문자열](/help/data-views/component-settings/substring.md) 구성 요소 설정을 사용하여 배열을 반환하도록 구성된 데이터 보기 구성 요소입니다.

사용자 지정 컨테이너를 추가하려면:

1. **[!UICONTROL 사용자 지정 컨테이너 추가]**&#x200B;를 선택합니다.
1. **[!UICONTROL 컨테이너 추가]** 대화 상자에서:
   1. **[!UICONTROL 컨테이너]** 드롭다운 메뉴에서 컨테이너를 선택합니다. 예: **[!UICONTROL productListItems.productCategories]**. 선택 시 **[!UICONTROL 스키마 경로]** 및 **[!UICONTROL 스키마 유형]**&#x200B;에 대해 업데이트된 값이 표시됩니다.

   1. 컨테이너의 **[!UICONTROL 표시 이름]**&#x200B;을(를) 입력하십시오. 예: `Product Categories`.
   1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

사용자 지정 컨테이너를 편집하려면:

1. **[!UICONTROL 표시 이름]** 열에서 사용자 지정 컨테이너에 대해 ![자세히](/help/assets/icons/More.svg)를 선택합니다.
1. 컨텍스트 메뉴에서 ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]**&#x200B;을 선택합니다.
1. **[!UICONTROL 컨테이너 편집]** 대화 상자에서:
   1. **[!UICONTROL 컨테이너]** 또는 **[!UICONTROL 표시 이름]** 또는 둘 다 수정하십시오.
   1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

사용자 지정 컨테이너를 삭제하려면:

1. 표시 이름 열에서 사용자 지정 컨테이너에 대해 ![자세히](/help/assets/icons/More.svg)를 선택합니다.
1. 컨텍스트 메뉴에서 ![삭제](/help/assets/icons/Delete.svg) **[!UICONTROL 삭제]**&#x200B;를 선택합니다.

   >[!NOTE]
   >
   >사용자 지정 컨테이너는 확인 없이 삭제됩니다.
   >

사용자 지정 컨테이너 목록을 변경하려면:

1. ![열 설정](/help/assets/icons/ColumnSetting.svg)을 선택하세요.
1. **[!UICONTROL 테이블 사용자 지정]**&#x200B;에서:
   1. 표시할 열을 선택합니다.
   1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.


## 구성 요소

다음으로 데이터 보기의 구성 요소를 설정하면 스키마 요소에서 지표와 차원을 생성할 수 있습니다. 표준 구성 요소를 사용할 수도 있습니다.

>[!IMPORTANT]
>
>단일 데이터 보기에 최대 5,000개의 지표와 5,000개의 차원을 추가할 수 있습니다.

1. **[!UICONTROL 구성 요소]** 탭을 선택합니다.

   ![구성 요소 탭](assets/dataview-components.png)

   데이터 세트를 포함하는 왼쪽 상단의 [!UICONTROL 연결]과 아래의 [!UICONTROL 스키마 필드]를 볼 수 있습니다.  모든 데이터 보기에는 이벤트, 사람, 세션 지표 및 시간 차원과 같은 표준 구성 요소가 포함됩니다.<ul><li>[사용자 지정 컨테이너](#containers-1)를 정의하면 지표가 ![ShowAllLayer](/help/assets/icons/ShowAllLayer.svg) **[!UICONTROL _사용자 지정 컨테이너 이름&#x200B;_회 발생]**(으)로 자동으로 추가됩니다.</li><li>시스템에서 기본적으로 **[!UICONTROL 은(는) 더 이상 사용되지 않습니다]** 필터를 적용하여 더 이상 사용되지 않는 스키마 필드만 나타납니다.</li></ul>

1. ![검색 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL 스키마 필드 검색]**&#x200B;을 사용하여 스키마 필드를 검색하거나 ![Folder](/help/assets/icons/Folder.svg) **[!UICONTROL 이벤트 데이트 세트]** 또는 ![Folder](/help/assets/icons/Folder.svg) **[!UICONTROL 조회 데이터 세트]** 등 데이터 세트 컬렉션으로 이동하여 필드를 찾습니다. 이벤트 데이터 세트의 경우 ![폴더](/help/assets/icons/Folder.svg) **[!UICONTROL XDM 필드]** 및 ![폴더](/help/assets/icons/Folder.svg) **[!UICONTROL 임시 및 관계 필드]**&#x200B;에 대한 개별 컬렉션을 사용할 수 있습니다.<br/>또는 ![데이터 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **파생 필드 만들기**&#x200B;를 사용하여 파생 필드를 만들 수 있습니다. 자세한 내용은 [파생 필드](./derived-fields/derived-fields.md)를 참조하십시오.

1. 특정 스키마 필드를 찾거나 파생 필드를 정의한 경우 ![Handle icon](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Page Name]**&#x200B;과 같은 필드를 왼쪽 레일에서 **[!UICONTROL 포함된 구성 요소]** 아래의 **[!UICONTROL 지표]** 또는 **[!UICONTROL 차원]** 섹션으로 끌어옵니다.동일한 스키마 필드를 차원 또는 지표 섹션으로 여러 번 드래그하고 동일한 차원 또는 지표를 여러 가지 방법으로 구성할 수 있습니다. 예를 들어 pageName 필드에서 오른쪽의 다른 [구성 요소 설정](component-settings/overview.md)을 사용하여 `Product Pages` 및 `Error pages` 차원을 만듭니다.왼쪽 메뉴에서 스키마 필드 폴더를 드래그하면 폴더 내 필드들이 적절한 섹션으로 자동 정렬됩니다. 문자열 필드는 [!UICONTROL 차원] 섹션에 표시되고 숫자 스키마 유형은 [!UICONTROL 지표] 섹션에 표시됩니다. **[!UICONTROL 모두 추가]**&#x200B;를 클릭하면 각 섹션에 모든 스키마 필드가 추가됩니다.

1. 한 가지 구성 요소를 선택하면 오른쪽에 설정이 나타납니다.

   ![데이터 보기 구성 선택됨](assets/dataview-component-pagename.png)

   [구성 요소 설정](component-settings/overview.md)을 사용하여 구성 요소를 구성합니다. 사용 가능한 구성 요소 설정은 구성 요소가 차원/지표 및 스키마 데이터 유형인 경우 달라집니다. 설정에는 다음이 포함됩니다.

   * [[!UICONTROL 속성]](component-settings/attribution.md)
   * [[!UICONTROL 비헤이비어]](component-settings/behavior.md)
   * [[!UICONTROL 포맷]](component-settings/format.md)
   * [[!UICONTROL 포함/제외 값]](component-settings/include-exclude-values.md)
   * [[!UICONTROL 지표 중복 제거]](component-settings/metric-deduplication.md)
   * [[!UICONTROL 값 옵션 없음]](component-settings/no-value-options.md)
   * [[!UICONTROL 지속성]](component-settings/persistence.md)
   * [[!UICONTROL 값 버킷팅]](component-settings/value-bucketing.md)

1. 신규 또는 기존 데이터 보기 구성을 계속하려면 **[!UICONTROL 저장 후 계속]**&#x200B;을 선택합니다. 기존 데이터 보기 구성을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

### 중복 지표 또는 차원

지표 또는 차원을 복제한 다음 특정 설정을 수정하는 것은 단일 스키마 필드에서 여러 지표 또는 차원을 만드는 효율적인 방법입니다. 오른쪽 상단에서 지표 또는 차원 이름 아래의 [!UICONTROL 복제] 설정을 선택합니다. 새 차원 또는 지표를 변경한 뒤 더 설명적인 이름으로 저장합니다.

### 필터, 스키마 필드 또는 데이터 세트

[!UICONTROL 데이터 유형], [!UICONTROL 데이터 세트], [!UICONTROL 데이터 거버넌스]와 [!UICONTROL 기타] 기준([!UICONTROL 데이터 포함 여부], [!UICONTROL ID 여부] 및 [!UICONTROL 미사용 여부] 기준)을 사용하여 왼쪽 레일의 ![필터 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) 스키마 필드를 필터링할 수 있습니다.

![필터 필드](assets/dataview-components-filter.png)

>[!TIP]
>
>데이터 보기에서 구성 요소가 제대로 로드되지 않고 오류 메시지가 표시되면 [권한 부족](../troubleshooting/lack-of-permissions.md)을 참조하여 해결 방법을 확인하십시오.


### 포함된 구성 요소 {#included-components}

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_custom"
>title="사용자 정의 레이블"
>abstract="Adobe에서 제공하는 레이블 외에도 조직에 대한 사용자 정의 레이블을 정의할 수도 있습니다."
>additional-url="https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/labels/overview" text="데이터 사용 레이블 개요"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_contract"
>title="약정 레이블"
>abstract="약정 (C) 레이블은 계약 의무가 있거나 조직의 데이터 거버넌스 정책과 관련된 데이터를 분류하는 데 사용됩니다."
>additional-url="https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/labels/overview" text="데이터 사용 레이블 개요"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_identity"
>title="ID 레이블"
>abstract="ID (I) 레이블은 특정 개인을 식별하거나 특정 개인에게 연락할 수 있는 데이터를 분류하는 데 사용됩니다."
>additional-url="https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/labels/overview" text="데이터 사용 레이블 개요"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_sensitive"
>title="민감 레이블"
>abstract="민감 (S) 레이블은 사용자 및 조직에서 민감하다고 간주하는 데이터를 분류하는 데 사용됩니다."
>additional-url="https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/labels/overview" text="데이터 사용 레이블 개요"


>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_partnerecosystem"
>title="파트너 에코시스템"
>abstract="파트너 에코시스템 (P) 레이블은 서드파티 파트너와 공유되는 데이터를 분류하는 데 사용됩니다."
>additional-url="https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/labels/overview" text="데이터 사용 레이블 개요"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_policies"
>title="정책"
>abstract="데이터 규정 준수를 지원하려면 데이터 사용 정책을 구현하십시오. 이러한 정책은 Experience Platform 내의 데이터에 대해 허용되거나 제한된 마케팅 작업을 설명합니다. 정책 필터는 활성화된 정책을 데이터 보기에 적용합니다."
>additional-url="https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/labels/overview" text="데이터 사용 레이블 개요"


>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_responsibleengagement"
>title="책임 있는 참여 레이블"
>abstract="책임 있는 참여 레이블은 책임 있는 참여를 지원하는 데 사용됩니다."
>additional-url="https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/labels/overview" text="데이터 사용 레이블 개요"


**[!UICONTROL 포함된 구성 요소]** 섹션에는 데이터 보기에 대해 구성한 **[!UICONTROL 지표]** 및 **[!UICONTROL 차원]** 목록이 포함되어 있습니다.

* 구성 요소를 검색하려면 ![검색](/help/assets/icons/Search.svg) **[!UICONTROL _구성 요소 검색_]**&#x200B;을 사용합니다.
* 나열된 포함된 구성 요소를 필터링하려면 ![필터](/help/assets/icons/Filter.svg)를 선택합니다.

  ![포함된 구성 요소 필터 대화 상자](assets/dataview_includedcomponents_filter.png)

  **[!UICONTROL 필드 필터링 기준]** 대화 상자에서 다음 카테고리를 필터링할 수 있습니다.

   * **[!UICONTROL 데이터 형식]** - [!UICONTROL 문자열], [!UICONTROL 정수], [!UICONTROL Short], [!UICONTROL 부울], [!UICONTROL Double], [!UICONTROL 바이트], [!UICONTROL Long], [!UICONTROL 날짜] 또는 [!UICONTROL 날짜-시간] 등의 데이터 형식 중 하나 이상을 선택할 수 있습니다.
   * **[!UICONTROL 데이터 세트]** - 하나 이상의 데이터 세트를 선택합니다.
   * **[!UICONTROL 데이터 거버넌스]**: [!UICONTROL 사용자 지정 레이블], [!UICONTROL 계약 레이블], [!UICONTROL ID 레이블], [!UICONTROL 민감도 레이블], [!UICONTROL 파트너 에코시스템] 또는 [!UICONTROL 정책] 하위 범주에서 하나 이상의 레이블을 선택합니다.
   * **[!UICONTROL 기타]** - [!UICONTROL 데이터 포함], [!UICONTROL ID 포함] 또는 [!UICONTROL 사용 중단 예정 아님] 옵션 중 하나 이상을 선택합니다.

  **[!UICONTROL 적용]**&#x200B;을 선택하여 필터를 적용합니다.



## 설정 {#dataview-settings}

1. **[!UICONTROL 설정]** 탭을 선택합니다.

   ![데이터 보기 설정](assets/dataview-settings.png)

1. 전체 데이터 보기에 적용할 세그먼트를 구성합니다. 아래 [설정(세그먼트)](#settings-filters)을 참조하십시오.
1. 세션 시간 제한 및 지표를 구성합니다. 아래 [세션 설정](#session-settings)을 참조하십시오.

1. 신규 또는 기존 데이터 보기 구성을 계속하려면 **[!UICONTROL 저장 후 계속]**&#x200B;을 선택합니다. 기존 데이터 보기 구성을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

### 설정(세그먼트) {#segment-settings}

전체 데이터 보기에 적용되는 세그먼트를 추가할 수 있습니다. 이 세그먼트는 작업 영역에서 실행하는 모든 보고서에 적용됩니다. 왼쪽 레일의 구성 요소에서 **[!UICONTROL 세그먼트 추가]** 필드로 세그먼트를 드래그합니다.

### 세션 설정

세션이 만료되기 전에 이벤트 간의 비활성 기간을 결정하면 새 세션이 시작됩니다. 기간은 필수 입력 항목입니다. 이벤트에 특정 지표가 포함되어 있을 때 선택적으로 새 세션이 강제로 시작될 수 있습니다. 자세한 내용은 [세션 설정](session-settings.md)을 참조하시기 바랍니다.

### 데이터 미리보기

데이터 미리보기는 다양한 컨테이너에 대해 이 데이터 보기의 데이터를 연결 데이터와 비교합니다. 미리보기 비율은 지난 90일 동안의 연결 총 수를 기준으로 합니다.

미리보기를 로드하지 않는 경우 연결이 여전히 다시 채워지는 중입니다.

원하는 설정이 모두 지정되면 **[!UICONTROL 저장]**&#x200B;을 클릭하고 마칩니다.
