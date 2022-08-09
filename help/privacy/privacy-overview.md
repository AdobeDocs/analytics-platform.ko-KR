---
title: Customer Journey Analytics 및 데이터 거버넌스
description: Customer Journey Analytics에서 데이터 거버넌스가 작동하는 방식을 설명합니다.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 2f74c10f821aed421e31ee8e14b854f2a73c11f1
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 75%

---

# Customer Journey Analytics 및 데이터 거버넌스

일반적으로 Customer Journey Analytics의 모든 데이터 거버넌스 관련 설정은 Adobe Experience Platform에서 상속됩니다.

## 데이터 거버넌스

CJA는 Adobe Experience Platform에 설정된 데이터 거버넌스 레이블 및 정책을 지원합니다. 자세한 내용은 [Adobe Experience Platform 데이터 거버넌스에 대한 CJA 지원](/help/data-views/data-governance.md).

## GDPR

Customer Journey Analytics는 GDPR(General Data Protection Regulation) Central Service에 직접 가입되어 있지 않으며 대신 Experience Platform에서 수행한 데이터 세트 변경 사항을 모두 상속합니다. Adobe는 Platform Data Lake를 통해 GDPR 삭제 요청을 시행하고 파이프라인에서 삭제 요청이 완료되면 Adobe에 통보합니다. Adobe는 파이프라인의 의견을 경청하여 이벤트 데이터 세트에 대한 Customer Journey Analytics에서 영향받는 배치의 변경 사항을 모두 동기화합니다. GDPR 삭제 요청의 영향을 받는 프로필 및 조회 데이터 세트는 각 삭제 요청 이후에 완전히 다시 수집됩니다. Adobe는 Data Lake에서 삭제 이벤트가 발생한 후 7일 이내에 삭제 요청이 실행되도록 보장할 수 있습니다.

## CCPA

CCPA(California Consumer Privacy Act)는 미국 캘리포니아주 거주자를 위해 개인정보 보호 권한 및 소비자 보호를 개선합니다. 이 조례는 2020년 1월 1일부터 시행됩니다.
CCPA는 개인 데이터의 판매 및 공개 여부(및 공개된 대상)를 인지하고, 개인 데이터 판매를 거부하기 위한 개인 데이터 액세스 및 삭제 권한과 같은 새로운 데이터 개인정보 보호 권한을 캘리포니아주 거주자에게 제공합니다.
CCPA에 따라 개인정보 보호 서비스는 개인 데이터 판매를 거부하는 요청을 지원합니다.
