---
title: 가이드 분석 개요
description: 제품 팀이 고품질 통찰력을 신속하게 얻을 수 있도록 하는 Customer Journey Analytics의 데이터 분석 방법입니다.
keywords: 제품 분석
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 06a0c35bcb256175bf7aa514dad89d1f3547e18d
workflow-type: tm+mt
source-wordcount: '1823'
ht-degree: 36%

---

# 가이드 분석 개요

안내식 Customer Journey Analytics을 통해 마케팅, 제품, 분석가에 이르기까지 사용자는 마케팅 채널의 크로스 채널 데이터를 기반으로 구축된 안내식 워크플로우를 통해 고품질 데이터와 고객 여정에 대한 통찰력을 자체 제공할 수 있습니다. Analysis Workspace 및 모바일 스코어카드와 유사하게 안내식 분석은 [데이터 보기](/help/data-views/data-views.md)의 데이터를 사용하며, 데이터 보기에서는 [연결](../connections/overview.md)을 통해 Adobe Experience Platform의 데이터를 참조합니다. 안내식 분석에서 만든 대다수의 보고서는 추가 연구를 위해 Analysis Workspace로 원활하게 전송할 수 있습니다.

>[!NOTE]
>
>안내식 분석과 Analysis Workspace 간의 용어(세그먼트, 필터 등)의 차이에 대한 자세한 내용은 [FAQ](faq.md)를 참조하세요.


다음 안내식 분석을 사용할 수 있습니다.

| 아이콘 | 분석 | 설명 |
| :----:|--- | --- |
| ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) | [활성 증가](types/active-growth.md) | 신규, 유지, 복귀 또는 휴면 상태를 식별합니다. |
| ![전환 트렌스](/help/assets/icons/ConversionTrends.svg) | [전환 추세](types/conversion-trends.md) | 시간 경과에 따른 전환율 변화를 추적합니다. |
| ![참여 그래프](/help/assets/icons/EngagementGraph.svg) | [참여](types/engagement.md) | 기능 참여의 폭과 깊이를 이해합니다. |
| ![처음 사용](/help/assets/icons/FirstUse.svg) | [첫 번째 사용 영향](types/first-use-impact.md) | 주요 지표에 대한 최초 기능 사용의 영향을 측정합니다. |
| ![Histogram](/help/assets/icons/Histogram.svg) | [빈도](types/frequency.md) | 사용 빈도로 참여도를 측정합니다. |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [단계](types/funnel.md) | 단계 간 전환율을 비교합니다. |
| ![NetGrowth](/help/assets/icons/NetGrowth.svg) | [순성장](types/net-growth.md) | 사용자가 증가하고 있습니까, 감소하고 있습니까? |
| ![릴리스](/help/assets/icons/Release.svg) | [릴리스 영향](types/release-impact.md) | 릴리스 전후 동일한 기간 동안의 성능을 비교합니다. |
| ![유지](/help/assets/icons/Retention.svg) | [유지](types/retention.md) | 사용자의 지속적인 재방문 습관을 측정합니다. |
| ![타임라인](/help/assets/icons/Timeline.svg) | [타임라인](types/timeline.md) | 세션 활동에서의 패턴을 탐색합니다. |
| ![그래프 트렌드](/help/assets/icons/GraphTrend.svg) | [트렌드](types/trends.md) | 시간 경과에 따른 사용자 참여를 측정합니다. |



## 액세스

Customer Journey Analytics 홈페이지에서 안내가 있는 분석에 액세스할 수 있습니다.

1. 홈페이지에서 **[!UICONTROL 분석 가이드]**&#x200B;를 선택하면 [트렌드 분석](types/trends.md)으로 바로 이동합니다.

   ![Landing page tile](assets/landing-page-tile.png){style="border:1px solid gray"}

1. **[!UICONTROL 새로 만들기]**&#x200B;를 선택하여 다양한 보기 옵션을 확인하고 분석을 위한 다양한 시작점을 선택할 수 있습니다.

   ![Create a new modal](assets/create-new-modal.png){style="border:1px solid gray"}

Analysis Workspace 프로젝트 내에서 안내식 분석에 액세스할 수도 있습니다.

1. 홈 페이지에서 **[!UICONTROL 빈 프로젝트]**&#x200B;를 선택하여 빈 Workspace 프로젝트를 만듭니다.

   ![Create blank project](assets/blank-project.png){style="border:1px solid gray"}

1. 왼쪽 레일에서 ![Guided analysis](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL 가이드 분석]**&#x200B;을 선택합니다.

   ![Workspace left rail](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. 새 분석을 Workspace 캔버스로 드래그한 다음 **[!UICONTROL 만들기]**&#x200B;를 선택하여 원하는 분석을 생성합니다(예: **[!UICONTROL 트렌드 만들기]**). **[!UICONTROL 저장됨]** 섹션 아래에서 기존 분석을 Workspace 캔버스로 드래그할 수도 있습니다.

   ![Create panel](assets/create-guided-analysis-panel.gif)

## 인터페이스

안내식 분석을 위한 인터페이스는 질문과 답변 형식을 따릅니다. 쿼리 레일에서 질문을 작성하면 글로 작성된 인사이트, 차트 및 표를 통해 답변을 얻을 수 있습니다. 그런 다음 분석 및 시각화 설정을 사용하여 다음 질문을 할 수 있습니다.

가이드 분석에서는 다음 UI 요소를 사용합니다.

| 인터페이스 미리보기 | UI 요소 | 설명 |
| --- | --- | --- |
| ![Query rail](assets/query-rail.png){style="border:1px solid gray"} | **[!UICONTROL Query rail]** | 분석을 구성하는 원하는 구성 요소(이벤트, 속성 및 세그먼트)를 선택하여 *질문*&#x200B;을 구성하십시오. 다음 옵션은 모든 분석에서 사용할 수 있으며, 뷰별로 추가 설정을 사용할 수 있습니다. <ul><li>**보기**: 새 분석으로 전환하려면 옵션에서 선택하십시오. 쿼리 선택 사항은 새 분석에 대해 허용된 제한 내에서 유지됩니다.</li><li>**이벤트**: 측정하려는 이벤트입니다. 각 분석에서는 구성할 수 있는 이벤트 수에 대해 서로 다른 제한을 적용합니다.  이벤트에는 **[!UICONTROL 시작 및 반환 이벤트]**, **[!UICONTROL 단계]** 또는 **[!UICONTROL 주요 지표]** 레이블이 지정됩니다. 이벤트는 분석에서 1, 2, ...<br/>새 이벤트를 추가하려면 ![추가](/help/assets/icons/Add.svg) **[!UICONTROL 이벤트 추가]**&#x200B;를 선택합니다.</li><li>**[!UICONTROL 요소]**: 사용 가능한 경우 다음 이후 날짜 및 첫 번째 이벤트와 같은 요소를 지정할 수 있습니다.</li><li>**다음 값으로 계산**: 선택한 이벤트에 적용할 계산 메서드입니다. 드롭다운 메뉴에서 을(를) 선택합니다.</li><li>**세그먼트**: 측정하려는 세그먼트입니다. 각 분석에서는 구성할 수 있는 세그먼트 수에 대해 서로 다른 제한을 적용합니다. 세그먼트는 분석에서 A, B, ...<br/>새 세그먼트를 추가하려면 ![추가](/help/assets/icons/Add.svg) **[!UICONTROL 세그먼트 추가]**&#x200B;를 선택합니다.</li><li>**[!UICONTROL 분류]**: 사용 가능한 경우 분석에 적용할 분류입니다.</li></ul>일부 설정에서는 추가 구성을 사용할 수 있습니다.<ul><li>**필터**: ![필터](assets/filter.png)를 사용하여 특정 차원별로 이벤트 또는 세그먼트 범위를 좁힙니다. 차원을 선택하면 표준 필터 기준(예: **[!UICONTROL 같음]**, **[!UICONTROL 포함]** 또는 **[!UICONTROL 다음으로 끝남]**)과 상위 1000개 차원 값을 모두 사용할 수 있습니다.<br/>필터를 추가하려면 ![필터](/help/assets/icons/Filter.svg)를 선택하십시오.<br/>필터를 제거하려면 ![제거](/help/assets/icons/Remove.svg)를 선택하십시오.</li><li>**추가 작업**: 다음과 같은 작업을 선택하려면 ![추가](/help/assets/icons/More.svg)를 사용합니다.<ul><li>![이름 바꾸기](/help/assets/icons/Rename.svg) **[!UICONTROL 이름 바꾸기]**: 이벤트 또는 세그먼트의 이름을 바꿉니다.</li><li>![복제](/help/assets/icons/Duplicate.svg) **[!UICONTROL 복제]**: 이벤트 또는 세그먼트를 복제합니다.</li><li>![삭제](/help/assets/icons/Delete.svg) **[!UICONTROL 제거]**: 이벤트, 세그먼트 또는 분류를 제거합니다.</li><li>![세그먼트 편집](/help/assets/icons/Edit.svg) **[!UICONTROL 세그먼트 편집]**: [필터 빌더](/help/components/filters/filter-builder.md)에서 세그먼트를 편집하려면</li><li>![시작](/help/assets/icons/Star.svg) **[!UICONTROL 즐겨찾기에 추가]**: [필터 관리자](/help/components/filters/manage-filters.md)의 즐겨찾기 필터 목록에 세그먼트를 추가합니다.</li><li>![SaveAsFloppy](/help/assets/icons/SaveAsFloppy.svg) **[!UICONTROL 다른 이름으로 저장]**: 세그먼트를 새 구성 요소로 저장합니다. **[!UICONTROL 구성 요소에 세그먼트 저장]** 대화 상자에서 세그먼트 이름과 설명을 지정할 수 있습니다. ![StarOutline](/help/assets/icons/StarOutline.svg)을(를) 선택하여 새 세그먼트를 즐겨찾기로 표시할 수 있습니다. 세그먼트를 새 필터로 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택하세요.</li><li>![링크](/help/assets/icons/Link.svg) **[!UICONTROL 시작 및 반환 이벤트 연결]**.: [유지](types/retention.md) 분석에서 시작 및 반환 이벤트를 연결합니다.</li><li>![연결 해제](/help/assets/icons/Unlink.svg) **[!UICONTROL 시작 및 이벤트 연결 해제]**: [유지](types/retention.md) 분석에서 시작 및 이벤트 연결을 해제하고 반환합니다.</li></ul></li></ul> |
| ![Chart](assets/chart.png){style="border:1px solid gray"} | **[!UICONTROL Chart]** | 쿼리 레일 및 설정의 입력을 기반으로 반환된 데이터의 시각화입니다. 표시되는 시각화는 차트 위의 보기 및 설정에 따라 달라집니다. 차트에는 다음도 포함됩니다. <ul><li>**도구 설명**: 차트 데이터 포인트를 마우스로 가리키면 추가 정보가 포함된 도구 설명이 표시됩니다.</li><li>**범례**: 차트 범례 시리즈를 마우스로 가리키면 가능한 경우 정의를 보고, 해당 시리즈에 초점을 맞추고, 다른 시리즈를 일시적으로 숨길 수 있습니다. 계열을 숨기려면 범례에서 계열을 선택합니다.</li><li>**주석**: 해당되는 [주석](../components/annotations/overview.md)이 시각화와 범례 사이에 표시됩니다. 주석의 구성된 색상이 적용된 ![Annotation icon](assets/annotation.png) 아이콘으로 표시됩니다. 시간 경과에 따른 데이터를 표시하는 분석은 ![주석 아이콘](assets/annotation.png) 아이콘을 구성된 날짜 또는 날짜 범위 아래에 배치합니다. 시간 경과에 따른 데이터를 표시하지 않는 분석은 차트의 오른쪽 아래 모서리에 ![주석 아이콘](assets/annotation.png) 아이콘을 표시합니다.</li><li>**작업 선택**: 데이터 포인트를 선택하여 사용 가능한 다음 작업을 표시합니다. 옵션으로는 **세그먼트 저장** 등이 있습니다.</li></ul> |
| ![Table](assets/table.png){style="border:1px solid gray"} | **[!UICONTROL Table]** | 쿼리 레일 및 설정의 입력을 기반으로 반환된 데이터의 테이블 표현입니다. 참조용으로 이벤트(1, 2, ...) 및 세그먼트 식별자(A, B, ...)를 사용하는 테이블의 행. 표의 열은 차트 위의 분석에 따라 다릅니다. 이 표에는 각 행에 대해서도 다음이 포함됩니다. <ul><li>**작업 선택**: ![숨기기 아이콘 표시](assets/hide-in-chart.png)를 전환하여 행에 대한 차트 계열을 숨기거나 표시합니다. 추가 작업을 보려면 ![자세히](/help/assets/icons/More.svg)를 선택하십시오. 옵션으로는 **세그먼트 저장** 등이 있습니다.</li></ul> |
| ![Visualization settings](assets/visualization-settings.png){style="border:1px solid gray"} | **[!UICONTROL Visualization settings]** | 차트 위의 옵션으로서 이를 통해 다음 질문을 하고 차트와 테이블이 데이터를 반환하는 방식을 사용자 정의할 수 있습니다. 다음 옵션은 모든 분석에서 사용할 수 있으며, 추가 설정은 분석별로 사용할 수 있습니다. <ul><li>![GraphTrend](/help/assets/icons/GraphTrend.svg) **차트 설정**: 차트와 표에 표시되는 내용을 미세 조정하십시오. 사용 가능한 옵션은 선택한 분석에 따라 다릅니다.</li><li>![레이어](/help/assets/icons/Layer.svg) **오버레이 설정**: 오버레이를 추가합니다. 사용 가능한 옵션은 선택한 분석에 따라 다릅니다.</li><li>![버킷](/help/assets/icons/Bucket.svg) **[!UICONTROL 버킷 설정]**: 자동 버킷 또는 사용자 지정 버킷 설정을 데이터에 적용합니다. 사용 가능한 옵션은 선택한 분석에 따라 다릅니다.<li>![DataCorrelated](/help/assets/icons/DataCorrelated.svg) **[!UICONTROL 설정 비교]**: 데이터를 특정 데이터 범위와 비교합니다. 사용 가능한 옵션은 선택한 분석에 따라 다릅니다.</li><li>![단계](/help/assets/icons/Footsteps.svg) **[!UICONTROL 표시 설정]**: 데이터를 표시하는 방법을 선택하십시오. 사용 가능한 옵션은 선택한 분석에 따라 다릅니다.<li>![일정](/help/assets/icons/Calendar.svg) **날짜 범위**: 분석의 날짜 범위를 결정할 수 있는 일정 선택기입니다. 일별, 주별 또는 월별 분석 등 트렌드 분석 간격을 선택할 수도 있습니다.</li><li>![LightBulb](/help/assets/icons/LightBulb.svg) **인사이트**: 표시되는 분석에 따른 상황별 인사이트. 이러한 인사이트에는 현재 분석에 대한 관찰 내용이 담겨 있습니다. 제공된 인사이트가 여러 개인 경우 오른쪽에 있는 화살표를 사용하여 볼 수 있습니다. 오른쪽 상단에 있는 전구 아이콘을 사용하여 이 상자의 표시 여부를 토글할 수 있습니다.</li></ul> |
| ![Menu](assets/menu.png){style="border:1px solid gray"} | **[!UICONTROL 메뉴]**<br/>안내식 분석 프로젝트에서 사용 가능 | 분석을 위해 중요한 작업을 제공하는 안내식 분석 프로젝트의 오른쪽 상단에 있는 명령입니다.<ul><li>![데이터](/help/assets/icons/Data.svg) ***데이터 보기의 이름***: 분석에서 사용하는 데이터 보기를 변경합니다. 데이터 보기를 변경하면 쿼리 레일에서 사용 가능한 구성 요소도 변경됩니다.</li><li>![링크](/help/assets/icons/Link.svg) **링크 복사**: 분석에 대한 링크를 클립보드에 복사합니다. 공유하기 전에 저장하라는 메시지가 표시됩니다.</li><li>**공유**: 개별 사용자 또는 그룹과 공유하기 위한 추가 옵션이 포함된 공유 모드를 엽니다. 분석을 다른 사용자와 공유하거나, 링크를 생성하여 모두와 공유할 수 있습니다.</li><li>**저장**: 분석을 저장합니다. 새 분석을 저장하는 경우 이름과 설명을 요청하는 **[!UICONTROL 분석 저장]** 대화 상자가 나타납니다. 저장되면 **[!UICONTROL 분석 저장]** 대화 상자를 통해 분석을 공유할 수 있습니다.</li></ul>다음과 같은 추가 작업을 보려면 ![자세히](/help/assets/icons/More.svg)를 선택하십시오.<ul><li>**다른 이름으로 저장**: 현재 분석과 별개로 분석을 저장하여 사본을 만듭니다. 새 이름과 설명을 요청하는 대화 상자가 나타납니다.</li><li>**Workspace으로 내보내기**: Analysis Workspace에서 현재 안내식 분석 쿼리를 다시 만듭니다. Workspace 프로젝트는 새 탭에서 만들어지므로 안내식 분석에서 작업하는 도중에 중단이 발생하지 않습니다. 이는 분석의 사본이며, 열면 원래 분석과 동기화되지 않습니다. 분석가 팀에 전달하거나 분석이 허용하는 것보다 더 깊이 데이터를 분석하려는 경우 이 명령을 사용합니다.</li><li>**클립보드에 차트 복사**: 다른 응용 프로그램에 붙여넣을 차트 그래픽을 클립보드에 복사합니다. 쿼리 레일과 테이블은 그래픽에 포함되지 않습니다.</li><li>**PNG 다운로드**: 차트 그래픽을 `.png`로 다운로드합니다. 쿼리 레일과 테이블은 그래픽에 포함되지 않습니다.</li><li>**CSV 다운로드**: 테이블 데이터를 `.csv`로 다운로드합니다. 쿼리 레일과 차트는 파일에 포함되지 않습니다.</li></ul> |
| ![메뉴 시각화](assets/menu-visualization.png){style="border:1px solid gray"} | **메뉴**<br/> Analysis Workspace의 안내식 분석 시각화에서 사용할 수 있습니다. | Analysis workspace에서 안내식 분석 시각화의 명령.<ul><li>![GraphScatter](/help/assets/icons/GraphScatter.svg) **[!UICONTROL 차트]**: 분석 차트만 표시합니다.</li><li>![테이블](/help/assets/icons/Table.svg) **[!UICONTROL 테이블]**: 분석 테이블만 표시합니다.</li><li>![TableAndChart](/help/assets/icons/TableAndChart.svg) **[!UICONTROL 모두]**: 분석의 차트와 테이블을 표시합니다.</li><li>![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 편집]**: 분석의 구성을 편집하려면</li><li>![일정](/help/assets/icons/Calendar.svg) **[!UICONTROL *날짜 범위&#x200B;*]**: 분석에 사용할 데이터 범위를 구성합니다.</li></ul> |


## 프로비저닝

안내식 분석은 다음 방법으로 Customer Journey Analytics 패키지에 포함됩니다.

| 패키지 | 사용 가능한 분석 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics 추가 기능] | 활성 증가, 전환 추세, 빈도, 단계, 순 성장, 유지, 추세 |
| [!UICONTROL Customer Journey Analytics 기초] | 트렌드 |
| [!UICONTROL Customer Journey Analytics 선택] | 기초 뷰 + 활성 증가, 전환 추세, 빈도, 단계, 순 증가, 유지 |
| [!UICONTROL Customer Journey Analytics Prime] | 보기 + 참여, 첫 번째 사용 영향, 릴리스 영향, 타임라인 선택 |
| [!UICONTROL Customer Journey Analytics Ultimate] | Prime 조회수 |

{style="table-layout:auto"}

제품 프로필 관리자는 Adobe Admin Console에서 안내가 있는 분석에 대한 액세스 권한을 추가하거나 제거할 수 있습니다.

1. [Adobe Admin Console](https://adminconsole.adobe.com)에 로그인합니다.
1. 제품 목록에서 **[!UICONTROL Customer Journey Analytics]**&#x200B;를 선택합니다.
1. 편집하려는 권한에 대해 원하는 제품 프로필을 선택합니다.
1. **[!UICONTROL 권한]** 탭을 선택한 다음 [!UICONTROL 보고 도구]에서 **[!UICONTROL 편집]**&#x200B;을 클릭합니다.
1. [!UICONTROL 사용 가능한 권한 항목] 목록에서 **[!UICONTROL 분석 액세스 가이드]** 옆에 있는 ![AddCircle](/help/assets/icons/AddCircle.svg)을(를) 선택하면 [!UICONTROL 포함된 권한 항목] 목록에 추가됩니다.
1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

자세한 내용은 [사용자 수준 액세스](/help/technotes/access-control.md#user-level-access)를 참조하십시오.

>[!TIP]
>
>일부 관리자는 Customer Journey Analytics를 처음 사용하는 사용자에 대해 안내식 분석은 활성화하고 Analysis Workspace는 비활성화하는 것을 선호합니다. 해당 사용자가 제품 및 조직 데이터에 익숙해지면 Analysis Workspace에 대한 액세스를 활성화할 수 있습니다.
