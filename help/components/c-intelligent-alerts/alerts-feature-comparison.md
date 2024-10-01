---
description: 경고의 Customer Journey Analytics이 Adobe Analytics과 어떻게 다른지 알아봅니다.
title: 경고 기능 비교 Customer Journey Analytics 및 Adobe Analytics
feature: Workspace Basics
role: User, Admin
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 5%

---

# 경고 기능 비교

Customer Journey Analytics에서의 경고 사용 프로세스는 Adobe Analytics에서의 경고 사용 프로세스와 거의 동일합니다. 그러나 중요한 차이점이 있습니다. 다음 섹션에서는 주요 차이점에 대해 설명합니다.

## 시간별 경고는 Customer Journey Analytics에서 사용할 수 없습니다.

시간별 경고는 Adobe Analytics에서와 같이 Customer Journey Analytics에서 사용할 수 없습니다. Customer Journey Analytics에서는 알림을 매일, 매주 또는 매월로 구성할 수 있습니다.

Customer Journey Analytics에서 보고되기 전에 Adobe Experience Platform에 데이터를 수집할 수 있는 다양한 방법 때문입니다. 한 시간 이내에 데이터 완전성과 가용성을 안정적으로 달성할 수 없으므로 불완전한 데이터의 가능성이 높기 때문에 시간별 경고를 비현실적으로 만듭니다. 자세한 내용은 [데이터 수집 시간이 다릅니다](#data-ingestion-times-vary-in-customer-journey-analytics)를 참조하세요.

## 데이터 수집 시간은 Customer Journey Analytics에 따라 다릅니다

데이터를 완료하고 Customer Journey Analytics에서 보고할 수 있기까지 필요한 시간은 조직에 따라 다릅니다.

이는 다음과 같은 이유 때문입니다.

* 모든 종류의 데이터 스키마와 유형을 보유할 수 있는 플랫폼의 기능

  웹 데이터에서만 보고하는 Adobe Analytics과 달리 [다양한 유형의 데이터를 Adobe Experience Platform에 수집](/help/data-ingestion/data-ingestion.md)하여 Customer Journey Analytics에서 보고할 수 있으며 모든 유형의 데이터를 순차적으로 실시간으로 전송할 수는 없습니다.

* Platform 데이터 세트에 일괄 데이터 전달 지연

  일부 데이터를 더 빨리 보고할 수 있지만 모든 [일괄 처리 데이터는 Platform 데이터 세트](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.)에 수집됩니다. 일반적으로 데이터 이벤트 시간이 3~9시간 경과합니다. 경고가 정확하려면 데이터 세트에서 사용 가능한 모든 일괄 처리 데이터를 사용하여 데이터 수집을 완료해야 합니다. <!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

이러한 이유로, 수집할 수 있는 다양한 종류의 이벤트 데이터에 대한 데이터 수집은 일정 지연 후에만 완료되며, 일반적으로 데이터 이벤트 시간이 3~9시간 경과합니다. 경고가 정확하게 표시되려면 지정된 이벤트 범위에 대한 이벤트 데이터가 완료되어야 합니다. 즉, Adobe은 더 이상 지정된 이벤트 범위에 대한 이벤트 데이터를 받지 않습니다.

이러한 수집 시간 지연을 감안하기 위해 경고는 전송되기 전에 기본 지연 시간인 9시간을 갖습니다.

9시간의 기본 지연을 0에서 24시간 사이의 어느 곳으로든 조정할 수 있습니다. 그러나 지연 시간을 9시간 미만으로 줄이면 불완전한 데이터에 대해 보고하고 있으며, 이로 인해 경고 정보가 부정확해질 수 있습니다.

지연 조정 방법 및 조정 시 고려해야 할 요소에 대한 자세한 내용은 [경고 만들기](/help/components/c-intelligent-alerts/alert-builder.md)를 참조하십시오.

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Analysis Workspace에서 경고를 만드는 옵션을 사용할 수 없습니다

Adobe Analytics의 Analysis Workspace에서는 아래에 설명된 방법으로 Analysis Workspace에서 경고를 만들 수 있습니다. Customer Journey Analytics에서는 Analysis Workspace에서 경고를 생성하는 옵션을 아직 사용할 수 없습니다. 대신 [경고 만들기](/help/components/c-intelligent-alerts/alert-builder.md)에 설명된 대로 경고 빌더에 액세스하십시오.

Adobe Analytics에서는 다음 옵션을 사용할 수 있습니다.

* 자유 형식 테이블에서 하나 이상의 라인 항목을 선택한 다음 마우스 오른쪽 단추를 클릭하고 **[!UICONTROL 선택 항목으로 경고 만들기]**&#x200B;를 선택합니다.

  이렇게 하면 즉시 경고 빌더가 미리 채워져서 올바른 지표와 필터로 경고를 만듭니다.

* Analysis Workspace에서 프로젝트를 연 다음 **[!UICONTROL 구성 요소]** > **[!UICONTROL 경고 만들기]**&#x200B;를 선택합니다.

* Analysis Workspace에서 프로젝트를 연 다음 다음 단축키를 사용합니다.

  `ctrl (or cmd) + shift + a`






