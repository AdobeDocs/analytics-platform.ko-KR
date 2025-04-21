---
title: 고객 관리 키
description: Customer Journey Analytics을 위해 고객 관리 키를 설정하는 방법에 대해 알아봅니다.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---

# 고객 관리 키

Adobe Customer Journey Analytics는 [Healthcare Shield](https://www.adobe.com/kr/trust/compliance/hipaa-ready.html) 및 Privacy &amp; Security Shield 고객에게 Customer Journey Analytics 데이터에 대한 고객 관리 키(CMK)를 사용할 수 있는 옵션을 제공합니다. 이 프로세스는 [Adobe Experience Platform CMK 설정](https://experienceleague.adobe.com/ko/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview)과 별개라는 점을 참고하십시오. 고객 관리 키는 [Healthcare Shield 또는 Privacy &amp; Security Shield](https://experienceleague.adobe.com/ko/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield) 추가 기능 서비스를 구입한 조직에서만 사용할 수 있습니다.

## Azure에서 Customer Journey Analytics를 위한 고객 관리 키 설정

Azure에서 실행되는 Customer Journey Analytics를 위한 CMK를 설정하려면 다음 단계를 수행하십시오.

1. Adobe Customer Journey Analytics CMK에 대한 권한이 있는지, 조직에서 Azure에서 실행되는 Adobe Experience Platform을 사용하는지 확인합니다. Adobe 계정 팀에 문의하여 이러한 권한을 확인할 수 있습니다.
1. Azure에서 애플리케이션 관리자, 클라우드 애플리케이션 관리자 또는 전역 관리자와 같은 권한이 부여된 역할을 가진 관리자인지 확인하십시오. 자세한 내용은 [Microsoft Entra 기본 제공 역할](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference)을 참조하십시오.
1. Customer Journey Analytics에서만 사용할 새 Azure 키 값을 만듭니다. 자세한 내용은 [Microsoft Azure 키 자격 증명 설명서](https://learn.microsoft.com/ko-kr/azure/key-vault/general/)를 참조하십시오.
1. 키 자격 증명의 키에 대한 액세스 권한을 Adobe Azure 앱에 부여합니다. 자세한 내용은 [기존 계정에 대한 고객 관리 키 구성](https://learn.microsoft.com/ko-kr/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)을 참조하십시오. Adobe 애플리케이션 ID는 다음과 같습니다.

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. CMK 설정을 요청하는 Adobe 고객 지원 티켓을 생성합니다. 티켓에 Azure URI를 포함하십시오. URI는 Azure 키의 **키 식별자** 필드에서 찾을 수 있습니다.

   ![https://cmkoberontest.vault.azure.net에 대한 URI를 표시하는 키 식별자 필드](assets/key-identifier.png)

1. Adobe 고객 지원 센터는 Customer Journey Analytics 데이터에 대한 CMK 신청이 완료되었음을 확인합니다.

Platform에서 사용하는 모든 데이터는 고객 관리 키의 유무에 관계없이 데이터를 안전하게 유지하기 위해 전송 중이거나 사용하지 않을 때 암호화됩니다. Adobe Experience Platform 암호화에 대한 자세한 내용은 [Adobe Experience Platform의 데이터 암호화](https://experienceleague.adobe.com/ko/docs/experience-platform/landing/governance-privacy-security/encryption)를 참조하십시오.

## Amazon Web Services에서 Customer Journey Analytics를 위한 고객 관리 키 설정

>[!AVAILABILITY]
>
>이 섹션은 Amazon Web Services(AWS)에서 실행되는 Experience Platform 구현에 적용됩니다. AWS에서 실행되는 Experience Platform은 현재 제한된 수의 고객에게만 제공됩니다. 지원되는 Experience Platform 인프라에 대해 자세히 알아보려면 [Experience Platform 멀티 클라우드 개요](https://experienceleague.adobe.com/ko/docs/experience-platform/landing/multi-cloud)를 참조하십시오.

조직이 Amazon Web Services에서 실행되는 Adobe Experience Platform을 사용하는 경우 CMK는 이미 구성되어 있습니다. 추가적인 설정이 필요 없습니다.
