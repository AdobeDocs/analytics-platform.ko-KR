---
title: 자유 형식 테이블
description: 자유 형식 테이블 및 자유 형식 테이블 빌더에 대해 알아보기
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 100%

---


# 자유 형식 테이블

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 계십니다. 이 기능은 [기존 Adobe Analytics의 Analysis Workspace](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html)와 약간 다릅니다. [추가 정보...](/help/getting-started/cja-aa.md)

Analysis Workspace에서 자유 형식 테이블은 데이터 테이블일 뿐만 아니라 대화형 시각화이기도 합니다. [구성 요소](/help/components/overview.md) 조합을 행과 열로 끌어다 놓아 분석에 사용할 사용자 지정 테이블을 만들 수 있습니다. 각 구성 요소가 삭제되면 테이블이 즉시 업데이트되므로 신속하게 분석할 수 있습니다.

다음과 같은 다양한 방법으로 테이블을 사용자 지정할 수 있습니다.

* **다른 결과를 표시했던**
   * 페이지 매김이 발생하기 전에 각 차원 행에 최대 400개의 행을 표시할 수 있습니다. 프로젝트의 [보기 밀도](/help/analysis-workspace/build-workspace-project/view-density.md)를 조정하여 더 많은 행을 단일 화면에 맞출 수 있습니다.
   * 행을 추가 구성 요소별로 분석할 수 있습니다. 한 번에 여러 행을 분석하려면 여러 행을 선택한 다음 선택한 행 위로 다음 구성 요소를 끌어다 놓으면 됩니다. [분류](/help/components/dimensions/t-breakdown-fa.md)에 대해 자세히 알아보십시오.
   * 행을 [필터링](/help/analysis-workspace/build-workspace-project/pagination-filtering-sorting.md)하여 축소된 항목 세트를 표시할 수 있습니다. 추가 설정은 [행 설정](/help/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md)에서 사용할 수 있습니다.

* **열**
   * 구성 요소를 열 내에 스택하여 세그먼트화된 지표, 탭 간 분석 등을 만들 수 있습니다.
   * 각 열의 보기는 [열 설정](/help/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md)에서 조정할 수 있습니다.
   * [마우스 오른쪽 단추 클릭 메뉴](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html)를 통해 몇 가지 작업을 사용할 수 있습니다. 이 메뉴는 표 머리글, 행 또는 열을 클릭하는지 여부에 따라 다른 작업을 제공합니다.

## 자유 형식 테이블 빌더

먼저 테이블에 여러 구성 요소를 추가한 다음 데이터를 렌더링하려는 경우 자유 형식 테이블 빌더를 활성화할 수 있습니다. 테이블 빌더를 활성화한 상태에서 많은 차원, 분류, 지표 및 세그먼트를 끌어다 놓아 더 복잡한 질문에 대한 답변을 제공하는 표를 작성할 수 있습니다. 데이터는 즉시 업데이트되지 않고 **[!UICONTROL 빌드]**&#x200B;를 클릭하면 업데이트됩니다.

테이블 빌더는 데이터에 대한 복잡한 질문이 있고 질문에 답변하기 위해 구성할 표에 대한 아이디어가 있을 때 시간을 절약할 수 있는 옵션입니다. 그 외에도 테이블 빌더에는 다음을 수행할 수 있는 기능이 포함되어 있습니다.

* 각 작업이 렌더링될 때까지 기다리지 않고 필요한 정확한 형식으로 표를 배열합니다.
* 최대 4가지 수준의 분류를 신속하게 수행합니다.
* 모든 테이블 행 및 차원 열에 대한 행 및 분류 설정을 정의합니다.
* 기본적으로 테이블의 모든 레벨에 대한 **[!UICONTROL 위치별 분석]**(기존의 자유 형식 테이블에서 기본값: **[!UICONTROL 항목별 분석]**)입니다.
* 테이블에서 정적 행의 순서를 수동으로 지정합니다. 예를 들어 지표 행을 특정 순서로 표시하려는 경우 이 방법을 사용합니다.
* 실제 데이터를 렌더링하기 전에 테이블 형식을 미리 봅니다.

자유 형식 테이블 빌더 기능을 [여기](https://youtu.be/GUMWiJAmMGI)서 살펴보십시오.

## 자유 형식 테이블 데이터 내보내기

자유 형식 테이블의 데이터는 다음과 같은 몇 가지 방법으로 Analysis Workspace에서 복사할 수 있습니다.

* 테이블 헤더를 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL 클립보드에 복사]**&#x200B;를 선택합니다. 이 경우 전체(표시된) 테이블을 내보냅니다.
* 테이블에서 특정 셀을 강조 표시하고 마우스 오른쪽 단추를 클릭하여 **[!UICONTROL 클립보드에 복사]**&#x200B;를 선택하거나, Ctrl+C 핫키를 사용합니다.
* **[!UICONTROL 프로젝트 > CSV 다운로드]**. 이렇게 하면 프로젝트에 표시된 모든 테이블을 CSV로 내보냅니다.
