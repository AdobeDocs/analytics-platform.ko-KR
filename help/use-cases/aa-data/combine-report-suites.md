---
title: 보고서 세트를 다른 스키마와 결합
description: 데이터 준비를 사용하여 보고서 세트를 다른 스키마와 결합하는 방법 알아보기
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
feature: Use Cases
role: User
source-git-commit: 664576605b8be098a751609536e388c304c65513
workflow-type: tm+mt
source-wordcount: '1321'
ht-degree: 55%

---

# 보고서 세트를 다른 스키마와 결합

[Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)는 Real-time Customer Data Platform 및 Customer Journey Analytics(Customer Journey Analytics)와 같은 Adobe Experience Platform 애플리케이션에서 사용할 수 있도록 Adobe Analytics의 보고서 세트 데이터를 Adobe Experience Platform으로 가져옵니다. Adobe Experience Platform으로 가져온 각 보고서 세트는 개별 소스 연결 데이터 흐름으로 구성되며, 각 데이터 흐름은 Adobe Experience Platform 데이터 레이크 내에 데이터 세트로 들어옵니다. Analytics 소스 커넥터는 보고서 세트당 하나의 데이터 세트를 만듭니다.

Customer Journey Analytics 고객은 [연결](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html)을 사용하여 Adobe Experience Platform 데이터 레이크의 데이터 세트를 Customer Journey Analytics Analysis Workspace에 통합합니다. 그러나 연결 내에서 보고서 세트를 결합할 경우 보고서 세트 간의 스키마 차이는 Adobe Experience Platform [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko-KR) 기능을 사용하여 해결해야 합니다. 목적은 prop 및 eVar와 같은 Adobe Analytics 변수가 Customer Journey Analytics에서 일관된 의미를 갖도록 하는 것입니다.

## 보고서 세트 간의 스키마 차이가 문제가 됩니다.

회사에서 Customer Journey Analytics에서 사용하기 위해 두 개의 서로 다른 보고서 세트의 데이터를 Adobe Experience Platform으로 가져오려고 하며 두 보고서 세트의 스키마에 차이가 있다고 가정해 봅시다.

| 보고서 세트 A | 보고서 세트 B |
| --- | --- |
| eVar1 = 검색어 | eVar1 = 비즈니스 단위 |
| eVar2 = 고객 범주 | eVar2 = 검색어 |

단순성을 위해 두 보고서 세트에 대해 정의된 eVar는 이것이 유일하다고 가정하십시오.

또한 다음 작업을 수행한다고 가정합니다.

- Adobe Experience Platform 데이터 레이크에 **보고서 세트 A**&#x200B;를 **데이터 세트 A**(으)로 수집하는 Analytics 소스 연결을 만듭니다(데이터 준비 사용 안 함).
- Adobe Experience Platform 데이터 레이크에 **보고서 세트 B**&#x200B;를 **데이터 세트 B**(으)로 수집하는 Analytics 소스 연결을 만듭니다(데이터 준비 사용 안 함).
- 데이터 세트 A와 데이터 세트 B를 결합하는 **모든 보고서 세트**&#x200B;라는 [Customer Journey Analytics 연결](/help/connections/create-connection.md)을 만듭니다.
- 모든 보고서 세트 연결을 기반으로 하는 **전역 보기**&#x200B;라는 [Customer Journey Analytics 데이터 보기](/help/data-views/create-dataview.md)를 만듭니다.

데이터 세트 A와 데이터 세트 B 사이의 스키마 차이를 해결하기 위해 데이터 준비를 사용하지 않으면 글로벌 보기 데이터 보기의 eVar에 다음과 같은 혼합된 값이 포함됩니다.

| Customer Journey Analytics의 글로벌 보기 데이터 보기 |
| --- |
| eVar1 => 검색어와 비즈니스 단위의 혼합 |
| eVar2 => 고객 범주와 검색어의 혼합 |

이 경우 eVar1과 eVar2에 대한 보고서가 무의미해집니다.

- eVar 필드에는 의미론적 의미가 다른 값의 혼합이 포함됩니다.
- 검색어는 eVar1과 eVar2 사이에 배포됩니다.
- 각 검색어, 비즈니스 단위 및 고객 범주에 대해 다른 기여도 모델을 사용할 수 없습니다.

## Adobe Experience Platform 데이터 준비를 사용하여 보고서 세트 간 스키마 차이 해결

Experience Platform 데이터 준비 기능은 Analytics 소스 커넥터와 통합되어 있으며 위의 시나리오에서 설명한 스키마 차이를 해결하는 데 사용할 수 있습니다. 이렇게 하면 Customer Journey Analytics 데이터 보기에서 일관된 의미를 갖는 eVar가 생성됩니다. (아래에 사용된 명명 규칙은 사용자의 필요에 맞게 사용자 정의할 수 있습니다.)

1. 보고서 세트 A 및 보고서 세트 B에 대한 소스 연결 데이터 흐름을 만들기 전에 Adobe Experience Platform에서 [새 스키마를 만들기](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ko)합니다(이 예에서는 **통합 스키마**&#x200B;라고 함). 다음을 스키마에 추가합니다.

   | &quot;통합 스키마&quot; |
   | --- |
   | **XDM ExperienceEvent** 클래스 |
   | **Adobe Analytics ExperienceEvent 템플릿** 필드 그룹 |

1. 스키마에 다른 필드 그룹을 추가하거나 [사용자 정의 필드 그룹을 생성](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail)한 후 스키마에 추가합니다. 새 필드 그룹을 만들고 이를 **통합 필드**&#x200B;라고 부릅니다. 그런 후에 다음 필드를 새 필드 그룹에 추가합니다.

   | &quot;통합 필드&quot; 사용자 정의 필드 그룹  |
   | --- |
   | 검색어 |
   | 비즈니스 단위 |
   | 고객 범주 |

1. **보고서 세트 A**&#x200B;에 대한 소스 연결 데이터 흐름을 만들고 데이터 흐름에서 사용할 **통합 스키마**&#x200B;를 선택합니다. 다음과 같이 데이터 흐름에 사용자 정의 매핑을 추가합니다.

   | 보고서 세트 A 소스 필드 | 통합 필드 필드 그룹의 대상 필드 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >대상 필드의 XDM 경로는 사용자 정의 필드 그룹을 구성하는 방법에 따라 달라집니다.

1. **보고서 세트 B**&#x200B;에 대한 소스 연결 데이터 흐름을 만들고 데이터 흐름에서 사용할 **통합 스키마**&#x200B;를 다시 선택합니다. 워크플로는 두 필드에 설명자 이름이 충돌하는 것을 보여 줍니다. 이는 eVar1 및 eVar2의 설명자가 보고서 세트 A의 설명자와 보고서 세트 B의 설명자가 서로 다르기 때문입니다. 그러나 이미 이 사실을 알고 있으므로 충돌을 무시하고 다음과 같이 사용자 정의 매핑을 사용할 수 있습니다.

   | 보고서 세트 B 소스 필드 | 통합 필드 필드 그룹의 대상 필드 |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. 이제 데이터 세트 A와 데이터 세트 B를 결합하여 Customer Journey Analytics을 위한 **모든 보고서 세트** 연결을 만듭니다.

1. Customer Journey Analytics에서 **전역 보기** 데이터 보기를 만듭니다. 원래 eVar 필드는 무시하고 통합 필드 필드 그룹의 필드만 포함합니다.

   Customer Journey Analytics의 **전역 보기** 데이터 보기:

   | 소스 필드 | 데이터 보기에 포함하시겠습니까? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | 아니요 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 아니요 |
   | _\&lt;path>_.Search_term | 예 |
   | _\&lt;path>_.Customer_category  | 예 |
   | _\&lt;path>_.Business_unit | 예 |

이제 소스 보고서 세트에서 eVar1 및 eVar2를 세 개의 새 필드로 매핑했습니다. 데이터 준비 매핑을 사용할 때의 또 다른 이점은 이제 대상 필드가 의미가 적은 eVar 이름(eVar1, eVar2) 대신 의미론적으로 의미 있는 이름(검색어, 비즈니스 단위, 고객 범주)을 기반으로 한다는 것입니다.

>[!NOTE]
>
>통합 필드 사용자 정의 필드 그룹 및 관련 필드 매핑은 언제든지 기존 Analytics 소스 커넥터 데이터 흐름 및 데이터 세트에 추가할 수 있습니다. 그러나 이는 향후 데이터에만 영향을 미칩니다.

## 보고서 세트 그 이상

데이터 세트를 다른 스키마와 결합하는 데이터 준비의 기능은 Analytics 보고서 세트를 능가합니다. 다음 데이터를 포함하는 데이터 세트가 두 개 있다고 가정합시다.

| 데이터 세트 A = Analytics 소스 커넥터를 통한 Analytics 보고서 세트 |
| --- |
| `eVar1` => 고객 범주 |

| 데이터 세트 B = 콜 센터 데이터 |
| --- |
| Some_field => 고객 범주 |

데이터 준비를 사용하면 Analytics 데이터의 eVar 1에 있는 고객 범주와 콜 센터 데이터의 Some_field에 있는 고객 범주를 결합할 수 있습니다. 그렇게 할 수 있는 한 가지 방법이 있습니다. 또한 명명 규칙을 필요에 맞게 변경할 수 있습니다.

1. Adobe Experience Platform에서 스키마를 만듭니다. 다음을 스키마에 추가합니다.

   | &quot;확장된 스키마&quot; |
   | --- | 
   | **XDM 경험 이벤트** 클래스 |
   | **Adobe Analytics 경험 이벤트 템플릿** 필드 그룹 |

1. 새 필드 그룹을 만들고 스키마에 추가합니다. 필드를 필드 그룹에 추가합니다.

   | &quot;고객 정보&quot; 사용자 정의 필드 그룹  |
   | --- |
   | 고객 범주 |

1. **데이터 세트 A**&#x200B;에 대한 데이터 흐름을 만들어 **확장된 스키마**&#x200B;를 스키마로 선택합니다. 다음과 같이 데이터 흐름에 사용자 정의 매핑을 추가합니다.

   | 데이터 세트 A 소스 필드 | 고객 정보 필드 그룹의 대상 필드 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. **데이터 세트 B**&#x200B;에 대한 데이터 흐름을 만들어 다시 **확장된 스키마**&#x200B;를 스키마로 선택합니다. 다음과 같이 데이터 흐름에 사용자 정의 매핑을 추가합니다.

   | 데이터 세트 B 소스 필드 | 고객 정보 필드 그룹의 대상 필드 |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

1. 데이터 세트 A와 데이터 세트 B를 결합하는 Customer Journey Analytics 연결을 만듭니다.

1. 방금 만든 Customer Journey Analytics 연결을 사용하여 Customer Journey Analytics에서 데이터 보기를 만듭니다. 원래 eVar 필드는 무시하고 고객 정보 필드 그룹의 필드만 포함합니다.

   Customer Journey Analytics의 데이터 보기:

   | 소스 필드 | 데이터 보기에 포함하시겠습니까? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | 아니요 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 아니요 |
   | _\&lt;path>_.Customer_category | 예 |

## 데이터 준비 대 구성 요소 ID

위에서 설명한 대로 데이터 준비를 사용하면 여러 Adobe Analytics 보고서 세트에서 다른 필드를 함께 매핑할 수 있습니다. 이 기능은 여러 데이터 세트의 데이터를 단일 Customer Journey Analytics 연결로 결합하려는 경우 Customer Journey Analytics에 유용합니다. 그러나 보고서 세트를 별도의 Customer Journey Analytics 연결로 유지하되 이러한 연결 및 데이터 보기에서 하나의 보고서 세트를 사용하려는 경우 Customer Journey Analytics에서 기본 구성 요소 ID를 변경하면 스키마가 다르더라도 보고서가 호환되도록 할 수 있습니다. 자세한 내용은 [구성 요소 설정 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html)을 참조하십시오.

구성 요소 ID 변경은 Customer Journey Analytics 전용 기능이며 실시간 고객 프로필 및 RTCDP로 전송되는 Analytics 소스 커넥터의 데이터에는 영향을 주지 않습니다.
