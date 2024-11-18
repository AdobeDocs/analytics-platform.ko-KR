---
title: Customer Journey Analytics을 위해 Analytics 소스 커넥터에서 Web SDK로 이동
description: Customer Journey Analytics으로 업그레이드할 때 Analytics 소스 커넥터에서 웹 SDK로 이동하는 방법에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Customer Journey Analytics을 위해 Analytics 소스 커넥터에서 Web SDK로 이동

>[!NOTE]
> 
>[Customer Journey Analytics 업그레이드 확인 목록](https://gigazelle.github.io/cja-ttv/)의 질문에 답변할 때 이 페이지의 정보를 사용하십시오.

Analytics 소스 커넥터를 Customer Journey Analytics을 위한 유일한 구현으로 사용하는 데에는 고유한 단점이 있습니다. 조직이 이미 Analytics 소스 커넥터 구현만 사용하여 Customer Journey Analytics으로 업그레이드한 경우 웹 SDK 구현으로 이동하는 것이 좋습니다.

Adobe은 Web SDK의 새로운 구현(지속적인 데이터 수집을 위해)과 함께 Analytics 소스 커넥터(이전 데이터를 가져오는 경우)를 사용할 것을 권장합니다.

## Analytics 소스 커넥터만 사용할 때의 장단점을 이해합니다

Analytics 소스 커넥터 사용의 장점과 단점에 대한 자세한 내용은 [Analytics 소스 커넥터만 사용하여 Customer Journey Analytics으로 업그레이드](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)를 참조하십시오.

## Analytics 소스 커넥터에서 웹 SDK로 이동

다음은 Analytics 소스 커넥터에서 Analytics 소스 커넥터와 Web SDK 구현으로 구성된 구현으로 이동하는 높은 수준의 프로세스입니다.

1. 문서 [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)의 [자세한 권장 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)에 설명된 대로 Web SDK 구현을 만듭니다.

   웹 SDK 구현이 구성된 후 다음 단계를 계속 진행합니다.

1. 웹 SDK 구현에서 Adobe Analytics 스키마를 사용할지 XDM 스키마를 사용할지 결정합니다.

   자세한 내용은 [Customer Journey Analytics 스키마 선택](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)을 참조하세요.

1. (조건부) Adobe Analytics 스키마를 사용하려면 Analytics 소스 커넥터에 의해 자동으로 만들어진 데이터 세트를 Customer Journey Analytics 연결에 추가하십시오.

   자세한 내용은 [연결에 Analytics 소스 커넥터 데이터 세트 추가](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)를 참조하십시오.

1. (조건부) XDM 스키마를 만들려는 경우:

   1. [Analytics 원본 커넥터에 대한 XDM 스키마를 만듭니다](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

   1. 원래 Analytics 소스 커넥터로 자동으로 생성된 데이터 세트를 Customer Journey Analytics 연결에 추가합니다.

      자세한 내용은 [현재 Analytics 원본 커넥터의 데이터 집합을 연결에 추가](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)를 참조하십시오.

   1. 원래 Analytics 소스 커넥터를 삭제합니다. <!-- need to add steps somewhere about how to do this -->

   1. [새 Analytics 소스 커넥터를 만들고 필드를 매핑하십시오](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).








