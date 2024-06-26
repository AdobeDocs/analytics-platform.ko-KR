---
title: 레이블 및 정책
description: Adobe Experience Platform에 정의된 데이터 레이블 및 정책이 Customer Journey Analytics의 데이터 보기 및 보고에 미치는 영향에 대해 알아봅니다.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: ht
source-wordcount: '583'
ht-degree: 100%

---

# 레이블 및 정책

Experience Platform에서 데이터 세트를 생성할 때 데이터 세트의 일부 또는 모든 요소에 대한 [데이터 사용 레이블](https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/labels/reference)을 생성할 수 있습니다. Customer Journey Analytics에서 이러한 레이블과 정책을 볼 수 있습니다.

다음 레이블은 Customer Journey Analytics에서 특히 중요합니다.

* `C8`레이블 - **[!UICONTROL 측정 값이 없음]**. 이 레이블은 데이터를 조직의 웹 사이트나 앱에서 분석에 사용할 수 없음을 의미합니다.

* `C12` 레이블 - **[!UICONTROL 일반 데이터 내보내기 없음]**. 이 방식으로 레이블이 지정된 스키마 필드는 보고, 내보내기, API 등을 통해 Customer Journey Analytics에서 내보내거나 다운로드할 수 없습니다.

>[!NOTE]
>
>데이터 사용 레이블은 결합된 데이터 세트에 자동으로 전파되지 않습니다. 그러나 수동으로 추가할 수는 있습니다.

레이블 지정 자체가 이러한 데이터 사용 레이블이 시행됨을 의미하지는 않습니다. 이를 위해 정책이 사용됩니다. [Experience Platform UI](https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/policies/user-guide)를 사용하거나 Experience Platform의 [Policy Service API](https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/api/overview)를 통해 정책을 만들 수 있습니다.

Experience Platform에서 사용할 수 있는 Adobe에서 정의한 정책에는 다음 2가지가 있습니다. 이들 정책은 Customer Journey Analytics에 표시되고 보고 및 데이터 내보내기에 영향을 미칠 수 있습니다.

* **[!UICONTROL 사용 분석 및 사용자 기반 측정 제한]** 정책(`C8` 레이블 사용) 및
* **[!UICONTROL 데이터 내보내기 제한]** 정책(`C12` 레이블 사용)

## Customer Journey Analytics 데이터 보기에서 데이터 레이블 보기

Experience Platform에서 생성된 데이터 레이블은 데이터 보기 사용자 인터페이스의 3개 위치에 표시됩니다.

| 위치 | 설명 |
| --- | --- |
| 스키마 필드의 정보 버튼 | 이 버튼을 클릭하면 현재 필드에 적용되는 [!UICONTROL 데이터 사용 레이블]이 표시됩니다.<p>![](assets/data-label-left.png) |
| [구성 요소 설정](/help/data-views/component-settings/overview.md) 아래의 오른쪽 레일 | 모든 [!UICONTROL 데이터 사용 레이블]이 여기에 나열됩니다.<p>![](assets/data-label-right.png) |
| 데이터 레이블을 열로 추가 | 데이터 보기의 [!UICONTROL 포함된 구성 요소] 열에 [!UICONTROL 데이터 사용 레이블]을 열로 추가할 수 있습니다. 열 선택기 아이콘을 선택하고 **[!UICONTROL 데이터 사용 레이블]**&#x200B;을 선택하면 됩니다.<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## 데이터 보기에서 데이터 거버넌스 레이블 필터링

데이터 보기 편집기에서 왼쪽 레일에 있는 [!UICONTROL 필터] 아이콘을 선택하여 **[!UICONTROL 데이터 거버넌스]** 및 **[!UICONTROL 레이블]** 유형별로 데이터 보기 구성 요소를 필터링합니다.

![](assets/filter-labels.png)

**[!UICONTROL 적용]**&#x200B;을 클릭하여 레이블이 부착된 구성 요소를 확인합니다.

## 데이터 보기에서 데이터 거버넌스 정책 필터링

정책(예: **[!UICONTROL 분석 시행]**&#x200B;이라는 이름으로 생성한 정책)이 설정되어 있는지 확인할 수 있습니다. 해당 정책이 분석 또는 데이터 내보내기를 위한 특정 Customer Journey Analytics 데이터 보기 요소의 사용을 차단하는지 여부를 확인할 수도 있습니다.

다시 왼쪽 레일에 있는 [!UICONTROL 필터] 아이콘을 선택한 다음 **[!UICONTROL 데이터 거버넌스]**&#x200B;에서 **[!UICONTROL 정책]**&#x200B;을 선택합니다.

![선택된 사용 분석 및 사용자 기반 측정 제한을 표시하는 목록을 기준으로 포함된 구성 요소를 필터링](assets/filter-policies.png)

**[!UICONTROL 적용]**&#x200B;을 클릭하여 활성화된 정책을 확인합니다.

## 활성화된 정책이 데이터 보기에 미치는 영향

C8 또는 C12 레이블을 사용하여 하나 이상의 정책이 설정되어 있는 경우 특정 데이터 레이블이 적용된 해당 스키마 구성 요소를 데이터 보기에 추가할 수 없습니다.

이러한 구성 요소는 왼쪽 레일 [!UICONTROL 스키마 필드] 목록에서 회색으로 표시됩니다.

![회색으로 표시된 구성 요소와 데이터 사용을 제한하는 정책이 이 필드에 적용되었음을 나타내는 정책 메시지](assets/component-greyed.png)

또한 차단된 필드가 있는 데이터 보기는 저장할 수 없습니다.

데이터 보기에 이미 구성 요소가 정의되어 있는 Experience Platform의 필드 또는 필드 그룹에 정책을 통해 액세스 및 데이터 거버넌스 레이블을 적용할 때는 주의하십시오. 이 대화 상자가 표시될 수 있습니다.

![위반](assets/violation.png)

먼저 위반을 해결해야 합니다(예: 데이터 보기에서 구성 요소 제거).


>[!MORELIKETHIS]
>
>[중요한 데이터 다운로드](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Report Builder의 제한된 레이블은 무엇입니까?](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


