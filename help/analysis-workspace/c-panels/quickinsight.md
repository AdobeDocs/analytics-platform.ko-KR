---
description: 빠른 인사이트는 새로운 작업 영역 사용자가 데이터 테이블 및 시각화 작성을 안내하는 도구입니다
title: 빠른 인사이트 패널
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '1098'
ht-degree: 100%

---

# 빠른 인사이트 패널

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 계십니다. 이 기능은 [기존 Adobe Analytics의 Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html)와 약간 다릅니다. [자세히 알아보기...](/help/getting-started/cja-aa.md)

>[!IMPORTANT]
>
>**[!UICONTROL 빠른 인사이트]** 패널은 현재 제한적인 테스트가 실시되고 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics/landing/an-releases.html)

[!UICONTROL Quick Insights]는 [!UICONTROL Analysis Workspace]의 비분석가 및 새 사용자에게 비즈니스 관련 질문에 빠르고 쉽게 답변할 수 있는 방법을 배울 수 있도록 지침을 제공합니다. 또한, 표 자체를 만들지 않고도 간단한 질문에 신속하게 답변하고자 하는 고급 사용자에게는 탁월한 툴입니다.

이 [!UICONTROL Analysis Workspace]를 처음 사용할 때 어떤 시각화가 가장 유용한지, 어떤 차원 및 지표가 인사이트를 용이하게 하는지, 항목을 드래그 앤 드롭할 위치, 필터를 생성할 위치 등을 궁금해할 수 있습니다.

이를 위해 그리고 [!UICONTROL Analysis Workspace]에서 귀사의 데이터 구성 요소 사용을 기반으로 [!UICONTROL 빠른 인사이트]는 귀사에서 가장 많이 사용되는 차원, 지표, 필터 및 날짜 범위를 제공하는 알고리즘을 활용합니다. 실제로 다음과 같이 드롭다운 목록에서 [!UICONTROL 인기]로 태그가 지정된 차원, 지표 및 필터가 표시됩니다.

![](assets/popular-tag.png)

[!UICONTROL 빠른 인사이트]는 다음과 같은 지원을 제공합니다.

* [!UICONTROL Analysis Workspace]에서 데이터 테이블 및 관련 시각화를 올바르게 작성합니다.
* 기본 구성 요소 및 [!UICONTROL Analysis Workspace]조각에 대한 용어 및 용어를 알아봅니다.
* [!UICONTROL 자유 형식 테이블]에서 간단한 차원 분류를 수행하거나, 여러 지표를 추가하거나, 필터를 쉽게 비교할 수 있습니다.
* 다양한 시각화 유형을 변경하거나 테스트하여 분석에 필요한 찾기 툴을 빠르고 직관적으로 찾을 수 있습니다.

## 기본 키 용어

다음은 익숙해야 하는 몇 가지 기본 용어입니다. 각 데이터 테이블은 데이터 스토리를 전달하는 데 사용하는 2개 이상의 구성 요소 (구성 요소)로 구성됩니다.

| 빌딩 블록 (구성 요소) | 정의 |
|---|---|
| [!UICONTROL 차원] | 차원은 프로젝트에서 보고, 분류하고 비교할 수 있는 지표 데이터에 대한 설명 또는 특성입니다. 숫자가 아닌 값 및 차원 항목으로 분류되는 날짜입니다. 예를 들어 &quot;browser&quot; 또는 &quot;page&quot;는 차원입니다. |
| [!UICONTROL 차원 항목] | 차원 항목은 차원의 개별 값입니다. 예를 들어 브라우저 차원의 차원 항목은 &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot; 등이 됩니다. |
| [!UICONTROL 지표] | 지표는 보기 수, 클릭스루 횟수, 다시 로드 횟수, 평균 체류 시간, 판매량, 주문 수, 매출액 등과 같은 방문자 활동에 대한 수량 정보입니다. |
| [!UICONTROL 시각화] | 작업 영역에서는 막대 차트, 도넛 차트, 히스토그램, 선 차트, 맵, 산점도 등과 같은 데이터를 시각적으로 나타낼 수 있도록 해 주는 [다양한 시각화](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)를 제공합니다. |
| [!UICONTROL 차원 분류] | 차원 분류는 차원을 다른 차원으로 문자 그대로 분류하는 방법입니다. 이 예에서는 미국 주를 모바일 디바이스별로 분류하여 주별 모바일 디바이스 방문하거나 모바일 디바이스 유형별로, 지역별, 내부 캠페인 등으로 분류할 수 있습니다. |
| [!UICONTROL 필터] | 필터를 사용하여 특성 또는 웹 사이트 상호 작용에 따라 방문자 하위 세트를 식별할 수 있습니다. 예를 들어 속성(브라우저 유형, 디바이스, 방문 횟수, 국가, 성별), 상호 작용(캠페인, 키워드 검색, 검색 엔진), 종료 및 항목(Facebook의 방문자, 정의된 랜딩 페이지, 참조 도메인), 사용자 정의 변수(양식 필드, 정의된 범주, 고객 ID)를 기반으로 [!UICONTROL 방문자] 필터를 빌드할 수 있습니다. |

## 빠른 인사이트 시작하기

1. 제공된 자격 증명을 사용하여 Customer Journey Analytics에 로그인합니다.
1. [!UICONTROL Workspace]로 이동하고 **[!UICONTROL 새 프로젝트 만들기]**&#x200B;를 클릭한 다음 **[!UICONTROL 빠른 인사이트]**&#x200B;를 클릭합니다. (왼쪽 레일의 **[!UICONTROL 패널]** 메뉴에서 이 패널에 액세스할 수도 있습니다.)

   ![](assets/qibuilder.png)

   ![](assets/qi-panel.png)

1. 처음 시작할 때 [!UICONTROL 빠른 인사이트 패널]의 기본 사항을 설명하는 간단한 튜토리얼을 살펴보십시오. 또는 **[!UICONTROL 튜토리얼 건너뛰기]**&#x200B;를 클릭합니다.
1. 기본 요소(구성 요소라고도 함): 차원(주황색), 지표(녹색), 필터(파란색) 또는 날짜 범위(보라색)를 선택합니다. 표를 자동으로 작성하려면 하나 이상의 차원과 지표를 선택해야 합니다.

   ![](assets/qibuilder2.png)

   다음 세 가지 방법으로 구성 요소를 선택할 수 있습니다.
   * 왼쪽 레일에서 끌어서 놓습니다.
   * 원하는 내용을 알고 있는 경우: 입력을 시작하면 [!UICONTROL 빠른 인사이트] 기능이 빈 공간을 채워줍니다.
   * 드롭다운을 클릭하고 목록을 검색합니다.

1. 하나 이상의 차원과 지표를 추가한 경우 다음을 생성합니다.

   * 세로 차원 (미국 주)과 맨 위에 가로로 지표 (방문)가 있는 자유 형식 테이블입니다. 다음 표를 확인하십시오.

   ![](assets/qibuilder3.png)

   * 함께 제공되는 시각화 (이 경우 [막대 차트](/help/analysis-workspace/visualizations/bar.md)) 생성된 시각화는 표에 추가한 데이터 유형을 기반으로 합니다. 시간 기반 데이터 (예: 일/개월당 [!UICONTROL 방문 수])는 기본적으로 [!UICONTROL 라인] 차트로 설정됩니다. 시간 기반이 아닌 데이터 (예: [!UICONTROL 디바이스]당 [!UICONTROL 방문 수])는 기본적으로 [!UICONTROL 막대] 차트로 제공됩니다. 시각화 유형 옆의 드롭다운 화살표를 클릭하여 시각화 유형을 변경할 수 있습니다.


1. (선택 사항) 차원 옆에 있는 > 오른쪽 화살표를 클릭하여 차원을 드릴다운하고 차원 항목을 살펴봅니다.

1. 아래의 &quot;추가 팁&quot;에 설명된 대로 세부 사항을 추가해 보십시오.

1. **[!UICONTROL 프로젝트 > 저장]**&#x200B;을 클릭하여 프로젝트를 저장합니다.

## 더 많은 팁

다른 유용한 힌트는 [!UICONTROL 빠른 인사이트 빌더]에 표시되며, 일부는 마지막 작업에 따라 표시됩니다.

* 먼저 **[!UICONTROL 추가 팁]** 튜토리얼을 완료합니다. 도움말 (?) ([!UICONTROL 빠른 인사이트] 타일 옆) 아이콘을 통해 액세스합니다. 이 튜토리얼은 하나 이상의 차원과 지표가 있는 프로젝트를 만든 후 24시간을 보여 줍니다.

   ![](assets/qibuilder4.png)

* **분류 기준**: 차원에서 최대 3개의 분류 수준을 사용하여 필요한 데이터로 드릴다운할 수 있습니다.

   ![](assets/qibuilder5.png)

* **지표 추가**: AND 연산자를 사용하여 표에 지표를 추가하여 최대 2개의 지표를 추가할 수 있습니다.

   ![](assets/qibuilder6.png)

* **필터 추가**: AND 또는 OR 연산자를 사용하여 표를 추가하면 최대 2개의 필터를 추가할 수 있습니다. 모바일 사용자 또는 단골 방문자를 추가할 때 표에 표시되는 상황을 살펴봅니다. 이러한 정보는 지표 위에 서로 나란히 표시됩니다. 모바일 사용자 및 단골 고객을 추가하면 두 필터의 결과가 함께 표시되고 표에서 서로 겹쳐집니다.

   ![](assets/qibuilder7.png)

## 알려진 제한 사항

표 내에서 바로 편집하는 경우 이로 인해 [!UICONTROL 빠른 인사이트] 패널이 동기화되지 않게 됩니다. 패널 오른쪽 상단에 있는 [!UICONTROL 빌더 재동기화]를 클릭하여 이전 **[!UICONTROL 빠른 인사이트]** 설정으로 복원할 수 있습니다.

![](assets/qibuilder9.png)

테이블에 직접 추가하기 전에 경고가 표시됩니다.

![](assets/qibuilder8.png)

그렇지 않으면, 직접 작성하면 새 사용자에게 유용한 기능을 제공하지 않고도 테이블이 이제 기존의 자유 형식 테이블로 동작하게 됩니다.
