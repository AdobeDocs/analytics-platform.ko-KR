---
title: Experience Platform 쿼리 서비스(Data Distiller) 및 데이터 세트 내보내기
description: 쿼리 서비스(Data Distiller) 및 데이터 세트 내보내기를 사용하여 데이터를 내보내는 방법에 대해 설명합니다.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 14a90758-91eb-4610-8802-1edfdb8b9689
source-git-commit: 20ead546897ad517840f95a5ec4dcd7f830afe8c
workflow-type: tm+mt
source-wordcount: '2642'
ht-degree: 3%

---

# 쿼리 서비스(데이터 Distiller) 및 데이터 세트 내보내기

이 문서에서는 Experience Platform 쿼리 서비스(데이터 Distiller)와 데이터 세트 내보내기의 조합을 사용하여 다음 [데이터 내보내기 사용 사례](overview.md)를 구현하는 방법에 대해 간략히 설명합니다.

- 데이터 유효성 검사
- Data Lake, BI 도구의 Data Warehouse
- 인공 지능 및 머신 러닝을 위한 준비


Adobe Analytics은 [데이터 피드](https://experienceleague.adobe.com/ko/docs/analytics/export/analytics-data-feed/data-feed-overview) 기능을 사용하여 이러한 사용 사례를 구현할 수 있습니다. 데이터 피드는 Adobe Analytics에서 원시 데이터를 가져오는 강력한 방법입니다. 이 문서에서는 위에서 언급한 사용 사례를 구현할 수 있도록 Experience Platform에서 유사한 유형의 원시 데이터를 가져오는 방법에 대해 설명합니다. 이 문서에 설명된 적용 가능한 기능을 Adobe Analytics 데이터 피드와 비교하여 데이터 및 프로세스의 차이를 명확히 합니다.

## 소개

쿼리 서비스(데이터 Distiller)를 사용하여 데이터 내보내기 및 데이터 세트 내보내기는 다음과 같이 구성됩니다.

- **쿼리 서비스**&#x200B;를 사용하여 데이터 피드에 대한 데이터를 출력 데이터 세트 ![출력 데이터 세트](../assets/output-dataset.svg)(으)로 생성하는 **예약된 쿼리**&#x200B;를 정의합니다.
- **데이터 세트 내보내기**&#x200B;를 사용하여 출력 데이터 세트를 클라우드 저장소 대상으로 내보내는 **예약된 데이터 세트 내보내기**&#x200B;를 정의합니다.

![데이터 피드](../assets/queryservice-export-datasets.svg)


## 사전 요구 사항

이 사용 사례에서 설명하는 기능을 사용하기 전에 다음 요구 사항을 모두 충족하는지 확인하십시오.

- Experience Platform의 데이터 레이크로 데이터를 수집하는 작업 구현입니다.
- 데이터 Distiller 추가 기능에 액세스하여 일괄 쿼리를 실행할 권한이 있습니다. 자세한 내용은 [쿼리 서비스 패키징](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging)을 참조하십시오.
- Real-Time CDP Prime 또는 Ultimate 패키지, Adobe Journey Optimizer 또는 Customer Journey Analytics을 구입한 경우 사용할 수 있는 데이터 세트 내보내기 기능에 액세스합니다. 자세한 내용은 [클라우드 저장소 대상으로 데이터 세트 내보내기](https://experienceleague.adobe.com/ko/docs/experience-platform/destinations/ui/activate/export-datasets)를 참조하십시오.
- 데이터 피드의 원시 데이터를 내보낼 수 있는 하나 이상의 구성된 대상(예: Amazon S3, Google 클라우드 스토리지).


## 쿼리 서비스

Experience Platform 쿼리 서비스를 사용하면 Experience Platform 데이터 레이크의 데이터 세트를 데이터베이스 테이블처럼 쿼리하고 조인할 수 있습니다. 그런 다음 보고 또는 내보내기에 추가로 사용하기 위해 결과를 새 데이터 세트로 캡처할 수 있습니다.

쿼리 서비스 [사용자 인터페이스](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview), PostgresQL 프로토콜을 통해 연결된 [클라이언트](https://experienceleague.adobe.com/ko/docs/experience-platform/query/clients/overview) 또는 [RESTful API](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started)를 사용하여 데이터 피드에 대한 데이터를 수집하는 쿼리를 만들고 예약할 수 있습니다.

### 쿼리 만들기

SELECT 문용 표준 ANSI SQL의 모든 기능과 기타 제한된 명령을 사용하여 데이터 피드에 대한 데이터를 생성하는 쿼리를 만들고 실행할 수 있습니다. 자세한 내용은 [SQL 구문](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax)을 참조하십시오. 이 SQL 구문 외에도 Adobe은 다음을 지원합니다.

- [세션화](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions) 및 [속성](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing)에 대한 함수를 포함하여 Experience Platform 데이터 레이크에 저장된 이벤트 데이터에 대해 일반적인 비즈니스 관련 작업을 수행하는 데 도움이 되는 사전 빌드된 [Adobe 정의 함수(ADF)](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview),
- 여러 기본 제공 [Spark SQL 함수](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions),
- [메타데이터 PostgreSQL 명령](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata),
- [준비된 문](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements).

#### 데이터 피드 열

쿼리에 사용할 수 있는 XDM 필드는 데이터 세트가 기반으로 삼는 스키마 정의에 따라 다릅니다. 데이터 세트의 기본 스키마를 이해해야 합니다. 자세한 내용은 [데이터 세트 UI 안내서](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide)를 참조하십시오.

데이터 피드 열과 XDM 필드 간의 매핑을 정의하려면 [Analytics 필드 매핑](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)을 참조하세요. 스키마, 클래스, 필드 그룹 및 데이터 형식을 포함하여 XDM 리소스를 관리하는 방법에 대한 자세한 내용은 [스키마 UI 개요](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields)를 참조하십시오.

예를 들어 *페이지 이름*&#x200B;을(를) 데이터 피드의 일부로 사용하려는 경우:

- Adobe Analytics 데이터 피드의 UI에서 데이터 피드 정의에 추가할 열로 **[!UICONTROL pagename]**&#x200B;을(를) 선택합니다.
- Query Service에서는 `web.webPageDetails.name` 데이터 집합의 `sample_event_dataset_for_website_global_v1_1`을(를) 쿼리에 포함합니다(**웹 사이트에 대한 샘플 이벤트 스키마(전역 v1.1)** 경험 이벤트 스키마 기반). 자세한 내용은 [웹 세부 정보 스키마 필드 그룹](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details)을 참조하세요.


#### ID

Experience Platform에서는 다양한 ID를 사용할 수 있습니다. 쿼리를 만들 때 ID를 올바르게 쿼리하고 있는지 확인하십시오.


종종 별도의 필드 그룹에서 ID를 찾습니다. 구현 ECID(`ecid`)는 `core` 개체의 일부인 `identification` 개체가 있는 필드 그룹의 일부로 정의할 수 있습니다(예: `_sampleorg.identification.core.ecid`). ECID는 스키마에서 다르게 구성될 수 있습니다.

또는 `identityMap`을(를) 사용하여 ID를 쿼리할 수 있습니다. `identityMap`은(는) 형식이 `Map`이고 [중첩된 데이터 구조](#nested-data-structure)를 사용합니다.

Experience Platform에서 ID 필드를 정의하는 방법에 대한 자세한 내용은 [UI에서 ID 필드 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/ui/fields/identity)를 참조하십시오.

Analytics 소스 커넥터를 사용할 때 Adobe Analytics ID가 Experience Platform ID에 매핑되는 방식에 대한 이해는 Analytics 데이터의 [기본 식별자](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data)를 참조하십시오. 이 매핑은 Analytics 소스 커넥터를 사용하지 않는 경우에도 ID를 설정하는 데 지침으로 사용될 수 있습니다.


#### 히트 수준 데이터 및 식별

구현에 따라, 전통적으로 Adobe Analytics에서 수집된 히트 수준 데이터는 이제 Experience Platform에서 타임스탬프가 지정된 이벤트 데이터로 저장됩니다. 다음 테이블은 [Analytics 필드 매핑](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields)에서 추출되며 히트 수준별 Adobe Analytics 데이터 피드 열을 쿼리의 해당 XDM 필드와 매핑하는 방법에 대한 예제를 보여줍니다. 이 표에서는 XDM 필드를 사용하여 히트, 방문 및 방문자를 식별하는 방법의 예도 보여줍니다.

| 데이터 피드 열 | XDM 필드 | 유형 | 설명 |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | 문자열 | 히트를 식별하는 고유 식별자입니다. |
| `hitid_low` | `_id` | 문자열 | 히트를 고유하게 식별하기 위해 `hitid_high`과(와) 함께 사용됩니다. |
| `hitid_high` | `_id` | 문자열 | 히트를 고유하게 식별하기 위해 `hitid_high`과(와) 함께 사용됩니다. |
| `hit_time_gmt` | `receivedTimestamp` | 문자열 | UNIX® 시간을 기반으로 한 히트의 타임스탬프입니다. |
| `cust_hit_time_gmt` | `timestamp` | 문자열 | 이 타임스탬프는 타임스탬프가 활성화된 데이터 세트에서만 사용됩니다. 이 타임스탬프는 UNIX® 시간을 기반으로 히트와 함께 전송됩니다. |
| `visid_high` + `visid_low` | `identityMap` | 오브젝트 | 방문에 대한 고유 식별자. |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | 문자열 | 방문에 대한 고유 식별자. |
| `visid_high` | `endUserIDs._experience.aaid.primary` | 부울 | 방문을 고유하게 식별하기 위해 `visid_low`과(와) 함께 사용됩니다. |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | 문자열 | 방문을 고유하게 식별하기 위해 `visid_low`과(와) 함께 사용됩니다. |
| `visid_low` | `identityMap` | 오브젝트 | 방문을 고유하게 식별하기 위해 `visid_high`과(와) 함께 사용됩니다. |
| `cust_visid` | `identityMap` | 오브젝트 | 고객 방문자 ID입니다. |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | 오브젝트 | 고객 방문자 ID입니다. |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | 부울 | 고객 방문자 ID 네임스페이스 코드. |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | 문자열 | 고객 방문자 ID를 고유하게 식별하기 위해 `visid_low`과(와) 함께 사용됩니다. |
| `geo\_*` | `placeContext.geo.* ` | 문자열, 숫자 | 국가, 지역, 도시 등 지리적 위치 데이터 |
| `event_list` | `commerce.purchases`, `commerce.productViews`, `commerce.productListOpens`, `commerce.checkouts`, `commerce.productListAdds`, `commerce.productListRemovals`, `commerce.productListViews`, `_experience.analytics.event101to200.*`, ..., `_experience.analytics.event901_1000.*` | 문자열 | 히트에서 트리거된 표준 상거래 및 사용자 지정 이벤트. |
| `page_event` | `web.webInteraction.type` | 문자열 | 이미지 요청(표준 히트, 다운로드 링크, 종료 링크 또는 클릭한 사용자 지정 링크)에서 전송된 히트 유형입니다. |
| `page_event` | `web.webInteraction.linkClicks.value` | 숫자 | 이미지 요청(표준 히트, 다운로드 링크, 종료 링크 또는 클릭한 사용자 지정 링크)에서 전송된 히트 유형입니다. |
| `page_event_var_1` | `web.webInteraction.URL` | 문자열 | 링크 추적 이미지 요청에만 사용되는 변수입니다. 이 변수에는 클릭한 다운로드 링크, 종료 링크 또는 사용자 지정 링크의 URL이 포함됩니다. |
| `page_event_var_2` | `web.webInteraction.name` | 문자열 | 링크 추적 이미지 요청에만 사용되는 변수입니다. 지정된 경우 링크의 사용자 지정 이름이 나열됩니다. |
| `paid_search` | `search.isPaid` | 부울 | 히트가 유료 검색 감지와 일치하는 경우 설정되는 플래그입니다. |
| `ref_type` | `web.webReferrertype` | 문자열 | 히트에 대한 참조 유형을 나타내는 숫자 ID입니다. |

#### 게시물 열

Adobe Analytics 데이터 피드는 처리 후 데이터가 포함된 열인 `post_` 접두사가 있는 열 개념을 사용합니다. 자세한 내용은 [데이터 피드 FAQ](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post)를 참조하십시오.

Experience Platform Edge Network(웹 SDK, 모바일 SDK, 서버 API)를 통해 데이터 세트에 수집된 데이터에는 `post_` 필드에 대한 개념이 없습니다. 그 결과, 접두사가 `post_`인 데이터 피드 열과 접두사가 *non*-`post_`인 데이터 피드 열이 동일한 XDM 필드에 매핑됩니다. 예를 들어 `page_url`과(와) `post_page_url` 데이터 피드 열은 모두 동일한 `web.webPageDetails.URL` XDM 필드에 매핑됩니다.

데이터 처리의 차이점에 대한 개요는 [Adobe Analytics과 Customer Journey Analytics 간의 데이터 처리 비교](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons)를 참조하십시오.

그러나 Experience Platform 데이터 레이크에 수집되는 데이터의 `post_` 접두사 열 유형은 데이터 피드 사용 사례에서 성공적으로 사용되기 전에 고급 변환이 필요하지 않습니다. 쿼리에서 이러한 고급 변환을 수행하려면 세션화, 속성 및 중복 제거를 위해 [Adobe 정의 함수](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions)를 사용해야 합니다. 이러한 함수를 사용하는 방법에 대해서는 [예제](#examples)를 참조하십시오.

#### 조회

다른 데이터 세트에서 데이터를 조회하려면 표준 SQL 기능(`WHERE` 절, `INNER JOIN`, `OUTER JOIN` 등)을 사용합니다.

#### 계산

필드(열)에서 계산을 수행하려면 표준 SQL 함수(예: `COUNT(*)`)나 Spark SQL의 [수학 및 통계 연산자 및 함수](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math) 부분을 사용하십시오. 또한 [window 함수](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions)에서는 집계를 업데이트하고 정렬된 하위 집합의 각 행에 대해 단일 항목을 반환할 수 있습니다. 이러한 함수를 사용하는 방법에 대해서는 [예제](#examples)를 참조하십시오.

#### 중첩된 데이터 구조

데이터 세트가 기반으로 삼는 스키마에는 종종 중첩된 데이터 구조를 포함하여 복잡한 데이터 유형이 포함됩니다. 이전에 언급된 `identityMap`은(는) 중첩 데이터 구조의 예입니다. `identityMap` 데이터의 예는 아래를 참조하십시오.

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

Spark SQL의 [`explode()` 또는 기타 배열 함수](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays)을 사용하여 중첩된 데이터 구조 내의 데이터를 가져올 수 있습니다. 예를 들면 다음과 같습니다.

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

- [찾아보기 중단](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [속성 분석](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [보트 필터링](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- 및 쿼리 서비스 안내서에서 [지원되는 사용 사례](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview)를 참조하십시오.

다음은 세션 간에 속성을 올바르게 적용하는 예제이며, 이는 다음 방법을 보여줍니다.

- 지난 90일을 전환 확인으로 사용,
- 세션 및/또는 기여도 분석과 같은 창 함수 적용
- `ingest_time`을(를) 기준으로 출력을 제한합니다.

  +++ 세부 사항

  이렇게 하려면 다음을 수행해야 합니다.

   - 처리 상태 테이블 `checkpoint_log`을(를) 사용하여 현재 시간과 마지막 수집 시간을 추적합니다. 자세한 내용은 [이 안내서](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/incremental-load)를 참조하십시오.
   - `_acp_system_metadata.ingestTime`을(를) 사용할 수 있도록 시스템 열을 삭제하지 않도록 설정하십시오.
   - 가장 안쪽의 `SELECT`을(를) 사용하여 사용할 필드를 선택하고 세션 및/또는 속성 계산을 위해 이벤트를 전환 기간으로 제한합니다. 예를 들어 90일입니다.
   - 다음 수준 `SELECT`을(를) 사용하여 세션 및/또는 속성 창 함수와 기타 계산을 적용합니다.
   - 출력 테이블에서 `INSERT INTO`을(를) 사용하여 마지막 처리 시간 이후 도착한 이벤트로만 전환 확인을 제한합니다. `_acp_system_metadata.ingestTime `을(를) 처리 상태 테이블에 마지막으로 저장한 시간과 비교하여 필터링하여 이 작업을 수행합니다.

  **세션화 창 함수 예제**

  ```sql
  $$ BEGIN
     -- Disable dropping system columns
     set drop_system_columns=false; 
  
     -- Initialize variables
     SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
     -- Get the last processed batch ingestion time
     SET @from_batch_ingestion_time = SELECT coalesce(last_batch_ingestion_time, 'HEAD') 
        FROM checkpoint_log a 
        JOIN (
              SELECT MAX(process_timestamp) AS process_timestamp 
              FROM checkpoint_log
              WHERE process_name = 'data_feed' 
              AND process_status = 'SUCCESSFUL'
        ) b
        ON a.process_timestamp = b.process_timestamp;
  
     -- Get the last batch ingestion time
     SET @to_batch_ingestion_time = SELECT MAX(_acp_system_metadata.ingestTime) 
        FROM events_dataset;
  
     -- Sessionize the data and insert into data_feed.
     INSERT INTO data_feed
     SELECT *
     FROM (
        SELECT
              userIdentity,
              timestamp,
              SESS_TIMEOUT(timestamp, 60 * 30) OVER (
                 PARTITION BY userIdentity
                 ORDER BY timestamp
                 ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
              ) AS session_data,
              page_name,
              ingest_time
        FROM (
              SELECT
                 userIdentity,
                 timestamp,
                 web.webPageDetails.name AS page_name,
                 _acp_system_metadata.ingestTime AS ingest_time
              FROM events_dataset
              WHERE timestamp >= current_date - 90
        ) AS a
        ORDER BY userIdentity, timestamp ASC
     ) AS b
     WHERE b.ingest_time >= @from_batch_ingestion_time;
  
     -- Update the checkpoint_log table
     INSERT INTO checkpoint_log
     SELECT
        'data_feed' process_name,
        'SUCCESSFUL' process_status,
        cast(@to_batch_ingestion_time AS string) last_batch_ingestion_time,
        cast(@last_updated_timestamp AS TIMESTAMP) process_timestamp
  END
  $$;
  ```

  **속성 창 함수 예제**

  ```sql
  $$ BEGIN
   SET drop_system_columns=false;
  
  -- Initialize variables
   SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
  -- Get the last processed batch ingestion time 1718755872325
   SET @from_batch_ingestion_time =
       SELECT coalesce(last_snapshot_id, 'HEAD')
       FROM checkpoint_log a
       JOIN (
           SELECT MAX(process_timestamp) AS process_timestamp
           FROM checkpoint_log
           WHERE process_name = 'data_feed'
           AND process_status = 'SUCCESSFUL'
       ) b
       ON a.process_timestamp = b.process_timestamp;
  
   -- Get the last batch ingestion time 1718758687865
   SET @to_batch_ingestion_time =
       SELECT MAX(_acp_system_metadata.ingestTime)
       FROM demo_data_trey_mcintyre_midvalues;
  
   -- Sessionize the data and insert into new_sessionized_data
   INSERT INTO new_sessionized_data
   SELECT *
   FROM (
       SELECT
           _id,
           timestamp,
           struct(User_Identity,
           cast(SESS_TIMEOUT(timestamp, 60 * 30) OVER (
               PARTITION BY User_Identity
               ORDER BY timestamp
               ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
           ) as string) AS SessionData,
           to_timestamp(from_unixtime(ingest_time/1000, 'yyyy-MM-dd HH:mm:ss')) AS IngestTime,      
           PageName,
           first_url,
           first_channel_type
             ) as _demosystem5
       FROM (
           SELECT
               _id,
               ENDUSERIDS._EXPERIENCE.MCID.ID as User_Identity,
               timestamp,
               web.webPageDetails.name AS PageName,
              attribution_first_touch(timestamp, '', web.webReferrer.url) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_url,
              attribution_first_touch(timestamp, '',channel.typeAtSource) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_channel_type,
               _acp_system_metadata.ingestTime AS ingest_time
           FROM demo_data_trey_mcintyre_midvalues
           WHERE timestamp >= current_date - 90
       )
       ORDER BY User_Identity, timestamp ASC    
   )
   WHERE _demosystem5.IngestTime >= to_timestamp(from_unixtime(@from_batch_ingestion_time/1000, 'yyyy-MM-dd HH:mm:ss'));
  
  -- Update the checkpoint_log table
  INSERT INTO checkpoint_log
  SELECT
     'data_feed' as process_name,
     'SUCCESSFUL' as process_status,
     cast(@to_batch_ingestion_time AS string) as last_snapshot_id,
     cast(@last_updated_timestamp AS timestamp) as process_timestamp;
  
  END
  $$;
  ```

  +++


### 쿼리 예약

쿼리를 예약하여 쿼리가 실행되고 결과가 원하는 간격으로 생성되도록 합니다.

#### 쿼리 편집기 사용

쿼리 편집기를 사용하여 쿼리를 예약할 수 있습니다. 쿼리를 예약할 때 출력 데이터 세트를 정의합니다. 자세한 내용은 [일정 쿼리](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules)를 참조하십시오.


#### 쿼리 서비스 API 사용

또는 RESTful API를 사용하여 쿼리와 쿼리에 대한 일정을 정의할 수 있습니다. 자세한 내용은 [쿼리 서비스 API 안내서](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started)를 참조하십시오.
쿼리를 만들 때(`ctasParameters`쿼리 만들기[) 또는 쿼리에 대한 일정을 만들 때(](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)예약된 쿼리 만들기[) 출력 데이터 집합을 선택적 &#x200B;](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule) 속성의 일부로 정의하는지 확인하십시오.



## 데이터 세트 내보내기

쿼리를 만들고 예약했으며 결과를 확인하면 원시 데이터 세트를 클라우드 스토리지 대상으로 내보낼 수 있습니다. 이 내보내기는 데이터 세트 내보내기 대상이라고 하는 Experience Platform 대상 용어에 있습니다. 개요는 [클라우드 저장소 대상으로 데이터 세트 내보내기](https://experienceleague.adobe.com/ko/docs/experience-platform/destinations/ui/activate/export-datasets)를 참조하십시오.

지원되는 클라우드 스토리지 대상은 다음과 같습니다.

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [데이터 랜딩 영역](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google 클라우드 저장소](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### EXPERIENCE PLATFORM UI

Experience Platform UI를 통해 출력 데이터 세트를 내보내고 내보내기를 예약할 수 있습니다. 이 섹션에서는 관련 단계에 대해 설명합니다.

#### 대상 선택

출력 데이터 집합을 내보낼 클라우드 저장소 대상을 결정했으면 [대상을 선택](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination)합니다. 기본 클라우드 저장소에 대한 대상을 아직 구성하지 않은 경우 [새 대상 연결을 만들어야](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination) 합니다.

대상을 구성하는 과정의 일부로

- 파일 유형(JSON 또는 Parquet)을 정의하고
- 결과 파일의 압축 여부 및
- 매니페스트 파일을 포함해야 하는지 여부를 나타냅니다.


#### 데이터세트 선택

대상을 선택한 경우 다음 **[!UICONTROL 데이터 세트 선택]** 단계에서는 데이터 세트 목록에서 출력 데이터 세트를 선택해야 합니다. 예약된 쿼리를 여러 개 만들었고 출력 데이터 세트를 동일한 클라우드 스토리지 대상으로 보내려는 경우 해당 출력 데이터 세트를 선택할 수 있습니다. 자세한 내용은 [데이터 세트 선택](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets)을 참조하십시오.

#### 데이터 세트 내보내기 예약

마지막으로, **[!UICONTROL 예약]** 단계의 일부로 데이터 세트 내보내기를 예약하려고 합니다. 이 단계에서는 일정 및 출력 데이터 세트 내보내기가 증분적이어야 하는지 여부를 정의할 수 있습니다. 자세한 내용은 [데이터 세트 내보내기 예약](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling)을 참조하십시오.


#### 최종 단계

선택 항목을 [검토](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review)하고, 올바른 경우 출력 데이터 세트를 클라우드 저장소 대상으로 내보내기를 시작합니다.

데이터를 성공적으로 내보내려면 [확인](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify)해야 합니다. 데이터 세트를 내보낼 때 Experience Platform은 대상에 정의된 저장소 위치에 하나 이상의 `.json` 또는 `.parquet` 파일을 만듭니다. 설정한 내보내기 일정에 따라 새 파일이 저장소 위치에 저장됩니다. Experience Platform은 선택한 대상의 일부로 지정한 저장소 위치에 내보낸 파일을 저장하는 폴더 구조를 만듭니다. 내보낼 때마다 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM` 패턴을 따라 새 폴더가 만들어집니다. 기본 파일 이름은 임의로 생성되며 내보낸 파일 이름이 고유한지 확인합니다.

### 플로우 서비스 API

또는 API를 사용하여 출력 데이터 세트를 내보내고 내보내기를 예약할 수 있습니다. 관련된 단계는 [흐름 서비스 API를 사용하여 데이터 세트 내보내기](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets)에 설명되어 있습니다.

#### 시작하기

데이터 세트를 내보내려면 [필요한 권한](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions)이 있는지 확인하십시오. 또한 출력 데이터 세트를 전송할 대상 이 데이터 세트 내보내기를 지원하는지 확인하십시오. 그런 다음 API 호출에서 사용하는 필수 및 선택적 헤더에 대한 값을 [수집](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers)해야 합니다. 데이터 세트를 내보내려는 [대상의 연결 사양 및 흐름 사양 ID를 식별](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec)해야 합니다.

#### 적격 데이터 세트 검색

내보내기를 위해 [적격한 데이터 세트 목록을 검색](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets)하고 [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API를 사용하여 출력 데이터 세트가 해당 목록에 속하는지 확인할 수 있습니다.


#### 소스 연결 만들기

그런 다음 고유한 ID를 사용하여 클라우드 저장소 대상으로 내보낼 출력 데이터 집합에 대해 [원본 연결을 만들어야](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) 합니다. [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API를 사용합니다.

#### 대상에 인증(기본 연결 만들기)

이제 [&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) API를 사용하여 자격 증명을 인증하고 클라우드 저장소 대상에 안전하게 저장하려면 [`POST /targetConection`기본 연결을 만들어야](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) 합니다.


#### 내보내기 매개 변수 제공

그런 다음 [&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) API를 사용하여 출력 데이터 집합에 대한 내보내기 매개 변수를 저장하는 추가 대상 연결을 [`POST /targetConection`만들어야](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) 합니다. 이러한 내보내기 매개 변수에는 위치, 파일 형식, 압축 등이 포함됩니다.

#### 데이터 흐름 설정

마지막으로 [데이터 흐름을 설정](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow)하여 [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API를 사용하여 출력 데이터 세트를 클라우드 저장소 대상으로 내보냅니다. 이 단계에서는 `scheduleParams` 매개 변수를 사용하여 내보내기 일정을 정의할 수 있습니다.

#### 데이터 흐름 유효성 검사

[데이터 흐름의 성공적인 실행을 확인](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs)하려면 [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API를 사용하여 데이터 흐름 ID를 쿼리 매개 변수로 지정하십시오. 이 데이터 흐름 ID는 데이터 흐름을 설정할 때 반환되는 식별자입니다.

[데이터를 성공적으로 내보냈습니다.](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) 데이터 세트를 내보낼 때 Experience Platform은 대상에 정의된 저장소 위치에 하나 이상의 `.json` 또는 `.parquet` 파일을 만듭니다. 설정한 내보내기 일정에 따라 새 파일이 저장소 위치에 저장됩니다. Experience Platform은 선택한 대상의 일부로 지정한 저장소 위치에 내보낸 파일을 저장하는 폴더 구조를 만듭니다. 내보낼 때마다 `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM` 패턴을 따라 새 폴더가 만들어집니다. 기본 파일 이름은 임의로 생성되며 내보낸 파일 이름이 고유한지 확인합니다.

## 결론

즉, Adobe Analytics 데이터 피드 기능을 에뮬레이션한다는 것은 쿼리 서비스를 사용하여 예약된 쿼리를 설정하고 이러한 쿼리의 결과를 예약된 데이터 세트 내보내기에서 사용함을 의미합니다.

>[!IMPORTANT]
>
>이 사용 사례에는 두 개의 스케줄러가 포함됩니다. 에뮬레이트된 데이터 피드 기능이 적절히 작동하도록 하려면 쿼리 서비스 및 데이터 내보내기에 구성된 일정이 간섭되지 않도록 하십시오.
