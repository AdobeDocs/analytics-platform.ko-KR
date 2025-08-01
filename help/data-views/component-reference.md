---
title: 표준 구성 요소 참조
description: 데이터 보기에 추가할 수 있는 모든 표준 구성 요소에 관한 세부 정보.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 6cabedc5ed58dac450577fc3505be5f95b7a959d
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 90%

---

# 표준 구성 요소 참조

Customer Journey Analytics의 차원 및 지표 대부분은 Adobe Experience Platform 데이터 세트의 스키마 요소를 기반으로 합니다. 하지만 사용하는 연결에 관계없이 데이터 보기에 추가하도록 여러 구성 요소를 사용할 수 있습니다.

[!UICONTROL 표준 구성 요소]는 데이터 세트 스키마 필드에서 생성되지 않고 대신 시스템에서 생성되는 구성 요소입니다. Analysis Workspace에서 보고 기능을 용이하게 하기 위해 일부 시스템 구성 요소가 필요한 반면 다른 시스템 구성 요소는 선택 사항입니다.

![표준 구성 요소](assets/dataview-standard-components.png)

## 필수 표준 구성 요소 {#required}

이러한 필요한 표준 구성 요소는 기본적으로 각 데이터 보기에 추가됩니다. 이는 Customer Journey Analytics에서 제공하는 보고 기능에 필수적입니다.

### 표준 차원

{{standard-dimensions}}


### 표준 지표

{{standard-metrics}}


## 선택 사항 표준 구성 요소 {#optional}

선택 사항 표준 구성 요소는 **[!UICONTROL 데이터 보기]** > **[!UICONTROL 데이터 보기 편집]** > **[!UICONTROL 구성 요소]** 탭 > **[!UICONTROL 표준 구성 요소]** 탭에서 사용할 수 있습니다.

| 구성 요소 이름 | 차원 또는 지표 | 메모 및 값 |
| --- | --- | --- |
| [!UICONTROL 오전/오후] | 차원 시간 분할 | 오전 또는 오후 |
| [!UICONTROL 일괄 처리 ID] | 차원 | [!UICONTROL 이벤트]가 속한 Experience Platform 배치의 식별자입니다. |
| [!UICONTROL 데이터 세트 ID] | 차원 | [!UICONTROL 이벤트]가 속한 Experience Platform 데이터 세트에 대한 식별자입니다. |
| [!UICONTROL 날짜] | 차원 시간 분할 | 1-31 |
| [!UICONTROL 요일] | 차원 시간 분할 | 월요일, 화요일, 수요일, 목요일, 금요일, 토요일, 일요일 |
| [!UICONTROL 일 (한 해 기준)] | 차원 시간 분할 | 1-366 |
| [!UICONTROL 시간 (일 기준)] | 차원 시간 분할 | 0-23 |
| [!UICONTROL &#x200B; 월 (연 기준)] | 차원 시간 분할 | 1월~12월 |
| [!UICONTROL 최초 세션] | 지표 | 보고 기간 내에서 개인이 정의한 첫 번째 세션입니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ko#new-repeat) |
| [!UICONTROL 복귀 세션] | 지표 | 개인의 첫 번째 세션이 아닌 세션 수입니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ko#new-repeat) |
| [!UICONTROL 개인 ID] | 차원 | Experience Platform에 정의된 각 데이터 세트 스키마에는 1개 이상의 ID가 ID 네임스페이스로 정의되고 연결된 고유한 ID 세트가 있을 수 있습니다. 이들 ID 중 원하는 ID를 개인 ID로 사용할 수 있습니다. 예를 들면 쿠키 ID, 결합된 ID, 사용자 ID, 추적 코드 등이 있습니다. [!UICONTROL 개인 ID] 차원은 데이터 세트를 결합하고 Customer Journey Analytics에서 고유 사용자를 식별하는 기반입니다.<p>가능한 사용 사례는 다음과 같습니다.<ul><li>특정 개인 ID 값에 대한 세그먼트를 만들어 해당 사용자의 비헤이비어에 따라 모든 항목을 세그먼트화합니다.</li><li>디버깅: 특정 쿠키 ID(또는 특정 고객 ID)에 대한 데이터가 있는지 확인합니다.</li><li>콜센터를 이용한 사용자를 식별합니다.</li></ul> |
| [!UICONTROL 개인 ID 네임스페이스] | 차원 | [!UICONTROL 개인 ID]로 구성된 ID 유형입니다. 예는 `email address`, `cookie ID`, `Analytics ID`와 같습니다. |
| [!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}<br/>[!UICONTROL 글로벌 계정 ID] | 차원 | 연결에서 글로벌 계정 컨테이너를 사용하는 경우의 [!UICONTROL 글로벌 계정 ID]입니다. |
| [!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}<br/>[!UICONTROL 계정 ID] | 차원 | [!UICONTROL 계정 ID]&#x200B;(연결에서 계정 컨테이너를 사용하는 경우). |
| [!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}<br/>[!UICONTROL 기회 ID] | 차원 | 연결에서 기회 컨테이너를 사용하는 경우의 [!UICONTROL 기회 ID]입니다. |
| [!BADGE B2B 에디션]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B 에디션"}<br/>[!UICONTROL 구매 그룹 ID] | 차원 | 연결에서 구매 그룹 컨테이너를 사용하는 경우의 [!UICONTROL 구매 그룹 ID]입니다. |
| [!UICONTROL 사분기] | 차원 시간 분할 | Q1, Q2, Q3, Q4 |
| [!UICONTROL 세션 반복] | 지표 | 개인의 첫 번째 세션이 아닌 세션의 수입니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ko#new-repeat) |
| [!UICONTROL 세션 유형] | 차원 | 이 차원에는 [!UICONTROL 첫 방문] 및 2. 재방문의 두 가지 값이 있습니다. [!UICONTROL 첫 방문] 라인 항목에는 개인이 정의한 첫 번째 세션으로 결정된 세션의 모든 활동(즉, 이 차원에 대한 지표)이 포함됩니다. 다른 모든 항목은 [!UICONTROL 재방문] 항목에 포함됩니다(모든 항목이 세션에 속한다고 가정). 지표가 세션에 포함되지 않는 경우, 지표는 이 차원의 ‘해당되지 않음&#39; 버킷에 표시됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ko#new-repeat) |
| [!UICONTROL 이벤트당 소비한 시간] | 차원 | [!UICONTROL 소비한 시간] 지표를 [!UICONTROL 이벤트] 버킷에 버킷팅합니다. |
| [!UICONTROL 세션당 소비한 시간] | 차원 | [!UICONTROL 소비한 시간] 지표를 [!UICONTROL 세션] 버킷에 버킷팅합니다. |
| [!UICONTROL 사용자당 소비한 시간] | 차원 | [!UICONTROL 소비한 시간] 지표를 [!UICONTROL 개인] 버킷에 버킷팅합니다. |
| [!UICONTROL 주말]/[!UICONTROL 평일] | 차원 시간 분할 | 주말 또는 평일 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[이벤트 깊이 기능을 통해 더 자세한 고객 인사이트 검색](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947?profile.language=ko#M576)
>