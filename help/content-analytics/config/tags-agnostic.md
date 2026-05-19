---
title: Content Analytics JavaScript 라이브러리
description: Experience Platform 데이터 수집 태그를 사용하지 않고 Content Analytics을 구성하고 대신 Content Analytics JavaScript 라이브러리를 사용하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
autotag-review: '2026-05-19T06:56:34.440Z'
TQID: 'https://experienceleague.adobe.com/GUYf0ZoTlAkoIIPWzfZTm0-eMvBjN8ieYSu6goHu3GA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 484
ht-degree: 4%

---


# Content Analytics JavaScript 라이브러리

Adobe Content Analytics JavaScript 라이브러리를 사용하면 Experience Platform Edge Network을 통해 Adobe Experience Platform에 컨텐츠 데이터를 전송하여 웹 사이트에서 컨텐츠 관련 이벤트를 추적할 수 있습니다. Adobe Experience Platform 태그 없이 Content Analytics을 구현하려면 이 라이브러리를 사용하십시오.

>[!NOTE]
>
>이 문서는 웹 채널용 Content Analytics에 적용됩니다.


>[!PREREQUISITES]
>
>* `initializeContentLibrary`을(를) 호출하기 전에 페이지에서 Adobe Experience Platform Web SDK(Alloy)를 초기화해야 합니다.
>* Content Analytics 구성 마법사를 완료하여 Content Analytics 구성에 대한 사전 요구 사항을 설정하는 데 필요한 모든 단계를 안내합니다.
>* 안내식 구성이 완료되면 JavaScript 설정을 사용할 수 있습니다.


## 설치

다음 두 가지 방법으로 라이브러리를 설치할 수 있습니다.

### npm 패키지

`npm`을(를) 사용하여 라이브러리를 설치합니다.

1. 명령줄에서 다음을 사용합니다.

   ```bash
   npm install @adobe/content-analytics
   ```

1. 라이브러리를 가져옵니다:

   ```JavaScript
   import initializeContentLibrary from "@adobe/content-analytics";
   ```

### 스크립트 태그(CDN)

CDN에서 직접 라이브러리를 로드합니다.

1. [웹 SDK JavaScript 라이브러리](https://experienceleague.adobe.com/ko/docs/experience-platform/collection/js/install/library)를 초기화하고 Content Analytics 번들을 로드합니다.

   ```html
   <!-- 1. Load and configure Alloy first -->
   <script src="https://cdn1.adoberesources.net/alloy/2.x.x/alloy.min.js"></script>
   <script>
   alloy("configure", {
       datastreamId: "YOUR_DATASTREAM_ID",
       orgId: "YOUR_ORG_ID@AdobeOrg",
   });
   </script>
   
   <!-- 2. Load Content Analytics -->
   <script src="https://cdn1.adoberesources.net/content-analytics/1.x.x/content-analytics.min.js"></script>
   <script>
   window.contentAnalytics({
       datastreamId: "YOUR_DATASTREAM_ID",
   });
   </script>
   ```

   장소
   * `alloy/2.x.x`은(는) [웹 SDK JavaScript 라이브러리](https://experienceleague.adobe.com/ko/docs/experience-platform/collection/js/install/library)를 사용할 버전을 참조합니다.
   * `content-analytics/1.x.x`은(는) Content Analytics SDK 라이브러리를 사용할 버전을 참조합니다.

2. 독립 실행형 빌드가 `window.contentAnalytics`을(를) 초기화 함수로 표시합니다.


## 데이터 스트림 구성

`datastreamId` 옵션은 필수이며, 활성화된 Content Analytics 경험 이벤트 데이터 세트로 Experience Platform 서비스가 구성된 데이터 스트림을 참조해야 합니다. 데이터 스트림과 연결된 샌드박스가 다른 Content Analytics 설정과 아직 연결되어 있지 않은지 확인합니다.

환경별로 별도의 데이터 스트림 ID를 제공할 수 있습니다.

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## 경험 캡처 및 정의

경험 추적을 활성화하고 웹 사이트에서 경험이 식별되는 방법을 제어합니다. 경험은 **도메인 정규식**&#x200B;을(를) 일치하는 페이지 내에서 한 경험과 다른 경험을 구별하는 선택적 **쿼리 매개 변수**&#x200B;와 결합하여 정의됩니다.

| 옵션 | 유형 | 기본값 | 설명 |
|--------|------|---------|-------------|
| `includeExperiences` | 부울 | `false` | 페이지/경험 보기 추적 활성화 |
| `experienceConfigurations` | 배열 | - | 도메인 정규 표현식 및 쿼리 매개 변수로 경험 정의 |

`experienceConfigurations`의 각 항목은 다음을 허용합니다.

| 속성 | 유형 | 설명 |
|----------|------|-------------|
| `regEx` | 문자열 | 페이지 URL에 대해 일치하는 도메인 정규 표현식(예: `^(?!.*\b(store\|help\|admin)\b)`) |
| `queryParameters` | 배열 | 값이 일치하는 페이지의 경험을 구분하는 쿼리 매개 변수 이름(예: `["outdoors", "patio", "kitchen"]`) |

### 예

도메인 정규 표현식 및 쿼리 매개 변수를 사용하여 경험 추적을 활성화하는 방법에 대한 예는 아래를 참조하십시오.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  includeExperiences: true,
  experienceConfigurations: [
    {
      regEx: "^https://www\\.example\\.com/products",
      queryParameters: ["category", "collection"],
    },
    {
      regEx: "^https://www\\.example\\.com/blog",
      queryParameters: [],
    },
  ],
});
```

## 이벤트 필터링

정규 표현식을 사용하여 데이터 수집에 포함되는 페이지 URL 및 에셋 URL을 제어합니다. 아래 패턴 예제를 시작점으로 사용하여 배포 전에 regex 테스터로 패턴을 확인하십시오.

| 옵션 | 유형 | 기본값 | 설명 |
|--------|------|---------|-------------|
| `pageUrlQualifier` | 문자열(정규 표현식) | - | URL이 이 패턴과 일치하는 페이지만 추적 |
| `assetUrlQualifier` | 문자열(정규 표현식) | - | URL이 이 패턴과 일치하는 에셋만 추적 |
| `excludeURLsFromTracking` | 배열 | `[]` | 추적에서 제외할 URL 문자열 목록 |

### 예

Content Analytics에서 설명서 페이지를 제외하고 Content Analytics에 대한 제품 이미지만 고려하는 방법에 대한 예는 아래를 참조하십시오.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  pageUrlQualifier: "^(?!.*\\/documentation).*",
  assetUrlQualifier: ".*\\/products\\/.*\\.(?:jpg|png|webp)",
  excludeURLsFromTracking: [
    "https://www.example.com/internal",
    "https://www.example.com/staging",
  ],
});
```
