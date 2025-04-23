---
title: 세그먼트 관리
description: Customer Journey Analytics에서 세그먼트를 관리하는 방법 알아보기
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters, Segments
role: User
source-git-commit: 85a22d1e57925f0512ce0cc658cfba1008339d91
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 33%

---

# 세그먼트 관리


중앙 [!UICONTROL 세그먼트] 관리 인터페이스에서 [공유](filters-share.md), [세그먼트](filters-filter.md), [태그](filters-tag.md), [승인](filters-approve.md), 이름 바꾸기, [복사](filters-copy.md), 세그먼트 삭제, 내보내기 및 [즐겨찾기로 표시](filters-favorite.md)할 수 있습니다. 세그먼트를 관리하려면 다음을 수행하십시오.

* 기본 인터페이스에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택한 다음 **[!UICONTROL 세그먼트]**&#x200B;를 선택하십시오.


>[!NOTE]
>
>특정 Workspace 프로젝트 내에서 만드는 빠른 세그먼트는 모든 프로젝트에서 사용할 수 있도록 설정하지 않은 한 [!UICONTROL 세그먼트] 관리자에 표시되지 않습니다.
>

## 세그먼트 관리자

세그먼트 관리자에는 다음과 같은 인터페이스 요소가 있습니다.

![세그먼트 인터페이스](assets/filters-manager.png)

### 세그먼트 목록

세그먼트 목록➊에는 사용자가 소유한 모든 세그먼트, 모든 프로젝트에 범위가 지정된 세그먼트, 사용자와 공유된 세그먼트가 표시됩니다. 목록은 다음과 같습니다.

| 열 | 설명 |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 세그먼트를 ![Star](/help/assets/icons/Star.svg)로 전환하거나 ![StarOutline](/help/assets/icons/StarOutline.svg)으로 전환하지 않도록 선택하십시오. [세그먼트를 즐겨찾기로 표시](/help/components/filters/filters-favorite.md) 참조 |
| **[!UICONTROL 제목 및 설명]** | 세그먼트를 편집하려면 제목 링크를 선택하여 [세그먼트 빌더](filter-builder.md)를 엽니다. 공유 세그먼트는 ![공유](/help/assets/icons/ShareAlt.svg)(으)로 표시됩니다. |
| **[!UICONTROL 데이터 보기]** | 이 세그먼트가 적용되는 데이터 보기. |
| **[!UICONTROL 소유자]** | 세그먼트 소유자. 사용자는 소유한 세그먼트나 사용자와 공유된 주석만 볼 수 있습니다. |
| **[!UICONTROL 태그]** | 이 세그먼트의 태그입니다. |
| **[!UICONTROL 다음 사용자와 공유]** | 세그먼트를 공유한 개인 또는 그룹 수입니다. **[!UICONTROL 구성 요소 공유]** 대화 상자를 열지 선택합니다. 자세한 내용은 [세그먼트 공유](filters-share.md)를 참조하십시오. |
| **[!UICONTROL 수정한 날짜]** | 세그먼트를 마지막으로 수정한 날짜 및 시간입니다. |
| **[!UICONTROL 다음에서 사용]** | 현재 세그먼트가 사용되는 위치와 각 영역에서 세그먼트가 사용되는 횟수를 보여줍니다. <p>예를 들어, 세그먼트가 40개의 프로젝트와 2개의 경고에서 사용 중인 경우 이 열의 값은 [!UICONTROL **42개의 구성 요소**]&#x200B;로 표시됩니다.</p> <p>세그먼트가 사용되는 위치의 분류를 보려면 이 열의 값을 선택하십시오(예: [!UICONTROL **프로젝트(40)**], [!UICONTROL **모바일 스코어카드(2)**]). 또한 세그먼트가 사용되는 항목 목록을 볼 수 있습니다. 예를 들어 해당 프로젝트가 사용되는 프로젝트 목록을 보려면 [!UICONTROL **프로젝트(40)**] 링크를 선택합니다.</p><p>다음 각 영역은 해당 영역에서 사용 중인 세그먼트 인스턴스 수를 보여줍니다.</p>  <ul><li>[!UICONTROL **프로젝트**]<p>[세그먼트 빌더에서 만들었으며](/help/components/filters/filter-builder.md#) 모든 프로젝트에 사용할 수 있는 세그먼트를 포함합니다.</p></li><li>[!UICONTROL **애드혹 구성 요소**]<p>[빠른 세그먼트로 만든](/help/components/filters/quick-filters.md) 세그먼트를 포함하며 단일 프로젝트 내에서만 사용할 수 있습니다.</p></li><li>[!UICONTROL **예약된 프로젝트**]</li><li>[!UICONTROL **모바일 스코어카드**]</li><li>[!UICONTROL **주석**]</li><li>[!UICONTROL **계산된 지표**]</li><li>[!UICONTROL **Report Builder**]<p>이 옵션을 선택하면 다음 데이터 열이 포함된 CSV 파일이 다운로드됩니다.</p><ul><li>Report Builder 이름</li><li>마지막 액세스</li><li>마지막으로 액세스한 IMS 사용자 ID</li><li>마지막으로 액세스한 사용자 이름</li></ul></li></ul><p>이 정보는 구성 요소가 조직의 사용자에게 유용한지, 어디에서 사용되는지, 삭제 또는 수정이 필요한지를 결정하는 데 도움이 됩니다.</p><p>이 열을 조회할 때 다음 사항을 고려하십시오.</p><ul><li>이 정보는 시스템 관리자만 사용할 수 있습니다.</li><li>기본적으로 [!UICONTROL **다음에서 사용됨**] 열은 표시되지 않습니다. ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을 사용하여 이 열의 표시를 구성합니다.</li><li>이 정보에는 API 또는 Data Warehouse의 사용이 포함되지 않습니다.</li><li>주어진 구성 요소에 대한 데이터가 이 열에 없지만 구성 요소의 [!UICONTROL **마지막 사용**] 날짜가 있는 경우, 해당 구성 요소는 저장되지 않고 분석에 사용되었을 수 있습니다.</li><li>사용량 정보는 2023년 9월부터의 자료만 제공됩니다.</li></ul><p>이 정보와 함께 [데이터 사전](/help/components/data-dictionary/data-dictionary-overview.md)을 사용하면 조직에서 구성 요소가 사용되는 방식을 지속적으로 추적하고 보다 명확하게 파악할 수 있습니다.</p> |
| **[!UICONTROL 마지막 사용]** | 세그먼트를 마지막으로 사용한 때입니다. |

![ColumnSetting](/help/assets/icons/ColumnSetting.svg)을 사용하여 표시할 열을 지정합니다.

### 작업 표시줄

작업 표시줄을 사용하여 세그먼트에 대해 작업을 수행할 수 있습니다➋. 작업 표시줄에는 다음 액션이 포함됩니다.

| 액션 | 설명 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 추가]** | [세그먼트 빌더](filter-builder.md)를 사용하여 다른 세그먼트를 추가하십시오. |
| ![검색](/help/assets/icons/Search.svg) [!UICONTROL *제목별 검색*] | 목록에서 선택한 세그먼트가 없으면 이 검색 필드를 사용하여 세그먼트를 검색합니다. |
| ![레이블](/help/assets/icons/Label.svg) **[!UICONTROL 태그]** | 선택한 세그먼트에 태깅합니다. **[!UICONTROL 세그먼트 태그]** 대화 상자에서 선택한 세그먼트에 대한 태그를 선택하거나 선택 취소합니다. **[!UICONTROL 저장]**&#x200B;을 선택하여 선택한 세그먼트에 대한 태그를 저장합니다. 자세한 내용은 [세그먼트 태그 지정](/help/components/filters/filters-tag.md)을 참조하십시오. |
| ![공유](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 공유]** | 선택한 세그먼트를 공유합니다. **[!UICONTROL 세그먼트 공유]** 대화 상자에서 ![검색](/help/assets/icons/Search.svg) *개인 또는 그룹 검색*&#x200B;하거나 **[!UICONTROL 조직]** 또는 **[!UICONTROL 그룹]**&#x200B;을 선택할 수 있습니다. **[!UICONTROL 저장]**&#x200B;을 선택하여 선택한 세그먼트에 대한 공유 세부 정보를 저장합니다. 자세한 내용은 [세그먼트 공유](filters-share.md)를 참조하십시오. |
| ![삭제](/help/assets/icons/Delete.svg) **[!UICONTROL 삭제]** | 선택한 세그먼트를 삭제합니다. 확인 메시지가 표시됩니다. |
| ![편집](/help/assets/icons/Edit.svg) **[!UICONTROL 이름 바꾸기]** | 선택한 단일 세그먼트의 이름을 변경합니다. 선택하면 인라인 세그먼트 이름을 바꿀 수 있습니다. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 승인]** | 선택한 세그먼트를 승인합니다. 자세한 내용은 [세그먼트 승인](filters-approve.md)을 참조하세요. |
| ![복사](/help/assets/icons/Copy.svg) **[!UICONTROL 복사]** | 선택한 세그먼트를 복사합니다. 같은 이름과 접미사 `(Copy)`을(를) 사용하여 새 세그먼트를 만듭니다. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL CSV로 내보내기]** | 세그먼트를 `Segments List.csv` 파일로 내보냅니다. |

### 활성 필터 표시줄

필터 모음은 ➌ 필터 패널에서 세그먼트 목록(있는 경우)에 적용된 활성 세그먼트를 표시합니다. ![CrossSize75](/help/assets/icons/CrossSize75.svg)를 사용하여 필터를 빠르게 제거할 수 있습니다. 필터를 두 개 이상 지정한 경우 **[!UICONTROL 모두 제거]**&#x200B;를 사용하여 모든 필터를 제거할 수 있습니다.

### 필터 패널

![필터](/help/assets/icons/Filter.svg) **[!UICONTROL 필터]** 왼쪽 패널을 사용하여 세그먼트 목록을 필터링할 수 있습니다➍. 필터 패널에는 필터 유형과 특정 필터를 적용하는 세그먼트 수가 표시됩니다. 필터 패널의 표시를 전환하려면 ![필터](/help/assets/icons/Filter.svg)를 선택하십시오.

자세한 내용은 [세그먼트 목록 필터링](filters-filter.md)을 참조하십시오.
