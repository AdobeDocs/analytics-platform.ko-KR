---
title: 고객 관리 키
description: CJA용 고객 관리 키를 설정하는 방법을 알아봅니다.
hide: true
hidefromtoc: true
source-git-commit: 3aa5d9e1b426e67f27ef1909a2640f335719502a
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 33%

---

# 고객 관리 키

>[!NOTE]
>
>이 기능은 2022년 11월에 사용할 수 있습니다.

Customer Journey Analytics(CJA)는 [의료 보호](https://www.adobe.com/trust/compliance/hipaa-ready.html) 및 Privacy &amp; Security Shield 고객이 CJA 데이터에 적용할 CMK(Azure Customer Managed Key)를 활용하도록 합니다.  이 프로세스는 [Adobe Experience Platform CMK 설정](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>고객 관리 키는 현재 [Healthcare Shield 또는 Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) 추가 기능 서비스를 구입한 조직에서만 사용할 수 있습니다.

## CJA용 CMK 설정

다음 단계에 따라 CJA용 CMK를 설정하십시오.

1. Adobe 계정 팀과 확인하여 CJA CMK Adobe 권한이 있는지 확인합니다.
1. Azure에서 사용자는 응용 프로그램 관리자, 클라우드 응용 프로그램 관리자 또는 글로벌 관리자와 같은 권한이 있는 관리자인지 확인하십시오. [Microsoft에서 자세히 알아보기](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. CJA에서만 사용할 새 Azure 키 값을 만듭니다. [Microsoft에서 자세히 알아보기](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. 키 저장소에서 키에 대한 Adobe Azure 앱 액세스 권한을 부여합니다. Adobe 애플리케이션 ID입니다. 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Microsoft에서 자세히 알아보기](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. CMK 설정을 요청하는 Adobe 고객 지원 티켓을 생성합니다. 티켓에 Azure URI를 포함하십시오.
1. Adobe 고객 지원 센터에서 CJA 데이터에 대한 CMK 애플리케이션 완료를 확인합니다.
