---
title: 데이터 보기 만들기
description: 데이터 보기를 만들거나 편집하기 위해 조정할 수 있는 모든 설정입니다.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 49b4998194274eec2ab8eca231029ccb5ccf648d
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 77%

---

# 데이터 보기 만들기

데이터 보기 만들기에는 스키마 요소에서 지표와 차원을 생성하거나 표준 구성 요소를 활용하는 작업이 포함됩니다. 대부분의 스키마 요소는 비즈니스 요구 사항에 따라 차원이나 지표일 수 있습니다. 스키마 요소를 데이터 보기로 드래그하면 CJA에서 차원이나 지표가 작동하는 방식을 조정할 수 있는 오른쪽에 옵션이 나타납니다.

## 데이터 보기 설정 및 컨테이너 구성

1. Customer Journey Analytics에서 **[!UICONTROL 데이터 보기]** 탭으로 이동합니다.
2. 데이터 보기를 추가하고 해당 설정을 구성하려면 **[!UICONTROL 추가]**&#x200B;를 클릭합니다.

![새로운 데이터 보기](assets/new-data-view.png)

| 설정 | 설명/사용 사례 |
| --- | --- |
| [!UICONTROL 연결] | 이 필드는 하나 이상의 Adobe Experience Platform 데이터 세트가 포함되어 있으며 이전에 설정한 연결에 데이터 보기를 연결합니다. |
| [!UICONTROL 이름] | 데이터 보기에 이름을 지정해야 합니다. |
| [!UICONTROL 설명] | 자세한 설명은 필수가 아니지만, 권장됩니다. |
| [!UICONTROL 시간대] | 데이터를 표시할 표준 시간대를 선택합니다. |
| [!UICONTROL 태그] | [!UICONTROL 태그]를 사용하여 데이터 보기를 범주로 구성할 수 있습니다. |
| [!UICONTROL 컨테이너] | 여기서 컨테이너의 이름을 바꾸어 이 데이터 보기에 기반한 모든 Workspace 프로젝트에 컨테이너가 표시되는 방식을 결정할 수 있습니다. [!UICONTROL 컨테이너]는 필터 및 폴아웃/흐름 등에 사용되어 범위 또는 컨텍스트의 폭이 얼마나 넓은지 정의합니다. [추가 정보](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=ko-KR#filter-containers) |
| [!UICONTROL 개인 컨테이너 이름…] | [!UICONTROL 개인] (기본값). [!UICONTROL 개인] 컨테이너에는 지정된 기간 내의 방문자에 대한 모든 방문 및 페이지 보기가 포함됩니다. 이 컨테이너의 이름을 &#39;사용자&#39; 또는 원하는 다른 용어로 바꿀 수 있습니다. |
| [!UICONTROL 세션 컨테이너 이름…] | [!UICONTROL 세션] (기본값). [!UICONTROL 세션] 컨테이너에서 특정 세션에 대한 페이지 상호 작용, 캠페인 또는 대화를 식별할 수 있습니다. 이 컨테이너의 이름을 &#39;방문&#39; 또는 원하는 다른 용어로 바꿀 수 있습니다. |
| [!UICONTROL 이벤트 컨테이너 이름…] | [!UICONTROL 이벤트] (기본값). [!UICONTROL 이벤트] 컨테이너는 필터에서 포함 또는 제외할 페이지 이벤트를 정의합니다. |

그런 다음 스키마 요소에서 지표와 차원을 생성할 수 있습니다. 표준 구성 요소를 사용할 수도 있습니다.

## 스키마 요소에서 지표 및 차원 생성

1. [!UICONTROL Customer Journey Analytics] > [!UICONTROL 데이터 보기]에서 [!UICONTROL 구성 요소] 탭을 클릭합니다.

![구성 요소 탭](assets/components-tab.png)

데이터 세트를 포함하는 왼쪽 상단의 [!UICONTROL 연결]과 아래의 [!UICONTROL 스키마 필드]를 볼 수 있습니다. 주의 사항:

* 이미 포함된 구성 요소는 표준 필수 구성 요소(시스템 생성)입니다.
* Adobe는 기본값으로 **[!UICONTROL 데이터 포함]** 필터를 적용하여 데이터가 포함된 스키마 필드만 나타나도록 합니다. 데이터가 포함되지 않은 필드를 찾는 경우 필터를 제거하면 됩니다.

1. 이제 왼쪽 레일에서 지표 또는 차원 섹션으로 [!UICONTROL pageTitle]과 같은 스키마 필드를 끌어옵니다.

   동일한 스키마 필드를 차원 또는 지표 섹션으로 여러 번 끌어오고 동일한 차원 또는 지표를 여러 가지 방법으로 구성할 수 있습니다.
예를 들어 **[!UICONTROL pageTitle]** 필드에서 오른쪽에 있는 **[!UICONTROL 구성 요소 이름]**&#x200B;의 이름을 바꾸어 &quot;제품 페이지&quot;라는 차원과 &quot;오류 페이지&quot;라는 차원 등을 생성할 수 있습니다. **[!UICONTROL pageTitle]** 필드의 문자열 값에서 지표를 생성할 수도 있습니다. 예를 들어 속성 설정이 다르고 포함/제외 값이 다른 하나 이상의 **[!UICONTROL 주문]** 지표를 생성할 수 있습니다.

   ![탭 3](assets/components-tab-3.png)

   >[!NOTE]
   >
   >왼쪽 레일에서 전체 스키마 필드 폴더를 드래그할 수 있으며, 일반 섹션으로 자동으로 정렬됩니다. 문자열 필드는 [!UICONTROL Dimension] 섹션과 [!UICONTROL 지표] 섹션에 있습니다. 또는 **[!UICONTROL 모두 추가]**&#x200B;를 클릭하면 모든 스키마 필드가 추가됩니다.

1. 구성 요소를 선택하면 오른쪽에 여러 가지 설정이 나타납니다. 에 설명된 설정을 사용하여 구성 요소를 구성합니다.

* [ 구성 요소 설정 개요](/help/data-views/component-settings/overview.md)
* [ 속성 구성 요소 설정](/help/data-views/component-settings/attribution.md)
* [ 동작 구성 요소 설정](/help/data-views/component-settings/behavior.md)
* [ Formatcomponent 설정](/help/data-views/component-settings/format.md)
* [[!UICONTROL 포함|] 제외 구성 요소 설정](/help/data-views/component-settings/include-exclude-values.md)
* [[!UICONTROL 지표 ] 중복 제거 구성 요소 설정](/help/data-views/component-settings/metric-deduplication.md)
* [[!UICONTROL 값 ] 구성 요소 설정이 없음](/help/data-views/component-settings/no-value-options.md)
* [ Persistencecomponent 설정](/help/data-views/component-settings/persistence.md)
   [[!UICONTROL 값 ] 그룹 구성 요소 설정](/help/data-views/component-settings/value-bucketing.md)

## [!UICONTROL 복제] 기능 사용

지표 또는 차원을 복제한 뒤 특정 설정을 변경하면 단일 스키마 필드에서 다수의 지표 또는 차원을 손쉽게 만들 수 있습니다. 간단하게 오른쪽 상단에서 지표 또는 차원 이름 아래의 [!UICONTROL 복제] 설정을 선택하면 됩니다. 그 후 새 지표 또는 차원을 변경한 뒤 더 설명적인 이름으로 저장합니다.

![복제](assets/duplicate.png)

## 필터, 스키마 필드 및 차원/지표

다음 데이터 유형을 사용하여 왼쪽 레일의 스키마 필드를 필터링할 수 있습니다.

![필터 필드](assets/filter-fields.png)

또한 데이터 세트 및 스키마 필드에 데이터가 포함되어 있는지 또는 ID인지 여부를 기준으로 필터링할 수도 있습니다. 기본적으로 모든 데이터 보기에 **[!UICONTROL 데이터 포함]** 필터를 적용합니다.

![기타 필터링](assets/filter-other.png)

## 데이터 보기에 글로벌 필터 추가

전체 데이터 보기에 적용되는 필터를 추가할 수 있습니다. 이 필터는 Workspace에서 실행하는 모든 보고서에 적용됩니다.

1. [!UICONTROL 데이터 보기]에서 [!UICONTROL 설정] 탭을 클릭합니다.
1. 왼쪽 레일의 목록에서 [!UICONTROL 필터 추가] 필드로 필터를 끌어옵니다.
