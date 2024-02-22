---
source-git-commit: 2f7e11106334560d3c4b54e6c5eaf84d5e1d4fb6
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 62%

---
# 스니펫

## 릴리스 단계 제한된 테스트 {#release-limited-testing}

>[!AVAILABILITY]
>
>이 문서에서 설명하는 기능은 릴리스의 제한된 테스트 단계에 있으며 사용자 환경에서 아직 사용하지 못할 수 있습니다. 기능이 일반적으로 제공되면 이 메모는 제거됩니다. Customer Journey Analytics 릴리스 프로세스에 대한 자세한 내용은 [Customer Journey Analytics 기능 릴리스](/help/release-notes/releases.md).

## 릴리스 단계 제한된 테스트 섹션 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>이 섹션에서 설명하는 기능은 릴리스의 제한된 테스트 단계에 있으며 사용자 환경에서 아직 사용하지 못할 수 있습니다. 기능이 일반적으로 제공되면 이 메모는 제거됩니다. Customer Journey Analytics 릴리스 프로세스에 대한 자세한 내용은 [Customer Journey Analytics 기능 릴리스](/help/release-notes/releases.md).

## 패키지 선택 {#select-package}

>[!NOTE]
>
>다음을 보유해야 합니다. **선택** 이 섹션에 설명된 기능을 사용하려면 패키지 이상을 따르십시오. 어떤 Customer Journey Analytics 패키지가 있는지 확실하지 않은 경우 관리자에게 문의하십시오.

## 프라임 패키지 {#prime-package}

>[!NOTE]
>
>다음을 보유해야 합니다. **Prime** 이 섹션에 설명된 기능을 사용하려면 패키지 이상을 따르십시오. 어떤 Customer Journey Analytics 패키지가 있는지 확실하지 않은 경우 관리자에게 문의하십시오.

## Ultimate 패키지 {#ultimate-package}

>[!NOTE]
>
>다음을 보유해야 합니다. **최적** 패키지 : 이 섹션에 설명된 기능을 사용하기 위해 어떤 Customer Journey Analytics 패키지가 있는지 확실하지 않은 경우 관리자에게 문의하십시오.


## 데이터 사전 필터 조건 {#dd-filter-criteria}

1. (선택 사항) **필터** 아이콘 ![데이터 사전 필터 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)을 선택한 후 다음 필터 옵션 중 하나를 선택하여 구성 요소 목록을 필터링합니다.

   | 옵션 | 함수 |
   |---------|----------|
   | [!UICONTROL **승인됨**] | 관리자가 승인함으로 표시된 구성 요소만 표시합니다. |
   | [!UICONTROL **즐겨찾기**] | 즐겨찾기 목록에 있는 구성 요소만 표시합니다. 즐겨찾기 목록에 구성 요소를 추가하는 방법에 대한 자세한 내용은 [구성 요소 개요](/help/components/overview.md)를 참조하십시오. |
   | [!UICONTROL **차원**] | 차원인 구성 요소만 표시합니다. (이 옵션은 데이터 사전에 처음 액세스할 때 [!UICONTROL **빠른 필터**] 탭에서도 사용할 수 있음) |
   | [!UICONTROL **지표**] | 지표인 구성 요소만 표시합니다. (이 옵션은 데이터 사전에 처음 액세스할 때 [!UICONTROL **빠른 필터**] 탭에서도 사용할 수 있음) |
   | [!UICONTROL **필터**] | 필터인 구성 요소만 표시합니다. (이 옵션은 데이터 사전에 처음 액세스할 때 [!UICONTROL **빠른 필터**] 탭에서도 사용할 수 있음) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **날짜 범위**] | 날짜 범위인 구성 요소만 표시합니다. (이 옵션은 데이터 사전에 처음 액세스할 때 [!UICONTROL **빠른 필터**] 탭에서도 사용할 수 있음) |
   | [!UICONTROL **모두 표시**] | 모든 구성 요소를 표시합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **승인되지 않음**] | 관리자가 승인함으로 표시하지 않은 구성 요소만 표시합니다. 관리자가 검토 및 승인이 필요한 구성 요소를 식별할 때 유용합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **설명 누락**] | 설명 필드에 아직 설명이 없는 구성 요소만 표시합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **중복 항목 표시**] | 선택한 데이터 보기에서 다른 구성 요소와 이름 또는 설명이 동일한 구성 요소만 표시합니다. 여기에는 사용자가 만든 구성 요소와 Adobe에서 제공하는 구성 요소가 포함됩니다. 중복 항목으로 표시하려면 이름이나 설명이 정확히 일치해야 합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **최근 데이터 없음**] | 지난 90일 동안 데이터를 수집하지 않은 구성 요소만 표시합니다. 이 옵션은 관리자만 사용할 수 있습니다. |
   | [!UICONTROL **제작자: Adobe**] <!-- I don't see this option--> | Adobe에서 제작한 구성 요소만 표시합니다. 조직의 관리자 또는 다른 사용자가 만든 구성 요소는 표시되지 않습니다. |

   {style="table-layout:auto"}

## 데이터 사전 구성 요소 정보 {#dd-component-information}

| 옵션 | 함수 |
|---------|----------|
| [!UICONTROL **승인됨**] | <p>관리자가 구성 요소를 검토하고 승인했음을 나타냅니다.</p><p>관리자에게는 [!UICONTROL **승인 취소**] 옵션이 표시됩니다. 이 옵션을 선택하면 구성 요소가 사용자에게 “승인되지 않음”으로 표시됩니다.</p> |
| [!UICONTROL **승인되지 않음**] | <p>관리자가 아직 구성 요소를 검토하고 승인하지 않았음을 나타냅니다.</p><p>관리자에게는 [!UICONTROL **승인**] 옵션이 표시됩니다. 이 옵션을 선택하면 구성 요소가 사용자에게 “승인됨”으로 표시됩니다.</p> |
| [!UICONTROL **설명**] | 구성 요소의 의도된 기능을 설명합니다. (이 정보는 [구성 요소 설명 추가](/help/components/add-component-descriptions.md)에 설명된 대로 Analytics 관리자가 추가함) |
| [!UICONTROL **다음과 함께 자주 사용됨**] | <p>현재 보고 있는 구성 요소와 함께 가장 일반적으로 사용되는 구성 요소를 표시합니다.</p><p>5개의 기본 구성 요소 유형인 지표, 계산된 지표, Dimension, 필터 및 날짜 범위에 최대 5개의 구성 요소가 표시됩니다.</p><p>이 목록은 지난 90일 동안의 데이터를 기반으로 합니다. 볼 수 있는 액세스 권한이 있는 구성 요소만 표시됩니다.</p><p>관리자는 [!UICONTROL **항상 포함**] 및 [!UICONTROL **항상 제외**] 드롭다운 영역에서 원하는 구성 요소를 선택해서 이 섹션에서 사용자에게 표시되는 구성 요소를 조정할 수 있습니다. 사용자에게 표시되는 구성 요소를 조정하기 전에 먼저 **모두 표시** 다른 관리자가 추가했을 수 있는 사용자와 공유되지 않는 구성 요소가 표시되는지 확인하기 위해 필터링합니다.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **다음과 유사**] | <p>현재 보고 있는 구성 요소와 유사한 이름이 있는 구성 요소를 표시합니다.</p><p>5개의 기본 구성 요소 유형인 지표, 계산된 지표, Dimension, 필터 및 날짜 범위에 최대 5개의 구성 요소가 표시됩니다.</p><p>볼 수 있는 액세스 권한이 있는 구성 요소만 표시됩니다.</p><p>데이터 보기에 있는 모든 중복 구성 요소가 여기에 표시됩니다. Analytics 관리자는 [데이터 사전 상태 모니터링](/help/components/data-dictionary/monitor-data-dictionary-health.md)에 설명된 대로 모든 중복 구성 요소를 식별하고 제거해야 합니다.</p><p>관리자는 [!UICONTROL **항상 포함**] 및 [!UICONTROL **항상 제외**] 드롭다운 영역에서 원하는 구성 요소를 선택해서 이 섹션에서 사용자에게 표시되는 구성 요소를 조정할 수 있습니다. 사용자에게 표시되는 구성 요소를 조정하기 전에 먼저 **모두 표시** 다른 관리자가 추가했을 수 있는 사용자와 공유되지 않는 구성 요소가 표시되는지 확인하기 위해 필터링합니다.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**참고:** 현재 **다음과 유사** 섹션에는 사용자가 만든 구성 요소만 포함되고 Adobe에서 제공하는 구성 요소는 포함되지 않습니다. Adobe 제공 구성 요소는 향후 릴리스에 추가될 예정입니다.</p> |
| [!UICONTROL **태그**] | 구성 요소에 적용된 모든 태그가 표시됩니다. 관리자 액세스 권한이 있는 사용자는 구성 요소를 편집할 때 태그를 추가할 수 있습니다. |
| [!UICONTROL **구성 요소 유형**] | 구성 요소의 유형(Dimension, 지표, 필터 또는 날짜 범위)을 나열합니다. |
| [!UICONTROL **작성자**] | 구성 요소를 생성한 사용자 이름을 표시합니다. |
| [!UICONTROL **미리보기**] | Analysis Workspace에서 구성 요소가 어떻게 보이는지 미리보기를 표시합니다. |
| [!UICONTROL **마지막 수정일**] | 구성 요소가 마지막으로 수정된 날짜를 표시합니다. 이 섹션은 필터, 지표, 계산된 지표 및 날짜 범위를 볼 때 표시됩니다. |

{style="table-layout:auto"}

## 구성 요소 정렬 옵션 {#components-sort-options}

| 옵션 | 함수 |
|---------|----------|
| [!UICONTROL **권장**] | 목록 맨 위에 권장되는 순서로 구성 요소를 정렬합니다. 귀하 또는 귀사의 다른 사용자가 가장 자주 그리고 가장 최근에 사용한 구성 요소가 목록의 위쪽에 표시됩니다. |
| [!UICONTROL **알파벳**] | 구성 요소를 알파벳순으로 정렬합니다. |
| [!UICONTROL **범주**] | 구성 요소 유형(차원, 지표, 필터, 날짜 범위)에 따라 구성 요소를 정렬합니다. |

{style="table-layout:auto"}

## 시간 비교 {#apply-time-comparison}

현재 기간을 이전 기간과 비교할 수 있습니다. 이 메뉴에서 옵션을 선택하면 모든 데이터 포인트에 유사한 색상의 점선 상대가 표시됩니다. 이 대응 항목은 선택한 이전 날짜 범위에서 동일한 지표를 나타냅니다. 이 옵션을 설정하면 차트와 테이블의 행 수가 두 배가 됩니다.

사용 가능한 시간 비교 옵션에는 이전 기간, 13주 전, 52주 전 및 사용자 지정된 날짜 범위가 포함됩니다. 사용자 지정 날짜 범위를 선택하면 숫자와 세부기간을 선택할 수 있는 추가 옵션이 나타납니다. 없음을 선택하면 날짜 비교가 제거됩니다.
