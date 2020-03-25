---
title: 데이터 뷰 만들기
description: CJA(Customer Journey Analytics)에서 플랫폼 데이터 세트에 대한 데이터 보기를 만드는 방법에 대해 설명합니다.
translation-type: tm+mt
source-git-commit: c85b5d2e702a38aa6569da893a25bacd39604f8a

---


# 데이터 뷰 만들기

데이터 보기는 데이터의 &quot;필터링된&quot; 보기라는 점에서 Analytics의 가상 보고서 세트와 유사합니다. 방문 시간 초과, 속성 등에 대한 서로 다른 설정을 사용하여 동일한 연결에 대해 다른 데이터 보기를 만들 수 있습니다. 단일 데이터 세트에 대해 여러 데이터 보기를 만들 수 있습니다. 예를 들어 모든 차원이 &quot;마지막 터치&quot;로 설정되는 하나의 데이터 보기를 가질 수 있고, 모든 차원이 &quot;첫 번째 터치&quot;로 설정된 다른 데이터 보기(동일한 데이터 세트 기반)를 동시에 볼 수 있습니다.

고객 여정 분석의 작업 영역 프로젝트는 데이터 뷰를 기반으로 합니다.

비디오 개요를 보려면 [여기를](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) 클릭하십시오.

## 전제 조건

데이터 뷰를 만들려면 먼저 Adobe Experience Platform 데이터 세트에 [](/help/connections/create-connection.md)대해 하나 이상의 연결을 설정해야 합니다.

## 설정 구성

1. 고객 여정 분석에서 **[!UICONTROL Data Views]** 탭으로 이동합니다.

1. 데이터 **[!UICONTROL Add]** 보기를 추가하고 설정을 구성하려면 클릭하십시오.

   | 세션 설정 | 정의 |
   |---|---|
   | 연결 | 이 필드는 데이터 보기를 이전에 설정한 연결과 연결하며, 여기에는 플랫폼 데이터 집합/s가 포함됩니다. |
   |  이름  | 데이터 보기에 이름을 지정해야 합니다. |
   | 설명 | 자세한 설명은 필수가 아니지만 권장됩니다. |
   | 태그 추가 | 태그를 사용하면 데이터 보기를 카테고리로 구성할 수 있습니다. |
   | 시간대 | 데이터 보기의 시간대를 선택합니다. |
   | 세션 시간 초과 | &quot;세션&quot;의 정의를 선택합니다. 세션 시간 초과 설정은 새 세션이 자동으로 시작되기 전에 고유 방문자가 가져야 하는 비활성 시간을 정의합니다. 기본값은 30분입니다. For example, if you set the session timeout to 45 minutes, a new session grouping is created for each sequence of hits collected, separated by 45 minutes of inactivity. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | 이벤트를 사용하여 새 세션 시작 | 세션이 시간 초과되었는지 여부에 관계없이 이벤트가 발생할 때 새 세션이 시작됩니다. 새로 만든 세션에는 세션을 시작한 이벤트가 포함됩니다. 또한 여러 이벤트를 사용하여 세션을 시작할 수 있으며, 데이터에서 이러한 이벤트가 관찰된 경우 새 세션이 실행됩니다. 이 설정은 방문 수, 세션(이전 방문) 세그먼트 컨테이너 및 차원에 대한 방문 만료 논리에 영향을 줍니다. |
   | 필터 추가 | &quot;필터&quot;는 고객 경로 분석의 &quot;세그먼트&quot;를 의미합니다. 데이터를 필터링하려면 왼쪽 레일에서 적절한 필터를 여기로 드래그합니다. 필터를 선택하지 않으면 데이터 보기에 모든 데이터가 포함됩니다. |

1. 클릭 **[!UICONTROL Continue]**.

## 구성 요소 추가

1. 이제 구성 요소(차원, 지표)를 데이터 보기에 추가할 때입니다(가상 보고서 세트의 조정 경험과 유사). 이제 데이터 세트에 있는 각 필드가 차원이나 지표로 변환됩니다. 차원 및 지표를 패널이나 **[!UICONTROL 모두** 선택을 선택하여 모든 구성 요소를 추가합니다.

   ![](assets/add-all-components.png)

1. 데이터 보기에 차원 및 지표를 추가하려면 **[!UICONTROL Add Components]** 탭을 클릭합니다.

   ![](assets/add-all-components2.png)

1. (선택 사항) 구성 요소를 선택하고 해당 설정을 편집하여 구성 요소의 이름을 친숙한 이름으로 변경하거나 속성 설정을 변경할 수 있습니다. 기본 이름은 그대로 유지됩니다. 자세한 내용은 데이터 보기 및 [속성 구성을 참조하십시오](/help/data-views/configure-dataviews.md).

1. 다음 단계는 구성 요소 및 속성 설정을 [지정하는 것입니다](/help/data-views/configure-dataviews.md).