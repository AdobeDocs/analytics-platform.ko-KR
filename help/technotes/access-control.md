---
title: Customer Journey Analytics 액세스 제어
description: Customer Journey Analytics에서 액세스 제어를 구현하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 8da8d22d35e0b4a77da010d0ba5fb230946ccce5
workflow-type: tm+mt
source-wordcount: '1560'
ht-degree: 17%

---

# 액세스 제어

Customer Journey Analytics은 세 가지 수준의 액세스 또는 세 가지 역할(제품 관리자 역할, 제품 프로필 관리자 역할 및 사용자 수준 액세스)로 제어합니다. 여기서는 이 역할에 대해 자세하게 설명합니다.

또한 이 문서에서는 Workspace 큐레이션 및 행 수준 및 가치 수준 액세스 제어와 같이 액세스를 제한하는 보다 세분화된 방법에 대해 설명합니다.

## 역할 기반 액세스 제어

다음 역할 기반 액세스 제어 수준을 사용할 수 있습니다.

### 제품 관리자 역할

제품 관리자 역할이 할당된 사용자에게는 기본적으로 Customer Journey Analytics 내에서 대부분의 작업을 수행하는 데 필요한 권한이 제공됩니다. 그러나 일부 작업에는 추가 권한이 필요합니다.

사용자를 제품 관리자로 추가하려면 다음을 수행하십시오.

1. [Admin Console](https://adminconsole.adobe.com/enterprise/)&#x200B;(으)로 이동합니다.

1. [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **관리자**] 탭 > [!UICONTROL **관리자 추가**]&#x200B;를 선택합니다.

   추가한 사용자에게 [제품 관리자 기본 권한](#product-admin-default-permissions)이 제공됩니다. 필요한 경우 [추가 권한](#product-admin-additional-permissions)을 부여할 수도 있습니다.

#### 제품 관리자 기본 권한

제품 관리자는 Customer Journey Analytics 내에서 대부분의 작업을 완료할 수 있는 권한이 있습니다.

제품 관리자에게는 기본적으로 다음 작업을 수행하는 데 필요한 권한이 부여됩니다.

* 데이터 보기 만들기, 업데이트 및 삭제
* 다른 사용자가 만든 프로젝트, 세그먼트, 계산된 지표, 대상자, 주석 또는 세그먼트 업데이트 및 삭제
* 모든 사용자에게 작업 영역 프로젝트 공유
* [보고 활동 관리자](/help/reporting-activity-manager/reporting-activity-overview.md)에서 보고 활동 관리
* Analysis Workspace에서 [전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md)

#### 제품 관리자 추가 권한

**Customer Journey Analytics**&#x200B;의 [Admin Console 제품 프로필](https://adminconsole.adobe.com/enterprise/)에서 제품 관리자로 추가되는 것 외에도 Customer Journey Analytics 내에서 다음 작업을 완료하려면 추가 권한이 필요합니다.

* 데이터 [연결](/help/connections/overview.md) 만들기, 업데이트 및 삭제

  이 작업을 수행하려면 사용자는 다음 권한을 제공하는 **Experience Platform 제품 프로필**&#x200B;의 일부여야 합니다.

  | 카테고리 | 사용 권한 | 설명 |
  |---|---|---|
  | [!UICONTROL 샌드박스] | [!UICONTROL 하나 이상] | CJA 연결의 관련 샌드박스에 대한 액세스 권한. |
  | [!UICONTROL 데이터 모델링] | [!UICONTROL 스키마 보기] | 스키마 및 관련 리소스에 대한 읽기 전용 액세스 권한. |
  | [!UICONTROL 데이터 모델링] | [!UICONTROL 스키마 관리] | 스키마 및 관련 리소스를 읽고, 만들고, 편집하고, 삭제할 수 있는 액세스 권한. |
  | [!UICONTROL 데이터 관리] | [!UICONTROL 데이터 세트 보기] | 데이터 세트 및 스키마에 대한 읽기 전용 액세스 권한. |
  | [!UICONTROL 데이터 관리] | [!UICONTROL 데이터 세트 관리] | 데이터 세트 읽기, 만들기, 편집 및 삭제에 대한 액세스 권한. 스키마에 대한 읽기 전용 액세스 권한. |
  | [!UICONTROL 데이터 수집] | [!UICONTROL 소스 관리] | 소스를 읽고, 만들고, 편집하고, 비활성화할 수 있는 액세스 권한. |
  | [!UICONTROL Identity Management] | [!UICONTROL ID 네임스페이스 보기] | ID 네임스페이스에 대한 읽기 전용 액세스 권한. |

  Experience Platform 권한에 대한 자세한 내용은 [제품 프로필에 대한 권한 관리](https://experienceleague.adobe.com/ko/docs/experience-platform/access-control/ui/permissions)를 참조하십시오.


* Adobe Journey Optimizer이 AJO 연결이 있는 CJA과 통합된 경우 연결에 액세스하려면 여정 권한도 추가해야 합니다.

  | 카테고리 | 사용 권한 | 설명 |
  |---|---|---|
  | [!UICONTROL 여정] | [!UICONTROL 여정 이벤트, 데이터 소스 및 작업 보기] | 여정 이벤트, 여정 지정 작업 및 여정 데이터 소스에 대한 읽기 전용 액세스 권한. |
  | [!UICONTROL 여정] | [!UICONTROL 여정 이벤트, 데이터 소스 및 작업 관리] | 이벤트, 소스 또는 작업을 읽고, 만들고, 편집하고, 삭제합니다. |
  | [!UICONTROL 여정] | [!UICONTROL 여정 보기] | 여정에 대한 읽기 전용 액세스 권한. |
  | [!UICONTROL 여정] | [!UICONTROL 여정 관리] | 여정 읽기, 만들기, 편집 및 삭제 |

* [대상](https://experienceleague.adobe.com/ko/docs/experience-platform/destinations/ui/activate/export-datasets)&#x200B;(으)로 데이터 세트 내보내기

  이 작업을 수행하려면 사용자는 다음 권한을 제공하는 **Experience Platform 제품 프로필**&#x200B;의 일부여야 합니다.

  | 카테고리 | 사용 권한 | 설명 |
  |---|---|---|
  | [!UICONTROL 대상] | [!UICONTROL 대상 관리] | 대상 연결 및 대상 계정을 읽고 만들고 삭제할 수 있는 액세스 권한. |
  | [!UICONTROL 대상] | [!UICONTROL 대상 활성화] | 사용자가 기존 대상에 대한 세그먼트를 활성화할 수 있도록 허용합니다. 활성화 워크플로에서 매핑 단계를 활성화합니다. 이 권한을 사용하려면 대상에 데이터를 활성화하려는 사용자에게 대상 보기 권한도 부여되어야 합니다. |

  Experience Platform 권한에 대한 자세한 내용은 [제품 프로필에 대한 권한 관리](https://experienceleague.adobe.com/ko/docs/experience-platform/access-control/ui/permissions)를 참조하십시오.

* [BI 확장 사용](../data-views/bi-extension.md)

  사용자가 BI 확장을 사용할 수 있도록 제품 관리자

   * 사용자의 Experience Platform 권한에 쿼리 관리 및 쿼리 서비스 통합 관리 옵션이 있는 쿼리 서비스 리소스가 있는 역할이 포함되어 있는지 확인해야 합니다. Experience Platform 권한에 대한 자세한 내용은 [제품 프로필에 대한 권한 관리](https://experienceleague.adobe.com/ko/docs/experience-platform/access-control/ui/permissions)를 참조하십시오.

     | 카테고리 | 사용 권한 | 설명 |
     |---|---|---| 
     | [!UICONTROL 쿼리 서비스] | [!UICONTROL 쿼리 관리] | Platform 데이터에 대한 구조화된 SQL 쿼리를 읽고, 만들고, 편집하고, 삭제할 수 있는 액세스 권한. |
     | [!UICONTROL 쿼리 서비스] | [!UICONTROL 쿼리 서비스 통합 관리] | 쿼리 서비스 액세스에 대한 만료되지 않는 자격 증명을 생성, 업데이트 및 삭제할 수 있는 액세스 권한입니다. |

   * 은(는) 사용자에게 적절한 Customer Journey Analytics 권한이 있는지 확인해야 합니다.
      * 관련 데이터 보기에 대한 액세스 권한. [!UICONTROL 사용자 수준 액세스]에서 [데이터 보기](#user-level-access)를 참조하십시오.
      * Customer Journey Analytics BI 확장 액세스 권한. [!UICONTROL 사용자 수준 액세스]에서 [데이터 보기 도구](#user-level-access)를 참조하십시오.

### 제품 프로필 관리자 역할

제품 프로필은 권한 그룹입니다. 제품 관리자는 제품 프로필을 만들고 제품 프로필 관리자에게 하나 이상의 제품 프로필을 관리하도록 할당할 수 있습니다. 그런 다음 제품 프로필 관리자는 다음 작업을 수행할 수 있습니다.

* 할당된 제품 프로필을 관리합니다. 사용자 또는 사용자 그룹 추가 또는 제거, 제품 프로필에 대한 권한 수정 등의 작업을 수행할 수 있습니다.

* Customer Journey Analytics에서 지정된 제품 프로필의 일부인 데이터 보기를 편집합니다. 제품 프로필 관리자는 새 데이터 보기를 만들 수 없습니다.

### 사용자 수준 액세스

아래 표는 관련 사용자에 대해 구성할 수 있는 다양한 Customer Journey Analytics 기능에 대한 기본 액세스 권한을 간략하게 설명합니다. 제품 프로필을 통해 다양한 수준의 사용자 액세스를 관리할 수 있습니다. 제품 프로필은 여러 권한을 결합하여 개별 사용자 또는 사용자 그룹에 할당할 수 있습니다.

**[!UICONTROL 권한]** 탭은 [Admin Console](https://adminconsole.adobe.com/enterprise/)의 각 제품 프로필에 포함되어 있습니다.

![Admin Console 권한](assets/permissions.png)

| 카테고리 | 사용 권한 | 설명 |
| --- | --- | ---|
| [!UICONTROL 데이터 보기] | *데이터 보기 이름* | **[!UICONTROL 자동 포함]**&#x200B;을 **[!UICONTROL 켜기]**&#x200B;로 전환하면 이 제품 프로필의 일부인 사용자가 기존 데이터 보기와 새로 생성된 데이터 보기를 모두 볼 수 있습니다. 이 설정을 **[!UICONTROL 끄기]**&#x200B;로 설정하면 사용자가 액세스할 수 있는 특정 데이터 보기를 선택할 수 있습니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL Analysis Workspace 액세스] | 사용자가 [Analysis Workspace](/help/analysis-workspace/home.md)에 액세스할 수 있도록 허용합니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL 안내식 분석 액세스] | 사용자가 [안내가 있는 분석](/help/guided-analysis/overview.md)에 액세스할 수 있도록 허용합니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL 계산된 지표 만들기] | 사용자가 [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md)을(를) 만들 수 있도록 허용합니다. 사용자는 자신이 만든 계산된 지표 또는 자신과 공유된 계산된 지표만 태그 지정, 공유, 삭제, 이름 변경, 승인, 승인을 취소할 수 있습니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL 세그먼트 만들기] | 사용자가 [세그먼트](/help/components/segments/seg-overview.md)를 만들 수 있도록 허용합니다. 사용자는 자신이 만든 세그먼트 또는 자신과 공유된 세그먼트만 태그 지정, 공유, 삭제, 이름 변경, 승인 및 승인 취소할 수 있습니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL Labs 액세스] | 사용자가 Customer Journey Analytics의 [Labs](/help/labs/labs.md) 탭에 액세스할 수 있도록 허용합니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL 주석 작성] | 사용자가 [주석](/help/components/annotations/overview.md)을 만들 수 있도록 허용합니다. 사용자는 자신이 만든 주석이나 자신과 공유된 주석에 태깅하고, 공유하고, 삭제하고, 이름을 바꿀 수 있습니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL 대상자 보기] | 사용자가 [대상](/help/components/audiences/audiences-overview.md)을 볼 수 있도록 허용합니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL 대상자 생성] | 사용자가 [대상](/help/components/audiences/audiences-overview.md)을 만들 수 있도록 허용합니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL 감사 로그 액세스] | [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) 및 감사 로그 UI에 권한 검사를 적용합니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL 모든 사람과 프로젝트 링크 공유] | 사용자가 [누구와도 프로젝트를 공유할 수 있도록 허용합니다.](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL 보고 도구] | [!UICONTROL 예측] | 사용자가 Analysis Workspace의 [예측](../analysis-workspace/c-forecast/forecasting.md) 기능에 액세스할 수 있도록 허용 |
| [!UICONTROL 보고 도구] | [!UICONTROL AI 어시스턴트: 제품 지식] | 사용자가 [AI Assistant](../ai-assistant.md)에 액세스하여 제품을 이해할 수 있도록 허용합니다. |
| [!UICONTROL 보고 도구] | [!UICONTROL 인텔리전트 캡션] | 사용자가 [지능형 캡션](/help/analysis-workspace/visualizations/intelligent-captions.md)에 액세스할 수 있도록 허용합니다. |
| [!UICONTROL 데이터 보기 도구] | [!UICONTROL 전체 테이블 내보내기] | 사용자가 [전체 테이블을 클라우드로 내보내기](/help/analysis-workspace/export/export-cloud.md)하도록 허용합니다. |
| [!UICONTROL 데이터 보기 도구] | [!UICONTROL CJA BI 확장] | 사용자가 [BI 확장](../data-views/bi-extension.md)을 사용하도록 허용합니다. |

{style="table-layout:auto"}

## 작업 영역 프로젝트 큐레이션

작업 영역 보고 수준에서 다른 수준의 액세스 제어를 사용할 수 있습니다. 특정 구성 요소에 대한 특정 사용자의 액세스를 제한할 수 있습니다. 작업 영역 프로젝트 수준에서 구성 요소(차원, 지표, 세그먼트, 날짜 범위)를 제한하는 방법과 큐레이션이 데이터 보기에 연결되는 방법에 대한 자세한 내용은 [프로젝트 구성](/help/analysis-workspace/curate-share/curate.md)을 참조하십시오.

## 개별 지표 또는 차원에 대한 액세스 권한 부여

Customer Journey Analytics에서는 기존의 Adobe Analytics에서와 같이 개별 지표 또는 차원에 대한 권한을 부여하거나 거부할 수 없습니다. 지표 및 차원은 [데이터 보기](/help/data-views/data-views.md)에서 수정할 수 있으므로 Customer Journey Analytics에서 변경될 수 있습니다. 소급하여 변경하면 보고도 변경됩니다.

## 사용 사례

다음은 액세스 제어를 실제 시나리오에서 어떻게 사용할 수 있는지 보여 주는 몇 가지 사용 사례입니다.

### 서드파티 액세스

귀사가 근무하는 서드파티의 팀장에게 제품 프로필 관리 액세스 권한을 제공할 수 있습니다. 이 관리자는 회사 팀의 사용자를 이 제품 프로필에 추가할 수 있습니다. 이 제품 프로필 관리자는 특정 데이터 보기에 대한 액세스 권한을 부여하고 서드파티 내의 다른 사용자를 이 제품 프로필에 추가할 수 있습니다. 제품 프로필 관리자는 서드파티 팀의 요구 사항에 맞게 데이터 보기를 수정할 수 있습니다.

### 행 수준 액세스 제어

사용자에게 하루만 데이터 액세스 권한을 부여하려고 합니다. 이러한 특정 행에 대한 액세스를 제한하는 방법은 다음과 같습니다.

1. 특정 데이터 보기의 [!UICONTROL 설정]에서 세그먼트를 만드십시오. 여기서 [!UICONTROL 일]은(는) 데이터에 액세스할 수 있는 날짜와 같습니다. 자세한 내용은 [데이터 보기 만들기](/help/data-views/create-dataview.md#settings-filters)를 참조하십시오.
1. 기본 연결에서 데이터 세트의 데이터 부분에 세그먼트를 적용하는 데이터 보기를 저장합니다. 세그먼트 정의와 맞지 않는 행은 데이터 보기에서 자동으로 제외되며 이 데이터 보기를 사용할 때 Analysis Workspace에서 사용할 수 없습니다.
1. Admin Console에서 새 [제품 프로필](#product-profile-admin-role)을 만들고, 사용자를 제품 프로필에 추가하고, 제품 프로필에 이 특정 데이터 보기만 포함하십시오.

### 가치 수준 액세스 제어

데이터 보기에 대한 액세스 권한이 있는 사용자는 관리자가 이 데이터 보기에 포함시킨 지표 및 차원으로만 작업할 수 있습니다. 관리자는 데이터 보기에서 [포함/제외 기능](/help/data-views/component-settings/include-exclude-values.md) 또는 [값 버킷팅](../data-views/component-settings/value-bucketing.md) 구성 요소 설정을 사용하여 데이터 보기에서 특정 차원 값을 제외하거나 집계할 수 있습니다.

예: 데이터 세트의 개별 환자 데이터가 포함된 구성 요소의 데이터 보기에서 *고혈압*&#x200B;이라는 지표를 만듭니다. 값 버킷팅을 사용하여 버킷된 값에만 액세스할 수 있으므로 데이터 사용자가 개별 환자 데이터를 보지 않습니다.


