---
title: 세분화 개요
description: 에 사용되는 세그먼트와 간단한 세그먼트를 만드는 방법을 이해합니다.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: 85a22d1e57925f0512ce0cc658cfba1008339d91
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 5%

---


# 세분화 개요

Customer Journey Analytics을 사용하면 강력하고 집중된 대상 세그먼트를 작성하고 관리하고 공유하고 보고서에 적용할 수 있습니다. 세그먼트를 사용하여 특성 또는 상호 작용에 따라 개인, 세션 또는 이벤트의 하위 집합을 식별할 수 있습니다. 세그먼트는 특정 요구 사항에 맞게 작성한 다음 확인 및 편집하고 다른 팀 구성원과 공유할 수 있는 체계화된 대상 인사이트로 디자인됩니다.

세그먼트는 다음을 기반으로 할 수 있습니다.

- 속성(브라우저 유형, 디바이스, 방문 횟수, 국가, 성별),
- 상호 작용(캠페인, 키워드 검색, 검색 엔진)
- 종료 및 시작(Facebook, 정의된 랜딩 페이지, 참조 도메인, geofence 이벤트의 사용자),
- 사용자 지정 변수(양식 필드, 정의된 카테고리, 고객 ID)
- 및 기타 기준.

세그먼트를 만드는 데 사용할 수 있는 다양한 옵션에 대해서는 [세그먼트 만들기](/help/components/filters/create-filters.md)를 참조하십시오. 그런 다음 [세그먼트 빌더](filter-builder.md)에서 세그먼트 정의를 빌드, 수정 및 저장합니다. 또는 [빠른 세그먼트 빌더](quick-filters.md)를 사용하여 빠른 세그먼트를 만들 수 있습니다. 또한 [폴아웃](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu) 시각화를 사용하는 등 Workspace의 시각화에서 세그먼트를 생성할 수도 있습니다.

[세그먼트 관리자](manage-filters.md)를 사용하여 세그먼트를 관리합니다.

## 계획 세그먼트

특히 관리자의 경우 적절한 세그먼트 계획을 통해 세그먼트가 사용될 가능성을 높일 수 있습니다. 세그먼트를 계획할 때는 다음 사항을 고려하십시오.

- **대상자**: 세그먼트를 사용할 사용자는 누구입니까? 대상자가 이해할 수 있도록 올바른 세그먼트 설명을 제공해야 합니다.
   - 이 세그먼트는 어떤 작업에 유용합니까?

   - 이 세그먼트를 언제 사용해야 합니까?

- **범위**: 원하는 데이터를 가장 잘 나타내는 [세그먼트 컨테이너](#filter-containers)는 무엇입니까? 가능한 가장 작은 컨테이너를 사용합니다.

- **구성 요소**: 세그먼트 정의에 포함할 구성 요소와 조건이 유효성을 검사해야 하는 값을 결정합니다.

- **프로세스**: 세그먼트에 대한 승인 프로세스를 고려하십시오. Customer Journey Analytics에는 승인 워크플로가 없지만, 세그먼트 승인 여부를 결정하는 프로세스를 구성할 수 있습니다.

- **모듈화**: 모듈화를 염두에 두고 세그먼트를 정의합니다. 세그먼트 사용자는 강력한 새 세그먼트를 만들기 위해 세그먼트를 쉽게 [스택](filter-builder.md#stack-filters)할 수 있어야 합니다.


## 세그먼트 유형

세 가지 유형의 세그먼트를 만들 수 있습니다.

### 빠른 세그먼트

빠른 세그먼트를 사용하면 [세그먼트 빌더](/help/components/filters/create-filters.md)에서 세그먼트를 만들지 않고도 주어진 Workspace 프로젝트 내에서 데이터를 쉽게 탐색할 수 있습니다. Workspace 인터페이스 내에서 세그먼트를 직접 정의합니다. 자세한 내용은 [빠른 세그먼트](quick-filters.md)를 참조하십시오.

### 정규 세그먼트

일반 세그먼트를 사용하면 하나 이상의 조건에 따라 데이터(사용자, 세션, 이벤트)를 식별할 수 있습니다. 조건이 두 개 이상인 경우 And 및 Or와 같은 논리 연산자를 사용하여 세그먼트를 추가로 정의합니다. 컨테이너를 사용하여 조건을 그룹화하고 더 복잡한 세그먼트를 만들 수 있습니다. 자세한 내용은 [세그먼트 빌더](filter-builder.md)를 참조하십시오.

### 순차적 세그먼트

>[!IMPORTANT]
>
>채널 간 순차적 세그먼트를 만들려면 **Select** 패키지가 있어야 합니다. 보유 중인 Customer Journey Analytics 패키지가 무엇인지 확실하지 않은 경우에는 귀사의 관리자에게 문의하십시오.

순차적 세그먼트는 탐색(사이트 간 페이지 보기, 모바일 앱의 장면과의 상호 작용 또는 셋톱 박스의 메뉴 사용)에 따라 데이터(개인, 세션, 이벤트)를 식별할 수 있도록 해줍니다. 예를 들어, 순차적 세그먼트는 개인이 좋아하는 항목 및 개인이 피하는 항목을 식별하는 데 도움이 됩니다. Then 논리 연산자를 사용하여 순차적 세그먼트를 정의합니다. 자세한 내용은 [순차적 세그먼트](seg-sequential-build.md)를 참조하십시오.


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## 세그먼트 컨테이너 {#containers}

세그먼트는 중첩 컨테이너 모델을 사용하여 사람, 세션 및 이벤트 수준 계층을 기반으로 합니다. 중첩된 컨테이너를 사용하여 컨테이너 간에 조건을 정의할 수 있습니다.


<table style="table-layout: fixed; border: none;" width="100%">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 개인</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 세션</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> 이벤트</td>
</tr>
</table>

>[!NOTE]
>
>Adobe Analytics 사용자의 경우:
> 
> - Adobe Analytics에서 **Person** 컨테이너를 **Visitor** 컨테이너로 알고 있습니다.
> - **세션** 컨테이너는 Adobe Analytics에서 **방문** 컨테이너로 알려져 있습니다.
> - **Event** 컨테이너는 Adobe Analytics에서 **Hit** 컨테이너로 알려져 있습니다.
>

세그먼트는 조건에 따라 개인, 세션 또는 이벤트를 세그먼트화하는 조건을 설정합니다. 예를 들어, 사람을 세그먼트화하는 조건은 사람 특성과 탐색 트레이트를 기반으로 합니다. 데이터를 더 자세히 분류하려면 특정 세션, 페이지 보기 이벤트, 화면 탭, 셋톱 박스의 메뉴 선택 사항 등을 세그먼트화할 수 있습니다. CRM 또는 로열티 시스템에서 수집한 속성에 대해 세그먼트화할 수도 있습니다. [세그먼트 빌더](/help/components/filters/filter-builder.md)에서는 이러한 하위 집합을 빌드하고 중첩된 계층형 개인, 세션 또는 이벤트 컨테이너에 조건을 적용할 수 있는 간단한 인터페이스를 제공합니다.

[세그먼트 빌더](/help/components/filters/filter-builder.md)에 사용된 컨테이너 아키텍처는 개인을 가장 바깥쪽 컨테이너로 정의합니다. 이 컨테이너에는 세션 및 이벤트(예: 페이지 보기 횟수, 모바일 애플리케이션 화면 또는 셋톱 박스의 메뉴 화면)에서 해당 사용자에 맞는 중요한 데이터가 포함되어 있습니다. 중첩된 세션 컨테이너를 사용하여 세션에 따라 개인의 데이터를 분류하는 규칙을 설정할 수 있습니다. 중첩된 이벤트 컨테이너를 사용하여 개별 상호 작용에 따라 개인 정보를 분류할 수 있습니다. 각 컨테이너를 사용하여 개인의 내역에서 세션별로 분류된 상호 작용을 보고하거나 개별 이벤트를 분류할 수 있습니다.

### 개인 컨테이너

개인 컨테이너에는 컨테이너에 지정된 조건에 해당하는 개인에 대한 모든 세션 및 모든 이벤트가 포함됩니다. `Page Name equals Checkout`과(와) 같은 간단한 조건으로 세그먼트를 정의하면 개인 컨테이너는 다음으로 확인됩니다.

- 이름이 `Checkout`인 페이지를 방문한 모든 사람입니다.
- 이러한 사용자에 대한 모든 세션입니다.
- 이러한 사용자에 대한 모든 이벤트 데이터.

가장 광범위하게 정의된 컨테이너인 개인 컨테이너 수준에서 생성된 보고서는 세그먼트 자격이 있는 모든 개인에 대한 이벤트 및 세션을 반환합니다. 개인 컨테이너는 정의된 날짜 범위에 따라 변경되기가 가장 쉽습니다.
개인 컨테이너에는 개인의 전체 내역을 기반으로 하는 값이 포함될 수 있습니다.

- 첫 구매까지 소요된 일 수.
- 원래 시작 페이지 또는 모바일 앱 홈 화면입니다.
- 최초 참조 도메인.

### 세션 컨테이너

세션 컨테이너에서 특정 세션에 대한 페이지 상호 작용 또는 모바일 앱 상호 작용, 캠페인 또는 대화를 식별할 수 있습니다. 세션 컨테이너는 규칙이 충족되면 전체 세션에 대한 동작을 캡처하므로 가장 일반적으로 사용되는 컨테이너입니다. 세션 컨테이너에서도 세그먼트 작성 및 적용 시 포함 또는 제외할 세션을 정의할 수 있습니다.  `Page Name equals Checkout`과(와) 같은 간단한 조건으로 세그먼트를 정의하면 세션 컨테이너는 다음으로 확인됩니다.

- 이름이 `Checkout`인 페이지를 방문한 모든 세션입니다.
- 해당 세션에 대한 모든 이벤트 데이터.

세션 컨테이너는 다음 질문에 답변하는 데 도움이 될 수 있습니다.

- 웹 및 콜센터 데이터 소스와 관련된 세션은 몇 개입니까?
- 어떤 페이지가 판매로 성공적으로 전환되었습니까?

세션 컨테이너에는 세션당 이벤트를 기반으로 하는 값이 포함됩니다.

- 세션 유형.
- 시작 페이지.
- 반환 주기.
- 기여도 지표.
- 선형 할당 지표.

Customer Journey Analytics의 데이터 보기를 사용하면 세션 지속 시간과 새 세션을 만들어야 하는 시간을 결정할 수 있습니다. 예를 들어 사용자가 모바일 앱을 시작할 때마다 를 기반으로 새 모바일 앱 세션을 정의할 수 있습니다. 자세한 내용은 [세션 설정](/help/data-views/session-settings.md)을 참조하세요.

### 이벤트 컨테이너

이벤트 컨테이너는 세그먼트에서 포함 또는 제외할 페이지, 모바일 애플리케이션 또는 기타 이벤트 유형을 정의합니다. 그것은 사용 가능한 용기 중 가장 좁다. 조건이 참인 모바일 앱에서 특정 클릭, 페이지 보기, 탭 단추를 식별할 수 있습니다. 이벤트 컨테이너를 사용하여 단일 추적 코드를 보거나 모바일 앱의 특정 영역 내에서 동작을 격리할 수 있습니다. 주문이 이행되었을 때의 마케팅 채널과 같이 작업이 발생할 때의 특정 값을 정확하게 지정할 수도 있습니다. `Page Name equals Checkout`과(와) 같은 간단한 조건으로 세그먼트를 정의하면 이벤트 컨테이너는 다음으로 확인됩니다.

- 페이지 이름이 `Checkout`인 모든 페이지 보기 이벤트입니다.

이벤트 컨테이너에는 다음에 대한 값 기반 단일 페이지 분류가 포함됩니다.

- 제품
- 모든 prop
- 목록 차원
- 머천다이징 차원(이벤트 컨텍스트)



### B2B 컨테이너

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

[Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md)에 대한 액세스 권한이 있는 경우 세그먼트에서 사용할 추가 컨테이너를 사용할 수 있습니다. 이러한 추가 컨테이너의 사용에 대한 자세한 내용은 [B2B 개념 및 기능](/help/getting-started/cja-b2b-concepts-features.md)에서 확인할 수 있습니다.


### 논리 그룹 컨테이너

논리 그룹을 사용하면 조건을 하나의 순차적 세그먼트 체크포인트로 그룹화할 수 있습니다. 시퀀스의 일부로, [!UICONTROL 논리 그룹]&#x200B;(으)로 식별된 컨테이너에 정의된 논리는 이전의 순차적 체크포인트 후와 다음의 순차적 체크포인트 전에 평가됩니다. 자세한 내용은 [논리 그룹](seg-sequential-build.md#logic-group)을 참조하세요.

### 컨테이너 중첩

다른 컨테이너 내에 컨테이너를 만들면 세그먼트 내에 실제로 세그먼트를 만들게 됩니다. 중첩 컨테이너에는 다음 논리가 적용됩니다.

1. 가장 바깥쪽 컨테이너를 사용하여 포함된 데이터를 확인합니다. 이 외부 규칙과 일치하지 않는 데이터는 보고서에서 무시됩니다.
2. 나머지 데이터에 중첩된 세그먼트 정의를 적용합니다. 중첩된 세그먼트 정의는 첫 번째 정의가 삭제된 데이터에는 적용되지 않습니다.
3. 모든 중첩 컨테이너 세그먼트 정의가 계산될 때까지 반복합니다. 그런 다음 나머지 데이터는 결과에 포함되어 보고에 사용됩니다.

>[!NOTE]
>
>세그먼트 내에 세그먼트를 중첩하면(예: 구성 요소 패널에서 세그먼트 정의로 세그먼트 드래그) 드래그한 세그먼트 정의의 복사본(참조가 아님)으로 컨테이너가 만들어집니다.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box segment template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Segment Name | Description |
| --- | --- |
| All Data | All Data is a required segment that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[세그먼트 만들기](create-filters.md)
>[세그먼트 빌더](filter-builder.md)
>[빠른 세그먼트](quick-filters.md)
>[순차적 세그먼트](seg-sequential-build.md)
>[세그먼트 관리](manage-filters.md)
>
