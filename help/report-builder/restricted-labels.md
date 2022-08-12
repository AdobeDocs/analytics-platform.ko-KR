---
title: Report Builder에서 제한된 레이블은 무엇입니까?
description: Report Builder에서 제한된 레이블에 대해 설명합니다.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
source-git-commit: 0e626b4072c68a69ae94dbfdfb53169aa34ca8ac
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 2%

---


# Report Builder의 제한된 레이블

일반적으로 Customer Journey Analytics의 데이터 거버넌스 관련 설정은 Adobe Experience Platform에서 상속됩니다. CJA와 Adobe Experience Platform 데이터 거버넌스 간의 통합을 통해 중요한 CJA 데이터에 레이블을 지정하고 개인 정보 정책을 적용할 수 있습니다.

Experience Platform이 사용하는 데이터 세트에서 만들어진 개인 정보 레이블 및 정책은 CJA 데이터 보기 워크플로우에서 표시할 수 있습니다. 이러한 레이블은 중요 필드에서 지표 및/또는 차원을 생성하는 사용자에게 중지하거나 경고 합니다. 데이터 세트에 대한 자세한 내용은 [데이터 세트 개요](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html)

또한 CJA에서 데이터를 내보낼 때(보고, 내보내기, API 등을 통해) 경고 또는 레이블이 추가되어 보고서에 특정 방식으로 처리되어야 하는 중요한 정보가 포함되어 있음을 사용자에게 알립니다.

이러한 통합을 통해 규정 준수를 보다 손쉽게 관리할 수 있습니다. 조직의 데이터 관리자는 사용을 제한하는 정책을 설정할 수 있습니다. 그 결과 CJA 사용자는 데이터 관리자가 정의한 정책을 준수한다는 것을 알고 데이터를 보다 안전하게 사용할 수 있습니다.

자세한 내용은 [Customer Journey Analytics 및 데이터 거버넌스](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)

## Report Builder에서 제한된 데이터 보기

>[!NOTE]
>
>이 기능은 현재 [제한적인 테스트](/help/release-notes/releases.md)가 실시되고 있습니다.

보고, 다운로드 및 공유에 영향을 주는 두 개의 Adobe 정의 정책이 CJA에 표시됩니다.

* Analytics 정책 적용
* 다운로드 정책 적용

이러한 정책의 영향을 받는 구성 요소는 회색으로 표시됩니다. 정책이 적용된 구성 요소 위로 마우스를 가져가면 다음을 나타내는 메모가 표시됩니다. **이 데이터의 사용을 금하는 정책을 이 필드에 적용했습니다.** 자세한 내용은 [레이블 및 정책](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html).

![](assets/rb-restricted-label.png)

## 제한된 데이터가 포함된 보고서 업데이트

사용자가 나중에 제한된 데이터 요소를 사용하여 Report Builder 보고서를 만든 경우 보고서를 새로 고치면 오류 메시지가 표시됩니다.

![](assets/error-restricted-data.png)
