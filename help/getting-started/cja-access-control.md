---
title: CJA 액세스 제어
description: CJA에서 액세스 제어를 구현하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: ccb13b9632433f2fcc9c765e9527f157dad632d4
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 17%

---

# CJA 액세스 제어

CJA(Customer Journey Analytics)은 세 가지 액세스 수준 또는 세 가지 역할의 적용을 받습니다. 제품 관리자 역할, 제품 프로필 관리자 역할 및 사용자 수준 액세스. 이 항목에서는 이러한 역할에 대해 자세히 설명합니다.

## 제품 관리자 역할

제품 관리자는 CJA 내에서 필요한 작업을 완료할 수 있는 권한이 있습니다. 에 제품 관리자로 추가되어야 합니다 **Customer Journey Analytics 제품 프로필** 에서 [Admin Console](https://adminconsole.adobe.com/enterprise/) 아래에 [!UICONTROL Customer Journey Analytics] > [!UICONTROL 관리자] 탭 > [!UICONTROL 관리자 추가]. 제품 관리자에게는 다음 권한이 부여됩니다.

* 연결 또는 데이터 보기 만들기/업데이트/삭제
* 다른 사용자가 만든 프로젝트, 필터, 계산된 지표, 대상, 주석 또는 필터 업데이트/삭제
* 모든 사용자에게 작업 영역 프로젝트 공유

Customer Journey Analytics에서만 제품 관리자가 되는 것만으로는 [연결](/help/connections/overview.md). Experience Platform 데이터 세트에 대한 연결을 만들려면 Experience Platform 권한도 필요합니다. 특히 다음 권한을 부여하는 **Experience Platform 제품 프로필**&#x200B;의 일부여야 합니다.

* 데이터 모델링: 스키마 보기, 스키마 관리
* 데이터 관리: 데이터 세트 보기, 데이터 세트 관리
* 데이터 수집: 소스 관리
* ID 네임스페이스 보기

Experience Platform 권한에 대한 자세한 내용은 [Adobe Experience Platform의 액세스 제어](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ko)를 참조하십시오.

## 제품 프로필 관리자 역할

제품 프로필은 권한 세트입니다. 제품 프로필 관리자는 다음을 수행할 수 있습니다

* 새 사용자 추가 등 개별 제품 프로필을 만들고 관리합니다.

* CJA에서 관리하는 제품 프로필에 포함된 데이터 보기를 편집합니다. 새 데이터 보기를 만들 수 없습니다.

## 사용자 수준 액세스

Customer Journey Analytics 사용자는 데이터 보기 또는 연결을 만들거나, 편집하거나, 볼 수 없습니다. 사용자는 Admin Console에서 특수 권한이 있는 필터, 프로젝트, 대상 및 계산된 지표를 만들 수 있습니다.

## 작업 공간 프로젝트 큐레이션

Workspace 보고 수준에서 다른 수준의 액세스 제어를 사용할 수 있습니다. 특정 사용자의 특정 구성 요소에 대한 액세스를 제한할 수 있습니다. Workspace 프로젝트 수준에서 구성 요소(차원, 지표, 세그먼트, 날짜 범위)를 제한하는 방법 및 큐레이션이 데이터 보기에 연결된 방법에 대한 자세한 내용은 [프로젝트 조정](/help/analysis-workspace/curate-share/curate.md).

## 개별 지표 또는 차원에 대한 액세스 권한 부여

Customer Journey Analytics에서는 기존의 Adobe Analytics에서와 같이 개별 지표 또는 차원을 거부하거나 허용할 수 없습니다. 지표와 차원은 다음 위치에서 수정할 수 있습니다 [데이터 보기](/help/data-views/data-views.md) 따라서 CJA에서 변경될 수 있습니다. 이를 변경하면 변경 사항이 보고에 소급하여 적용됩니다.

## 사용 사례

다음은 실시간 시나리오에서 액세스 제어를 사용하는 방법을 보여주는 몇 가지 사용 사례입니다.

### 타사 액세스

회사에서 일하는 타사에는 제품 프로필 관리자가 될 수 있는 팀 리드가 있습니다. 그러면 이 관리자는 이 제품 프로필에 자신의 팀의 사용자를 추가할 수 있습니다. 이 관리자는 특정 데이터 보기에 대한 액세스 권한을 제공하고 이 제품 프로필에 다른 사용자를 추가할 수 있습니다. 또한 팀의 요구 사항에 맞게 제어할 수 있는 데이터 보기를 수정할 수 있습니다.

### 행 수준 액세스 제어

사용자에게 하루 동안만 데이터에 액세스할 수 있는 권한을 제공한다고 가정합니다. 다음은 특정 행에 대한 액세스를 제한하는 방법입니다.

1. CJA에서 필터를 만듭니다. **[!UICONTROL 일]** 는 데이터 액세스 권한을 부여할 날짜와 같습니다.
1. in [!UICONTROL 데이터 보기] > [!UICONTROL 설정]를 눌러 해당 필터를 데이터 보기에 추가합니다.
1. 데이터 보기를 저장하고 데이터 세트에 필터를 자동으로 적용합니다. 필터 정의에 맞지 않는 모든 행은 이제 편집된 데이터 보기에서 자동으로 제외됩니다.
1. Admin Console에서 새 제품 프로필을 만들고 사용자를 추가하고 이 데이터 보기에 대한 액세스를 제한합니다.

### 값 수준 액세스 제어

데이터 보기에 액세스할 수 있는 사용자는 관리자가 이 데이터 보기에 포함한 지표 및 차원에서만 작업할 수 있습니다. 관리자는 [포함/제외 기능](/help/data-views/component-settings/include-exclude-values.md) 예를 들어 데이터 보기에서에 대한 특정 차원 값을 데이터 보기에서 제외합니다.

다음은 의료 관련 예입니다. 이 데이터를 포함하는 데이터 세트에서 데이터 보기에 &quot;고혈압&quot;이라는 지표를 만든다고 가정합니다. 지표가 된다는 사실은 이 지표의 총계를 볼 수 있게 하지만 그 아래에 있는 개별 환자는 볼 수 없습니다.

## CJA 권한

다음 **[!UICONTROL 권한]** 탭에서 [Admin Console](https://adminconsole.adobe.com/enterprise/). 특정 제품 프로필에 사용자를 추가할 수 있습니다. 그런 다음 특정 데이터 보기에 권한을 지정하고 제품 프로필의 사용자에게 어떤 권한을 부여할지 지정합니다. 다음은 CJA별 권한입니다.

![admin console 권한](assets/permissions.png)

| 사용 권한 | 정의 |
| --- | --- |
| **[!UICONTROL 데이터 보기]** | 전환하면 **[!UICONTROL 자동 포함]** to **[!UICONTROL 설정]**, 이 제품 프로필에 포함된 사용자는 모든 기존 및 새로 만든 데이터 보기를 볼 수 있습니다. 이 설정이 **[!UICONTROL 해제]**, 사용자가 액세스할 수 있는 특정 데이터 보기를 선택할 수 있습니다. |
| **[!UICONTROL 보고 도구]**: |  |
| **[!UICONTROL 감사 로그 액세스]** | 현재, [감사 로그](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) 는 API를 통해서만 사용할 수 있습니다. 이 권한은 개발 중인 향후 UI에 대한 것입니다. |
| **[!UICONTROL 보고 사용 관리자]** | 사용자가 회사에서 실행 중인 보고서를 보고 삭제할 수 있도록 해줍니다. (보고 사용 기능은 아직 출시되지 않았습니다.) |
| **[!UICONTROL 보고 사용 보기]** | 사용자가 모든 동시 보고 요청을 볼 수 있도록 해줍니다. (보고 사용 기능은 아직 출시되지 않았습니다.) |
| **[!UICONTROL 계산된 지표 생성]** | 사용자가 만들 수 있음 [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL 필터 만들기]** | 사용자가 만들 수 있음 [필터](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs 액세스]** | 사용자가 [Labs](/help/labs/labs.md) CJA의 탭에서 액세스할 수 있습니다. |
| **[!UICONTROL 주석 작성]** | 사용자가 만들 수 있음 [주석](/help/components/annotations/overview.md). |
| **[!UICONTROL 대상 생성]** | 사용자가 만들 수 있음 [대상자](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL 대상 보기]** | 사용자가 볼 수 있음 [대상자](/help/components/audiences/audiences-overview.md). |