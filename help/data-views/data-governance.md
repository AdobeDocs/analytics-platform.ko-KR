---
title: 레이블 및 정책
description: AEP에 정의된 데이터 레이블 및 정책이 CJA의 데이터 보기 및 보고에 미치는 영향을 알아봅니다.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 7962114aaab42a283f1cb35a312b0a707038c31a
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# 레이블 및 정책

Experience Platform에서 데이터 세트를 만들 때 만들 수 있습니다 [데이터 사용 레이블](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) 데이터 세트에 있는 일부 또는 모든 요소에 대해 를 사용할 수 있습니다. 지금까지 이러한 레이블은 CJA에서 노출되지 않았습니다. 이 릴리스를 사용하면 CJA에서 이러한 레이블 및 정책을 볼 수 있습니다.

CJA에 대한 특별한 관심 사항은 다음과 같습니다.

* 다음 `C8` 레이블 - **[!UICONTROL 측정 없음]**. 이 레이블은 조직의 웹 사이트 또는 앱에서 데이터를 분석에 사용할 수 없음을 의미합니다.

* 다음 `C12` 레이블 - **[!UICONTROL 일반 데이터 내보내기 없음]**. 이러한 방식으로 레이블이 지정된 스키마 필드는 CJA에서(보고, 내보내기, API 등을 통해) 내보내거나 다운로드할 수 없습니다.

레이블 지정 자체가 이러한 데이터 사용 레이블이 적용된다는 것을 의미하지는 않습니다. 그것이 정책이 사용되는 것입니다. 를 통해 정책을 만듭니다 [정책 서비스 API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) Experience Platform에서 확인하십시오.

CJA에는 두 개의 Adobe 정의 정책이 표시되며 보고 및 다운로드/공유에 영향을 줍니다.

* **[!UICONTROL Analytics 적용]** 정책
* **[!UICONTROL 다운로드 적용]** 정책

## CJA 데이터 보기에서 데이터 레이블 보기

Experience Platform에서 만든 데이터 레이블은 데이터 보기 사용자 인터페이스의 세 위치에 표시됩니다.

| 위치 | 설명 |
| --- | --- |
| 스키마 필드의 정보 단추 | 이 단추를 클릭하면 다음 내용이 표시됩니다 [!UICONTROL 데이터 사용 레이블] 현재 필드에 적용:<p>![](assets/data-label-left.png) |
| 아래의 오른쪽 레일 [구성 요소 설정](/help/data-views/component-settings/overview.md) | 임의 [!UICONTROL 데이터 사용 레이블] 여기에 나열됩니다.<p>![](assets/data-label-right.png) |
| 데이터 레이블을 열로 추가 | 추가할 수 있습니다 [!UICONTROL 데이터 사용 레이블] 를 [!UICONTROL 포함된 구성 요소] 데이터 보기의 열. 열 선택기 아이콘을 클릭하고 를 선택하면 됩니다 **[!UICONTROL 데이터 사용 레이블]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## 데이터 보기의 데이터 거버넌스 레이블 필터링

데이터 보기 편집기에서 왼쪽 트레일의 필터 아이콘을 클릭하고 데이터 보기 구성 요소를 **[!UICONTROL 데이터 거버넌스]** 및 유형 **[!UICONTROL 레이블]**:

![](assets/filter-labels.png)

클릭 **[!UICONTROL 적용]** 어떤 구성 요소에 레이블이 부착되어 있는지 확인합니다.

## 데이터 보기의 데이터 거버넌스 정책 필터링

분석이나 내보내기를 위해 특정 CJA 데이터 보기 요소를 사용할 수 없도록 하는 정책이 설정되어 있는지 확인할 수 있습니다.

다시 왼쪽 레일과 아래의 필터 아이콘을 클릭합니다 **[!UICONTROL 데이터 거버넌스]**&#x200B;를 클릭합니다. **[!UICONTROL 정책]**:

![](assets/filter-policies.png)

클릭 **[!UICONTROL 적용]** 활성화되는 정책을 확인합니다.

## 활성화된 정책이 데이터 보기에 미치는 영향

만약 **[!UICONTROL Analytics 적용]** 또는 **[!UICONTROL 다운로드 적용]** 정책이 설정되어 있으면 연관된 특정 데이터 레이블(예: C8 또는 C12)이 있는 스키마 구성 요소는 데이터 보기에 추가할 수 없습니다.

이러한 구성 요소는 왼쪽 레일에서 회색으로 표시됩니다 [!UICONTROL 스키마 필드] 목록:

![](assets/component-greyed.png)

또한 데이터 보기에 차단된 필드가 있는 데이터 보기는 저장할 수 없습니다.

>[!MORELIKETHIS]
>[중요 데이터 다운로드](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[Report Builder에서 제한된 레이블은 무엇입니까?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=en)


