---
title: Customer Journey Analytics(CJA)에서 분석을 위해 Adobe Experience Platform으로 Google Analytics 데이터를 가져오는 방법
description: 'Customer Journey Analytics(CJA)를 사용하여 Google Analytics 및 firebase 데이터를 Adobe Experience Platform에 인제스트하는 방법에 대해 설명합니다. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 793b2ce4ec8a487f6c4290fe2eff00879fcca13d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 2%

---


# Adobe Experience Platform에 Google Analytics 데이터 인제스트

이 사용 사례에서는 Google Analytics 데이터를 데이터 집합으로 Adobe Experience Platform에 인제스트하는 방법에 중점을 둡니다. (이것은 내역 데이터와 라이브 데이터 모두에 적용됩니다.) 한 번 작업을 완료하면 두 데이터 세트를 결합하여 사용자 여정의 크로스 디바이스 보기를 수행할 수 있습니다.

Experience Platform의 데이터 세트는 다음 두 가지 항목으로 구성됩니다.스키마 및 데이터 세트에 있는 실제 레코드. 스키마(이것을 경험 데이터 모델 또는 XDM이라고 함)는 데이터 세트 열과 비슷하며 데이터 자체를 설명하는 블루프린트 또는 규칙과 같습니다. 플랫폼 내에서 Adobe은 다음 2가지 유형의 스키마를 제공합니다.

* Google Analytics 데이터를 자동으로 매핑할 수 있는 기본 스키마(경험 이벤트 스키마라고 함)
* Google Analytics 데이터를 만들고 쉽게 매핑할 수 있는 사용자 정의 스키마

Adobe 데이터 모델의 가장 강력한 측면 중 하나는 모든 고객 상호 작용 데이터를 하나의 공통 스키마로 표준화할 수 있다는 것입니다. 이를 통해 CJA에서 데이터를 결합하는 것이 훨씬 수월해졌습니다.

## 전제 조건

이러한 작업을 수행하려면 다음 액세스 및 권한이 필요합니다.

* Adobe Experience Platform 액세스
* 유니버설 Google Analytics(Google Analytics 360 버전) 또는 Google Analytics 4(무료 버전 또는 Google Analytics 360 버전) 액세스
* Customer Journey Analytics 및 해당 [관리 권한](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#admin-access-permissions)에 대한 액세스.

Google Analytics 데이터를 Adobe Experience Platform으로 가져오는 방법은 사용 중인 Google Analytics 버전에 따라 달라집니다.

| 다음 항목을 사용하는 경우 | 이 라이선스도 필요합니다... | 그리고 이렇게... |
| --- | --- | --- |
| **범용 Google Analytics** | Google Analytics 360 | 아래 지침 중 1 - 5단계를 수행합니다. |
| **Google Analytics 4** | 무료 GA 버전 또는 Google Analytics 360 | 아래 지침의 1단계와 3-5단계를 수행합니다. 2단계를 수행하지 않아도 됩니다. |

## 1. Google Analytics 데이터를 BigQuery에 연결

다음 지침은 범용 Google Analytics을 기반으로 합니다.

[다음 지침](https://support.google.com/analytics/answer/3416092?hl=en)을 참조하십시오.

## 2. Google Analytics 세션을 BigQuery의 이벤트로 변환합니다.

>[!IMPORTANT]
>
>이 단계는 Universal Analytics 고객에게만 적용됩니다

GA 데이터는 개별 이벤트가 아닌 사용자의 세션으로 데이터의 각 레코드를 저장합니다. 데이터를 변환하면 데이터가 Adobe Experience Platform과 호환됩니다.

[다음 지침](https://support.google.com/analytics/answer/3437618?hl=en)을 참조하십시오.

유니버설 분석 데이터를 경험 플랫폼 호환 형식으로 변환하려면 SQL 쿼리를 만들어야 합니다. 다음 지침을 보려면 이 비디오를 보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3. Google Analytics 이벤트를 JSON 형식으로 Google 클라우드 스토리지에 내보내고 버킷에 저장합니다.

[다음 지침](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)을 참조하십시오.

## 4. Google 클라우드 스토리지의 데이터를 Experience Platform으로 가져옵니다.

다음 지침을 보려면 이 비디오를 보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5. GCS 이벤트를 Adobe Experience Platform으로 가져오고 XDM 스키마에 매핑

BigQuery 내보내기 스키마(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
