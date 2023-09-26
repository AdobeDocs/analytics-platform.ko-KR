---
description: Analysis Workspace 프로젝트를 클라우드 위치로 내보냅니다.
keywords: Analysis Workspace
title: 클라우드로 Customer Journey Analytics 보고서 내보내기
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: 5ab26cec464051ace651d3ac9c2942f671b0df92
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 4%

---

# 클라우드로 Customer Journey Analytics 보고서 내보내기

Customer Journey Analytics에서 작업 영역 전체 테이블을 내보내고 내보내기를 지정된 클라우드 대상으로 보낼 수 있습니다.

에 설명된 대로 Customer Journey Analytics 보고서를 내보내는 다른 방법도 사용할 수 있습니다 [내보내기 개요](/help/analysis-workspace/export/export-project-overview.md).

## Analysis Workspace에서 전체 테이블 내보내기

>[!NOTE]
>
>이 섹션에 설명된 대로 데이터를 내보내려면 먼저 테이블이 [내보내기 요구 사항](#export-requirements).

Analysis Workspace에서 전체 테이블을 내보내려면 다음을 수행합니다.

1. 에 설명된 대로 내보내기 계정 및 위치를 아직 구성하지 않은 경우 구성합니다 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md).

1. Analysis Workspace에서 내보낼 데이터가 포함된 자유 형식 테이블을 마우스 오른쪽 단추로 클릭합니다.

1. 선택 [!UICONTROL **전체 테이블 내보내기**].

   ![전체 테이블 내보내기](assets/export-full-table.png)

1. 다음에서 [!UICONTROL **새 전체 테이블 내보내기**] 대화 상자에서 다음 정보를 지정합니다.

   | 필드 이름 | 함수 |
   |---------|----------|
   | 이름 | 내보낼 이름을 지정합니다. 이 이름은 내보내기 목록에 표시됩니다. |
   | 태그 | 내보내기에 기존 태그를 적용하거나 새 태그를 만들어 적용할 수 있습니다. <p>내보내기에 기존 태그를 적용하려면 드롭다운 메뉴에서 태그를 선택합니다. 회사의 모든 태그를 적용할 수 있습니다.<!-- double-check this -->.</p> <p>새 태그를 만들려면 새 태그의 이름을 입력한 다음 Enter 키를 누릅니다.</p><p>내보내기에 태그를 적용할 때는 다음 사항을 고려하십시오. <ul><li>적용하는 태그는 내보내기 테이블에서 필터링하거나 검색할 수 있습니다.</li> <li>의 &quot;내보내기 페이지의 열 구성&quot;에 설명된 대로 전체 테이블을 내보낼 때 프로젝트에 적용된 태그는 자동으로 적용되지 않습니다. [내보내기 관리](/help/components/exports/manage-exports.md). (또는 [내보내기를 위한 전체 프로젝트 예약](/help/analysis-workspace/export/t-schedule-report.md)프로젝트에 적용된 모든 태그는 내보내기에 자동으로 적용됩니다.)  <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | 설명 | 내보내기에 설명을 추가합니다. 설명을 의 열로 보도록 선택할 수 있습니다. [내보내기 페이지](/help/components/exports/manage-exports.md) 내보내기를 볼 때. |
   | 데이터 보기 | 내보내기에 포함할 구성 요소가 포함된 데이터 보기를 선택합니다. 데이터 보기 드롭다운 메뉴는 대화 상자의 왼쪽 상단 모서리에 있으며 데이터 보기 아이콘으로 식별할 수 있습니다![데이터 보기 아이콘](assets/data-view-icon.png).  <p>**참고:** 데이터 테이블에 이미 포함된 구성 요소가 누락된 데이터 보기를 선택하면 데이터 테이블을 지우고 선택한 데이터 보기에 포함된 구성 요소를 사용하여 데이터 테이블을 다시 작성하라는 메시지가 표시됩니다. </p> |
   | 전환 확인 기간 | 각 내보내기 파일에 포함할 보고 기간을 선택합니다. 옵션은 다음과 같습니다 [!UICONTROL **오늘**], [!UICONTROL **어제**], [!UICONTROL **지난 7일**], [!UICONTROL **지난 30일**], [!UICONTROL **이번 주**], 및 [!UICONTROL **이번 달**]. |
   | 지우기 | 데이터 테이블의 내용을 지웁니다. 이렇게 하면 새 전체 테이블 내보내기 대화 상자 내에서 직접 새 테이블 빌드를 시작할 수 있습니다. |
   | 내보내기 빈도 | 내보내기가 발생하는 빈도에 대한 일정을 설정합니다. <p>다음을 선택할 수 있습니다. [!UICONTROL **지금 보내기(한 번)**] 내보내기를 한 번만 보냅니다. 이 옵션을 선택하면 내보내기가 즉시 시작됩니다.<p>또는 정의된 일정에 따라 내보내기를 전송하도록 선택할 수 있습니다. 일정에 따라 보낼 때 옵션은 다음과 같습니다 [!UICONTROL **매일**], [!UICONTROL **매주**], [!UICONTROL **요일별 월간**], [!UICONTROL **매월(날짜 기준)**], [!UICONTROL **연간 날짜(월 기준)**], 및 [!UICONTROL **특정 날짜별 연간**]. </p><p>내보내기 빈도를 선택할 때는 다음 사항을 고려하십시오.</p><ul><li>의 옵션 [!UICONTROL **전환 확인 기간**] 여기서 선택한 항목에 따라 필드가 변경됩니다.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>선택한 옵션에 따라 추가 구성 필드가 표시됩니다.</li></ul> |
   | 에 시작 | 예약된 내보내기가 시작되는 날짜 및 시간입니다. <p>이 옵션은 예약된 내보내기 빈도를 선택하는 경우에만 사용할 수 있습니다.</p> |
   | 종료 일자 | 예약된 내보내기가 만료되는 날짜 및 시간입니다. 예약된 내보내기는 설정한 날짜 및 시간 이후에 더 이상 실행되지 않습니다. <p>이 옵션은 예약된 내보내기 빈도를 선택하는 경우에만 사용할 수 있습니다.</p> |
   | 파일 형식 | 내보낸 데이터가 .csv 형식이어야 하는지 .json 형식이어야 하는지 선택합니다. |
   | 계정 | 데이터를 전송할 클라우드 내보내기 계정을 선택합니다. <p>자세한 내용은 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md).</p> |
   | 위치 이름 | 계정에서 내보내기 데이터를 보낼 위치를 선택합니다. <p>자세한 내용은 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md).</p><p>다음을 선택할 수 있습니다. [!UICONTROL **새 위치 추가**] 단추를 클릭하여 기존 내보내기 계정에 대한 새 위치를 만듭니다. |

   {style="table-layout:auto"}

1. 선택 [!UICONTROL **저장**] 내보내기를 저장합니다.

   데이터는 지정한 빈도로 지정한 클라우드 계정으로 전송됩니다.

1. (선택 사항) 내보내기를 만든 후에 지금 보내도록 선택했는지 정의된 일정에 따라 보내도록 선택했는지에 관계없이 [내보내기 페이지](/help/components/exports/manage-exports.md) 및 다음에서 보기: [로그 내보내기](/help/components/exports/manage-export-logs.md).</p>

## 클라우드로 내보내기의 장점

Customer Journey Analytics 데이터를 클라우드로 내보내면 다음 작업을 수행할 수 있습니다.

* Adobe Experience Platform 데이터 랜딩 영역, Google Cloud Platform, Microsoft Azure, Amazon S3 또는 Snowflake과 같은 공유 위치로 내보냅니다.

* 대량의 내역 데이터를 저장합니다.

  이러한 유형의 데이터는 비즈니스 인텔리전스를 얻고 궁극적으로 더 나은 비즈니스 의사 결정을 이끌어내기 위해 장기적인 추세를 감지하는 데 사용할 수 있습니다.

* 수천 또는 수백만 개의 행(라이선스 유형에 따라 300만, 3000만 또는 1억 5000만 행)이 포함된 전체 테이블을 내보냅니다. 다른 내보내기 방법을 사용하면 최대 50,000개의 행을 사용할 수 있습니다.

* 내보낸 Customer Journey Analytics 데이터에 계산된 지표를 포함합니다.

* 연결된 값으로 데이터 출력을 구조화합니다.

* 애드혹 또는 일정에 따라 내보냅니다. (또한 [기타 내보내기 옵션](/help/analysis-workspace/export/export-project-overview.md).)

* CSV 또는 JSON 형식으로 파일을 내보냅니다. (또한 [기타 내보내기 옵션](/help/analysis-workspace/export/export-project-overview.md).)

* 여러 차원이 포함된 표를 내보냅니다.

## 내보내기 요구 사항 {#export-requirements}

### 최소 요구 사항

전체 테이블 내보내기를 지원하려면 테이블에 행에 하나 이상의 차원이 포함되어야 하며 각 열에 하나의 지표가 있어야 합니다.

관리자는에 나열된 IP 주소를 확인해야 합니다. [Customer Journey Analytics에서 사용하는 IP 주소](/help/admin/ip-addresses.md) 방화벽 허용 목록에 포함됩니다.

### 지원되지 않는 기능

다음 기능은 지원되지 않으며 전체 테이블 내보내기에서 자동으로 제거됩니다.

* 백분율
* 총계
* 검색 필터링
* 정적 행
* 날짜 정렬
* 동적 차원

  자세한 내용은 [자유 형식 테이블의 동적 차원 항목과 정적 차원 항목 비교](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* 첫 번째 분류의 Dimension은 변환된 후 내보낸 테이블의 행에 보조 차원으로 추가됩니다. 다른 모든 분류는 테이블에 포함되지 않습니다
* 대부분의 데이터 세트에서는 정렬이 지원되지 않습니다. 작은 데이터 세트에서는 데이터를 정렬할 수 있습니다

### 지원되지 않는 구성 요소

다음 구성 요소는 지원되지 않으며, Analysis Workspace은 전체 테이블 내보내기를 수행할 때 테이블에서 해당 구성 요소를 제거하라는 메시지를 표시합니다.

* 지표 정의에서 기본 또는 고급 함수를 사용하는 계산된 지표( 참조) [기본 함수](/help/components/calc-metrics/cm-functions.md) 및 [고급 함수](/help/components/calc-metrics/cm-adv-functions.md) 추가 정보)
* 관리자가 제한한 구성 요소의 내보내기 제한( *데이터 보기에서 데이터 거버넌스 정책 필터링* 의 섹션 [레이블 및 정책](/help/data-views/data-governance.md) 추가 정보)
* 보고서당 5개 이상의 차원과 5개의 지표(최대 5개의 차원과 5개의 지표가 지원됨)
* 테이블 열:
   * 날짜 범위
   * 차원
* 테이블 행에서:
   * 계산된 지표
   * 지표
   * 날짜 범위
   * 필터

### 속성 동작

전체 테이블 내보내기는 다음에 설명된 대로 기본값이 아닌 속성 모델을 사용하는 계산된 지표를 지원합니다. *기본이 아닌 속성 모델 사용* 의 섹션 [열 설정](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)).

보고서에서 기본값이 아닌 속성 모델을 사용하는 경우 보고서에 단일 차원이 있는지 아니면 여러 차원이 있는지에 따라 보고서에서 사용 중인 할당 모델이 무시되거나 유지됩니다.

* **단일 차원에 지표 속성을 포함하는 보고서의 경우:** [지표 속성](/help/data-views/component-settings/attribution.md) 재정의 [배분 모델](/help/data-views/component-settings/persistence.md) 일반적으로 지표 속성을 사용할 때 수행됩니다.

  예를 들어 &quot;첫 번째 터치&quot; 지표 속성은 &quot;가장 최근&quot; 차원 할당을 무시합니다.

* **동시에 여러 차원에 대한 지표 속성을 포함하는 보고서의 경우:** [지표 속성](/help/data-views/component-settings/attribution.md) 은 차원에 추가됩니다 [배분 모델](/help/data-views/component-settings/persistence.md).

  예를 들어 &quot;가장 최근&quot; 차원 할당 외에 &quot;첫 번째 터치&quot; 지표 속성이 적용됩니다. 또한 지표 속성은 일반적으로 자유 형식 테이블에서 수행되는 것처럼 각 차원 항목에 독립적으로 적용되는 것이 아니라, 단일 차원 항목인 것처럼 사후 할당된 차원 항목 쌍에 적용됩니다.

  >[!NOTE]
  >
  >다차원 보고서는 이 문서에 설명된 대로 데이터를 클라우드로 내보낼 때만 지원됩니다.

## 내보내기 관리

Analysis Workspace에서 데이터를 내보낸 후에 설명된 대로 기존 내보내기를 편집, 재내보내기, 복제, 태그 지정 또는 삭제할 수 있습니다. [내보내기 관리](/help/components/exports/manage-exports.md).

## 내보낸 데이터 및 매니페스트 파일 보기

### 내보낸 데이터

내보낸 데이터는에 설명된 대로 구성한 클라우드 대상에서 압축 파일로 사용할 수 있습니다 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md) 및 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md).

압축 파일의 파일 이름은 파일 형식으로 CSV 또는 JSON을 선택했는지 여부에 따라 다음과 같습니다.

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>파일 형식은 [!UICONTROL **파일 형식**] 에 설명된 대로 테이블을 내보낼 때 필드 [Analysis Workspace에서 전체 테이블 내보내기](#export-full-tables-from-analysis-workspace).

### 매니페스트 파일

파일 이름이 인 매니페스트 파일 `cja-export-{reportInstanceId}-{idx}.json.gz` 하나 이상의 파일이 포함된 성공적인 내보내기 게재에 포함됩니다. 매니페스트 파일을 사용하면 모든 파일이 성공적으로 배달되었는지 확인할 수 있습니다. 여기에는 다음 정보가 포함됩니다.

* 게재된 모든 파일 목록

* 각 파일의 크기

* 각 파일의 타임스탬프

<!-- add in  what the file name, structure, and file format will be -->

## 전체 테이블 내보내기(Customer Journey Analytics) 대 Data Warehouse(Adobe Analytics) 비교

이전에 Data Warehouse을 사용하여 Adobe Analytics 데이터를 내보낸 경우 다음 표를 통해 Customer Journey Analytics에서 전체 표를 내보내는 것과 Adobe Analytics에서 Data Warehouse을 사용하여 데이터를 내보내는 것의 차이점을 파악할 수 있습니다.


| 기능 | Customer Journey Analytics에서 전체 테이블 내보내기 | Adobe Analytics의 Data Warehouse |
|---------|----------|---------|
| 사용자 지정 보고서 작성 | 예 | 예 |
| 계산된 지표 | 예 | 아니요 |
| 세그먼트 | 예 | 제한적 |
| 차원 | 5 제한 | 제한 없음 |
| 지표 | 5 제한 | 제한 없음 |
| 행 보고 | 계층에 따라 300만, 3000만, 1억 5000만 또는 3억 제한 | 제한 없음 |
| 보고서 수 | 제한 없음 | 제한 없음 |
| 애드혹 게재 | 예 | 예 |
| 반복 게재 예약 | 예 | 예 |
| 이메일 게재 | 아니요 | 예 |
| FTP / SFTP | 아니요 | 레거시 지원 |
| Azure | 예 | 예 |
| Amazon S3 | 예 | 예 |
| Google Cloud 플랫폼 | 예 | 예 |
| Snowflake | 예 | 아니요 |
| 게재 빈도 | 일별 | 시간별 |
