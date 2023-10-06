---
title: 필터 관리자
description: Customer Journey Analytics에서 필터를 관리 방법 알아보기
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
source-git-commit: 8e04cdf67a365cb229660223547d60a4b8991f36
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 24%

---

# 필터 관리자

필터 관리자는 공유, 태그 지정, 승인, 복사, 삭제 및 즐겨찾기로 표시 등 다양한 필터 처리 방법을 제공합니다.

필터 관리자는 사용자가 소유하며 사용자와 공유된 모든 필터를 표시합니다. 관리자 수준의 사용자는 조직의 모든 필터를 볼 수 있습니다. 이 개요에서는 필터 관리자의 사용자 인터페이스와 기능을 설명합니다.

![](assets/filter-manager-ui.png)

## 필터 관리자 액세스

1. Customer Journey Analytics에서 **[!UICONTROL 구성 요소]** 탭을 선택한 다음 를 선택합니다 **[!UICONTROL 필터]**.

## 필터 관리자에서 사용할 수 있는 작업

필터 관리자에서 다음 작업을 수행할 수 있습니다.

* [필터 목록 필터링](/help/components/filters/filters-filter.md)

* [필터를 즐겨찾기로 표시](/help/components/filters/filters-favorite.md)

* [승인 필터](/help/components/filters/filters-approve.md)

* [태그 필터](/help/components/filters/filters-tag.md)

* [공유 필터](/help/components/filters/filters-share.md)

* 필터를 CSV 파일로 내보냅니다.

* [필터 복사](/help/components/filters/filters-copy.md)

* 필터 삭제

## 열 구성

표시되는 열을 구성하여 필터 관리자에서 각 필터에 대해 표시되는 정보를 구성할 수 있습니다.

필터 관리자에서 표시되는 열을 구성하려면 다음을 수행합니다.

1. Customer Journey Analytics에서 **[!UICONTROL 구성 요소]** 탭을 선택한 다음 를 선택합니다 **[!UICONTROL 파일러]**.

1. 필터 관리자에서 **열 사용자 지정** 아이콘 ![열 사용자 정의 아이콘](assets/customize-columns-icon.png)을 클릭한 다음 필터 관리자에 표시할 열을 선택합니다.

   다음 열을 사용할 수 있습니다.

   | 열 제목 | 설명 |
   |---|---|
   | 제목 및 설명 | 이러한 값은 필터 빌더에 제공됩니다. 제목 및 설명을 편집하려면 제목 링크를 선택하여 필터 빌더를 엽니다. |
   | 즐겨찾기 | 각 필터 옆에 별 아이콘을 표시하여 필터를 즐겨찾기로 표시할 수 있습니다. 자세한 내용은 [필터를 즐겨찾기로 표시](/help/components/filters/filters-favorite.md). |
   | 데이터 보기 | 이 열은 필터를 마지막으로 저장한 데이터 보기를 나타냅니다. |
   | 소유자 | 필터를 소유한 사람을 나타냅니다. 관리자가 아닌 경우 사용자가 소유하거나 사용자와 공유된 필터만 표시할 수 있습니다. |
   | 태그 (열 선택기에서 선택되지 않았으므로 열이 나타나지 않음) | 사용자 또는 사용자와 세그먼트를 공유한 다른 사람이 필터에 적용한 태그입니다. |
   | 다음 사용자와 공유 | 필터를 공유한 개인 또는 그룹(관리자만) 또는 모든 사용자(관리자만)를 표시합니다. <p>필터를 공유하거나 공유할 때 필터 이름 옆에 공유 아이콘이 표시됩니다.</p> |
   | 수정한 날짜 | 필터를 마지막으로 수정한 날짜를 표시합니다. |
   | 다음에서 사용 | 현재 필터가 사용 중인 구성 요소의 수를 표시합니다. <p>예를 들어 필터가 40개의 프로젝트와 2개의 경고에서 사용되고 있는 경우 이 열의 값은 로 표시됩니다. [!UICONTROL **42개 구성 요소**].</p> <p>이 열의 값을 선택하여 필터가 사용되는 위치 분류를 확인합니다(예: [!UICONTROL **프로젝트 (40)**], [!UICONTROL **경고 (2)**]).</p><p>필터는 다음 구성 요소 유형 중 하나에서 사용할 수 있습니다.</p> <ul><li>계산된 지표</li><li>프로젝트</li><li>예약된 프로젝트</li></ul><p>이 정보는 구성 요소가 조직의 사용자에게 유용한지, 어디에서 사용되는지, 삭제 또는 수정이 필요한지를 결정하는 데 도움이 됩니다.</p><p>이 열을 볼 때는 다음 사항을 고려하십시오.</p><ul><li>이 정보에는 API, Report Builder 또는 Data Warehouse의 사용이 포함되지 않습니다.</li><li>다음 [!UICONTROL **다음에서 사용됨**] 열은 기본적으로 표시되지 않습니다. [열 구성](#configure-columns) 표시합니다.</li><li>지정된 구성 요소에 대해 이 열에 데이터가 없지만 [!UICONTROL **마지막으로 사용한 날짜**] 날짜: 구성 요소가 저장되지 않고 분석에 사용되었을 수 있습니다.</li></ul><p>다음을 사용할 수 있습니다. [데이터 사전](/help/components/data-dictionary/data-dictionary-overview.md) 이 정보와 함께 구성 요소가 조직에서 어떻게 사용되는지 추적하고 더 잘 이해하는 데 도움이 됩니다.</p> |
   | 마지막 사용 | 다음 구성 요소 유형에서 마지막으로 필터를 사용한 날짜를 표시합니다. <ul><li>계산된 지표</li><li>프로젝트</li><li>예약된 프로젝트</li><li>필터</li></ul> <p>이 정보는 구성 요소가 조직의 사용자에게 중요한지 또는 삭제해야 하는지 여부를 결정하는 데 도움이 될 수 있습니다.</p><p>이 열을 볼 때는 다음 사항을 고려하십시오.</p><ul><li>이 정보에는 API, Report Builder 또는 Data Warehouse의 사용이 포함되지 않습니다.</li><li>일부 구성 요소의 경우 구성 요소가 2023년 9월 이전에 마지막으로 사용된 경우 이 열에 데이터가 포함되지 않을 수 있습니다.</li></ul><p>다음을 사용할 수 있습니다. [데이터 사전](/help/components/data-dictionary/data-dictionary-overview.md) 이 정보와 함께 구성 요소가 조직에서 어떻게 사용되는지 추적하고 더 잘 이해하는 데 도움이 됩니다. |

   {style="table-layout:auto"}
