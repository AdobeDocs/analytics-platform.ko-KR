---
title: Experience Platform 쿼리 서비스(Data Distiller) 및 데이터 세트 내보내기
description: 쿼리 서비스(Data Distiller) 및 데이터 세트 내보내기를 사용하여 데이터를 내보내는 방법에 대해 설명합니다.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '2475'
ht-degree: 3%

---

# 쿼리 서비스(데이터 Distiller) 및 데이터 세트 내보내기

이 문서에서는 Experience Platform 쿼리 서비스(데이터 Distiller)와 데이터 세트 내보내기의 조합을 사용하여 다음을 구현하는 방법에 대해 설명합니다 [데이터 내보내기 사용 사례](overview.md):

- 데이터 유효성 검사
- Data Lake, BI 도구 Data Warehouse
- 인공 지능 및 머신 러닝을 위한 준비


Adobe Analytics은 다음을 사용하여 이러한 사용 사례를 구현할 수 있습니다 [데이터 피드](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) 기능. 데이터 피드는 Adobe Analytics에서 원시 데이터를 가져오는 강력한 방법입니다. 이 문서에서는 위에서 언급한 사용 사례를 구현할 수 있도록 Experience Platform에서 유사한 유형의 원시 데이터를 가져오는 방법에 대해 설명합니다. 이 문서에 설명된 적용 가능한 기능을 Adobe Analytics 데이터 피드와 비교하여 데이터 및 프로세스의 차이를 명확히 합니다.

## 소개

쿼리 서비스(데이터 Distiller)를 사용하여 데이터 내보내기 및 데이터 세트 내보내기는 다음과 같이 구성됩니다.

- 정의 **예약된 쿼리** 데이터 피드에 대한 데이터를 출력 데이터 세트로 생성합니다 ![출력 데이터 세트](../assets/output-dataset.svg), 사용 **쿼리 서비스**.
- 정의 **예약된 데이터 세트 내보내기** 를 사용하여 출력 데이터 세트를 클라우드 스토리지 대상으로 내보냅니다. **데이터 세트 내보내기**.

![데이터 피드](../assets/queryservice-export-datasets.svg)


## 사전 요구 사항

이 사용 사례에서 설명하는 기능을 사용하기 전에 다음 요구 사항을 모두 충족하는지 확인하십시오.

- Experience Platform의 데이터 레이크에 데이터를 수집하는 작업 구현입니다.
- 데이터 Distiller 추가 기능에 액세스하여 일괄 쿼리를 실행할 권한이 있습니다. 다음을 참조하십시오 [쿼리 서비스 패키징](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging) 추가 정보.
- Real-Time CDP Prime 또는 Ultimate 패키지, Adobe Journey Optimizer 또는 Customer Journey Analytics을 구입한 경우 사용할 수 있는 데이터 세트 내보내기 기능에 액세스합니다. 다음을 참조하십시오 [클라우드 스토리지 대상으로 데이터 세트 내보내기](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) 추가 정보.
- 데이터 피드의 원시 데이터를 내보낼 수 있는 하나 이상의 구성된 대상(예: Amazon S3, Google 클라우드 스토리지).


## 쿼리 서비스

Experience Platform 쿼리 서비스를 사용하면 Experience Platform 데이터 레이크의 데이터 세트를 데이터베이스 테이블처럼 쿼리하고 조인할 수 있습니다. 그런 다음 보고 또는 내보내기에 추가로 사용하기 위해 결과를 새 데이터 세트로 캡처할 수 있습니다.

쿼리 서비스를 사용할 수 있습니다 [사용자 인터페이스](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview), a [PostgresQL 프로토콜을 통해 연결된 클라이언트](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview), 또는 [RESTful API](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) 데이터 피드에 대한 데이터를 수집하는 쿼리를 만들고 예약합니다.

### 쿼리 만들기

SELECT 문용 표준 ANSI SQL의 모든 기능과 기타 제한된 명령을 사용하여 데이터 피드에 대한 데이터를 생성하는 쿼리를 만들고 실행할 수 있습니다. 다음을 참조하십시오 [SQL 구문](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax) 추가 정보. 이 SQL 구문 이상의 Adobe은

- 사전 빌드됨 [Adobe 정의 함수 (ADF)](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) Experience Platform 데이터 레이크에 저장된 이벤트 데이터에 대한 일반적인 비즈니스 관련 작업을 수행하는 데 도움이 됩니다. [세션화](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing) 및 [속성](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview),
- 여러 기본 제공 [Spark SQL 함수](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions),
- [metadata PostgreSQL 명령](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata),
- [준비된 진술](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements).

#### 데이터 피드 열

쿼리에 사용할 수 있는 XDM 필드는 데이터 세트가 기반으로 삼는 스키마 정의에 따라 다릅니다. 데이터 세트의 기본 스키마를 이해해야 합니다. 자세한 내용은 다음을 참조하십시오. [데이터 세트 UI 안내서](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide).

데이터 피드 열과 XDM 필드 간의 매핑을 정의하는 데 도움이 필요하면 를 참조하십시오. [Analytics 필드 매핑](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics). 다음 항목도 참조하십시오. [스키마 UI 개요](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields) 스키마, 클래스, 필드 그룹 및 데이터 형식을 포함하여 XDM 리소스를 관리하는 방법에 대한 자세한 내용을 알아봅니다.

예를 들어 를 사용하려는 경우 *페이지 이름* 데이터 피드의 일부로:

- Adobe Analytics 데이터 피드의 UI에서 **[!UICONTROL pagename]** 를 데이터 피드 정의에 추가할 열로 지정합니다.
- 쿼리 서비스에서 다음을 포함합니다. `web.webPageDetails.name` 다음에서 `sample_event_dataset_for_website_global_v1_1` 데이터 세트 (기반) **웹 사이트에 대한 샘플 이벤트 스키마(전역 v1.1)** 경험 이벤트 스키마)를 포함할 수 있습니다. 다음을 참조하십시오. [웹 세부 정보 스키마 필드 그룹](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details) 추가 정보.


#### ID

Experience Platform에서 다양한 ID를 사용할 수 있습니다. 쿼리를 만들 때 ID를 올바르게 쿼리하고 있는지 확인하십시오.


종종 별도의 필드 그룹에서 ID를 찾습니다. 구현 ECID에서 (`ecid`)은 를 사용하여 필드 그룹의 일부로 정의할 수 있습니다. `core` 객체, 그 자체가 `identification` 객체(예: `_sampleorg.identification.core.ecid`). ECID는 스키마에서 다르게 구성될 수 있습니다.

또는 다음을 사용할 수 있습니다 `identityMap` ID를 쿼리합니다. 다음 `identityMap` 은(는) 유형입니다. `Map` 및 를 사용합니다. [중첩된 데이터 구조](#nested-data-structure).

다음을 참조하십시오 [UI에서 ID 필드 정의](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) Experience Platform에서 id 필드를 정의하는 방법에 대한 자세한 정보.

을(를) 참조하십시오 [Analytics 데이터의 기본 식별자](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data) Analytics 소스 커넥터를 사용할 때 Adobe Analytics ID가 Experience Platform ID에 매핑되는 방식을 이해합니다. 이 매핑은 Analytics 소스 커넥터를 사용하지 않는 경우에도 ID를 설정하는 데 지침으로 사용될 수 있습니다.


#### 히트 수준 데이터 및 식별

구현에 따라, 전통적으로 Adobe Analytics에서 수집된 히트 수준 데이터는 이제 Experience Platform에서 타임스탬프가 지정된 이벤트 데이터로 저장됩니다. 다음 표는에서 추출됩니다. [Analytics 필드 매핑](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields) 및 에서는 히트 수준별 Adobe Analytics 데이터 피드 열을 쿼리의 해당 XDM 필드와 매핑하는 방법에 대한 예를 보여 줍니다. 이 표에서는 XDM 필드를 사용하여 히트, 방문 및 방문자를 식별하는 방법의 예도 보여줍니다.

| 데이터 피드 열 | XDM 필드 | 유형 | 설명 |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | 문자열 | 히트를 식별하는 고유 식별자입니다. |
| `hitid_low` | `_id` | 문자열 | 과 함께 사용됨 `hitid_high` 히트를 고유하게 식별합니다. |
| `hitid_high` | `_id` | 문자열 | 과 함께 사용됨 `hitid_high` 히트를 고유하게 식별합니다. |
| `hit_time_gmt` | `receivedTimestamp` | 문자열 | UNIX® 시간을 기반으로 한 히트의 타임스탬프입니다. |
| `cust_hit_time_gmt` | `timestamp` | 문자열 | 이 타임스탬프는 타임스탬프가 활성화된 데이터 세트에서만 사용됩니다. 이 타임스탬프는 UNIX® 시간을 기반으로 히트와 함께 전송됩니다. |
| `visid_high` + `visid_low` | `identityMap` | 오브젝트 | 방문에 대한 고유 식별자. |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | 문자열 | 방문에 대한 고유 식별자. |
| `visid_high` | `endUserIDs._experience.aaid.primary` | 부울 | 과 함께 사용됨 `visid_low` 방문을 고유하게 식별합니다. |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | 문자열 | 과 함께 사용됨 `visid_low` 방문을 고유하게 식별합니다. |
| `visid_low` | `identityMap` | 오브젝트 | 과 함께 사용됨 `visid_high` 방문을 고유하게 식별합니다. |
| `cust_visid` | `identityMap` | 오브젝트 | 고객 방문자 ID입니다. |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | 오브젝트 | 고객 방문자 ID입니다. |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | 부울 | 고객 방문자 ID 네임스페이스 코드. |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | 문자열 | 과 함께 사용됨 `visid_low` 고객 방문자 id를 고유하게 식별합니다. |
| `geo\_*` | `placeContext.geo.* ` | 문자열, 숫자 | 국가, 지역, 도시 등 지리적 위치 데이터 |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, ..., `_experience.analytics.event901_1000.*` | 문자열 | 히트에서 트리거된 표준 상거래 및 사용자 지정 이벤트. |
| `page_event` | `web.webInteraction.type` | 문자열 | 이미지 요청(표준 히트, 다운로드 링크, 종료 링크 또는 클릭한 사용자 지정 링크)에서 전송된 히트 유형입니다. |
| `page_event` | `web.webInteraction.linkClicks.value` | 숫자 | 이미지 요청(표준 히트, 다운로드 링크, 종료 링크 또는 클릭한 사용자 지정 링크)에서 전송된 히트 유형입니다. |
| `page_event_var_1` | `web.webInteraction.URL` | 문자열 | 링크 추적 이미지 요청에만 사용되는 변수입니다. 이 변수에는 클릭한 다운로드 링크, 종료 링크 또는 사용자 지정 링크의 URL이 포함됩니다. |
| `page_event_var_2` | `web.webInteraction.name` | 문자열 | 링크 추적 이미지 요청에만 사용되는 변수입니다. 지정된 경우 링크의 사용자 지정 이름이 나열됩니다. |
| `paid_search` | `search.isPaid` | 부울 | 히트가 유료 검색 감지와 일치하는 경우 설정되는 플래그입니다. |
| `ref_type` | `web.webReferrertype` | 문자열 | 히트에 대한 참조 유형을 나타내는 숫자 ID입니다. |

#### 게시물 열

Adobe Analytics 데이터 피드는 `post_` 접두사 : 처리 후 데이터가 포함된 열입니다. 자세한 내용은 [데이터 피드 FAQ](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post)를 참조하십시오.

Experience Platform Edge Network(Web SDK, Mobile SDK, Server API)을 통해 데이터 세트에 수집된 데이터에는 `post_` 필드. 그 결과, `post_` 접두사 및 *비*-`post_` 접두사가 있는 데이터 피드 열은 동일한 XDM 필드에 매핑됩니다. 예를 들어, 둘 다 `page_url` 및 `post_page_url` 데이터 피드 열이 동일한 열에 매핑 `web.webPageDetails.URL` XDM 필드.

다음을 참조하십시오 [Adobe Analytics 및 Customer Journey Analytics 간 데이터 처리 비교](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons) 데이터 처리의 차이점에 대한 개요입니다.

다음 `post_` 그러나 Experience Platform 데이터 레이크에 수집되는 데이터의 접두사 열 유형은 데이터 피드 사용 사례에서 성공적으로 사용되기 전에 고급 변형이 필요하지 않습니다. 쿼리에서 이러한 고급 변환을 수행하려면 다음을 사용해야 합니다. [Adobe 정의 함수](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) 세션, 속성 및 중복 제거용. 다음을 참조하십시오 [예](#examples) 이러한 기능을 사용하는 방법에 대해 설명합니다.

#### 조회

다른 데이터 세트에서 데이터를 조회하려면 표준 SQL 기능(`WHERE` 절, `INNER JOIN`, `OUTER JOIN`및 기타)를 참조하십시오.

#### 계산

필드(열)에 대한 계산을 수행하려면 표준 SQL 함수를 사용합니다(예: `COUNT(*)`) 또는 [수학 및 통계 연산자 및 함수](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math) spark SQL의 일부입니다. 또한, [창 함수](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions) 집계를 업데이트하고 순서가 지정된 하위 집합의 각 행에 대해 단일 항목을 반환할 수 있도록 지원을 제공합니다. 다음을 참조하십시오 [예](#examples) 이러한 기능을 사용하는 방법에 대해 설명합니다.

#### 중첩된 데이터 구조

데이터 세트가 기반으로 삼는 스키마에는 종종 중첩된 데이터 구조를 포함하여 복잡한 데이터 유형이 포함됩니다. 이전에 언급됨 `identityMap` 는 중첩된 데이터 구조의 예입니다. 의 예는 아래를 참조하십시오. `identityMap` 데이터.

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

다음을 사용할 수 있습니다. [`explode()` 또는 기타 배열 함수](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays) Spark SQL에서 중첩된 데이터 구조 내의 데이터로 이동합니다. 예를 들면 다음과 같습니다.

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

또는 점 표기법을 사용하여 개별 요소를 참조할 수 있습니다. 예:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

자세한 내용은 [Query Service에서 중첩된 데이터 구조로 작업](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/nested-data-structures)을 참조하십시오.


#### 예

쿼리:

- Experience Platform 데이터 레이크의 데이터 세트 데이터를 사용하는
- Adobe 정의 함수 및/또는 Spark SQL의 추가 기능을 탭하고 있습니다.
- 동등한 Adobe Analytics 데이터 피드와 유사한 결과를 제공하고,

다음을 참조하십시오.

- [포기한 찾아보기](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [속성 분석](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [보트 필터링](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- 및 기타 [쿼리 서비스 안내서에서 지원되는 사용 사례](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview).


### 쿼리 예약

쿼리를 예약하여 쿼리가 실행되고 결과가 원하는 간격으로 생성되도록 합니다.

#### 쿼리 편집기 사용

쿼리 편집기를 사용하여 쿼리를 예약할 수 있습니다. 쿼리를 예약할 때 출력 데이터 세트를 정의합니다. 다음을 참조하십시오 [쿼리 일정](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules) 추가 정보.


#### 쿼리 서비스 API 사용

또는 RESTful API를 사용하여 쿼리와 쿼리에 대한 일정을 정의할 수 있습니다. 다음을 참조하십시오. [쿼리 서비스 API 안내서](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started) 추가 정보.
출력 데이터 세트를 선택 사항의 일부로 정의해야 합니다. `ctasParameters` 쿼리를 만들 때 속성([쿼리 만들기](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) 또는 쿼리에 대한 일정을 만들 때([예약된 쿼리 만들기](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## 데이터 세트 내보내기

쿼리를 만들고 예약했으며 결과를 확인하면 원시 데이터 세트를 클라우드 스토리지 대상으로 내보낼 수 있습니다. 이 내보내기는 데이터 세트 내보내기 대상이라고 하는 Experience Platform 대상 용어에 있습니다. 다음을 참조하십시오 [클라우드 스토리지 대상으로 데이터 세트 내보내기](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) 개요를 참조하십시오.

지원되는 클라우드 스토리지 대상은 다음과 같습니다.

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [데이터 랜딩 영역](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google 클라우드 스토리지](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### EXPERIENCE PLATFORM UI

Experience Platform UI를 통해 출력 데이터 세트를 내보내고 내보내기를 예약할 수 있습니다. 이 섹션에서는 관련 단계에 대해 설명합니다.

#### 대상 선택

출력 데이터 세트를 내보낼 클라우드 스토리지 대상을 결정한 경우 [대상 선택](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). 기본 클라우드 스토리지에 대한 대상을 아직 구성하지 않은 경우 다음을 수행해야 합니다 [새 대상 연결 만들기](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

대상을 구성하는 과정의 일부로

- 파일 유형(JSON 또는 Parquet)을 정의하고
- 결과 파일의 압축 여부 및
- 매니페스트 파일을 포함해야 하는지 여부를 나타냅니다.


#### 데이터세트 선택

대상을 선택한 경우 다음에서 **[!UICONTROL 데이터 세트 선택]** 단계 데이터 세트 목록에서 출력 데이터 세트를 선택해야 합니다. 예약된 쿼리를 여러 개 만들었고 출력 데이터 세트를 동일한 클라우드 스토리지 대상으로 보내려는 경우 해당 출력 데이터 세트를 선택할 수 있습니다. 다음을 참조하십시오 [데이터 세트 선택](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) 추가 정보.

#### 데이터 세트 내보내기 예약

마지막으로, 데이터 세트 내보내기를 **[!UICONTROL 예약]** 단계. 이 단계에서는 일정 및 출력 데이터 세트 내보내기가 증분적이어야 하는지 여부를 정의할 수 있습니다. 다음을 참조하십시오 [데이터 세트 내보내기 예약](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) 추가 정보.


#### 최종 단계

[리뷰](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) 선택한 후 올바른 경우 출력 데이터 세트를 클라우드 스토리지 대상으로 내보내기를 시작합니다.

다음을 수행해야 합니다. [확인](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) 성공적인 데이터 내보내기. 데이터 세트를 내보낼 때 Experience Platform이 하나 또는 여러 개의 데이터 세트를 만듭니다 `.json` 또는 `.parquet` 대상에 정의된 저장소 위치의 파일입니다. 설정한 내보내기 일정에 따라 새 파일이 저장소 위치에 저장됩니다. Experience Platform은 선택한 대상의 일부로 지정한 저장소 위치에 내보낸 파일을 저장하는 폴더 구조를 만듭니다. 내보내기 시간마다 패턴을 따라 새 폴더가 만들어집니다. `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. 기본 파일 이름은 임의로 생성되며 내보낸 파일 이름이 고유한지 확인합니다.

### 플로우 서비스 API

또는 API를 사용하여 출력 데이터 세트를 내보내고 내보내기를 예약할 수 있습니다. 관련된 단계는에 설명되어 있습니다. [흐름 서비스 API를 사용하여 데이터 세트 내보내기](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### 시작

데이터 세트를 내보내려면 [필수 권한](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). 또한 출력 데이터 세트를 전송할 대상 이 데이터 세트 내보내기를 지원하는지 확인하십시오. 그러면 다음을 수행해야 합니다. [필수 및 선택적 헤더에 대한 값을 수집합니다.](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) API 호출에서 사용하는 쿠키입니다. 또한 다음을 수행해야 합니다 [대상의 연결 사양 및 흐름 사양 ID 식별](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) 데이터 세트를으로 내보내려고 합니다.

#### 적격 데이터 세트 검색

다음을 수행할 수 있습니다. [적격 데이터 세트 목록 검색](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) 를 사용하여 출력 데이터 세트가 해당 목록에 속하는지 여부를 내보내고 확인합니다. [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### 소스 연결 만들기

다음: [소스 연결 만들기](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) 클라우드 스토리지 대상으로 내보낼 출력 데이터 세트의 경우 고유 ID를 사용합니다. 다음을 사용합니다. [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### 대상에 인증(기본 연결 만들기)

이제 다음을 수행해야 합니다. [기본 연결 만들기](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) 을(를) 사용하여 자격 증명을 인증하고 클라우드 스토리지 대상에 안전하게 저장하려면 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### 내보내기 매개 변수 제공

다음으로, 다음을 수행해야 합니다. [내보내기 매개 변수를 저장하는 추가 target 연결 만들기](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) 를 사용하여 출력 데이터 세트에 대해 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. 이러한 내보내기 매개 변수에는 위치, 파일 형식, 압축 등이 포함됩니다.

#### 데이터 흐름 설정

마지막으로, [데이터 흐름 설정](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) 를 사용하여 출력 데이터 세트를 클라우드 스토리지 대상으로 내보냅니다. [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. 이 단계에서는 다음을 사용하여 내보내기 일정을 정의할 수 있습니다. `scheduleParams` 매개 변수.

#### 데이터 흐름 유효성 검사

종료 [데이터 흐름의 성공적인 실행 확인](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), 사용 [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) 데이터 흐름 ID를 쿼리 매개 변수로 지정하는 API입니다. 이 데이터 흐름 ID는 데이터 흐름을 설정할 때 반환되는 식별자입니다.

[확인](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) 성공적인 데이터 내보내기. 데이터 세트를 내보낼 때 Experience Platform이 하나 또는 여러 개의 데이터 세트를 만듭니다 `.json` 또는 `.parquet` 대상에 정의된 저장소 위치의 파일입니다. 설정한 내보내기 일정에 따라 새 파일이 저장소 위치에 저장됩니다. Experience Platform은 선택한 대상의 일부로 지정한 저장소 위치에 내보낸 파일을 저장하는 폴더 구조를 만듭니다. 내보내기 시간마다 패턴을 따라 새 폴더가 만들어집니다. `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. 기본 파일 이름은 임의로 생성되며 내보낸 파일 이름이 고유한지 확인합니다.

## 결론

즉, Adobe Analytics 데이터 피드 기능을 에뮬레이션한다는 것은 쿼리 서비스를 사용하여 예약된 쿼리를 설정하고 이러한 쿼리의 결과를 예약된 데이터 세트 내보내기에서 사용함을 의미합니다.

>[!IMPORTANT]
>
>이 사용 사례에는 두 개의 스케줄러가 포함됩니다. 에뮬레이트된 데이터 피드 기능이 적절히 작동하도록 하려면 쿼리 서비스 및 데이터 내보내기에 구성된 일정이 간섭되지 않도록 하십시오.
