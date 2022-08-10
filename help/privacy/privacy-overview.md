---
title: Customer Journey Analytics 및 데이터 거버넌스
description: Customer Journey Analytics에서 데이터 거버넌스가 작동하는 방식을 설명합니다.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 0d48c1ed8d0bf50939f8eda1f5656c95370ac0b7
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 51%

---

# Customer Journey Analytics 및 데이터 거버넌스

일반적으로 Customer Journey Analytics의 모든 데이터 거버넌스 관련 설정은 Adobe Experience Platform에서 상속됩니다.

## 데이터 거버넌스

CJA와 의 통합 [Adobe Experience Platform 데이터 거버넌스](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) 에서는 중요한 CJA 데이터에 대한 레이블 지정 및 개인 정보 보호 정책을 적용할 수 있습니다.

Experience Platform이 사용하는 데이터 세트에서 만들어진 개인 정보 레이블 및 정책은 CJA 데이터 보기 워크플로우에서 표시할 수 있습니다. 이러한 레이블은 중요 필드에서 지표 및/또는 차원을 생성하는 사용자에게 중지하거나 경고 합니다.

또한 CJA에서 데이터를 내보낼 때(보고, 내보내기, API 등을 통해) 경고 또는 레이블이 추가되어 보고서에 특정 방식으로 처리되어야 하는 중요한 정보가 포함되어 있음을 사용자에게 알립니다.

이러한 통합을 통해 규정 준수를 보다 손쉽게 관리할 수 있습니다. 조직의 데이터 관리자는 사용을 제한하는 정책을 설정할 수 있습니다. 그 결과 CJA 사용자는 데이터 관리자가 정의한 정책을 준수한다는 것을 알고 데이터를 보다 안전하게 사용할 수 있습니다.

## GDPR

Customer Journey Analytics는 GDPR(General Data Protection Regulation) Central Service에 직접 가입되어 있지 않으며 대신 Experience Platform에서 수행한 데이터 세트 변경 사항을 모두 상속합니다. Adobe는 Platform Data Lake를 통해 GDPR 삭제 요청을 시행하고 파이프라인에서 삭제 요청이 완료되면 Adobe에 통보합니다. Adobe는 파이프라인의 의견을 경청하여 이벤트 데이터 세트에 대한 Customer Journey Analytics에서 영향받는 배치의 변경 사항을 모두 동기화합니다. GDPR 삭제 요청의 영향을 받는 프로필 및 조회 데이터 세트는 각 삭제 요청 이후에 완전히 다시 수집됩니다. Adobe는 Data Lake에서 삭제 이벤트가 발생한 후 7일 이내에 삭제 요청이 실행되도록 보장할 수 있습니다.

## CCPA

CCPA(California Consumer Privacy Act)는 미국 캘리포니아주 거주자를 위해 개인정보 보호 권한 및 소비자 보호를 개선합니다. 이 법은 2020년 1월 1일부터 시행되었습니다.
CCPA는 개인 데이터의 판매 및 공개 여부(및 공개된 대상)를 인지하고, 개인 데이터 판매를 거부하기 위한 개인 데이터 액세스 및 삭제 권한과 같은 새로운 데이터 개인정보 보호 권한을 캘리포니아주 거주자에게 제공합니다.
CCPA에 따라 개인정보 보호 서비스는 개인 데이터 판매를 거부하는 요청을 지원합니다.
