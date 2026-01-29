---
title: 주의 사항
description: Customer Journey Analytics의 다양한 BI 도구의 BI 확장 경고
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# 주의 사항


지원되는 각 BI 도구에는 Customer Journey Analytics BI 확장을 사용할 때 몇 가지 주의 사항이 있습니다.

+++ BI 도구

>[!BEGINTABS]

>[!TAB Power BI 데스크톱]

* Power BI Desktop 고급 날짜 범위 필터링은 전용입니다.  종료 날짜의 경우 보고하려는 날짜가 지난 날짜를 선택해야 합니다. 예를 들어 **[!UICONTROL 이(가)]** `1/1/2023` **[!UICONTROL 다음]** `1/2/2023` 전후에 있습니다.
* 연결을 만들 때 Power BI Desktop의 기본값은 **[!UICONTROL 가져오기]**&#x200B;입니다. **[!UICONTROL 직접 쿼리]**&#x200B;를 사용하는지 확인하십시오.
* Power BI Desktop은 Power Query를 통해 데이터 변환을 표시합니다.  Power Query는 주로 가져오기 유형 연결에서 작동하므로 날짜 또는 문자열 함수와 같이 적용하는 많은 변환에서 가져오기 유형 연결로 전환해야 한다는 오류가 발생합니다.  쿼리 시간에 데이터를 변환해야 하는 경우 Power BI에서 변환 자체를 수행할 필요가 없도록 파생 차원 및 지표를 사용해야 합니다.
* Power BI Desktop이 날짜-시간 유형 열을 처리하는 방법을 이해하지 못하므로 **[!UICONTROL daterangehour *및&#x200B;*]**daterangeminute**[!UICONTROL 와 같은&#x200B;]**daterange**[!UICONTROL X ]**차원이 지원되지 않습니다.
* Power BI Desktop은 기본적으로 더 많은 쿼리 서비스 세션을 사용하여 여러 연결을 시도합니다.  프로젝트의 Power BI 설정으로 이동하여 병렬 쿼리를 비활성화합니다.
* Power BI Desktop은 모든 클라이언트측 정렬과 제한을 수행합니다. Power BI Desktop에는 연결된 값을 포함하는 상위 *X* 필터링에 대한 다른 의미 체계도 있습니다. 따라서 Analysis Workspace에서와 동일한 정렬 및 제한을 만들 수 없습니다.
* 이전 버전의 Power BI Desktop 2024년 10월 릴리스는 PostgreSQL 데이터 소스를 중단합니다. 이 문서에 언급된 버전을 사용해야 합니다.

>[!TAB 타블로 데스크톱]

* Tableau Desktop Range of Dates 필터링은 전용입니다. 종료 날짜의 경우 보고하려는 날짜가 지난 날짜를 선택해야 합니다.
* 기본적으로 시트의 행에 **[!UICONTROL Daterangemonth]**&#x200B;와 같은 날짜 또는 날짜-시간 차원을 추가하면 Tableau Desktop은 필드를 **[!UICONTROL YEAR()]** 함수로 래핑합니다.  원하는 항목을 얻으려면 해당 차원을 선택하고 드롭다운 메뉴에서 사용할 날짜 함수를 선택해야 합니다.  예를 들어 **[!UICONTROL Daterangemonth]**&#x200B;을(를) 사용하려는 경우 **[!UICONTROL Year]**&#x200B;을(를) **[!UICONTROL Month]**(으)로 변경합니다.
* 결과를 상위 *X*(으)로 제한하는 것은 Tableau Desktop에서 명확하지 않습니다. 결과를 명시적으로 제한하거나 계산 필드 및 **[!UICONTROL INDEX()]** 함수를 사용할 수 있습니다.  차원에 상위 *X* 필터를 추가하면 지원되지 않는 내부 조인을 사용하여 복잡한 SQL이 생성됩니다.

>[!TAB 조회자]

* Looker에는 노드당 최대 연결 수가 5~100개 사이여야 합니다.  이 값을 1로 설정할 수 없습니다.  이 설정은 Looker 연결이 사용 가능한 쿼리 서비스 세션 중 최소 5개를 항상 사용함을 의미합니다.
* 조회 기능을 사용하면 Customer Journey Analytics 데이터 보기를 기반으로 하는 보기를 사용하여 프로젝트를 만들 수 있습니다. 그런 다음 LookerML을 사용하여 데이터 보기에서 사용할 수 있는 차원 및 지표를 기반으로 모델을 만듭니다.  이 프로젝트 보기는 소스와 일치하도록 자동으로 업데이트되지 않습니다.  CJA 데이터 보기 차원, 지표, 계산된 지표 또는 세그먼트를 변경하거나 추가하는 경우 이러한 변경 사항은 자동으로 보기에 표시되지 않습니다.  프로젝트 보기를 수동으로 업데이트하거나 새 프로젝트를 만들어야 합니다.
* **[!UICONTROL 날짜 범위 날짜]** 또는 **[!UICONTROL 날짜 범위 날짜]**&#x200B;와 같은 날짜 또는 날짜-시간 필드에 대한 로커의 사용자 경험이 혼동됩니다.
* 검색자의 날짜 범위는 포괄적이 아닌 배타적입니다.  **[!UICONTROL until(before)]**&#x200B;이(가) 회색이므로 해당 측면을 놓칠 수 있습니다.  종료일의 경우 보고하려는 날의 지난 날짜를 선택해야 합니다.
* 조회 수는 지표를 자동으로 지표로 취급하지 않습니다.  지표를 선택하면 기본적으로 검색기가 지표를 쿼리의 차원으로 처리하려고 합니다.  지표를 지표로 처리하려면 위에 표시된 대로 사용자 지정 필드를 만들어야 합니다. 바로 가기로 **[!UICONTROL ⋮]**&#x200B;을(를) 선택하고 **[!UICONTROL 집계]**&#x200B;을(를) 선택한 다음 **[!UICONTROL 합계]**&#x200B;를 선택할 수 있습니다.

>[!TAB Jupyter 전자 필기장]

* Jupyter Notebook의 주요 주의 사항은 도구가 다른 BI 도구와 같은 드래그 앤 드롭 사용자 인터페이스가 아니라는 것입니다. 좋은 비주얼을 만들 수는 있지만, 이를 위해서는 코드를 작성해야 합니다.

>[!TAB 자습서]

* R 배포는 플랫 스키마에서 작동하므로 **[!UICONTROL FLATTEN]** 옵션이 필요합니다.
* RStudio의 주요 주의 사항은 도구가 다른 BI 도구처럼 드래그 앤 드롭 사용자 인터페이스가 아니라는 것입니다. 좋은 비주얼을 만들 수는 있지만, 이를 위해서는 코드를 작성해야 합니다.

>[!ENDTABS]

+++
