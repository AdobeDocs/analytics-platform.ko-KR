---
title: Customer Journey Analytics를 위해 Analytics 소스 커넥터에서 Web SDK로 전환
description: Customer Journey Analytics로 업그레이드할 때 Analytics 소스 커넥터에서 Web SDK로 전환하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '538'
ht-degree: 100%

---

# Customer Journey Analytics를 위해 Analytics 소스 커넥터에서 Web SDK로 전환 {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Analytics 소스 커넥터 구현"
>abstract="Analytics 소스 커넥터를 사용하면 Customer Journey Analytics를 손쉽게 활용할 수 있지만 Adobe Analytics와 Customer Journey Analytics를 모두 구독해야 합니다. 이 안내서는 독립적인 Web SDK 구현으로 전환하는 방법을 설명합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="기존의 Analytics 소스 커넥터 삭제"
>abstract="현재 사용 중인 Analytics 소스 커넥터는 조직의 사용자 정의 스키마와 호환되지 않습니다. 그러나 데이터는 여전히 Analytics 보고서 세트에 존재합니다. 이 단계는 현재 Analytics 소스 커넥터를 제거하여 이후 단계에서 올바른 스키마를 사용하여 다시 생성할 수 있게 합니다.<br><br>소스 커넥터를 삭제하기 전에 조직 내 다른 사용자와 협력하여 소스 커넥터 제거가 조직 내 보고에 영향을 미치지 않도록 확인하십시오. 이 조정을 완료하는 데 몇 주가 소요될 수 있습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Customer Journey Analytics의 유일한 구현으로 Analytics 소스 커넥터를 사용하는 데는 본질적인 단점이 있습니다.

조직에서 이미 Analytics 소스 커넥터 구현만을 사용하여 Customer Journey Analytics로 업그레이드한 경우, 지속적인 데이터 수집을 위해 Web SDK의 새로운 구현으로 전환하고, Analytics 소스 커넥터는 내역 데이터에만 사용하는 것이 좋습니다.

## Analytics 소스 커넥터만 사용하는 것의 장단점 이해

Analytics 소스 커넥터를 사용하는 데 따른 장단점에 대한 자세한 내용은 [Analytics 소스 커넥터만 사용하여 Customer Journey Analytics로 업그레이드](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)를 참조하십시오.

## Analytics 소스 커넥터에서 Web SDK로 전환

다음은 Analytics 소스 커넥터를 독점적으로 사용하는 것에서 Analytics 소스 커넥터와 Web SDK 구현으로 구성된 구현으로 전환하기 위한 상위 수준의 프로세스입니다.

1. [Adobe Analytics에서 Customer Journey Analytics로 업그레이드](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) 문서의 [자세한 권장 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)에 설명된 대로 Web SDK 구현을 만듭니다.

   Web SDK 구현이 구성된 후 다음 단계를 계속 진행합니다.

1. [Analytics 소스 커넥터용 XDM 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Analytics 소스 커넥터에서 각 Adobe Analytics 차원을 Web SDK 스키마의 차원으로 매핑합니다.

   1. 
      <!-- how do you get here -->

   1. **[!UICONTROL 표준 필드 매핑]** 섹션에서 **[!UICONTROL 사용자 정의]** 탭을 선택합니다.

   1. **[!UICONTROL 새 매핑 추가]**&#x200B;를 선택합니다.

      ![스키마 필드 매핑](assets/schema-mapping.png)

   1. **[!UICONTROL 소스 필드]**&#x200B;의 Adobe Analytics ExperienceEvent Template 필드 그룹에서 Adobe Analytics 필드를 선택합니다. 그 다음 **[!UICONTROL 대상 필드]**&#x200B;에서 매핑하려는 XDM 필드를 선택합니다.

   1. Adobe Analytics에서 데이터를 수집하는 데 사용하는 Adobe Analytics ExperienceEvent Template 필드 그룹의 각 필드에 대해 이 과정을 반복합니다.

1. 원래 Analytics 소스 커넥터를 사용하여 자동으로 생성된 데이터 세트를 Customer Journey Analytics 연결에 추가합니다.

   자세한 내용은 [현재 Analytics 소스 커넥터의 데이터 세트를 연결에 추가](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)를 참조하십시오.

1. (조건부) 조회 데이터 세트를 사용하는 경우, 조회 데이터 세트를 생성하고 연결에 추가해야 합니다. 자세한 내용은 [Customer Journey Analytics에서 데이터를 분류하기 위한 조회 데이터 세트 만들기](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)를 참조하십시오.

1. 원래 Analytics 소스 커넥터를 삭제합니다. <!-- need to add steps somewhere about how to do this -->

1. [새 Analytics 소스 커넥터 및 맵 필드 만들기](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

{{upgrade-final-step}}
