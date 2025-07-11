---
title: 콘텐츠 분석 가이드 구성
description: 온보딩 가이드 구성을 사용하여 콘텐츠 분석을 구성하는 방법
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 1c4342d91e0c939d596c9660ffc510c4698f8680
workflow-type: tm+mt
source-wordcount: '2696'
ht-degree: 98%

---

# 콘텐츠 분석 가이드 구성

가이드 구성을 통해 콘텐츠 분석을 빠르고 쉽게 구성할 수 있습니다. 가이드 구성은 마법사를 사용하여 조직에 맞게 콘텐츠 분석을 자동으로 구성하기 위한 요구 사항을 설정합니다. **[!UICONTROL 구성]** 화면에서 새로운 구성을 만들거나 기존 구성을 편집할 수 있습니다.

>[!IMPORTANT]
>
>조직의 샌드박스당 콘텐츠 분석 구성은 하나만 있을 수 있습니다.

콘텐츠 분석 구성 액세스 방법

* Customer Journey Analytics 메인 메뉴에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 콘텐츠 분석 구성]**&#x200B;을 선택합니다.

**[!UICONTROL 콘텐츠 분석 구성]** 화면에 기존의 콘텐츠 분석 구성 테이블이 표시됩니다.

![콘텐츠 분석 구성](../assets/aca-configuration-table.png)
각 구성에 다음의 세부 정보를 사용할 수 있습니다.

| 열 | 설명 |
|---|---|
| **[!UICONTROL 이름]** | 구성의 이름. |
| **[!UICONTROL 작성자]** | 구성을 생성한 기술 계정. |
| **[!UICONTROL 생성 일자]** | 구성을 처음 만든 타임스탬프. |
| **[!UICONTROL 수정 일자]** | 구성이가 마지막으로 수정된 타임스탬프. |
| **[!UICONTROL 샌드박스]** | 콘텐츠 분석이 구성되고 구현될 (예정인) 조직 내의 샌드박스. |
| **[!UICONTROL 상태]** | 구성의 상태. 상태는 다음과 같을 수 있습니다.<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 초안]**: 구성이 나중을 위해 저장되며 배포되지 않습니다.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 실패]**: 구성에 실패했습니다. **[!UICONTROL 편집]**&#x200B;을 선택하여 실패에 대한 정보를 얻을 수 있습니다. Adobe는 실패한 구현을 사전에 해결합니다. 자세한 내용은 고객 센터에 문의하십시오.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 완료]** 구성이 완료되고 성공적으로 구현되었습니다. |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을 사용해 테이블을 사용자 정의할 수 있습니다. **[!UICONTROL 테이블 사용자 정의]** 대화 상자에서 표시할 열을 선택하고 **[!UICONTROL 적용]**&#x200B;을 선택해 변경 사항을 적용합니다.

콘텐츠 분석 **[!UICONTROL 구성]** 화면에서 새로운 구성을 만들거나 기존 구성을 편집할 수 있습니다.

새 구성을 만드는 방법:

* **[!UICONTROL 구성 만들기]**&#x200B;를 선택합니다. 이 액션을 수행하면 [가이드 구성 마법사](#guided-configuration-wizard)가 열립니다.

기존 구성을 편집하는 방법:

* ![자세히](/help/assets/icons/More.svg)를 선택한 후 기존 콘텐츠 분석 구성을 ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]**&#x200B;합니다. 이 액션을 수행하면 [가이드 구성 마법사](#guided-configuration-wizard)가 열립니다.

## 가이드 구성 마법사

가이드 구성 마법사는 4개의 섹션([세부 사항](#details), [데이터 보기](#data-view), [경험 캡처 및 정의](#experience-capture-and-definition), [데이터 수집](#data-collection))으로 구성됩니다. 각각의 섹션에는 콘텐츠 분석을 올바르게 설정하고 구성하는 데 필요한 세부 정보를 입력하라는 메시지가 표시됩니다. 섹션의 일부 설정은 이전 섹션의 구성 값에 따라 달라질 수 있으므로 다음 섹션으로 이동하기 전에 각 섹션을 완료합니다.

### 세부 사항 {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="세부 사항"
>abstract="연결의 이름을 입력합니다. **[!UICONTROL 데이터 보기]**, **[!UICONTROL 경험 캡처 및 정의]**, **[!UICONTROL 데이터 수집]** 섹션에서 세부 정보를 제공하여 콘텐츠 분석이 올바르게 구성되도록 합니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="세부 사항"
>abstract="이 안내서에서는 Content Analytics를 구성하는 데 필요한 요구 사항에 대해 설명합니다. 이 구성에 대한 이름을 제공합니다."

<!-- markdownlint-enable MD034 -->

각 구성에는 고유한 이름이 필요합니다. 예, `Example Content Analytics configuration`. 해당 이름은 구성을 저장하거나 구현하는 데 필요합니다.

![콘텐츠 분석 구성 세부 사항](../assets/aca-configuration-details.png)


### 데이터 보기 {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="데이터 보기"
>abstract="Content Analytics을 구성하려면 기존 데이터 보기를 선택해야 합니다. 따라서 콘텐츠 분석 데이터를 다른 데이터와 병합할 수 있습니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="데이터 보기"
>abstract="Customer Journey Analytics에서 기존 데이터 보기를 선택하여 원하는 콘텐츠 분석 데이터를 병합합니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="데이터 보기"
>abstract="Customer Journey Analytics에서 기존 데이터 보기를 선택하여 원하는 콘텐츠 분석 데이터를 병합합니다.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="새로운 데이터 보기"
>abstract="이 구성에 대한 새로운 데이터 보기를 선택했습니다. 새 데이터 보기가 콘텐츠 분석 지표 및 차원을 포함하도록 업데이트됩니다. 원래 선택된 데이터 보기의 이들 지표 및 차원은 제거됩니다.<br/><br/>새 데이터 보기에 다른 연결이 연결된 경우 해당 연결은 콘텐츠 분석 데이터 세트를 포함하도록 업데이트됩니다. 콘텐츠 분석 데이터 세트는 원래 선택된 연결에서 제거되지 않습니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="선택한 데이터 보기 정리"
>abstract="Content Analytics에 이미 프로비저닝된 데이터 보기를 선택했습니다. 해당 기존 Content Analytics 구성이 제거되고 데이터 보기에 새 구성이 프로비저닝됩니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="이전 데이터 보기 정리"
>abstract="새로운 데이터 보기를 선택했습니다. 이전에 선택한 데이터 보기에 대한 Content Analytics 구성이 제거됩니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_new_dialog"
>title="새로운 데이터 보기"
>abstract="이 구성에 대한 새로운 데이터 보기를 선택했습니다. 새 데이터 보기가 콘텐츠 분석 지표 및 차원을 포함하도록 업데이트됩니다. 기존 데이터 보기의 유사한 지표 및 차원은 제거됩니다.<br/>새 데이터 보기에 다른 연결이 연결된 경우 해당 연결은 콘텐츠 분석 데이터 세트를 포함하도록 업데이트됩니다. 콘텐츠 분석 데이터 세트는 기존 구성에서 제거되지 않습니다."

<!-- markdownlint-enable MD034 -->

구성에는 [데이터 보기](/help/data-views/data-views.md)의 선택 항목이 필요합니다.

1. 데이터 보기 선택

   * 구성에 대한 새로운 데이터 보기를 선택하려면 ![데이터](/help/assets/icons/Data.svg) **[!UICONTROL 데이터 보기 선택]**&#x200B;을 사용합니다.

     ![데이터 보기의 콘텐츠 분석 구성](../assets/aca-configuration-dataview.png)

   * 구성에 대한 데이터 보기를 수정하려면 ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]**&#x200B;을 선택합니다.

     ![데이터 보기의 콘텐츠 분석 구성](../assets/aca-configuration-dataview-edit.png)


   두 시나리오 모두에서 구성에 대한 데이터 보기를 선택할 수 있는 대화 상자인 **[!UICONTROL 데이터 보기]** 대화 상자를 볼 수 있습니다.

   ![데이터 보기의 콘텐츠 분석 구성 - 데이터 보기 테이블](../assets/aca-configuration-dataview-dialog.png)

   새 구성을 만들면 활성 구성이 없는 샌드박스와 연결된 데이터 보기만 목록에 표시됩니다. 또한 액세스 권한이 있는 샌드박스와 수정 권한이 있는 연결에 연결된 데이터 보기만 볼 수 있습니다.

   기존 구성을 편집하는 경우, 목록에는 기존 구성과 이미 연결된 샌드박스 내에서 사용 가능한 데이터 보기만 표시됩니다.

   다음 작업을 수행할 수 있습니다.

   * 특정 데이터 보기를 검색하려면 ![검색](/help/assets/icons/Search.svg) 필드를 사용합니다.
   * 사용 가능한 데이터 보기 목록을 필터링하려면 ![필터 표시](/help/assets/icons/Filter.svg)를 선택하세요. [!UICONTROL 연결], [!UICONTROL 소유자] 및 [!UICONTROL 샌드박스]에서 목록을 필터링할 수 있습니다.<br/>세그먼트 창을 숨기려면 ![숨기기](/help/assets/icons/Filter.svg) **[!UICONTROL 세그먼트 숨기기]**&#x200B;를 사용합니다.
   * 테이블에 표시할 열을 정의하려면 ![열 설정](/help/assets/icons/ColumnSetting.svg)을 선택합니다. **[!UICONTROL 테이블 사용자 정의]** 대화 상자에서 표시할 열을 선택하고 **[!UICONTROL 적용]**&#x200B;을 선택해 변경 사항을 적용합니다.

1. 사용할 ![SelectBox](/help/assets/icons/SelectBox.svg) 데이터 보기를 선택합니다.
1. 선택한 데이터 보기를 확인하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다. 취소하려면 **[!UICONTROL 취소]**&#x200B;를 선택합니다.


Customer Journey Analytics에서 [데이터 보기](/help/data-views/data-views.md)는 Customer Journey Analytics [연결](/help/connections/overview.md)에 연결됩니다. 연결은 조직 내의 샌드박스를 기반으로 합니다. 구성을 저장하면 **[!UICONTROL 샌드박스]** 필드는 선택한 데이터 보기에 따라 샌드박스의 이름으로 자동 채워집니다.


### 경험 캡처 및 정의 {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="경험 캡처 및 정의"
>abstract="콘텐츠 분석을 통해 수집한 데이터에 경험을 포함하도록 선택할 수 있습니다. 선택한 경우 정규 표현식과 쿼리 매개변수의 조합을 하나 이상 설정하여 경험을 포함할 URL을 정의해야 합니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="경험 캡처 및 정의"
>abstract="콘텐츠 분석에서 경험 수집"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="경험 캡처 및 정의"
>abstract="웹 사이트에서 콘텐츠가 렌더링되는 방식을 결정하는 매개변수를 지정합니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="경험 캡처 및 정의"
>abstract="이 기능을 활성화하면 경험 데이터가 수집되고, 경험 속성이 생성되며, 경험 보고가 가능합니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="경험 캡처 및 정의"
>abstract="이 기능을 활성화하면 경험 데이터가 수집되고, 경험 속성이 생성되며, 경험 보고가 가능합니다. <br><br/>편집 ![사용](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 편집]**&#x200B;을 사용하여 태그 속성에서 현재 구성과 관련 있는 경험에 대한 수집 구성을 수정합니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="경험 캡처 및 정의"
>abstract="Adobe Content Analytics 확장 기능에서 경험 데이터 수집에 대한 설정을 편집해야 합니다."

<!-- markdownlint-enable MD034 -->

이 섹션에서 콘텐츠 분석을 통해 수집한 데이터에 경험을 포함하도록 선택할 수 있습니다.  경험은 웹 페이지를 처음 방문한 사용자가 사용한 URL을 사용하여 재생산할 수 있는 웹 페이지의 모든 텍스트입니다.

기본적으로 **[!UICONTROL 경험 포함]**&#x200B;이 꺼져 있습니다. 선택하면 어떤 URL에 경험을 포함할지 정의해야 합니다.

다음 사항이 해당되는 경우에만 경험을 포함하는 것을 고려하십시오.

* 사이트의 페이지는 페이지 URL을 사용하여 재현될 수 있어야 합니다.
* 특정 사용자가 보는 텍스트 콘텐츠는 페이지 URL을 사용하여 재생산될 수 있으며, 쿠키나 기타 개인화 메커니즘에 의존하지 않아야 합니다.

>[!IMPORTANT]
>
>콘텐츠 분석의 적용을 받는 경험(페이지)에 대한 변경 사항을 수집하도록 [콘텐츠 분석 버전 관리](manual.md#versioning)를 구현하십시오.



#### 새 구성 {#new-experiences-configuration}

새 구성이나 구현되지 않은 구성에 경험을 포함하는 방법은 다음과 같습니다.

![콘텐츠 분석 구성 경험 캡처 및 정의](../assets/aca-configuration-experience.png)

1. **[!UICONTROL 경험 포함]**&#x200B;을 활성화합니다. 경험을 활성화하도록 토글하면 다음에 영향을 미칩니다.

   * 콘텐츠 분석 확장 기능의 데이터 수집
   * 콘텐츠 분석 이벤트 데이터에서 경험 속성을 생성하는 프로세스
   * Customer Journey Analytics의 보고 템플릿

1. 웹 사이트에서 콘텐츠가 렌더링되는 방식에 대한 매개변수를 지정합니다. 매개변수는 0개 이상의 **[!UICONTROL 도메인 정규 표현식]**&#x200B;과 **[!UICONTROL 쿼리 매개변수]** 조합으로 구성됩니다. 쿼리 매개변수는 어떤 매개변수가 페이지의 콘텐츠에 영향을 미치는지 나타냅니다. 이 입력을 통해 콘텐츠 분석은 고유한 경험을 정의할 때 페이지의 콘텐츠에 영향을 미치지 않는 모든 매개변수를 무시할 수 있습니다.
   1. **[!UICONTROL 도메인 정규 표현식]**&#x200B;을 입력합니다(예: `/^(?!.*\b(store|help|admin)\b)/`). `/`을 사용하여 정규 표현식을 이스케이프해야 합니다. 도메인 정규 표현식은 이러한 매개변수가 적용되는 URL을 나타냅니다. 예를 들어 여러 사이트가 있고 각 사이트마다 다른 매개변수가 콘텐츠를 결정할 수 있습니다. 쿼리 매개변수가 모든 페이지에 적용되는 경우 `.*`를 사용하여 모든 페이지를 나타낼 수 있습니다.
   1. **[!UICONTROL 쿼리 매개변수]**&#x200B;의 쉼표로 구분된 목록을 지정합니다(예: `outdoors, patio, kitchen`).
1. 도메인 정규 표현식과 쿼리 매개변수의 조합을 제거하려면 **[!UICONTROL 제거]**&#x200B;를 선택합니다.
1. 정규 표현식과 쿼리 매개변수의 다른 조합을 추가하려면 **[!UICONTROL 정규 표현식 추가]**&#x200B;를 선택합니다.


#### 구현된 구성 {#implemented-experiences-configuration}

기존 경험을 편집하거나 구현된 구성에 새 경험을 포함하는 방법은 다음과 같습니다.

![콘텐츠 분석 구성 경험 캡처 및 정의](../assets/aca-configuration-experience-edit.png)

* **[!UICONTROL 경험 포함]**&#x200B;을 토글하여 다음을 활성화 또는 비활성화합니다.

   * 콘텐츠 분석 이벤트 데이터에서 경험 속성을 생성하는 프로세스
   * Customer Journey Analytics의 보고 템플릿

* ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]**&#x200B;을 선택하여 콘텐츠 분석의 경험을 위한 데이터 수집 구성을 추가로 편집합니다. 현재 구성과 연결된 태그 속성의 [Adobe Content Analytics 확장 기능](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)으로 리디렉션됩니다.


### 데이터 수집 {#onboarding-data-collection}

이 섹션에서는 콘텐츠 분석 데이터를 수집하는 방법을 구성합니다.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="데이터 수집"
>abstract="사용할 태그 속성을 정의하거나 태그 속성을 새로 만듭니다. 정규 표현식을 사용하여 포함하거나 제외할 페이지 및 자산을 정의합니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="데이터 수집"
>abstract="**태그 속성 제공**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="데이터 수집"
>abstract="**포함/제외할 페이지**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="데이터 수집"
>abstract="콘텐츠 분석을 위해 데이터를 수집할 때 **포함**&#x200B;하거나 **제외**&#x200B;할 페이지를 지정합니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="데이터 수집"
>abstract="**포함/제외할 자산**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="데이터 수집"
>abstract="콘텐츠 분석을 위해 데이터를 수집할 때 **포함**&#x200B;하거나 **제외**&#x200B;할 자산을 지정합니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="데이터 수집"
>abstract="현재 구성과 연결된 태그 속성의 Adobe Content Analytics 확장 기능에서 페이지 설정을 편집할 수 있습니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="데이터 수집"
>abstract="현재 구성과 연결된 태그 속성의 Adobe Content Analytics 확장 기능에서 자산 설정을 편집할 수 있습니다."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="태그 속성 비활성화됨"
>abstract="Content Analytics 확장 기능이 이미 활성화되었습니다."

<!-- markdownlint-enable MD034 -->

#### 새 구성 {#new-configuration}

새 구성에서는 기존 태그 속성을 사용할지 새 태그 속성을 만들지 정의해야 합니다. 정규 표현식을 사용하여 포함하거나 제외할 페이지 및 자산을 정의해야 합니다.

* 기존 태그 속성을 사용하는 방법은 다음과 같습니다.

  ![콘텐츠 분석 데이터 수집 기존 태그](../assets/aca-configuration-datacollection-existingtag.png)

   1. **[!UICONTROL 기존 항목 선택]**&#x200B;을 선택합니다.
   2. **[!UICONTROL 태그 속성]** 드롭다운 메뉴에서 기존 속성을 선택합니다. 속성을 입력하여 검색하고 사용 가능한 옵션을 제한할 수 있습니다. 이미 구현된 다른 콘텐츠 분석 구성에서 사용 중인 태그 속성은 선택할 수 없습니다.


* 새 태그 속성을 만드는 방법은 다음과 같습니다.

  ![콘텐츠 분석 데이터 수집 새 태그](../assets/aca-configuration-datacollection-newtag.png)

   1. **[!UICONTROL 새로 만들기]**&#x200B;를 선택합니다.
   1. **[!UICONTROL 태그 이름]**&#x200B;을 지정합니다(예: `ACA Test for Documentation`).
   1. **[!UICONTROL 도메인]**&#x200B;을 지정합니다(예: `example.com`).

* 콘텐츠 분석을 위해 데이터를 수집할 때 포함하거나 제외할 페이지를 지정합니다.

  **[!UICONTROL 포함/제외할 페이지]**&#x200B;에 대한 정규 표현식 문자열을 지정합니다. <br/>예를 들어 `^(?!.*documentation).*`을 지정하여 콘텐츠 분석에서 모든 설명서 페이지를 제외할 수 있습니다.

* 콘텐츠 분석을 위해 데이터를 수집할 때 포함하거나 제외할 자산을 지정합니다.

  **[!UICONTROL 포함/제외할 자산]**&#x200B;에 대한 정규 표현식 문자열을 지정합니다. <br/>예를 들어 `^(?!.*(logo\.jpg|\.svg)).*$`를 지정하여 콘텐츠 분석에서 모든 로고 JPEG 및 SVG 이미지를 제외할 수 있습니다.

>[!IMPORTANT]
>
>기존 Web SDK 구현이 [태그 확장 기능](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)이 아닌 [JavaScript 라이브러리](https://experienceleague.adobe.com/ko/docs/experience-platform/web-sdk/install/library)를 사용하는 경우, 새로 생성한 태그 속성에서 자동 포함된 Web SDK 확장 기능을 수동으로 제거하십시오.
>



#### 기존 구성 {#existing-configuration}

기존 구성의 경우 태그 속성을 편집할 수 없습니다. 기존 구성과 연결된 Tags 속성을 업데이트하려면 [Content Analytics 태그 확장 구성](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview)을 사용하십시오.

그러나 포함하거나 제외할 페이지와 자산을 편집할 수는 있습니다.

* 콘텐츠 분석을 위해 데이터를 수집할 때 포함하거나 제외할 페이지를 편집하려면 **[!UICONTROL 경험]** 아래의 ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]**&#x200B;을 선택합니다. 현재 콘텐츠 분석 구성의 태그 속성과 연결된 [Adobe Content Analytics 확장 기능](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)으로 리디렉션됩니다. 페이지를 포함하거나 제외하도록 정규 표현식을 편집할 수 있습니다. 변경 사항은 [게시](#publish)해야 합니다.

* 콘텐츠 분석을 위해 데이터를 수집할 때 포함하거나 제외할 자산을 편집하려면 **[!UICONTROL 자산]** 아래의 ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]**&#x200B;을 선택합니다. 현재 콘텐츠 분석 구성의 태그 속성과 연결된 [Adobe Content Analytics 확장 기능](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)으로 리디렉션됩니다. 자산을 포함하거나 제외하도록 정규 표현식을 편집할 수 있습니다. 변경 사항은 [게시](#publish)해야 합니다.

### 요약 {#summary}

필요한 모든 세부 정보를 제공하면 요약을 통해 생성되거나 수정된 아티팩트에 대한 세부 정보가 제공됩니다.

* 새 구성을 구현하면 **[!UICONTROL 콘텐츠 분석에 대한 _구성 이름_을 구현할 준비가 거의 되었습니다]** 요약이 표시됩니다.

* 기존에 구현된 구성의 경우 **[!UICONTROL 콘텐츠 분석에 대한 _구성 이름_을 구현했습니다]** 요약이 표시됩니다.

![콘텐츠 분석 구성 요약](../assets/aca-configuration-summary.png)

### 액션 {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="구현 확인"
>abstract="**[!UICONTROL 구현]**&#x200B;을 선택하면 이 워크플로에서 제공한 입력을 기반으로 Content Analytics가 구성됩니다. 일반적으로 콘텐츠 분석에 유용한 내용을 기반으로 여러 설정이 기본 선택되지만 귀하(데이터 컨트롤러)는 각 아티팩트의 설정을 검토하여 해당 설정이 귀하의 개인정보 처리방침, 계약상의 권리 및 의무, 해당 법에 따른 동의 요구 사항에 따라 구현되었는지 확인해야 합니다.<br/><br/>이 구성과 관련된 태그 라이브러리가 수동으로 게시될 때까지는 아무런 데이터도 수집되지 않습니다.<br/><br/>이미지와 텍스트의 속성을 얻기 위해 Adobe는 다음을 사용하여 속성을 가져옵니다.<ol><li>사용자가 구성한 데이터 수집 설정별로 사용자의 사이트 방문 시 캡처된 페이지의 URL</li><li>이미지가 호스팅되는 URL</li></ol>서드파티 사이트에 호스팅된 이미지에는 태그를 지정해서는 안 됩니다."

<!-- markdownlint-enable MD034 -->

구성을 생성하거나 편집할 때 다음과 같은 옵션이 있습니다.

* **[!UICONTROL 삭제]**: 구성의 일부로 적용된 모든 변경 사항이 삭제됩니다.
* **[!UICONTROL 나중을 위해 저장]**: 구성에 대한 변경 사항이 저장됩니다. 나중에 구성을 다시 방문하여 추가로 변경하거나 구성을 구현할 수 있습니다. 구성을 저장하려면 [!UICONTROL 이름] 값만 필요합니다.
* **[!UICONTROL 구현]**: 구성에 대한 설정 또는 변경 사항이 저장되고 구현됩니다. ![필수](/help/assets/icons/Required.svg) 필수로 표시되는 모든 필드는 적절한 값이 필요합니다. 구현은 다음으로 구성됩니다.

   * **[!UICONTROL Customer Journey Analytics]** 구성:
      * 선택한 데이터 보기가 콘텐츠 분석 차원 및 지표를 포함하도록 업데이트됩니다.
      * 선택한 데이터 보기에 연결된 연결이 콘텐츠 분석 이벤트 및 속성 데이터 세트를 포함하도록 수정됩니다.
      * 콘텐츠 분석 보고 템플릿이 Workspace에 추가됩니다.


   * **[!UICONTROL Adobe Experience Platform]** 구성:
      * 콘텐츠 분석 이벤트, 자산 속성 및 (구성된 경우) 경험 속성을 모델링하기 위한 스키마 생성.
      * 콘텐츠 분석 이벤트, 자산 속성 및 (구성된 경우) 경험 속성을 수집하기 위한 데이터 세트 생성.
      * 콘텐츠 분석 이벤트에서 콘텐츠 속성을 생성하고 업데이트하기 위해 기능화 서비스를 사용하는 데이터 흐름 생성.


   * **[!UICONTROL 데이터 수집]** 구성:
      * 새 태그 속성 또는 기존 태그 속성이 콘텐츠 분석 데이터 수집을 지원하도록 구성됩니다. 이 구성에는 태그에 대한 Adobe Content Analytics 확장 기능이 포함됨을 의미합니다.
      * 콘텐츠 분석 이벤트에 대한 데이터스트림이 생성됩니다.
      * Adobe Content Analytics 확장 기능은 콘텐츠 분석 이벤트가 콘텐츠 분석의 데이터스트림으로 전송되도록 구성됩니다.
      * 태그 속성에 대해 Web SDK가 구성되지 않은 경우 콘텐츠 분석 이벤트만 전송하기 위한 새 Web SDK 구성이 생성됩니다.
      * 이 태그 속성에 대해 Web SDK가 구성된 경우 기존 Web SDK 구성은 변경되지 않습니다.


* **[!UICONTROL 저장]**: 구현된 구성의 변경 사항이 저장되고 구현이 업데이트됩니다.
* **[!UICONTROL 종료]**. 가이드 구성을 종료합니다. 구현된 구성에 대한 모든 변경 사항이 삭제됩니다.


## 게시 {#publish}

콘텐츠 분석 구성에 대한 데이터 수집을 시작하려면 **[!UICONTROL 구현]**&#x200B;을 선택한 후 생성되는 태그 속성을 [수동으로](manual.md) 게시해야 합니다.


>[!MORELIKETHIS]
>
>[수동 구성](manual.md)
>
