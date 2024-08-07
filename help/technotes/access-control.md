---
title: Customer Journey Analytics 액세스 제어
description: Customer Journey Analytics에서 액세스 제어를 구현하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 1a470345a6a2748b992263c3ad25e4cd7d3daa9e
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 42%

---

# Customer Journey Analytics 액세스 제어

세 가지 수준의 액세스 또는 세 가지 역할(제품 관리자 역할, 제품 프로필 관리자 역할 및 사용자 수준 액세스)이 Customer Journey Analytics을 제어합니다. 여기서는 이 역할에 대해 자세하게 설명합니다.

또한 이 문서에서는 Workspace 큐레이션 및 행 수준 및 가치 수준 액세스 제어와 같이 액세스를 제한하는 보다 세분화된 방법에 대해 설명합니다.

## 제품 관리자 역할

제품 관리자 역할이 할당된 사용자에게는 기본적으로 Customer Journey Analytics 내에서 대부분의 작업을 수행하는 데 필요한 권한이 제공됩니다. 그러나 일부 작업에는 추가 권한이 필요합니다.

사용자를 제품 관리자로 추가하려면:

1. [Admin Console](https://adminconsole.adobe.com/enterprise/)(으)로 이동합니다.

1. [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **관리자**] 탭 > [!UICONTROL **관리자 추가**]&#x200B;를 선택합니다.

   추가한 사용자에게 [제품 관리자 기본 권한](#product-admin-default-permissions)이 제공됩니다. 필요한 경우 [추가 권한](#product-admin-additional-permissions)을 부여할 수도 있습니다.

### 제품 관리자 기본 권한

제품 관리자는 Customer Journey Analytics 내에서 대부분의 작업을 완료할 수 있는 권한이 있습니다.

제품 관리자에게는 기본적으로 다음 작업을 수행하는 데 필요한 권한이 부여됩니다.

* 데이터 보기 만들기, 업데이트 및 삭제
* 다른 사용자가 만든 프로젝트, 필터, 계산된 지표, 대상자, 주석 또는 필터 업데이트 및 삭제
* 모든 사용자에게 작업 영역 프로젝트 공유
* [보고 활동 관리자](/help/reporting-activity-manager/reporting-activity-overview.md)에서 보고 활동 관리
* Analysis Workspace에서 [전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md)

### 제품 관리자 추가 권한

[Admin Console](https://adminconsole.adobe.com/enterprise/)의 **Customer Journey Analytics 제품 프로필**&#x200B;에서 제품 관리자로 추가된 것 외에도 Customer Journey Analytics 내에서 다음 작업을 완료하려면 추가 권한이 필요합니다.

* 데이터 [연결](/help/connections/overview.md) 만들기, 업데이트 및 삭제

  이 작업을 수행하려면 사용자는 다음 권한을 제공하는 **Experience Platform 제품 프로필**&#x200B;의 일부여야 합니다.
   * 데이터 모델링: 스키마 보기, 스키마 관리
   * 데이터 관리: 데이터 세트 보기, 데이터 세트 관리
   * 데이터 수집: 소스 관리
   * ID 네임스페이스 보기

     Experience Platform 권한에 대한 자세한 내용은 [Adobe Experience Platform의 액세스 제어](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home)를 참조하십시오.

* 클라우드 [대상](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html)(으)로 데이터 세트 내보내기

  이 작업을 수행하려면 사용자에게 다음 Experience Platform 권한이 필요합니다.

   * 대상 관리
   * 대상 활성화

     Experience Platform 대상 권한에 대한 자세한 내용은 [대상 개요](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home)를 참조하십시오.

* [BI 확장 사용](../data-views/bi-extension.md)

  사용자가 BI 확장을 사용할 수 있도록 제품 관리자

   * 의 Experience Platform 권한에 쿼리 관리 및 쿼리 서비스 통합 관리 옵션이 있는 쿼리 서비스 리소스가 있는 역할이 포함되어 있는지 확인해야 합니다. [제품 프로필에 대한 권한 관리](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions)를 참조하세요.
   * 은(는) 사용자에게 적절한 Customer Journey Analytics 권한이 있는지 확인해야 합니다.
      * 관련 데이터 보기에 대한 액세스 권한. [Admin Console의 Customer Journey Analytics 권한](#customer-journey-analytics-permissions-in-admin-console)에서 데이터 보기를 참조하십시오.
      * cja BI 확장 기능에 액세스할 수 있는 권한. [Admin Console의 Customer Journey Analytics 권한](#customer-journey-analytics-permissions-in-admin-console)에서 데이터 보기 도구를 참조하십시오.

## 제품 프로필 관리자 역할

제품 프로필은 권한 그룹입니다. 제품 프로필 관리자는

* 개별 제품 프로필을 만들고 관리합니다. 새 사용자 추가 또는 사용자 그룹 및 관련 제품 프로필 관리 등.

* Customer Journey Analytics에서 관리하는 제품 프로필의 일부인 데이터 보기를 편집합니다. 새로운 데이터 보기를 만들 수 없습니다.

## 사용자 수준 액세스

아래 표는 제품 관리자가 아닌 사용자와 Customer Journey Analytics 제품 관리자를 위한 다양한 Customer Journey Analytics 기능에 대한 기본 액세스 권한을 간략하게 설명합니다. 이러한 권한을 이해하면 사용자가 조직 내에서 자신의 역할과 책임에 따라 Customer Journey Analytics을 효과적으로 탐색하고 사용할 수 있습니다.

| 제품 기능 | 제품 관리자가 아닌 사용자(사용자) | 제품 관리자 |
| --- | --- | --- |
| **데이터 보기** | 보기/업데이트/만들기/삭제할 수 없음 | 생성/업데이트/삭제 가능 |
| **연결** | 보기/업데이트/만들기/삭제할 수 없음 | 생성/업데이트/삭제 가능 |
| **필터** | 만들 수 있음 | 만들 수 있음 |
| **프로젝트** | 만들 수 있음 | 생성/업데이트/삭제 가능 |
| **대상자** | Admin Console에서 특별한 권한으로 만들 수 있음 | 만들 수 있음 |
| **계산된 지표** | Admin Console에서 특별한 권한으로 만들 수 있음 | 만들 수 있음 |

{style="table-layout:auto"}

## 작업 영역 프로젝트 큐레이션

작업 영역 보고 수준에서 다른 수준의 액세스 제어를 사용할 수 있습니다. 특정 구성 요소에 대한 특정 사용자의 액세스를 제한할 수 있습니다. Workspace 프로젝트 수준에서 구성 요소(차원, 지표, 필터, 날짜 범위)를 제한하는 방법과 큐레이션이 데이터 보기에 연결되는 방법에 대한 자세한 내용은 [프로젝트 조정](/help/analysis-workspace/curate-share/curate.md)을 참조하십시오.

## 개별 지표 또는 차원에 대한 액세스 권한 부여

Customer Journey Analytics에서는 기존의 Adobe Analytics에서와 같이 개별 지표 또는 차원에 대한 권한을 부여하거나 거부할 수 없습니다. 지표와 차원은 [데이터 보기](/help/data-views/data-views.md)에서 수정할 수 있으므로 Customer Journey Analytics에서 변경될 수 있습니다. 소급하여 변경하면 보고도 변경됩니다.

## 사용 사례

다음은 액세스 제어를 실제 시나리오에서 어떻게 사용할 수 있는지 보여 주는 몇 가지 사용 사례입니다.

### 서드파티 액세스

귀사와 함께 일하는 서드파티에 제품 프로필 관리자를 만들 수 있는 팀 리더를 지정합니다. 이 관리자는 회사 팀의 사용자를 이 제품 프로필에 추가할 수 있습니다. 이 관리자는 특정 데이터 보기에 액세스를 부여할 수 있고 다른 사용자를 이 제품 프로필에 추가할 수 있습니다. 팀의 필요에 맞게 제어할 수 있는 데이터 보기를 수정할 수도 있습니다.

### 행 수준 액세스 제어

사용자에게 하루만 데이터 액세스 권한을 부여하고 싶다고 가정해 보겠습니다. 이러한 특정 행에 대한 액세스를 제한하는 방법은 다음과 같습니다.

1. **[!UICONTROL Day]**&#x200B;이(가) 데이터에 액세스할 수 있는 날짜와 동일한 Customer Journey Analytics에 필터를 만듭니다.
1. [!UICONTROL 데이터 보기] > [!UICONTROL 설정]에서 이 필터를 데이터 보기에 추가합니다.
1. 데이터 보기를 저장하고 필터를 데이터 세트에 자동 적용합니다. 필터 정의와 맞지 않는 행은 이제 편집된 데이터 보기에서 자동 제외됩니다.
1. Admin Console에 새 제품 프로필을 만든 후 사용자를 추가하고 이 데이터 보기에 대한 사용자 액세스를 제한합니다.

### 가치 수준 액세스 제어

데이터 보기에 대한 액세스 권한이 있는 사용자는 관리자가 이 데이터 보기에 포함시킨 지표와 차원으로만 작업할 수 있습니다. 예를 들어 관리자가 데이터 보기에서 [포함/제외 기능](/help/data-views/component-settings/include-exclude-values.md)을 사용하여 특정 차원 값을 데이터 보기에서 제외할 수 있습니다.

건강 관리와 관련된 예를 들어 보겠습니다. 이 데이터가 포함된 데이터 세트에서 데이터 보기에 “고혈압”이라는 지표를 생성한다고 가정해 보겠습니다. 지표라는 사실을 통해 이 지표의 집계 값을 볼 수 있지만 지표에 해당하는 개별 환자는 볼 수 없습니다.

## Admin Console에서 권한 Customer Journey Analytics

**[!UICONTROL 권한]** 탭은 [Admin Console](https://adminconsole.adobe.com/enterprise/) 각 제품 프로필의 일부입니다. 특정 제품 프로필에 사용자를 추가할 수 있습니다. 그 다음 특정 데이터 보기에 대한 권한을 할당하고 제품 프로필의 사용자에게 부여할 권한을 지정합니다. 다음은 Customer Journey Analytics 관련 권한입니다.

![Admin Console 권한](assets/permissions.png)

| 사용 권한 | 정의 |
| --- | --- |
| **[!UICONTROL 데이터 보기]** | **[!UICONTROL 자동 포함]**&#x200B;을 **[!UICONTROL 켜기]**&#x200B;로 전환하면 이 제품 프로필의 일부인 사용자가 기존 데이터 보기와 새로 생성된 데이터 보기를 모두 볼 수 있습니다. 이 설정을 **[!UICONTROL 끄기]**&#x200B;로 설정하면 사용자가 액세스할 수 있는 특정 데이터 보기를 선택할 수 있습니다. |
| **[!UICONTROL 보고 도구]**: |   |
| **[!UICONTROL 감사 로그 액세스]** | 이 권한은 [API](https://www.adobe.io/cja-apis/docs/endpoints/auditlogs/) 및 감사 로그 UI에 대한 권한 검사를 시행합니다. |
| **[!UICONTROL Analysis Workspace 액세스]** | 사용자가 Customer Journey Analytics에서 Analysis Workspace에 액세스할 수 있도록 허용합니다. |
| [!UICONTROL **안내식 분석 액세스**] | 사용자가 [안내식 분석 프로젝트](/help/guided-analysis/overview.md)를 만들 수 있도록 허용합니다. |
| [!UICONTROL **예측**] | 사용자가 Analysis Workspace의 예측 기능에 액세스할 수 있도록 허용 |
| **[!UICONTROL 보고 사용 관리자]** | 사용자가 회사에서 실행 중인 보고서를 보고 삭제할 수 있도록 허용합니다. |
| **[!UICONTROL 보고 사용 보기]** | 사용자가 모든 동시 보고 요청을 볼 수 있도록 허용합니다. |
| [!UICONTROL **전체 테이블 내보내기**] | 사용자가 [전체 테이블을 클라우드로 내보내기](/help/analysis-workspace/export/export-cloud.md)하도록 허용합니다. |
| **[!UICONTROL 계산된 지표 만들기]** | 사용자가 [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md)을(를) 만들 수 있도록 허용합니다. |
| **[!UICONTROL 필터 만들기]** | 사용자가 [필터](/help/components/filters/filters-overview.md)를 만들 수 있도록 허용합니다. |
| **[!UICONTROL Labs 액세스]** | 사용자가 Customer Journey Analytics의 [Labs](/help/labs/labs.md) 탭에 액세스할 수 있도록 허용합니다. |
| **[!UICONTROL 주석 작성]** | 사용자가 [주석](/help/components/annotations/overview.md)을 만들 수 있도록 허용합니다. |
| **[!UICONTROL 대상자 생성]** | 사용자가 [대상](/help/components/audiences/audiences-overview.md)을 만들 수 있도록 허용합니다. |
| **[!UICONTROL 대상자 보기]** | 사용자가 [대상](/help/components/audiences/audiences-overview.md)을 볼 수 있도록 허용합니다. |
| [!UICONTROL **모든 사람과 프로젝트 링크 공유**] | 사용자가 [누구와도 프로젝트를 공유할 수 있도록 허용합니다.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| **[!UICONTROL 데이터 보기 도구]**: |   |
| [!UICONTROL **전체 테이블 내보내기**] | 사용자가 [전체 테이블을 클라우드로 내보내기](/help/analysis-workspace/export/export-cloud.md)하도록 허용합니다. |
| **[!UICONTROL [!UICONTROL CJA BI 확장]]** | 사용자가 [BI 확장](../data-views/bi-extension.md)을 사용하도록 허용합니다. |

{style="table-layout:auto"}
