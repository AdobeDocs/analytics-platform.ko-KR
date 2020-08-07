---
title: 자유 형식 테이블의 동적 차원 항목과 정적 차원 항목
description: 표의 동적 및 정적 차원 항목과 상호 작용하는 방법.
translation-type: tm+mt
source-git-commit: cee89d021e9cd034246fe9367bc8910dac7ca7cf
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 9%

---


# 자유 형식 테이블의 동적 차원 항목과 정적 차원 항목

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 계십니다. 이 기능은 [기존 Adobe Analytics의 Analysis Workspace](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html)와 약간 다릅니다. [추가 정보...](/help/getting-started/cja-aa.md)

자유 형식 테이블에서 행과 열에는 다양한 구성 요소 값이 포함될 수 있습니다. 이러한 값은 빌드할 분석에 따라 동적(시간에 따라 변경) 또는 정적(시간에 따라 변경되지 않음)일 수 있습니다.

## 동적 차원 항목

동적 차원 항목은 시간에 따라 변경되며 자유 형식 테이블에서 정렬되는 지표에 따라 달라집니다. 지정된 기간 동안 상위 항목을 분석하려는 경우 동적 차원 항목을 사용하는 것이 좋습니다.

차원을 자유 형식 테이블에 놓으면 동적 행이 반환됩니다. 지정된 지표 및 기간에 대한 차원에 해당하는 상위 항목을 나타냅니다. 차원을 자유 형식 테이블 열에 놓을 수 있으며 차원이 상위 5개 차원 항목으로 자동으로 확장됩니다.

예를 들어 브라우저 유형 차원을 테이블로 드래그하면 상위 브라우저 유형 차원 항목(예: Microsoft, Apple, Google 등)이 동적으로 테이블 행으로 돌아갑니다. 열에 드롭된 경우 상위 5개의 브라우저 유형 차원 항목이 동적으로 반환됩니다.

동적 차원 항목에는 행 필터 옵션이 있으며 **not** 잠금 및 X 아이콘이 표시됩니다.

![](assets/dynamic-items.png)

## 정적 차원 항목

정적 차원 항목은 시간에 따라 변경되지 않습니다. 자유 형식 테이블에서 항상 반환되는 고정 구성 요소입니다. 정적 차원 항목은 특정 캠페인이든 주의 특정 요일이든 항상 동일한 항목을 분석하려는 경우 선호됩니다.

특정 구성 요소 값(차원, 지표, 세그먼트, 날짜 범위)을 수동으로 선택하여 테이블에 놓을 때마다 결과는 행 또는 열의 정적 목록입니다. 다음 옵션을 선택하면 정적 차원 항목을 생성할 수도 있습니다.

* 행에서 마우스 오른쪽 단추 클릭 > [!UICONTROL 선택한 행만 표시]
* 열에서 마우스 오른쪽 단추 클릭 > [!UICONTROL 정적인 항목 만들기]

예를 들어 Microsoft 및 Apple과 같은 특정 브라우저 유형 항목 위로 드래그하면 해당 2개의 특정 항목이 항상 표로 가져오게 됩니다.

정적 차원 항목은 **not** 행 필터 옵션이 있어야 합니다. 대신 각 항목에 잠금 및 X 아이콘이 표시됩니다. 테이블에서 해당 차원 항목을 제거하려면 X 아이콘을 클릭합니다.

![](assets/static-items.png)

## 혼합 차원 항목

다른 차원의 Dimension 항목을 동일한 테이블에 추가할 수 있습니다. 이 경우 행 헤더에는 &quot;혼합 Dimension&quot;이 표시됩니다. 이러한 차원 항목은 정적입니다. 예를 들어 브라우저 유형 차원의 특정 차원 항목과 브라우저 차원의 기타 차원 항목을 추가하는 것이 좋습니다.

![](assets/mixed-dimensions.png)

## 자유 형식 총 행

동적 및 정적 행은 자유 형식 합계 행에서 다르게 동작합니다. 기본적으로:

* 동적 행은 방문 또는 방문자와 같은 서버 측 및 중복 제거 지표를 합합니다
* 정적 행은 클라이언트 측면으로 합해지고 **not** 지표 중복 제거 총 행 서버측을 계산하려면 행 설정을 **총 합계 표시**. [추가 정보](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html)

