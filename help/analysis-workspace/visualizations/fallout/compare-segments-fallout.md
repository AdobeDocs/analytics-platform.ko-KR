---
description: 터치 포인트에서 세그먼트를 만들고, 세그먼트를 터치 포인트로 추가하고, Analysis Workspace의 다양한 세그먼트 간에 주요 워크플로우를 비교할 수 있습니다.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: 폴아웃 분석에서 필터 적용
translation-type: tm+mt
source-git-commit: ab1ea4c75c4c28f196c6793a819ce4dbe656d52c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 23%

---


# 폴아웃 분석에서 필터 적용

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 계십니다. 이 기능은 [기존 Adobe Analytics의 Analysis Workspace](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html)와 약간 다릅니다. [추가 정보...](/help/getting-started/cja-aa.md)

터치포인트에서 필터를 만들고 세그먼트를 터치포인트로 추가하고 Analysis Workspace의 다양한 필터에서 주요 워크플로우를 비교할 수 있습니다.

>[!IMPORTANT]
>
>폴아웃에서 체크포인트로 사용되는 필터는 폴아웃 시각화의 전체 컨텍스트에 비해 낮은 수준의 컨테이너를 사용해야 합니다. 방문자 컨텍스트 폴아웃의 경우 체크포인트로 사용되는 필터는 방문 또는 히트 기반 필터여야 합니다. 방문 컨텍스트 폴아웃의 경우 체크포인트로 사용되는 필터는 히트 기반 세그먼트여야 합니다. 잘못된 조합을 사용하는 경우 폴아웃은 100%가 됩니다. 호환되지 않는 필터를 터치포인트로 추가할 때 표시되는 폴아웃 시각화에 경고를 추가했습니다. 유효하지 않은 필터 컨테이너 조합으로 인해 다음과 같은 폴아웃 다이어그램이 잘못되었습니다.

* 방문자 기반 필터를 방문자 컨텍스트 폴아웃 시각화 내의 터치포인트로 사용
* 방문자 기반 필터를 방문 컨텍스트 폴아웃 시각화 내의 터치포인트로 사용
* 방문 기반 필터를 방문 컨텍스트 폴아웃 시각화 내의 터치포인트로 사용

## 터치포인트 {#section_915E8FBF35CD4F34828F860C1CCC2272}에서 필터 만들기

1. 특히 관심 있고 다른 보고서에 적용하는 데 유용할 수 있는 특정 터치포인트에서 필터를 만듭니다. 터치포인트를 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL 터치포인트에서 필터 만들기]**&#x200B;를 선택하면 됩니다.

   ![](assets/segment-from-touchpoint.png)

   필터 빌더가 열리고 선택한 터치포인트와 일치하는 미리 작성된 순차적 필터가 미리 채워집니다.

   ![](assets/segment-builder.png)

1. 필터에게 제목과 설명을 지정하고 저장합니다.

   이제 원하는 모든 프로젝트에서 이 필터를 사용할 수 있습니다.

## 필터를 터치포인트 {#section_17611C1A07444BE891DC21EE8FC03EFC}(으)로 추가

예를 들어 미국 사용자가 트렌드를 표시하고 폴아웃에 영향을 주는 방식을 보려면 미국 사용자 필터를 폴아웃으로 드래그하면 됩니다.

![](assets/segment-touchpoint.png)

또는 미국 사용자를 다른 체크포인트로 드래그하여 AND 터치포인트를 만들 수 있습니다.

## 폴아웃 {#section_E0B761A69B1545908B52E05379277B56}의 필터 비교

폴아웃 시각화에서 제한 없는 수의 필터를 비교할 수 있습니다.

1. 왼쪽의 [!UICONTROL 필터] 레일에서 비교할 세그먼트를 선택합니다. 이 예에서는 미국 사용자와 비미국 사용자, 이렇게 2개의 세그먼트를 선택했습니다. 
1. 맨 위에 있는 필터 드롭 영역으로 드래그합니다.

   ![](assets/segment-drop.png)

1. 선택 사항: &quot;모든 방문 수&quot;를 기본 컨테이너로서 유지하거나 삭제할 수 있습니다. 

   ![](assets/seg-compare.png)

1. 이제 한 필터가 다른 필터나 다른 통찰력을 수행하는 경우와 같이 두 필터의 폴아웃을 비교할 수 있습니다.
