---
title: 날짜 범위 관리
description: Analysis Workspace에서 날짜 범위를 공유, 이름 변경 또는 삭제합니다.
feature: Calendar
exl-id: 694758c4-d740-4fd7-9fb0-3ff7f6b25a3d
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 13%

---

# 날짜 범위 관리

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 계십니다. 이 기능은 [기존 Adobe Analytics의 Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ko-KR)와 약간 다릅니다. [추가 정보...](/help/getting-started/cja-aa.md)

날짜 범위 관리자를 사용하여 날짜 범위를 공유, 이름 변경 또는 삭제할 수 있습니다. 날짜 관리자에 도달하려면,

1. AdobeID 자격 증명을 사용하여 [analytics.adobe.com](https://analytics.adobe.com)에 로그인합니다.
1. [!UICONTROL 구성 요소] > [!UICONTROL 날짜 범위]로 이동합니다.

## 인터페이스

![UI](../assets/date-range-ui.png)

날짜 범위 관리자에는 다음 옵션이 포함되어 있습니다.

* **추가**: 새 날짜 범위를 만듭니다. 자세한 내용은 [날짜 범위 만들기](create.md) 추가 정보.
* **제목별로 검색**: 제목별로 날짜 범위를 검색합니다. 결과는 여기에 입력한 텍스트를 기반으로 필터링됩니다.
* **필터**: 왼쪽 열을 사용하여 날짜 범위를 필터링합니다. 사용자 지정 태그, 소유자, 사용자가 만든 즐겨찾기, 승인됨 또는 사용자와 공유별로 필터링할 수 있습니다. 원하는 필터를 검색할 수도 있습니다.
* **즐겨찾기**: 을(를) 클릭합니다. ![별](../assets/star.png) 아이콘을 클릭하여 즐겨찾기에 추가합니다.
* **열 사용자 지정**: 을(를) 클릭합니다. ![열](../assets/columns.png) 아이콘을 사용하여 날짜 범위 관리자에 열을 표시하거나 숨길 수 있습니다.

추가 옵션을 보려면 하나 이상의 날짜 범위 옆에 있는 확인란을 클릭하십시오.

* **태그**: 선택한 모든 날짜 범위에 태그를 적용합니다. 태그는 날짜 범위를 구성하는 데 도움이 되며 왼쪽 열을 사용하여 필터링할 수 있도록 해줍니다.
* **공유**: 다른 Experience Cloud 사용자에게 날짜 범위를 공유합니다. 제품 관리자인 경우 전체 조직 또는 그룹에 공유할 수도 있습니다. 조직의 다른 사용자에게 공유되는 날짜 범위는 다음과 같습니다 ![공유](../assets/shared.png) 제목 옆에 있는 아이콘을 클릭합니다.
* **삭제**: 선택한 날짜 범위를 영구적으로 삭제합니다.
* **이름 변경**: 단일 날짜 범위를 선택한 경우 해당 제목을 변경할 수 있습니다.
* **승인**: 제품 관리자는 날짜 범위에 승인 스탬프를 추가할 수 있습니다. 승인된 날짜 범위는 조직의 사용자에게 &#39;공식&#39;임을 알리고 조직의 다른 사용자가 만든 날짜 범위와 구별합니다. 승인된 날짜 범위에는 ![승인됨](../assets/approved.png) 제목 옆에 있는 아이콘을 클릭합니다.
* **비승인**: 제품 관리자이고 이미 승인된 날짜 범위를 선택하는 경우, 승인을 취소할 수 있습니다.
* **복사**: 선택한 날짜 범위의 복사본을 만듭니다. 날짜 범위 복사 appends `(Copy)` 새로 복사한 날짜 범위의 제목 끝에 추가합니다.
* **CSV로 내보내기**: 선택한 모든 날짜 범위를 CSV 파일로 내보냅니다. 결과 CSV 파일의 열에는 날짜 범위 관리자에 표시된 모든 열이 포함됩니다.
