---
title: 고객 경로 분석 개인 정보 보호 개요
description: 고객 경로 분석에서 개인 정보 설정이 작동하는 방식을 설명합니다.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# 고객 경로 분석 개인 정보 보호 개요

일반적으로 고객 여정 분석의 개인 정보 관련 설정은 Adobe Experience Platform에서 상속됩니다.

## GDPR

Customer Journey Analytics는 GDPR(General Data Protection Regulation) Central Service에 직접 가입하지 않으며 대신 Experience Platform에서 수행한 모든 데이터 세트 변경 사항을 상속합니다. Adobe는 Platform Data Lake를 통해 GDPR 삭제 요청을 시행하고 파이프라인에서 완료되면 Adobe에 통보합니다. Adobe는 파이프라인의 의견을 수렴하여 이벤트 데이터 세트에 대해 고객 경로 분석에서 영향을 받는 배치의 모든 변경 사항을 동기화합니다. GDPR 삭제 요청의 영향을 받는 프로필 및 조회 데이터 세트는 각 삭제 요청 후 완전히 다시 수집됩니다. Data Lake에서 삭제 이벤트가 발생한 후 7일 이내에 삭제 요청이 실행되도록 보장할 수 있습니다.

## CCPA

CCPA(California Consumer Privacy Act)는 미국 캘리포니아 거주자를 위해 개인 정보 권한 및 소비자 보호를 개선합니다. 이 조례는 2020년 1월 1일부터 시행될 예정입니다.
CCPA는 개인 데이터가 판매되었거나 공개되었는지의 여부 및 그 대상을 확인하거나 개인 데이터 판매를 거절하기 위한 개인 데이터 액세스 및 삭제 권한과 같은 새로운 데이터 개인 정보 보호 권한을 캘리포니아 거주자에게 제공합니다.
CCPA의 예상에 따라 개인 정보 서비스는 개인 데이터 판매를 거부하도록 요청을 지원합니다.
