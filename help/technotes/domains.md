---
title: Customer Journey Analytics에서 사용하는 도메인
description: 조직 방화벽이 Adobe에서 생성하는 IP 주소를 차단하는 경우 이 목록을 사용하여 방화벽 설정을 업데이트하십시오.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
autotag-review: '2026-05-19T09:27:11.172Z'
TQID: 'https://experienceleague.adobe.com/y3FgZsfqtozN8IaJlBvmfybUIH3s7fiiw2Rc4iNLyGI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
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

위의 도메인 외에도 CX Enterprise는 데이터 수집 및 보고서 내보내기를 위해 여러 도메인을 사용합니다. 이 도메인 목록은 [CX Enterprise에서 사용하는 도메인](https://experienceleague.adobe.com/ko/docs/core-services/interface/data-collection/domains)을 참조하십시오.

>[!MORELIKETHIS]
>
>[Customer Journey Analytics에서 사용하는 IP 주소](ip-addresses.md)
>
>[CX Enterprise에서 사용하는 도메인](https://experienceleague.adobe.com/ko/docs/core-services/interface/data-collection/domains)
