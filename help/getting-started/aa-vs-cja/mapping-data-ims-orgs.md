---
title: 여러 IMS 조직의 Analytics 데이터 매핑
description: 여러 소스 IMS 조직의 보고서 세트 데이터를 보고서 세트 및 궁극적으로 대상 IMS 조직의 데이터 세트에 매핑하도록 요청하는 방법을 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
exl-id: c109742b-c1c5-45b3-971f-f8dcf814ec37
source-git-commit: 888420e8cd11cd447fec99257b213669edd345c1
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 1%

---

# Cross-IMS 데이터 매핑

이 문서에서는 여러 IMS 조직의 보고서 세트 데이터를 하나의 IMS 조직의 보고서 세트 및 궁극적으로 데이터 세트에 매핑하는 방법에 대해 설명합니다.

Analytics 소스 커넥터는 기본적으로 단일 조직 내의 Adobe Analytics 보고서 세트에서 데이터를 수집합니다. *IMS 간 데이터 매핑*&#x200B;은(는) 여러 IMS 조직의 Analytics 데이터를 매핑하는 기능이며 이 제한에 대한 솔루션을 제공합니다. 이 기능을 활성화하는 프로세스는 이 문서에 설명되어 있습니다.


## 시나리오

여러 IMS 조직과 함께 프로비저닝되고 이러한 IMS 조직의 여러 보고서 세트에 Analytics 데이터가 있습니다. 이 설정은 다음과 같은 결과일 수 있습니다.

* 인수 또는 합병
* 조직 구조 요구 사항
* 지역 배포 제한

기본적으로 Customer Journey Analytics의 여러 IMS 조직에서 여러 보고서 세트의 데이터 조합에 대해 보고할 수 없습니다. 이 제한이 적용되는 이유는 Analytics 소스 커넥터를 통한 Adobe Analytics에서 Experience Platform으로의 데이터 수집은 단일 IMS 조직이 소유한 데이터의 수집만 지원하기 때문입니다. 프로비저닝되고 Adobe Analytics, Experience Platform 및 Customer Journey Analytics에 로그인하는 데 사용하는 IMS 조직입니다.

*IMS 간 데이터 매핑* 기능을 사용하면 Adobe에 데이터 매핑을 요청할 수 있습니다. 이 기능은 Analytics 소스 커넥터를 사용하여 여러 *source* IMS 조직에 있는 보고서 세트의 데이터를 하나의 *destination* IMS 조직에 속하는 보고서 세트(및 궁극적으로 데이터 세트)에 매핑합니다. 예:

| 그림 | 설명 |
|---|---|
| ![여러 IMS 조직 간에 데이터 매핑](/help/getting-started/assets/map-data-across-ims-orgs.svg) | 이 매핑을 통해 IMS 조직 3 내에서 프로비저닝된 Customer Journey Analytics의 한 연결에서 IMS 조직 1, IMS 조직 2 및 IMS 조직 3에 존재하는 보고서 세트에 대해 보고할 수 있습니다. |

{style="table-layout:fixed"}

## 사용 방법

*IMS 간 데이터 매핑* 기능을 구성하고 활성화하려면 Adobe 계정 관리자를 통해 매핑을 요청해야 합니다. 이렇게 하려면 다음 작업을 수행하십시오.

1. 대상 IMS 조직 관리자는 보고서 세트를 매핑할 모든 소스 IMS 조직 관리자에게 승인 이메일을 요청합니다. 다음 텍스트를 이메일의 템플릿으로 사용하여 소스 IMS 조직 관리자에게 승인을 요청할 수 있습니다.

   | 샘플 이메일 템플릿 |
   | --- |
   | *회사 이름 담당자* 선택한 대상 조직에 다음 IMS 조직(원본 IMS 조직 목록)에 대한 액세스 권한을 부여하려면 각 IMS 조직의 관리자가 해당 데이터에 대한 액세스 권한을 허용하도록 승인을 제출하도록 해야 합니다. 이렇게 하면 영향을 받는 IMS 조직의 데이터 액세스 권한을 준수할 수 있습니다. 적절한 승인을 받으려면 각 관리 조직의 등록된 Adobe 관리자가 이 전자 메일에 이름과 해당 조직이 나타내는 IMS 조직을 회신하도록 요청하세요. &quot;승인합니다&quot;라고 말하면 이 IMS 조직의 데이터가 대상 조직 [목록 대상 IMS 조직]에 표시되도록 승인한다는 의미입니다. 이 관리자는 해당 IMS 조직의 관리자로 Adobe 시스템에 등록된 관리자여야 합니다. |

1. 여러 소스 IMS 조직 내의 보고서 세트에서 대상 IMS 조직으로의 매핑을 요청하는 대상 IMS 조직 관리자를 대신하여 Adobe 계정 관리자에게 이메일을 보냅니다. 소스 IMS 조직 관리자로부터 받은 승인 이메일을 첨부합니다.

Adobe 계정 관리자가 여러 조직의 Analytics 데이터를 매핑하라는 요청과 함께 이메일을 수신하면 Adobe 내에서 요청을 검토합니다. 추가 질문, 선택적 교육 및 기타 정보가 필요하면 Adobe 계정 관리자가 연락합니다.

승인되면 요청된 매핑이 만들어지고 사용자에게 알림이 전송됩니다. 소스 IMS 조직 이름이 Experience Platform의 Analytics 보고서 세트 [목록](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data)에 있는 보고서 세트 이름에 추가됩니다.


## 제한 사항

*Cross-IMS 데이터 매핑* 기능에는 다음 제한 사항이 적용되지 않습니다.

* 조직 간에 보고서 세트를 한 번만 연결할 수 있습니다.
* 매핑 삭제를 요청하려면 매핑에서 대상 IMS 조직으로 정의된 IMS 조직에 대한 모든 연결을 삭제해야 합니다.
* ECID는 매핑된 소스 IMS 조직 간에 호환되지 않으며 대상 IMS 조직과 호환되지 않습니다.


## 고려 사항

*IMS 간 데이터 매핑* 기능을 요청하기 전에 다음 항목을 고려해야 할 수 있습니다.

### 프로필

*IMS 간 데이터 매핑* 기능이 승인되면 대상 IMS 조직에 있는 하나 이상의 보고서 세트에 대한 데이터를 Experience Platform에 추가할 수 있습니다. [Analytics 원본 커넥터](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)의 구성을 통해 이 작업을 수행합니다. 그런 다음 Experience Platform에서 Target 데이터 세트가 만들어집니다. 이 구성 및 프로세스의 일부로 하나 이상의 보고서 세트에서 프로필 서비스로 프로필 데이터를 전송하는 옵션이 있습니다.

위에 설명된 대로 구성 및 프로세스의 결과인 총 프로필 수를 예측합니다. 총 수가 대상 조직에 대해 계약상 부여되는 프로필 수 이내인지 확인합니다. [필터링 규칙 및 조건](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#filtering-for-profile){target="_blank"}을(를) 적용하여 데이터를 수집에서 프로필 서비스에 선택적으로 포함하거나 제외합니다. 또는 관련 보고서 세트에 대해 프로필 서비스로 프로필 데이터를 전송하는 옵션을 비활성화합니다.


#### 결합

대상 데이터 세트에서 [필드 기반](/help/stitching/fbs.md) 및 [그래프 기반](/help/stitching/gbs.md) 결합을 모두 사용할 수 있습니다. 이러한 대상 데이터 세트 중 하나 이상에 대해 그래프 기반 결합을 사용하는 경우 [프로필](#profiles) 섹션에 설명된 대로 프로필 수에 대한 계약 권한 내에 있어야 합니다.

실시간 고객 프로필에 대한 라이선스가 없어도 하나 이상의 대상 데이터 세트에서 그래프 기반 결합을 사용하려는 경우 이러한 대상 데이터 세트에 대해서만 [ID 서비스](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)를 사용하도록 설정해야 합니다.


### 권한

대상 IMS 조직에서 Analytics 소스 커넥터를 구성할 수 있는 권한이 있는 사용자는 매핑된 소스 IMS 조직에서 Analytics 데이터를 수집할 수 있습니다. 소스 IMS 조직에 대해 해당 사용자에 대한 권한이 확인되지 않습니다.

### 데이터에 대한 보고서

*IMS 간 데이터 매핑* 기능은 Customer Journey Analytics [연결](/help/connections/overview.md), 하나 이상의 [데이터 보기](/help/data-views/data-views.md) 및 [작업 영역 프로젝트](/help/analysis-workspace/home.md)의 일부로 데이터를 사용할 수 있도록 하는 첫 번째 단계일 뿐입니다. 한 IMS 조직에서 현재 사용할 수 있는 데이터를 주의 깊게 검사해야 합니다. 또한 이 데이터에 대해 제대로 보고하기 전에 데이터 준비, 파생 필드, 추가 조회 테이블 등과 같은 기능을 고려하십시오.
