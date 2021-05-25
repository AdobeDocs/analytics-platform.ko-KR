---
title: Customer Journey Analytics의 데이터 뷰 사용 사례
description: Customer Journey Analytics에서 데이터 보기의 유연성과 성능을 보여 주는 여러 사용 사례
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
source-git-commit: 3553a6a684bc2cd015d1b2ad6a3b02987d6d6bb2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 90%

---

# 데이터 보기 활용 사례

이러한 사용 사례는 Customer Journey Analytics에서 데이터 보기의 유연성과 성능을 보여 줍니다.

## pageTitle (문자열) 스키마 필드에서 주문 지표 만들기

예를 들어 데이터 보기를 생성할 때 문자열인 [!UICONTROL pageTitle] 스키마 필드에서 [!UICONTROL 주문] 지표를 생성할 수 있습니다. 단계는 다음과 같습니다.

1. 구성 요소 탭의 [!UICONTROL 포함된 구성 요소] 아래의 [!UICONTROL 지표] 섹션으로 [!UICONTROL pageTitle]을 끌어옵니다.
   ![](assets/use-case1a.png)
1. 이제 방금 끌어온 지표를 강조 표시하고 오른쪽의 [!UICONTROL 구성 요소 설정]에서 이름을 바꿉니다.
   ![](assets/orders.png)
1. 오른쪽의 [!UICONTROL 포함/제외 값] 대화 상자를 열고 다음을 지정합니다.
   ![](assets/orders2.png)

   &quot;확인&quot; 구문은 이것이 주문임을 나타냅니다. 해당 기준이 충족되는 모든 페이지 제목을 검토한 후 각 인스턴스에 대해 &quot;1&quot;이 계산됩니다. 결과는 새 지표입니다(계산된 지표가 아님). 포함/제외된 값이 포함된 지표는 다른 지표를 사용할 수 있는 모든 곳에서 사용할 수 있습니다. Attribution IQ, 필터 및 표준 지표를 사용할 수 있는 모든 곳에서 작동합니다.
1. [!UICONTROL 세션]의 [!UICONTROL 전환 확인 기간]을 사용하여 [!UICONTROL 마지막 터치]와 같은 이 지표에 대한 속성 모델을 추가로 지정할 수 있습니다.
또한 동일한 필드에서 다른 [!UICONTROL 주문] 지표를 만들고 [!UICONTROL 첫 번째 터치]와 같은 다른 속성 모델과 [!UICONTROL 30일] 같은 다른 [!UICONTROL 전환 확인 기간]을 지정할 수 있습니다.

## 정수를 차원으로 사용

이전에는 정수가 자동으로 CJA에서 지표로 처리되었습니다. 이제 숫자(Adobe Analytics의 사용자 지정 이벤트 포함)를 차원으로 처리할 수 있습니다. 다음은 한 예입니다.

1. [!UICONTROL 포함된 구성 요소] 아래의 [!UICONTROL 차원] 섹션으로 [!UICONTROL call_length_min] 정수를 끌어옵니다.

   ![](assets/integers.png)

1. 이제 [!UICONTROL 값 버킷팅]을 추가하여 이 차원을 버킷 방식으로 보고에 표시할 수 있습니다. (버킷이 없으면 이 차원의 각 인스턴스가 Workspace 보고에 라인 항목으로 나타납니다.)

   ![](assets/bucketing.png)

## 숫자 차원을 흐름 다이어그램에서 &quot;지표&quot;로 사용합니다

숫자 차원을 사용하여 [!UICONTROL  흐름] 시각화로 &quot;지표&quot;를 가져올 수 있습니다. 아래 예제는 [!UICONTROL 마케팅 채널]이 [!UICONTROL 주문]에 흐르는 것을 보여줍니다.

![](assets/flow.png)

## 지표 값 포함 또는 제외

다른 데이터 보기 설정에 대한 자세한 내용은 [데이터 보기 만들기](/help/data-views/create-dataview.md)를 참조하십시오.
데이터 보기의 개념적인 개요는 [데이터 보기 개요](/help/data-views/data-views.md)를 참조하십시오.