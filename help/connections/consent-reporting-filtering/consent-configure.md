---
title: 동의 보고 및 필터링 구성
description: 프로비저닝 마법사를 사용하여 Customer Journey Analytics에서 연결에 대한 동의 보고와 선택적 수집 시간 필터링을 활성화하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8did: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 728
ht-degree: 2%

---

# 동의 보고 및 필터링 구성

시스템 관리자는 동의 보고 및 선택적으로 하나 이상의 연결에 대한 동의 필터링을 활성화할 수 있습니다. 개요 정보는 [동의 보고 및 필터링 개요](/help/connections/consent-reporting-filtering/consent-overview.md)를 참조하십시오.

>[!IMPORTANT]
>
>동의 필터링은 수집 시 동의하지 않는 방문자 데이터를 제외합니다. 필터링으로 제외된 데이터는 Customer Journey Analytics에 저장되지 않으며 이전 날짜에 대해 복구할 수 없습니다. 필터링을 활성화하기 전에 마케팅 액션 선택 사항을 주의 깊게 검토하십시오.

## 구성 만들기

동의 보고 및 필터링에 대한 구성을 만들 때 동의 정책 멤버십 데이터가 포함된 샌드박스 및 프로필 데이터 세트를 선택하고, 구성할 연결 또는 연결을 선택하고, 각 마케팅 작업에 대한 데이터를 필터링할지 여부를 선택합니다. 그런 다음 Customer Journey Analytics은 동의 정책 조회 데이터 세트와 동의 정책 구성 요소를 자동으로 만듭니다.

동의 보고 및 필터링 구성을 만들려면 다음 작업을 수행하십시오.

1. Customer Journey Analytics에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 동의 보고 및 필터링]**&#x200B;을 선택합니다.

1. **[!UICONTROL 구성 만들기]**&#x200B;를 선택합니다.

1. **[!UICONTROL 세부 정보]** 섹션에서 다음 정보를 지정하십시오.

   | 필드 | 설명 |
   |---------|----------|
   | **[!UICONTROL 이름]** | 구성의 이름을 지정합니다. |
   | **[!UICONTROL 샌드박스]** | 동의 정책 멤버십 데이터와 함께 프로필 데이터 세트가 포함된 Experience Platform 샌드박스를 선택합니다. <p>샌드박스당 최대 1개의 동의 정책 조회 데이터 세트가 있습니다. 동일한 샌드박스의 여러 구성이 동일한 조회 데이터 세트를 공유합니다.</p> |

1. **[!UICONTROL 프로필 데이터 세트]** 섹션에서 보고할 동의 정책 구성원 자격 데이터(`consentPoliciesIDMap` 필드)가 포함된 프로필 데이터 세트를 선택합니다. 동의 보고를 활성화하면 이 프로필 데이터 세트가 아직 일부가 아닌 경우 선택하는 연결에 추가됩니다.

1. **[!UICONTROL 연결]** 섹션에서 **[!UICONTROL 연결 선택]**&#x200B;을 선택하고 구성할 하나 이상의 연결 옆에 있는 확인란을 선택한 다음 **[!UICONTROL 연결 사용]**&#x200B;을 선택합니다.

   동의 보고 및 필터링은 연결 수준에서 적용됩니다. 구성된 연결의 모든 데이터 보기는 동일한 동작을 상속합니다.

1. **[!UICONTROL 데이터 보기]** 섹션에서 **[!UICONTROL 데이터 보기 선택]**&#x200B;을 클릭합니다.

1. 데이터 보기 대화 상자에서 동의 보고에 사용할 하나 이상의 데이터 보기 옆의 확인란을 선택합니다. 이러한 데이터 보기는 보고를 위해 Experience Platform 동의 데이터를 사용하여 자동으로 구성됩니다.

1. **[!UICONTROL 데이터 보기 사용]**&#x200B;을 선택합니다.

1. (선택 사항) **[!UICONTROL 필터링]** 섹션에서 다음 마케팅 작업에 대해 필터링을 활성화할 수 있습니다.

   >[!NOTE]
   >
   >마케팅 액션에 대한 필터링이 활성화된 경우 Customer Journey Analytics은 방문자가 해당 마케팅 액션에 적용되는 **모두** 동의 정책과 일치하는 경우에만 방문자의 데이터를 수집합니다. 자세한 내용은 [동의 보고 및 필터링 개요](/help/connections/consent-reporting-filtering/consent-overview.md)의 [동의 필터링](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering)을 참조하세요.

   | 마케팅 액션 | 설명 |
   |---------|----------|
   | **[!UICONTROL Analytics]** | Analysis Workspace의 표준 Customer Journey Analytics 보고에 사용되는 데이터를 필터링합니다. |
   | **[!UICONTROL 데이터 과학]** | 고급 분석, 머신 러닝 및 데이터 과학 사용 사례에 사용되는 데이터를 필터링합니다. |

1. 구성을 만들려면 **[!UICONTROL 만들기]**&#x200B;를 선택하십시오.

   보고를 활성화한 경우 Customer Journey Analytics이 자동으로 다음을 수행합니다.

   * 선택한 프로필 데이터 세트를 연결에 추가합니다.
   * 샌드박스에 대한 동의 정책 조회 데이터 세트를 생성하고(아직 존재하지 않는 경우) Experience Platform에서 정책 이름과 설명을 동기화합니다.
   * 구성된 연결 내의 데이터 보기에 동의 정책 구성 요소(차원, 지표 및 파생 필드)를 추가합니다.

1. 구성이 완료되면 [데이터 보기에서 동의 정책 구성 요소를 보고](#view-consent-policy-components-in-the-data-view)하여 사용 가능한지 확인하십시오.

## 데이터 보기에서 동의 정책 구성 요소 보기

[구성을 만들기](#create-a-configuration)한 후 구성된 연결 아래의 데이터 보기에 동의 정책 구성 요소가 추가되었는지 확인할 수 있습니다.

데이터 보기에서 동의 정책 구성 요소를 보려면 데이터 보기가 할당된 제품 프로필의 제품 프로필 관리자여야 합니다. 자세한 내용은 [액세스 제어](/help/technotes/access-control.md)를 참조하십시오.

데이터 보기에서 동의 정책 구성 요소를 보려면 다음 작업을 수행하십시오.

1. Customer Journey Analytics에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.

1. 구성된 연결과 연결된 데이터 보기를 엽니다.

1. **[!UICONTROL 차원]** 섹션에서 이제 다음 차원을 사용할 수 있습니다.

   * **[!UICONTROL 동의 정책 ID]**

   * **[!UICONTROL 정책 이름]**

   * **[!UICONTROL 정책 설명]**

1. **[!UICONTROL 지표]** 섹션에서 이제 다음 지표를 사용할 수 있습니다.

   * **[!UICONTROL 동의하는 방문자]**

   * **[!UICONTROL 동의가 있는 이벤트]**

   * **[!UICONTROL 고유 동의 정책]**

   <!-- TODO: Add a screenshot of the consent policy components in the data view (assets/consent-components-dataview.png). -->

1. Analysis Workspace에서 동의 정책 구성 요소를 사용합니다.

   Analysis Workspace의 데이터 보기에 액세스할 수 있는 사용자는 이제 새 구성 요소를 보고 분석에 사용할 수 있습니다. Analysis Workspace에서 동의 정책 구성 요소를 사용하는 방법에 대한 자세한 내용은 [동의 정책 데이터 분석](/help/connections/consent-reporting-filtering/consent-analyze.md)을 참조하십시오.
