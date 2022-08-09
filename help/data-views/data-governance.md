---
title: Adobe Experience Platform 데이터 거버넌스에 대한 CJA 지원
description: null
source-git-commit: 40b87cd748717124a355b030b17b1e3b6f94a99e
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---


# Adobe Experience Platform 데이터 거버넌스에 대한 CJA 지원

CJA와 의 통합 [Adobe Experience Platform 데이터 거버넌스](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) 에서는 중요한 CJA 데이터에 대한 레이블 지정 및 개인 정보 보호 정책을 적용할 수 있습니다.

Experience Platform이 사용하는 데이터 세트에서 만들어진 개인 정보 레이블 및 정책은 CJA 데이터 보기 워크플로우에서 표시할 수 있습니다. 이러한 레이블은 중요 필드에서 지표 및/또는 차원을 생성하는 사용자에게 중지하거나 경고 합니다.

또한 CJA에서 데이터를 내보낼 때(보고, 내보내기, API 등을 통해) 경고 또는 레이블이 추가되어 보고서에 특정 방식으로 처리되어야 하는 중요한 정보가 포함되어 있음을 사용자에게 알립니다.

이러한 통합을 통해 규정 준수를 보다 손쉽게 관리할 수 있습니다. 조직의 데이터 관리자는 사용을 제한하는 정책을 설정할 수 있습니다. 그 결과 CJA 사용자는 데이터 관리자가 정의한 정책을 준수한다는 것을 알고 데이터를 보다 안전하게 사용할 수 있습니다.

## Adobe Experience Platform의 레이블 지정 및 정책

Experience Platform에서 데이터 세트를 만들 때 만들 수 있습니다 [데이터 사용 레이블](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) 데이터 세트에 있는 일부 또는 모든 요소에 대해 를 사용할 수 있습니다. 지금까지 이러한 레이블은 CJA에서 노출되지 않았습니다. 이 릴리스를 사용하면 CJA에서 이러한 레이블을 볼 수 있습니다. CJA에 대한 특별한 관심 사항은 C8 레이블입니다. 이 레이블에는 &quot;데이터를 조직의 웹 사이트 또는 앱 측정에 사용할 수 없습니다.&quot;가 표시됩니다.

레이블 지정 자체가 이러한 데이터 사용 레이블이 적용된다는 것을 의미하지는 않습니다. 그것이 정책이 사용되는 것입니다. 를 통해 정책을 만듭니다 [정책 서비스 API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) Experience Platform에서 확인하십시오.

정책에는 두 가지 구성 요소가 있습니다. 데이터 레이블 및 데이터 소비자가 제한된 데이터 사용 정책의 컨텍스트 내에서 수행할 수 있는 마케팅 작업입니다. CJA의 컨텍스트에서 두 개의 Adobe 정의 [마케팅 작업](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) 중요 사항:

* Analytics - 조직의 사이트 또는 앱에서 소비자 사용 측정, 분석 및 보고와 같이, 분석 목적으로 데이터를 사용합니다.

* 데이터를 제3자로 내보내는 등의 Adobe 환경에서 이 데이터를 내보냅니다.

레이블과 마케팅 작업을 정책과 함께 연결한 다음 정책을 설정합니다. 이 정책은 레이블과 마케팅 작업을 수행하며 다음과 같이 말합니다. 이 제한을 적용합니다. CJA에는 두 개의 Adobe 정의 정책이 표시됩니다.

* Analytics 정책
* 정책 다운로드

## CJA 데이터 보기에서 데이터 레이블 보기

Experience Platform에서 만든 데이터 레이블은 데이터 보기 사용자 인터페이스의 세 위치에 표시됩니다.

| 위치 | 설명 |
| --- | --- |
| 스키마 필드의 정보 단추 | 이 단추를 클릭하면 현재 필드에 적용되는 데이터 사용 레이블 이 표시됩니다.<p>![](assets/data-label-left.png) |
| 아래의 오른쪽 레일 [구성 요소 설정](/help/data-views/component-settings/overview.md) | 모든 데이터 사용 레이블은 다음과 같습니다.<p>![](assets/data-label-right.png) |
| 데이터 레이블을 열로 추가 | 데이터 레이블 을 데이터 보기의 포함된 구성 요소 열에 열로 추가할 수 있습니다. 열 선택기 아이콘을 클릭하고 데이터 사용 레이블 을 선택하면 됩니다.<p>![](assets/data-label-column.png) |

### CJA에서 데이터 거버넌스 레이블 필터링

데이터 보기 편집기에서 왼쪽 트레일의 필터 아이콘을 클릭하고 데이터 거버넌스 레이블로 데이터 보기 구성 요소를 필터링합니다.

![](assets/filter-labels.png)

### CJA에서 데이터 거버넌스 정책 필터링

분석이나 내보내기를 위해 특정 CJA 데이터 보기 요소를 사용할 수 없도록 하는 정책이 설정되어 있는지 확인할 수 있습니다.

왼쪽 레일과 데이터 거버넌스에서 필터 아이콘을 다시 클릭하고 정책을 클릭합니다.

![](assets/filter-policies.png)

정책이 켜져 있으면 특정 데이터 레이블(예: C8)이 연결된 스키마 필드는 CJA Workspace 내에서 Analytics 또는 다운로드(예: pdf 이메일 또는 공유)에 사용할 수 없습니다.

참고

* 데이터 보기에 추가할 수 없습니다. 이러한 필드는 왼쪽 레일 스키마 필드 목록에서 회색으로 표시됩니다.
* 차단된 필드가 있는 데이터 보기는 저장할 수 없습니다.


