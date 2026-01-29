---
title: 정렬
description: Customer Journey Analytics의 다양한 BI 도구에서 BI 확장에 대한 정렬 사용 사례
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 1%

---

# 정렬


이 사용 사례에서는 2023년 1월 동안의 구매 매출 및 제품 이름에 대한 구매를 내림차순 구매 매출 순서로 보고하려고 합니다.

+++ Customer Journey Analytics

사용 사례에 대한 **[!UICONTROL 정렬]** 패널 예:

![Customer Journey Analytics 정렬 패널](../assets/cja-sort.png)

+++

+++ BI 도구

>[!PREREQUISITES]
>
>[연결에 성공했는지 확인하고, 데이터 보기를 나열하고, 이 사용 사례를 시도하려는 BI 도구에 대해 데이터 보기를 사용](connect-and-validate.md)할 수 있는지 확인하십시오.
>

>[!BEGINTABS]

>[!TAB Power BI 데스크톱]

1. **[!UICONTROL 데이터]** 창:
   1. **[!UICONTROL 날짜 범위]**&#x200B;를 선택합니다.
   1. **[!UICONTROL product_name]**&#x200B;을(를) 선택하십시오.
   1. **[!UICONTROL purchase_revenue 합계]**&#x200B;를 선택하십시오.
   1. **[!UICONTROL 총 구매]**&#x200B;를 선택하세요.

1. **[!UICONTROL 필터]** 창:
   1. **[!UICONTROL 이 시각적 개체의 필터]**&#x200B;에서 **[!UICONTROL 날짜 범위는 (모두)]**&#x200B;입니다.
   1. **[!UICONTROL 고급 필터링]**&#x200B;을(를) **[!UICONTROL 필터 형식]**(으)로 선택합니다.
   1. **[!UICONTROL 값이]** **[!UICONTROL 이거나]** `1/1/2023` **[!UICONTROL 이거나]** **[!UICONTROL 이(가)]** `2/1/2023` 이전인 경우 항목 표시로 필터를 정의합니다.

1. 시각화 창에서 다음을 수행합니다.
   1. 열에서 데이터 범위를 제거하려면 ![CrossSize75](/help/assets/icons/CrossSize75.svg)을(를) 선택하십시오.
   1. **[!UICONTROL purchase_revenue의 합계]**&#x200B;를 **[!UICONTROL 열]**&#x200B;개 항목의 맨 아래로 끕니다.

1. 보고서에서 **[!UICONTROL purchase_revenue의 합계]**&#x200B;를 선택하여 구매 매출의 내림차순으로 테이블을 정렬합니다.

   Power BI 데스크톱은 다음과 같아야 합니다.

   ![필터링할 날짜 범위 이름을 사용하는 Power BI 데스크톱](../assets/uc11-powerbi-final.png)

BI 확장을 사용하여 Power BI Desktop에서 실행한 쿼리에 `sort` 문이 포함되어 있지 않습니다. `sort` 문이 없다는 것은 정렬이 클라이언트측에서 실행됨을 의미합니다.

```sql
select "_"."product_name",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where "_"."daterange" < date '2023-02-01' and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```


>[!TAB 타블로 데스크톱]

1. 하단의 **[!UICONTROL 시트 1]** 탭을 선택하여 **[!UICONTROL 데이터 원본]**&#x200B;에서 전환하세요. **[!UICONTROL 시트 1]** 보기에서:
   1. **[!UICONTROL 필터]** 셸프의 **[!UICONTROL 테이블]** 목록에서 **[!UICONTROL Daterange]** 항목을 드래그합니다.
   1. **[!UICONTROL 필터 필드 \[Daterange\]]** 대화 상자에서 **[!UICONTROL 날짜 범위]**&#x200B;를 선택하고 **[!UICONTROL 다음 >]**&#x200B;을(를) 선택합니다.
   1. **[!UICONTROL 필터 \[Daterange\]]** 대화 상자에서 **[!UICONTROL 날짜 범위]**&#x200B;를 선택하고 `01/01/2023` - `1/2/2023`을(를) 선택합니다. **[!UICONTROL 적용]** 및 **[!UICONTROL 확인]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 테이블]** 목록에서 **[!UICONTROL 제품 이름]**&#x200B;을(를) 드래그하여 **[!UICONTROL 행]** 옆의 필드에 항목을 놓습니다.
   1. **[!UICONTROL 테이블]** 목록에서 **[!UICONTROL 구매]** 항목을 드래그하여 **[!UICONTROL 열]** 옆의 필드에 항목을 놓습니다. 값이 **[!UICONTROL SUM(구매)]**(으)로 변경됩니다.
   1. **[!UICONTROL 테이블]** 목록에서 **[!UICONTROL 구매 매출]** 항목을 드래그하여 **[!UICONTROL 열]** 옆의 필드, **[!UICONTROL SUM(구매)]** 옆의 필드에 항목을 놓습니다. 값이 **[!UICONTROL SUM(구매 매출)]**(으)로 변경됩니다.
   1. **[!UICONTROL 표시]**&#x200B;에서 **[!UICONTROL 텍스트 테이블]**&#x200B;을(를) 선택하십시오.
   1. **[!UICONTROL 맞춤]** 드롭다운 메뉴에서 **[!UICONTROL 맞춤]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 구매 매출]** 열 헤더를 선택하고 이 열의 테이블을 내림차순으로 정렬하십시오.

      Tableau Desktop은 다음과 같습니다.

      ![타블로 데스크톱 정렬](../assets/uc11-tableau-final.png)

Tableau Desktop에서 BI 확장을 사용하여 실행한 쿼리에 `sort` 문이 포함되어 있지 않습니다. 이 `sort` 문이 없다는 것은 정렬이 클라이언트측에서 실행됨을 의미합니다.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-02-01')))
GROUP BY 1
```

>[!TAB 조회자]

1. Looker의 **[!UICONTROL 탐색]** 인터페이스에서 연결을 새로 고치십시오. ![설정](/help/assets/icons/Setting.svg) **[!UICONTROL 캐시 지우기 및 새로 고침]**&#x200B;을 선택하십시오.
1. Looker의 **[!UICONTROL Explore]** 인터페이스에서 제대로 설정했는지 확인하십시오. 그렇지 않으면 ![설정](/help/assets/icons/Setting.svg) **[!UICONTROL 필드 및 필터 제거]**&#x200B;를 선택하십시오.
1. **[!UICONTROL 필터]** 아래의 **[!UICONTROL + 필터]**&#x200B;을(를) 선택하십시오.
1. **[!UICONTROL 필터 추가]** 대화 상자에서:
   1. **[!UICONTROL ‣Cc 데이터 보기 선택]**
   1. 필드 목록에서 **[!UICONTROL 날짜 범위 날짜]**‣을 선택한 다음 **[!UICONTROL 날짜 범위 날짜]**을 선택합니다.
      ![조회 필터](../assets/uc2-looker-filter.png)
1. **[!UICONTROL 이(가) 범위에 있으므로]** Cc 데이터 보기 날짜&#x200B;**[!UICONTROL 필터를 지정하십시오]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 까지(이전)]** **[!UICONTROL 2023/02/01]**.
1. 왼쪽 레일의 **[!UICONTROL ‣Cc 데이터 보기]** 섹션에서 **[!UICONTROL 제품 이름]**&#x200B;을(를) 선택합니다.
1. 왼쪽 레일의 {0‣} 사용자 지정 필드&#x200B;**[!UICONTROL 섹션에서 다음을 수행합니다.]**
   1. **[!UICONTROL + 추가]** 드롭다운 메뉴에서 **[!UICONTROL 사용자 지정 측정값]**&#x200B;을(를) 선택합니다.
   1. **[!UICONTROL 사용자 지정 측정값 만들기]** 대화 상자에서 다음을 수행합니다.
      1. **[!UICONTROL 측정할 필드]** 드롭다운 메뉴에서 **[!UICONTROL 구매 매출]**&#x200B;을(를) 선택합니다.
      1. **[!UICONTROL 측정값 유형]** 드롭다운 메뉴에서 **[!UICONTROL 합계]**&#x200B;를 선택합니다.
      1. **[!UICONTROL 이름]**&#x200B;의 사용자 지정 필드 이름을 입력하십시오. 예: `Sum of Purchase Revenue`.
      1. **[!UICONTROL 필드 세부 정보]** 탭을 선택합니다.
      1. **[!UICONTROL 형식]** 드롭다운 메뉴에서 **[!UICONTROL 소수 자릿수]**&#x200B;을(를) 선택하고 `0`이(가) **[!UICONTROL 소수 자릿수]**에 입력되었는지 확인하십시오.
         ![사용자 지정 지표 필드 보기](../assets/uc5-looker-customfield.png)
      1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.
1. **[!UICONTROL 구매 매출]** 열에서 **[!UICONTROL ↓]**(**[!UICONTROL 내림차순, 정렬 순서: 1]**)을(를) 선택하십시오.
1. **[!UICONTROL 실행]**&#x200B;을 선택합니다.
1. **[!UICONTROL ‣개의 시각화]**&#x200B;를 선택하십시오.

아래 표시된 것처럼 시각화 및 테이블이 표시됩니다.

![고유 조회 수](../assets/uc11-looker-result.png)


Looker에서 BI 확장을 사용하여 생성한 쿼리에 `ORDER BY`이(가) 포함되어 있습니다. 이는 정렬이 Looker 및 BI 확장을 통해 실행됨을 의미합니다.

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"fc83573987b999306eaf6e1a3f2cde70","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "purchase_revenue"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2024-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2023-02-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```


>[!TAB Jupyter 전자 필기장]

1. 새 셀에 다음 문을 입력합니다.

   ```python
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 5;
   display(data)
   ```

1. 셀을 실행합니다. 아래 스크린샷과 비슷한 출력이 표시됩니다.

   ![Jupyter Notebook 결과](../assets/uc11-jupyter-results.png)

이 쿼리는 Jupyter Notebook에 정의된 BI 확장에서 실행됩니다.


>[!TAB 자습서]

1. 새 청크에 ` ```{r} `에서 ` ``` ` 사이의 다음 문을 입력하십시오.

   ```R
   ## Dimension 1 Sorted
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. 청크를 실행합니다. 아래 스크린샷과 비슷한 출력이 표시됩니다.

   ![라디오 결과](../assets/uc11-rstudio-results.png)

BI 확장을 사용하여 RStudio에서 생성된 쿼리에 `ORDER BY`이(가) 포함되어 있습니다. 이는 순서가 RStudio 및 BI 확장을 통해 적용됨을 의미합니다.

```sql
SELECT
  "product_name",
  SUM("purchase_revenue") AS "purchase_revenue",
  SUM("purchases") AS "purchases"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2023-02-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "purchase_revenue" DESC
LIMIT 1000
```

>[!ENDTABS]

+++
