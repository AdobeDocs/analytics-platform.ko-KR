---
title: 고객 관리 키
description: CJA용 고객 관리 키를 설정하는 방법을 알아봅니다.
hide: true
hidefromtoc: true
source-git-commit: ce386f30e344b3921689a8ecc0e6fba0a55137f9
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# 고객 관리 키

>[!NOTE]
>
>이 기능은 2022년 11월에 제공될 예정입니다.

Customer Journey Analytics(CJA)는 [의료 보호](https://www.adobe.com/trust/compliance/hipaa-ready.html) 및 Privacy &amp; Security Shield 고객이 CJA 데이터에 적용할 CMK(Azure Customer Managed Key)를 활용하도록 합니다.  이 프로세스는 [Adobe Experience Platform CMK 설정](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>고객 관리 키는 현재 [의료 보호 또는 개인 정보 보호 및 보안 보호](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) 추가 기능 제공.

다음 단계에 따라 CJA용 CMK를 설정합니다.

1. Adobe 계정 팀과 확인하여 CMK에 대한 권한이 있는지 확인합니다.
1. CJA에서만 사용할 새 Azure 키 저장소를 만듭니다.
1. Azure 키 값을 Azure CJA CMK 앱에 연결(팔로우 링크).
1. CMK 설정을 요청하는 Adobe 고객 지원 티켓을 만듭니다. 티켓에 Azure URI를 포함하십시오.
1. Adobe 고객 지원 센터에서 CJA 데이터에 대한 CMK 애플리케이션 완료를 확인합니다.
