---
title: 레이블 및 정책
description: Adobe Experience Platform에 정의된 데이터 레이블 및 정책이 Customer Journey Analytics의 데이터 보기 및 보고에 미치는 영향에 대해 알아봅니다.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 45%

---

# 레이블 및 정책

Experience Platform에서 데이터 세트를 만들 때 [데이터 사용 레이블](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/reference) 데이터 세트에 있는 일부 또는 모든 요소에 대해 설명합니다. Customer Journey Analytics에서 이러한 레이블과 정책을 볼 수 있습니다.

다음 레이블은 Customer Journey Analytics에서 특히 중요합니다.

* `C8`레이블 - **[!UICONTROL 측정 값이 없음]**. 이 레이블은 데이터를 조직의 웹 사이트나 앱에서 분석에 사용할 수 없음을 의미합니다.

* 다음 `C12` 레이블 - **[!UICONTROL 일반 데이터 내보내기 없음]**. 이 방식으로 레이블이 지정된 스키마 필드는 보고, 내보내기, API 등을 통해 Customer Journey Analytics에서 내보내거나 다운로드할 수 없습니다.

>[!NOTE]
>
>데이터 사용 레이블은 결합된 데이터 세트에 자동으로 전파되지 않습니다. 그러나 수동으로 추가할 수는 있습니다.

레이블 지정 자체가 이러한 데이터 사용 레이블이 시행됨을 의미하지는 않습니다. 이를 위해 정책이 사용됩니다. 다음을 사용하여 정책을 만들 수 있습니다. [EXPERIENCE PLATFORM UI](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/policies/user-guide) 또는 를 통해 [정책 서비스 API](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/api/overview) Experience Platform.

Experience Platform에 표시될 수 있고 보고 및 데이터 내보내기에 영향을 줄 수 있는 두 가지 Adobe 정의 정책을 Customer Journey Analytics에서 사용할 수 있습니다.

* **[!UICONTROL 사용 분석 및 사용자 기반 측정 제한]** 정책, 사용 `C8` 레이블 및
* **[!UICONTROL 데이터 내보내기 제한]** 정책, 사용 `C12` 레이블.

## Customer Journey Analytics 데이터 보기에서 데이터 레이블 보기

사용자나 다른 사용자가 Experience Platform에서 만든 데이터 레이블은 데이터 보기 사용자 인터페이스의 세 위치에 표시됩니다.

| 위치 | 설명 |
| --- | --- |
| 스키마 필드의 정보 버튼 | 이 버튼을 클릭하면 현재 필드에 적용되는 [!UICONTROL 데이터 사용 레이블]이 표시됩니다.<p>![](assets/data-label-left.png) |
| [구성 요소 설정](/help/data-views/component-settings/overview.md) 아래의 오른쪽 레일 | 모든 [!UICONTROL 데이터 사용 레이블]이 여기에 나열됩니다.<p>![](assets/data-label-right.png) |
| 데이터 레이블을 열로 추가 | 데이터 보기의 [!UICONTROL 포함된 구성 요소] 열에 [!UICONTROL 데이터 사용 레이블]을 열로 추가할 수 있습니다. 열 선택기 아이콘을 선택한 다음 를 선택하면 됩니다. **[!UICONTROL 데이터 사용 레이블]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## 데이터 보기에서 데이터 거버넌스 레이블 필터링

데이터 보기 편집기에서 [!UICONTROL 필터] 왼쪽 레일에 있는 아이콘을 클릭하여 데이터 보기 구성 요소 필터링 기준 **[!UICONTROL 데이터 거버넌스]** 및 유형 **[!UICONTROL 레이블]**:

![](assets/filter-labels.png)

**[!UICONTROL 적용]**&#x200B;을 클릭하여 레이블이 부착된 구성 요소를 확인합니다.

## 데이터 보기에서 데이터 거버넌스 정책 필터링

정책(예: 만든 정책, 이름이 인 정책)이 있는지 확인할 수 있습니다 **[!UICONTROL 분석 시행]**)이 켜져 있습니다. 또한 해당 정책이 분석 또는 데이터 내보내기를 위한 특정 Customer Journey Analytics 데이터 보기 요소의 사용을 차단하는지 여부입니다.

다시 다음을 선택합니다. [!UICONTROL 필터] 아이콘(왼쪽 레일 및 아래) **[!UICONTROL 데이터 거버넌스]**, 선택 **[!UICONTROL 정책]**:

![사용 분석 및 사용자 기반 측정 제한이 선택된 상태로 표시되는 목록별로 포함된 구성 요소 필터링](assets/filter-policies.png)

클릭 **[!UICONTROL 적용]** 사용 가능한 정책을 확인합니다.

## 활성화된 정책이 데이터 보기에 미치는 영향

C8 또는 C12 레이블을 사용하여 하나 이상의 정책이 켜진 경우 특정 데이터 레이블이 적용된 스키마 구성 요소를 데이터 보기에 추가할 수 없습니다.

이러한 구성 요소는 왼쪽 레일에서 회색으로 표시됩니다 [!UICONTROL 스키마 필드] 목록:

![회색으로 표시된 구성 요소와 데이터 사용을 제한하는 정책이 이 필드에 적용되었음을 나타내는 정책 메시지](assets/component-greyed.png)

또한 차단된 필드가 있는 데이터 보기는 저장할 수 없습니다.

데이터 보기에 이미 구성 요소가 정의된 Experience Platform의 필드 또는 필드 그룹에 정책을 통해 액세스 및 데이터 거버넌스 레이블을 적용하려는 경우 주의하십시오. 이 대화 상자가 표시될 수 있습니다.

![위반](assets/violation.png)

먼저 위반을 해결해야 합니다(예: 데이터 보기에서 구성 요소 제거).


>[!MORELIKETHIS]
>
>[중요한 데이터 다운로드](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Report Builder의 제한된 레이블은 무엇입니까?](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


