---
title: 동의 보고 및 필터링 개요
description: Customer Journey Analytics에서 수집 시 방문자 동의 정책 멤버십을 보고하고 동의하지 않는 방문자를 필터링하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 1058
ht-degree: 2%

---

# 동의 보고 및 필터링 개요

동의 보고 및 필터링은 Adobe Experience Platform 프로필 데이터 세트에 저장된 동의 정책 멤버십 데이터를 사용하여 방문자 동의를 보고하고, 동의를 받지 않은 방문자의 데이터를 Customer Journey Analytics에 수집하기 전에 선택적으로 제외하는 데 도움이 됩니다.

## 사전 요구 사항

동의 보고 및 필터링을 구성하기 전에 다음을 확인하십시오.

* 조직은 Adobe Healthcare Shield 또는 Privacy &amp; Security Shield에 라이선스를 부여했습니다.
* Customer Journey Analytics에서 시스템 관리자 권한이 있습니다.
* 사용하려는 샌드박스에 동의 정책 구성원 데이터가 있는 프로필 데이터 세트가 `consentPoliciesIDMap` 필드에 포함되어 있습니다.
* 구성할 연결이 이미 있습니다. 자세한 내용은 [연결 만들기 또는 편집](/help/connections/create-connection.md)을 참조하세요.

다음 다이어그램 및 관련 테이블은 동의 보고 및 필터링을 통해 Analysis Workspace에서 동의 정책 데이터를 사용할 수 있도록 하고 수집 시 방문자 데이터를 필터링하는 방법을 개괄적으로 보여 줍니다.

![동의 보고 및 필터링 개요](assets/consent-overview.png)

| 숫자 | 기능 | 함수 |
|---------|----------|---------|
| 1 | 동의 보고 및 필터링 구성 | 동의 보고 및 선택적으로 동의 필터링을 활성화하는 데 사용되는 Customer Journey Analytics의 구성 인터페이스입니다. |
| 2 | 샌드박스 | 보고할 동의 정책 멤버십 데이터를 포함하는 프로필 데이터 세트가 있어야 합니다. |
| 3 | 프로필 데이터 세트 | 각 방문자에 대한 동의 정책 멤버십 데이터를 포함합니다. 동의 정책 멤버십은 프로필 데이터 집합의 `consentPoliciesIDMap` 필드에 저장됩니다. 이 프로필 데이터 세트는 선택한 연결에 추가됩니다. <p>각 방문자의 프로필에는 방문자가 일치하는 동의 정책이 나열됩니다. Customer Journey Analytics은 이 필드를 읽어 보고에 사용할 수 있는 동의 정책을 만들고 수집 중에 포함할 방문자를 평가합니다.</p> |
| 4 | 동의 정책 조회 데이터 세트 | 보고할 친숙한 정책 이름 및 설명을 제공합니다. 조회 데이터 세트는 자동으로 생성되고 Experience Platform과 계속 동기화됩니다. 샌드박스당 최대 1개의 동의 정책 조회 데이터 세트가 있습니다. |
| 5 | 연결 | 동의 보고 및 필터링이 적용되는 연결입니다. 연결 아래의 모든 데이터 보기는 구성을 상속합니다. |
| 6 | 동의 정책 구성 요소 | 동의 정책 멤버십을 나타내는 새 차원, 지표 및 파생 필드입니다. 이러한 구성 요소는 자동으로 생성되며 Analysis Workspace에서 보고에 사용할 수 있습니다. |
| 7 | 수집 시간 필터링 | 필터링을 활성화하면 동의하지 않는 방문자는 사용자가 구성하는 마케팅 작업에 따라 수집 중에 제외됩니다. |

## 동의 보고와 필터링

동의 보고 및 필터링은 두 가지 별개의 기능입니다. 동의 보고를 자체적으로 활성화하거나 보고와 필터링을 함께 활성화할 수 있습니다.

### 동의 보고

동의 보고를 활성화하면 Customer Journey Analytics은 구성된 연결 아래의 데이터 보기에 동의 정책 구성 요소 집합을 추가합니다. 이러한 구성 요소를 사용하면 Analysis Workspace 프로필 데이터 세트의 동의 정책 멤버십 데이터를 사용하여 Experience Platform을 사용하여 다양한 동의 정책과 일치하는 방문자를 보고할 수 있습니다.

보고를 읽기 쉽게 하기 위해 Customer Journey Analytics은 Experience Platform의 정책 이름 및 설명을 동의 정책 조회 데이터 세트로 동기화합니다. Experience Platform에서 정책을 만들거나, 업데이트하거나, 이름을 바꾸거나, 삭제하면 조회 데이터 세트가 자동으로 업데이트됩니다.

동의 보고에서 만드는 구성 요소에 대한 자세한 내용은 [동의 정책 데이터 분석](/help/connections/consent-reporting-filtering/consent-analyze.md)을 참조하십시오.

### 동의 필터링

>[!IMPORTANT]
>
>필터링(제외됨)된 동의 데이터는 Customer Journey Analytics에 저장되지 않으며 구성을 업데이트하여 지난 날짜 동안 복구할 수 없습니다.

동의 필터링을 활성화하면 Customer Journey Analytics에서는 수집 시 동의하지 않는 방문자를 제외합니다. 필터링은 수집 시에 발생하므로 제외된 방문자의 데이터는 Customer Journey Analytics에 들어오지 않고 보고에 사용할 수 없습니다.

동의 필터링을 사용할 때는 다음 사항을 고려하십시오.

* Customer Journey Analytics은 구성한 마케팅 작업에 적용되는 동의 정책을 결정합니다.

  마케팅 액션은 데이터 사용 카테고리를 나타냅니다. Customer Journey Analytics은 각 마케팅 작업에 적용되는 동의 정책을 결정하며, [구성을 만들](/help/connections/consent-reporting-filtering/consent-configure.md#create-a-configuration) 때 각 마케팅 작업에 대해 독립적으로 필터링을 활성화합니다.

  | 마케팅 액션 | 설명 |
  |---------|----------|
  | **[!UICONTROL Analytics]** | Analysis Workspace의 표준 Customer Journey Analytics 보고. |
  | **[!UICONTROL 데이터 과학]** | 고급 분석, 머신 러닝 및 데이터 과학 사용 사례. |

* 방문자의 데이터는 해당 동의 정책 **모두**&#x200B;와(과) 일치하는 경우에만 수집됩니다. 방문자에게 적용 가능한 정책이 없는 경우 해당 방문자의 데이터는 제외됩니다.

## 동의 보고 및 필터링 구성

동의 보고 및 필터링을 구성할 때는 동의 정책 멤버십 데이터가 포함된 샌드박스 및 프로필 데이터 세트를 선택하고, 구성할 연결 또는 연결을 선택하고, 각 마케팅 작업에 대한 데이터를 필터링할지 여부를 선택합니다. 그런 다음 Customer Journey Analytics은 동의 정책 조회 데이터 세트와 동의 정책 구성 요소를 자동으로 만듭니다.

자세한 내용은 [동의 보고 및 필터링 구성](/help/connections/consent-reporting-filtering/consent-configure.md)을 참조하십시오.

## 동의 보고 및 필터링 구성 관리

동의 보고 및 필터링 구성을 만든 후 관리할 수 있습니다. 구성을 보고, 편집하고, 삭제할 수 있습니다.

기존 구성 관리에 대한 자세한 내용은 [동의 보고 및 필터링 구성 관리](/help/connections/consent-reporting-filtering/consent-manage.md)를 참조하십시오.

## 동의 정책 데이터 분석

Customer Journey Analytics에서 동의 정책 데이터를 사용할 수 있으면 어떤 방문자가 어떤 동의 정책과 일치하는지 보고하고 해당 insight을 사용하여 보고서에서 동의를 받는 대상자를 이해할 수 있습니다.

자세한 내용은 [동의 정책 데이터 분석](/help/connections/consent-reporting-filtering/consent-analyze.md)을 참조하십시오.

## 동의 보고 및 필터링 역할 및 권한 요구 사항

동의 보고 및 필터링에는 다음 Customer Journey Analytics 역할 및 Experience Platform 권한이 필요합니다.

| 기능 | Customer Journey Analytics 역할 또는 권한 요구 사항 | Experience Platform 권한 요구 사항 |
|---------|----------|----------|
| [동의 보고 및 필터링 구성 만들기](/help/connections/consent-reporting-filtering/consent-configure.md) | 시스템 관리자 | <ul><li>데이터 세트: 읽기, 쓰기</li><li>스키마: 읽기, 쓰기</li></ul> <p>동의 정책 멤버십 데이터를 포함하는 프로필 데이터 세트에 대한 읽기 액세스 권한이 필요합니다. 동의 정책 조회 데이터 세트가 만들어지고 동기화되므로 쓰기 권한이 필요합니다.</p> |
| 데이터 보기에서 동의 정책 구성 요소 보기 | 데이터 보기가 할당된 제품 프로필의 제품 프로필 관리자 <p>자세한 내용은 [액세스 제어](/help/technotes/access-control.md)를 참조하십시오.</p> | 해당 사항 없음 |
| Analysis Workspace에서 동의 정책 구성 요소 사용 | 동의 정책 구성 요소가 추가된 데이터 보기에 대한 액세스 | 해당 없음 |

## 동의 보고 및 필터링 사용 사례

예를 들어 동의 보고 및 필터링이 제공하는 값을 강조 표시하는 사용 사례는 [동의 보고 및 필터링 사용 사례](/help/connections/consent-reporting-filtering/consent-use-cases.md)를 참조하십시오.

## 동의 보고 및 필터링 제한

[동의 보고 및 필터링을 구성](/help/connections/consent-reporting-filtering/consent-configure.md)할 때 다음 제한을 고려하십시오.

* 단일 샌드박스에는 동의 정책 조회 데이터 세트가 하나만 있을 수 있습니다. 동일한 샌드박스의 여러 구성이 해당 조회 데이터 세트를 공유합니다.

* 연결은 하나의 동의 보고 및 필터링 구성에만 연결할 수 있습니다.
