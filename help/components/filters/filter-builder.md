---
description: 필터 빌더는 컨테이너 계층 논리, 규칙 및 연산자를 기준으로 지표 Dimension, 필터 및 이벤트를 필터 방문자로 드래그하여 놓을 수 있는 캔버스를 제공합니다. 이 통합 개발 도구를 사용하여 방문과 이벤트 간에 방문자 특성 및 작업을 식별하는 간단하거나 복잡한 필터를 작성하고 저장할 수 있습니다.
title: 필터 빌드
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '2052'
ht-degree: 36%

---

# 필터 빌더

다음 [!UICONTROL 필터 빌더] 방문 및 이벤트 간에 방문자 특성 및 작업을 식별하는 간단하거나 복잡한 필터를 작성할 수 있습니다. 여기서는 계층 논리, 규칙 및 연산자에 따라 방문자를 필터링하기 위해 지표 차원, 이벤트 또는 기타 필터를 드래그 앤 드롭할 수 있는 캔버스를 제공합니다.

빠른 필터가 만들어진 프로젝트에만 적용되는 빠른 필터를 만드는 방법에 대한 자세한 내용은 다음을 참조하십시오. [빠른 필터](/help/components/filters/quick-filters.md).

## 필터 빌더 액세스

다음 방법 중 하나로 필터 빌더에 액세스할 수 있습니다.

* **Analytics 위쪽 탐색**: 클릭 **[!UICONTROL 분석]** > **[!UICONTROL 구성 요소]** > **[!UICONTROL 필터]**.
* **[!UICONTROL Analysis Workspace]**: Analysis Workspace에서 프로젝트를 열어 놓고 다음을 선택합니다. **[!UICONTROL + 구성 요소]** > **[!UICONTROL 필터 만들기]**.
* **[!UICONTROL Reports &amp; Analytics]**: 클릭 **[!UICONTROL 분석]** > **[!UICONTROL 보고서]**&#x200B;를 클릭하고 기존 보고서를 연 다음 **필터** 왼쪽 탐색 창에서 아이콘을 클릭한 다음 **[!UICONTROL 추가]**.
* **[!UICONTROL Report Builder]**: [Report Builder에서 필터 추가 또는 편집](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html?lang=ko-KR).

## 빌더 기준 개요 {#section_F61C4268A5974C788629399ADE1E6E7C}

규칙 정의 및 컨테이너를 추가하여 필터를 정의할 수 있습니다. 필터 빌더 액세스에 대한 자세한 내용은 [필터 빌더 액세스](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL 제목]**: 필터 이름을 지정합니다.
1. **[!UICONTROL 설명]**: 필터에 대한 설명을 제공합니다.
1. **[!UICONTROL 태그]**: [필터에 태그 지정](/help/components/filters/manage-filters.md) 기존 태그 목록에서 선택하거나 새 태그를 만들어 만듭니다.
1. **[!UICONTROL 정의]**: 여기에서 [필터 빌드 및 구성](/help/components/filters/filters-overview.md), 규칙 추가, 컨테이너 중첩 및 시퀀스 지정.
1. **[!UICONTROL 표시]**: (위쪽 컨테이너 선택기) 최상위 수준을 선택할 수 있습니다. [컨테이너](/help/components/filters/filters-overview.md) ( [!UICONTROL 개인], [!UICONTROL 세션], [!UICONTROL 이벤트]). 기본 최상위 수준 컨테이너는 이벤트 컨테이너입니다.
1. **[!UICONTROL 옵션]**: (톱니바퀴) 아이콘

   * **[!UICONTROL + 컨테이너 추가]**: 필터 정의에 새 컨테이너(최상위 컨테이너 아래)를 추가할 수 있습니다.
   * **[!UICONTROL 제외]**: 하나 이상의 차원, 필터 또는 지표를 제외하는 식으로 필터를 정의합니다.

1. **[!UICONTROL 차원]**: 구성 요소는 차원 목록 (주황색 사이드바)에서 드래그하여 놓습니다.
1. **[!UICONTROL 연산자]**: 선택한 연산자를 사용하여 값을 비교하고 제한할 수 있습니다.
1. **[!UICONTROL 값]**: 입력했거나 선택한 차원, 필터 또는 지표 값입니다.
1. **[!UICONTROL 속성 모델]**: 차원에만 사용할 수 있으며, 이 모델은 차원에서 필터링할 값을 결정합니다. Dimension 모델은 순차적 필터에서 특히 유용합니다.

   * **[!UICONTROL 반복]**  (기본값): 차원의 인스턴스와 지속적인 값을 포함합니다.
   * **[!UICONTROL 인스턴스]**: 차원의 인스턴스를 포함합니다.
   * **[!UICONTROL 비반복 인스턴스]**: 차원에 대한 고유한 인스턴스(비반복)를 포함합니다. 반복 인스턴스가 제외될 때 플로우에 적용되는 모델입니다.

   ![](assets/attribution-models.jpg)

   **예: 이벤트 필터. 여기서 eVar1 = A**

   | 예 | A | A | A (지속됨) | B | A | C |
   |---|---|---|---|---|---|---|
   | 반복 | X | X | X | - | X | - |
   | 인스턴스 | X | X | - | - | X | - |
   | 비반복 인스턴스 | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**: 컨테이너나 규칙 사이에 [!UICONTROL AND/OR/THEN] 연산자를 지정합니다. THEN 연산자를 사용하여 다음을 수행할 수 있습니다. [순차적 필터 정의](/help/components/filters/filters-overview.md).
1. **[!UICONTROL 지표]**: (녹색 사이드바) 지표 목록에서 드래그 앤 드롭한 지표입니다.
1. **[!UICONTROL 비교]** 연산자: 선택한 연산자를 사용하여 값을 비교하고 제한할 수 있습니다.
1. **[!UICONTROL 값]**: 입력했거나 선택한 차원, 필터 또는 지표 값입니다.
1. **[!UICONTROL X]**: (삭제) 이 필터 정의 부분을 삭제할 수 있습니다.
1. **[!UICONTROL Experience Cloud 게시]**: Experience Cloud에 Adobe Analytics 필터를 게시하면 의 마케팅 활동에 필터를 사용할 수 있습니다 [!DNL Audience Manager] 및 기타 활성화 채널에서 확인할 수 있습니다. [자세히 알아보기...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)
1. **[!UICONTROL 대상 라이브러리]**: Adobe의 대상 서비스는 방문자 데이터를 대상 필터로 변환하는 작업을 관리합니다. 이와 같이 대상을 만들고 관리하는 작업은 필터를 만들고 사용하는 것과 비슷하며, Experience Cloud에 대상 필터를 공유하는 기능이 추가되었다고 생각하면 됩니다. [자세히 알아보기...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)
1. **[!UICONTROL 검색]**: 차원, 필터 또는 지표 목록을 검색합니다.
1. **[!UICONTROL 차원]**: (목록) 확장할 헤더를 클릭합니다.
1. **[!UICONTROL 지표]**: 확장할 헤더를 클릭합니다.
1. **[!UICONTROL 필터]**: 확장할 헤더를 클릭합니다.
1. **[!UICONTROL 데이터 보기 선택기]**: 이 필터가 저장될 보고서 세트를 선택할 수 있습니다. 모든 데이터 보기에서 필터를 계속 활용할 수 있습니다.
1. **[!UICONTROL 필터 미리보기]**: 주요 지표를 미리 보기하여 유효한 필터가 있는지 여부와 필터의 폭이 얼마나 넓은지 확인할 수 있습니다. 이 필터를 적용할 경우 표시될 것으로 예상되는 데이터 세트 분류를 표시합니다. 3개의 동심원 및 목록을 표시하여 일치 항목 수 및 비율을 표시합니다. [!UICONTROL 이벤트], [!UICONTROL 개인], 및 [!UICONTROL 세션] 데이터 세트에 대해 실행되는 필터입니다. 이 차트는 필터 정의를 만들거나 변경한 직후에 업데이트됩니다.
1. **[!UICONTROL 제품 호환성]** Adobe Analytics : 제품 목록을 제공합니다(Analysis Workspace, [!UICONTROL Reports &amp; Analytics], Data Warehouse) 을 사용하여 만든 필터가 호환됩니다. 대부분의 필터는 모든 제품과 호환됩니다. 하지만 모든 연산자 및 차원이 모든 Analytics 제품 (특히 [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). 이 차트는 필터 정의를 변경한 직후에 업데이트됩니다.
1. **[!UICONTROL 저장]** 또는 **[!UICONTROL 취소]**: 필터를 저장하거나 취소합니다. 클릭 후 **[!UICONTROL 저장]**&#x200B;를 클릭하면 필터를 관리할 수 있는 필터 관리자로 이동됩니다.

포함된 날짜 범위가 있는 필터는 Analysis Workspace에서 와 [!UICONTROL Reports &amp; Analytics]: Workspace에서 포함된 날짜 범위가 있는 필터가 패널 날짜 범위를 무시합니다. 대조적으로, [!UICONTROL Reports &amp; Analytics] 보고서 날짜 범위와 필터의 포함된 날짜 범위의 교차 날짜를 제공합니다.

## 필터 구축 {#build-filters}

1. 왼쪽 창에서 로 Dimension, 필터 또는 지표 이벤트 를 드래그하기만 하면 됩니다. [!UICONTROL 정의] 필드.

   ![](assets/drag_n_drop_dimension.png)

1. 드롭다운 메뉴에서 [연산자](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html)를 설정합니다.
1. 선택한 항목에 대한 값을 입력하거나 선택합니다.
1. 필요한 경우 **[!UICONTROL And]**, **[!UICONTROL Or]** 또는 **[!UICONTROL Then]** 규칙을 사용하여 컨테이너를 더 추가합니다.
1. 컨테이너를 배치하고 규칙을 설정한 후에는 오른쪽 상단의 유효성 검사 차트에서 필터 결과를 확인합니다. 유효성 검사기는 사용자가 만든 필터와 일치하는 페이지 보기, 방문 및 고유 방문자의 비율과 절대 수를 나타냅니다.
1. 아래 **[!UICONTROL 태그]**, [태그](/help/components/filters/manage-filters.md) 기존 태그를 선택하거나 새 태그를 만들어 컨테이너에 추가합니다.
1. 클릭 **[!UICONTROL 저장]** 필터를 저장합니다.

   다음으로 이동되었습니다. [필터 관리자](/help/components/filters/manage-filters.md)를 사용하여 다양한 방식으로 필터에 태그를 지정하고, 공유하고, 관리할 수 있습니다.

## 컨테이너 추가 {#section_1C38F15703B44474B0718CEF06639EFD}

[컨테이너 프레임워크를 작성한 다음](/help/components/filters/filters-overview.md) 사이에 논리 규칙 및 연산자를 배치할 수 있습니다.

1. 클릭 **[!UICONTROL 옵션 > 컨테이너 추가]**.

   새 항목 [!UICONTROL **이벤트**] 컨테이너 없이 열림 [!UICONTROL **이벤트**] (페이지 보기) 식별됨.

   ![](assets/new_container.png)

1. 필요에 따라 컨테이너 유형을 변경합니다.
1. 왼쪽 창에서 컨테이너로 Dimension, 필터 또는 이벤트를 드래그합니다.
1. 정의 상단에 있는 최상위 수준 **[!UICONTROL 옵션]** > **[!UICONTROL 컨테이너 추가]** 버튼에서 계속해서 새 컨테이너를 추가하거나 컨테이너 내에 컨테이너를 추가하여 논리를 중첩합니다.

   **또는**

   하나 이상의 규칙을 선택하고 **[!UICONTROL 옵션]** > **[!UICONTROL 선택에서 컨테이너 추가]**&#x200B;를 클릭합니다. 이렇게 하면 선택 영역이 별도의 컨테이너로 바뀝니다.

## 날짜 범위 사용 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

진행 중인 캠페인 또는 이벤트에 대한 질문에 답변하는 순서로 롤링 날짜 범위를 포함하는 필터를 빌드할 수 있습니다.

예를 들어 &quot;지난 60일 동안 구매한 모든 사람&quot;을 포함하는 필터를 쉽게 작성할 수 있습니다.

세션 컨테이너를 만들고 그 안에 을(를) 추가합니다. [!UICONTROL 지난 60일] 시간 범위 및 지표 [!UICONTROL 주문이 1보다 크거나 같음], AND 연산자 사용.

다음은 필터에서 롤링 기간 사용하기에 대한 비디오입니다.

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## 스택 필터 {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

스택 필터는 &#39;and&#39; 연산자를 사용하여 각 필터에서 기준을 조합한 다음 조합된 기준을 적용하는 방식으로 작동합니다. Workspace 프로젝트에서 직접 또는 필터 빌더에서 수행할 수 있습니다.

예를 들어 &quot;휴대폰 사용자&quot; 필터와 &quot;미국 지리&quot; 필터를 스택하면 미국의 휴대폰 사용자에 대한 데이터만 반환됩니다.

이러한 필터를 필터 라이브러리에 포함할 수 있는 기본 구성 요소 또는 모듈로 간주하여 사용자가 필요할 때 사용할 수 있습니다. 이를 통해 필요한 필터의 수를 획기적으로 줄일 수 있습니다. 예를 들어 40개의 필터가 있다고 가정해 보겠습니다.

* 다른 국가의 휴대폰 사용자를 위한 20개 세그먼트 (US_mobile, Germany_mobile, France_mobile, Brazil_mobile 등)
* 다른 국가의 태블릿 사용자를 위한 20개 세그먼트 (US_tablet, Germany_tablet, France_tablet, Brazil_tablet 등)

필터 스택을 사용하여 필터 수를 22개로 줄이고 필요에 따라 스택할 수 있습니다. 다음 필터를 만들어야 합니다.

* 모바일 사용자를 위한 하나의 필터
* 태블릿 사용자를 위한 필터 1개
* 다른 지역을 위한 20개 필터

>[!NOTE]
>
>2개의 필터를 스택할 때 기본적으로 AND 문으로 연결됩니다. 이를 OR 문으로 변경할 수 없습니다.

1. 필터 빌더로 이동합니다.

1. 필터의 제목과 설명을 입력합니다.

1. 클릭 **[!UICONTROL 필터 표시]** 왼쪽 탐색 영역에 필터 목록을 표시합니다.

1. 스택할 필터를 필터 정의 캔버스로 드래그합니다.

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

## 템플릿 필터링 {#concept_5098446CC78D441E93B8E4D1D1EA6558}

필터 템플릿은 &quot;처음 방문&quot; 또는 &quot;모바일 장치에서 방문&quot;과 같은 일반적인 필터 사용 사례에 대해 제공됩니다. Workspace 프로젝트 및 필터 빌더에서 새 필터의 빌딩 블록으로 사용할 수 있습니다.

템플릿은 Adobe &quot;A&quot; 로고로 표시됩니다. 템플릿 샘플은 아래에 나와 있습니다.

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 템플릿 이름 </th> 
   <th colname="col2" class="entry"> 정의 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 장바구니 포기 </td> 
   <td colname="col2">장바구니에 품목을 추가했지만 아직 주문하지 않은 방문자의 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 이 순차적 필터에 대한 규칙은 다음과 같습니다. <p> 장바구니 추가는 null입니다. </p> <p>Then </p> <p>주문은 0입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 최초 방문 </td> 
   <td colname="col2">최대 [1]회 방문한 방문자에 대한 데이터를 봅니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>방문 번호가 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 비구매자 </td> 
   <td colname="col2">주문 이벤트에 참가하지 않은 방문자에 대한 데이터를 봅니다. 필터 정의에서 이 컨테이너는 방문자입니다. 이 필터는 제외 논리를 사용합니다. 규칙: <p>주문은 null이 아닙니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 단일 페이지 방문 아님 (바운스 아님) </td> 
   <td colname="col2">두 번 이상 방문한 방문자의 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문자입니다. 이 필터는 제외 논리를 사용합니다. 규칙: <p>단일 액세스가 null이 아닙니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 유료 검색 </td> 
   <td colname="col2">유료 검색에서 시작한 방문자의 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>유료 검색은 1입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 구매자 </td> 
   <td colname="col2">주문 이벤트에 참가한 방문자에 대한 데이터를 봅니다. 필터 정의에서 이 컨테이너는 방문자입니다. 규칙: <p>주문은 null이 아닙니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 재방문 </td> 
   <td colname="col2">1번 이상 방문한 방문자의 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>방문 번호가 1보다 큼. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 단일 페이지 방문 횟수 </td> 
   <td colname="col2"> 해당 방문 중에 여러 페이지 보기를 제출할 수 있더라도 단일 페이지 값을 열람한 방문의 데이터를 표시합니다. 종료 링크 이벤트가 있는 단일 페이지 방문이 필터에 포함됩니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>단일 페이지 방문 횟수는 1입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 열람되었지만 장바구니에 추가되지 않은 제품 </td> 
   <td colname="col2">제품을 열람했지만 장바구니에 추가하지 않은 방문자의 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 이 순차적 필터에 대한 규칙은 다음과 같습니다. <p>제품 보기가 null이 아닙니다. </p> <p>Then </p> <p> 장바구니 추가는 0입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 캠페인에서 방문 </td> 
   <td colname="col2">캠페인에서 참조한 방문자에 대한 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>추적 코드가 null이 아닙니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 모바일 기기로부터 찾아온 방문 </td> 
   <td colname="col2">모바일 디바이스를 사용한 방문자의 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>모바일 디바이스가 Null이 아닙니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 자연어 검색으로 찾아온 방문 </td> 
   <td colname="col2">유료 검색에서 시작하지 않은 방문자의 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>유료 검색은 0입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 비모바일 디바이스에서 시작된 방문 </td> 
   <td colname="col2">모바일 디바이스를 사용하지 않은 방문자의 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 이 필터는 제외 논리를 사용합니다. 규칙: <p>모바일 디바이스 유형이 휴대 전화와 같음 </p> <p>또는 </p> <p>모바일 디바이스 유형이 태블릿과 같음. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 휴대폰에서 시작된 방문 </td> 
   <td colname="col2">휴대폰을 사용한 방문자의 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>디바이스 유형이 휴대폰입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 검색 엔진에서 시작된 방문 </td> 
   <td colname="col2">검색 엔진에서 참조한 방문자에 대한 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>레퍼러 유형이 검색 엔진입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 소셜 사이트에서 찾아온 방문 </td> 
   <td colname="col2">소셜 사이트에서 참조한 방문자에 대한 데이터를 봅니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>레퍼러 유형이 소셜 네트워크. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 태블릿에서 시작된 방문 </td> 
   <td colname="col2">태블릿을 사용한 방문자의 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>디바이스 유형이 태블릿입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 방문자 ID를 갖는 방문 </td> 
   <td colname="col2">영구적 쿠키가 필요한 사이트의 방문자에 대한 데이터를 표시합니다. 필터 정의에서 이 컨테이너는 방문입니다. 규칙: <p>영구적 쿠키는 1입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>