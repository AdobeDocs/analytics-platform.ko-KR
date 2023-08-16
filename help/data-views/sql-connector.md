---
title: SQL 커넥터
description: 쿼리 서비스, Power BI 및/또는 타블로를 사용하여 SQL 커넥터를 사용하여 데이터 보기에 액세스하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
exl-id: 80feadef-3e2d-4901-8c82-25c56d296e9f
source-git-commit: 7ae94bb46d542181c6438e87f204bd49c2128c8c
workflow-type: tm+mt
source-wordcount: '2938'
ht-degree: 1%

---

# SQL 커넥터

{{release-limited-testing}}

{{select-package}}

다음 [!DNL Customer Journey Analytics SQL Connector] 에 대한 SQL 액세스 활성화 [데이터 보기](./data-views.md) Customer Journey Analytics에서 정의했습니다. 데이터 엔지니어와 분석가는 Power BI, Tableau 또는 기타 비즈니스 인텔리전스 및 시각화 도구(BI 도구라고도 함)에 더 익숙할 수 있습니다. 이제 Customer Journey Analytics 사용자가 Analysis Workspace 프로젝트를 만들 때 사용하는 것과 동일한 데이터 보기를 기반으로 보고 및 대시보드를 만들 수 있습니다.

Adobe Experience Platform [쿼리 서비스](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ko-KR?lang=kr) 는 Experience Platform의 데이터 레이크에서 사용할 수 있는 데이터에 대한 SQL 인터페이스입니다. 포함 [!DNL Customer Journey Analytics SQL Connector] 활성화됨, 의 기능 [!DNL Query Service] 를 확장하여 Customer Journey Analytics 데이터 보기를 테이블 또는 뷰로 [!DNL Query Service] 세션. 따라서 다음을 사용하는 비즈니스 인텔리전스 도구 [!DNL Query Service] PostgresSQL 인터페이스가 이 확장된 기능을 원활하게 활용할 수 있습니다.

주요 이점은 다음과 같습니다.

- BI 도구 자체 내에서 Customer Journey Analytics 데이터 보기의 동등한 표현을 다시 만들 필요가 없습니다. <br/>다음을 참조하십시오 [데이터 보기](data-views.md) 를 참조하십시오.<br/>

- BI 도구와 Customer Journey Analytics 간 보고 및 분석의 일관성 향상.

- Customer Journey Analytics 데이터를 BI 도구에서 이미 사용 가능한 다른 데이터 소스와 결합합니다.

## 사전 요구 사항

이 기능을 사용하려면 다음을 수행해야 합니다

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- 관련 제품 프로필, 사용자 그룹 및/또는 개별 사용자에 대한 기능을 구성합니다.<br/>
사용자는 다음에 대한 액세스 권한이 있어야 합니다.
   - Experience Platform 쿼리 서비스,
   - Customer Journey Analytics 작업 공간 프로젝트 및
   - Customer Journey Analytics 데이터 보기를 사용할 수 있습니다.

- 만료되지 않는 자격 증명의 만료일을 사용하여 BI 도구를 Customer Journey Analytics SQL 커넥터에 연결합니다. Thr [자격 증명 안내서](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) 만료 자격 증명 또는 만료되지 않는 자격 증명 설정에 대한 자세한 내용을 제공합니다.

다음을 참조하십시오 [액세스 제어](../admin/cja-access-control.md) 자세한 내용은 Customer Journey Analytics 관리 섹션을 참조하십시오.


## 사용

을(를) 사용하려면 [!DNL Customer Journey Analytics SQL Connector] 기능을 사용하면 SQL을 직접 사용하거나 특정 BI 도구에서 사용할 수 있는 끌어서 놓기 환경을 사용할 수 있습니다.

### SQL

쿼리 편집기 또는 표준 PostgresSQL 명령줄 인터페이스(CLI) 클라이언트를 사용하여 SQL 문에서 직접 기능을 사용할 수 있습니다.

+++ 쿼리 편집기

Experience Platform UI에서

1. 선택 **[!UICONTROL **&#x200B;쿼리&#x200B;**]** 출처: **[!UICONTROL **&#x200B;데이터 관리&#x200B;**]** 왼쪽 레일에서.

2. 선택 ![쿼리 만들기](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;쿼리 만들기&#x200B;**]**.

3. 쿼리를 실행하려면 SQL 문을 입력하고 ![재생](assets/Smock_Play_18_N.svg) 단추(또는 Shift + Enter를 누름).

+++


+++ PostgresSQL CLI

1. Experience Platform UI에서 PostgresSQL 자격 증명을 조회하고 복사합니다.

   1. 선택 **[!UICONTROL **&#x200B;쿼리&#x200B;**]** 왼쪽 레일에서(아래) **[!UICONTROL **&#x200B;데이터 관리&#x200B;**]**).

   2. 선택 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]** 을 클릭합니다.

   3. 연결 문자열을 복사하려면 ![복사](assets/Smock_Copy_18_N.svg) 다음에서 **[!UICONTROL ** PSQL 명령&#x200B;**]** 섹션.

2. PostgresSQL CLI를 엽니다.

3. 로그인하여 쿼리 실행을 시작하려면 PostgresSQL CLI에 연결 문자열을 붙여넣습니다.

+++

다음을 참조하십시오 [쿼리 편집기 UI 안내서](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) 추가 정보.


### BI 도구

현재 Customer Journey Analytics SQL 커넥터는 Power BI 및 Tableau에 대해서만 지원 및 테스트됩니다. PSQL 인터페이스를 사용하는 다른 BI 도구도 작동할 수 있지만 아직 공식적으로 지원되지 않습니다.

+++ Power BI

1. Adobe Experience Platform UI에서 PostgresSQL 자격 증명의 세부 정보를 조회합니다.

   1. 선택 **[!UICONTROL **&#x200B;쿼리&#x200B;**]** 왼쪽 레일에서(아래) **[!UICONTROL **&#x200B;데이터 관리&#x200B;**]**).

   2. 선택 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]** 을 클릭합니다.

   3. Copy를 사용 ![ 하 여 POWER BI에서 필요한 경우 사후 Gres 자격 증명 매개 변수 ( [!UICONTROL  호스트 ] , [!UICONTROL  포트 ] , [!UICONTROL  데이터베이스 ] , [!UICONTROL  사용자 이름 ] 등)를 각각 복사 합니다. ](assets/Smock_Copy_18_N.svg)

2. Power BI에서:

   1. 기본 창의 상단 도구 모음에서 데이터 **]** 가져오기를 선택 **[!UICONTROL ** 합니다.

   2. 왼쪽 레일에서 [자세히 **]** ...]를 선택 **[!UICONTROL ** 합니다.

   3. 다음에서 **데이터 가져오기** 화면, 검색 `PostgresSQL` 및 선택 **[!UICONTROL ** PostgresSQL 데이터베이스&#x200B;**]** 목록에서 삭제할 수 있습니다.

   4. 다음에서 **[!UICONTROL ** PostgressSQL 데이터베이스&#x200B;**]** 대화 상자:

      1. 붙여넣기 **[!UICONTROL **&#x200B;호스트&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 대상 **[!UICONTROL **&#x200B;서버&#x200B;**]** 텍스트 필드.

      2. 붙여넣기 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 위치: **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 텍스트 필드.

         추가 `?FLATTEN` (으)로 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개 변수이므로 다음과 같이 읽음 `prod:all?FLATTEN` 예. 다음을 참조하십시오 [타사 BI 도구와 함께 사용할 중첩된 데이터 구조 평면화](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 추가 정보.

      3. 을 묻는 메시지가 표시되면 **[!UICONTROL **&#x200B;데이터 연결&#x200B;**]** 모드, 선택 **[!UICONTROL ** DirectQuery **]** 데이터 구조가 올바르게 병합되도록 합니다.

      4. 을 묻는 메시지가 표시됩니다. **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** 및 **[!UICONTROL **&#x200B;암호&#x200B;**]**. Experience Platform 쿼리에서 동등한 매개 변수 사용 [!UICONTROL 자격 증명].


   5. 로그인에 성공하면 Customer Journey Analytics 데이터 보기 테이블이 Power BI의 **[!UICONTROL **&#x200B;네비게이터&#x200B;**]**. 데이터 보기 테이블은 다음을 사용하여 식별됩니다 `dv_` 그들의 이름으로.


   6. 사용할 데이터 보기 테이블을 선택하고 **[!UICONTROL **&#x200B;로드&#x200B;**]**.

   하나 이상의 선택한 테이블과 연관된 모든 차원 및 지표가 오른쪽 창에 표시되어 시각화에 사용할 수 있습니다.

   다음을 참조하십시오 [쿼리 서비스에 Power BI 연결](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) 추가 정보.

+++

+++Tableau

1. Experience Platform UI에서 PostgresSQL 자격 증명의 세부 정보를 조회합니다.

   1. 선택 **[!UICONTROL **&#x200B;쿼리&#x200B;**]** 왼쪽 레일에서(아래) **[!UICONTROL **&#x200B;데이터 관리&#x200B;**]**).

   2. 선택 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]** 을 클릭합니다.

   3. 사용 ![복사](assets/Smock_Copy_18_N.svg) 각 Postgres 자격 증명 매개 변수를 복사하려면([!UICONTROL 호스트], [!UICONTROL 포트], [!UICONTROL 데이터베이스], [!UICONTROL 사용자 이름]및 기타)를 사용할 수 있습니다.

2. 타블로의 경우:

   1. 선택 **[!UICONTROL **&#x200B;자세히&#x200B;**]** 출처: **[!UICONTROL **&#x200B;서버에&#x200B;**]** 왼쪽 레일에서.

   2. 선택 **[!UICONTROL ** PostgresSQL **]** 목록에서 삭제할 수 있습니다.

   3. 다음에서 [!UICONTROL PostgresSQL] 대화 상자:

      1. 붙여넣기 **[!UICONTROL **&#x200B;호스트&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 대상 **[!UICONTROL **&#x200B;서버&#x200B;**]** 텍스트 필드.

      2. 붙여넣기 **[!UICONTROL **&#x200B;포트&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 대상 **[!UICONTROL **&#x200B;포트&#x200B;**]** 텍스트 필드.

      3. 붙여넣기 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 대상 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 텍스트 필드.

         추가 `%3FFLATTEN` (으)로 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개 변수이므로 다음과 같이 읽음 `prod:all%3FFLATTEN` 예. 다음을 참조하십시오 [타사 BI 도구와 함께 사용할 중첩된 데이터 구조 평면화](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 추가 정보.

      4. 선택 **[!UICONTROL **&#x200B;사용자 이름 및 암호&#x200B;**]** 출처: **[!UICONTROL **&#x200B;인증&#x200B;**]** 목록을 표시합니다.

      5. 붙여넣기 **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** Experience Platform 쿼리의 매개 변수 [!UICONTROL 자격 증명] 대상 **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** 텍스트 필드.

      6. 암호 **]** 매개 변수를 Experience Platform 쿼리 [!UICONTROL  자격 증명 **[!UICONTROL ** ] 에서 암호 **]** 텍스트 필드로 붙여넣기 **[!UICONTROL ** 합니다.

      7. 로그인 **]** 을 선택 **[!UICONTROL ** 합니다.

   4. Customer Journey Analytics 데이터 보기는 **[!UICONTROL ** 테이블 **]** 목록에 테이블로 표시 됩니다. 데이터 뷰 테이블에는 접두사가 사용 `dv_` 됩니다.

   5. 사용 하려는 테이블을 캔버스에서 드래그 합니다.

   이제 데이터 보기 테이블의 데이터로 작업 하 여 보고서 및 시각화를 빌드 수 있습니다.

   다음을 참조하십시오 [쿼리 서비스에 타블로 연결](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) 추가 정보.

+++

다음을 참조하십시오 [클라이언트를 쿼리 서비스에 연결](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) 사용 가능한 다양한 도구에 대한 개요와 추가 정보입니다.

## 기능

기본적으로 데이터 보기에는 친숙한 이름에서 생성된 테이블 안전 이름이 있습니다. (예: 이름이 인 데이터 보기) [!UICONTROL 내 웹 데이터] 보기 이름 있음 `dv_my_web_data`.

데이터 보기 ID를 테이블 이름으로 사용하려면 선택 사항을 추가할 수 있습니다 `CJA_USE_IDS` 연결할 때 데이터베이스 이름으로 설정합니다. 예를 들어, `prod:all?CJA_USE_IDS` 다음과 같은 이름으로 데이터 보기를 표시합니다. `dv_ABC123`.

### 데이터 거버넌스

Customer Journey Analytics의 데이터 거버넌스 관련 설정은 Adobe Experience Platform에서 상속됩니다. Customer Journey Analytics과 Adobe Experience Platform 데이터 거버넌스 간의 통합을 통해 민감한 Customer Journey Analytics 데이터의 레이블 지정 및 개인정보 처리방침 시행을 수행할 수 있습니다.

Experience Platform이 사용하는 데이터 세트에 생성된 개인정보 보호 레이블 및 정책은 Customer Journey Analytics 데이터 보기 워크플로우에 표시될 수 있습니다. 따라서 Customer Journey Analytics SQL Connector를 사용하여 쿼리한 데이터는 정의된 개인 정보 레이블 및 정책을 준수하지 않을 때 적절한 경고 또는 오류를 표시합니다.

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

### 중첩 및 병합

기본적으로 데이터 보기의 스키마는 원래 XDM 스키마와 마찬가지로 중첩된 구조를 사용합니다. 통합은 `FLATTEN` 옵션을 선택합니다. 이 옵션을 사용하여 데이터 보기(및 세션의 다른 테이블)에 대한 스키마를 강제 병합할 수 있습니다. 병합을 사용하면 구조화된 스키마를 지원하지 않는 BI 도구를 보다 쉽게 사용할 수 있습니다. 다음을 참조하십시오 [쿼리 서비스에서 중첩 데이터 구조 작업](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 추가 정보.

### 지원되는 SQL

다음을 참조하십시오 [쿼리 서비스 SQL 참조](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) 지원되는 SQL 유형에 대한 전체 참조.

사용할 수 있는 SQL의 예는 아래 표를 참조하십시오.

+++ 예

| 패턴 | 예 |
|---|---|
| 스키마 검색 | <pre>SELECT * FROM dv1 (WHERE 1 = 0)</pre> |
| 등급/분류 | <pre>Dim1, SUM (metric1)를 &#39; 2022-01-01 &#39; 및 &#39; 2022-01-02 &#39; <br/> 그룹 간 dim1에서 M1 <br/> 으로 dv1 <br/></pre><pre>Dim1, SUM (metric1) <br/> 를 &#39; 2022-01-01 &#39; 및 &#39; 2022-01-02 &#39; 및 <br/> filterid = &#39; 12345 &#39; <br/> GROUP BY dim1에서 dv1 <br/> .</pre><pre>dim1, SUM(metric1) 을 M1로 선택합니다.<br/>DV1에서<br/>여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의<br/>  AND (dim2 = &#39;A&#39; 또는 DIM3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>DIM1로 그룹화</pre> |
| HAVING 절 | <pre>dim1, SUM(metric1) 을 M1로 선택합니다.<br/>DV1에서<br/>여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의<br/>DIM1로 그룹화<br/>M1 > 100 사용</pre> |
| 고유, 상단 <br/>차원 값 | <pre>DV1에서 개별 DIM1 선택</pre><pre>dim1 AS dv1 선택<br/>DV1에서<br/>여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의<br/>DIM1로 그룹화</pre><pre>dim1 AS dv1 선택<br/>DV1에서<br/>여기서 \`timestamp\` >= &#39;2022-01-01&#39; 및 \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>DIM1로 그룹화<br/>합계별 정렬(metric1)<br/>제한 15</pre> |
| 지표 합계 | <pre>SUM(metric1) 을 M1 로 선택합니다.<br/>DV1에서<br/>여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의</pre> |
| 다차원<br/>분류<br/>및 상위 차이점 | <pre>dim1, dim2, SUM(metric1) 을 m1로 선택합니다.<br/>DV1에서<br/>여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의<br/>GROUP BY DIM1, dim2</pre><pre>dim1, dim2, SUM(metric1) 을 m1로 선택합니다.<br/>DV1에서<br/>여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의<br/>그룹화 기준 1, 2<br/>정렬 기준: 1, 2</pre><pre>고유 치수1, 치수2 선택<br/>DV1에서</pre> |
| 하위 선택:<br/>추가 결과<br/>필터링 | <pre>dim1, m1 선택<br/>출처: (<br/>  dim1, SUM(metric1) 을 M1로 선택합니다.<br/>  DV1에서<br/>  여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의</br>  DIM1로 그룹화<br/>)<br/>위치 dim1(&#39;A&#39;, &#39;B&#39;)</pre> |
| 하위 선택:<br/>다음으로 가입<br/>데이터 세트가 다음에 없음<br/>Customer Journey Analytics | <pre>b.key, a.dim1, a.m1 선택<br/>출처: (<br/>  dim1, SUM(metric1) 을 M1로 선택합니다.<br/>  DV1에서<br/>  여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의<br/>  DIM1로 그룹화<br/>) a<br/>a.dim1 = b.key의 LEFT JOIN 조회 b</pre> |
| 하위 선택:<br/>쿼리 대상<br/>데이터 보기 | <pre>키, SUM(m1)을 합계로 선택<br/>출처: (<br/>  DIM1을 키로, SUM(metric1)을 M1로 선택합니다.<br/>  DV1에서<br/>  여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의<br/>  DIM1로 그룹화<br/><br/>  결합<br/><br/>  DIM2를 키로, SUM(m1)을 m1로 선택<br/>  DV2에서<br/>  여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의<br/>  DIM2로 그룹화<br/>키로 그룹화<br/>합계별 주문</pre> |
| 하위 선택: <br/>계층화된 소스, <br/>필터링, <br/>및 집계 | 하위 선택을 사용하여 계층화:<br><pre>rows.dim1, SUM(rows.m1)을 합계로 선택합니다.<br/>출처: (<br/>  \_.dim1,\_.m1 선택<br/>  출처: (<br/>    DV1에서 \* 선택<br/>    여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의<br/>  ) \_<br/>  여기서 \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) 행<br/>그룹화 기준 1<br/>합계별 주문</pre><br/>CTE를 사용하는 레이어:<br/><pre>((으)로 행 포함<br/>  \_ AS (<br/>    DATA_ARES에서 * 선택<br/>    여기서 \`timestamp\`는 &#39;2021-01-01&#39;과 &#39;2021-02-01&#39; 사이입니다.<br/>  )<br/>  _에서 _.item, _.units 선택<br/>  여기서 _.item 은 NULL 이 아닙니다.<br/>)<br/>rows.item, SUM(rows.units)을 단위로 선택<br/>(&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)의 rows.item이 있는 행에서<br/>행별 그룹화.항목</pre> |
| 다음 위치를 선택합니다.<br/>다음 항목 앞에 지표 표시<br/> 또는 와 혼합되어 있습니다.<br/>차원 | <pre>SUM(metric1) 을 M1, dim1로 선택합니다.<br/>DV1에서<br/>여기서 \`timestamp\`는 &#39;2022-01-01&#39;과 &#39;2022-01-02&#39; 사이의<br/>그룹화 기준 2</pre> |

{style="table-layout:auto"}

+++

### 차원

기본적으로 사용할 수 있거나 데이터 보기에서 정의된 차원을 선택할 수 있습니다. ID로 차원를 선택 합니다.

### 지표

선택할 수 있는 지표는 다음과 같습니다.

- 기본적으로 사용 가능한 모든 지표

- 데이터 보기에서 정의 된

- 사용자가 액세스할 수 있는 데이터 보기와 호환되는 계산된 지표입니다.

에 래핑된 ID로 지표를 선택합니다. `SUM(metric)` 다른 SQL 소스를 사용하는 것과 같은 표현식.

다른 기준과 동일한 방식으로:

- `SELECT COUNT(*)` 또는 `COUNT(1)` 발생 횟수 지표를 가져옵니다.

- `SELECT COUNT(DISTINCT dimension)` 또는 `SELECT APPROX_COUNT_DISTINCT(dimension)` 을 눌러 차원의 근사 고유 값을 계산합니다. 자세한 내용은에서 참조하십시오. [계산 차이점](#counting-distincts).

- [인라인 계산](#inline-calculations) 즉석으로 지표를 결합하고/하거나 지표에 대해 수학을 수행합니다.

#### 계산 차이점

Customer Journey Analytics 작동 방식의 기본 특성으로 인해 정확한 고유 카운트를 얻을 수 있는 유일한 차원은 입니다. `adobe_personid` 차원. 다음 SQL 문 `SELECT COUNT(DISTINCT adobe_personid)` 또는 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` 고유 사용자의 수인 기본 사용자 지표의 값을 반환합니다. 다른 차원의 경우 대략적인 고유 수가 반환됩니다.

#### 조건부 지표

다음을 포함할 수 있습니다. `IF` 또는 `CASE` 의 절 `SUM` 또는 `COUNT` 함수 를 사용하여 선택한 지표와 관련된 필터링을 추가합니다. 이 절을 추가하는 것은 작업 영역 보고서 테이블의 지표 열에 필터를 적용하는 것과 비슷합니다.

예:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 인라인 계산

의 지표 표현식에 추가 를 적용할 수 있습니다. `SELECT` 계산된 지표에 수학을 정의하는 대신. 다음 표에는 지원되는 표현식 유형이 나와 있습니다.

| 연산자 또는 함수 | 세부 사항 |
|---|---|
| `+`, `-`, `*`, `/`, 및 `%` | 더하기, 빼기, 곱하기, 나누기 및 모듈형/나머지 |
| `-X` 또는 `+X` | X가 지표 표현식인 기호 또는 지표 변경 |
| `PI()` | π 상수 |
| `POSITIVE`, `NEGATIVE` , `ABS` `FLOOR` `CEIL` ,,,, `CEILING` , `EXP` ,, `LOG1P` `COSH` `TAN` `COS` `ACOS` `SIN` `ASIN` `ATAN` `LN` `SQRT` `SINH` `LOG10` `CBRT` `DEGREES` `RADIANS` ,,,,,,,,,,,,,,,,,,,,,,,, 및`TANH` | 단항 수학 함수 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 이진 수학 함수 |

{style="table-layout:auto"}

### 특수 열

**타임스탬프**

다음 `timestamp` 특수 열은 쿼리에 대한 날짜 범위를 제공하는 데 사용됩니다. 날짜 범위는 다음을 사용하여 정의할 수 있습니다 `BETWEEN` 표현식 또는 쌍 `timestamp` `>`, `>=`, `<`, `<=` 확인 `AND`함께 에드.
다음 `timestamp` 는 선택 사항이며 전체 범위를 제공하지 않으면 기본값이 사용됩니다.

- 최소값만 제공되는 경우(`timestamp > X` 또는 ` timestamp >= X`), 범위는 X부터 지금까지입니다.

- 최대값만 제공되는 경우 (`timestamp < X` 또는 `timestamp <= X`), 범위는 X-30일에서 X까지입니다.

- 아무 것도 제공되지 않는 경우 범위는 지금부터 30일 사이입니다.

타임스탬프 범위는 RankedRequest에서 날짜 범위 전역 필터로 변환됩니다.
타임스탬프 필드는 이벤트 타임스탬프를 구문 분석하고 자르는 날짜-시간 함수에서도 사용할 수 있습니다.

**날짜 범위**

다음 `daterange` 특수 열은 다음과 유사하게 작동합니다.  `timestamp`, 하지만 필터링은 전체 날짜로 제한됩니다. 다음 `daterange` 는 또한 선택 사항이며 과 동일한 범위 기본값을 갖습니다. `timestamp`.
다음 `daterange` 날짜-시간 함수에서 필드를 사용하여 이벤트 날짜를 구문 분석하고 자를 수도 있습니다.

**filterId**

다음 `filterId` 특수 열은 선택 사항이며 외부에서 정의한 필터를 쿼리에 적용하는 데 사용됩니다. 외부에서 정의된 필터를 쿼리에 적용하는 것은 작업 영역의 패널에서 필터를 드래그하는 것과 비슷합니다. 에서 여러 필터 ID를 제공할 수 있습니다 `AND`-그들을..

### WHERE 절

WHERE 절은 다음 세 단계로 처리됩니다.

1. 다음에서 날짜 범위를 찾습니다. `timestamp` 특수 필드.

2. 외부에서 정의된 항목 찾기 `filterId`필터링에 포함할 s입니다.

3. 나머지 표현식을 임시 필터로 변환합니다.

의 첫 번째 수준을 구문 분석하여 처리를 수행합니다. `AND`의 s `WHERE` 절. 각 최상위 `AND`ed 표현식은 위의 표현식 중 하나와 일치해야 합니다. 의 첫 번째 수준보다 더 깊은 `AND`s 또는, `WHERE` 절 사용 `OR`최상위 수준의 은 임시 필터로 처리됩니다.

### 정렬 기준

기본적으로 쿼리는 처음 선택한 지표를 기준으로 결과를 내림차순으로 정렬합니다. 을 지정하여 기본 정렬 순서를 덮어쓸 수 있습니다 `ORDER BY ... ASC` 또는 `ORDER BY ... DESC`. 를 사용하는 경우 `ORDER BY`, 다음을 지정해야 합니다. `ORDER BY` 을(를) 방문하십시오.

를 사용하여 순서를 전환할 수도 있습니다. `-` (빼기) 를 사용하여 지표를 표시할 수 있습니다. 아래의 두 명령문은 동일한 순서를 갖습니다.

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 일반 기능 지원

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [캐스트 (열 유형)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 또는 <br/> `` `timestamp`::string `` | 유형 캐스팅은 현재 지원 되지 않지만, 오류는 발생 하지 않습니다. 함수는 `CAST` 무시 됩니다. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 시간 문자열을 내에서 사용할 타임스탬프로 구문 분석 `WHERE` 절. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 시간 문자열을 내에서 사용할 타임스탬프로 구문 분석 `WHERE` 원할 경우 해당 시간 문자열에 대한 형식을 제공합니다. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 내에서 사용할 타임스탬프로 날짜 문자열 구문 분석 `WHERE` 절. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 내에서 사용할 타임스탬프로 날짜 문자열 구문 분석 `WHERE` 원할 경우 해당 날짜 문자열에 대한 형식을 제공합니다. |

{style="table-layout:auto"}

### Dimension 기능 지원

이러한 함수는 `SELECT`, `WHERE` 조항 또는 조건부 지표에서 참조할 수 있습니다.

**문자열 함수**

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 전달된 필드에 동적 차원 ID를 생성합니다. |

{style="table-layout:auto"}

**날짜-시간 함수**

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [YEAR(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [MONTH(date 또는 date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [DAY(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [DAYOFWEEK(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 번호가 필요하므로 값 대신 항목 ID를 사용하십시오. |
| [DAYOFYEAR(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [주(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [QUARTER(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [HOUR(날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 번호가 필요하므로 값 대신 항목 ID를 사용하십시오. |
| [MINUTE(일자 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [EXTRACT(일부 시작 날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 이 함수의 일부 부분에 대한 값 대신 항목 ID를 사용하십시오.<br/>지원되는 부품은 다음과 같습니다.<br>- 키워드: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- 문자열:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, 또는 `'MINUTE'`. |
| [DATE_PART(part, date 또는 date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 이 함수의 일부 부분에 대한 값 대신 항목 ID를 사용하십시오.<br/>지원되는 문자열 부분은 다음과 같습니다. `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, 또는 `'MINUTE'`. |
| [DATE_TRUNC(세부기간, 날짜 또는 날짜-시간)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다.<br/>지원되는 문자열 세부기간은 다음과 같습니다. `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, 또는 `'MINUTE'`. |

{style="table-layout:auto"}
