---
title: 필터 개요
description: 필터를 사용하는 이유 및 간단한 필터를 만드는 방법을 이해합니다.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 5fbb228fc02304be2246f0b49cb49de7f160b227
workflow-type: tm+mt
source-wordcount: '1423'
ht-degree: 8%

---


# 필터 개요

Customer Journey Analytics를 사용하면 강력한 집중 대상자 필터를 빌드, 관리, 공유하고 보고서에 적용할 수 있습니다. 필터를 사용하여 특성 또는 상호 작용에 따라 개인, 세션 또는 이벤트의 하위 집합을 식별할 수 있습니다. 필터는 특정 요구 사항에 맞게 작성한 다음 확인 및 편집하고 다른 팀원과 공유할 수 있는 체계화된 대상자 인사이트로 디자인되었습니다.

필터는 다음을 기반으로 할 수 있습니다.

- 속성(브라우저 유형, 디바이스, 방문 횟수, 국가, 성별),
- 상호 작용(캠페인, 키워드 검색, 검색 엔진)
- 종료 및 시작(Facebook, 정의된 랜딩 페이지, 참조 도메인, geofence 이벤트의 개인),
- 사용자 지정 변수(양식 필드, 정의된 카테고리, 고객 ID)
- 및 기타 기준.

필터를 만드는 데 사용할 수 있는 다양한 옵션은 [필터 만들기](/help/components/filters/create-filters.md)를 참조하십시오. 그런 다음 [필터 빌더](filter-builder.md)에서 필터 정의를 빌드, 수정 및 저장합니다. 또는 [빠른 필터 게시자](quick-filters.md)를 사용하여 빠른 필터를 만들 수 있습니다. 또한 [폴아웃](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu) 시각화를 사용하는 등 Workspace의 시각화에서 필터를 생성할 수도 있습니다.

[필터 관리자](manage-filters.md)를 사용하여 필터를 관리합니다.

## 플랜 필터

특히, 관리자로서 필터의 적절한 계획은 필터가 사용될 가능성을 향상시킨다. 필터를 계획할 때는 다음 사항을 고려하십시오.

- **대상자**: 필터를 사용할 사용자는 누구입니까? 대상자가 이해할 수 있도록 필터 설명을 제공하십시오.
   - 이 필터는 어떤 작업에 유용합니까?

   - 이 필터를 언제 사용해야 합니까?

- **범위**: 원하는 데이터를 가장 잘 나타내는 [필터 컨테이너](#filter-containers)는 무엇입니까? 가능한 가장 작은 컨테이너를 사용합니다.

- **구성 요소**: 필터 정의에 포함할 구성 요소와 조건이 유효성을 검사해야 하는 값을 결정합니다.

- **프로세스**: 필터에 대한 승인 프로세스를 고려하십시오. Customer Journey Analytics에 승인 워크플로가 없지만 필터를 승인할지 여부를 결정하는 프로세스를 구성할 수 있습니다.

- **모듈화**: 모듈화를 염두에 두고 필터를 정의합니다. 따라서 필터 사용자는 필터를 [스택](filter-builder.md#stack-filters)하여 강력한 새 필터를 쉽게 만들 수 있습니다.


## 필터 유형

세 가지 유형의 필터를 만들 수 있습니다.

### 빠른 필터

빠른 필터를 사용하면 [필터 빌더](/help/components/filters/create-filters.md)에서 필터를 만들지 않고도 주어진 Workspace 프로젝트 내에서 데이터를 쉽게 탐색할 수 있습니다. Workspace 인터페이스 내에서 필터를 직접 정의합니다. 자세한 내용은 [빠른 필터](quick-filters.md)를 참조하세요.

### 일반 필터

일반 필터를 사용하면 하나 이상의 조건에 따라 데이터(사용자, 세션, 이벤트)를 식별할 수 있습니다. 조건이 두 개 이상인 경우 And 및 Or와 같은 논리 연산자를 사용하여 필터를 추가로 정의합니다. 컨테이너를 사용하여 조건을 그룹화하고 더 복잡한 필터를 빌드할 수 있습니다. 자세한 내용은 [필터 빌더](filter-builder.md)를 참조하십시오.

### 순차적 필터

>[!IMPORTANT]
>
>채널 간 순차적 필터를 만들려면 **Select** 패키지가 있어야 합니다. 어떤 Customer Journey Analytics 패키지가 있는지 확실하지 않은 경우 관리자에게 문의하십시오.

순차적 필터는 탐색 (사이트 내 페이지 보기, 모바일 앱의 장면과 상호 작용 또는 셋톱 박스의 메뉴 사용)에 따라 데이터 (개인, 세션, 이벤트)를 식별할 수 있도록 해줍니다. 순차적 필터는 예를 들어, 개인이 좋아하는 항목 및 개인이 피하는 항목을 식별하는 데 도움이 됩니다. Then 논리 연산자를 사용하여 순차적 필터를 정의합니다. 자세한 내용은 [순차적 필터](seg-sequential-build.md)를 참조하십시오.


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## 필터 컨테이너 {#containers}

필터는 중첩된 컨테이너 모델을 사용하는 사람, 세션 및 이벤트 수준 계층을 기반으로 합니다. 중첩된 컨테이너를 사용하여 컨테이너 간에 조건을 정의할 수 있습니다.


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

필터는 조건에 따라 개인, 세션 또는 이벤트를 필터링하는 조건을 설정합니다. 예를 들어 사용자 특성 및 탐색 트레이트에 따라 사용자를 필터링하는 조건입니다. 데이터를 추가로 분류하려면 특정 세션, 페이지 보기 이벤트, 화면 탭, 셋톱 박스의 메뉴 선택 사항 등을 필터링할 수 있습니다. 또한 CRM 또는 로열티 시스템에서 수집한 속성을 필터링할 수도 있습니다. [필터 빌더](/help/components/filters/filter-builder.md)에서는 이러한 하위 집합을 빌드하고 중첩된 계층형 개인, 세션 또는 이벤트 컨테이너에 조건을 적용할 수 있는 간단한 인터페이스를 제공합니다.

[필터 빌더](/help/components/filters/filter-builder.md)에 사용된 컨테이너 아키텍처는 개인을 가장 바깥쪽 컨테이너로 정의합니다. 컨테이너에는 세션 및 이벤트(예: 페이지 보기, 모바일 애플리케이션 화면 또는 셋톱 박스의 메뉴 화면)에서 해당 사용자에 맞는 중요한 데이터가 포함됩니다. 중첩된 세션 컨테이너를 사용하여 세션에 따라 개인의 데이터를 분류하는 규칙을 설정할 수 있습니다. 중첩된 이벤트 컨테이너를 사용하여 개별 상호 작용에 따라 개인 정보를 분류할 수 있습니다. 각 컨테이너를 사용하여 개인의 내역에서 세션별로 분류된 상호 작용을 보고하거나 개별 이벤트를 분류할 수 있습니다.

### 개인 컨테이너

개인 컨테이너에는 컨테이너에 지정된 조건에 해당하는 개인에 대한 모든 세션 및 모든 이벤트가 포함됩니다. `Page Name equals Checkout`과(와) 같은 간단한 조건으로 필터를 정의하면 개인 컨테이너는 다음으로 확인됩니다.

- 이름이 `Checkout`인 페이지를 방문한 모든 사람입니다.
- 이러한 사용자에 대한 모든 세션입니다.
- 이러한 사용자에 대한 모든 이벤트 데이터.

가장 광범위하게 정의된 컨테이너인 개인 컨테이너 수준에서 생성된 보고서는 필터 자격이 있는 모든 개인에 대한 이벤트 및 세션을 반환합니다. 개인 컨테이너는 정의된 날짜 범위에 따라 변경되기가 가장 쉽습니다.
개인 컨테이너에는 개인의 전체 내역을 기반으로 하는 값이 포함될 수 있습니다.

- 첫 구매까지 소요된 일 수.
- 원래 시작 페이지 또는 모바일 앱 홈 화면입니다.
- 최초 참조 도메인.

### 세션 컨테이너

세션 컨테이너에서 특정 세션에 대한 페이지 상호 작용 또는 모바일 앱 상호 작용, 캠페인 또는 대화를 식별할 수 있습니다. 세션 컨테이너는 규칙이 충족되면 전체 세션에 대한 동작을 캡처하므로 가장 일반적으로 사용되는 컨테이너입니다. 또한 세션 컨테이너에서 필터 작성 및 적용 시 포함 또는 제외할 세션을 정의할 수 있습니다.  `Page Name equals Checkout`과(와) 같은 간단한 조건으로 필터를 정의하면 세션 컨테이너는 다음으로 확인됩니다.

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

Customer Journey Analytics의 데이터 보기를 사용하여 세션 지속 시간과 새 세션을 만들어야 하는 시간을 결정할 수 있습니다. 예를 들어 사용자가 모바일 앱을 시작할 때마다 를 기반으로 새 모바일 앱 세션을 정의할 수 있습니다. 자세한 내용은 [세션 설정](/help/data-views/session-settings.md)을 참조하세요.

### 이벤트 컨테이너

이벤트 컨테이너는 필터에서 포함 또는 제외할 페이지, 모바일 애플리케이션 또는 기타 유형의 이벤트를 정의합니다. 조건이 참인 모바일 앱에서 특정 클릭, 페이지 보기 및 탭 버튼을 식별할 수 있도록 하는 데 사용할 수 있는 컨테이너 중 가장 좁은 범위입니다. 이벤트 컨테이너를 사용하여 단일 추적 코드를 보거나 모바일 앱의 특정 영역 내에서 동작을 격리할 수 있습니다. 주문이 이행되었을 때의 마케팅 채널과 같이 작업이 발생할 때의 특정 값을 정확하게 지정할 수도 있습니다. `Page Name equals Checkout`과(와) 같은 간단한 조건으로 필터를 정의하면 이벤트 컨테이너는 다음으로 확인됩니다.

- 페이지 이름이 `Checkout`인 모든 페이지 보기 이벤트입니다.

이벤트 컨테이너에는 다음에 대한 값 기반 단일 페이지 분류가 포함됩니다.

- 제품
- 모든 prop
- 목록 차원
- 머천다이징 차원(이벤트 컨텍스트)


### 논리 그룹 컨테이너

논리 그룹을 사용하면 조건을 하나의 순차적 필터 체크포인트로 그룹화할 수 있습니다. 시퀀스의 일부로, [!UICONTROL 논리 그룹](으)로 식별된 컨테이너에 정의된 논리는 이전의 순차적 체크포인트 후와 다음의 순차적 체크포인트 전에 평가됩니다. 자세한 내용은 [논리 그룹](seg-sequential-build.md#logic-group)을 참조하세요.

### 컨테이너 중첩

다른 컨테이너 내에 컨테이너를 만들 때 실제로 필터 내에 필터를 만듭니다. 중첩 컨테이너에는 다음 논리가 적용됩니다.

1. 가장 바깥쪽 컨테이너를 사용하여 포함된 데이터를 확인합니다. 이 외부 규칙과 일치하지 않는 데이터는 보고서에서 무시됩니다.
2. 나머지 데이터에 중첩 필터 정의를 적용합니다. 중첩된 필터 정의는 첫 번째 정의가 삭제된 데이터에는 적용되지 않습니다.
3. 중첩된 컨테이너 필터 정의가 모두 계산될 때까지 반복합니다. 그런 다음 나머지 데이터는 결과에 포함되어 보고에 사용됩니다.

>[!NOTE]
>
>필터 내에 필터를 중첩하면(예: [구성 요소] 패널에서 필터 정의로 필터를 드래그하면) 드래그한 필터 정의의 복사본(참조가 아님)을 사용하여 컨테이너가 만들어집니다.

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box filter template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required filter that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[필터 만들기](create-filters.md)
>[필터 빌더](filter-builder.md)
>[빠른 필터](quick-filters.md)
>[순차적 필터](seg-sequential-build.md)
>[필터 관리](manage-filters.md)
>
