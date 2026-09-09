---
title: AppMeasurement 또는 태그에서 XDM으로 마이그레이션
description: AppMeasurement 또는 태그에서 XDM으로 마이그레이션에 대해 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
source-git-commit: db34e721f156b3eb0aab20b2dca57e194c83d6fb
workflow-type: tm+mt
source-wordcount: '2379'
ht-degree: 5%

---

# 태그에서 XDM으로 마이그레이션 {#upgrade-migration-planner}

{{upgrade-note-step}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_intro"
>title="마이그레이션 개요"
>abstract="Customer Journey Analytics으로 업그레이드할 때 Tags 구현을 Adobe Experience Platform Web SDK으로 마이그레이션하십시오.<br/>기존 마이그레이션을 계속하거나 새 마이그레이션을 시작하십시오."

<!-- markdownlint-enable MD034 -->

Migration Planner는 스키마 생성을 포함하여 태그에서 XDM으로의 마이그레이션을 자동화하는 마이그레이션 마법사를 제공합니다. 이러한 작업은 Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 작업과 관련하여 가장 복잡하고 시간이 오래 걸리는 작업 중 일부입니다.

## 지원되는 Adobe Analytics 구현

마이그레이션 플래너는 Analytics 확장(태그)을 사용하는 Adobe Analytics 구현을 지원합니다.

마이그레이션 플래너는 AppMeasurement 또는 Experience Platform 웹 SDK을 사용하는 Adobe Analytics 구현에 사용할 수 없습니다.

## 마이그레이션 플래너에 포함된 업그레이드 작업

Migration Planner는 다음과 같은 복잡하고 시간이 많이 소요되는 업그레이드 작업을 자동화하는 마이그레이션 마법사를 제공합니다.

* **XDM 스키마 만들기**: Adobe Analytics 보고서 세트 변수를 기반으로 하는 새 XDM 스키마를 자동으로 만듭니다. 마이그레이션 플래너는 Adobe Analytics 보고서 세트 변수를 지능적으로 스캔한 다음 해당 정보를 사용하여 XDM에서 필요한 필드를 만듭니다. 결과 XDM 스키마에는 Customer Journey Analytics 스키마에 필요한 필드만 포함됩니다.

  또는 기존 XDM 스키마를 지정하거나 처음부터 XDM 스키마를 만들 수 있습니다.

  +++ 처음부터 XDM 스키마를 만들도록 선택하는 경우 이 섹션을 확장하여 유용한 리소스에 대한 정보를 확인할 수 있습니다.

  * [XDM 스키마 아키텍처 계획 수립](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}.

  * [Adobe Experience Platform에 원하는 사용자 정의 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}.

    스키마를 생성할 때 다음 옵션을 고려합니다.

    * Customer Journey Analytics를 RTCDP와 통합하려면 [Customer Journey Analytics에 사용할 XDM 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}에 설명된 대로 스키마에서 **[!UICONTROL 프로필]** 옵션을 활성화해야 합니다. 이 옵션을 활성화한 후 데이터가 이 스키마를 기반으로 데이터 세트로 수집되면 해당 데이터는 실시간 고객 프로필에 병합됩니다.

    * 스트리밍 미디어 데이터를 포함하려면 [스트리밍 데이터를 수집하고 사용하도록 스키마를 구성](/help/data-ingestion/streaming.md){target="_blank"}해야 합니다.

    +++

  * **Adobe Analytics 구현을 웹 SDK으로 마이그레이션**: Adobe Analytics 구현에서 태그를 사용하든 JavaScript을 사용하든 마이그레이션 플래너는 Experience Platform 웹 SDK으로의 마이그레이션을 안내합니다.

    * **AppMeasurement에서 웹 SDK으로 태그 속성 마이그레이션**:

    * **JavaScript 구현을 AppMeasurement에서 웹 SDK JavaScript 라이브러리로 마이그레이션**

  * **Customer Journey Analytics에서 데이터 보기 만들기**: 만들어진 XDM 스키마 필드를 기반으로 데이터 보기를 자동으로 만들고 구성 요소로 채웁니다.


## 시작하기에 앞서

마이그레이션을 만들기 전에 다음 사항이 있는지 확인하십시오.

* 지원되는 Adobe Analytics 구현(태그용 Analytics 확장). [지원되는 Adobe Analytics 구현](#supported-adobe-analytics-implementations)을 참조하세요.

* 로그인한 Experience Cloud 조직에서 마이그레이션할 Adobe 태그 속성에 액세스합니다.

* XDM에 매핑할 변수가 있는 Adobe Analytics 보고서 세트에 액세스합니다.

* Adobe Experience Platform에서 스키마를 만들 수 있는 권한입니다.

<!-- Confirm the exact roles and permissions required to use the Migration Planner and to create schemas and Data Views. -->

## Analytics 구현을 웹 SDK으로 마이그레이션

마이그레이션이 [!UICONTROL **감사**], [!UICONTROL **매핑**], [!UICONTROL **구현**]&#x200B;의 세 단계로 이동합니다. 다음 단계를 사용하여 마이그레이션을 만든 다음 [마이그레이션 유효성 검사 및 배포](#validate-and-deploy-a-migration)를 계속 진행하여 각 단계를 완료하십시오.

1. Customer Journey Analytics에서 [!UICONTROL **마이그레이션 플래너**]&#x200B;를 엽니다.

   <!-- Confirm the exact navigation path to open the Migration Planner in Customer Journey Analytics. -->

1. 마이그레이션 플래너의 [!UICONTROL **마이그레이션**] 탭에서 [!UICONTROL **새로 만들기**]&#x200B;를 선택합니다.

   ![마이그레이션 유형을 선택하고 마이그레이션 이름을 입력할 수 있는 새 마이그레이션 대화 상자입니다.](assets/migration-planner-new-migration.png)

1. 다음 정보를 지정합니다.

   | 필드 이름 | 함수 |
   | --------- | ---------- |
   | [!UICONTROL **이름**] | 이 마이그레이션의 이름을 지정합니다. |
   | [!UICONTROL **설명**] | 이 마이그레이션에 대한 선택적 설명을 지정하십시오. |
   | [!UICONTROL **태그 속성**] | 마이그레이션할 Adobe 태그 속성을 선택합니다. 자세한 내용은 Experience Platform 설명서의 [속성](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/admin/companies-and-properties){target="_blank"}을 참조하십시오. |
   | [!UICONTROL **태그 라이브러리**] | 마이그레이션의 기반이 되는 태그 라이브러리 스냅샷을 선택합니다. 스냅샷은 사용되는 태그 라이브러리의 버전을 결정합니다. 자세한 내용은 Experience Platform 설명서에서 [게시 개요](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/publish/overview){target="_blank"}를 참조하십시오. |

1. [!UICONTROL **마이그레이션 이름**] 필드에서 이 마이그레이션의 이름을 지정한 다음 [!UICONTROL **다음**]&#x200B;을 선택합니다.

1. 마이그레이션할 태그 속성을 선택한 다음 [!UICONTROL **다음**]&#x200B;을 선택합니다.

   로그인한 Experience Cloud 조직에서 사용할 수 있는 태그 속성만 표시됩니다.

1. 마이그레이션할 태그 라이브러리 스냅숏을 선택한 후 [!UICONTROL **다음**]&#x200B;을 선택하십시오.

   스냅샷은 마이그레이션의 기반이 되는 태그 라이브러리의 버전을 결정합니다. 각 스냅숏은 해당 환경(예: [!UICONTROL **개발**], [!UICONTROL **스테이징**] 또는 [!UICONTROL **프로덕션**])을 표시합니다.

1. 매핑 세트를 선택하여 Analytics 변수가 XDM 스키마 필드에 매핑되는 방법을 결정합니다.

   다음 중 하나를 수행합니다.

   * [!UICONTROL **새 매핑 집합 만들기**]&#x200B;를 선택합니다.

   * 기존 매핑 세트를 선택합니다.

     이전 마이그레이션 중에 또는 독립 실행형 매핑 세트로 생성된 매핑 세트를 선택할 수 있습니다.

     여러 마이그레이션에서 매핑 세트를 재사용하면 각 마이그레이션에 동일한 매핑이 적용됩니다.

1. [!UICONTROL **마이그레이션 만들기**]&#x200B;를 선택합니다.

1. [마이그레이션 유효성 검사 및 배포](#validate-and-deploy-a-migration) 섹션을 계속합니다.

## 마이그레이션 확인 및 배포

마이그레이션을 만든 후 [!UICONTROL **감사**], [!UICONTROL **매핑**] 및 [!UICONTROL **구현**]&#x200B;의 세 단계를 완료하도록 여십시오.

1. 마이그레이션 플래너에서 [!UICONTROL **마이그레이션**] 탭을 선택합니다.

1. 유효성을 검사할 마이그레이션 옆에 있는 [!UICONTROL **열기**]&#x200B;를 선택합니다.

   마이그레이션 개요 페이지에는 마이그레이션 및 해당 아티팩트에 대한 요약과 함께 완료할 세 단계가 표시됩니다.

   ![감사, 매핑 및 구현 단계 카드가 있는 마이그레이션 개요 페이지입니다.](assets/migration-planner-overview.png)

1. [!UICONTROL **감사**] 단계 완료:

   1. 마이그레이션 유형에 따라 감사 카드([!UICONTROL **태그 확장 감사**] 또는 [!UICONTROL **JavaScript 감사**])에서 [!UICONTROL **감사 시작**]&#x200B;을(를) 선택하여 마이그레이션에 포함된 규칙 및 데이터 요소를 검토합니다.

      ![규칙과 데이터 요소를 선택하고 결과를 확인하는 감사 페이지입니다.](assets/migration-planner-audit.png)

   1. [!UICONTROL **규칙**] 및 [!UICONTROL **데이터 요소**] 탭에서 마이그레이션에 포함할 항목을 선택합니다.

      [!UICONTROL **In library**](으)로 표시된 규칙이 게시되었습니다. [!UICONTROL **속성만**](으)로 표시된 규칙이 속성에 있지만 선택한 라이브러리에 속하지 않습니다.

   1. 선택한 규칙에 대한 결과를 검토합니다. 각 검색 결과에 대해 [!UICONTROL **검토**]&#x200B;를 선택하여 해결하거나 [!UICONTROL **무시**]&#x200B;를 선택하여 해결되지 않은 상태로 두십시오.

      예를 들어, 두 규칙에 동일한 이벤트와 조건이 있는 경우 [!UICONTROL **중복 규칙 이벤트**] 검색 결과를 통해 한 규칙을 유지하고 다른 규칙을 제거할 수 있습니다. 또는 [!UICONTROL **아무 것도 안 함**]&#x200B;을 선택하여 변경하지 않고 검색 결과를 확인합니다.

      계속하기 전에 결과를 확인하는 것은 선택 사항입니다. 검색 결과의 전체 목록 및 각 결과를 확인하는 방법은 [감사 결과 검토 및 확인](#review-and-resolve-audit-findings)을 참조하십시오.

   1. [!UICONTROL **저장 후 계속**]&#x200B;을 선택합니다.

1. [!UICONTROL **매핑**] 단계를 완료합니다.

   1. [!UICONTROL **Analytics → XDM 매핑**] 카드에서 [!UICONTROL **새 매핑 만들기**]&#x200B;를 선택합니다.

   1. Analytics 변수를 기반으로 새 스키마를 만들지 또는 기존 Experience Platform 스키마에 매핑할지 여부를 선택한 다음 나타나는 메시지에 따라 보고서 세트를 선택하고 필드를 매핑한 다음 스키마를 검토합니다.

      자세한 단계는 [XDM 필드에 Analytics 변수 매핑](#map-analytics-variables-to-xdm-fields)을 참조하십시오. 마이그레이션 간에 매핑 집합을 다시 사용하려면 [매핑 집합 만들기 및 관리](#create-and-manage-mapping-sets)를 참조하세요.

1. [!UICONTROL **구현**] 단계를 완료합니다.

   1. [!UICONTROL **웹 SDK 구현 생성**] 카드에서 감사 및 매핑 결과를 사용하여 웹 SDK 구현 패키지를 생성한 다음 사이트에 배포합니다.

      자세한 단계는 [웹 SDK 구현 생성 및 배포](#generate-and-deploy-the-web-sdk-implementation)를 참조하십시오.


## 감사 결과 검토 및 해결

[!UICONTROL **Audit**] 단계 동안 마이그레이션 플래너는 선택한 규칙에 대한 검색 결과에 플래그를 지정합니다. 계속하기 전에 결과를 해결하는 것은 선택 사항이지만, 해결하면 깔끔한 마이그레이션이 보장됩니다.

각 검색 결과에 대해 [!UICONTROL **검토**]&#x200B;를 선택하여 검색 결과를 열고 해결 방법을 선택하거나 [!UICONTROL **무시**]&#x200B;를 선택하여 해결되지 않은 상태로 두십시오.

마이그레이션 플래너는 다음 유형의 결과에 플래그를 지정할 수 있습니다.

* [!UICONTROL **중복 규칙 이벤트**]: 둘 이상의 규칙에 동일한 이벤트와 조건이 있습니다. 검색 결과를 검토할 때 기본 규칙과 중복 규칙을 비교한 다음 한 규칙을 유지하고 다른 규칙을 제거하거나 [!UICONTROL **아무 작업도 안 함**]&#x200B;을 선택하여 변경하지 않고 검색 결과를 확인합니다.

* [!UICONTROL **중복 규칙 논리**]: 규칙이 동일한 논리를 공유합니다. <!-- Confirm the exact remediation options for this finding type. -->

* [!UICONTROL **잘못된 규칙 작업**]: 마이그레이션 중에 문제를 일으킬 수 있는 순서로 규칙 작업이 실행됩니다. <!-- Confirm the exact remediation options for this finding type. -->

검색 결과에 관리 방법을 지정하지 않은 경우 마이그레이션 플래너는 [!UICONTROL **사용 가능한 수정 정보가 없습니다**]&#x200B;를 표시합니다. 검색 결과를 수동으로 검토하고 해결되면 닫습니다.

[!UICONTROL **결과**] 패널에는 처리한 결과 수와 아직 열려 있는 결과 수가 표시됩니다. 완료되면 [!UICONTROL **저장 후 계속**]&#x200B;을 선택합니다.

## XDM 필드에 Analytics 변수 매핑

[!UICONTROL **매핑**] 단계 동안 Analytics 변수를 XDM 필드에 매핑하고 대상 스키마를 생성하거나 선택합니다. [!UICONTROL **Analytics → XDM 매핑**] 카드에서 [!UICONTROL **새 매핑 만들기**]&#x200B;를 선택한 후 다음 단계를 완료하십시오.

1. **스키마 선택**: Analytics 변수를 기반으로 새 스키마를 만들지 또는 기존 Experience Platform 스키마에 매핑할지 여부를 선택합니다.

1. **보고서 세트**: 매핑할 변수가 있는 Analytics 보고서 세트를 선택합니다.

1. **Experience Platform 스키마**: 대상 XDM 스키마를 만들거나 매핑할 기존 스키마를 선택하십시오.

1. **수동 매핑**: 자동 매핑을 검토하고 개별 Analytics 변수가 XDM 필드에 매핑되는 방법을 조정하십시오.

1. **스키마 검토**: 결과 매핑과 스키마를 검토한 다음 확인하십시오.

<!-- The XDM mapping editor was not captured in the walkthrough. Confirm the exact steps, controls, and options on each step (Schema choice, Report suite, Experience Platform schema, Manual mapping, Review schema). -->

마이그레이션 간에 매핑 집합을 다시 사용하려면 [매핑 집합 만들기 및 관리](#create-and-manage-mapping-sets)를 참조하세요.

## 마이그레이션 출력 비교

마이그레이션 개요 페이지에서 [!UICONTROL **출력 비교**]&#x200B;를 사용하여 마이그레이션을 배포하기 전에 유효성을 검사하십시오.

<!-- The Compare outputs screen was not captured in the walkthrough. Confirm what the comparison shows (for example, AppMeasurement output compared with the Web SDK / XDM output) and how to interpret the results. -->

## 웹 SDK 구현 생성 및 배포

[!UICONTROL **구현**] 단계에서 마이그레이션 플래너는 감사 및 매핑 결과를 사용하여 웹 SDK 구현 패키지를 빌드합니다.

1. 마이그레이션 개요 페이지의 [!UICONTROL **웹 SDK 구현 생성**] 카드에서 구현 패키지를 생성합니다.

1. [!UICONTROL **태그 라이브러리 빌드**]&#x200B;를 선택하여 마이그레이션할 태그 라이브러리를 빌드합니다.

1. 이중 배포를 구성한 다음 웹 SDK 구현을 사이트에 배포합니다.

<!-- This stage was not captured in the walkthrough. Confirm the exact steps for generating the package, configuring the dual deployment, building the tag library, and deploying to the site. -->

이 단계에서 생성된 아티팩트에 대해서는 [마이그레이션 아티팩트 내보내기](#export-migration-artifacts)를 참조하십시오.

## 마이그레이션 아티팩트 내보내기

마이그레이션 개요 페이지는 마이그레이션 플래너가 생성하는 객체를 제공합니다. [!UICONTROL **프로젝트 아티팩트**] 패널에서 개별 아티팩트를 다운로드하거나 [!UICONTROL **모두 내보내기**]&#x200B;를 선택하여 한 번에 모두 내보낼 수 있습니다.

다음 아티팩트를 사용할 수 있습니다.

* [!UICONTROL **JSON 매핑**]: Analytics 변수와 XDM 필드 간의 매핑입니다.

* [!UICONTROL **XDM 스키마(JSON)**]: 마이그레이션을 위해 만들어진 대상 XDM 스키마.

* [!UICONTROL **태그 개발 라이브러리**]: 웹 SDK 구현을 위해 빌드된 태그 라이브러리입니다.

각 아티팩트는 [!UICONTROL **준비**] 또는 [!UICONTROL **빌드되지 않음**]&#x200B;과 같은 상태를 표시합니다. 아티팩트는 해당 단계에서 생성된 후 다운로드할 수 있습니다.

## 매핑 세트 만들기 및 관리 {#mapping-sets}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_sets"
>title="매핑 세트"
>abstract="매핑 세트는 Analytics 변수가 XDM 필드에 매핑되는 방법을 결정합니다.<br/>새 매핑 집합을 만들거나 기존 매핑 집합을 선택하여 여러 마이그레이션에 동일한 매핑을 적용합니다. 다른 마이그레이션 작업에서 매핑 세트를 참조할 수도 있습니다."

<!-- markdownlint-enable MD034 -->

매핑 세트는 Analytics 변수가 XDM 스키마 필드에 매핑되는 방법을 결정합니다.

마이그레이션 프로세스](#migrate-an-analytics-implementation-to-the-web-sdk)에서 새 매핑 집합 [을(를) 만들 수 있습니다. 또는 향후 마이그레이션 또는 다른 마이그레이션 작업에 사용할 독립형 매핑 세트를 만들 수 있습니다.

### 독립형 매핑 세트 만들기 {#xdm-mapping}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_schema"
>title="스키마 선택"
>abstract="매핑 세트는 Analytics 변수가 XDM 필드에 매핑되는 방법을 결정합니다.<br/>새 매핑 집합을 만들거나 기존 매핑 집합을 선택하여 여러 마이그레이션에 동일한 매핑을 적용합니다. 다른 마이그레이션 작업에서 매핑 세트를 참조할 수도 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_field_group"
>title="필드 그룹 환경 설정"
>abstract="가능한 경우 게시된 Adobe 필드 그룹을 사용하려면 표준 필드 그룹을 선택하십시오. 이렇게 하면 최대 일관성이 향상되고, 표준 필드를 사용할 수 없을 때 사용자 정의 테넌트 필드로 대체됩니다.<br/>가능한 경우 테넌트 네임스페이스 사용자 지정 필드를 사용하려면 사용자 지정 필드 그룹을 선택하십시오. 이를 통해 최대 유연성을 높일 수 있습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_lookback"
>title="전환 기간"
>abstract="현재 데이터를 받고 있는 변수를 결정할 때 살펴볼 거리를 제어합니다. 전환 확인 기간 내에 데이터를 포함하는 변수는 스키마에 포함됩니다."

<!-- markdownlint-enable MD034 -->

1. 마이그레이션 플래너에서 [!UICONTROL **매핑 세트**] 탭을 선택합니다.

1. [!UICONTROL **새 매핑 집합**]&#x200B;을(를) 선택하십시오.

1. [!UICONTROL **이름**] 필드에 이 매핑 집합을 나중에 식별할 수 있도록 수사적 이름을 입력한 다음 [!UICONTROL **다음**]&#x200B;을 선택합니다.

1. [!UICONTROL **보고서 세트**] 메뉴에서 XDM 필드에 매핑할 변수가 있는 보고서 세트를 선택한 다음 [!UICONTROL **다음**]&#x200B;을 선택합니다.

1. [!UICONTROL **XDM 매핑 섹션의 스키마 선택**]&#x200B;에서 Analytics 변수를 기반으로 새 스키마를 만들지 기존 Experience Platform 스키마에 매핑할지 여부를 선택합니다.

   새 스키마를 만들도록 선택하면 Analytics 변수를 XDM 필드에 매핑하는 프로세스를 안내합니다. 기존 스키마를 사용하도록 선택하면 변수를 Experience Platform 스키마 레지스트리에 사전 등록된 스키마에 수동으로 매핑할 수 있습니다.

   <!-- Screenshot pending: the XDM mapping editor (Create new mapping) was not available for capture in the walkthrough. -->

   * [!UICONTROL **새 스키마 만들기**]: 기본 및 고급 검사를 실행하여 Analytics 변수에 대한 XDM 필드 매핑을 자동으로 제안한 다음 결과 스키마를 검토하십시오.

   * [!UICONTROL **기존 스키마 사용**]: Experience Platform 스키마 레지스트리에 이미 등록된 스키마를 검색하고 선택한 다음 Analytics 변수를 수동으로 XDM 필드로 끌어옵니다.

1. [!UICONTROL **필드 그룹 환경 설정**] 드롭다운 메뉴에서 사용자 지정 변수를 필드 그룹으로 구성하는 방법을 선택합니다.

   * [!UICONTROL **표준 우선**]: 가능한 경우 게시된 Adobe 필드 그룹을 사용합니다. 이렇게 하면 최대 일관성이 향상되고, 표준 필드를 사용할 수 없을 때 사용자 정의 테넌트 필드로 대체됩니다.

   * [!UICONTROL **사용자 지정 먼저**]: 가능한 경우 테넌트 네임스페이스 사용자 지정 필드를 사용합니다. 이를 통해 최대 유연성을 높일 수 있습니다.

   <!-- * [!UICONTROL **Ask each time**]: Prompt for each signal so you can decide individually. -->

1. [!UICONTROL **전환 확인 기간**] 필드에서 데이터를 적극적으로 받고 있는 변수를 결정할 때 표시되는 전환 확인 기간을 선택합니다. 전환 확인 기간 내에 데이터를 포함하는 변수는 스키마에 포함됩니다.

1. [!UICONTROL **매핑 집합 만들기**]&#x200B;를 선택합니다.

새 매핑 세트가 [!UICONTROL **매핑 세트**] 탭에 표시되어 열어서 세부 정보를 검토할 수 있습니다.

### 매핑 세트 내보내기

매핑 세트를 내보내서 다른 마이그레이션 작업 또는 다른 도구에서 사용할 수 있습니다.

<!-- Confirm where the export control lives (the Mapping sets list exposes only an Open action) and the export format (for example, JSON). -->

### 게시 및 버전 매핑 세트

각 매핑 세트에는 상태와 버전이 있습니다. [!UICONTROL **매핑 세트**] 탭에서 매핑 세트가 다음과 같이 나타날 수 있습니다.

* [!UICONTROL **초안**]: 매핑 집합이 아직 편집 중입니다.

* [!UICONTROL **게시됨**]: 매핑 집합이 완료되었습니다.

* [!UICONTROL **마이그레이션에서**]: 매핑 집합이 하나 이상의 마이그레이션에 바인딩되어 있습니다.

<!-- Confirm how to publish a mapping set, how versions are created (v1, v2, v3), and what "bindings" represent. -->

### 매핑 집합 <!-- can you? --> 편집

<!-- Steps pending: confirm whether a mapping set can be edited after creation and where the edit control lives (the Mapping sets list exposes only an Open action). -->

### 매핑 집합 <!-- can you? -->을(를) 삭제합니다.

<!-- Steps pending: confirm whether a mapping set can be deleted, and whether deletion is blocked while the set is in use by a migration. -->

## 기존 마이그레이션 관리

### 마이그레이션 찾기 및 추적

[!UICONTROL **마이그레이션**] 탭에 마이그레이션 및 진행 상황이 나열됩니다. 계속하려면 마이그레이션을 찾거나 진행 중인 마이그레이션의 상태를 확인할 수 있습니다.

* **검색**: 검색 필드를 사용하여 이름 또는 속성별로 마이그레이션을 찾으십시오.

* **필터**: 마이그레이션 유형별 또는 상태별로 목록을 필터링합니다.

* **진행률 추적**: 각 마이그레이션은 세 단계(예: 1/3)의 진행률과 전체 상태를 표시합니다.

  * [!UICONTROL **시작되지 않음**]: 마이그레이션이 만들어졌지만 완료된 단계는 없습니다.

  * [!UICONTROL **진행 중**]: 하나 이상의 단계가 완료되었습니다.

  * [!UICONTROL **완료**]: 세 단계가 모두 완료되었습니다.

마이그레이션을 계속하려면 옆에 있는 [!UICONTROL **열기**]&#x200B;를 선택하십시오.

<!-- The row actions ("...") menu was not captured in the walkthrough. Confirm which actions it contains (for example, rename, duplicate, or delete a migration). -->

