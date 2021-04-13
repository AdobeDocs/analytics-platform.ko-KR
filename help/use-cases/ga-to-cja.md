---
title: Customer Journey Analytics에서 Google Analytics 보고 설정
description: null
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 49b49f24dbc68b1d9e843e0f4522123e6792a438
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Customer Journey Analytics에서 Google Analytics 보고 설정

이 사용 사례에서는 Google Analytics 데이터를 Adobe Experience Platform으로 가져온 다음

## 전제 조건

* Adobe Experience Platform 액세스
* 유니버설 Google Analytics(Google Analytics 360 버전) 또는 Google Analytics 4(무료 버전 또는 Google Analytics 360 버전) 액세스
* Customer Journey Analytics 액세스

## 1. Google Analytics 데이터를 Adobe Experience Platform에 연결

Google Analytics 데이터를 Adobe Experience Platform으로 가져오는 방법은 사용 중인 Google Analytics 버전에 따라 달라집니다.

| 다음 항목을 사용하는 경우 | 이 라이선스도 필요합니다... | 그리고 이렇게... |
| --- | --- | --- |
| **범용 Google Analytics** | Google Analytics 360 | 아래 지침 중 1 - 5단계를 수행합니다. |
| **Google Analytics 4** | 무료 GA 버전 또는 Google Analytics 360 | 아래 지침 중 2 - 5단계를 수행합니다. 1단계가 필요하지 않습니다. |

다음 지침은 범용 Google Analytics을 기준으로 합니다.

1. 일부 데이터를 변형할 수 있도록 Google Analytics 데이터를 BigQuery에 연결합니다.
[다음 지침](https://support.google.com/analytics/answer/3416092?hl=en)을 참조하십시오.

1. (Universal Analytics 고객만 해당) Google Analytics 세션을 BigQuery의 이벤트로 변환합니다.
이렇게 하면 데이터가 Adobe Experience Platform과 호환됩니다. [다음 지침](https://support.google.com/analytics/answer/3437618?hl=en)을 참조하십시오.

   세부 정보:BigQuery에서 GA 데이터는 표로 나타납니다.

   ![](assets/ga-bigquery.png)
유니버설 분석 데이터를 경험 플랫폼 호환 형식으로 변환하려면 SQL 쿼리를 만들어야 합니다. 다음 지침을 보려면 이 비디오를 보십시오.

   >[!VIDEO](https://video.tv.adobe.com/v/332634)

1. Google Analytics 이벤트를 JSON 형식으로 Google 클라우드 스토리지에 내보내고 버킷에 저장합니다.
[다음 지침](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)을 참조하십시오.

1. Google 클라우드 스토리지의 데이터를 Experience Platform으로 가져옵니다.
다음 지침을 보려면 이 비디오를 보십시오.

   >[!VIDEO](https://video.tv.adobe.com/v/332641)

1. GCS 이벤트를 Adobe Experience Platform으로 가져오고 XDM 스키마에 매핑

BigQuery 내보내기 스키마(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
