---
description: Analysis Workspace에서 차원 및 차원 항목을 분류하는 방법을 알아봅니다.
keywords: Analysis Workspace
title: 차원 분류
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
source-git-commit: a32f2c308b8fc1b463dc00d77008063035968241
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 56%

---

# 차원 분류

Analysis Workspace에서 특정 요구 사항에 맞게 데이터를 무제한으로 분류할 수 있습니다. 관련 지표, 차원, 세그먼트, 타임라인 및 기타 분석 분류 값을 사용하여 쿼리를 작성하십시오.

1. [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)에서 하나 이상의 선택한 행의 컨텍스트 메뉴에서 **[!UICONTROL 분류]** ![V자형 화살표](/help/assets/icons/ChevronRight.svg)를 선택합니다.

   ![선택한 항목에서 경고 만들기를 보여 주는 단계 결과.](assets/breakdown.png)

1. 하위 메뉴에서 **[!UICONTROL 차원]**, **[!UICONTROL 지표]**, **[!UICONTROL 세그먼트]** 또는 **[!UICONTROL 날짜 범위]**&#x200B;를 선택한 다음 항목을 선택하십시오. 또는 **[!UICONTROL *검색&#x200B;*]**필드에서 구성 요소를 검색하면 됩니다.

선택한 기간에 대해 차원 항목이나 대상자 세그먼트를 분류할 수 있습니다. 더 세부적인 수준으로 드릴다운할 수도 있습니다.

>[!NOTE]
>
>테이블에 표시되는 분류의 수는 200개로 제한됩니다. 이 제한은 분류 내보내기에 대해서는 증가합니다.

## 위치별 분류

기본적으로 분류는 정적 행 항목에 고정됩니다. 예를 들어 마케팅 채널별로 상위 3개 페이지 차원 항목(홈 페이지, 검색 결과, 체크아웃)을 분류한다고 가정합니다. 그런 다음 프로젝트를 떠났다가 2주 후에 돌아옵니다. 프로젝트를 다시 열면 상위 3개 페이지가 변경되고 대신 이제 홈 페이지, 검색 결과 및 체크아웃이 상위 4-6개 페이지가 됩니다. 기본적으로 마케팅 채널 분류는 4-6행에 있는 경우에도 여전히 홈 페이지, 검색 결과 및 체크아웃 아래에 표시됩니다.

반면 **위치별 분류**&#x200B;은(는) 상위 3개 항목이 무엇인지에 관계없이 항상 상위 3개 항목을 분류합니다. 예를 다시 참조하면, 프로젝트를 다시 열면 마케팅 채널 분류가 표의 상위 3페이지에 연결됩니다. 홈 페이지, 검색 결과 및 체크아웃은 이제 4-6행에 있습니다. 이 설정을 구성하는 방법은 [행 설정](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)을 참조하세요.

## 분류에 속성 모델 적용

테이블 내의 모든 분류에는 모든 속성 모델이 적용될 수 있습니다. 이 속성 모델은 상위 열과 동일하거나 다를 수 있습니다. 예를 들어 마케팅 채널 차원에서 선형 주문을 분석하고 채널 내 특정 추적 코드에 U자형 주문을 적용할 수 있습니다. 분류에 적용되는 속성 모델을 편집하려면 분류 모델 위로 마우스를 이동하고 **[!UICONTROL 편집]**&#x200B;을 선택하세요.

![분류 설정을 표시하는 순서 특성 비교](assets/breakdown-attribution.png)

이는 분류에 속성 모델을 적용하거나 편집할 때 예상되는 비헤이비어입니다.

* 다른 속성이 존재하지 않을 때 속성을 적용하는 경우 해당 속성이 전체 항목 트리에 적용됩니다.

* 속성이 적용된 후 분류를 추가하면 추가된 해당 분류에 대해 기본값이 사용됩니다(해당 차원에 기본값이 있는 경우). 그렇지 않은 경우 상위 열의 분류가 사용됩니다. 일부 차원에는 기본 할당이 있습니다. 예를 들어 시간 차원과 레퍼러는 동일한 터치를 사용합니다. 제품 차원은 마지막 터치를 사용합니다. 다른 차원에는 기본값이 없으며 상위 열 할당을 사용합니다.

* 항목 트리에 속성이 이미 있는 경우 속성을 변경하면 편집 중인 속성만 변경됩니다.

>[!BEGINSHADEBOX]

데모 비디오는 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace의 Dimension](https://video.tv.adobe.com/v/23971?quality=12&learn=on){target="_blank"}을 참조하십시오.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

데모 비디오를 보려면 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimension 분류](https://video.tv.adobe.com/v/23969?quality=12&learn=on){target="_blank"}를 참조하십시오.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

데모 비디오는 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [차원 및 지표 추가](https://video.tv.adobe.com/v/30606?quality=12&learn=on){target="_blank"}를 참조하십시오.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

데모 비디오는 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [자유 형식 테이블에서 차원 작업](https://video.tv.adobe.com/v/40179?quality=12&learn=on){target="_blank"}을 참조하십시오.

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

데모 비디오는 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [위치별 Dimension 분류](https://video.tv.adobe.com/v/24033){target="_blank"}를 참조하십시오.

{{videoaa}}

>[!ENDSHADEBOX]



