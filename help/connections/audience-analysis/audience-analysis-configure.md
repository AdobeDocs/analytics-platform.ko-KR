---
title: 대상 분석 구성
description: 대상 분석을 구성하는 방법 알아보기
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 0db3f6f7-9d7e-41bf-8eb5-02e439bab10a
source-git-commit: 20ead546897ad517840f95a5ec4dcd7f830afe8c
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 14%

---

# 대상 분석 구성 {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="병합 정책"
>abstract="병합 정책은 여러 데이터 세트의 프로필 데이터를 대상 만들기에 사용되는 통합 고객 프로필로 결합합니다. 여러 병합 정책이 표시되고 어떤 정책을 선택할지 확실하지 않은 경우 &#39;기본 시간 기반&#39;을 선택합니다. 또는 데이터 팀에 문의하여 각 병합 정책과 연결된 대상을 확인하십시오."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-sandbox"
>title="샌드박스"
>abstract="올바른 Experience Platform 프로필 데이터 세트가 포함된 샌드박스를 선택합니다. 이러한 데이터 세트에는 Analysis Workspace에서 보고할 대상 데이터를 포함해야 합니다. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-person-id"
>title="개인 ID"
>abstract="스키마에서 개인 ID를 나타내는 필드를 선택합니다. 선택 항목은 ID로 표시되고 ID 네임스페이스가 있는 스키마의 필드 목록으로 제한됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-namespace"
>title="기본 ID 네임스페이스 사용"
>abstract="Customer Journey Analytics이 ID 맵에서 primary=true 속성으로 표시된 ID를 찾으려는 경우 이 옵션을 활성화하고 해당 ID를 해당 행의 개인 ID로 사용합니다. 이 ID는 Experience Platform에서 파티셔닝에 사용하는 기본 키입니다. <br/>이 옵션을 사용하지 않도록 설정한 경우 아래 ID 네임스페이스 필드에서 네임스페이스를 선택하십시오. Customer Journey Analytics은 각 행의 ID 맵에서 이 네임스페이스 키를 검색하고 해당 네임스페이스 아래의 ID를 해당 행의 개인 ID로 사용합니다."

<!-- markdownlint-enable MD034 -->

대상 분석을 사용하면 Experience Platform 프로필 데이터 세트의 대상 멤버십 데이터를 Customer Journey Analytics 연결로 수집할 수 있습니다. 대상은 Analysis Workspace에서 사용할 새 차원으로 사용할 수 있게 됩니다. 대상 분석에 대한 자세한 개요 정보는 [대상 분석 개요](/help/connections/audience-analysis/audience-analysis-overview.md)를 참조하십시오.

>[!IMPORTANT]
>
>대상 데이터는 매일 밤 재처리 및 생성되므로 전날(&quot;어제&quot;)에 대해서만 대상 데이터를 정확하게 분석하여 분석할 수 있습니다.
>
>대상은 대상 분석 구성을 만든 다음 날에 Customer Journey Analytics 데이터 보기에서 사용할 수 있습니다.

## 대상 분석 구성 만들기

대상 분석 구성을 만들 때는 분석할 Experience Platform 대상과 연결된 샌드박스 및 병합 정책을 선택합니다. Customer Journey Analytics은 새 조회 데이터 세트를 만든 다음 사용자가 선택한 연결에 조회 데이터 세트와 프로필 데이터 세트를 자동으로 추가합니다.

시스템 관리자만 대상 분석 구성을 만들 수 있습니다.

대상 분석 구성을 만들려면 다음 작업을 수행하십시오.

1. Customer Journey Analytics에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 대상 분석 구성]**&#x200B;을 선택합니다.

   ![대상 분석 기본 페이지](assets/audience-analysis-empty.png)

1. **[!UICONTROL 구성 만들기]**&#x200B;를 선택합니다.

   ![대상 분석 구성 만들기](assets/audience-analysis-create.png)

1. **[!UICONTROL 세부 정보]** 섹션에서 다음 정보를 지정하십시오.

   | 필드 | 설명 |
   |---------|----------|
   | **[!UICONTROL 이름]** | 구성의 이름을 지정합니다. |
   | **[!UICONTROL 샌드박스]** | 연결에 추가하려는 프로필 데이터 세트가 포함된 Experience Platform 샌드박스를 선택합니다. 단일 샌드박스는 최대 100개의 대상 분석 구성을 지원할 수 있습니다. <p>Adobe Experience Platform은 디지털 경험 애플리케이션을 개발하고 발전시키는 데 도움이 되는 단일 Platform 인스턴스를 별도의 가상 환경으로 분할하는 [샌드박스](https://experienceleague.adobe.com/ko/docs/experience-platform/sandbox/home)를 제공합니다. 샌드박스를 데이터 세트가 포함된 “데이터 사일로”로 간주할 수 있습니다. 샌드박스는 데이터 세트에 대한 액세스를 제어하는 데 사용됩니다.</p> |

1. **[!UICONTROL 프로필 데이터 집합]** 섹션에서 다음 정보를 지정하십시오.

   | 필드 | 설명 |
   |---------|----------|
   | **[!UICONTROL 병합 정책]** | 대상자 분석에 사용할 프로필 데이터 세트에 해당하는 병합 정책을 선택하십시오. <p>병합 정책 은 Adobe Experience Platform이 여러 데이터 세트의 프로필 데이터를 대상 만들기에 사용되는 통합 고객 프로필에 결합하는 방법을 결정합니다. 선택한 병합 정책은 대상자에 포함된 프로필 속성에 영향을 줍니다. 매일 Experience Platform에서 이 데이터의 스냅샷이 생성됩니다. 이 스냅샷은 특정 시점의 데이터에 대한 정적 보기를 제공하며 이벤트 데이터를 포함하지 않습니다.</p><p>여러 병합 정책이 표시되고 선택할 정책을 모를 경우 **[!UICONTROL 기본 시간 기반]** 병합 정책을 선택합니다. 각 병합 정책과 연결된 대상을 더 잘 이해하려면 데이터 팀에 문의하십시오.</p> |
   | **[!UICONTROL 프로필 데이터 세트]** | 선택한 병합 정책과 연결된 프로필 데이터 세트입니다. 이 프로필 데이터 세트에는 분석할 Experience Platform 대상 데이터가 포함되어 있습니다. 이 프로필 데이터 세트는 선택한 연결에 추가됩니다.<p>병합 정책을 선택하면 프로필 스냅샷 내보내기가 표시됩니다. 예: `Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`.</p><p>자세한 내용은 Experience Platform 대시보드 가이드의 [프로필 특성 데이터 세트](https://experienceleague.adobe.com/ko/docs/experience-platform/dashboards/query#profile-attribute-datasets)를 참조하십시오.</p> |

1. **[!UICONTROL 연결]** 섹션에서 **[!UICONTROL 연결 선택]**&#x200B;을 클릭합니다.

1. 연결 대화 상자에서 프로필 데이터 세트를 추가할 연결 옆의 확인란을 선택한 다음 **[!UICONTROL 연결 사용]**&#x200B;을 선택합니다.

   연결은 하나의 대상 분석 구성에만 연결할 수 있습니다.

1. 다음 정보를 지정하여 연결을 구성하십시오.

   | 필드 | 설명 |
   |---------|----------|
   | **[!UICONTROL 개인 ID]** | 스키마에서 개인 ID를 나타내는 필드를 선택합니다.<p>선택 항목은 ID로 표시되고 ID 네임스페이스가 있는 스키마의 필드 목록으로 제한됩니다. **[!UICONTROL IdentityMap]**&#x200B;이(가) 기본적으로 선택되어 있으며 대부분의 구성에 적합합니다. </p><p>선택할 개인 ID가 없는 경우, 하나 이상의 개인 ID가 스키마에 정의되어 있지 않음을 의미합니다. 자세한 내용은 [UI에서 ID 필드 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/ui/fields/identity)를 참조하십시오.</p> |
   | **[!UICONTROL 기본 ID 네임스페이스 사용]** | 이 옵션은 개인 ID로 **[!UICONTROL ID 맵]**&#x200B;을(를) 선택한 경우 표시됩니다. <p>Customer Journey Analytics이 ID 맵에서 primary=true 속성으로 표시된 ID를 찾으려는 경우 이 옵션을 활성화하고 해당 ID를 해당 행의 개인 ID로 사용합니다. 이 ID는 Experience Platform에서 파티셔닝에 사용하는 기본 키입니다. 이 ID는 Customer Journey Analytics 개인 ID로 사용하기에 가장 적합한 후보이기도 합니다(Customer Journey Analytics 연결에 데이터 세트가 구성되는 방법에 따라 다름).</p> |
   | **[!UICONTROL ID 네임스페이스]** | 이 옵션은 개인 ID로 **[!UICONTROL ID 맵]**&#x200B;을(를) 선택한 경우 표시됩니다. 기본 ID 네임스페이스를 사용하는 경우 이 옵션이 비활성화됩니다. <p>ID 네임스페이스는 [Experience Platform Identity Service](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/namespaces)의 구성 요소입니다. 네임스페이스는 ID가 연관되는 컨텍스트의 지표 역할을 합니다. 네임스페이스를 지정하면 Customer Journey Analytics에서 각 행의 ID 맵에서 이 네임스페이스 키를 검색하고 해당 네임스페이스 아래의 ID를 해당 행의 개인 ID로 사용합니다. Customer Journey Analytics에서는 모든 행을 전체 데이터 세트로 스캔하여 존재하는 네임스페이스를 확인할 수 없으므로 가능한 모든 네임스페이스가 드롭다운 메뉴에 표시됩니다. 데이터에 지정된 네임스페이스를 알아야 하지만 해당 네임스페이스는 자동으로 검색되지 않습니다.</p> |

   <!-- Add this when B2B releases for AuA **[!UICONTROL Account ID]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}|  (only displayed for account-based connections) The Account ID that is used to support account-based reporting for the dataset. -->

1. **[!UICONTROL 데이터 보기]** 섹션에서 **[!UICONTROL 데이터 보기 선택]**&#x200B;을 클릭합니다.

1. 데이터 보기 대화 상자에서 Analysis Workspace 내의 Experience Platform 대상 데이터를 분석할 때 사용할 하나 이상의 데이터 보기 옆의 확인란을 선택합니다. 이러한 데이터 보기는 보고를 위해 Experience Platform 대상 데이터로 자동으로 구성됩니다.

1. **[!UICONTROL 데이터 보기 사용]**&#x200B;을 선택합니다.

1. 구성을 만들려면 **[!UICONTROL 만들기]**&#x200B;를 선택하십시오.

   >[!IMPORTANT]
   >
   >프로필 데이터 세트는 하루에 한 번 업데이트되므로 대상 분석 구성을 만든 다음 날에 Customer Journey Analytics 데이터 보기에서 대상을 사용할 수 있습니다.


1. 24시간 후 [데이터 보기에서 대상 차원을 봅니다](#view-audience-dimensions-in-the-data-view). 선택한 데이터 보기에서 대상 차원을 사용할 수 있는지 확인합니다.

## 데이터 보기에서 대상 차원 보기

[대상 분석 구성을 만들기](#create-an-audience-analysis-configuration)한 후 구성 중에 선택한 데이터 보기에 대상 차원이 추가되었는지 확인할 수 있습니다.

데이터 보기에서 대상 차원을 보려면 데이터 보기가 할당된 제품 프로필의 제품 프로필 관리자여야 합니다. 자세한 내용은 [액세스 제어](/help/technotes/access-control.md)를 참조하십시오.

데이터 보기에서 대상 분석 차원을 보려면 다음 작업을 수행하십시오.

1. Customer Journey Analytics에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.

1. **[!UICONTROL 차원]** 섹션에서 이제 다음 차원을 사용할 수 있습니다.

   * **[!UICONTROL 대상 이름]**

   * **[!UICONTROL 대상 원본]**

   * **[!UICONTROL 종료된 대상 원본]**

   * **[!UICONTROL 종료된 대상 이름]**

   이러한 각 차원은 대상 분석 구성 중에 선택한 병합 정책과 연결된 프로필 데이터 세트에 추가되고, 각 차원은 생성된 새 조회 데이터 세트에 추가되었습니다.

   ![데이터 보기에서 사용할 수 있는 대상 차원](assets/audience-analysis-dataview-dataset.png)

1. Analysis Workspace에서 대상 분석 차원을 사용합니다.

   Analysis Workspace에서 데이터 보기를 사용할 수 있는 액세스 권한이 있는 사용자는 이제 새 차원을 보고 분석에 사용할 수 있습니다. Analysis Workspace에서 대상 분석 차원을 사용하는 방법에 대한 자세한 내용은 [Customer Journey Analytics에서 Experience Platform 대상 분석](/help/connections/audience-analysis/analyze-audiences.md)을 참조하십시오.
