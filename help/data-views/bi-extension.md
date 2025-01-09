---
title: Customer Journey Analytics BI 확장 기능
description: Power BI 또는 Tableau Desktop을 사용하여 Customer Journey Analytics BI 확장을 사용하여 데이터 보기에 액세스하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: d7d16dbef202db9fdac08796dacc3368e0119456
workflow-type: tm+mt
source-wordcount: '3176'
ht-degree: 73%

---

# Customer Journey Analytics BI 확장 기능

{{select-package}}

[!DNL Customer Journey Analytics BI extension]를 통해 SQL은 Customer Journey Analytics에서 정의한 [데이터 보기](./data-views.md)에 액세스할 수 있습니다. 데이터 엔지니어와 분석가는 Power BI, Tableau Desktop 또는 기타 비즈니스 인텔리전스 및 시각화 도구(BI 도구라고도 함)에 더 익숙할 수 있습니다. 이제 Customer Journey Analytics 사용자가 Analysis Workspace 프로젝트를 생성할 때 사용하는 것과 동일한 데이터 보기를 기반으로 보고 및 대시보드를 만들 수 있습니다.

Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home)는 Experience Platform의 데이터 레이크에서 사용 가능한 데이터에 대한 SQL 인터페이스입니다. [!DNL Customer Journey Analytics BI extension]를 활성화하면 Customer Journey Analytics 데이터 보기를 [!DNL Query Service] 세션의 테이블 또는 보기로 볼 수 있도록 [!DNL Query Service] 기능이 확장됩니다. 따라서 [!DNL Query Service]를 PostgresSQL 인터페이스로 사용하는 비즈니스 인텔리전스 도구는 이러한 확장 기능을 통해 원활하게 이점을 누릴 수 있습니다.

주요 이점은 다음과 같습니다.

* BI 도구 자체 내에서 Customer Journey Analytics 데이터 보기의 동등한 표시를 다시 만들 필요가 없습니다. <br/>[데이터 보기](data-views.md)의 기능에 대한 자세한 내용은 데이터 보기를 참조하여 재생성해야 하는 내용을 알아보십시오.
* BI 도구와 Customer Journey Analytics 간의 보고 및 분석 일관성이 향상되었습니다.
* Customer Journey Analytics 데이터를 이미 BI 도구에서 사용할 수 있는 다른 데이터 소스와 결합합니다.

## 사전 요구 사항

이 기능을 사용하려면 만료되거나 만료되지 않는 자격 증명을 사용하여 BI 도구를 [!DNL Customer Journey Analytics BI extension]에 연결할 수 있습니다. [자격 증명 안내서](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials)에서 만료되는 자격 증명 또는 만료되지 않는 자격 증명을 설정하는 방법에 대한 자세한 정보를 제공합니다.
다음은 CJA 권한을 설정하는 추가 단계입니다
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### 자격 증명 만료

만료 자격 증명을 사용하려면 다음을 수행할 수 있습니다.

* Experience Platform 및 Customer Journey Analytics에 대한 액세스 권한을 부여합니다.
* 연결 및 데이터 보기를 보기, 편집, 업데이트 또는 삭제할 수 있도록 Customer Journey Analytics에 대한 제품 관리자 액세스 권한을 부여합니다.

또는 다음을 수행할 수 있습니다.

* 액세스하려는 데이터 보기에 대한 액세스 권한을 부여합니다.
* Customer Journey Analytics BI 확장 기능에 대한 액세스 권한을 부여합니다.

### 만료되지 않는 자격 증명

만료되지 않는 자격 증명을 사용하려면 다음을 수행하십시오.

* Experience Platform에서 만료되지 않는 자격 증명을 만듭니다.
* [만료되는 자격 증명](#Expiring-credentials)에 언급된 단계에 따라 만료되지 않는 자격 증명에 대한 액세스 권한을 부여합니다.

자세한 내용은 [고객 여정 액세스 제어](../technotes/access-control.md)를 참조하십시오. 특히 [제품 관리자 추가 권한](../technotes/access-control.md#product-admin-additional-permissions) 및 [Admin Console의 Customer Journey Analytics 권한](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console)을 참조하십시오.


## 사용

[!DNL Customer Journey Analytics BI extension] 기능을 사용하려면 SQL을 직접 사용하거나 특정 BI 도구에서 사용 가능한 드래그 앤 드롭 경험을 사용할 수 있습니다.

### SQL

쿼리 편집기나 표준 PostgresSQL 명령줄 인터페이스(CLI) 클라이언트를 사용하여 SQL 문에서 직접 기능을 사용할 수 있습니다.

+++ 쿼리 편집기

Adobe Experience Platform:

1. 왼쪽 레일의 **[!UICONTROL **&#x200B;데이터 관리&#x200B;**]**&#x200B;에서 **[!UICONTROL **&#x200B;쿼리&#x200B;**]**&#x200B;를 선택합니다.

1. ![쿼리 만들기](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;쿼리 만들기&#x200B;**]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터베이스]** 드롭다운 메뉴의 데이터베이스 목록에서 샌드박스의 `cja` 데이터베이스를 선택하십시오. 예 `prod:cja`.

1. 쿼리를 실행하려면 SQL 문을 입력하고 ![재생](assets/Smock_Play_18_N.svg) 버튼을 선택합니다(또는 `[SHIFT]` + `[ENTER]` 누르기).

+++


+++ PostgresSQL CLI

1. Adobe Experience Platform에서 PostgresSQL 자격 증명을 찾아 복사합니다.

   1. 왼쪽 레일에서 **[!UICONTROL **&#x200B;쿼리&#x200B;**]**&#x200B;를 선택합니다(**[!UICONTROL **&#x200B;데이터 관리&#x200B;**]** 아래).

   1. 상단 막대에서 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]**&#x200B;을 선택합니다.

   1. **[!UICONTROL 데이터베이스]** 드롭다운 메뉴의 데이터베이스 목록에서 샌드박스의 `cja` 데이터베이스를 선택하십시오. 예 `prod:cja`.

   1. 명령 문자열을 복사하려면 **[!UICONTROL ** PSQL 명령&#x200B;**]** 섹션의 ![복사](assets/Smock_Copy_18_N.svg)를 사용합니다.

1. 명령 또는 터미널 창을 엽니다.

1. 로그인하여 쿼리 실행을 시작하려면 터미널에 명령 문자열을 붙여넣으십시오.

+++

자세한 내용은 [쿼리 편집기 UI 안내서](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide)를 참조하십시오.


### BI 도구

현재 [!DNL Customer Journey Analytics BI extension]은(는) Power BI 및 Tableau Desktop에 대해서만 지원되고 테스트됩니다. PSQL 인터페이스를 사용하는 다른 BI 도구에서도 작동할 수 있지만, 아직 공식적으로 지원되지는 않습니다.

+++ Power BI

1. Adobe Experience Platform에서 PostgresSQL 자격 증명의 세부 정보를 찾습니다.

   1. 왼쪽 레일에서 **[!UICONTROL **&#x200B;쿼리&#x200B;**]**&#x200B;를 선택합니다(**[!UICONTROL **&#x200B;데이터 관리&#x200B;**]** 아래).

   1. 상단 막대에서 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]**&#x200B;을 선택합니다.

   1. **[!UICONTROL 데이터베이스]** 드롭다운 메뉴의 데이터베이스 목록에서 샌드박스의 `cja` 데이터베이스를 선택하십시오. 예 `prod:cja`.

   1. Power BI에서 필요한 경우 ![복사](assets/Smock_Copy_18_N.svg)를 사용하여 각 Postgres 자격 증명 매개변수([!UICONTROL 호스트], [!UICONTROL 포트], [!UICONTROL 데이터베이스], [!UICONTROL 사용자 이름] 및 기타)를 복사합니다.

1. Power BI에서 다음 작업을 수행합니다.

   1. 기본 창의 상단 도구 모음에서 **[!UICONTROL **&#x200B;데이터 내보내기&#x200B;**]**&#x200B;를 선택합니다.

   1. 왼쪽 레일에서 **[!UICONTROL 자세히...]**&#x200B;를 선택합니다.

   1. **데이터 가져오기** 화면에서 `PostgresSQL`을 검색하고 해당 목록에서 **[!UICONTROL ** PostgresSQL 데이터베이스&#x200B;**]**&#x200B;를 선택합니다.

   1. **[!UICONTROL ** PostgressSQL 데이터베이스&#x200B;**]** 대화 상자에서 다음 작업을 수행합니다.

      1. **[!UICONTROL ** Server **]** 텍스트 필드에 Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL ** Host **]** 매개 변수를 붙여 넣습니다.

      1. **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 텍스트 필드에 Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개 변수를 붙여 넣습니다.

         예를 들어 `prod:cja?FLATTEN`처럼 읽히도록 `?FLATTEN`을 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개변수에 추가합니다. 자세한 내용은 [서드파티 BI 도구와 함께 사용할 수 있도록 중첩 데이터 구조 평면화](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data)를 참조하십시오.

      1. **[!UICONTROL 데이터 연결]** 모드를 묻는 메시지가 나타나면 **[!UICONTROL DirectQuery]**&#x200B;를 선택합니다.

      1. **[!UICONTROL 사용자 이름]** 및 **[!UICONTROL 암호]**&#x200B;를 묻는 메시지가 표시됩니다. Experience Platform 쿼리 [!UICONTROL 자격 증명]의 동등한 매개변수 사용


   1. 로그인에 성공하면 Customer Journey Analytics 데이터 보기 테이블이 Power BI **[!UICONTROL ** Navigator **]**&#x200B;에 나타납니다.

   1. 사용할 데이터 보기 테이블을 선택하고 **[!UICONTROL **&#x200B;로드&#x200B;**]**&#x200B;를 선택합니다

   하나 이상의 선택한 테이블과 연결된 모든 차원 및 지표가 오른쪽 창에 표시되어 시각화에 사용할 수 있습니다.

   자세한 내용은 [Power BI를 Query Service에 연결](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi)을 참조하십시오.

+++

+++타블로 데스크톱

1. Adobe Experience Platform에서 PostgresSQL 자격 증명의 세부 정보를 찾습니다.

   1. 왼쪽 레일에서 **[!UICONTROL **&#x200B;쿼리&#x200B;**]**&#x200B;를 선택합니다(**[!UICONTROL **&#x200B;데이터 관리&#x200B;**]** 아래).

   1. 상단 막대에서 **[!UICONTROL **&#x200B;자격 증명&#x200B;**]**&#x200B;을 선택합니다.

   1. **[!UICONTROL 데이터베이스]** 드롭다운 메뉴의 데이터베이스 목록에서 샌드박스의 `cja` 데이터베이스를 선택하십시오. 예 `prod:cja`.

   1. 필요한 경우 Tableau Desktop에서 각 Postgres 자격 증명 매개 변수([!UICONTROL 호스트], [!UICONTROL 포트], [!UICONTROL 데이터베이스], [!UICONTROL 사용자 이름] 등)를 복사하려면 ![복사](assets/Smock_Copy_18_N.svg)를 사용하십시오.

1. Tableau Desktop에서:

   1. 왼쪽 레일의 **[!UICONTROL **&#x200B;서버로&#x200B;**]**&#x200B;에서 **[!UICONTROL **&#x200B;자세히&#x200B;**]**&#x200B;를 선택합니다.

   1. 목록에서 **[!UICONTROL ** PostgresSQL **]**&#x200B;을 선택합니다.

   1. [!UICONTROL PostgresSQL] 대화 상자에서 다음 작업을 수행합니다.

      1. Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL ** Host **]** 매개 변수를 **[!UICONTROL ** Server **]** 텍스트 필드에 붙여 넣으십시오.

      1. Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL ** Port **]** 매개 변수를 **[!UICONTROL ** Port **]** 텍스트 필드에 붙여 넣으십시오.

      1. Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL ** Database **]** 매개 변수를 **[!UICONTROL ** Database **]** 텍스트 필드에 붙여 넣으십시오.

         예를 들어 `prod:cja%3FFLATTEN`처럼 읽히도록 `%3FFLATTEN`을 **[!UICONTROL **&#x200B;데이터베이스&#x200B;**]** 매개변수에 추가합니다. 자세한 내용은 [서드파티 BI 도구와 함께 사용할 수 있도록 중첩 데이터 구조 평면화](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data)를 참조하십시오.

      1. **[!UICONTROL **&#x200B;인증&#x200B;**]** 목록에서 **[!UICONTROL **&#x200B;사용자 이름 및 암호&#x200B;**]**&#x200B;를 선택합니다.

      1. **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** 텍스트 필드에 Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL **&#x200B;사용자 이름&#x200B;**]** 매개변수를 붙여넣습니다.

      1. Experience Platform 쿼리 [!UICONTROL 자격 증명]의 **[!UICONTROL **&#x200B;암호&#x200B;**]** 매개 변수를 **[!UICONTROL **&#x200B;암호&#x200B;**]** 텍스트 필드에 붙여 넣으십시오.

      1. **[!UICONTROL **&#x200B;로그인&#x200B;**]**&#x200B;을 선택합니다.

   1. Customer Journey Analytics 데이터 보기가 **[!UICONTROL **&#x200B;테이블&#x200B;**]** 목록에 테이블로 표시됩니다.

   1. 사용하려는 테이블을 캔버스로 드래그합니다.

   이제 데이터 보기 테이블의 데이터를 사용하여 보고서 및 시각화를 빌드할 수 있습니다.

   자세한 내용은 [Query Service에 Tableau 연결](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau)을 참조하십시오.

+++

사용 가능한 다양한 도구에 대한 개요 및 자세한 내용은 [Query Service에 클라이언트 연결](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview)을 참조하십시오.

Customer Journey Analytics BI 확장을 사용하여 다양한 사용 사례를 완수하는 방법은 [사용 사례](/help/use-cases/data-views/bi-extension-usecases.md)를 참조하세요.

## 기능

기본적으로 데이터 보기에는 친숙한 이름에서 생성된 테이블 보안 이름이 있습니다. 예를 들어, 이름이 [!UICONTROL 내 웹 데이터 보기]인 데이터 보기의 보기 이름은 `my_web_data_view`입니다. 데이터 보기를 위해 BI 도구에서 사용할 기본 이름을 정의할 수 있습니다. 자세한 내용은 [데이터 보기 설정](create-dataview.md#settings)을 참조하세요.

데이터 보기 ID를 테이블 이름으로 사용하려면 연결할 때 데이터베이스 이름에 옵션인 `CJA_USE_IDS` 설정을 추가할 수 있습니다. 예를 들어 `prod:cja?CJA_USE_IDS`에는 `dv_ABC123`과 같은 데이터 보기가 표시됩니다.

### 데이터 거버넌스

Customer Journey Analytics의 데이터 거버넌스 관련 설정은 Adobe Experience Platform에서 상속됩니다. Customer Journey Analytics와 Adobe Experience Platform 데이터 거버넌스의 통합을 통해 중요한 Customer Journey Analytics 데이터에 레이블을 지정하고 개인정보 처리방침을 시행할 수 있습니다.

Experience Platform에서 사용하는 데이터 세트에 생성된 개인정보 보호 레이블 및 정책은 Customer Journey Analytics 데이터 보기 워크플로에 표시될 수 있습니다. 따라서 [!DNL Customer Journey Analytics BI extension]을 사용하여 쿼리한 데이터는 정의된 개인정보 보호 레이블 및 정책을 준수하지 않을 경우 적절한 경고 또는 오류를 표시합니다.

### 데이터 보기 나열

표준 PostgreSQL CLI에서 `\dv`를 사용하여 보기를 나열할 수 있음

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres
```

### 중첩 및 평면화

기본적으로 데이터 보기의 스키마는 원래 XDM 스키마와 마찬가지로 중첩 구조를 사용합니다. 또한 통합은 `FLATTEN` 옵션을 지원합니다. 이 옵션을 사용하면 데이터 보기(및 세션의 다른 테이블)에 대한 스키마를 강제로 평면화할 수 있습니다. 평면화를 사용하면 구조화된 스키마를 지원하지 않는 BI 도구를 더 쉽게 사용할 수 있습니다. 자세한 내용은 [Query Service에서 중첩된 데이터 구조로 작업](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data)을 참조하십시오.


### 기본값 및 제한 사항

BI 확장을 사용할 때 다음과 같은 추가 기본값과 제한이 적용됩니다.

* BI 확장 기능에는 쿼리 결과에 대한 행 제한이 필요합니다. 기본값은 50이지만 `LIMIT n`을(를) 사용하여 SQL에서 재정의할 수 있습니다. 여기서 `n`은(는) 1 - 50000입니다.
* BI 확장을 사용하려면 계산에 사용되는 행을 제한하는 날짜 범위가 필요합니다. 기본값은 최근 30일이지만 SQL `WHERE` 절에서 특수 [`timestamp`](#timestamp) 또는 [`daterange`](#date-range) 열을 사용하여 이 값을 재정의할 수 있습니다.
* BI 확장을 사용하려면 집계 쿼리가 필요합니다. `SELECT * FROM ...`과(와) 같은 SQL을 사용하여 원시 기본 행을 가져올 수 없습니다. 높은 수준에서 집계 쿼리는 다음을 사용해야 합니다.
   * `SUM` 및/또는 `COUNT`을(를) 사용하여 합계를 선택하십시오.<br/> 예: `SELECT SUM(metric1), COUNT(*) FROM ...`
   * 차원별로 분류된 지표를 선택합니다. <br/>예: `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * 고유한 지표 값을 선택합니다.<br/>예: `SELECT DISTINCT dimension1 FROM ...`

     자세한 내용은 [지원되는 SQL](#supported-sql)을(를) 참조하십시오.


### 지원되는 SQL

지원되는 SQL 유형에 대한 전체 참조는 [Query Service SQL 참조](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview)를 확인하십시오.

사용할 수 있는 SQL의 예는 아래 표를 참조하십시오.

+++ 예

| 패턴 | 예 |
|---|---|
| 스키마 검색 | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| 등급 또는 분류 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| `HAVING` 절 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| 고유, 상단 <br/>차원 값 | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| 지표 합계 | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| 다차원<br/>분류<br/>및 상단 고유 항목 | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| 하위 선택: <br/>추가 결과 필터링<br/> | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| 하위 선택: 데이터 보기<br/>전체 쿼리<br/> | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| 하위 선택: <br/>계층 소스, <br/>필터링, <br/>및 집계 | 하위 선택을 사용하여 계층화됨:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>CTE WITH를 사용한 계층:<br/><pre>(<br/>(으)로 \_ 행 (<br/>)    SELECT * FROM data_ares<br/>    여기서 \`timestamp\`는 &#39;2021-01-01&#39;과(와) &#39;2021-02-01&#39;<br/> )<br/> \_.item, \_.units를 \_<br/>에서 선택합니다. 여기서 \_.item은 NULL이 아닙니다.<br/><br/>행.item, SUM(rows.units)을 단위로 선택<br/>행(&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)의 행.item인 행에서<br/>행 단위로 그룹화.item</pre> |
| 지표가 차원 <br/>앞에 있거나<br/> 혼합되는<br/>위치 선택 | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### 차원

기본적으로 사용 가능하거나 데이터 보기에 정의된 차원을 선택할 수 있습니다. ID로 차원을 선택합니다.

### 지표

선택할 수 있는 지표는 다음과 같습니다.

* 기본적으로 사용 가능한 지표.
* 데이터 보기에 정의되어 있음.
* 사용자가 액세스할 수 있는 데이터 보기와 호환되는 계산된 지표.

다른 SQL 소스에서와 마찬가지로 `SUM(metric)` 표현식으로 래핑된 ID를 기준으로 지표를 선택합니다.

다음과 같은 작업을 수행할 수 있습니다.

* `SELECT COUNT(*)` 또는 `COUNT(1)`는 발생 횟수 지표를 얻습니다.
* `SELECT COUNT(DISTINCT dimension)` 또는 `SELECT APPROX_COUNT_DISTINCT(dimension)`는 차원의 대략적인 고유 값을 계산합니다. [고유 값 계산](#counting-distinct-values)에서 세부 사항을 확인하십시오.
* [인라인 계산](#inline-calculations)은 즉시 지표 및/또는 이에 대한 연산을 결합합니다.

#### 고유 값 계산

Customer Journey Analytics 작동 방식의 근본적인 특성 때문에 정확한 고유 카운트를 얻을 수 있는 유일한 차원은 `adobe_personid` 차원입니다. 다음 SQL 문 `SELECT COUNT(DISTINCT adobe_personid)` 또는 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)`은(는) 고유한 사람의 수인 기본 사람 지표의 값을 반환합니다. 다른 차원의 경우, 대략적인 고유 카운트가 반환됩니다.

#### 조건부 지표

`SUM` 또는 `COUNT` 함수에 `IF` 또는 `CASE` 절을 임베드하여 선택한 지표와 관련된 필터링을 추가할 수 있습니다. 이러한 절을 추가하는 것은 Workspace 보고서 테이블의 지표 열에 필터를 적용하는 것과 유사합니다.

예:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### 인라인 계산

`SELECT`의 지표 표현식에 추가 계산을 적용할 수 있습니다. 이 수학은 계산된 지표에서 수학을 정의하는 대신 사용할 수 있습니다. 다음 테이블에는 지원되는 표현식 유형이 나열되어 있습니다.

| 연산자 또는 함수 | 세부 사항 |
|---|---|
| `+`, `-`, `*`, `/` 및 `%` | 더하기, 빼기, 곱하기, 나누기 및 모듈러스/나머지 |
| `-X` 또는 `+X` | X가 지표 표현식인 기호 또는 지표 변경 |
| `PI()` | π 상수 |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` 및 `TANH` | 단항 수학 함수 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 이진 수학 함수 |

{style="table-layout:auto"}

### 특수 열

#### 타임스탬프

`timestamp` 특수 열을 사용하여 쿼리의 날짜 범위를 제공합니다. 날짜 범위는 `BETWEEN` 표현식을 사용하거나 `timestamp` `>`, `>=`, `<`, `<=` 확인 `AND` 쌍을 함께 사용하여 정의할 수 있습니다.
`timestamp`는 옵션이며 전체 범위가 제공되지 않으면 기본값이 사용됩니다.

* 최소값만 제공되는 경우(`timestamp > X` 또는 ` timestamp >= X`), 범위는 X부터 지금까지입니다.
* 최대값만 제공되는 경우(`timestamp < X` 또는 `timestamp <= X`), 범위는 X-30일부터 X까지입니다.
* 아무것도 제공되지 않는 경우 범위는 지금부터 -30일까지입니다.

타임스탬프 범위는 RankedRequest에서 날짜 범위 전역 필터로 변환됩니다.
타임스탬프 필드는 날짜/시간 함수에서 이벤트 타임스탬프를 구문 분석하고 자르는 데 사용될 수도 있습니다.

#### 날짜 범위

`daterange` 특수 열은 `timestamp`과(와) 유사하게 작동하지만 필터링은 전체 날짜로 제한됩니다. `daterange`는 옵션이며 범위 기본값은 `timestamp`와 동일합니다.
`daterange` 필드를 사용하여 날짜/시간 함수에서 이벤트 날짜를 구문 분석하고 자를 수 있습니다.

`daterangeName` 특수 열을 사용하면 `Last Quarter`와 같이 이름이 지정된 날짜 범위를 사용하여 쿼리를 필터링할 수 있습니다.

>[!NOTE]
>
>Power BI이 하루(시간, 30분, 5분 등) 미만의 `daterange` 지표를 지원하지 않습니다.
>

#### 필터 ID

`filterId` 특수 열은 옵션이며 외부에서 정의된 필터를 쿼리에 적용하는 데 사용됩니다. 외부에서 정의된 필터를 쿼리에 적용하는 것은 Workspace의 패널에서 필터를 드래그하는 것과 비슷합니다. 여러 필터 ID는 `AND`-ing에서 사용할 수 있습니다.

`filterId`과 함께 `filterName` ID 대신 필터 이름을 사용할 수 있습니다.

### WHERE 절

`WHERE` 절은 세 단계로 처리됩니다.

1. `timestamp`, `daterange` 또는 `daterangeName` 특수 필드에서 날짜 범위를 찾습니다.

1. 필터링에 포함할 외부에서 정의된 `filterId` 또는 `filterName`을(를) 찾습니다.

1. 나머지 표현식을 임시 필터로 전환합니다.

`WHERE` 절에서 `AND`의 첫 번째 수준을 구문 분석하여 처리됩니다. 각 최상위 `AND`-ed 표현식은 위의 표현식 중 하나와 일치해야 합니다. `AND`의 첫 번째 수준보다 자세한 항목이거나 `WHERE` 절이 최상위 수준에서 `OR`을 사용하는 경우, 임시 필터로 처리됩니다.

### 정렬 순서

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
| [Cast](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 또는 <br/> `` `timestamp`::string `` | 유형 캐스팅은 현재 지원되지 않지만 오류는 발생하지 않습니다. `CAST` 함수는 무시됩니다. |
| [타임스탬프](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | `WHERE` 절 내에서 사용할 타임스탬프로 시간 문자열을 구문 분석합니다. |
| [타임스탬프](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 시간 문자열을 `WHERE` 절 내에서 사용할 타임스탬프로 구문 분석하고, 옵션으로 해당 시간 문자열에 대한 형식을 제공합니다. |
| [날짜](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | `WHERE` 절 내에서 사용할 타임스탬프로 날짜 문자열을 구문 분석합니다. |
| [종료 일자](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 날짜 문자열을 `WHERE` 절 내에서 사용할 타임스탬프로 구문 분석하고, 옵션으로 해당 날짜 문자열에 대한 형식을 제공합니다. |

{style="table-layout:auto"}

### 차원 함수 지원

이러한 함수는 `SELECT`, `WHERE` 절의 차원에서 사용하거나 조건부 지표에서 사용할 수 있습니다.

**문자열 함수**

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [Lower](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 전달된 필드에 동적 차원 ID를 생성합니다. |

{style="table-layout:auto"}

**날짜-시간 함수**

| 함수 | 예 | 세부 사항 |
|---|---|---|
| [년](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [월](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [일](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [요일](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 값 대신 항목 ID를 사용합니다. |
| [일(한 해 기준)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [주](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [분기](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [시간](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 값 대신 항목 ID를 사용합니다. |
| [분](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. |
| [추출](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 이 함수의 일부 부분에 대한 값 대신 항목 ID를 사용합니다.<br/>지원되는 항목:<br>- 키워드: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- 문자열:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` 또는 `'MINUTE'`. |
| [날짜(일부)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다. 친숙한 이름이 아닌 숫자가 필요하므로 이 함수의 일부 부분에 대한 값 대신 항목 ID를 사용합니다.<br/>지원되는 문자열 항목: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` 또는 `'MINUTE'`. |
| [날짜(잘림)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 전달된 필드에 동적 차원 ID를 생성합니다.<br/>지원되는 문자열 세부 기간: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` 또는 `'MINUTE'`. |

{style="table-layout:auto"}

### 부분 지원

일부 SQL 기능은 BI 확장 기능에서만 부분적으로 지원되며 다른 데이터베이스에서 볼 수 있는 것과 동일한 결과를 반환하지 않습니다.  이 특정 기능은 다양한 BI 도구로 생성된 SQL에서 사용되며 BI 확장에 정확한 일치가 없습니다. 따라서 BI 확장은 오류를 발생시키지 않고 최소 BI 도구 사용을 다루는 제한된 구현에 중점을 둡니다. 자세한 내용은 아래 표를 참조하십시오.

| 함수 | 예 | 세부 사항 |
|---|---|---|
| MIN() 및 MAX() | ``MIN(daterange)`` 또는 <br/> ``MAX(daterange)`` | `timestamp`, `daterange`의 `MIN()` 또는 `daterangeday`과(와) 같은 `daterangeX`이(가) 2년 전에 반환됩니다.<br/><br/> `timestamp`, `daterange`의 `MAX()` 또는 `daterangeday`과(와) 같은 `daterangeX`의 이(가) 현재 날짜/시간을 반환합니다.다른 차원, 지표 또는 식의 <br/><br/>`MIN()` 또는 `MAX()`은(는) 0을 반환합니다. |

{style="table-layout:auto"}
