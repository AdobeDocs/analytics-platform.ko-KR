---
title: SQL 커넥터
description: Query Service, Power BI 및/또는 Tableau를 사용하여 SQL 커넥터를 통해 데이터 보기에 액세스하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
exl-id: 1827a637-6c0f-43f2-862a-928089340d30
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '2789'
ht-degree: 99%

---

# SQL 커넥터

{{release-limited-testing}}

{{select-package}}

[!DNL Customer Journey Analytics SQL Connector]를 통해 SQL은 Customer Journey Analytics에서 정의한 [데이터 보기](./data-views.md)에 액세스할 수 있습니다. 데이터 엔지니어와 분석가는 Power BI, Tableau 또는 기타 비즈니스 인텔리전스 및 시각화 도구(BI 도구라고도 함)에 더 익숙할 수 있습니다. 이제 Customer Journey Analytics 사용자가 Analysis Workspace 프로젝트를 생성할 때 사용하는 것과 동일한 데이터 보기를 기반으로 보고 및 대시보드를 만들 수 있습니다.

Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html)는 Experience Platform의 데이터 레이크에서 사용 가능한 데이터에 대한 SQL 인터페이스입니다. [!DNL Customer Journey Analytics SQL Connector]를 활성화하면 Customer Journey Analytics 데이터 보기를 [!DNL Query Service] 세션의 테이블 또는 보기로 볼 수 있도록 [!DNL Query Service] 기능이 확장됩니다. 따라서 [!DNL Query Service]를 PostgresSQL 인터페이스로 사용하는 비즈니스 인텔리전스 도구는 이러한 확장 기능을 통해 원활하게 이점을 누릴 수 있습니다.

주요 이점은 다음과 같습니다.

- BI 도구 자체 내에서 Customer Journey Analytics 데이터 보기의 동등한 표시를 다시 만들 필요가 없습니다. <br/>데이터 보기의 기능에 대한 자세한 내용은 [데이터 보기](data-views.md)를 참조하여 재생성해야 하는 내용을 알아보십시오.<br/>

- BI 도구와 Customer Journey Analytics 간의 보고 및 분석 일관성이 향상되었습니다.

- Customer Journey Analytics 데이터를 이미 BI 도구에서 사용할 수 있는 다른 데이터 소스와 결합합니다.

## 사전 요구 사항

이 기능을 사용하려면 다음을 수행해야 합니다.

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- 관련 제품 프로필, 사용자 그룹 및/또는 개별 사용자의 기능을 구성합니다.<br/>
사용자는 다음 항목에 액세스할 수 있어야 합니다.
   - Experience Platform Query Service,
   - Customer Journey Analytics Workspace 프로젝트 및
   - 사용하려는 Customer Journey Analytics 데이터 보기.

- 만료되지 않는 자격 증명에 대한 만료를 사용하여 BI 도구를 Customer Journey Analytics SQL 커넥터에 연결합니다. [자격 증명 안내서](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html)에서는 만료될 예정인 자격 증명 또는 만료되지 않은 자격 증명 설정에 대한 자세한 정보를 제공합니다.

자세한 내용은 Customer Journey Analytics 관리 섹션의 [액세스 제어](../admin/cja-access-control.md)를 참조하십시오.


## 사용

[!DNL Customer Journey Analytics SQL Connector] 기능을 사용하려면 SQL을 직접 사용하거나 특정 BI 도구에서 사용 가능한 드래그 앤 드롭 경험을 사용할 수 있습니다.

### SQL

쿼리 편집기나 표준 PostgresSQL 명령줄 인터페이스(CLI) 클라이언트를 사용하여 SQL 문에서 직접 기능을 사용할 수 있습니다.

+++ 쿼리 편집기

Experience Platform UI에서 다음을 수행합니다.

1. 왼쪽 레일의 **[!UICONTROL **&#x200B;데이터 관리&#x200B;**]**&#x200B;에서 **[!UICONTROL **&#x200B;쿼리&#x200B;**]**&#x200B;를 선택합니다.

2. ![쿼리 만들기](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;쿼리 만들기&#x200B;**]**&#x200B;를 선택합니다.

3. 쿼리를 실행하려면 SQL 문을 입력하고 ![재생](assets/Smock_Play_18_N.svg) 버튼을 선택합니다(또는 SHIFT + ENTER 누르기).

+++


+++ PostgresSQL CLI

1. Experience Platform UI에서 PostgresSQL 자격 증명을 찾아 복사합니다.

   1. 왼쪽 레일에서 **[!UICONTROL **&#x200B;쿼리&#x200B;**]**&#x200B;를 선택합니다(**[!UICONTROL **&#x200B;데이터 관리&#x200B;**]** 아래).

   2. 상단 막대에서 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]**&#x200B;을 선택합니다.

   3. 연결 문자열을 복사하려면 **[!UICONTROL ** PSQL 명령&#x200B;**]** 섹션의 ![복사](assets/Smock_Copy_18_N.svg)를 사용합니다.

2. PostgresSQL CLI를 엽니다.

3. 로그인하여 쿼리 실행을 시작하려면 PostgresSQL CLI에 연결 문자열을 붙여넣습니다.

+++

자세한 내용은 [Query Editor UI 안내서](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=ko)를 참조하십시오.


### BI 도구

현재 Customer Journey Analytics SQL 커넥터는 Power BI 및 Tableau에서만 지원되고 테스트됩니다. PSQL 인터페이스를 사용하는 다른 BI 도구에서도 작동할 수 있지만, 아직 공식적으로 지원되지는 않습니다.

+++ Power BI

1. Adobe Experience Platform UI에서 PostgresSQL 자격 증명의 세부 정보를 찾습니다.

   1. 왼쪽 레일에서 **[!UICONTROL **&#x200B;쿼리&#x200B;**]**&#x200B;를 선택합니다(**[!UICONTROL **&#x200B;데이터 관리&#x200B;**]** 아래).

   2. 상단 막대에서 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]**&#x200B;을 선택합니다.

   3. Power BI에서 필요한 경우 ![복사](assets/Smock_Copy_18_N.svg)를 사용하여 각 Postgres 자격 증명 매개변수([!UICONTROL 호스트], [!UICONTROL 포트], [!UICONTROL 데이터베이스], [!UICONTROL 사용자 이름] 및 기타)를 복사합니다.

2. Power BI에서 다음을 수행합니다.

   1. 기본 창의 상단 도구 모음에서 **[!UICONTROL **&#x200B;데이터 내보내기&#x200B;**]**&#x200B;를 선택합니다.

   2. 왼쪽 레일에서 **[!UICONTROL **&#x200B;자세히...**]**&#x200B;를 선택합니다.

   3. **데이터 가져오기** 화면에서 `PostgresSQL`을 검색하고 해당 목록에서 **[!UICONTROL ** PostgresSQL 데이터베이스&#x200B;**]**&#x200B;를 선택합니다.

   4. **[!UICONTROL ** PostgressSQL 데이터베이스&#x200B;**]** 대화 상자에서 다음을 수행합니다.

      1. Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL **&#x200B;호스트&#x200B;**]** 매개변수를 **[!UICONTROL **&#x200B;서버&#x200B;**]** 텍스트 필드에 붙여넣습니다.

      2. **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 텍스트 필드의 Experience Platform 쿼리 [!UICONTROL 자격 증명]에서 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개변수를 붙여넣습니다.

         예를 들어 `prod:cja?FLATTEN`처럼 읽히도록 `?FLATTEN`을 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개변수에 추가합니다. 자세한 내용은 [서드파티 BI 도구와 함께 사용할 수 있도록 중첩 데이터 구조 평면화](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html)를 참조하십시오.

      3. **[!UICONTROL **&#x200B;데이터 연결&#x200B;**]** 모드를 묻는 메시지가 나타나면 **[!UICONTROL ** DirectQuery **]**&#x200B;를 선택하여 데이터 구조가 제대로 평면화되었는지 확인합니다.

      4. **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** 및 **[!UICONTROL **&#x200B;암호&#x200B;**]**&#x200B;를 묻는 메시지가 표시됩니다. Experience Platform 쿼리 [!UICONTROL 자격 증명]의 동등한 매개변수 사용


   5. 로그인에 성공하면 Power BI의 **[!UICONTROL **&#x200B;탐색기&#x200B;**]**&#x200B;에 Customer Journey Analytics 데이터 보기 테이블이 표시됩니다. 이름에 `dv_`를 사용하여 데이터 보기 테이블을 식별합니다.


   6. 사용할 데이터 보기 테이블을 선택하고 **[!UICONTROL **&#x200B;로드&#x200B;**]**&#x200B;를 선택합니다

   하나 이상의 선택한 테이블과 연결된 모든 차원 및 지표가 오른쪽 창에 표시되어 시각화에 사용할 수 있습니다.

   자세한 내용은 [Power BI를 Query Service에 연결](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html)을 참조하십시오.

+++

+++Tableau

1. Experience Platform UI에서 PostgresSQL 자격 증명의 세부 정보를 찾습니다.

   1. 왼쪽 레일에서 **[!UICONTROL **&#x200B;쿼리&#x200B;**]**&#x200B;를 선택합니다(**[!UICONTROL **&#x200B;데이터 관리&#x200B;**]** 아래).

   2. 상단 막대에서 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]**&#x200B;을 선택합니다.

   3. Tableau에서 필요한 경우 ![복사](assets/Smock_Copy_18_N.svg)를 사용하여 각 Postgres 자격 증명 매개변수([!UICONTROL 호스트], [!UICONTROL 포트], [!UICONTROL 데이터베이스], [!UICONTROL 사용자 이름] 및 기타)를 복사합니다.

2. Tableau에서 다음을 수행합니다.

   1. 왼쪽 레일의 **[!UICONTROL **&#x200B;서버로&#x200B;**]**&#x200B;에서 **[!UICONTROL **&#x200B;자세히&#x200B;**]**&#x200B;를 선택합니다.

   2. 목록에서 **[!UICONTROL ** PostgresSQL **]**&#x200B;을 선택합니다.

   3. [!UICONTROL PostgresSQL] 대화 상자에서 다음을 수행합니다.

      1. Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL **&#x200B;호스트&#x200B;**]** 매개변수를 **[!UICONTROL **&#x200B;서버&#x200B;**]** 텍스트 필드에 붙여넣습니다.

      2. Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL **&#x200B;포트&#x200B;**]** 매개변수를 **[!UICONTROL **&#x200B;포트&#x200B;**]** 텍스트 필드에 붙여넣습니다.

      3. **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 텍스트 필드에 Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개변수를 붙여넣습니다.

         예를 들어 `prod:cja%3FFLATTEN`처럼 읽히도록 `%3FFLATTEN`을 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개변수에 추가합니다. 자세한 내용은 [서드파티 BI 도구와 함께 사용할 수 있도록 중첩 데이터 구조 평면화](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html)를 참조하십시오.

      4. **[!UICONTROL **&#x200B;인증&#x200B;**]** 목록에서 **[!UICONTROL **&#x200B;사용자 이름 및 암호&#x200B;**]**&#x200B;를 선택합니다.

      5. **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** 텍스트 필드에 Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** 매개변수를 붙여넣습니다.

      6. **[!UICONTROL **&#x200B;암호&#x200B;**]** 텍스트 필드에 Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL **&#x200B;암호&#x200B;**]** 매개변수를 붙여넣습니다.

      7. **[!UICONTROL **&#x200B;로그인&#x200B;**]**&#x200B;을 선택합니다.

   4. Customer Journey Analytics 데이터 보기가 **[!UICONTROL **&#x200B;테이블&#x200B;**]** 목록에 테이블로 표시됩니다. 데이터 보기 테이블에는 앞에 `dv_`가 붙습니다.

   5. 사용하려는 테이블을 캔버스로 드래그합니다.

   이제 데이터 보기 테이블의 데이터를 사용하여 보고서 및 시각화를 빌드할 수 있습니다.

   자세한 내용은 [Query Service에 Tableau 연결](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html)을 참조하십시오.

+++

사용 가능한 다양한 도구에 대한 개요 및 자세한 내용은 [Query Service에 클라이언트 연결](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html)을 참조하십시오.

## 기능

기본적으로 데이터 보기에는 친숙한 이름에서 생성된 테이블 보안 이름이 있습니다. 예를 들어 [!UICONTROL My Web Data]라는 데이터 보기의 보기 이름은 `dv_my_web_data`입니다.

데이터 보기 ID를 테이블 이름으로 사용하려면 연결할 때 데이터베이스 이름에 옵션인 `CJA_USE_IDS` 설정을 추가할 수 있습니다. 예를 들어 `prod:all?CJA_USE_IDS`에는 `dv_ABC123`과 같은 데이터 보기가 표시됩니다.

### 데이터 거버넌스

Customer Journey Analytics의 데이터 거버넌스 관련 설정은 Adobe Experience Platform에서 상속됩니다. Customer Journey Analytics와 Adobe Experience Platform 데이터 거버넌스의 통합을 통해 중요한 Customer Journey Analytics 데이터에 레이블을 지정하고 개인정보 처리방침을 시행할 수 있습니다.

Experience Platform에서 사용하는 데이터 세트에 생성된 개인정보 보호 레이블 및 정책은 Customer Journey Analytics 데이터 보기 워크플로에 표시될 수 있습니다. 따라서 Customer Journey Analytics SQL 커넥터를 사용하여 쿼리한 데이터는 정의된 개인정보 보호 레이블 및 정책을 준수하지 않을 경우 적절한 경고 또는 오류를 표시합니다.

### 데이터 보기 나열

표준 PostgreSQL CLI에서 `\dv`를 사용하여 보기를 나열할 수 있음

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

### 중첩 및 평면화

기본적으로 데이터 보기의 스키마는 원래 XDM 스키마와 마찬가지로 중첩 구조를 사용합니다. 또한 통합은 `FLATTEN` 옵션을 지원합니다. 이 옵션을 사용하면 데이터 보기(및 세션의 다른 테이블)에 대한 스키마를 강제로 평면화할 수 있습니다. 평면화를 사용하면 구조화된 스키마를 지원하지 않는 BI 도구를 더 쉽게 사용할 수 있습니다. 자세한 내용은 [Query Service에서 중첩된 데이터 구조로 작업](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html)을 참조하십시오.

### 지원되는 SQL

지원되는 SQL 유형에 대한 전체 참조는 [Query Service SQL 참조](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html)를 확인하십시오.

사용할 수 있는 SQL의 예는 아래 테이블을 참조하십시오.

+++ 예

| 패턴 | 예 |
|---|---|
| 스키마 검색 | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| 등급 / 분류 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| HAVING 절 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| 고유, 상단 <br/>차원 값 | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| 지표 합계 | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| 다차원<br/>분류<br/>및 상단 고유 항목 | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| 하위 선택:<br/>추가 결과<br/>필터링 | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| 하위 선택:<br/>Customer Journey Analytics에 포함되지 않은 데이터 세트에 <br/>조인<br/> | <pre>SELECT b.key, a.dim1, a.m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/>) a<br/>LEFT JOIN lookups b ON a.dim1 = b.key</pre> |
| 하위 선택: 데이터 보기<br/>전체 쿼리<br/> | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| 하위 선택: <br/>계층 소스, <br/>필터링, <br/>및 집계 | 하위 선택을 사용하여 계층화됨:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>CTE WITH를 사용한 계층:<br/><pre>WITH rows AS (<br/>  WITH \_ AS (<br/>    SELECT * FROM data_ares<br/>    WHERE \`timestamp\` BETWEEN &#39;2021-01-01&#39; AND &#39;2021-02-01&#39;<br/>  )<br/>  SELECT _.item, _.units FROM _<br/>  WHERE _.item IS NOT NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FROM rows WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| 지표가 차원 <br/>앞에 있거나<br/> 혼합되는<br/>위치 선택 | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### 차원

기본적으로 사용 가능하거나 데이터 보기에 정의된 차원을 선택할 수 있습니다. ID로 차원을 선택합니다.

### 지표

선택할 수 있는 지표는 다음과 같습니다.

- 기본적으로 사용 가능한 지표.

- 데이터 보기에 정의되어 있음.

- 사용자가 액세스할 수 있는 데이터 보기와 호환되는 계산된 지표.

다른 SQL 소스에서와 마찬가지로 `SUM(metric)` 표현식으로 래핑된 ID를 기준으로 지표를 선택합니다.

다음을 수행할 수 있습니다.

- `SELECT COUNT(*)` 또는 `COUNT(1)`는 발생 횟수 지표를 얻습니다.

- `SELECT COUNT(DISTINCT dimension)` 또는 `SELECT APPROX_COUNT_DISTINCT(dimension)`는 차원의 대략적인 고유 값을 계산합니다. [고유값 카운트](#counting-distincts)에서 세부 사항을 확인하십시오.

- [인라인 계산](#inline-calculations)은 즉시 지표 및/또는 이에 대한 연산을 결합합니다.

#### 고유값 카운트

Customer Journey Analytics 작동 방식의 근본적인 특성 때문에 정확한 고유 카운트를 얻을 수 있는 유일한 차원은 `adobe_personid` 차원입니다. 다음 SQL 문 `SELECT COUNT(DISTINCT adobe_personid)` 또는 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)`는 고유 사용자의 수인 기본 사용자 지표의 값을 반환합니다. 다른 차원의 경우, 대략적인 고유 카운트가 반환됩니다.

#### 조건부 지표

`SUM` 또는 `COUNT` 함수에 `IF` 또는 `CASE` 절을 임베드하여 선택한 지표와 관련된 필터링을 추가할 수 있습니다. 이러한 절을 추가하는 것은 Workspace 보고서 테이블의 지표 열에 필터를 적용하는 것과 유사합니다.

예:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 인라인 계산

계산된 지표에 수학을 정의하는 대신 `SELECT`에 있는 지표 표현식을 추가로 적용할 수 있습니다. 다음 테이블에는 지원되는 표현식 유형이 나열되어 있습니다.

| 연산자 또는 함수 | 세부 사항 |
|---|---|
| `+`, `-`, `*`, `/` 및 `%` | 더하기, 빼기, 곱하기, 나누기 및 모듈러스/나머지 |
| `-X` 또는 `+X` | X가 지표 표현식인 기호 또는 지표 변경 |
| `PI()` | π 상수 |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` 및 `TANH` | 단항 수학 함수 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 이진 수학 함수 |

{style="table-layout:auto"}

### 특수 열

**타임스탬프**

`timestamp` 특수 열을 사용하여 쿼리의 날짜 범위를 제공합니다. 날짜 범위는 `BETWEEN` 표현식을 사용하거나 `timestamp` `>`, `>=`, `<`, `<=` 확인 `AND` 쌍을 함께 사용하여 정의할 수 있습니다.
`timestamp`는 옵션이며 전체 범위가 제공되지 않으면 기본값이 사용됩니다.

- 최소값만 제공되는 경우(`timestamp > X` 또는 ` timestamp >= X`), 범위는 X부터 지금까지입니다.

- 최대값만 제공되는 경우(`timestamp < X` 또는 `timestamp <= X`), 범위는 X-30일부터 X까지입니다.

- 아무것도 제공되지 않는 경우 범위는 지금부터 30일까지입니다.

타임스탬프 범위는 RankedRequest에서 날짜 범위 전역 필터로 변환됩니다.
타임스탬프 필드는 날짜-시간 함수에서 이벤트 타임스탬프를 구문 분석하고 자르는 데 사용될 수도 있습니다.

**날짜 범위**

`daterange` 특수 열은 `timestamp`와 유사하게 작동하나, 필터링은 하루 종일로 제한됩니다. `daterange`는 옵션이며 범위 기본값은 `timestamp`와 동일합니다.
`daterange` 필드를 사용하여 날짜-시간 함수에서 이벤트 날짜를 구문 분석하고 자를 수 있습니다.

**filterId**

`filterId` 특수 열은 옵션이며 외부에서 정의된 필터를 쿼리에 적용하는 데 사용됩니다. 외부에서 정의된 필터를 쿼리에 적용하는 것은 Workspace의 패널에서 필터를 드래그하는 것과 비슷합니다. 여러 필터 ID는 `AND`-ing로 제공할 수 있습니다.

### WHERE 절

WHERE 절은 세 단계로 처리됩니다.

1. `timestamp` 특수 필드에서 날짜 범위를 찾습니다.

2. 필터링에 포함할 외부에서 정의된 `filterId`를 찾습니다.

3. 나머지 표현식을 임시 필터로 전환합니다.

`WHERE` 절에서 `AND`의 첫 번째 수준을 구문 분석하여 처리됩니다. 각 최상위 `AND` 표현식은 위의 표현식 중 하나와 일치해야 합니다. `AND`의 첫 번째 수준보다 자세한 항목이거나 `WHERE` 절이 최상위 수준에서 `OR`을 사용하는 경우, 임시 필터로 처리됩니다.

### 주문 기준

기본적으로 쿼리는 처음 선택한 지표를 기준으로 내림차순으로 결과를 정렬합니다. `ORDER BY ... ASC` 또는 `ORDER BY ... DESC`를 지정하여 기본 정렬 순서를 덮어쓸 수 있습니다. `ORDER BY`를 사용하는 경우, 첫 번째 선택한 지표에서 `ORDER BY`를 지정해야 합니다.

지표 앞에 `-`(빼기)를 사용하여 순서를 뒤집을 수도 있습니다. 아래 두 명령문의 순서는 동일합니다.

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 일반 함수 지원

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [CAST(열 AS 유형)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 또는 <br/> `` `timestamp`::string `` | 유형 캐스팅은 현재 지원되지 않지만 오류는 발생하지 않습니다. `CAST` 함수는 무시됩니다. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | `WHERE` 절 내에서 사용할 타임스탬프로 시간 문자열을 구문 분석합니다. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 시간 문자열을 `WHERE` 절 내에서 사용할 타임스탬프로 구문 분석하고, 옵션으로 해당 시간 문자열에 대한 형식을 제공합니다. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | `WHERE` 절 내에서 사용할 타임스탬프로 날짜 문자열을 구문 분석합니다. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 날짜 문자열을 `WHERE` 절 내에서 사용할 타임스탬프로 구문 분석하고, 옵션으로 해당 날짜 문자열에 대한 형식을 제공합니다. |

{style="table-layout:auto"}

### 차원 함수 지원

이러한 함수는 `SELECT`, `WHERE` 절의 차원에서 사용하거나 조건부 지표에서 사용할 수 있습니다.

**문자열 함수**

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 전달된 필드에 동적 차원 ID를 생성합니다. |

{style="table-layout:auto"}

**날짜-시간 함수**

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [YEAR(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [MONTH(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [DAY(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [DAYOFWEEK(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 값 대신 항목 ID를 사용합니다. |
| [DAYOFYEAR(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [WEEK(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [QUARTER(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [HOUR(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 값 대신 항목 ID를 사용합니다. |
| [MINUTE(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [EXTRACT(날짜 또는 날짜-시간 부분)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 이 함수의 일부 부분에 대한 값 대신 항목 ID를 사용합니다.<br/>지원되는 항목:<br>- 키워드: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- 문자열:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` 또는 `'MINUTE'`. |
| [DATE_PART(부분, 날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 이 함수의 일부 부분에 대한 값 대신 항목 ID를 사용합니다.<br/>지원되는 문자열 항목: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` 또는 `'MINUTE'`. |
| [DATE_TRUNC(세부 기간, 날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다.<br/>지원되는 문자열 세부 기간: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` 또는 `'MINUTE'`. |

{style="table-layout:auto"}
