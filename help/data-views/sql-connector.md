---
title: SQL 커넥터
description: Query Service, Power BI 및/또는 타블로를 사용하여 SQL Connector를 사용하여 데이터 보기에 액세스하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 5b84c2c908f947b1abed621f68aa1a324faeecde
workflow-type: tm+mt
source-wordcount: '2890'
ht-degree: 2%

---

# SQL 커넥터

{{release-limited-testing}}

다음 [!DNL Customer Journey Analytics (CJA) SQL Connector] SQL에서 [데이터 보기](./data-views.md) 추가 콘텐츠는 CJA에서 정의한 것입니다. 데이터 엔지니어 및 분석가는 Power BI, 타블로 또는 기타 비즈니스 인텔리전스 및 시각화 도구(BI 도구라고도 함)에 더 익숙할 수 있습니다. 이제 CJA 사용자가 Analysis Workspace 프로젝트를 만들 때 사용하는 것과 동일한 데이터 보기를 기반으로 보고 및 대시보드를 만들 수 있습니다.

Adobe Experience Platform [쿼리 서비스](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ko-KR?lang=kr) 는 Experience Platform 데이터 레이크에서 사용할 수 있는 데이터에 대한 SQL 인터페이스입니다. 사용 [!DNL CJA SQL Connector] 활성화됨, 기능 [!DNL Query Service] 는 CJA 데이터 보기를 [!DNL Query Service] 세션. 그 결과, [!DNL Query Service] 의 PostgresSQL 인터페이스는 이러한 확장 기능을 통해 원활하게 제공됩니다.

주요 이점은 다음과 같습니다.

- BI 도구 자체 내에서 CJA 데이터 보기에 대한 동등한 표현을 다시 만들 필요가 없습니다. <br/>자세한 내용은 [데이터 보기](data-views.md) 다시 만들어야 하는 사항을 이해하기 위해 데이터 보기 기능에 대한 자세한 내용을 참조하십시오.<br/>

- BI 도구와 CJA 간의 보고 및 분석에서 일관됩니다.

- CJA 데이터를 BI 도구에서 이미 사용 가능한 다른 데이터 소스와 결합합니다.

## 사전 요구 사항

이 기능을 사용하려면 다음을 수행해야 합니다

- 를 활성화합니다 [!UICONTROL CJA SQL 커넥터] Experience Platform 조직에 로그인합니다.

- 관련 제품 프로필, 사용자 그룹 및/또는 개별 사용자에 대한 기능을 구성합니다.<br/>
사용자에게 다음에 대한 액세스 권한이 있어야 합니다.
   - Experience Platform 쿼리 서비스,
   - CJA 작업 공간 프로젝트 및
   - 사용하려는 CJA 데이터 보기.

- 만료되지 않은 자격 증명에서 만료되는 항목을 사용하여 BI 도구를 CJA SQL Connector에 연결합니다. Thr [자격 증명 안내서](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) 만료 자격 증명 또는 만료되지 않은 자격 증명 설정에 대한 자세한 정보를 제공합니다.

자세한 내용은 [액세스 제어](../admin/cja-access-control.md) 자세한 내용은 CJA 관리 섹션에서 확인하십시오.


## 사용

를 사용하려면 [!DNL CJA SQL Connector] 기능을 통해 SQL을 직접 사용하거나 특정 BI 도구에서 사용할 수 있는 드래그하여 놓기 경험을 사용할 수 있습니다.

### SQL

쿼리 편집기 또는 표준 PostgresSQL 명령줄 인터페이스(CLI) 클라이언트를 사용하여 SQL 문에서 직접 기능을 사용할 수 있습니다.

+++ 쿼리 편집기

Experience Platform UI에서:

1. 선택 **[!UICONTROL **&#x200B;쿼리&#x200B;**]** 변환 전: **[!UICONTROL **&#x200B;데이터 관리&#x200B;**]** 왼쪽 레일에 있습니다.

2. 선택 ![쿼리 만들기](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;쿼리 만들기&#x200B;**]**.

3. 쿼리를 실행하려면 SQL 문을 입력하고 ![재생](assets/Smock_Play_18_N.svg) 단추(또는 Shift + Enter 키)를 누릅니다.

+++


+++ PostgresSQL CLI

1. Experience Platform UI에서 PostgresSQL 자격 증명을 조회하고 복사합니다.

   1. 선택 **[!UICONTROL **&#x200B;쿼리&#x200B;**]** 왼쪽 레일에서(아래) **[!UICONTROL **&#x200B;데이터 관리&#x200B;**]**).

   2. 선택 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]** 상단 막대에서

   3. 연결 문자열을 복사하려면 ![복사](assets/Smock_Copy_18_N.svg) 에서 **[!UICONTROL ** PSQL 명령&#x200B;**]** 섹션을 참조하십시오.

2. PostgresSQL CLI를 엽니다.

3. 로그인하여 쿼리 실행을 시작하려면 PostgresSQL CLI에 연결 문자열을 붙여 넣습니다.

+++

자세한 내용은 [쿼리 편집기 UI 안내서](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) 추가 정보.


### BI 도구

현재 CJA SQL 커넥터는 Power BI 및 타블로에 대해 지원됩니다.

+++ Power BI

1. Adobe Experience Platform UI에서 PostgresSQL 자격 증명에 대한 세부 사항을 확인합니다.

   1. 선택 **[!UICONTROL **&#x200B;쿼리&#x200B;**]** 왼쪽 레일에서(아래) **[!UICONTROL **&#x200B;데이터 관리&#x200B;**]**).

   2. 선택 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]** 상단 막대에서

   3. 사용 ![복사](assets/Smock_Copy_18_N.svg) 각 Postgres 자격 증명 매개 변수([!UICONTROL 호스트], [!UICONTROL 포트], [!UICONTROL 데이터베이스], [!UICONTROL 사용자 이름], 및 기타)만 사용할 수 있습니다.

2. Power BI:

   1. 주 창에서 **[!UICONTROL **&#x200B;데이터 가져오기&#x200B;**]** 상단 도구 모음에서 를 클릭합니다.

   2. 선택 **[!UICONTROL **&#x200B;자세히...**]** 왼쪽 레일에 있습니다.

   3. 에서 **데이터 가져오기** screen, search `PostgresSQL` 을(를) 선택하고 을(를) 선택합니다. **[!UICONTROL ** PostgresSQL 데이터베이스&#x200B;**]** 참조하십시오.

   4. 에서 **[!UICONTROL ** PostgressSQL 데이터베이스&#x200B;**]** 대화 상자:

      1. 붙여넣기 **[!UICONTROL **&#x200B;호스트&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 변환 **[!UICONTROL **&#x200B;서버&#x200B;**]** 텍스트 필드.

      2. 붙여넣기 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] in **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 텍스트 필드.

         추가 `?FLATTEN` 변환 후 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개 변수를 사용하여 `prod:all?FLATTEN` 예. 자세한 내용은 [타사 BI 도구에서 사용할 중첩 데이터 구조 병합](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 추가 정보.

      3. 을 묻는 메시지가 나타나면 **[!UICONTROL **&#x200B;데이터 연결&#x200B;**]** 모드, 선택 **[!UICONTROL ** DirectQuery **]** 데이터 구조가 제대로 변환되도록 합니다.

      4. 을 묻는 메시지가 표시됩니다 **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** 및 **[!UICONTROL **&#x200B;암호&#x200B;**]**. Experience Platform 쿼리에서 동등 매개 변수를 사용합니다 [!UICONTROL 자격 증명].
   5. 성공적으로 로그인하면 CJA 데이터 보기 테이블이 Power BI의 **[!UICONTROL **&#x200B;네비게이터&#x200B;**]**. 데이터 보기 테이블은 `dv_` 이름 안에


   6. 사용할 데이터 보기 테이블을 선택하고 을 선택합니다 **[!UICONTROL **&#x200B;로드&#x200B;**]**.

   선택한 하나 이상의 테이블과 연관된 모든 차원과 지표는 시각화에 사용할 준비가 된 오른쪽 창에 표시됩니다.

   자세한 내용은 [쿼리 서비스에 Power BI 연결](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) 추가 정보.

+++

+++타블로

1. Experience Platform UI에서 PostgresSQL 자격 증명에 대한 세부 사항을 찾습니다.

   1. 선택 **[!UICONTROL **&#x200B;쿼리&#x200B;**]** 왼쪽 레일에서(아래) **[!UICONTROL **&#x200B;데이터 관리&#x200B;**]**).

   2. 선택 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]** 상단 막대에서

   3. 사용 ![복사](assets/Smock_Copy_18_N.svg) 각 Postgres 자격 증명 매개 변수([!UICONTROL 호스트], [!UICONTROL 포트], [!UICONTROL 데이터베이스], [!UICONTROL 사용자 이름]( 및 기타)가 있어야 합니다.

2. 타블로에서:

   1. 선택 **[!UICONTROL **&#x200B;자세히&#x200B;**]** 변환 전: **[!UICONTROL **&#x200B;서버로&#x200B;**]** 왼쪽 레일에 있습니다.

   2. 선택 **[!UICONTROL ** PostgresSQL **]** 참조하십시오.

   3. 에서 [!UICONTROL PostgresSQL] 대화 상자:

      1. 붙여넣기 **[!UICONTROL **&#x200B;호스트&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 변환 **[!UICONTROL **&#x200B;서버&#x200B;**]** 텍스트 필드.

      2. 붙여넣기 **[!UICONTROL **&#x200B;포트&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 변환 **[!UICONTROL **&#x200B;포트&#x200B;**]** 텍스트 필드.

      3. 붙여넣기 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 변환 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 텍스트 필드.

         추가 `%3FFLATTEN` 변환 후 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개 변수를 사용하여 `prod:all%3FFLATTEN` 예. 자세한 내용은 [타사 BI 도구에서 사용할 중첩 데이터 구조 병합](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 추가 정보.

      4. 선택 **[!UICONTROL **&#x200B;사용자 이름 및 암호&#x200B;**]** 변환 전: **[!UICONTROL **&#x200B;인증&#x200B;**]** 목록.

      5. 붙여넣기 **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 변환 **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** 텍스트 필드.

      6. 붙여넣기 **[!UICONTROL **&#x200B;암호&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 변환 **[!UICONTROL **&#x200B;암호&#x200B;**]** 텍스트 필드.

      7. 선택 **[!UICONTROL **&#x200B;로그인&#x200B;**]**.
   4. CJA 데이터 보기는 **[!UICONTROL **&#x200B;표&#x200B;**]** 목록. 데이터 보기 테이블에는 `dv_`.

   5. 캔버스에서 사용할 표를 드래그합니다.

   이제 데이터 보기 테이블의 데이터를 사용하여 보고서 및 시각화를 작성할 수 있습니다.

   자세한 내용은 [타블로와 쿼리 서비스 연결](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) 추가 정보.

+++

자세한 내용은 [클라이언트를 Query Service에 연결](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) 를 참조하십시오.

## 기능

기본적으로 데이터 보기에는 친숙한 이름에서 생성된 테이블 안전 이름이 있습니다. 예를 들어 이름이 인 데이터 보기가 있습니다 [!UICONTROL 내 웹 데이터] 에는 보기 이름이 있습니다. `dv_my_web_data`.

데이터 보기 ID를 테이블 이름으로 사용하려면 선택 사항을 추가할 수 있습니다 `CJA_USE_IDS` 연결할 때 데이터베이스 이름으로 설정합니다. 예, `prod:all?CJA_USE_IDS` 는 와 같은 이름으로 데이터 보기를 표시합니다 `dv_ABC123`.

### 데이터 거버넌스

Customer Journey Analytics의 데이터 거버넌스 관련 설정은 Adobe Experience Platform에서 상속됩니다. CJA와 Adobe Experience Platform 데이터 거버넌스 간의 통합을 통해 민감한 CJA 데이터의 레이블 지정 및 개인정보 처리방침 시행이 가능합니다.

Experience Platform에서 사용하는 데이터 세트에 생성된 개인정보 보호 레이블 및 정책은 CJA 데이터 보기 워크플로에 표시될 수 있습니다. 따라서 CJA SQL Connector를 사용하여 쿼리된 데이터는 정의된 개인 정보 레이블 및 정책을 준수하지 않을 때 적절한 경고 또는 오류를 표시합니다.

### 목록 데이터 보기

표준 PostgreSQL CLI에서는 `\dv`

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### 중첩된 것과 병합된 것

기본적으로 데이터 보기의 스키마에서는 원래 XDM 스키마처럼 중첩된 구조를 사용합니다. 통합은 또한 `FLATTEN` 선택 사항입니다. 이 옵션을 사용하여 데이터 보기(및 세션의 다른 테이블)에 대한 스키마를 평면화할 수 있습니다. 병합을 사용하면 구조화된 스키마를 지원하지 않는 BI 도구에서 쉽게 사용할 수 있습니다. 자세한 내용은 [Query Service에서 중첩된 데이터 구조 작업](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 추가 정보.

### 지원되는 SQL

자세한 내용은 [쿼리 서비스 SQL 참조](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) 을 참조하십시오.

패턴 및 예제에 대한 개요는 아래의 패턴 표를 참조하십시오.

+++패턴

| 패턴 | 예 |
|---|---|
| 스키마 검색 | <pre>DV1에서 * 선택(여기서 1=0)</pre> |
| 등급/분류 | <pre>DIM1, SUM(metric1) AS m1 선택<br/>DV1에서<br/>여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>DIM1로 그룹화</pre><pre>DIM1, SUM(metric1) AS m1 선택<br/>DV1에서<br/>여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>  filterId = &#39;12345&#39;<br/>DIM1로 그룹화</pre><pre>DIM1, SUM(metric1) AS m1 선택<br/>DV1에서<br/>여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>DIM1로 그룹화</pre> |
| HAVING 절 | <pre>DIM1, SUM(metric1) AS m1 선택<br/>DV1에서<br/>여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>DIM1로 그룹화<br/>m1 > 100 포함 |
| 개별적인, 위쪽 <br/>차원 값 | <pre>DV1에서 DISTINCT dim1 선택</pre><pre>DIM1 AS dv1 선택<br/>DV1에서<br/>여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>DIM1로 그룹화</pre><pre>DIM1 AS dv1 선택<br/>DV1에서<br/>여기서 \&#39;timestamp\&#39; >= &#39;2022-01-01&#39; AND \&#39;timestamp\&#39; &lt; &#39;2022-01-02&#39;<br/>DIM1로 그룹화<br/>합계별 주문(지표1)<br/>제한 15</pre> |
| 지표 합계 | <pre>SUM(metric1) AS m1 선택<br/>DV1에서<br/>여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;</pre> |
| 다중 차원<br/>분류<br/>및 최상위 차이점 | <pre>DIM1, dim2, SUM(metric1) AS m1 을 선택합니다.<br/>DV1에서<br/>여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>GROUP BY dim1, dim2</pre><pre>DIM1, dim2, SUM(metric1) AS m1 을 선택합니다.<br/>DV1에서<br/>여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>그룹 기준 1, 2<br/>주문 기준 1, 2</pre><pre>DISTINCT dim1, dim2 선택<br/>DV1에서</pre> |
| 하위 선택:<br/>추가 결과<br/>필터링 | <pre>DIM1, m1 선택<br/>FROM (<br/>  DIM1, SUM(metric1) AS m1 선택<br/>  DV1에서<br/>  여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;</br>  DIM1로 그룹화<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| 하위 선택:<br/>참가<br/>데이터 세트가 없습니다.<br/>CJA | <pre>b.key, a.dim1, a.m1 선택<br/>FROM (<br/>  DIM1, SUM(metric1) AS m1 선택<br/>  DV1에서<br/>  여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>  DIM1로 그룹화<br/>)<br/>a.dim1 = b.key에서 왼쪽 조인 조회</pre> |
| 하위 선택:<br/>전체 쿼리<br/>데이터 보기 | <pre>SELECT 키, SUM(m1) AS 합계<br/>FROM (<br/>  DIM1 AS 키, SUM(metric1) AS m1 선택<br/>  DV1에서<br/>  여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>  DIM1로 그룹화<br/><br/>  결합<br/><br/>  DIM2 AS 키, SUM(m1) AS m1 선택<br/>  DV2에서<br/>  여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>  DIM2로 그룹화<br/>GROUP BY 키<br/>합계별 주문</pre> |
| 하위 선택: <br/>레이어 소스, <br/>필터링, <br/>및 집계 | 하위 선택을 사용하여 레이어됨:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    dv1에서 \* 를 선택합니다.<br/>    여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>  ) \_<br/>  여기서 (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;의 \_.dim1)<br/>) 행을 참조하십시오<br/>그룹 기준 1<br/>합계별 주문</pre><br/>CTE를 사용하는 레이어:<br/><pre>(으)로 행 사용<br/>  WITH \_ AS(<br/>    DATA_ares에서 * SELECT<br/>    여기서 &#39;2021-01-01&#39;과 &#39;2021-02-01&#39; 사이의 \&#39;timestamp\&#39;<br/>  )<br/>  _.item, _.units FROM _<br/>  WHERE _.ITEM은 NULL이 아닙니다.<br/>)<br/>rows.item, SUM(rows.units) AS units 를 선택합니다.<br/>FROM 행 WHERE 행 (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)의 행.item<br/>rows.item별로 그룹화</pre> |
| 선택<br/>지표가 다음 전에<br/> 또는 이<br/>차원 | <pre>SUM(metric1) AS m1, dim1 선택<br/>DV1에서<br/>여기서 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의 \&#39;timestamp\&#39;<br/>그룹 기준 2</pre> |

{style="table-layout:auto"}

+++

### 차원

기본적으로 사용 가능한 차원 또는 데이터 보기에서 정의된 차원을 선택할 수 있습니다. 해당 ID로 차원을 선택합니다.

### 지표

선택할 수 있는 지표는 다음과 같습니다.

- 기본적으로 사용할 수 있는 지표 중 하나,

- 데이터 보기에 정의됨,

- 사용자가 액세스할 수 있는 데이터 보기와 호환되는 계산된 지표입니다.

래핑된 해당 ID로 지표를 선택합니다 `SUM(metric)` 다른 SQL 소스에서와 마찬가지로 표현식을 사용합니다.

다른 기준과 동일한 방식으로:

- `SELECT COUNT(*)` 또는 `COUNT(1)` 발생 횟수 지표를 가져올 수 있습니다.

- `SELECT COUNT(DISTINCT dimension)` 또는 `SELECT APPROX_COUNT_DISTINCT(dimension)` 차원의 대략적인 고유 값을 카운트하려면 자세한 내용은 [차이점 계산](#counting-distincts).

- [인라인 계산](#inline-calculations) 지표를 즉시 결합하거나 계산하기 위해.

#### 차이점 계산

CJA 작동 방식의 기본 특성으로 인해 다음과 같은 정확한 고유 카운트를 얻을 수 있는 유일한 차원은 입니다 `adobe_personid` 차원. 다음 SQL 문 `SELECT COUNT(DISTINCT adobe_personid)` 또는 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` 고유 방문자 수를 나타내는 기본 방문자 지표의 값을 반환합니다. 다른 차원의 경우 대략적인 고유 카운트가 반환됩니다.

#### 조건부 지표

를 포함할 수 있습니다 `IF` 또는 `CASE` 의 조항 `SUM` 또는 `COUNT` 선택한 지표에만 해당하는 추가 필터링을 추가하는 함수입니다. 이러한 절을 추가하는 것은 Workspace 보고서 테이블의 지표 열에 필터를 적용하는 것과 비슷합니다.

예:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 인라인 계산

의 지표 표현식에 를 추가로 적용할 수 있습니다 `SELECT` 계산된 지표에 수학이 정의된 대신 다음 표에는 지원되는 표현식 유형이 나열되어 있습니다.

| 연산자 또는 함수 | 세부 사항 |
|---|---|
| `+`, `-`, `*`, `/`, 및 `%` | 추가, 빼기, 곱하기, 나누기 및 모던스/잔부 |
| `-X` 또는 `+X` | X가 지표 표현식인 기호 또는 지표 변경 |
| `PI()` | 파이 |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`, 및 `TANH` | 단항 수학 함수 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 이진 수학 함수 |

{style="table-layout:auto"}

### 특수 열

**타임스탬프**

다음 `timestamp` 특수 열은 쿼리의 날짜 범위를 제공하는 데 사용됩니다. 날짜 범위는 `BETWEEN` 식 또는 한 쌍의 `timestamp` `>`, `>=`, `<`, `<=` check `AND`함께
다음 `timestamp` 은 선택 사항이며 전체 범위가 제공되지 않으면 기본값이 사용됩니다.

- 최소값만 제공된 경우(`timestamp > X` 또는 ` timestamp >= X`) 범위의 범위가 X부터 지금부터 이제까지입니다.

- 최대값만 제공된 경우(`timestamp < X` 또는 `timestamp <= X`) 범위의 값은 X-30일에서 X까지 입니다.

- 제공된 것이 없으면 범위는 지금부터 30일 사이입니다.

타임스탬프 범위가 RankedRequest의 날짜 범위 글로벌 필터로 변환됩니다.
타임스탬프 필드는 Date-Time 함수에서 사용하여 이벤트 타임스탬프를 구문 분석하고 자를 수도 있습니다.

**날짜 범위**

다음 `daterange` 특수 열은  `timestamp`하지만 필터링은 전체 날짜로 제한됩니다. 다음 `daterange` 도 선택 사항이며, 다음과 같은 범위 기본값이 있습니다. `timestamp`.
다음 `daterange` 날짜-시간 함수에서 필드를 사용하여 이벤트 날짜를 구문 분석하고 자를 수도 있습니다.

**filterId**

다음 `filterId` 특수 열은 선택 사항이며 외부에서 정의된 필터를 쿼리에 적용하는 데 사용됩니다. 외부에서 정의한 필터를 쿼리에 적용하는 것은 Workspace에서 패널에서 필터를 드래그하는 것과 비슷합니다. 여러 필터 ID는 `AND`&quot;그들을 죽입니다.

### WHERE 절

WHERE 절은 다음 세 단계로 처리됩니다.

1. 다음에서 날짜 범위를 찾습니다. `timestamp` 특수 필드.

2. 외부에서 정의된 항목 찾기 `filterId`필터링에 포함할 입니다.

3. 나머지 표현식을 임시 필터로 변환합니다.

처리는 의 첫 번째 수준을 구문 분석하여 수행됩니다 `AND`에서 `WHERE` 절. 각 최상위 수준 `AND`ed 표현식은 위의 표현식 중 하나와 일치해야 합니다. 첫 번째 수준 이상의 `AND`s, 또는, `WHERE` 조항 사용 `OR`최상위 수준에서 은 임시 필터로 처리됩니다.

### 정렬 기준

기본적으로 쿼리는 결과를 내림차순으로 선택한 첫 번째 지표 별로 정렬합니다. 다음을 지정하여 기본 정렬 순서를 덮어쓸 수 있습니다 `ORDER BY ... ASC` 또는 `ORDER BY ... DESC`. 만약 `ORDER BY`, 을 지정해야 합니다 `ORDER BY` 을 입력합니다.

또한 `-` 지표 앞에 (빼기) 있습니다. 아래의 두 문 모두 동일한 순서가 됩니다.

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 일반 기능 지원

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [캐스트(열 AS 유형)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 또는 <br/> `` `timestamp`::string `` | 형식 캐스팅은 현재 지원되지 않지만 오류가 발생하지 않습니다. 다음 `CAST` 함수가 무시됩니다. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 시간 문자열을 타임스탬프로 구문 분석하여 `WHERE` 절. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 시간 문자열을 타임스탬프로 구문 분석하여 `WHERE` 절, 선택적으로 해당 시간 문자열에 대한 형식을 제공합니다. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 날짜 문자열을 다음 내에서 사용할 타임스탬프로 구문 분석 `WHERE` 절. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 날짜 문자열을 다음 내에서 사용할 타임스탬프로 구문 분석 `WHERE` 절, 선택적으로 해당 날짜 문자열에 대한 형식을 제공합니다. |

{style="table-layout:auto"}

### Dimension 기능 지원

이러한 함수는 `SELECT`, `WHERE` 절 또는 조건부 지표에 있습니다.

**문자열 함수**

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 전달된 필드에 동적 차원 ID를 생성합니다. |

{style="table-layout:auto"}

**날짜-시간 함수**

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [YEAR(날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [MONTH(날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [DAY(날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [DAYOFWEEK(날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 값 대신 항목 ID를 사용하십시오. |
| [DAYOFYEAR(날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [주(날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [분기(날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [시간(날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 값 대신 항목 ID를 사용하십시오. |
| [MINUTE(날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [EXTRACT(부품 FROM 날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 이 함수의 일부 부분에 대한 값 대신 항목 ID를 사용하십시오.<br/>지원되는 부품은 다음과 같습니다.<br>- 키워드: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- 문자열: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, 또는 `'MINUTE'`. |
| [DATE_PART(부품, 날짜 또는 날짜 시간)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 이 함수의 일부 부분에 대한 값 대신 항목 ID를 사용하십시오.<br/>지원되는 문자열 부분은 다음과 같습니다. `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, 또는 `'MINUTE'`. |
| [DATE_TRUNC(세부기간, 날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다.<br/>지원되는 문자열 세부기간: `'YEAR'`, ``Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, 또는 `'MINUTE'`. |

{style="table-layout:auto"}

