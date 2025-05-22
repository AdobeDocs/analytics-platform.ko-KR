---
description: Analysis Workspace 프로젝트를 클라우드 위치로 내보내는 방법에 대해 알아봅니다.
keywords: Analysis Workspace
title: Customer Journey Analytics 보고서를 클라우드로 내보내기
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: 0891aa2bed446e704b0222eff992c5f5bc200f82
workflow-type: tm+mt
source-wordcount: '2340'
ht-degree: 94%

---

# Customer Journey Analytics 보고서를 클라우드로 내보내기 {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Data Warehouse와 유사한 전체 테이블 내보내기 만들기"
>abstract="Analysis Workspace에서 데이터를 확인하는 즉시 전체 테이블 내보내기가 가능합니다. 필요에 따라 전체 테이블 내보내기를 만들거나 예약할 수 있습니다.<br><br>내보내기에 포함할 데이터를 이미 알고 있는 경우 전체 테이블 내보내기를 완료하는 데 몇 분밖에 걸리지 않습니다."

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics에서 Workspace 전체 테이블을 내보내고 지정된 클라우드 대상으로 내보낼 수 있습니다.

Customer Journey Analytics 보고서를 내보내는 다른 방법도 사용할 수 있으며, 자세한 내용은 [내보내기 개요](/help/analysis-workspace/export/export-project-overview.md)에서 설명합니다.

## 전체 테이블 내보내기 이해

Analysis Workspace에서 전체 테이블을 클라우드 공급자(예: Google, Azure, Amazon, Adobe)로 내보낼 수 있습니다.

[전체 테이블을 클라우드로 내보낼 때의 이점](#advantages-of-exporting-to-the-cloud)으로는 수백만 개의 행을 내보낼 수 있으며, 계산된 지표가 포함되고, 연결된 값으로 데이터 출력을 구조화하는 것이 가능합니다.

전체 테이블을 내보낼 때 다음 사항을 고려합니다.

* 클라우드 내보내기 전에 테이블, 환경 및 권한이 [내보내기 요구 사항](#export-requirements)을 충족하는지 확인합니다.

* 전체 테이블을 클라우드로 내보낼 때 일부 [기능](#unsupported-features) 및 [구성 요소](#unsupported-components)는 지원되지 않습니다.

전체 테이블을 클라우드로 내보낼 때는 다음 프로세스를 따릅니다.

1. [클라우드 계정 구성](/help/components/exports/cloud-export-accounts.md)

1. [계정에서 위치 구성](/help/components/exports/cloud-export-locations.md)

1. [Workspace에서 전체 테이블 내보내기](#export-full-tables-from-analysis-workspace)

1. [클라우드의 데이터 액세스](#view-exported-data-and-manifest-file) 및 [Adobe에서 내보내기 관리](/help/components/exports/manage-exports.md)

![1~4단계에서 설명한 전체 테이블 내보내기 프로세스.](assets/export-full-table-process.png)

## Analysis Workspace에서 전체 테이블 내보내기 {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="매니페스트 파일"
>abstract="이 기능을 활성화하면 모든 성공적인 내보내기 게재에 매니페스트 파일이 포함됩니다. 매니페스트 파일을 통해 모든 파일이 성공적으로 게재되었는지 확인할 수 있습니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>이 섹션에 설명된 대로 데이터를 내보내기 전에 위의 [전체 테이블 내보내기 이해](#understand-full-table-export) 섹션에서 전체 테이블 내보내기에 대해 자세히 알아보십시오.

Analysis Workspace에서 전체 테이블 내보내는 방법:

1. 아직 구성하지 않았다면 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md)에 설명된 대로 내보내기 계정과 위치를 구성합니다.

1. Analysis Workspace에서 내보내려는 데이터가 포함된 자유 형식 테이블을 마우스 오른쪽 버튼으로 클릭합니다.

1. [!UICONTROL **전체 테이블 내보내기**]&#x200B;를 선택합니다.

   ![전체 테이블 내보내기가 강조 표시된 자유 형식 테이블 드롭다운 메뉴.](assets/export-full-table.png)

1. [!UICONTROL **새 전체 테이블 내보내기**] 대화 상자에서 다음 정보를 지정합니다.

   | 필드 이름 | 함수 |
   |---------|----------|
   | 이름 | 내보내기 이름을 지정합니다. 이 이름은 내보내기 목록에 표시됩니다. |
   | 태그 | 기존 태그를 내보내기에 적용할 수도 있고, 새 태그를 만들어 적용할 수도 있습니다. <p>기존 태그를 내보내기에 적용하려면 드롭다운 메뉴에서 원하는 태그를 선택합니다. 사용자의 모든 태그를 적용할 수 있습니다<!-- double-check this -->.</p> <p>새로운 태그를 만들려면 새 태그의 이름을 입력한 다음 Enter를 누릅니다.</p><p>내보내기에 태그를 적용할 때 다음 사항을 고려합니다. <ul><li>적용한 태그는 내보내기 테이블에서 필터링하거나 검색할 수 있습니다.</li> <li>프로젝트에 적용된 태그는 전체 테이블을 내보낼 때 자동으로 적용되지 않습니다. 자세한 내용은 [내보내기 관리](/help/components/exports/manage-exports.md)의 “내보내기 페이지에서 열 구성”에 설명되어 있습니다. (또는 [내보내기에 전체 프로젝트를 예약](/help/analysis-workspace/export/t-schedule-report.md)하는 경우 프로젝트에 적용된 모든 태그가 자동으로 내보내기에 적용됩니다.) <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | 설명 | 내보내기에 설명을 추가합니다. 내보내기를 볼 때 [내보내기 페이지](/help/components/exports/manage-exports.md)에서 설명을 열로 볼 수 있습니다. |
   | 데이터 보기 | 내보내기에 포함할 구성 요소가 들어 있는 데이터 보기를 선택합니다. 데이터 보기 드롭다운 메뉴는 대화 상자의 왼쪽 상단에 있으며 데이터 보기 아이콘![데이터 보기 아이콘](assets/data-view-icon.png)으로 식별할 수 있습니다.  <p>**참고:** 데이터 테이블에 이미 포함된 구성 요소가 없는 데이터 보기를 선택하면 데이터 테이블을 지우고 선택한 데이터 보기에 포함된 구성 요소를 사용하여 다시 만들라는 메시지가 표시됩니다. </p> |
   | 전환 확인 기간 | 각 내보내기 파일에 포함할 보고 기간을 선택합니다. 옵션에는 [!UICONTROL **오늘**], [!UICONTROL **어제**], [!UICONTROL **지난 7일**], [!UICONTROL **지난 30일**], [!UICONTROL **이번 주**], [!UICONTROL **이번 달**]&#x200B;이 있습니다. <p>[!UICONTROL **내보내기 빈도**]&#x200B;를 [!UICONTROL **지금 보내기(일회성)**]&#x200B;로 설정한 경우 이 옵션은 표시되지 않습니다. |
   | 데이터 테이블 | 내보내고 있는 자유 형식 테이블을 표시합니다. 왼쪽 패널에서 테이블로 구성 요소를 끌어서 데이터 테이블을 수정할 수 있습니다. 캔버스에 구성 요소를 추가하면 테이블이 동적으로 업데이트됩니다.  <p>프로젝트의 전체 테이블에 적용된 모든 세그먼트는 테이블 각 열의 맨 위에 나타납니다.</p> |
   | 지우기 | 데이터 테이블의 내용을 지웁니다. 이렇게 하면 새 테이블 내보내기 대화 상자에서 직접 새 테이블 만들기를 시작할 수 있습니다. |
   | 내보내기 빈도 | 내보내기가 얼마나 자주 수행되어야 하는지 일정을 설정합니다. <p>[!UICONTROL **지금 보내기(일회성)**]&#x200B;를 선택하면 내보내기를 한 번만 보낼 수 있습니다. 이 옵션을 선택하면 내보내기가 즉시 시작됩니다.<p>또는 정의된 일정에 따라 내보내기를 보낼 수 있습니다. 일정에 따라 보낼 경우 옵션으로는 [!UICONTROL **매일**], [!UICONTROL **매주**], [!UICONTROL **매월 특정 주의 요일**], [!UICONTROL **매월 특정 날짜**], [!UICONTROL **매년 특정 월의 특정 요일**], [!UICONTROL **매년 특정 날짜**]&#x200B;가 있습니다. </p><p>내보내기 빈도를 선택할 때 다음 사항을 고려합니다.</p><ul><li>[!UICONTROL **전환 확인 기간**] 필드의 옵션은 여기에서 선택한 내용에 따라 달라집니다.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>선택한 옵션에 따라 추가 구성 필드가 표시됩니다.</li></ul> |
   | 시작 날짜 | 예약된 내보내기가 시작되어야 하는 날짜 및 시간. <p>이 옵션은 예약된 내보내기 빈도를 선택할 때만 사용할 수 있습니다.</p> |
   | 종료 날짜 | 예약된 내보내기가 만료되는 날짜 및 시간. 예약된 내보내기 작업은 설정한 날짜 및 시간 이후에는 더 이상 실행되지 않습니다. <p>이 옵션은 예약된 내보내기 빈도를 선택할 때만 사용할 수 있습니다.</p> |
   | 파일 포맷 | 내보낼 데이터가 .csv인지 .json인지 선택합니다. |
   | 매니페스트 파일 포함 | 이 기능을 활성화하면 모든 성공적인 내보내기 게재에 매니페스트 파일이 포함됩니다. 매니페스트 파일을 통해 모든 파일이 성공적으로 게재되었는지 확인할 수 있습니다. 다음과 같은 정보가 포함됩니다.<ul><li>게재된 모든 파일의 목록</li><li>각 파일의 MD5 체크섬</li></ul><p>내보낸 데이터는 구성한 클라우드 대상에 압축 파일로 제공됩니다. 자세한 내용은 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md) 및 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md)에 설명되어 있습니다.</p><p>압축 파일의 파일 이름은 파일 형식으로 CSV 또는 JSON을 선택했는지에 따라 다음과 같습니다.</p><ul><li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li></ul><p>위의 [!UICONTROL **파일 형식**] 필드에서 파일 형식을 선택합니다.</p> |
   | 계정 | 데이터를 전송할 클라우드 내보내기 계정을 선택합니다. <p>또는 사용하려는 클라우드 계정을 아직 구성하지 않은 경우 새 계정을 구성할 수 있습니다.<ol><li>[!UICONTROL **계정 추가**]&#x200B;를 선택하고 다음 정보를 지정합니다.<ul><li>[!UICONTROL **위치 계정 이름**]: 위치 계정의 이름을 지정합니다. 위치가 생성되면 이 이름이 표시됩니다. </li><li>[!UICONTROL **위치 계정 설명**]: 동일한 계정 유형의 다른 계정과 구분할 수 있도록 계정에 대한 간단한 설명을 제공합니다.</li><li>[!UICONTROL **계정 유형**]: 내보내려는 클라우드 계정 유형을 선택합니다. 사용 가능한 계정 유형은 Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake, AEP 데이터 랜딩 존입니다.</li></ul><li>계정 구성을 완료하려면 선택한 [!UICONTROL **계정 유형**]&#x200B;에 해당하는 아래 링크에서 계속합니다.<ul><li>[AEP 데이터 랜딩 영역](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | 위치 | 내보내기 데이터를 보낼 계정의 위치를 선택합니다.<p>또는 선택한 계정에서 사용하려는 위치를 아직 구성하지 않은 경우 새 위치를 구성할 수 있습니다.<ol><li>[!UICONTROL **위치 추가**]&#x200B;를 선택하고 다음 정보를 지정합니다. <ul><li>[!UICONTROL **이름**]: 위치 이름.</li><li>[!UICONTROL **설명**]: 계정의 다른 위치와 구분할 수 있도록 위치에 대한 간단한 설명을 제공합니다.</li><li>[!UICONTROL **위치 계정**]: 위치를 만들려는 계정을 선택합니다.</li></ul><li>위치 구성을 완료하려면 [!UICONTROL **위치 계정**] 필드에서 선택한 계정 유형에 해당하는 아래 링크를 계속 진행합니다.<ul><li>[AEP 데이터 랜딩 영역](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. 내보내기를 저장하려면 [!UICONTROL **저장**]&#x200B;을 선택합니다.

   데이터는 사용자가 지정한 빈도로 지정한 클라우드 계정으로 전송됩니다.

1. (선택 사항) 내보내기를 만든 후 지금 보내기로 선택했든 정의된 일정에 따라 보내기로 선택했든 [내보내기 페이지](/help/components/exports/manage-exports.md)에서 보고 관리할 수 있으며 [내보내기 로그](/help/components/exports/manage-export-logs.md)에서 볼 수 있습니다.</p>

## 내보내기 관리

Analysis Workspace에서 데이터를 내보낸 후에는 기존 내보내기를 편집, 다시 내보내기, 복제, 태그 지정 또는 삭제할 수 있습니다. 자세한 내용은 [내보내기 관리](/help/components/exports/manage-exports.md)에 설명되어 있습니다.

## 클라우드로 내보낼 때의 이점 {#advantages}

Customer Journey Analytics 데이터를 클라우드로 내보내면 다음 작업이 가능합니다.

* Adobe Experience Platform 데이터 랜딩 영역, Google Cloud Platform, Microsoft Azure, Amazon S3 또는 Snowflake와 같은 공유 위치로 내보냅니다.

* 대량의 내역 데이터를 저장합니다.

  이러한 유형의 데이터는 장기적인 추세를 감지하여 비즈니스 인텔리전스를 확보하고 궁극적으로 더 나은 비즈니스 의사 결정으로 이어질 수 있습니다.

* 수천 개 또는 수백만 개의 행(라이선스 유형에 따라 300만, 3천만, 1억 5천만, 3억 개의 행)이 포함된 전체 테이블을 내보냅니다. 그 밖의 내보내기 방법에서는 최대 50,000개의 행이 허용됩니다.

* 내보낸 Customer Journey Analytics 데이터에 계산된 지표를 포함합니다.

* 연결된 값으로 데이터 출력을 구조화합니다.

* 한 번만 또는 일정에 따라 내보냅니다. (또한 [그 밖의 내보내기 옵션](/help/analysis-workspace/export/export-project-overview.md)으로 사용 가능.)

* CSV 또는 JSON 형식으로 파일을 내보냅니다. (또한 [그 밖의 내보내기 옵션](/help/analysis-workspace/export/export-project-overview.md)으로 사용 가능.)

* 여러 차원을 포함하는 테이블을 내보냅니다.

## 내보내기 요구 사항 {#export-requirements}

### 최소 요구 사항

테이블, 환경 및 권한이 다음 요구 사항을 충족하는지 확인합니다.

* **테이블:** 전체 테이블 내보내기를 지원하려면 모든 테이블의 행에 하나 이상의 차원과 각 열에 하나 이상의 지표가 포함되어야 합니다.

* **환경:** Customer Journey Analytics에서 사용하는 [IP 주소](/help/technotes/ip-addresses.md)와 [도메인](/help/technotes/domains.md)이 해당 조직의 방화벽을 통과할 수 있는지 확인합니다.

* **권한:** Adobe Admin Console에서 사용자에게 전체 테이블을 내보내려면 [!UICONTROL **전체 테이블 내보내기**] 권한이 할당된 제품 프로필이 지정되어야 합니다. Admin Console에서 제품 프로필에 대한 권한을 할당하는 방법에 대한 자세한 내용은 [Admin Console에서 Customer Journey Analytics 권한](/help/technotes/access-control.md)을 참조하십시오.

  >[!NOTE]
  >
  >  [제품 관리자 역할](/help/technotes/access-control.md#product-admin-role)이 할당된 사용자는 항상 전체 테이블을 내보낼 수 있는 권한이 있으므로 [!UICONTROL **전체 테이블 내보내기**] 권한을 할당받을 필요가 없습니다.


### 지원되지 않는 기능

다음 기능은 지원되지 않으며 전체 테이블 내보내기에서 자동으로 제거됩니다.

* 백분율
* 총계
* 검색 필터링
* 정적 행
* 날짜 정렬
* 요약 데이터 세트의 지표
* 동적 차원 항목

  동적 차원 항목은 자유 형식 테이블의 열 헤더에 차원을 놓을 때 생성되므로 열이 상위 5개 차원 항목에 의해 동적으로 필터링됩니다. Analysis Workspace에서 이러한 상위 5개 차원 항목은 프로젝트를 로드할 때마다 업데이트됩니다. 전체 테이블 내보내기에서 이러한 차원 항목은 정적이 됩니다. 자세한 내용은 [자유 형식 테이블의 동적 차원 항목과 정적 차원 항목](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)을 참조하십시오.
* 첫 번째 분류의 차원은 변환되어 내보낸 테이블 행의 보조 차원으로 추가되며, 다른 분류는 테이블에 포함되지 않습니다
* 대부분의 데이터 세트에서는 정렬이 지원되지 않습니다. 소규모 데이터 세트의 경우 데이터가 정렬될 수 있습니다.

### 지원되지 않는 구성 요소

다음 구성 요소는 지원되지 않으며, Analysis Workspace에서 전체 테이블 내보내기를 수행할 때 테이블에서 이러한 구성 요소를 제거하라는 메시지를 표시합니다.

* 지표 정의에서 기본 또는 고급 함수를 사용하는 계산된 지표(자세한 내용은 [기본 함수](/help/components/calc-metrics/cm-functions.md) 및 [고급 함수](/help/components/calc-metrics/cm-adv-functions.md) 참조)
* 관리자가 제한한 구성 요소의 내보내기 제한(자세한 내용은 [레이블 및 정책](/help/data-views/data-governance.md)의 *데이터 보기의 데이터 거버넌스 정책에 대한 세그먼트* 섹션 참조)
* 다음 모든 기준을 충족하는 차원:
   * [오브젝트 배열](/help/use-cases/object-arrays.md)의 일부인 필드에서 생성(Adobe Analytics의 다중 값 변수와 유사)
   * [지속성 활성화](/help/data-views/component-settings/persistence.md)
   * [바인딩 차원](/help/use-cases/data-views/binding-dimensions-metrics.md)을 사용하지 않음
* 다양한 [오브젝트 배열](/help/use-cases/object-arrays.md)을 참조하는 필드에서 나온 여러 차원. (동일한 오브젝트 배열을 참조하는 여러 차원이 허용됨.)
* 보고서당 10개 이상의 차원과 10개의 지표 (최대 10개의 차원과 10개의 지표가 지원됨)
* 테이블 열:
   * 날짜 범위
   * 차원
* 테이블 행:
   * 계산된 지표
   * 지표
   * 날짜 범위
   * 세그먼트

### 속성 행동

전체 테이블 내보내기는 비기본 속성 모델을 사용하는 계산된 지표를 지원합니다([열 설정](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)의 *비기본 속성 모델 사용* 섹션 설명 참조).

보고서에 비기본 속성 모델이 사용되는 경우 보고서에 사용되는 할당 모델은 보고서에 단일 차원이 있는지 또는 여러 차원이 있는지에 따라 무시되거나 유지됩니다.

* **단일 차원에서 지표 속성을 포함하는 보고서의 경우**: [지표 속성](/help/data-views/component-settings/attribution.md)은 일반적으로 [지표 속성](/help/data-views/component-settings/persistence.md)을 사용할 때 수행되는 할당 모델을 재정의합니다.

  예를 들어 “첫 번째 터치” 지표 속성은 “가장 최근” 차원 할당을 재정의합니다.

* **동시에 여러 차원에 대한 지표 속성을 포함하는 보고서의 경우:** [지표 속성](/help/data-views/component-settings/attribution.md)은 차원 [할당 모델](/help/data-views/component-settings/persistence.md)과 함께 적용됩니다.

  예를 들어 “가장 최근” 차원 할당과 함께 “첫 번째 터치” 지표 속성이 적용됩니다. 또한 지표 속성은 일반적으로 자유 형식 테이블에서 수행되는 각 차원 항목에 독립적으로 적용되는 것과 달리, 단일 차원 항목처럼 사후 할당된 차원 항목 쌍에 적용됩니다.

  >[!NOTE]
  >
  >다차원 보고서는 이 문서에서 설명한 대로 클라우드 데이터를 내보낼 때만 지원됩니다.

## 전체 테이블 내보내기(Customer Journey Analytics)와 Data Warehouse(Adobe Analytics) 비교 {#comparison}

이전에 Data Warehouse를 사용하여 Adobe Analytics 데이터를 내보낸 적이 있다면 다음 테이블을 통해 Customer Journey Analytics에서 전체 테이블을 내보내는 것과 Adobe Analytics에서 Data Warehouse로 데이터를 내보내는 것의 차이점을 이해할 수 있습니다.


| 기능 | Customer Journey Analytics에서 전체 테이블 내보내기 | Adobe Analytics의 Data Warehouse |
|---------|----------|---------|
| 사용자 정의 보고서 빌드 | 예 | 예 |
| 계산된 지표 | 예 | 아니요 |
| 세그먼트 | 예 | 제한적 |
| 차원 | 10의 제한 | 제한 없음 |
| 지표 | 10의 제한 | 제한 없음 |
| 보고 행 | 등급에 따라 300만, 3천만, 1억 5천만, 3억으로 제한 | 제한 없음 |
| 보고서 수 | 제한 없음 | 제한 없음 |
| 임시(일회) 게재 | 예 | 예 |
| 반복 게재 일정 | 예 | 예 |
| 이메일 게재 | 아니요 | 예 |
| FTP / SFTP | 아니요 | 이전 지원 |
| Azure | 예 | 예 |
| Amazon S3 | 예 | 예 |
| Google Cloud Platform | 예 | 예 |
| Snowflake | 예 | 아니요 |
| 게재 빈도 | 일별 | 시간별 |
