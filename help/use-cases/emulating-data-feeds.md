---
title: 데이터 피드 기능 에뮬레이션
description: Experience Platform의 데이터로 Adobe Analytics 데이터 피드를 에뮬레이션하는 방법을 이해합니다.
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: d5719dddfb4cefda761370951973d55b3904032f
workflow-type: tm+mt
source-wordcount: '2107'
ht-degree: 1%

---

# 데이터 피드 기능 에뮬레이션

Adobe Analytics 데이터 피드는 Adobe Analytics에서 원시 데이터를 가져오는 강력한 방법입니다. 이 사용 사례에서는 Experience Platform에서 유사한 유형의 원시 데이터를 가져와 Adobe 외부의 다른 플랫폼에서 사용하고 조직의 재량으로 사용하는 방법에 대해 설명합니다.

## 사전 요구 사항

이 사용 사례에서 설명하는 기능을 사용하기 전에 다음 요구 사항을 모두 충족하는지 확인하십시오.

* Experience Platform의 데이터 레이크로 온라인 및 오프라인 데이터를 전송하는 작업 구현입니다.
* 플랫폼 기반 응용 프로그램 또는 Data Distiller 추가 기능의 일부로 패키지된 Query Service에 액세스합니다. 다음을 참조하십시오 [쿼리 서비스 패키징](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) 추가 정보.
* Real-Time CDP Prime 또는 Ultimate 패키지, Adobe Journey Optimizer 또는 Customer Journey Analytics을 구매한 고객이 사용할 수 있는 데이터 세트 내보내기 기능에 액세스합니다. 다음을 참조하십시오 [클라우드 스토리지 대상으로 데이터 세트 내보내기](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ko) 추가 정보.
* 데이터 피드의 원시 데이터를 내보낼 수 있는 위치에 구성된 하나 이상의 대상(예: Amazon S3, Google 클라우드 스토리지).

## 소개

Adobe Analytics 데이터 피드 에뮬레이션에는 다음이 포함됩니다.

* 정의 **예약된 쿼리** 를 사용하여 데이터 피드에 대한 데이터를 출력 데이터 세트로 생성합니다. **쿼리 서비스**.
* 정의 **예약된 데이터 세트 내보내기** 를 사용하여 출력 데이터 세트를 클라우드 스토리지 대상으로 내보냅니다. **데이터 세트 내보내기**.


![데이터 피드](assets/data-feed.svg)


## 쿼리 서비스

Experience Platform 쿼리 서비스를 사용하면 Experience Platform 데이터 레이크의 데이터 세트를 데이터베이스 테이블처럼 쿼리하고 조인할 수 있습니다. 그런 다음 보고 또는 내보내기에 추가로 사용하기 위해 결과를 새 데이터 세트로 캡처할 수 있습니다.

쿼리 서비스를 사용합니다. [사용자 인터페이스](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en), a [PostgresSQL 프로토콜을 통해 연결된 클라이언트](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=ko), 또는 [RESTful API](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) 데이터 피드에 대한 데이터를 수집하는 쿼리를 만들고 예약합니다.

### 쿼리 만들기

SELECT 문용 표준 ANSI SQL의 모든 기능과 기타 제한된 명령을 사용하여 데이터 피드에 대한 데이터를 생성하는 쿼리를 만들고 실행할 수 있습니다. 다음을 참조하십시오 [SQL 구문](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) 추가 정보. 이 SQL 구문 이상의 Adobe은

* 사전 빌드됨 [Adobe 정의 함수 (ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) Experience Platform 데이터 레이크에 저장된 이벤트 데이터에 대해 일반적인 비즈니스 관련 작업을 수행하는 데 도움이 됩니다. [세션화](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=ko) 및 [속성](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=ko),
* 여러 기본 제공 [Spark SQL 함수](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en),
* [metadata PostgreSQL 명령](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en),
* [준비된 진술](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### 예

데이터 피드에 대한 데이터를 수집하는 쿼리의 몇 가지 예가 아래에 나와 있습니다. 이러한 예제는 `demo_system_event_dataset_for_website_global_v1_1` 는 웹 사이트와 상호 작용하는 고객으로부터 수집된 데이터를 포함하는 샘플 경험 이벤트 데이터 세트입니다.

+++상위 5개 제품

*웹사이트에서 본 상위 5개 제품은 무엇입니까?*

```sql
select productListItems.name, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType = 'commerce.productViews'
group  by productListItems.name
order  by 2 desc
limit 5;
```

+++

+++제품 상호 작용 단계

*웹 사이트에서 다양한 제품 상호 작용은 무엇입니까?*

```sql
select eventType, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType is not null
and    eventType <> ''
group  by eventType;
```

+++

+++사람들이 하는 일

*사람들이 한 세션에서 세 번째 페이지로 &quot;서비스 취소&quot; 페이지에 도달하기 전에 사이트에서 수행하는 작업은 무엇입니까?*

이 쿼리는 Adobe 정의 함수를 사용합니다. `SESS_TIMEOUT` 및 `NEXT`.

* 다음 `SESS_TIMEOUT()` Adobe Analytics에 있는 방문 그룹화를 재현합니다. 이는 유사한 시간 기반 그룹화를 수행하지만 사용자 정의 가능한 매개 변수를 사용합니다.
* `NEXT()` 및 `PREVIOUS()` 고객이 사이트를 탐색하는 방법을 이해할 수 있도록 지원합니다.

```sql
SELECT
  webPage,
  webPage_2,
  webPage_3,
  webPage_4,
  count(*) journeys
FROM
  (
      SELECT
        webPage,
        NEXT(webPage, 1, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_2,
        NEXT(webPage, 2, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_3,
        NEXT(webPage, 3, true)
           OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_4,
        session.depth AS SessionPageDepth
      FROM (
            select a._sampleorg.identification.core.ecid as ecid,
                   a.timestamp,
                   web.webPageDetails.name as webPage,
                    SESS_TIMEOUT(timestamp, 60 * 30)
                       OVER (PARTITION BY a._sampleorg.identification.core.ecid
                             ORDER BY timestamp
                             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
                  AS session
            from   demo_system_event_dataset_for_website_global_v1_1 a
            where  a._sampleorg.identification.core.ecid in (
                select b._sampleorg.identification.core.ecid
                from   demo_system_event_dataset_for_website_global_v1_1 b
                where  b.web.webPageDetails.name = 'Cancel Service'
            )
        )
)
WHERE SessionPageDepth=1
and   webpage_3 = 'Cancel Service'
GROUP BY webPage, webPage_2, webPage_3, webPage_4
ORDER BY journeys DESC
LIMIT 10;
```

+++

+++시간

*방문자가 &quot;서비스 취소&quot; 페이지를 방문한 후 콜센터에 문의 전화를 하기까지 시간이 얼마나 됩니까?*

이러한 종류의 쿼리에 응답하려면 `TIME_BETWEEN_NEXT_MATCH()` Adobe 정의 함수입니다. 이전 또는 다음 일치 함수 사이의 시간 기능은 특정 인시던트 이후 경과된 시간을 측정하는 새 차원을 제공합니다.

```sql
select * from (
       select _sampleorg.identification.core.ecid as ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
where r.webPage = 'Cancel Service'
limit 15;
```

+++

+++결과는 무엇입니까?

*고객이 콜센터에 전화하면 어떤 결과가 나오나요?*

이 쿼리의 경우 `demo_system_event_dataset_for_website_global_v1_1` 데이터 세트가 예제로 결합됨 `demo_system_event_dataset_for_call_center_global_v1_1` 콜센터 상호 작용이 포함된 데이터 세트입니다.

```sql
select distinct r.*,
       c._sampleorg.interactionDetails.core.callCenterAgent.callFeeling,
       c._sampleorg.interactionDetails.core.callCenterAgent.callTopic,
       c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled
from (
       select _sampleorg.identification.core.ecid ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
, demo_system_event_dataset_for_call_center_global_v1_1 c
where r.ecid = c._sampleorg.identification.core.ecid
and r.webPage = 'Cancel Service'
and c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled IN (true,false)
and c._sampleorg.interactionDetails.core.callCenterAgent.callTopic IN ('contract', 'invoice','complaint','wifi')
limit 15;
```

+++

+++마케팅 채널 참여(Adobe Analytics 데이터)

*이탈리아어 중심의 웹 트래픽을 위한 마케팅 채널 전반의 참여는 무엇입니까?*

이 예에서는 Adobe Analytics 소스 커넥터에서 자동으로 만든 데이터 세트(예: )를 사용합니다 `demo_data_sample_org_midvalues`.

```sql
select 
    channel.typeAtSource, count(*) 
from 
    demo_data_sample_org_midvalues 
where 
    (channel.typeAtSource IS NOT NULL
and
    web.webPageDetails.URL LIKE '%/it/it/%')
group by 
    channel.typeAtSource
order by 2 desc;
```

+++

더 많은 (고급) 샘플 쿼리는 다음을 참조하십시오. [포기한 찾아보기](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en), [속성 분석](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en), [보트 필터링](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en)및 쿼리 서비스 안내서의 기타 예제를 참조하십시오.


#### ID

Experience Platform에서 다양한 ID를 사용할 수 있습니다. ID를 올바르게 쿼리하고 있는지 확인합니다. 위의 예에서 ECID는 식별 개체의 일부인 핵심 개체의 일부로 정의되며, 둘 다 경험 이벤트 핵심 필드 그룹을 사용하여 스키마에 추가됩니다(예: `_sampleorg.identification.core.ecid`). ECID는 스키마에서 다르게 구성될 수 있습니다.

또는 다음을 사용할 수 있습니다 `identityMap` ID를 쿼리합니다. 이 개체는 유형입니다. `Map` 및 를 사용합니다. [중첩된 데이터 구조](#nested-data-structure).

Adobe Analytics 소스 커넥터를 사용하여 수집된 데이터의 경우 여러 ID를 사용할 수 있습니다. 기본 식별자는 ECID 또는 AAID의 존재 여부에 따라 다릅니다. 다음을 참조하십시오 [Adobe Analytics 데이터의 기본 식별자](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#how-the-analytics-source-treats-identities) 및 [AAID, ECID, AACUSTOMID 및 Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=ko) 추가 정보

#### 데이터 피드 열

쿼리에 사용할 수 있는 필드(열)는 데이터 세트의 기반이 되는 스키마 정의에 따라 다릅니다. 데이터 세트의 기본 스키마를 이해해야 합니다.

예를 들어, 일부 [예제 쿼리](#examples) 을(를) 쿼리했습니다. *페이지 이름*.

* Adobe Analytics 데이터 피드의 UI에서 **[!UICONTROL pagename]** 를 데이터 피드 정의에 추가할 열로 지정합니다.
* 쿼리 서비스에서 다음을 포함합니다. `web.webPageDetails.name` 다음에서 `demo_system_event_dataset_for_website_global_v1_1` 데이터 세트 (기반) **데모 시스템 - 웹 사이트에 대한 이벤트 스키마(전역 v1.1)** 경험 이벤트 스키마)를 포함할 수 있습니다. 다음을 참조하십시오. [웹 세부 정보 스키마 필드 그룹](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) 추가 정보.

경험 이벤트 데이터 세트와 기본 스키마의 이전 Adobe Analytics 데이터 열과 XDM 필드 간의 매핑을 이해하려면 다음을 참조하십시오. [Analytics 필드 매핑](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ko) 및 [Adobe Analytics ExperienceEvent 전체 확장 스키마 필드 그룹](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) 추가 정보.

또한, Experience Platform Web SDK에서 자동으로 수집된 정보는 쿼리의 열을 식별하는 것과 관련이 있을 수 있습니다. 다음을 참조하십시오 [자동으로 수집된 정보](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) 추가 정보.


#### 조회

다른 데이터 세트에서 데이터를 조회하려면 표준 SQL 기능(WHERE 절, INNER JOIN, OUTER JOIN 등)을 사용합니다. 다음을 참조하십시오. [결과는 무엇입니까?](#examples) 예제에서 를 쿼리합니다.

#### 계산

필드(열)에서 계산을 수행하려면 표준 SQL 함수를 사용합니다(예: `COUNT(*)` 다음에서 [제품 상호 작용 단계](#examples) 예제에서 쿼리) 또는 [수학 및 통계 연산자 및 함수](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) spark SQL의 일부입니다.

#### 중첩된 데이터 구조

데이터 세트가 기반으로 하는 스키마에는 종종 중첩된 데이터 구조를 포함하는 복잡한 데이터 유형이 포함됩니다. 이전에 언급됨 `identityMap` 는 중첩된 데이터 구조의 예입니다. 의 예는 아래를 참조하십시오. `identityMap` 데이터.

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

다음을 사용할 수 있습니다. [`explode()` 또는 기타 배열 함수](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) Spark SQL에서 중첩된 데이터 구조 내의 데이터로 이동합니다.

예:

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

또는 점 표기법을 사용하여 개별 요소를 참조할 수 있습니다. 예:

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

자세한 내용은 [Query Service에서 중첩된 데이터 구조로 작업](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en)을 참조하십시오.

### 쿼리 예약

쿼리를 예약하여 쿼리가 실행되고 결과가 원하는 간격으로 생성되도록 합니다. 쿼리를 예약할 때 출력 데이터 세트를 정의합니다.

#### 쿼리 편집기 사용

쿼리 편집기를 사용하여 쿼리를 예약할 수 있습니다. 쿼리에 대한 일정을 정의할 때 출력 데이터 세트를 정의할 수 있습니다. 다음을 참조하십시오 [쿼리 일정](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) 추가 정보.


#### 쿼리 서비스 API 사용

또는 RESTful API를 사용하여 쿼리와 쿼리에 대한 일정을 정의할 수 있습니다. 다음을 참조하십시오 [쿼리 서비스 API 안내서](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en_) 추가 정보.
출력 데이터 세트를 선택 사항의 일부로 정의해야 합니다. `ctasParameters` 쿼리를 만들 때 속성([쿼리 만들기](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)) 또는 쿼리에 대한 일정을 만들 때([예약된 쿼리 만들기](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)).



## 데이터 세트 내보내기

쿼리를 만들고 예약했으며 출력 데이터 세트의 결과가 요구 사항과 일치하는지 확인하면 원시 데이터 세트를 클라우드 스토리지 대상으로 내보낼 수 있습니다. 이 내보내기는 데이터 세트 내보내기 대상이라고 하는 Experience Platform 대상 용어에 있습니다. 다음을 참조하십시오 [클라우드 스토리지 대상으로 데이터 세트 내보내기](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ko) 개요를 참조하십시오.

지원되는 클라우드 스토리지 대상은 다음과 같습니다.

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [데이터 랜딩 영역](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Google 클라우드 스토리지](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### EXPERIENCE PLATFORM UI

Experience Platform UI를 통해 출력 데이터 세트를 내보내고 내보내기를 예약할 수 있습니다. 이 섹션에서는 관련 단계에 대해 설명합니다.

#### 대상 선택

출력 데이터 세트를 내보낼 클라우드 스토리지 대상을 결정한 경우 [대상 선택](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). 기본 클라우드 스토리지에 대한 대상을 아직 구성하지 않은 경우 다음을 수행해야 합니다 [새 대상 연결 만들기](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=en).

대상 구성의 일부로 파일 유형(JSON 또는 Parquet), 결과 파일의 압축 여부 및 매니페스트 파일의 포함 여부를 정의할 수 있습니다.


#### 데이터세트 선택

대상을 선택한 경우 다음에서 **[!UICONTROL 데이터 세트 선택]** 단계 데이터 세트 목록에서 출력 데이터 세트를 선택해야 합니다. 예약된 쿼리를 여러 개 만들었고 출력 데이터 세트를 동일한 클라우드 스토리지 대상으로 보내려는 경우 해당 출력 데이터 세트를 선택할 수 있습니다. 다음을 참조하십시오 [데이터 세트 선택](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) 추가 정보.

#### 데이터 세트 내보내기 예약

마지막으로, 데이터 세트 내보내기를 **[!UICONTROL 예약]** 단계. 이 단계에서는 일정 및 출력 데이터 세트 내보내기가 증분적이어야 하는지 여부를 정의할 수 있습니다. 다음을 참조하십시오 [데이터 세트 내보내기 예약](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) 추가 정보.


#### 최종 단계

[리뷰](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) 선택 사항 및 올바른 경우 출력 데이터 세트를 클라우드 스토리지 대상으로 내보냅니다.

다음을 수행해야 합니다. [확인](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) 성공적인 데이터 내보내기. 데이터 세트를 내보낼 때 Experience Platform이 하나 또는 여러 개의 데이터 세트를 만듭니다 `.json` 또는 `.parquet` 대상에 정의된 저장소 위치의 파일입니다. 설정한 내보내기 일정에 따라 새 파일이 저장소 위치에 저장됩니다. Experience Platform은 선택한 대상의 일부로 지정한 저장소 위치에 내보낸 파일을 저장하는 폴더 구조를 만듭니다. 내보내기 시간마다 패턴을 따라 새 폴더가 만들어집니다. `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. 기본 파일 이름은 임의로 생성되며 내보낸 파일 이름이 고유한지 확인합니다.

### 플로우 서비스 API

또는 API를 사용하여 출력 데이터 세트를 내보내고 내보내기를 예약할 수 있습니다. 관련된 단계는에 설명되어 있습니다. [흐름 서비스 API를 사용하여 데이터 세트 내보내기](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### 시작

다음을 확인합니다. [필수 권한](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) 데이터 세트를 내보내고 출력 데이터 세트를 보낼 대상에 가 데이터 세트 내보내기를 지원하는지 확인하십시오. 그러면 다음을 수행해야 합니다. [필수 및 선택적 헤더에 대한 값을 수집합니다.](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) API 호출에서뿐만 아니라 [대상의 연결 사양 및 흐름 사양 ID 식별](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) 데이터 세트를으로 내보내려고 합니다.

#### 적격 데이터 세트 검색

다음을 수행할 수 있습니다. [적격 데이터 세트 목록 검색](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) 를 사용하여 출력 데이터 세트가 해당 목록에 속하는지 여부를 내보내고 확인합니다. [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API.


#### 소스 연결 만들기

다음: [소스 연결 만들기](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) 클라우드 스토리지 대상으로 내보낼 출력 데이터 세트의 경우 고유 ID를 사용합니다. 다음을 사용합니다. [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API.

#### 대상에 인증(기본 연결 만들기)

이제 다음을 수행해야 합니다. [기본 연결 만들기](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) 을(를) 사용하여 자격 증명을 올바르게 인증하고 클라우드 스토리지 대상에 안전하게 저장하려는 경우 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API.


#### 내보내기 매개 변수 제공

다음으로, 다음을 수행해야 합니다. [내보내기 매개 변수를 저장하는 추가 target 연결 만들기](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) 를 사용하여 출력 데이터 세트에 대해 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API. 이러한 내보내기 매개 변수에는 위치, 파일 형식, 압축 등이 포함됩니다.

#### 데이터 흐름 설정

마지막으로, [데이터 흐름 설정](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) 를 사용하여 출력 데이터 세트를 클라우드 스토리지 대상으로 내보냅니다. [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API. 이 단계에서는 다음을 사용하여 내보내기 일정을 정의할 수 있습니다. `scheduleParams` 매개 변수.

#### 데이터 흐름 유효성 검사

종료 [데이터 흐름의 성공적인 실행 확인](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs), 사용 [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) 데이터 흐름 ID를 쿼리 매개 변수로 지정하는 API입니다. 이 데이터 흐름 ID는 데이터 흐름을 설정할 때 반환되는 식별자입니다.

[확인](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) 성공적인 데이터 내보내기. 데이터 세트를 내보낼 때 Experience Platform이 하나 또는 여러 개의 데이터 세트를 만듭니다 `.json` 또는 `.parquet` 대상에 정의된 저장소 위치의 파일입니다. 설정한 내보내기 일정에 따라 새 파일이 저장소 위치에 저장됩니다. Experience Platform은 선택한 대상의 일부로 지정한 저장소 위치에 내보낸 파일을 저장하는 폴더 구조를 만듭니다. 내보내기 시간마다 패턴을 따라 새 폴더가 만들어집니다. `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. 기본 파일 이름은 임의로 생성되며 내보낸 파일 이름이 고유한지 확인합니다.

## 결론

즉, Adobe Analytics 데이터 피드 기능을 에뮬레이션한다는 것은 쿼리 서비스를 사용하여 예약된 쿼리를 설정하고 이러한 쿼리의 결과를 예약된 데이터 세트 내보내기에서 사용함을 의미합니다.

>[!IMPORTANT]
>
>이 사용 사례에는 두 개의 스케줄러가 포함됩니다. 에뮬레이트된 데이터 피드 기능이 적절히 작동하도록 하려면 쿼리 서비스 및 데이터 내보내기에 구성된 일정이 간섭되지 않도록 하십시오.

