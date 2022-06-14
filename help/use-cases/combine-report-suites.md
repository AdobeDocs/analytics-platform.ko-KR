---
title: 보고서 세트와 다른 스키마 결합
description: 데이터 준비를 사용하여 보고서 세트를 다른 스키마와 결합하는 방법을 알아봅니다
source-git-commit: 02483345326180a72a71e3fc7c60ba64a5f8a9d6
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 3%

---


# 보고서 세트를 다른 스키마와 결합

다음 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko) Real-time Customer Data Platform 및 CJA(Customer Journey Analytics)과 같은 AEP 애플리케이션에서 사용할 수 있도록 Adobe Analytics의 AEP(Adobe Experience Platform)으로 보고서 세트 데이터를 가져옵니다. AEP로 가져온 각 보고서 세트는 개별 소스 연결 데이터 플로로 구성되고 각 데이터 플로우는 AEP 데이터 레이크 내에 데이터 세트로 이동합니다. Analytics 소스 커넥터는 보고서 세트당 하나의 데이터 세트를 만듭니다.

CJA 고객이 [연결](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ko) aep 데이터 레이크의 데이터 세트를 CJA의 Analysis Workspace에 통합합니다. 하지만 연결 내에 보고서 세트를 결합할 때 AEP의 [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko-KR) 기능을 사용할 수 있습니다. 목적은 prop 및 eVar와 같은 Adobe Analytics 변수가 CJA에서 일관된 의미를 갖도록 하는 것입니다.

## 보고서 세트 간의 스키마 차이점은 문제입니다

회사가 CJA에서 사용하기 위해 서로 다른 두 보고서 세트의 데이터를 AEP로 가져오려고 하며 두 보고서 세트의 스키마에 차이가 있다고 가정해 보십시오.

| 보고서 세트 A | 보고서 세트 B |
| --- | --- |
| eVar1 = 검색어 | eVar1 = 비즈니스 단위 |
| eVar2 = 고객 카테고리 | eVar2 = 검색어 |

단순성을 위해 두 보고서 세트 모두에 대해 유일하게 정의된 eVar라고 가정해 보겠습니다.

또한 다음 작업을 수행한다고 가정합니다.

- 수집하는 Analytics 소스 연결(데이터 준비 없이)을 만듭니다 **보고서 세트 A** 로서의 AEP Data Lake **데이터 세트 A**.
- 수집하는 Analytics 소스 연결(데이터 준비 없이)을 만듭니다 **보고서 세트 B** 로서의 AEP Data Lake **데이터 세트 B**.
- 만들기 [CJA 연결](/help/connections/create-connection.md) called **모든 보고서 세트** 데이터 세트 A와 데이터 세트 B를 결합합니다.
- 만들기 [CJA 데이터 보기](/help/data-views/create-dataview.md) called **전역 보기** 이것은 모든 보고서 세트 연결을 기반으로 합니다.

데이터 준비 를 사용하여 데이터 세트 A와 데이터 세트 B 간의 스키마 차이점을 해결하지 않으면 글로벌 보기 데이터 보기의 eVar에 값 혼합이 포함됩니다.

| CJA의 글로벌 보기 데이터 보기 |
| --- |
| eVar1 => 검색어와 비즈니스 단위의 혼합 |
| eVar2 => 고객 카테고리와 검색어의 혼합 |

이 경우 eVar1 및 eVar2에 대한 의미 없는 보고서가 발생합니다.

- eVar 필드는 의미가 다른 값의 혼합을 포함합니다.
- 검색어는 eVar1과 eVar2 간에 배포됩니다.
- 각 검색어, 비즈니스 단위 및 고객 카테고리에 대해서는 서로 다른 속성 모델을 사용할 수 없습니다.

## AEP 데이터 준비를 사용하여 보고서 세트 간의 스키마 차이를 해결합니다

Experience Platform 데이터 준비 기능은 Analytics 소스 커넥터와 통합되며 위의 시나리오에 설명된 스키마 차이점을 해결하는 데 사용할 수 있습니다. 따라서 CJA 데이터 보기에서 일관된 의미가 있는 eVar가 만들어집니다. (아래 사용된 이름 지정 규칙을 필요에 맞게 사용자 지정할 수 있습니다.)

1. 보고서 세트 A 및 보고서 세트 B에 대한 소스 연결 데이터 흐름을 만들기 전에 [사용자 지정 필드 그룹 만들기](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail.) AEP에서 (We&#39;ll call it) **통합 필드** 예제에서는 다음 필드를 포함합니다.

   | &quot;통합 필드&quot; 사용자 지정 필드 그룹  |
   | --- |
   | 검색어 |
   | 비즈니스 단위 |
   | 고객 카테고리 |

1. [새 스키마 만들기](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) AEP에서 (We&#39;ll call it) **통합 스키마** 이 예제에서는 입니다.) 다음 필드 그룹을 스키마에 추가합니다.

   | &quot;통합 스키마&quot;에 대한 필드 그룹 |
   | --- |
   | XDM 경험 이벤트 |
   | Adobe Analytics 경험 이벤트 템플릿 |
   | 통합 필드 |

   소스 연결 데이터 흐름을 만들 때 **보고서 세트 A**, 선택 **통합 스키마** 데이터 플로우에서 사용할 수 있습니다.

1. 다음과 같이 사용자 지정 매핑을 추가합니다.

   | 보고서 세트 소스 필드 | 통합 필드 그룹의 대상 필드 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >대상 필드의 XDM 경로는 사용자 지정 필드 그룹을 설정하는 방법에 따라 다릅니다.

1. 소스 연결 데이터 흐름을 만들 때 **보고서 세트 B**, 다시 선택합니다. **통합 스키마** 데이터 플로우에서 사용할 수 있습니다.

   워크플로우에서는 두 필드에 설명자 이름 충돌이 있음을 보여줍니다. 이것은 eVar1 및 eVar2의 설명자가 보고서 세트 A에 있었던 설명자와 보고서 세트 B에 있는 설명자가 다르기 때문입니다. 하지만 이미 알고 있으므로 충돌을 무시하고 다음과 같이 사용자 정의 매핑을 사용할 수 있습니다.

   | 보고서 세트 B 소스 필드 | 통합 필드 그룹의 대상 필드 |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. 이제 **모든 보고서 세트** 데이터 세트 A와 데이터 세트 B를 결합한 CJA용 연결입니다.

1. 만들기 **전역 보기** cja의 데이터 보기.

   원래 eVar 필드를 무시하고 통합 필드 그룹의 필드만 포함합니다.

   CJA의 전역 보기 데이터 보기:

   | 소스 필드 | 데이터 보기에 를 포함하시겠습니까? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | 아니요 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 아니요 |
   | _\&lt;path>_.Search_term | 예 |
   | _\&lt;path>_.Customer_category  | 예 |
   | _\&lt;path>_.Business_unit | 예 |

   이제 소스 보고서 세트의 eVar1 및 eVar2를 3개의 새 필드에 매핑했습니다. 데이터 준비 매핑을 사용하는 또 다른 이점은 대상 필드가 이제 덜 의미 있는 eVar 이름(eVar1, eVar2) 대신 의미상 이름(검색어, 비즈니스 단위, 고객 카테고리)을 기반으로 한다는 것입니다.

   >[!NOTE]
   >
   >통합 필드 사용자 지정 필드 그룹 및 관련 필드 매핑을 기존 Analytics 소스 커넥터 데이터 흐름 및 데이터 세트에 언제든지 추가할 수 있습니다. 하지만 이는 앞으로 진행될 데이터만 영향을 줍니다.

## 보고서 세트 이상

데이터 준비에서 다른 스키마와 데이터 세트를 결합하는 기능은 Analytics 보고서 세트를 벗어납니다. 다음 데이터가 포함된 데이터 세트가 두 개 있다고 가정합니다.

| 데이터 세트 A = Analytics 소스 커넥터를 통한 Analytics 보고서 세트 |
| --- |
| `eVar1` => 고객 카테고리 |

| 데이터 세트 B = 콜 센터 데이터 |
| --- |
| Some_field => 고객 범주 |

데이터 준비를 사용하여 Analytics 데이터의 eVar 1에서 고객 카테고리를 콜 센터 데이터의 Some_field에서 고객 카테고리와 결합할 수 있습니다. 한 가지 방법이 있습니다. 필요에 따라 이름 지정 규칙을 변경할 수 있습니다.

1. 사용자 지정 필드 그룹을 만듭니다.

   | &quot;고객 정보&quot; 사용자 지정 필드 그룹  |
   | --- |
   | Customer_category |

1. AEP에서 스키마를 만듭니다. 다음 필드 그룹을 스키마에 추가합니다.

   | 확장 스키마에 대한 필드 그룹 |
   | --- | 
   | XDM 경험 이벤트 |
   | Adobe Analytics 경험 이벤트 템플릿 |
   | 고객 정보 |

1. 데이터 흐름을 만들 때 **데이터 세트 A**, 선택 **확장 스키마** 를 스키마 로 사용합니다.

1. 다음과 같이 사용자 지정 매핑을 추가합니다.

   | 데이터 집합 소스 필드 | 고객 정보 필드 그룹의 대상 필드 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. 데이터 흐름을 만들 때 **데이터 세트 B**, 다시 선택합니다. **확장 스키마** 를 스키마 로 사용합니다.

1. 다음과 같이 사용자 지정 매핑을 추가합니다.

   | 데이터 집합 B 소스 필드 | 고객 정보 필드 그룹의 대상 필드 |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

   데이터 세트 A와 데이터 세트 B를 결합하는 CJA 연결을 만듭니다. 방금 만든 CJA 연결을 사용하여 CJA에서 데이터 보기를 만듭니다 . 원래 eVar 필드를 무시하고 고객 정보 필드 그룹의 필드만 포함합니다.

   CJA의 데이터 보기:

   | 소스 필드 | 데이터 보기에 를 포함하시겠습니까? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | 아니요 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 아니요 |
   | _\&lt;path>_.Customer_category | 예 |

## 데이터 준비와 구성 요소 ID 비교

위에 설명된 대로 데이터 준비를 사용하면 여러 Adobe Analytics 보고서 세트에 서로 다른 필드를 함께 매핑할 수 있습니다. 이 기능은 여러 데이터 세트의 데이터를 단일 CJA 연결로 결합하려는 경우 CJA에서 유용합니다. 그러나 보고서 세트를 별도의 CJA 연결에 보관하려고 하지만 그러한 연결 및 데이터 보기에서 한 세트의 보고서를 사용하려는 경우 CJA에서 기본 구성 요소 ID를 변경하면 스키마가 다른 경우에도 보고서가 호환될 수 있습니다. 자세한 내용은 [구성 요소 설정](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) 추가 정보.

구성 요소 ID 변경은 CJA 전용 기능이며 실시간 고객 프로필 및 RTCDP로 전송되는 Analytics 소스 커넥터의 데이터에는 영향을 주지 않습니다.

