---
title: Customer Journey Analytics의 데이터 뷰 사용 사례
description: Customer Journey Analytics에서 데이터 보기의 유연성과 성능을 보여 주는 여러 사용 사례
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1360'
ht-degree: 90%

---

# 데이터 보기 사용 사례

이러한 사용 사례는 Customer Journey Analytics에서 데이터 보기의 유연성과 성능을 보여 줍니다.

## 1. 문자열 스키마 필드로부터 지표 만들기 {#string}

예를 들어 데이터 보기를 생성할 때 문자열인 [!UICONTROL pageTitle] 스키마 필드에서 [!UICONTROL 주문] 지표를 생성할 수 있습니다. 단계는 다음과 같습니다.

1. 구성 요소 탭의 [!UICONTROL 포함된 구성 요소] 아래의 [!UICONTROL 지표] 섹션으로 [!UICONTROL pageTitle]을 끌어옵니다.
   ![구성 요소 이름 목록에서 pageTitle을 가리키는 화살표가 있는 스키마 필드.](../assets/use-case1a.png)
1. 이제 방금 끌어온 지표를 강조 표시하고 오른쪽의 [!UICONTROL 구성 요소 설정]에서 이름을 바꿉니다.
   ![구성 요소 설정 아래의 주문을 강조 표시하는 스키마 필드.](../assets/orders.png)
1. 오른쪽의 [!UICONTROL 포함/제외 값] 대화 상자를 열고 다음을 지정합니다.
   ![포함/제외 값을 선택하고 포함/제외 값 설정 및 대/소문자 구분 을 선택합니다.](../assets/orders2.png)

   &quot;확인&quot; 구문은 이것이 주문임을 나타냅니다. 해당 기준이 충족되는 모든 페이지 제목을 검토한 후 각 인스턴스에 대해 &quot;1&quot;이 계산됩니다. 결과는 새 지표입니다(계산된 지표가 아님). 포함/제외된 값이 포함된 지표는 다른 지표를 사용할 수 있는 모든 곳에서 사용할 수 있습니다. Attribution IQ, 필터 및 표준 지표를 사용할 수 있는 모든 곳에서 작동합니다.
1. [!UICONTROL 세션]의 [!UICONTROL 전환 확인 기간]을 사용하여 [!UICONTROL 마지막 터치]와 같은 이 지표에 대한 속성 모델을 추가로 지정할 수 있습니다.
또한 동일한 필드에서 다른 [!UICONTROL 주문] 지표를 만들고 [!UICONTROL 첫 번째 터치]와 같은 다른 속성 모델과 [!UICONTROL 30일] 같은 다른 [!UICONTROL 전환 확인 기간]을 지정할 수 있습니다.

또 다른 예는 회사에서 얼마나 많은 방문자 ID를 보유하는지 결정하는 지표로, 차원으로서의 방문자 ID 사용하는 것입니다.

## 2. 정수를 차원으로 사용 {#integers}

이전에는 정수가 자동으로 Customer Journey Analytics에서 지표로 처리되었습니다. 이제 숫자(Adobe Analytics의 사용자 정의 이벤트 포함)를 차원으로 처리할 수 있습니다. 다음은 한 예입니다.

1. [!UICONTROL 포함된 구성 요소] 아래의 [!UICONTROL 차원] 섹션으로 [!UICONTROL call_length_min] 정수를 끌어옵니다.

   ![Dimension 목록에서 call_length_mins를 가리키는 화살표입니다.](../assets/integers.png)

1. 이제 [!UICONTROL 값 버킷팅]을 추가하여 이 차원을 버킷 방식으로 보고에 표시할 수 있습니다. (버킷이 없으면 이 차원의 각 인스턴스가 작업 영역 보고에 라인 항목으로 나타납니다.)

   ![버킷 값이 선택된 값 버킷팅.](../assets/bucketing.png)

## 3. 플로우 다이어그램에서 &quot;지표&quot;로서 수치 차원 사용 {#numeric}

수치 차원을 사용하여 “지표”를 [!UICONTROL  플로우] 시각화에 나타낼 수 있습니다.

1. 데이터 보기 [구성 요소](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ko-KR#configure-component-settings) 탭에서 [!UICONTROL 마케팅 채널] 스키마 필드를 [!UICONTROL 포함된 구성 요소] 아래의 [!UICONTROL 지표] 영역으로 드래그합니다.
2. 작업 영역 보고에서 이 플로우는 [!UICONTROL 마케팅 채널]이 [!UICONTROL 주문]으로 흘러가는 모습을 보여 줍니다.

![이메일에서 종료/주문으로의 마케팅 채널 흐름.](../assets/flow.png)

## 4. 하위 이벤트 필터링 수행 {#sub-event}

이 기능은 특히 배열 기반 필드에 적용 가능합니다. 필터 빌더에 빌트인된 필터(세그먼트)는 이벤트 수준에서만 필터링할 수 있지만 포함/제외 기능을 사용하면 하위 이벤트 수준에서 필터링을 수행할 수 있습니다. 따라서 데이터 보기에서 포함/제외를 사용하여 하위 이벤트 필터링을 수행한 뒤 이벤트 수준에서 필터 내 이 새 지표/차원을 참고할 수 있습니다.

예를 들어 데이터 보기에서 포함/제외 기능을 사용하여 50달러가 넘는 매출을 생성한 제품만 중점적으로 살펴볼 수 있습니다. 그러므로 50달러 제품 구매와 25달러 제품 구매를 포함하는 주문이 있는 경우, 전체 주문이 아니라 25달러 제품 구매만 제외시키는 것입니다.

1. 데이터 보기 [구성 요소](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ko-KR#configure-component-settings) 탭에서 [!UICONTROL 수입] 스키마 필드를 [!UICONTROL 포함된 구성 요소] 아래의 [!UICONTROL 지표] 영역으로 드래그합니다.
1. 지표를 선택하고 오른쪽에 다음 내용을 구성합니다.
a. [!UICONTROL 형식]에서 [!UICONTROL 통화]를 선택합니다.
나. [!UICONTROL 통화]에서 USD를 선택합니다.
c. [!UICONTROL 값 포함/제외]에서 [!UICONTROL 포함/제외 값 설정] 옆에 있는 확인란을 선택합니다.
d. [!UICONTROL Match]에서 [!UICONTROL 모든 기준이 충족되는 경우]을 선택합니다.
e. [!UICONTROL 기준]에서 [!UICONTROL 이]보다 크거나 같음을 선택합니다.
f. &quot;50&quot;을 값으로 지정합니다.

이러한 새 설정을 사용해, 고가치 매출만 볼 수 있으며 50달러 미만인 모든 항목을 배제할 수 있습니다.

## 5. [!UICONTROL 값 옵션 없음] 설정 사용 {#no-value}

사용자들을 열심히 트레이닝할 때, 보고서에 &quot;지정되지 않음&quot;이 사용된다고 설명한 회사도 있을 것입니다. 데이터 보기에서 기본값은 &quot;값 없음&quot;입니다. 이제 데이터 보기 UI에서 [&quot;값 없음&quot;의 이름을 &quot;지정되지 않음&quot;으로 변경](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ko-KR#configure-no-value-options-settings)할 수 있습니다.

또 다른 예로 멤버십 프로그램 등록에 대한 차원을 들 수 있습니다. 이 경우에서는 &quot;값 없음&quot;의 이름을 &quot;멤버십 프로그램 등록 없음&quot;으로 변경할 수 있습니다.

## 6. 다양한 [!UICONTROL 속성] 설정을 사용하여 다수의 지표 만들기 {#attribution}

오른쪽 상단의 [!UICONTROL 복제] 기능을 사용하여 [!UICONTROL 첫 번째 터치], [!UICONTROL 마지막 터치], [!UICONTROL 알고리즘] 속성과 같은 다양한 속성 설정을 갖는 다수의 매출 지표를 만듭니다.

이때 각 지표의 이름을 &quot;알고리즘 매출&quot;과 같이 그 차이가 반영되도록 변경해야 합니다.

![동작 목록에서 카운트 값이 선택된 알고리즘 매출.](../assets/algo-revenue.png)

다른 데이터 보기 설정에 대한 자세한 내용은 [데이터 보기 만들기](/help/data-views/create-dataview.md)를 참조하십시오.
데이터 보기의 개념적인 개요는 [데이터 보기 개요](/help/data-views/data-views.md)를 참조하십시오.

## 7. 새 세션 및 재방문 세션 보고 {#new-repeat}

해당 데이터 보기에 대해 정의한 보고 기간과 13개월 전환 확인 기간을 기반으로 세션이 실제로 사용자의 첫 번째 세션인지 재방문 세션인지 판단할 수 있습니다. 이 보고를 통해 다음을 결정할 수 있습니다.

* 재방문 세션의 주문 비율은 얼마입니까?

* 특정 마케팅 채널 또는 특정 캠페인의 경우 처음 사용자를 대상으로 하십니까, 아니면 재방문 사용자를 대상으로 하십니까? 이 선택이 전환율에 어떤 영향을 미쳤습니까?

한 차원 및 두 지표를 통해 이 보고를 원활하게 수행할 수 있습니다.

* [세션 유형](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html#optional) - 이 차원에는 1) [!UICONTROL 신규] 및 2) [!UICONTROL 재방문]의 두 가지 값이 있습니다. [!UICONTROL 신규] 항목에는 개인이 정의한 첫 번째 세션으로 결정된 세션의 모든 활동(즉, 이 차원에 대한 지표)이 포함됩니다. 다른 모든 항목은 [!UICONTROL 재방문] 항목에 포함됩니다(모든 항목이 세션에 속한다고 가정). 지표가 세션에 포함되지 않는 경우 지표는 이 차원의 “해당되지 않음” 버킷에 표시됩니다.

* [최초 세션](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html#optional). 최초 세션 지표는 보고 기간 내에서 개인이 정의한 첫 번째 세션으로 정의됩니다.

* [재방문 세션](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html#optional) 재방문 세션 지표는 개인의 첫 번째 세션이 아닌 세션의 수입니다.—>

이러한 구성 요소에 액세스하려면:

1. 데이터 보기 편집기로 이동합니다.
1. 왼쪽 레일에서 **[!UICONTROL 구성 요소]** > **[!UICONTROL 선택 사항 표준 구성 요소]** 탭을 클릭합니다.
1. 이러한 구성 요소를 데이터 보기로 드래그합니다.

95%~99%의 시간 동안 신규 세션이 정확하게 보고됩니다. 유일한 예외는 다음과 같습니다.

* 13개월 전환 확인 기간 전에 첫 번째 세션이 발생한 경우. 이 세션은 무시됩니다.

* 세션이 전환 확인 기간과 보고 기간 모두에 걸쳐 있는 경우. 2022년 6월 1일부터 6월 15일까지 보고서를 실행한다고 가정해 보겠습니다. 전환 확인 기간은 2021년 5월 1일부터 2022년 5월 31일까지입니다. 세션이 2022년 5월 30일에 시작하여 2022년 6월 1일에 끝나는 경우 세션이 전환 확인 기간에 포함되므로 보고 기간의 모든 세션이 재방문 세션으로 계산됩니다.

## 8. 날짜 및 날짜-시간 기능 사용 {#date}

Adobe Experience Platform의 스키마에는 [!UICONTROL 날짜] 및 [!UICONTROL 날짜-시간] 필드가 있습니다. 이제 Customer Journey Analytics 데이터 보기에서 이러한 필드를 지원합니다. 이러한 필드를 데이터 보기에 차원으로 드래그하면 해당 [형식](/help/data-views/component-settings/format.md)을 지정할 수 있습니다. 이 형식 설정에 따라 보고에서의 필드 표시 방법이 결정됩니다. 예:

* 날짜 형식의 경우 **[!UICONTROL 월, 일, 년]** 형식으로 **[!UICONTROL 날짜]**&#x200B;를 선택하면 보고의 출력 예는 2022년 8월 23일과 같을 수 있습니다.

* 날짜-시간 형식의 경우 **[!UICONTROL 시간:분]** 형식으로 **[!UICONTROL 분]**&#x200B;을 선택하면 결과는 20:20과 같이 표시될 수 있습니다.

현재는 1900년 1월 1일 이후의 날짜(1970년 1월 1일만 예외)와 2000년 1월 1일 00:00:00 이후의 날짜-시간 값을 지원합니다.

### 날짜 및 날짜-시간 사용 사례

* 날짜: 여행사는 여행 출발 날짜를 데이터의 필드로 수집하고 있습니다. 여행사는 수집된 모든 출발 날짜의 [!UICONTROL 요일]을 비교하여 가장 인기 있는 날짜를 파악하는 보고서를 원합니다. 여행사는 [!UICONTROL 월(연 기준)]에도 동일한 작업을 수행하려고 합니다.

* 날짜-시간: 소매업체는 매장에서 POS(판매 시점) 각 구매에 대한 시간을 수집하고 있습니다. 주어진 한 달 동안, 가장 바쁜 쇼핑 기간을 [!UICONTROL 시간(일 기준)]별로 이해하려고 합니다.

>[!MORELIKETHIS]
>[형식 구성 요소 설정의 날짜 및 날짜-시간](/help/data-views/component-settings/format.md)

