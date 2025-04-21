---
description: 세그먼트 빌더는 컨테이너 계층 논리, 규칙 및 연산자를 기준으로 지표 차원, 세그먼트 및 이벤트를 세그먼트 개인으로 드래그하여 놓을 수 있는 캔버스를 제공합니다. 이 통합 개발 도구를 사용하여 방문과 이벤트 간에 개인 속성 및 작업을 식별하는 간단하거나 복잡한 세그먼트를 작성하고 저장할 수 있습니다.
title: 세그먼트 작성
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1571'
ht-degree: 45%

---

# 세그먼트 작성 {#build-segments}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="대상자 만들기"
>abstract="세그먼트에서 대상을 만들고 활성화를 위해 Adobe Experience Platform과 공유할 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="데이터 미리보기"
>abstract="이 세그먼트의 데이터를 데이터 보기의 데이터와 비교합니다. 미리보기 비율은 **지난 90일** 동안의 데이터 보기 총 수를 기준으로 합니다.<br><br/>미리보기가 로드되지 않는다면 연결이 아직 다시 채우는 중일 수 있습니다."

<!-- markdownlint-enable MD034 -->



**[!UICONTROL 세그먼트 빌더]** 대화 상자를 사용하여 새 세그먼트를 만들거나 기존 세그먼트를 편집합니다. 대화 상자의 제목이 [[!UICONTROL 세그먼트] 관리자](/help/components/filters/manage-filters.md)에서 만들거나 관리하는 세그먼트에 대한 **[!UICONTROL 새 세그먼트]** 또는 **[!UICONTROL 세그먼트 편집]**&#x200B;입니다.

>[!BEGINTABS]

>[!TAB 세그먼트 빌더]

![다음 섹션에 설명된 필드와 옵션을 표시하는 세그먼트 세부 정보 창.](assets/filter-builder.png)

>[!TAB 세그먼트 만들기 또는 편집]

![다음 섹션에 설명된 필드와 옵션을 표시하는 세그먼트 세부 정보 창.](assets/create-edit-filter.png)

>[!ENDTABS]

1. 다음 세부 정보를 지정합니다(![필수](/help/assets/icons/Required.svg)는 필수 입력 항목).

   | 요소 | 설명 |
   | --- | --- |
   | **[!UICONTROL 데이터 보기]** | 세그먼트에 대한 데이터 보기를 선택할 수 있습니다.  정의한 세그먼트는 데이터 보기의 [설정](/help/data-views/create-dataview.md#settings-filters) 탭에서 세그먼트로 사용할 수 있습니다. |
   | **[!UICONTROL 프로젝트 전용 세그먼트]** | 세그먼트가 생성된 프로젝트에서만 볼 수 있고 세그먼트는 구성 요소 목록에 추가되지 않음을 설명하는 정보 상자입니다. **[!UICONTROL 이 세그먼트를 모든 프로젝트에 사용할 수 있도록 설정하고 구성 요소 목록에 추가]**&#x200B;하여 해당 설정을 변경할 수 있습니다. 이 정보 상자는 [빠른 세그먼트](quick-filters.md)를 만들고 [!UICONTROL 빠른 세그먼트] 인터페이스에서 **[!UICONTROL 빌더 열기]**&#x200B;를 사용하여 빠른 세그먼트 정보를 일반 세그먼트로 변경하는 경우에만 표시됩니다. |
   | **[!UICONTROL 제목]** ![필수](/help/assets/icons/Required.svg) | 세그먼트 이름을 지정합니다(예: `Last month mobile customers`). |
   | **[!UICONTROL 설명]** | 세그먼트에 대한 설명을 입력하십시오(예: `Segment to define the mobile customers for the last month`). |
   | **[!UICONTROL 태그]** | 하나 이상의 태그를 만들거나 적용하여 세그먼트를 구성합니다. 이름을 입력하여 선택할 수 있는 기존 태그를 찾습니다. 또는 **[!UICONTROL ENTER]** 키를 눌러 새 태그를 추가합니다. ![CrossSize75](/help/assets/icons/CrossSize75.svg)를 선택하여 태그를 제거합니다. |
   | **[!UICONTROL 정의]** ![필수](/help/assets/icons/Required.svg) | [정의 빌더](#definition-builder)를 사용하여 세그먼트를 정의합니다. |

   {style="table-layout:auto"}

1. 세그먼트 정의가 올바른지 확인하려면 오른쪽 상단에서 지속적으로 업데이트된 세그먼트 결과 미리보기를 사용합니다.
1. 세그먼트에서 대상자를 만들고 대상자를 Experience Platform과 공유하려면 **[!UICONTROL 세그먼트에서 대상자 만들기]**&#x200B;를 선택하세요. 자세한 내용은 [대상자 만들기 및 게시](/help/components/audiences/publish.md)를 참조하십시오.
1. 다음을 선택합니다.
   * 세그먼트를 저장하려면 **[!UICONTROL 저장]**&#x200B;하세요.
   * **[!UICONTROL 다른 이름으로 저장]**&#x200B;하여 세그먼트 복사본을 저장합니다.
   * 세그먼트를 삭제하려면 **[!UICONTROL 삭제]**&#x200B;하십시오.
   * 세그먼트에 대한 변경 내용을 취소하거나 새 세그먼트 만들기를 취소하려면 **[!UICONTROL 취소]**&#x200B;하십시오.


## 정의 빌더

정의 빌더를 사용하여 세그먼트 정의를 구성합니다. 해당 구성에서는 구성 요소, 컨테이너, 연산자, 논리를 사용합니다.

정의의 유형과 범위를 구성할 수 있습니다.

1. 정의 유형을 지정하려면 포함 정의를 작성할지, 제외 정의를 작성할지 지정합니다. ![설정](/help/assets/icons/Setting.svg) **[!UICONTROL 옵션]**&#x200B;을 선택하고 드롭다운 토글에서 **[!UICONTROL 포함]** 또는 **[!UICONTROL 제외]**&#x200B;를 선택합니다.
1. 정의 범위를 지정하려면 **[!UICONTROL 포함]** 또는 **[!UICONTROL 제외]** 드롭다운에서 정의 범위를 **[!UICONTROL 이벤트]**, **[!UICONTROL 세션]**, **[!UICONTROL 개인]**, **[!UICONTROL 글로벌 계정]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL 계정]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL 영업 기회]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} 또는 **[!UICONTROL 구매 그룹]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"} 중 하나를 선택합니다

나중에 언제든지 이러한 설정을 변경할 수 있습니다.

### 구성 요소

세그먼트 정의 구성 시 중요한 부분은 차원, 지표, 기존 세그먼트 및 날짜 범위를 사용하는 것입니다. 이러한 모든 구성 요소는 세그먼트 빌더의 구성 요소 패널에서 사용할 수 있습니다.

![정의 작성 시작](assets/start-building-filter.gif){width=100%}

구성 요소 추가 방법:

1. 구성 요소 패널에서 **[!UICONTROL 여기에 지표, 세그먼트 및/또는 차원을 드래그 앤 드롭하십시오]**. 특정 구성 요소를 검색하려면 구성 요소 표시줄의 ![검색](/help/assets/icons/Search.svg)을 사용할 수 있습니다.
1. 구성 요소에 대한 세부 정보를 지정합니다. 예를 들어 **[!UICONTROL 값 선택]**&#x200B;에서 값을 선택합니다. 또는 값을 입력합니다. 하나 이상의 값을 지정하는 방법은 구성 요소와 연산자에 따라 다릅니다.
1. 필요한 경우 기본 연산자를 수정합니다. 예: **[!UICONTROL 다음과 같음]**&#x200B;에서 **[!UICONTROL 다음 중 하나 이상의 항목과 같음]**&#x200B;으로 수정. 사용 가능한 연산자에 대한 자세한 개요는 [연산자](operators.md)를 참조하십시오.

구성 요소 편집 방법:

* 연산자 드롭다운 메뉴에서 구성 요소에 대한 새 연산자를 선택합니다.
* 적절한 경우 연산자에 대해 다른 값을 선택하거나 지정합니다.
* 구성 요소 유형이 차원인 경우, 속성 모델을 정의할 수 있습니다. 자세한 내용은 [속성 모델](#attribution-models)을 참조하십시오.

구성 요소 삭제 방법:

* 구성 요소에서 ![CrossSize75](/help/assets/icons/CrossSize75.svg)를 선택합니다.

### 컨테이너

여러 구성 요소를 하나 이상의 컨테이너로 그룹화하고 컨테이너 내부 및 컨테이너 간의 논리를 정의할 수 있습니다. 컨테이너를 사용하여 세그먼트에 대한 복잡한 정의를 작성할 수 있습니다.

![컨테이너 추가](assets/add-container.gif){Width=100%}

* 컨테이너를 추가하려면 ![설정](/help/assets/icons/Setting.svg) **[!UICONTROL 옵션]**&#x200B;에서 **[!UICONTROL 컨테이너 추가]**&#x200B;를 선택합니다.
* 컨테이너에 기존 구성 요소를 추가하려면 구성 요소를 컨테이너로 끌어다 놓습니다.
* 컨테이너에 다른 구성 요소를 추가하려면 구성 요소 패널에서 컨테이너로 구성 요소를 끌어다 놓습니다. 파란색 삽입선을 가이드로 활용합니다.
* 컨테이너 외부에 다른 구성 요소를 추가하려면 구성 요소 패널에서 구성 요소를 컨테이너 외부가 아닌 기본 정의 컨테이너 내부로 끌어다 놓습니다. 파란색 삽입선을 가이드로 활용합니다.
* 컨테이너 내 구성 요소 간, 컨테이너 간 또는 컨테이너와 구성 요소 간의 논리를 수정하려면 적절한 **[!UICONTROL And]**, **[!UICONTROL Or]**, **[!UICONTROL Then]**&#x200B;을 선택합니다. 다음 을 선택하면 세그먼트를 순차적 세그먼트로 변환합니다. 자세한 내용은 [순차적 세그먼트 만들기](seg-sequential-build.md)를 참조하십시오.
* 컨테이너 수준을 전환하려면 ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL 전역 계정]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![계정](/help/assets/icons/Account.svg) **[!UICONTROL 계정]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![기회](/help/assets/icons/Opportunity.svg) **[!UICONTROL 기회]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![구매 그룹](/help/assets/icons/BuyingGroup.svg) **[!UICONTROL 구매 그룹]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, ![웹 페이지](/help/assets/icons/WebPage.svg) **[!UICONTROL 이벤트]**, ![방문](/help/assets/icons/Visit.svg) **[!UICONTROL 세션]** 또는 ![을(를) 선택하십시오. 사용자](/help/assets/icons/User.svg) **[!UICONTROL 개인]**.

다음 액션을 위해 컨테이너에서 ![설정](/help/assets/icons/Setting.svg)을 사용할 수 있습니다.

| 컨테이너 액션 | 설명 |
|---|---|
| **[!UICONTROL 컨테이너 추가]** | 컨테이너에 중첩된 컨테이너를 추가합니다. |
| **[!UICONTROL 제외]** | 세그먼트 정의의 컨테이너에서 결과를 제외합니다. 가는 빨간색 왼쪽 막대가 제외 컨테이너를 식별합니다. |
| **[!UICONTROL 포함]** | 세그먼트 정의에 컨테이너의 결과를 포함합니다. 포함이 기본값입니다. 가는 회색 왼쪽 막대는 포함 컨테이너를 식별합니다. |
| **[!UICONTROL 이름 컨테이너]** | 기본 설명에서 컨테이너의 이름을 바꿉니다. 텍스트 필드에 이름을 입력합니다. 아무런 입력도 하지 않으면 기본 설명이 사용됩니다. |
| **[!UICONTROL 컨테이너 삭제]** | 정의에서 컨테이너를 삭제합니다. |


## 날짜 범위

순환 날짜 범위를 포함하는 세그먼트를 작성할 수 있습니다. 이렇게 하면 진행 중인 캠페인 또는 이벤트에 대한 질문에 답변할 수 있습니다. 예를 들어 *지난 60일 동안 온라인 구매를 한 모든 사용자*&#x200B;를 포함하는 세그먼트를 만들 수 있습니다.

![순환 날짜 범위를 사용하는 세그먼트](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

데모 비디오를 보려면 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [세그먼트별 순환 날짜 범위](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"}를 확인하십시오.

>[!ENDSHADEBOX]


## 스택 세그먼트 {#stack}

세그먼트를 사용하여 세그먼트를 작성할 수 있습니다. 세그먼트에서 세그먼트를 사용할 때 세그먼트를 최적화하고 복잡성을 줄일 수 있습니다.

장치 유형 (2)와 미국 상태 (50)의 조합으로 세분화하려고 한다고 상상해 보십시오. 각각 디바이스 유형(휴대폰 대 태블릿)과 미국 상태의 고유한 조합에 대해 100개의 세그먼트를 작성할 수 있습니다. 캘리포니아에서 태블릿 사용자를 가져오려면 100개의 세그먼트 중 하나를 사용합니다.

![캘리포니아 및 태블릿용 단순 세그먼트](assets/filter-ca-tablet-single.png)

또는 미국 주에 대한 50개 세그먼트, 휴대폰용 세그먼트 및 태블릿용 세그먼트 등 52개 세그먼트를 정의할 수 있습니다. 그런 다음 세그먼트를 스택하여 동일한 결과를 얻습니다. California 태블릿 사용자를 가져오려면 두 개의 세그먼트를 스택합니다.

![CA 및 태블릿에 대한 스택 세그먼트](assets/filter-ca-tablet-stacked.png)


## 속성 {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="반복"
>abstract="차원에 대한 인스턴스 및 지속된 값 포함"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="인스턴스"
>abstract="차원에 대한 인스턴스 및 지속된 값 포함"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="비반복 인스턴스"
>abstract="차원에 대한 고유(비반복) 인스턴스를 포함합니다."

<!-- markdownlint-enable MD034 -->



세그먼트 빌더에서 차원을 사용하는 경우 해당 차원에 대한 속성 모델을 지정하는 옵션이 있습니다. 선택한 속성 모델은 차원 구성 요소에 대해 지정한 조건에 데이터가 적합한지 여부를 결정합니다.

차원 구성 요소 내에서 ![설정](/help/assets/icons/Setting.svg)을 선택하고 팝업에서 속성 모델 중 하나를 선택합니다.

| 모델 | 설명 |
|---|---|
| **[!UICONTROL 반복 모델(기본값)]** | 선별을 결정하기 위해 차원에 대한 인스턴스 값과 지속되는 값을 포함합니다. |
| **[!UICONTROL 인스턴스]** | 선별을 결정하기 위해 차원에 대한 인스턴스 값만 포함합니다. |
| **[!UICONTROL 비반복 인스턴스]** | 선별을 결정하기 위해 차원에 대한 고유한 인스턴스(비반복) 값을 포함합니다. |


세그먼트를 작성할 때 차원의 ![속성 모델](assets/filter-dimension-attribution.png)

### 예

세그먼트 정의의 일부로 다음 조건을 지정했습니다. 페이지 이름이 여성과 같음. 위의 예와 유사합니다. 다른 두 기여도 분석 모델을 사용하여 이 세그먼트 정의를 반복합니다. 따라서 각각 고유한 속성 모델이 있는 세 개의 세그먼트가 있습니다.

* 여성 페이지 - 속성 - 반복(기본값)
* 여성 페이지 - 속성 - 인스턴스
* 여성 페이지 - 속성 - 비반복 인스턴스


아래 테이블은 각 속성 모델에 대해 해당 조건에 적합한 ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)에 해당하는 수신 이벤트를 설명합니다.


| 여성 페이지 - 속성 - <br/>*속성 모델* | 이벤트 1:<br/>페이지 이름이 여성과 같음<br/> | 이벤트 2:<br/>페이지 이름이 남성과 같음<br/> | 이벤트 3:<br/>페이지 이름이 여성과 같음<br/> | 이벤트 4:<br/>페이지 이름이<br/>여성과 같음<br/>(지속) | 이벤트 5:<br/>페이지 이름이 체크아웃과 같음<br/> | 이벤트 6:<br/>페이지 이름이 여성과 같음<br/> | 이벤트 7:<br/>페이지 이름이 홈과 같음<br/> |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 반복(기본값) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![제거](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![제거](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![제거](/help/assets/icons/Remove.svg) |
| 인스턴스 | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![제거](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![제거](/help/assets/icons/Remove.svg) | ![제거](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![제거](/help/assets/icons/Remove.svg) |
| 비반복 인스턴스 | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![제거](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![제거](/help/assets/icons/Remove.svg) | ![제거](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![제거](/help/assets/icons/Remove.svg) |

세 개의 세그먼트를 사용하는 이벤트에 대한 예제 보고서는 다음과 같습니다.

![세그먼트 속성 모델 결과](assets/filter-dimension-attribution-results.png)
