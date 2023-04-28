---
title: 파생 필드
description: 파생 필드는 사용 가능한 함수 및 함수 템플릿 집합을 통해 스키마 필드 및/또는 표준 구성 요소의 보고서 시간 조작을 지정합니다.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
source-git-commit: 35a1a93a43869abab6e53ffb1d02edb5fad9a0c1
workflow-type: tm+mt
source-wordcount: '3062'
ht-degree: 9%

---


# 파생 필드

{{release-limited-testing}}

파생된 필드는 CJA(Customer Journey Analytics)의 실시간 보고 기능의 중요한 측면입니다. 파생된(사용자 지정) 필드를 사용하면 사용자 지정 가능한 규칙 빌더를 통해(종종 복잡함) 데이터 조작을 즉시 정의할 수 있습니다. 그런 다음 해당 파생 필드를 [작업 공간](../../analysis-workspace/home.md) 또는 을 의 구성 요소로 추가로 정의할 수 있습니다 [데이터 보기](../data-views.md).

파생된 필드는 CJA 외부의 다른 위치에서 데이터를 변환하거나 조작하는 것과 비교하여 상당한 시간과 노력을 절약할 수 있습니다. 예 [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko-KR), [데이터 Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en)또는 고유한 ETL(Extract Transform Load)/ELT(Extract Load Transform) 프로세스 내에서 사용할 수 있습니다.

파생 필드는 내에서 사용자 정의 필드로 정의됩니다 [데이터 보기](../data-views.md)는 규칙으로 정의된 함수 집합을 기반으로 하며 사용 가능한 표준 및/또는 스키마 필드에 적용됩니다.

사용 사례는 다음과 같습니다.

- 잘못된 수집된 페이지 이름 값을 수정하여 페이지 이름 값을 수정하는 사용자 지정 페이지 이름 필드를 정의합니다.

- 하나 이상의 조건(예: URL 매개 변수, 페이지 URL, 페이지 이름)을 기반으로 적절한 마케팅 채널을 결정하는 사용자 지정 마케팅 채널 필드를 정의합니다.

## 사용자 지정 필드 인터페이스

사용자 지정 필드를 만들거나 편집할 때 사용자 지정 필드 인터페이스를 사용합니다.

![사용자 지정 필드 대화 상자](assets/custom-field-dialog.png)


|  |  이름  | 설명 |
|---------|----------|--------|
| 1 | **선택기** | 선택기 영역을 사용하여 선택 및 끌어서 놓습니다 ![함수](assets/Smock_Function_18_N.svg) 함수,![함수 템플릿 아이콘](assets/Smock_FileTemplate_18_N.svg) 함수 템플릿,![스키마 필드 아이콘](assets/Smock_Folder_18_N.svg) 스키마 필드 또는![표준 필드 아이콘](assets/Smock_DragHandle_18_N.svg)규칙 빌더에 대한 표준 필드입니다. <br/>드롭다운을 사용하여 다음 중 하나를 선택합니다 [!UICONTROL 함수], [!UICONTROL 함수 템플릿], [!UICONTROL 스키마 필드], 및 [!UICONTROL 표준 필드].<br/>를 사용하여 함수, 함수 템플릿, 스키마 및 표준 필드를 검색할 수 있습니다 ![검색 아이콘](assets/Smock_Search_18_N.svg) 검색 상자. <br/>선택한 객체 목록을 선택하여 필터링할 수 있습니다 ![필터 아이콘](assets/Smock_Filter_18_N.svg) 에서 필터 및 지정 [!UICONTROL 필드 필터링 기준] 대화 상자. 을 사용하여 필터를 쉽게 제거할 수 있습니다 ![닫기 아이콘](assets/CrossSize75.svg) 참조하십시오. |
| 2 | **규칙 빌더** | 하나 이상의 규칙을 사용하여 사용자 지정 필드를 순차적으로 작성합니다. 규칙은 함수의 특정 구현이므로 항상 하나의 함수만 연관됩니다. 함수를 규칙 빌더에 끌어다 놓아 규칙을 만듭니다. 함수 유형은 규칙의 인터페이스를 결정합니다.<br/>자세한 내용은 [규칙 인터페이스](#rule-interface) 추가 정보. <br/>규칙 빌더에서 이미 사용할 수 있는 규칙 간, 시작, 종료 또는 사이에 함수를 삽입할 수 있습니다. 규칙 빌더의 마지막 규칙은 사용자 지정 필드의 최종 출력을 결정합니다. |
| 3 | **[!UICONTROL **&#x200B;필드 설정&#x200B;**]** | 사용자 지정 필드의 이름을 지정하고 설명하며 필드 유형을 검사할 수 있습니다. |
| 4 | **[!UICONTROL **&#x200B;최종 출력&#x200B;**]** | 이 영역에서는 지난 30일 동안의 데이터와 규칙 빌더의 사용자 지정 필드에 대한 변경 사항을 기반으로, 즉시 업데이트된 출력 값 미리 보기를 보여줍니다. |

{style="table-layout:auto"}

사용자 지정 필드 인터페이스에 처음 액세스하면 [!UICONTROL 필드 템플릿으로 시작] 마법사가 표시됩니다.

![사용자 지정 필드 템플릿 마법사 대화 상자](assets/field-template-dialog.png)

1. 만들려는 필드 유형을 가장 잘 설명하는 템플릿을 선택합니다.
2. 을(를) 선택합니다 **[!UICONTROL **&#x200B;선택&#x200B;**]** 계속하려면 클릭하십시오.

사용자 지정 필드 대화 상자는 선택한 필드 유형에 필요한 규칙(및 함수)으로 채워지거나 유용합니다. 자세한 내용은 [함수 템플릿](#function-templates) 를 참조하십시오.

## 규칙 인터페이스

규칙 빌더에서 규칙을 정의하면 규칙 인터페이스를 사용합니다.

![규칙 인터페이스](assets/rule-interface.png)

|  |  이름  | 설명 |
|---------|----------|--------|
| A | **규칙 이름** | 기본적으로 규칙 이름은 다음과 같습니다 **규칙 X** (X는 시퀀스 번호를 참조합니다.) 규칙 이름을 편집하려면 규칙 이름과 새 이름을 선택합니다(예: ) `Query Parameter`. |
| B | **함수 이름** | 규칙에 대해 선택한 함수 이름(예: ) [!DNL URL PARSE]. 함수가 함수 시퀀스의 마지막 부분이고 최종 출력 값을 결정하면 함수 이름 뒤에 이 함수가 옵니다 [!DNL FINAL OUTPUT], 예 [!DNL URL PARSE - FINAL OUTPUT]. <br/>함수에 대한 자세한 정보가 있는 팝업을 표시하려면 ![도움말 아이콘](assets/Smock_HelpOutline_18_N.svg). |
| C | **규칙 설명** | 선택적으로 규칙에 설명을 추가할 수 있습니다.<br/>선택 ![자세히 아이콘](assets/More.svg)를 선택하고 을 선택합니다. **[!UICONTROL **&#x200B;설명 추가&#x200B;**]** 설명을 추가하려면 **[!UICONTROL **&#x200B;설명 편집&#x200B;**]** 기존 설명을 편집하려면 다음을 수행하십시오.<br/>편집기를 사용하여 설명을 입력합니다. 도구 모음을 사용하여 텍스트 서식을 지정(스타일 선택기, 굵게, 기울임체, 밑줄, 오른쪽, 왼쪽, 가운데, 색상, 숫자 목록, 글머리 기호 목록 사용)하고 외부 정보에 링크를 추가할 수 있습니다. <br/>설명 편집을 완료하려면 편집기 외부를 클릭합니다. |
| D | **함수 영역** | 함수의 논리를 정의합니다. 인터페이스는 함수 유형에 따라 달라집니다. 자세한 내용은 [함수 참조](#function-reference) 지원되는 각 기능에 대한 자세한 정보를 제공합니다. |

{style="table-layout:auto"}

## 사용자 지정 필드 만들기

1. 기존 데이터 보기를 선택하거나 데이터 보기를 만듭니다. 자세한 내용은 [데이터 보기](../data-views.md) 추가 정보.

2. 을(를) 선택합니다 **[!UICONTROL **&#x200B;구성 요소&#x200B;**]** 탭을 클릭합니다.

3. 선택 **[!UICONTROL **&#x200B;사용자 지정 필드 만들기&#x200B;**]** 왼쪽 레일에서

4. 사용자 지정 필드를 정의하려면 [!UICONTROL 사용자 지정 필드 만들기] 인터페이스. 자세한 내용은 [사용자 지정 필드 인터페이스](#custom-field-interface).

   새 사용자 지정 필드를 저장하려면 **[!UICONTROL **&#x200B;저장&#x200B;**]**.

5. 새 사용자 지정 필드가 **[!UICONTROL **&#x200B;사용자 지정 필드 >**]** 컨테이너, **[!UICONTROL **&#x200B;스키마 필드&#x200B;**]** ( 데이터 보기의 왼쪽 레일에 있습니다.)


## 사용자 지정 필드 편집

1. 기존 데이터 보기를 선택합니다. 자세한 내용은 [데이터 보기](../data-views.md) 추가 정보.

2. 을(를) 선택합니다 **[!UICONTROL **&#x200B;구성 요소&#x200B;**]** 탭을 클릭합니다.

3. 선택 **[!UICONTROL **&#x200B;스키마 필드&#x200B;**]** 탭에서 다음을 수행합니다. [!UICONTROL 연결] 창의 왼쪽에 있습니다.

4. 선택 **[!UICONTROL **&#x200B;사용자 지정 필드 >**]** 컨테이너.

5. 편집할 사용자 지정 필드 위로 마우스를 가져간 다음 선택합니다 ![편집 아이콘](assets/Smock_Edit_18_N.svg).

6. 사용자 지정 필드를 편집하려면 [!UICONTROL 사용자 지정 필드 편집] 인터페이스. 자세한 내용은 [사용자 지정 필드 인터페이스](#custom-field-interface).

   - 선택 **[!UICONTROL **&#x200B;저장&#x200B;**]** 업데이트된 사용자 지정 필드를 저장하려면 을 클릭합니다.

   - 선택 **[!UICONTROL **&#x200B;취소&#x200B;**]** 사용자 지정 필드의 변경 사항을 취소하려면 다음을 수행하십시오.

   - 선택 **[!UICONTROL **&#x200B;다른 이름으로 저장&#x200B;**]** 사용자 지정 필드를 새 사용자 지정 필드로 저장 새 사용자 지정 필드의 이름은 `(copy)` 가 추가되었습니다.

## 사용자 지정 필드 삭제

1. 기존 데이터 보기를 선택합니다. 자세한 내용은 [데이터 보기](../data-views.md) 추가 정보.

2. 을(를) 선택합니다 **[!UICONTROL **&#x200B;구성 요소&#x200B;**]** 탭을 클릭합니다.

3. 선택 **[!UICONTROL **&#x200B;스키마 필드&#x200B;**]** 탭 [!UICONTROL 연결] 창

4. 선택 **[!UICONTROL **&#x200B;사용자 지정 필드 >**]** 컨테이너.

5. 삭제할 사용자 지정 필드를 마우스로 가리킨 다음 을 선택합니다 ![편집 아이콘](assets/Smock_Edit_18_N.svg).

6. 사용 중 **[!UICONTROL **&#x200B;사용자 지정 필드 편집&#x200B;**]** 인터페이스에서 삭제를 선택합니다.

   A [!UICONTROL 구성 요소 삭제] 대화 상자에 삭제를 확인하는 메시지가 표시됩니다. 데이터 보기 외부에 사용자 지정 필드에 있을 수 있는 외부 참조를 고려하십시오.

   - 선택 **[!UICONTROL **&#x200B;계속&#x200B;**]** 를 클릭하여 사용자 지정 필드를 삭제합니다.


## 함수 템플릿

특정 사용 사례에 대한 사용자 지정 필드를 빠르게 만들기 위해 함수 템플릿을 사용할 수 있습니다. 이러한 함수 템플릿은 사용자 지정 필드 인터페이스의 선택기 영역에서 액세스할 수 있거나, 처음 사용할 때 [!UICONTROL 필드 템플릿으로 시작] 마법사


### 마케팅 채널

이 템플릿은 [Url 구문 분석](#dnl-url-parse) 및 [Case When](#dnl-case-when) 함수를 여러 번 사용하여 URL에서 적절한 값을 가져올 수 있습니다. 그런 다음 이러한 값에 논리를 적용하여 URL을 특정 마케팅 채널과 연결합니다.

+++ 세부 사항

템플릿을 사용하려면 템플릿에 있는 규칙의 일부로 나열된 각 함수에 대한 올바른 매개 변수를 지정해야 합니다. 자세한 내용은 [함수 참조](#function-reference) 추가 정보.

![마케팅 채널 템플릿 규칙 빌더](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## 함수 참조

지원되는 각 함수에 대해 아래에서 세부 정보를 확인하십시오.

- 입력, 연산자 및 출력

- 사용 사례:
   - 사용자 지정 필드를 정의하기 전 데이터
   - 사용자 지정 필드를 정의하는 방법
   - 사용자 지정 필드를 정의한 후 데이터


<!-- Concatenate -->

### [!DNL Concatenate]

두 개 이상의 필드, 사용자 지정 필드 또는 사용자 입력 값을 정의된 구분 기호가 있는 단일 필드에 결합합니다.

+++ 세부 사항

## 입력/연산자/출력 {#concatenate-io}

| 입력 데이터 유형 | 입력 | 포함된 연산자 | 출력 |
|---|---|---|---|
| <p>문자열</p> | <ul><li>결합할 둘 이상의 값<ul><li>필드</li><li>이전 규칙에서 파생된 값</li><li>사용자 입력 값</li></ul></li><li>구분 기호<ul><li>각 값에 대한 구분 기호 입력 또는 선택</li></ul></li> </ul> | <p>해당 사항 없음</p> | <p>새 사용자 지정 필드</p> |

{style="table-layout:auto"}


## 사용 사례 {#concatenate-uc}

현재 원본 및 대상 공항 코드를 별도의 필드로 수집합니다. 두 필드를 하이픈(-)으로 구분하여 단일 차원으로 결합하려는 경우 따라서 원본과 대상의 조합을 분석하여 예약된 상위 경로를 식별할 수 있습니다.

가정:

- 원본 및 대상 값은 동일한 테이블의 개별 필드에 수집됩니다.
- 사용자는 값 사이에 구분 기호 &#39;-&#39;를 사용하도록 결정합니다.

다음과 같은 예약이 발생한다고 가정합니다.

- 고객 ABC123은 Salt Lake City(SLC)와 Orlando(MCO) 간 비행을 예약했습니다
- 고객 ABC456 는 Salt Lake City(SLC)와 Los Angeles(LAX) 간 비행을 예약합니다.
- 고객 ABC789에서 Salt Lake City(SLC)와 Seattle(SEA) 간 비행을 예약합니다.
- 고객 ABC987은 Salt Lake City(SLC)와 San Jose(SJO) 간 비행을 예약했습니다
- 고객 ABC654는 Salt Lake City(SLC)와 Orlando(MCO) 간 비행을 예약했습니다

원하는 보고서는 다음과 같습니다.

| 원본/대상 | 예약 |
|---|---|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### 이전 데이터 {#concatenate-uc-databefore}

| Origin | 대상 |
|----|----|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### 사용자 지정 필드 {#concatenate-customfield}

새 **[!UICONTROL **&#x200B;원본 - 대상&#x200B;**]** 사용자 지정 필드. 를 사용합니다 **[!UICONTROL 연결]** 를 연결하는 규칙을 정의하는 함수 [!UICONTROL 원본] 및 [!UICONTROL 대상] 필드를 사용하여 `-` [!UICONTROL 구분 기호].

![[!DNL Concatenate] 규칙](assets/concatenate.png)

### 데이터 후 {#concatenate-dataafter}

| 원본 - 대상<br/>(사용자 지정 필드) |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++

<!-- CASE WHEN -->

### [!DNL Case When]

하나 이상의 필드에서 정의된 기준에 따라 조건을 적용합니다. 그런 다음 이러한 기준을 사용하여 조건의 시퀀스를 기반으로 새 사용자 지정 필드에 값을 정의합니다.

+++ 세부 사항

## 입력/연산자/출력 {#casewhen-io}

| 입력 데이터 유형 | 입력 | 포함된 연산자 | 출력 |
|---|---|---|---|
| <ul><li>문자열</li><li>숫자</li><li>날짜/날짜-시간</li></ul> | <ul><li>입력 필드</li><li>기준</li></ul> | <p><u>문자열</u></p><ul><li>다음과 같음</li><li>모든 검색어와 같음</li><li>구문 포함</li><li>검색어를 하나라도 포함</li><li>다음 검색어 포함</li><li>다음으로 시작</li><li>임의의 용어로 시작</li><li>다음으로 끝남</li><li>임의의 용어로 종료</li><li>다음과 같지 않음</li><li>모든 검색어와 같지 않음</li><li>다음 구문 포함 안 함</li><li>검색어 포함 안 함</li><li>모든 검색어를 포함하지 않음</li><li>다음으로 시작하지 않음</li><li>다음으로 시작하지 않음</li><li>다음으로 끝나지 않음</li><li>어떤 용어로도 끝나지 않음</li><li>세트임</li><li>세트가 아님</li></ul><p><u>숫자</u></p><ul><li>다음과 같음</li><li>다음과 같지 않음</li><li>다음보다 큼</li><li>다음보다 크거나 같음</li><li>다음보다 작음</li><li>다음보다 작거나 같음</li><li>세트임</li><li>세트가 아님</li></ul><p><u>날짜</u></p><ul><li>다음과 같음</li><li>다음과 같지 않음</li><li>보다 나중</li><li>다음보다 이후이거나 같음</li><li>다음 이전</li><li>다음 이전이거나 다음과 같음</li><li>세트임</li><li>세트가 아님</li></ul> | <p>새 사용자 지정 필드</p> |

{style="table-layout:auto"}


## 사용 사례 1 {#casewhen-uc1}

마케팅 채널 필드를 적절한 값으로 설정하는 계단식 논리를 적용하여 다양한 마케팅 채널을 식별하는 규칙을 정의하려고 합니다.

- 레퍼러가 검색 엔진에서 온 것이며 페이지에 다음과 같은 쿼리 문자열 값이 있는 경우 `cid` 다음 포함 `ps_`, 마케팅 채널은 **유료 검색**.
- 레퍼러가 검색 엔진에서 온 것이며 페이지에 쿼리 문자열이 없는 경우 `cid`, 마케팅 채널은 **자연어 검색**.
- 페이지에 다음과 같은 쿼리 문자열 값이 있는 경우 `cid` 다음 포함 `em_`, 마케팅 채널은 **이메일**.
- 페이지에 다음과 같은 쿼리 문자열 값이 있는 경우 `cid` 다음 포함 `ds_`, 마케팅 채널은 **디스플레이 광고**.
- 페이지에 다음과 같은 쿼리 문자열 값이 있는 경우 `cid` 다음 포함 `so_`, 마케팅 채널은 **유료 소셜**.
- 레퍼러가 twitter.com, facebook.com, linkedin.com 또는 tiktok.com의 참조 도메인에서 온 경우 마케팅 채널은 **자연어 소셜**.
- 위의 규칙 중 어느 하나도 일치하지 않는 경우 마케팅 채널을 **기타 레퍼러**.

레퍼러 및 페이지 URL이 포함된 다음 샘플 이벤트를 사이트가 수신하는 경우 이러한 이벤트를 다음과 같이 식별해야 합니다.

| 이벤트 | 레퍼러 | 페이지 URL | 마케팅 채널 |
|:----:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | 자연어 소셜 |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | 표시 |
| 3 |  | `https://site.com/?cid=em_12345678` | 이메일 |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | 유료 검색 |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | 이메일 |
| 6 | `https://google.com` |  | 자연어 검색 |

{style="table-layout:auto"}

### 이전 데이터 {#casewhen-uc1-databefore}

| 레퍼러 | 페이지 URL |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` |

{style="table-layout:auto"}

### 사용자 지정 필드 {#casewhen-uc1-customfield}

새 `Marketing Channel` 사용자 지정 필드. 를 사용합니다 **[!UICONTROL CASE WHEN]** 함수를 사용하여 두 페이지의 `Page URL` 및 `Referring URL` 필드.

함수의 사용에 주목하십시오 **[!UICONTROL ** URL 구문 분석&#x200B;**]** 값을 가져올 규칙을 정의하려면 `Page Url` 및 `Referring Url` 이전 **[!UICONTROL ** CASE WHEN **]** 규칙이 적용됩니다.

![[!DNL Case when] 규칙 1](assets/case-when-1.png)

### 데이터 후 {#casewhen-uc1-dataafter}

| 마케팅 채널 |
|----|
| 자연어 소셜 |
| 표시 |
| 이메일 |
| 유료 검색 |
| 이메일 |
| 자연어 검색 |

{style="table-layout:auto"}


## 사용 사례 2 {#casewhen-uc2}

제품 검색 방법 차원 내에서 여러 가지 검색 변형을 수집했습니다. 검색과 찾아보기의 전반적인 성과를 이해하려면 결과를 수동으로 결합하는 데 많은 시간을 사용해야 합니다.

사이트에서는 제품 검색 방법 차원에 대해 다음 값을 수집합니다. 결국 이 모든 값은 검색을 나타냅니다.

| 수집된 값 | 실제 값 |
|---|---|
| 검색 p13n_no | 검색 |
| p13n_yes 검색 | 검색 |
| 검색 세분화 p13n_no | 검색 |
| 검색 세분화 p13n_yes | 검색 |
| 검색 리디렉션 p13n_yes | 검색 |
| search-redirect | 검색 |

{style="table-layout:auto"}


### 이전 데이터 {#casewhen-uc2-databefore}

| 제품 검색 방법 |
|----|
| 검색 p13_no |
| p13_yes 검색 |
| 검색 |
| 검색 세분화 p13_no |
| 검색 세분화 p13_yes |
| 검색 |
| 검색 리디렉션 p13_yes |
| search-redirect |
| 검색 |

{style="table-layout:auto"}

### 사용자 지정 필드 {#casewhen-uc2-customfield}

을(를) 정의합니다 `Product Finding Methods (new)` 사용자 지정 필드. 다음을 만듭니다 **[!UICONTROL ** CASE WHEN **]** 규칙 빌더의 규칙. 이러한 규칙은 이전 규칙의 가능한 모든 변형에 논리를 적용합니다 **[!UICONTROL **&#x200B;제품 검색 방법&#x200B;**]** 필드 값 `search` 및 `browse` 사용 **[!UICONTROL 구문을 포함합니다]** 기준.

![[!DNL Case When] 규칙 2](assets/case-when-2.png)

### 데이터 후 {#casewhen-uc2-dataafter}

| 제품 검색 방법(신규) |
|----|
| 검색 |
| 검색 |
| 검색 |
| 검색 |
| 검색 |
| 검색 |
| 검색 |
| 검색 |
| 검색 |

{style="table-layout:auto"}


## 사용 사례 3 {#casewhen-uc3}

여행 회사는 전체 여행 기간을 보고할 수 있도록 예약 여행에 대한 이동 기간을 버켓으로 설정하고 싶습니다.

가정:

- 조직에서 이동 기간을 숫자 필드로 수집 중입니다.
- 그들은 &#39;짧은 여행&#39;이라고 불리는 버킷에 1-3일 동안의 기간을 버킷하고 싶어한다
- 그들은 &#39;중간 여행&#39;이라고 불리는 버킷에 4-7일 동안의 기간을 버킷하고 싶어한다
- 그들은 &#39;긴 여행&#39;이라는 버킷에 8일 이상의 기간을 버킷하고 싶어한다
- 1일 동안 132번의 여행이 예약되었다
- 110번의 여행이 2일 동안 예약되었다
- 3일 동안 105번의 여행이 예약되었다
- 4일 동안 99번의 여행이 예약되었다
- 5일 동안 92번의 여행이 예약되었다
- 6일 동안 85번의 여행이 예약되었다
- 82번의 여행이 7일 동안 예약되었다
- 8일 동안 78번의 여행이 예약되었다
- 9일 동안 50번의 여행이 예약되었다
- 10일 동안 44번의 여행이 예약되었다
- 11일 동안 38번의 여행이 예약되었다
- 12일 동안 31번의 여행이 예약되었다

원하는 보고서는 다음과 같습니다.

| 이동 기간 유형 | 예약 |
|----|---:|
| 중간 여행 | 358 |
| 짧은 여행 | 347 |
| 긴 여행 | 241 |

{style="table-layout:auto"}

### 이전 데이터 {#casewhen-uc3-databefore}

| 이동 기간 |
|---:|
| 1 |
| 12 |
| 3 |
| 6 |
| 4 |
| 8 |
| 6 |
| 2 |
| 1 |
| 2 |
| 21 |
| 8 |

{style="table-layout:auto"}

### 사용자 지정 필드 {#casewhen-uc3-customfield}

을(를) 정의합니다 `Trip Duration (bucketed)` 사용자 지정 필드. 다음을 만듭니다 **[!UICONTROL ** CASE WHEN **]** 규칙 빌더의 규칙. 이 규칙은 이전 규칙을 버킷하는 논리를 적용합니다 **[!UICONTROL **&#x200B;이동 기간&#x200B;**]** 필드 값을 세 개의 값으로 설정합니다. `short trip`, `medium  trip`, 및 `long trip`.

![[!DNL Case When] 규칙 3](assets/case-when-3.png)


### 데이터 후 {#casewhen-uc3-dataafter}

| 이동 기간(그룹) |
|---|
| 짧은 여행 |
| 긴 여행 |
| 짧은 여행 |
| 중간 여행 |
| 중간 여행 |
| 긴 여행 |
| 중간 여행 |
| 짧은 여행 |
| 짧은 여행 |
| 짧은 여행 |
| 긴 여행 |
| 긴 여행 |

+++


<!-- FIND AND REPLACE -->

### [!DNL Find and Replace]

선택한 필드에서 모든 값을 찾은 다음 새 사용자 지정 필드에서 다른 값으로 대체합니다.

+++ 세부 사항

## 입력/연산자/출력 {#findreplace-io}

| 입력 데이터 유형 | 입력 | 포함된 연산자 | 출력 |
|---|---|---|---|
| <p>문자열</p> | <ul><li><span>&#39;바꿀 시기&#39; 필드 기준</span></li><li><span>&#39;다음으로 바꾸기&#39; 필드 값</span><ul><li><span>사용자 입력</span></li><li><span>별도의 필드</span></li></ul></li></ul> | <p><u>문자열</u></p><ul><li>모두 찾기 및 모두 바꾸기</li></ul> | <p>새 사용자 지정 필드</p> |

{style="table-layout:auto"}


## 사용 사례 {#findreplace-uc}

외부 마케팅 채널 보고서에 대한 잘못된 값(예: )을 받았습니다 `email%20 marketing` 대신 `email marketing`. 잘못된 형식의 값으로 인해 보고가 손상되므로 이메일의 수행 방식을 더 쉽게 파악할 수 있습니다. 바꾸려는 경우 `email%20marketing` with `email marketing`.

**원래 보고서**

| 외부 마케팅 채널 | 세션 |
|---|---|
| 이메일 마케팅 | 500 |
| email%20marketing | 24 |

{style="table-layout:auto"}

**기본 보고서**

| 외부 마케팅 채널 | 세션 |
|---|---|
| 이메일 마케팅 | 524 |


### 이전 데이터 {#findreplace-uc-databefore}

| 외부 마케팅 |
|----|
| 이메일 마케팅 |
| email%20marketing |
| 이메일 마케팅 |
| 이메일 마케팅 |
| email%20marketing |

{style="table-layout:auto"}

### 사용자 지정 필드 {#findreplace-uc-customfield}

을(를) 정의합니다 `Email Marketing (updated)` 사용자 지정 필드. 를 사용합니다 **[!UICONTROL 찾기 및 바꾸기]** 규칙을 정의하여, `email%20marketing` with `email marketing`.

![[!DNL Find and Replace] 규칙](assets/find-and-replace.png)

### 데이터 후 {#findreplace-uc-dataafter}

| 외부 마케팅<br/>(사용자 지정 필드) |
|----|
| 이메일 마케팅 |
| 이메일 마케팅 |
| 이메일 마케팅 |
| 이메일 마케팅 |
| 이메일 마케팅 |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### [!DNL Lookup]

해당 값으로 대체되는 조회 값 집합을 정의합니다.

+++ 세부 사항


## 입력/연산자/출력 {#lookup-io}

| 입력 데이터 유형 | 입력 | 포함된 연산자 | 출력 |
|---|---|---|---|
| <ul><li>문자열</li><li>숫자</li><li>날짜</li></ul> | <ul><li>Sing 필드</li><li>조회 파일<ul><li>키 열</li><li>새 필드 열</li></ul></li></ul> | <p>해당 사항 없음</p> | <p>새 사용자 지정 필드</p> |

{style="table-layout:auto"}


## 사용 사례 1 {#lookup-uc1}

에 대한 키 열이 포함된 CSV 파일이 있습니다 `hotelID` 및 `hotelID`: `city`, `rooms`, `hotel name`.
차원에서 호텔 ID를 수집하지만 `hotelID` 를 입력합니다.

**CSV 파일 구조 및 컨텐츠**

| hotelID | city | 객실 | 호텔 이름 |
|---|---|---:|---|
| SLC123 | 솔트레이크시티 | 40 | SLC 다운타운 |
| LAX342 | 로스 엔젤스 | 60 | LA 공항 |
| SFO456 | 샌프란시스코 | 75 | 마켓 스트리트 |

{style="table-layout:auto"}

**현재 보고서**

| 호텔 ID | 제품 보기 |
|---|---:|
| SLC123 | 200 |
| LX342 | 198 |
| SFO456 | 190 |

{style="table-layout:auto"}


**원하는 보고서**

| 호텔 이름 | 제품 보기 |
|----|----:|
| SLC 다운타운 | 200 |
| LA 공항 | 198 |
| 마켓 스트리트 | 190 |

{style="table-layout:auto"}

### 이전 데이터 {#lookup-uc1-databefore}

| 호텔 ID |
|----|
| SLC123 |
| LAX342 |
| SFO456 |

{style="table-layout:auto"}


### 사용자 지정 필드 {#lookup-uc1-customfield}

을(를) 정의합니다 `Hotel Name` 사용자 지정 필드. 를 사용합니다 **[!UICONTROL **&#x200B;조회&#x200B;**]** 함수를 사용하여 **[!UICONTROL **&#x200B;호텔 ID **]** 필드 및 를 새 값으로 바꿉니다.

![[!DNL Lookup] 규칙 1](assets/lookup-1.png)

### 데이터 후 {#lookup-uc1-dataafter}

| 호텔 이름 |
|----|
| SLC 다운타운 |
| LA 공항 |
| 마켓 스트리트 |

{style="table-layout:auto"}


## 사용 사례 2 {#lookup-uc2}

여러 페이지에 대한 친숙한 페이지 이름 대신 URL을 수집했습니다. 이렇게 혼합 값 컬렉션으로 인해 보고가 중단됩니다.

### 이전 데이터 {#lookup-uc2-databefore}

| 페이지 이름 |
|---|
| 홈 페이지 |
| 플라이트 검색 |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| 거래 및 오퍼 |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### 사용자 지정 필드 {#lookup-uc2-customfield}

을(를) 정의합니다 `Page Name (updated)` 사용자 지정 필드. 를 사용합니다 **[!UICONTROL **&#x200B;조회&#x200B;**]** 함수를 사용하여 기존 값을 조회할 수 있는 규칙을 정의합니다. **[!UICONTROL **&#x200B;페이지 이름&#x200B;**]** 필드 및 를 업데이트된 올바른 값으로 바꿉니다.

![[!DNL Lookup] 규칙 2](assets/lookup-2.png)

### 데이터 후 {#lookup-uc2-dataafter}

| 페이지 이름 (업데이트됨) |
|---|
| 홈 페이지 |
| 플라이트 검색 |
| 호텔 검색 |
| 패키지 검색 |
| 거래 및 오퍼 |
| 검토 |
| 견적 생성 |

+++

<!-- URL PARSE -->

### [!DNL URL Parse]

프로토콜, 호스트, 경로 또는 쿼리 매개 변수를 포함하여 URL의 다른 부분을 구문 분석합니다.

+++ 세부 사항

## 입력/연산자/출력 {#urlparse-io}

| 입력 데이터 유형 | 입력 | 포함된 연산자 | 출력 |
|---|---|---|---|
| <ul><li>문자열</li></ul> | <ul><li>Sing 필드</li><li>구문 분석 옵션<ul><li>프로토콜 가져오기</li><li>호스트 가져오기</li><li>경로 가져오기</li><li>쿼리 값 가져오기<ul><li>쿼리 매개변수</li></ul></li><li>해시 값 가져오기</li></ul></li></ul></li></ul> | <p>해당 사항 없음</p> | <p>새 사용자 지정 필드</p> |

{style="table-layout:auto"}


## 사용 사례 1 {#urlparse-uc1}

마케팅 채널의 규칙 세트의 일부로서 참조 URL의 참조 도메인만 사용할 수 있습니다.

### 이전 데이터 {#urlparse-uc1-databefore}

| 참조 URL |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### 사용자 지정 필드 {#urlparse-uc1-customfield}

을(를) 정의합니다  `Referring Domain` 사용자 지정 필드. 를 사용합니다 **[!UICONTROL ** URL 구문 분석&#x200B;**]** 함수에서 호스트를 가져올 규칙을 정의하는 함수입니다. **참조 URL** 새 사용자 지정 필드에 저장합니다.

![[!DNL Url Parse] 규칙 1](assets/url-parse-1.png)

### 데이터 후 {#urlparse-uc1-dataafter}

| 레퍼러 도메인 |
|----|
| www.google.com |
| duckduckgo.com |
| t.co |
| l.facebook.com |

{style="table-layout:auto"}


## 사용 사례 2 {#urlparse-uc2}

의 값을 사용하려는 경우 `cid` 파생 추적 코드 보고서 출력의 일부로서 페이지 URL에 있는 쿼리 문자열의 매개 변수.

### 이전 데이터 {#urlparse-uc2-databefore}

| 페이지 URL |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### 사용자 지정 필드 {#urlparse-uc2-customfield}

을(를) 정의합니다 `Query String CID` 사용자 지정 필드. 를 사용합니다 **[!UICONTROL ** URL 구문 분석&#x200B;**]** 페이지 URL에서 쿼리 문자열 매개 변수의 값을 가져올 규칙을 정의하고 `cid` 을 쿼리 매개 변수로 사용합니다. 출력 값은 새 사용자 정의 필드에 저장됩니다.

![[!DNL Url Parse] 규칙 2](assets/url-parse-2.png)

### 데이터 후 {#urlparse-uc2-dataafter}

| 쿼리 문자열 CID |
|----|
| abc123 |
| def123 |
| xyz123 |

{style="table-layout:auto"}

+++
