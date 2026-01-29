---
title: Dimension 값을 사용하여 세그먼트화
description: 차원 값을 사용하여 Customer Journey Analytics의 다양한 BI 도구에서 BI 확장의 사용 사례를 세그먼트화합니다
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 0%

---

# 차원 값을 사용하여 세그먼트화

**[!UICONTROL 제품 범주]**&#x200B;에 대해 동적 **[!UICONTROL Hunting]** 값을 사용하여 헌팅 범주의 제품을 세그먼트화합니다. 또는 제품 카테고리 값의 동적 검색을 지원하지 않는 BI 도구의 경우 Customer Journey Analytics에서 헌팅 제품 카테고리의 제품을 세그먼트화하는 새 세그먼트를 만듭니다.
그런 다음 새 세그먼트를 사용하여 2023년 1월 중에 헌팅 카테고리의 제품에 대한 제품 이름과 발생 횟수(이벤트)를 보고할 수 있습니다.

+++ Customer Journey Analytics

Customer Journey Analytics에서 **[!UICONTROL 제목]** `Hunting Products`을(를) 사용하여 새 세그먼트를 만듭니다.

![Customer Journey Analytics에서 Dimension 값을 사용하여 세그먼테이션](../assets/cja-hunting-products.png)

그런 다음 사용 사례에 대해 **[!UICONTROL Dimension 값을 사용하여 필터링]** 패널의 예에서 해당 세그먼트를 사용할 수 있습니다.

![Customer Journey Analytics 고유 개수 값](../assets/cja-using-dimension-values-to-filter.png)

+++

+++ BI 도구

>[!PREREQUISITES]
>
>[연결에 성공했는지 확인하고, 데이터 보기를 나열하고, 이 사용 사례를 시도하려는 BI 도구에 대해 데이터 보기를 사용](connect-and-validate.md)할 수 있는지 확인하십시오.
>

>[!BEGINTABS]

>[!TAB Power BI 데스크톱]

1. 메뉴에서 **[!UICONTROL 홈]**&#x200B;을 선택한 다음 도구 모음에서 **[!UICONTROL 새로 고침]**&#x200B;을 선택하십시오. Customer Journey Analytics에서 방금 정의한 새 필터를 선택하려면 연결을 새로 고쳐야 합니다.

1. **[!UICONTROL 데이터]** 창:
   1. **[!UICONTROL 날짜 범위]**&#x200B;를 선택합니다.
   1. **[!UICONTROL product_category]**&#x200B;을(를) 선택하십시오.
   1. **[!UICONTROL product_name]**&#x200B;을(를) 선택하십시오.
   1. **[!UICONTROL 발생 횟수 합계]**&#x200B;를 선택합니다.

**[!UICONTROL 이 비주얼에 대한 데이터를 가져오는 동안 오류가 발생했습니다]**&#x200B;을(를) 표시하는 시각화가 표시됩니다.

1. **[!UICONTROL 필터]** 창:
   1. 이 시각적 개체의 **[!UICONTROL 필터]**&#x200B;에서 **[!UICONTROL filterName is (All)]**&#x200B;을(를) 선택하십시오.
   1. **[!UICONTROL 기본 필터링]**&#x200B;을(를) **[!UICONTROL 필터 형식]**(으)로 선택합니다.
   1. **[!UICONTROL 이 시각적 개체의 필터]**&#x200B;에서 **[!UICONTROL 날짜 범위는 (모두)]**&#x200B;입니다.
   1. **[!UICONTROL 고급 필터링]**&#x200B;을(를) **[!UICONTROL 필터 형식]**(으)로 선택합니다.
   1. **[!UICONTROL 값이]** **[!UICONTROL 이거나]** `1/1/2023` **[!UICONTROL 이거나]** **[!UICONTROL 이(가)]** `2/1/2023` 이전인 경우 항목 표시로 필터를 정의합니다.
   1. **[!UICONTROL product_category]**&#x200B;의 **[!UICONTROL 필터 형식]**(으)로 **[!UICONTROL 기본 필터]**&#x200B;을(를) 선택하고 가능한 값 목록에서 **[!UICONTROL Hunting]**&#x200B;을(를) 선택하십시오.
   1. ![열](/help/assets/icons/CrossSize75.svg)에서 **[!UICONTROL filterName]**&#x200B;을(를) 제거하려면 **[!UICONTROL CrossSize75]**&#x200B;을(를) 선택하십시오.
   1. ![열](/help/assets/icons/CrossSize75.svg)에서 **[!UICONTROL daterange]**&#x200B;을(를) 제거하려면 **[!UICONTROL CrossSize75]**&#x200B;을(를) 선택하십시오.

   적용된 **[!UICONTROL product_category]** 필터로 업데이트된 표가 표시됩니다. Power BI 데스크톱은 다음과 같아야 합니다.

   ![필터링할 날짜 범위 이름을 사용하는 Power BI 데스크톱](../assets/uc10-powerbi-final.png)



>[!TAB 타블로 데스크톱]

![AlertRed](/help/assets/icons/AlertRed.svg) Tableau Desktop은 Customer Journey Analytics에서 제품 범주의 동적 목록을 가져올 수 없습니다. 대신, 이 사용 사례에서는 **[!UICONTROL Hunting Products]**&#x200B;에 대해 새로 만든 필터를 사용하고 필터 이름 기준을 사용합니다.

1. **[!UICONTROL 데이터 Source]** 보기의 **[!UICONTROL 데이터]** 아래에서 **[!UICONTROL cc_data_view(prod:cja%3FLATTEN)]**&#x200B;의 컨텍스트 메뉴에서 **[!UICONTROL 새로 고침]**&#x200B;을 선택합니다. Customer Journey Analytics에서 방금 정의한 새 필터를 선택하려면 연결을 새로 고쳐야 합니다.
1. 하단의 **[!UICONTROL 시트 1]** 탭을 선택하여 **[!UICONTROL 데이터 원본]**&#x200B;에서 전환하세요. **[!UICONTROL 시트 1]** 보기에서:
   1. **[!UICONTROL 필터]** 셸프의 **[!UICONTROL 테이블]** 목록에서 **[!UICONTROL 필터 이름]** 항목을 드래그합니다.
   1. **[!UICONTROL 필터 \[필터 이름\]]** 대화 상자에서 **[!UICONTROL 목록에서 선택]**&#x200B;을 선택했는지 확인하고 목록에서 **[!UICONTROL 제품 사냥]**&#x200B;을 선택하십시오. **[!UICONTROL 적용]** 및 **[!UICONTROL 확인]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 필터]** 셸프의 **[!UICONTROL 테이블]** 목록에서 **[!UICONTROL Daterange]** 항목을 드래그합니다.
   1. **[!UICONTROL 필터 필드 \[Daterange\]]** 대화 상자에서 **[!UICONTROL 날짜 범위]**&#x200B;를 선택하고 **[!UICONTROL 다음 >]**&#x200B;을(를) 선택합니다.
   1. **[!UICONTROL 필터 \[Daterange\]]** 대화 상자에서 **[!UICONTROL 날짜 범위]**&#x200B;를 선택하고 `01/01/2023` - `1/2/2023`을(를) 선택합니다. **[!UICONTROL 적용]** 및 **[!UICONTROL 확인]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 테이블]** 목록에서 **[!UICONTROL 제품 이름]**&#x200B;을(를) **[!UICONTROL 행]**(으)로 드래그합니다.
   1. **[!UICONTROL 테이블]** 목록에서 **[!UICONTROL 발생 횟수]** 항목을 드래그하여 **[!UICONTROL 열]** 옆의 필드에 항목을 놓습니다. 값이 **[!UICONTROL SUM(발생 횟수)]**(으)로 변경됩니다.
   1. **[!UICONTROL 표시]**&#x200B;에서 **[!UICONTROL 텍스트 테이블]**&#x200B;을(를) 선택하십시오.
   1. **[!UICONTROL 맞춤]** 드롭다운 메뉴에서 **[!UICONTROL 맞춤]**&#x200B;을 선택합니다.

      Tableau Desktop은 다음과 같습니다.

      ![Tableau Desktop Multiple Dimension 등급 필터](../assets/uc10-tableau-final.png)

>[!TAB 조회자]

1. &#x200B;1. Looker의 **[!UICONTROL 탐색]** 인터페이스에서 연결을 새로 고치십시오. ![설정](/help/assets/icons/Setting.svg) **[!UICONTROL 캐시 지우기 및 새로 고침]**&#x200B;을 선택하십시오.
1. Looker의 **[!UICONTROL Explore]** 인터페이스에서 제대로 설정했는지 확인하십시오. 그렇지 않으면 ![설정](/help/assets/icons/Setting.svg) **[!UICONTROL 필드 및 필터 제거]**&#x200B;를 선택하십시오.
1. **[!UICONTROL 필터]** 아래의 **[!UICONTROL + 필터]**&#x200B;을(를) 선택하십시오.
1. **[!UICONTROL 필터 추가]** 대화 상자에서:
   1. **[!UICONTROL ‣Cc 데이터 보기 선택]**
   1. 필드 목록에서 **[!UICONTROL 날짜 범위 날짜]**‣을 선택한 다음 **[!UICONTROL 날짜 범위 날짜]**&#x200B;을 선택합니다.
      ![조회 필터](../assets/uc2-looker-filter.png)
1. **[!UICONTROL 이(가) 범위에 있으므로]** Cc 데이터 보기 날짜&#x200B;**[!UICONTROL 필터를 지정하십시오]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 까지(이전)]** **[!UICONTROL 2023/02/01]**.
1. 다른 필터를 추가하려면 **[!UICONTROL 필터]** 아래의 **[!UICONTROL + 필터]**&#x200B;을(를) 선택하십시오.
1. **[!UICONTROL 필터 추가]** 대화 상자에서:
   1. **[!UICONTROL ‣Cc 데이터 보기 선택]**
   1. 필드 목록에서 **[!UICONTROL ‣ 제품 범주]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL is]**&#x200B;을(를) 필터에 대한 선택으로 확인합니다.

![AlertRed](/help/assets/icons/AlertRed.svg) 조회 수에 **[!UICONTROL 제품 범주]**&#x200B;에 대해 가능한 값 목록이 표시되지 않습니다.

![고유 조회 수](../assets/uc10-looker-result.png)


>[!TAB Jupyter 전자 필기장]

1. 새 셀에 다음 문을 입력합니다.

   ```python
   data = %sql SELECT DISTINCT product_category FROM cc_data_view WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01';
   style = {'description_width': 'initial'}
   category_filter = widgets.Dropdown(
      options=[d for d, in data],
      description='Product Category:',
      style=style
   )
   display(category_filter)
   ```

1. 셀을 실행합니다. 아래 스크린샷과 비슷한 출력이 표시됩니다.

   ![Jupyter Notebook 결과](../assets/uc10-jupyter-input.png)

1. 드롭다운 메뉴에서 **[!UICONTROL Hunting]**&#x200B;을(를) 선택합니다.

1. 새 셀에 다음 문을 입력합니다.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               AND product_category = '{category_filter.value}' \
               GROUP BY 1 \
               ORDER BY Events DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. 셀을 실행합니다. 아래 스크린샷과 비슷한 출력이 표시됩니다.

   ![Jupyter Notebook 결과](../assets/uc10-jupyter-results.png)


>[!TAB 자습서]

1. 새 청크에 ` ` ``{r} `에서 ` `` ` ` 사이의 다음 문을 입력하십시오. 적절한 카테고리를 사용해야 합니다. 예: `Hunting`.

   ```R
   ## Dimension 1 Filtered by Dimension 2 value
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & product_category == "Hunting") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. 청크를 실행합니다. 아래 스크린샷과 비슷한 출력이 표시됩니다.

   ![라디오 결과](../assets/uc10-rstudio-results.png)

>[!ENDTABS]

+++

