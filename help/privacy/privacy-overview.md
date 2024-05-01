---
title: Customer Journey Analytics 및 데이터 거버넌스
description: Customer Journey Analytics에서 데이터 거버넌스가 작동하는 방식을 설명합니다.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 56%

---

# Adobe Customer Journey Analytics 및 데이터 거버넌스

일반적으로 Customer Journey Analytics의 데이터 거버넌스 관련 설정은 Adobe Experience Platform에서 상속됩니다.

## 데이터 거버넌스

Adobe Customer Journey Analytics과 의 통합 [Adobe Experience Platform 데이터 거버넌스](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=ko-KR?lang=ko) 민감한 Customer Journey Analytics 데이터의 레이블 지정 및 개인정보 처리방침 시행을 허용합니다.

Experience Platform에서 사용하는 데이터 세트에 생성된 개인정보 보호 레이블 및 정책은 Customer Journey Analytics 데이터 보기 워크플로에 표시될 수 있습니다. 이러한 레이블은 중요한 필드에서 지표 및/또는 차원을 생성하는 사용자를 중단 또는 경고합니다.

또한 보고, 내보내기, API 등을 통해 Customer Journey Analytics에서 데이터를 내보낼 경우, 보고서에 특정 방식으로 처리해야 하는 기밀 정보가 포함되어 있음을 사용자에게 통지하기 위해 경고 또는 레이블이 추가됩니다.

이 통합을 통해 규정 준수를 보다 쉽게 관리할 수 있습니다. 조직의 데이터 관리자는 사용을 제한하는 정책을 설정할 수 있습니다. 따라서 Customer Journey Analytics 사용자는 데이터 관리자에 의해 정의된 정책을 준수함을 알고 보다 자신 있게 데이터를 사용할 수 있습니다.

[자세히 알아보기](/help/data-views/data-governance.md)

## GDPR

Customer Journey Analytics는 GDPR(General Data Protection Regulation) Central Service에 직접 가입되어 있지 않으며 대신 Experience Platform에서 수행한 데이터 세트 변경 사항을 모두 상속합니다. Customer Journey Analytics은 Platform Data Lake에 따라 GDPR 삭제 요청을 적용하고 요청이 완료되면 Customer Journey Analytics에게 알립니다. 이벤트 데이터 세트에 대한 Customer Journey Analytics의 영향을 받는 배치에 대한 모든 변경 사항은 플랫폼 데이터와 동기화됩니다. GDPR 삭제 요청의 영향을 받는 프로필 및 조회 데이터 세트는 각 삭제 요청 후에 완전히 다시 수집됩니다. 삭제 요청은 일반적으로 데이터 레이크에서 삭제 이벤트가 발생한 후 7일 이내에 완료됩니다.

## CCPA

CCPA(California Consumer Privacy Act)는 미국 캘리포니아주 거주자를 위해 개인정보 보호 권한 및 소비자 보호를 개선합니다. 이 법은 2020년 1월 1일부터 시행되었습니다.
CCPA는 개인 데이터의 판매 및 공개 여부(및 공개된 대상)를 인지하고, 개인 데이터 판매를 거부하기 위한 개인 데이터 액세스 및 삭제 권한과 같은 새로운 데이터 개인정보 보호 권한을 캘리포니아주 거주자에게 제공합니다.
CCPA에 따라 Privacy Service는 개인 데이터 판매를 거부하도록 요청을 지원합니다.
