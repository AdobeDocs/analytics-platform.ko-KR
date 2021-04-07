---
title: Customer Journey Analytics에서 Google Analytics 보고 설정
description: null
translation-type: tm+mt
source-git-commit: 9bbc625aca9e0b8384b3e95d79fd695fda863f0b
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---


# Customer Journey Analytics에서 Google Analytics 보고 설정

Google 클라우드 스토리지 커넥터 설정,

Google 태그 관리자 구성

BigQuery 내보내기 스키마(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

1. 큰 쿼리에서 GA 세션을 이벤트로 변환
1. Google Analytics 이벤트를 Google 클라우드 스토리지로 내보내기
1. GCS 이벤트를 Adobe Experience Platform으로 가져오고 XDM 스키마에 매핑

## 전제 조건

* Adobe Experience Platform 액세스
* 유니버설 Google Analytics(Google Analytics 360 버전) 또는 Google Analytics 4(무료 버전 또는 Google Analytics 360 버전) 액세스
* Customer Journey Analytics 액세스

## Adobe Experience Platform에 Google Analytics 데이터 연결

Google Analytics 데이터를 Adobe Experience Platform으로 가져오는 방법은 사용 중인 Google Analytics 버전에 따라 달라집니다.

| 다음 항목을 사용하는 경우 | 이 라이선스도 필요합니다... | 그리고 이렇게... |
| --- | --- | --- |
| **범용 Google Analytics** | Google Analytics 360 | 아래의 지침 1 - x 단계를 수행합니다. |
| **Google Analytics 4** | 무료 GA 버전 또는 Google Analytics 360 | 아래 지침에 x단계가 필요하지 않습니다. |

다음 지침은 범용 Google Analytics을 기준으로 합니다.

1. Google Analytics 데이터를 BigQuery 및
[다음 지침](https://support.google.com/analytics/answer/3416092?hl=en)을 참조하십시오.
1. (Universal Analytics 고객만 해당) Google Analytics 세션을 BigQuery의 이벤트로 변환합니다.
[다음 지침](https://support.google.com/analytics/answer/3437618?hl=en)을 참조하십시오.
1. Google Analytics 이벤트를 Google 클라우드 스토리지로 내보냅니다.
[다음 지침](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)을 참조하십시오.
