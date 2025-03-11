---
title: Customer Journey Analytics에 사용할 스키마 설계
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 26%

---

# Customer Journey Analytics에 사용할 스키마 설계 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="스키마 설계"
>abstract="조직 내에서 데이터 수집 요구 사항에 대해 논의하고 Adobe Experience Platform에서 사용할 스키마를 빌드하는 방법을 결정합니다. 이 단계는 조직에 맞춘 스키마를 사용하는 권장 프로세스를 사용하고자 하기 때문에 나타납니다. 이 단계를 올바르게 수행하는 것이 매우 중요합니다. 조직 내 모든 팀이 일치하는 스키마를 적용하면 데이터 수집이 훨씬 쉬워지기 때문입니다.<br><br>조직 내 모든 관련 당사자들이 통합된 스키마를 구성하는 데 걸리는 예상 시간은 1~2개월입니다. 이 기간은 조정해야 하는 팀의 수와 정렬할 차원과 지표의 수에 따라 크게 달라집니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe에서는 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 웹 SDK과 함께 사용할 사용자 지정 XDM(경험 데이터 모델) 스키마를 생성할 것을 권장합니다. 또는 Adobe Analytics ExperienceEvent 필드 그룹을 사용하는 기본 Adobe Analytics 스키마를 사용할 수 있습니다.

사용자 지정 XDM 스키마를 사용하면 조직의 요구 사항과 사용하는 특정 Platform 애플리케이션에 맞게 조정된 간소화된 스키마를 사용할 수 있습니다. Adobe Analytics ExperienceEvent 필드 그룹을 사용하는 기본 Adobe Analytics 스키마와 달리, 사용자 지정 XDM 스키마에 대한 변경이 필요한 경우 업데이트가 필요한 필드를 찾기 위해 수천 개의 사용되지 않은 필드를 이동할 필요가 없습니다.

이러한 스키마 옵션에 대한 자세한 내용은 [Customer Journey Analytics에 대한 스키마 선택](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)을 참조하십시오.

XDM 스키마 아키텍처를 시작할 때 다음 섹션을 검토하십시오.

## XDM 스키마에서 Adobe Analytics 제한 방지

Customer Journey Analytics의 기본 아키텍처는 Adobe Analytics보다 훨씬 더 많은 유연성을 제공합니다. 새로운 XDM 스키마를 만드는 것은 그러한 유연성을 여는 핵심 방법입니다. Customer Journey Analytics으로 업그레이드할 때 불필요한 Adobe Analytics 제한 사항을 스키마에 전달하지 않도록 하십시오.

>[!NOTE]
>
>다음 정보는 아직 완료되지 않았습니다. 그것은 가까운 장래에 완성될 것이다.

| Adobe Analytics 데이터 아키텍처 | XDM 스키마 아키텍처 |
|---------|----------|
| 개별 지표가 Analytics 데이터 아키텍처에 추가됩니다.<br/>예를 들어 Adobe Analytics의 경우 각 이벤트에 대해 다른 eVar이 있습니다. | XDM 스키마가 아닌 데이터 보기에서 개별 지표를 만듭니다. 이렇게 하면 나중에 변경해야 하는 경우에서 보다 유연하게 수행할 수 있습니다.<br/>예를 들어 Customer Journey Analytics의 경우 스키마에 단일 이벤트가 있으며 데이터 보기에서 이벤트 만들기를 사용합니다. |
| 사용자 지정 변수를 만들려면 prop 및 eVar가 필요합니다. |  |

## 조직 전체에서 데이터 팀 및 기타 관련자 식별

>[!NOTE]
>
>이 정보는 아직 이용할 수 없습니다. 가까운 시일 내에 사용할 수 있습니다.

## 조직에서 사용되는 다른 Adobe Experience Platform 애플리케이션 고려

>[!NOTE]
>
>이 정보는 아직 이용할 수 없습니다. 가까운 시일 내에 사용할 수 있습니다.
