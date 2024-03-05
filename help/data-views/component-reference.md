---
title: 표준 구성 요소 참조
description: 데이터 보기에 추가할 수 있는 모든 표준 구성 요소에 관한 세부 정보.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 949f0870c8607879d4f685f4fbeb838ddb68f80a
workflow-type: ht
source-wordcount: '1016'
ht-degree: 100%

---

# 표준 구성 요소 참조

Customer Journey Analytics의 차원 및 지표 대부분은 Adobe Experience Platform 데이터 세트의 스키마 요소를 기반으로 합니다. 하지만 사용하는 연결에 관계없이 데이터 보기에 추가하도록 여러 구성 요소를 사용할 수 있습니다.

[!UICONTROL 표준 구성 요소]는 데이터 세트 스키마 필드에서 생성되지 않고 대신 시스템에서 생성되는 구성 요소입니다. Analysis Workspace에서 보고 기능을 용이하게 하기 위해 일부 시스템 구성 요소가 필요한 반면 다른 시스템 구성 요소는 선택 사항입니다.

![표준 구성 요소](assets/dataview-standard-components.png)

## 필수 표준 구성 요소 {#required}

이러한 필요한 표준 구성 요소는 기본적으로 각 데이터 보기에 추가됩니다. 이는 Customer Journey Analytics에서 제공하는 보고 기능에 필수적입니다.

| 구성 요소 이름 | 차원 또는 지표 | 참고 |
| --- | --- | --- |
| [!UICONTROL 사람] | 지표 | [!UICONTROL 연결]에 지정된 개인 ID를 기반으로 합니다. |
| [!UICONTROL 세션] | 지표 | 데이터 보기의 세션 설정을 기반으로 합니다. |
| [!UICONTROL 이벤트] | 지표 | [!UICONTROL 연결]의 모든 이벤트 데이터 세트의 행 수입니다. |
| [!UICONTROL 초] | 차원 | 특정 이벤트기 발생한 시간(초)입니다(내림). 첫 번째 차원 항목은 날짜 범위에서 첫 번째 시산(초)이고 마지막 차원 항목은 날짜 범위에서 마지막 시간(초)입니다. |
| [!UICONTROL 분] | 차원 | 특정 이벤트기 발생한 시간(분)입니다(내림). 첫 번째 차원 항목은 날짜 범위에서 첫 번째 분이고 마지막 차원 항목은 날짜 범위에서 마지막 분입니다. |
| [!UICONTROL 시간] | 차원 | 특정 이벤트기 발생한 시간(시)입니다(내림). 첫 번째 차원 항목은 날짜 범위에서 첫 번째 시간이고 마지막 차원 항목은 날짜 범위에서 마지막 시간입니다. |
| [!UICONTROL 일] | 차원 | 특정 이벤트기 발생한 시간(일)입니다. 첫 번째 차원 항목은 날짜 범위에서 첫 번째 일이고 마지막 차원 항목은 날짜 범위에서 마지막 일입니다. |
| [!UICONTROL 주] | 차원 | 특정 이벤트기 발생한 시간(주)입니다. 첫 번째 차원 항목은 날짜 범위에서 첫 번째 주이고 마지막 차원 항목은 날짜 범위에서 마지막 주입니다. |
| [!UICONTROL 월] | 차원 | 특정 이벤트기 발생한 시간(월)입니다. 첫 번째 차원 항목은 날짜 범위에서 첫 번째 월이고 마지막 차원 항목은 날짜 범위에서 마지막 월입니다. |
| [!UICONTROL 분기] | 차원 | 특정 이벤트기 발생한 시간(분기)입니다. 첫 번째 차원 항목은 날짜 범위에서 첫 번째 분기이고 마지막 차원 항목은 날짜 범위에서 마지막 분기입니다. |
| [!UICONTROL 년] | 차원 | 특정 이벤트기 발생한 시간(년)입니다. 첫 번째 차원 항목은 날짜 범위에서 첫 번째 해이고 마지막 차원 항목은 날짜 범위에서 가장 최근 연도입니다. |
| [!UICONTROL 세션 시작] | 지표 | 세션의 첫 번째 이벤트였던 이벤트 수입니다. 필터 정의(예: &#39;[!UICONTROL 세션 시작]이 존재합니다&#39;)에 사용될 경우 이 필터는 모든 세션의 첫 번째 이벤트까지만 필터링합니다.<p>다음 [계산된 지표](/help/components/calc-metrics/default-calcmetrics.md)를 Workspace에서 사용할 수 있으려면 이 구성 요소가 데이터 보기에 포함되어 있어야 합니다. <ul><li>세션 시작 비율</li></p> |
| [!UICONTROL 세션 종료] | 지표 | 세션의 마지막 이벤트였던 이벤트 수입니다. [!UICONTROL 세션 시작]과 마찬가지로 필터 정의에서도 모든 세션의 마지막 이벤트까지 필터링하는 데 사용할 수 있습니다.<p>다음 [계산된 지표](/help/components/calc-metrics/default-calcmetrics.md)를 Workspace에서 사용할 수 있으려면 이 구성 요소가 데이터 보기에 포함되어 있어야 합니다. <ul><li>세션 종료 비율</li></p> |
| [!UICONTROL 소비한 시간(초)] | 지표 | 차원에 대한 두 개의 서로 다른 값 사이의 시간을 합산합니다.<p>다음 [계산된 지표](/help/components/calc-metrics/default-calcmetrics.md)를 Workspace에서 사용할 수 있으려면 이 구성 요소가 데이터 보기에 포함되어 있어야 합니다. <ul><li>사용자당 소비한 시간</li><li>세션당 소비한 시간</li></p> |

{style="table-layout:auto"}

## 선택 사항 표준 구성 요소 {#optional}

선택 사항 표준 구성 요소는 **[!UICONTROL 데이터 보기]** > **[!UICONTROL 데이터 보기 편집]** > **[!UICONTROL 구성 요소]** 탭 > **[!UICONTROL 표준 구성 요소]** 탭에서 사용할 수 있습니다.

| 구성 요소 이름 | 차원 또는 지표 | 메모 및 값 |
| --- | --- | --- |
| [!UICONTROL 오전/오후] | 차원 시간 분할 | 오전 또는 오후 |
| [!UICONTROL 일괄 처리 ID] | 차원 | [!UICONTROL 이벤트]가 속한 Experience Platform 일괄 처리를 나타냅니다. |
| [!UICONTROL 데이터 세트 ID] | 차원 | [!UICONTROL 이벤트]가 속한 Experience Platform 데이터 세트를 나타냅니다. |
| [!UICONTROL 날짜] | 차원 시간 분할 | 1-31 |
| [!UICONTROL 요일] | 차원 시간 분할 | 월요일, 화요일, 수요일, 목요일, 금요일, 토요일, 일요일 |
| [!UICONTROL 일 (한 해 기준)] | 차원 시간 분할 | 1-366 |
| [!UICONTROL 시간 (일 기준)] | 차원 시간 분할 | 0-23 |
| [!UICONTROL  월 (연 기준)] | 차원 시간 분할 | 1월~12월 |
| [!UICONTROL 최초 세션] | 지표 | 보고 기간 내에서 개인이 정의한 첫 번째 세션입니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ko-KR#new-repeat) |
| [!UICONTROL 복귀 세션] | 지표 | 개인의 첫 번째 세션이 아닌 세션 수입니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ko-KR#new-repeat) |
| [!UICONTROL 개인 ID] | 차원 | Experience Platform에 정의된 각 데이터 세트 스키마에는 1개 이상의 ID가 ID 네임스페이스로 정의되고 연결된 고유한 ID 세트가 있을 수 있습니다. 이들 ID 중 원하는 ID를 개인 ID로 사용할 수 있습니다. 예를 들면 쿠키 ID, 결합된 ID, 사용자 ID, 추적 코드 등이 있습니다. [!UICONTROL 개인 ID] 차원은 데이터 세트를 결합하고 Customer Journey Analytics에서 고유 사용자를 식별하는 기반입니다.<p>가능한 사용 사례는 다음과 같습니다.<ul><li>특정 개인 ID 값에 대한 필터를 생성하여 해당 사용자의 비헤이비어를 포함한 모든 사항을 필터링합니다.</li><li>디버깅: 특정 쿠키 ID(또는 특정 고객 ID)에 대한 데이터가 있는지 확인합니다.</li><li>콜센터를 이용한 사용자를 식별합니다.</li></ul> |
| [!UICONTROL 개인 ID 네임스페이스] | 차원 | [!UICONTROL 개인 ID]로 구성된 ID 유형입니다. 예는 `email address`, `cookie ID`, `Analytics ID`와 같습니다. |
| [!UICONTROL 사분기] | 차원 시간 분할 | Q1, Q2, Q3, Q4 |
| [!UICONTROL 세션 반복] | 지표 | 개인의 첫 번째 세션이 아닌 세션의 수입니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ko-KR#new-repeat) |
| [!UICONTROL 세션 유형] | 차원 | 이 차원에는 1) [!UICONTROL 첫 방문] 및 2) 재방문의 두 가지 값이 있습니다. [!UICONTROL 첫 방문] 라인 항목에는 개인이 정의한 첫 번째 세션으로 결정된 세션의 모든 활동(즉, 이 차원에 대한 지표)이 포함됩니다. 다른 모든 항목은 [!UICONTROL 재방문] 항목에 포함됩니다(모든 항목이 세션에 속한다고 가정). 지표가 세션에 포함되지 않는 경우, 지표는 이 차원의 ‘해당되지 않음&#39; 버킷에 표시됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=ko-KR#new-repeat) |
| [!UICONTROL 이벤트당 소비한 시간] | 차원 | [!UICONTROL 소비한 시간] 지표를 [!UICONTROL 이벤트] 버킷에 버킷팅합니다. |
| [!UICONTROL 세션당 소비한 시간] | 차원 | [!UICONTROL 소비한 시간] 지표를 [!UICONTROL 세션] 버킷에 버킷팅합니다. |
| [!UICONTROL 사용자당 소비한 시간] | 차원 | [!UICONTROL 소비한 시간] 지표를 [!UICONTROL 개인] 버킷에 버킷팅합니다. |
| [!UICONTROL 주말]/[!UICONTROL 평일] | 차원 시간 분할 | 주말 또는 평일 |

{style="table-layout:auto"}
