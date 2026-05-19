---
title: Customer Journey Analytics에서 사용하는 도메인
description: 조직 방화벽이 Adobe에서 생성하는 IP 주소를 차단하는 경우 이 목록을 사용하여 방화벽 설정을 업데이트하십시오.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
TQID: https://experienceleague.adobe.com/d-nNfumskelDKrgCPQpyoZIagJrGcniXyQgACaHh5tA
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 0145475e18cfbc3ae3a83e5e3838cdec02b57bda
workflow-type: tm+mt
source-wordcount: 163
ht-degree: 16%

---

# Customer Journey Analytics에서 사용하는 도메인

일부 방화벽 구성은 Customer Journey Analytics이 제품 인터페이스에 의존하는 도메인을 차단합니다. 이 도메인 목록을 사용하여 조직 내에서 제품 액세스를 허용하도록 조직의 네트워크 설정을 변경할 수 있습니다. Adobe에서는 최적의 경험을 위해 이러한 도메인을 조직의 방화벽을 통해 사용할 수 있도록 권장합니다.

| 기술 | 도메인 |
| --- | --- |
| Customer Journey Analytics 도메인 | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| ® Azure Blob 저장소 | `awaascicdprodva7.blob.core.windows.net` |
| ® AZURE CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## CX 엔터프라이즈 도메인

위의 도메인 외에도 CX Enterprise는 데이터 수집 및 보고서 내보내기를 위해 여러 도메인을 사용합니다. 이 도메인 목록은 [CX Enterprise에서 사용하는 도메인](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)을 참조하십시오.

>[!MORELIKETHIS]
>
>[Customer Journey Analytics에서 사용하는 IP 주소](ip-addresses.md)
>
>[CX Enterprise에서 사용하는 도메인](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)
