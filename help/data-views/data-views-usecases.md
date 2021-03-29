---
title: Customer Journey Analytics의 데이터 보기에 대한 사용 사례
description: Customer Journey Analytics에서 데이터 보기의 유연성과 강력함을 보여주는 다양한 사용 사례
translation-type: tm+mt
source-git-commit: 7db2474bf3cd16863c597295399a262c328172dc
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---


# 데이터 보기 사용 사례

사용 가능한

## pageTitle(문자열) 스키마 필드에서 주문 지표 만들기

예를 들어 데이터 보기를 만들 때 문자열인 [!UICONTROL pageTitle] 스키마 필드에서 [!UICONTROL 주문] 지표를 만들 수 있습니다. 다음은 단계입니다.

1. 구성 요소 탭에서 [!UICONTROL pageTitle]을 [!UICONTROL 포함된 구성 요소]의 [!UICONTROL 지표] 섹션으로 드래그합니다.
   ![](assets/use-case1a.png)
1. 이제 방금 드래그한 지표를 강조 표시하고 오른쪽의 [!UICONTROL 구성 요소 설정] 아래에서 이름을 변경합니다.
   ![](assets/orders.png)
1. 오른쪽에서 [!UICONTROL 값 포함/제외] 대화 상자를 열고 다음을 지정합니다.
   ![](assets/orders2.png)

   &quot;확인&quot; 구문은 이것이 주문임을 나타냅니다. 이러한 기준이 충족되는 모든 페이지 제목을 검토한 후 각 인스턴스에 대해 &quot;1&quot;이 계산됩니다. 결과는 새 지표(계산된 지표가 아님)입니다. 표준 지표를 사용할 수 있는 모든 Attribution IQ, 필터 및 다른 지표와 연동됩니다.
1. [!UICONTROL 세션]의 [!UICONTROL 뒤로 조회 창]과 같이 이 지표에 대한 속성 모델을 추가로 지정할 수 있습니다(예: [!UICONTROL 마지막 접촉]).
동일한 필드에서 다른 [!UICONTROL 주문] 지표를 만들고 그에 대해 다른 속성 모델(예: [!UICONTROL 첫 번째 터치])을 지정하고 다른 [!UICONTROL 룩백 창]을(를) 지정할 수도 있습니다(예: [!UICONTROL 30일]).

## 하나의 스키마 필드에서 여러 차원 만들기

## 정수를 차원으로 사용

34:00

버킷 포함