---
description: 프로젝트를 만들고 구성 요소(차원, 지표, 세그먼트 및 날짜 범위)를 자유 형식 패널에 추가합니다.
keywords: Analysis Workspace
title: 작업 공간 프로젝트 만들기
topic: Reports and analytics
uuid: c1def77a-a76e-4699-9feb-1ede5b70b7ba
translation-type: tm+mt
source-git-commit: e004a2a8ec24113ae8b62a9d30c10fe0eb763460
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 99%

---


# 작업 공간 프로젝트 만들기

프로젝트를 만들고 구성 요소(차원, 지표, 세그먼트 및 날짜 범위)를 자유 형식 패널에 추가합니다.

이 문서는 Analysis Workspace 인터페이스 요소에 익숙해지도록 하고 프로젝트를 만드는 방법을 보여줍니다.

## 프로젝트를 만듭니다.

1. 프로젝트를 생성하고 조정하는 사용자 권한을 지정합니다.

   Analysis Workspace 프로젝트를 만들거나 조정하기 전에 관리자가 **[!UICONTROL Analysis Workspace에서 프로젝트 만들기 / 조정]** 권한이 활성화된 그룹이나 **[!UICONTROL 모든 보고서 액세스]** 사용자 그룹에 사용자를 추가해야 합니다. ( **[!UICONTROL 관리]** > **[!UICONTROL 사용자 관리]** > [그룹](https://docs.adobe.com/content/help/ko-KR/analytics/admin/user-product-management/user-groups/groups.html)).

1. [!DNL Experience Cloud]에서 **[!UICONTROL Analytics]** > **[!UICONTROL 작업 공간]**&#x200B;를 클릭합니다.

   ![](assets/analysis_workspace_menu.png)

   또는, 슬래시(/)를 입력하여 보고서 검색 막대를 연 다음, *`workspace`*&#x200B;를 입력합니다.

   ![](assets/analysis-app-search.png)

1. **[!UICONTROL 새 프로젝트 만들기]**&#x200B;를 클릭합니다.

   프로젝트를 다음 중 어느 방법으로 작성할지 선택할 수 있습니다.

* 빈 프로젝트(기본값). 자세한 내용은 다음을 참조하십시오.
* 표준 템플릿. 이러한 템플릿은 Adobe가 만들어 특별 배송합니다. 자세한 내용은 [템플릿](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)을 참조하십시오.
* 사용자 지정 템플릿. 이러한 템플릿은 관리자 권한을 가진 사용자가 작성합니다. 자세한 내용은 [템플릿](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)을 참조하십시오.

   ![](assets/start_modal.png)

1. 빈 프로젝트에서 프로젝트를 생성하려면 **[!UICONTROL 빈 프로젝트]**&#x200B;를 클릭하십시오.

   * 그런 다음 **[!UICONTROL 만들기]**&#x200B;를 클릭하거나,
   * 간단히 **[!UICONTROL Enter를 클릭합니다]**.

   자유 형식 패널과 데이터 테이블 시각화를 보여주는 빈 프로젝트가 표시됩니다.

   ![](assets/fa_project_new.png)

   >[!NOTE]
   >
   >프로젝트에 포함된 일부 구성 요소(지표/차원)만 보고서 세트에 포함된 경우 프로젝트를 로드할 때(또는 보고서 세트로 전환할 때) &quot;호환되지 않는 보고서 세트&quot; 메시지가 표시되는 경우가 있습니다. 호환되지 않는 구성 요소 목록을 볼 수 있으므로 메시지가 표시되는 이유를 알 수 있습니다.

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/analysis-workspace-components.md"  > 구성 요소</a> </td> 
   <td colname="col2"> <p>프로젝트로 드래그할 수 있는 차원, 지표, 세그먼트 및 날짜 범위입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > 시각화</a> </td> 
   <td colname="col2"> <p>패널이나 인터페이스의 프로젝트 영역에 드래그할 수 있는 항목입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md"  > 자유 형식 패널 </a> </td> 
   <td colname="col2"> <p>Analysis Workspace에서 상호 작용하는 캔버스 또는 작업 공간입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 프로젝트를 저장하십시오. 프로젝트 이름을 지정하고 (선택 사항이지만 유용한) 설명을 제공하고 프로젝트에 태그를 달고(선택 사항) **[!UICONTROL 프로젝트 저장을 클릭하십시오]**.

   ![](assets/save_project.png)

1. 이제 시각화 또는 패널을 마우스 오른쪽 단추로 클릭하고 복사한 다음, 복사한 요소를 프로젝트 내의 다른 위치 또는 다른 프로젝트에 붙여넣을(&quot;삽입&quot;) 수 있습니다.

   이 기능을 사용하면 다른 프로젝트에 복사할 수 있는 &quot;문서 블록&quot;(사전 정의된 시각화/패널)을 작성하여 비즈니스와 관련된 데이터로 빠르게 시작할 수 있습니다.

   >[!NOTE]
   >
   >이제 인트라 링크는 복사/다른 이름으로 저장하면 복사한 원래 프로젝트가 아닌, 활성 상태인 프로젝트를 기준으로 합니다.

## 구성 요소 및 시각화 추가 {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. *`components`* 및 *`visualizations`*&#x200B;를 프로젝트에 드래그하여 프로젝트를 작성합니다.

   **구성 요소**

   구성 요소 도구 모음에는 가장 자주 사용하는 검색 가능한 차원, 지표, 세그먼트 및 날짜 범위가 표시됩니다.

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 구성 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 차원(주황색) </td> 
   <td colname="col2"> <p>프로젝트 수준에서 적용합니다. </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>Prop#, eVar# 및 event#가 차원 이름에 추가되고 해당 숫자를 검색할 수 있습니다. 예: 왼쪽 레일에 "내부 캠페인"이 "내부 캠페인(evar2)"으로 표시됩니다. </p> <p> 표에 prop, eVar 및 이벤트 번호가 표시되지 않습니다(제목을 짧게 유지하기 위해). </p> <p>일부 특별 차원을 자유 형식 테이블에 드래그하거나 왼쪽 레일에서 볼 때 이 차원들을 위한 기본 정렬 순서가 있습니다. 예를 들어, "시간"을 테이블에 놓거나 왼쪽 레일에서 보면, 오전 12시부터 오후 11시까지 정렬됩니다. 지표 열을 기준으로 정렬할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 지표(녹색) </td> 
   <td colname="col2"> <p>프로젝트 수준에서 적용합니다. </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> <span class="term"> 발생 횟수</span>는 데이터 테이블용 기본 지표입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 세그먼트(파란색) </td> 
   <td colname="col2"> <p>패널 수준에서만 드래그할 수 있지만, 데이터 테이블에서 인라인 세그먼트를 만들 수 있습니다. </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>자세한 내용은 <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > 세그먼트 </a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 날짜 범위 및 세부기간(자주색) </td> 
   <td colname="col2"> <p>패널 수준에서 드래그할 수 있습니다. 날짜 범위를 구성할 때 [일정]에서 프로젝트를 만들 수 있습니다. </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[시각화](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)**

[!UICONTROL 시각화] 패널은 표준 분석 그래프, 차트, 도넛, 데이터 테이블, [집단](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) 테이블, 벤 다이어그램 등을 제공합니다. 여러 시각화를 프로젝트로 드래그하여 놓을 수 있습니다.

![단계 결과](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. 단계. 

## 마우스 오른쪽 단추 클릭 메뉴를 사용하여 데이터 사용자 지정 {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

마우스 오른쪽 버튼 클릭 메뉴를 사용하면 마우스 오른쪽 버튼으로 클릭하는 테이블의 셀에 따라 다음 작업을 수행할 수 있습니다.

![단계 결과](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 작업 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > 기간 열 추가</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > 기간 비교</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>클립보드에 복사 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>선택 항목 삭제 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md"  > 선택 항목으로 경고 만들기</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md"  > 분류</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">차원 </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">지표 </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">세그먼트 </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">시간 </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > 시각화</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/curate-share/download-send.md"  > CSV로 다운로드</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/home.md"  > 트렌드 선택</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > 선택 항목에서 세그먼트 만들기</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md"  > 세그먼트 비교에서 실행</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 선택한 행만 표시 </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 모든 행 표시 </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

행 복사 및 선택에 대한 자세한 내용은 [Analysis Workspace에서 사용할 수 있는 키보드 및 마우스 상호 작용](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)을 참조하십시오.
