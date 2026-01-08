---
title: 여러 IMS 조직의 Analytics 데이터 매핑
description: 여러 소스 IMS 조직의 보고서 세트에서 대상 IMS 조직으로 데이터를 매핑하도록 요청하는 방법에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
source-git-commit: 3c34bd50c12b370f5e9f95ac5d6357de4f63e5f6
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# 여러 IMS 조직의 Analytics 데이터 매핑

Analytics 소스 커넥터는 Customer Journey Analytics을 사용할 권한이 있는 동일한 조직에 속한 Adobe Analytics 보고서 세트에서만 데이터를 수집할 수 있습니다. 여러 IMS 조직의 Analytics 데이터를 매핑하는 기능은 이 제한에 대한 솔루션을 제공합니다. 이 기능을 활성화하는 프로세스는 이 문서에 설명되어 있습니다.


## 시나리오

여러 IMS 조직과 함께 프로비저닝되고 이러한 IMS 조직의 여러 보고서 세트에 Analytics 데이터가 있습니다. 이 설정은 다음과 같은 결과일 수 있습니다.

* 인수 또는 합병
* 조직 구조 요구 사항
* 지역 배포 제한

기본적으로 Customer Journey Analytics의 여러 IMS 조직에서 여러 보고서 세트의 데이터 조합에 대해 보고할 수 없습니다. 이 제한이 적용되는 이유는 Analytics 소스 커넥터를 통한 Adobe Analytics에서 Experience Platform으로의 데이터 수집은 단일 IMS 조직이 소유한 데이터의 수집만 지원하기 때문입니다. 프로비저닝되고 Adobe Analytics, Experience Platform 및 Customer Journey Analytics에 로그인하는 데 사용하는 IMS 조직입니다.

*여러 IMS 조직의 Analytics 데이터 매핑* 기능을 사용하면 Adobe에 데이터 매핑을 요청할 수 있습니다. 이 기능은 Analytics 소스 커넥터를 사용하여 여러 *소스* IMS 조직에 있는 보고서 세트의 데이터를 하나의 *대상* IMS 조직에 속한 데이터 세트에 매핑합니다. 예:

| 그림 | 설명 |
|---|---|
| ![여러 IMS 조직 간에 데이터 매핑](/help/getting-started/assets/map-data-across-ims-orgs.svg) | 이 매핑을 통해 IMS 조직 3 내에서 프로비저닝된 Customer Journey Analytics의 한 연결에서 IMS 조직 1, IMS 조직 2 및 IMS 조직 3에 존재하는 보고서 세트에 대해 보고할 수 있습니다. |

{style="table-layout:fixed"}

## 사용 방법

*여러 IMS 조직의 Analytics 데이터 매핑* 기능을 구성하고 활성화하려면 Adobe 계정 관리자를 통해 매핑을 요청해야 합니다. 이렇게 하려면 다음 작업을 수행하십시오.

1. 대상 IMS 조직 관리자는 보고서 세트를 매핑할 모든 소스 IMS 조직 관리자에게 승인 이메일을 요청합니다. 다음 텍스트를 이메일의 템플릿으로 사용하여 소스 IMS 조직 관리자에게 승인을 요청할 수 있습니다.

   | 샘플 이메일 템플릿 |
   | --- |
   | *회사 이름 담당자* 선택한 대상 조직에 다음 IMS 조직(원본 IMS 조직 목록)에 대한 액세스 권한을 부여하려면 각 IMS 조직의 관리자가 해당 데이터에 대한 액세스 권한을 허용하도록 승인을 제출하도록 해야 합니다. 이렇게 하면 영향을 받는 IMS 조직의 데이터 액세스 권한을 준수할 수 있습니다. 적절한 승인을 받으려면 각 관리 조직의 등록된 Adobe 관리자가 이 전자 메일에 이름과 해당 조직이 나타내는 IMS 조직을 회신하도록 요청하세요. &quot;승인합니다&quot;라고 말하면 이 IMS 조직의 데이터가 대상 조직 [목록 대상 IMS 조직]에 표시되도록 승인한다는 의미입니다. 이 관리자는 해당 IMS 조직의 관리자로 Adobe 시스템에 등록된 관리자여야 합니다. |

1. 여러 소스 IMS 조직 내의 보고서 세트에서 대상 IMS 조직으로의 매핑을 요청하는 Adobe 계정 관리자에게 대상 IMS 조직 관리자로 이메일을 보냅니다. 소스 IMS 조직 관리자로부터 받은 승인 이메일을 첨부합니다.

계정 관리자가 여러 조직의 Analytics 데이터를 매핑하라는 요청과 함께 이메일을 수신하면 Adobe 내에서 요청을 검토합니다. 계정 관리자는 추가 질문, 선택적 교육 및 기타 정보를 얻기 위해 귀하에게 연락합니다.

승인되면 요청된 매핑이 만들어지고 사용자에게 알림이 전송됩니다. 소스 IMS 조직 이름이 Experience Platform의 Analytics 보고서 세트 [목록](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data)에 있는 보고서 세트 이름에 추가됩니다.

## 제한 사항 및 위험

*여러 IMS 조직의 Analytics 데이터 매핑* 기능에는 다음 제한이 적용되지 않습니다.

* 조직 간에 보고서 세트를 한 번만 연결할 수 있습니다.
* 매핑 삭제를 요청하려면 매핑에서 대상 IMS 조직으로 정의된 IMS 조직에 대한 모든 연결을 삭제해야 합니다.
* ECID는 매핑된 소스 IMS 조직 간에 호환되지 않으며 대상 IMS 조직과 호환되지 않습니다.
* 대상 IMS 조직에서 Analytics 소스 커넥터를 구성할 수 있는 권한이 있는 사용자는 매핑된 소스 IMS 조직에서 Analytics 데이터를 수집할 수 있습니다. 소스 IMS 조직에 대해 해당 사용자에 대한 권한이 확인되지 않습니다.
