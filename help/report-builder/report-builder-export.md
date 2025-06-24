---
title: Report Builder에서 보고서 내보내기
description: Report Builder에서 보안 대상으로 데이터를 내보내는 방법을 설명합니다.
role: User, Admin
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 1d5d87d8-1920-406b-8cce-41b89b7ae70b
source-git-commit: 5a0cb6fa221282b70df5efb58362855ff58f76b8
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 38%

---

# 클라우드 대상으로 내보내어 통합 문서 예약

Report Builder의 Customer Journey Analytics 통합 문서를 Google, Azure 및 Amazon과 같은 클라우드 공급자로 내보낼 수 있습니다.

[Report Builder에서 클라우드로 보고서를 내보낼 수 있는 이점](#advantages-of-exporting-to-the-cloud)에는 서드파티 도구에서 보고서를 사용하거나 외부 데이터와 결합하는 기능이 있습니다.

Report Builder에서 클라우드 대상으로 통합 문서를 내보내기 전에 데이터 블록, 환경 및 권한이 [내보내기 요구 사항](#export-requirements)을 충족하는지 확인하십시오.

## 내보내기 프로세스 이해

Report Builder에서 클라우드로 통합 문서를 내보낼 때 다음 프로세스를 사용하십시오.

1. [클라우드 계정 구성](/help/components/exports/cloud-export-accounts.md)

1. [계정에서 위치 구성](/help/components/exports/cloud-export-locations.md)

1. [Report Builder에서 보고서 내보내기](#export-a-report-from-report-builder)

1. 클라우드 계정의 데이터에 액세스하고 [Adobe에서 내보내기를 관리합니다](/help/components/exports/manage-exports.md)

![1~4단계에 설명된 내보내기 프로세스입니다.](assets/report-builder-export-process.png)

## Report Builder에서 보고서 내보내기

>[!NOTE]
>
>이 섹션에 설명된 대로 데이터를 내보내기 전에 위의 섹션에서 [내보내기 프로세스](#understand-the-export-process)에 대해 자세히 알아보세요.

Report Builder에서 보고서를 내보내려면 다음을 수행하십시오.

1. 아직 구성하지 않았다면 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md)에 설명된 대로 내보내기 계정과 위치를 구성합니다.

1. 내보낼 데이터가 포함된 Excel 스프레드시트에서 **[!UICONTROL Adobe Report Builder]** 오른쪽 패널을 엽니다.

1. [!UICONTROL **일정**]&#x200B;을 선택하세요.

<!-- add screenshot -->

1. **[!UICONTROL 통합 문서]** 탭에서 더하기 아이콘을 선택하여 새 일정을 만듭니다

   ![Report Builder 일정 탭](assets/report-builder-schedule-cloud.png)

   또는

   이미 만든 일정으로 통합 문서를 내보내려면 일정 목록에서 일정을 선택한 다음 **[!UICONTROL 일정에 따라 보내기]**&#x200B;를 선택합니다.

1. [!UICONTROL **Adobe Report Builder**] 오른쪽 패널에서 다음 정보를 지정하여 새 일정을 계속 만듭니다.

   | 필드 이름 | 함수 |
   |---------|----------|
   | **[!UICONTROL 파일]** | 현재 내보내기 위해 선택한 통합 문서 파일을 표시합니다. 현재 통합 문서를 선택하지 않은 경우 파일 이름 옆에 있는 통합 문서 아이콘 ![TableSelect](/help/assets/icons/TableSelect.svg)을(를) 선택하여 선택합니다. |
   | **[!UICONTROL 파일 이름]** <!--should be File name --> | 통합 문서를 내보내기 전에 파일 이름을 변경할 수 있습니다.<p>통합 문서 파일 이름은 기본적으로 통합 문서의 이름으로 설정됩니다</p> |
   | **[!UICONTROL 파일 형식]** | 내보낸 파일의 파일 유형을 선택합니다. Excel, PDF 또는 CSV를 선택할 수 있습니다. <p>**[!UICONTROL CSV]**&#x200B;을(를) 선택하면 예약된 통합 문서가 ZIP 첨부 파일로 전송됩니다. 일부 회사 이메일 관리자는 ZIP 첨부 파일이 있는 이메일을 차단할 수 있습니다. 그에 따라 경고가 표시됩니다.</p> |
   | **[!UICONTROL 파일 이름에 타임스탬프 추가]** | 통합 문서가 업데이트된 날짜를 식별하기 위해 파일 이름에 타임스탬프를 추가하려면 이 옵션을 선택합니다. 타임스탬프는 특정 날짜에 전송된 통합 문서의 버전을 확인하는 데 유용합니다. 선택하면 다음 중 하나를 선택할 수 있습니다. |
   | **[!UICONTROL 파일 이름 미리 보기]** <!--should be File name preview --> | 내보내기 후 파일 이름이 표시되는 방식의 미리보기를 표시합니다. |
   | **[!UICONTROL 통합 문서 암호 보호]** | 암호를 가진 사용자만 액세스할 수 있도록 내보낸 파일을 보호하는 암호를 지정합니다. <p>암호는 8자 이상이어야 하며 1개 이상의 숫자와 1개의 특수 문자(`!`,`@`,`#` 및 `$`)를 포함해야 합니다.</p> |
   | **[!UICONTROL 이메일]** | 파일을 특정 이메일 주소로 보내려면 이 옵션을 선택합니다. 자세한 내용은 [전자 메일을 통해 공유하여 통합 문서 예약](/help/report-builder/schedule-reportbuilder.md)을 참조하세요. |
   | **[!UICONTROL 기타 게재]** | 파일을 클라우드 계정으로 보내려면 이 옵션을 선택하고 아래에 설명된 **[!UICONTROL 계정]** 및 **[!UICONTROL 위치]** 드롭다운 메뉴를 사용하여 계정과 위치를 선택하십시오. |
   | **[!UICONTROL 계정]** | 데이터를 전송할 클라우드 내보내기 계정을 선택합니다. <p>또는 사용하려는 클라우드 계정을 아직 구성하지 않은 경우 새 계정을 구성할 수 있습니다.<ol><li>[!UICONTROL **계정 추가**]&#x200B;를 선택하고 다음 정보를 지정합니다.<ul><li>[!UICONTROL **위치 계정 이름**]: 위치 계정의 이름을 지정합니다. 위치가 생성되면 이 이름이 표시됩니다. </li><li>[!UICONTROL **위치 계정 설명**]: 동일한 계정 유형의 다른 계정과 구분할 수 있도록 계정에 대한 간단한 설명을 제공합니다.</li><li>**[!UICONTROL 조직의 모든 사용자가 계정을 사용할 수 있도록 합니다]**: 조직의 다른 사용자가 계정을 사용할 수 있도록 하려면 이 옵션을 선택하십시오. 계정을 공유할 때는 다음 사항을 고려하십시오.<ul><li>공유하는 계정은 공유 해제할 수 없습니다.</li><li>공유 계정은 계정 소유자만 편집할 수 있습니다.</li><li>누구나 공유 계정의 위치를 만들 수 있습니다.</li></ul></li><li>[!UICONTROL **계정 유형**]: 내보내는 클라우드 계정 유형을 선택하십시오. 사용 가능한 계정 유형은 Amazon S3 역할 ARN, Google Cloud Platform, Azure SAS 및 Azure RBAC입니다.</li></ul><li>계정 구성을 완료하려면 선택한 [!UICONTROL **계정 유형**]&#x200B;에 해당하는 아래 링크에서 계속합니다.<ul><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li></ul></ol> |
   | **[!UICONTROL 위치]** | 내보내기 데이터를 보낼 계정의 위치를 선택합니다.<p>또는 선택한 계정에서 사용하려는 위치를 아직 구성하지 않은 경우 새 위치를 구성할 수 있습니다.<ol><li>[!UICONTROL **위치 추가**]&#x200B;를 선택하고 다음 정보를 지정합니다. <ul><li>[!UICONTROL **이름**]: 위치 이름.</li><li>[!UICONTROL **설명**]: 계정의 다른 위치와 구분할 수 있도록 위치에 대한 간단한 설명을 제공합니다.</li><li>**[!UICONTROL 조직의 모든 사용자가 위치를 사용할 수 있도록 설정]**: 조직의 다른 사용자가 위치를 사용할 수 있도록 하려면 이 옵션을 선택하십시오. 계정을 공유할 때는 다음 사항을 고려하십시오.<ul><li>공유하는 위치는 공유 해제할 수 없습니다.</li><li>공유 위치는 계정 소유자만 편집할 수 있습니다.</li><li>위치가 연결된 계정도 공유된 경우에만 위치를 공유할 수 있습니다.</li></ul></li><li>[!UICONTROL **위치 계정**]: 위치를 만들려는 계정을 선택합니다.</li></ul><li>위치 구성을 완료하려면 [!UICONTROL **위치 계정**] 필드에서 선택한 계정 유형에 해당하는 아래 링크를 계속 진행합니다.<ul><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li></ul> |
   | **[!UICONTROL 예약 옵션 표시]** | 내보내기 예약에 대한 추가 옵션을 보려면 이 옵션을 선택합니다. 내보내기를 한 번만 전송하려면 이 옵션을 선택하지 않은 상태로 둡니다. 이 옵션을 선택하지 않으면 내보내기가 즉시 시작됩니다. |
   | **[!UICONTROL 시작 날짜]** | 예약된 내보내기가 시작되어야 하는 날짜 및 시간. <p>이 옵션은 예약된 내보내기 빈도를 선택할 때만 사용할 수 있습니다.</p> |
   | **에**&#x200B;종료 | 예약된 내보내기가 만료되는 날짜 및 시간. 예약된 내보내기 작업은 설정한 날짜 및 시간 이후에는 더 이상 실행되지 않습니다. <p>이 옵션은 예약된 내보내기 빈도를 선택할 때만 사용할 수 있습니다.</p> |
   | **[!UICONTROL 빈도]** | 특정 날짜의 빈도를 시간대별, 일일, 주간, 월간 또는 연간으로 설정할 수 있습니다. 예를 들어, 수신자가 월요일 아침에 받은 편지함에 이메일을 먼저 보낼 수 있도록 통합 문서를 그 달의 첫 번째 일요일 밤에 보내도록 일정을 설정할 수 있습니다. |

   {style="table-layout:auto"}

1. 통합 문서를 내보내려면 [!UICONTROL **일정에 따라 보내기**]&#x200B;를 선택하십시오.

   데이터는 사용자가 지정한 빈도로 지정한 클라우드 계정으로 전송됩니다.

1. (선택 사항) 내보내기를 만든 후 지금 보내기로 선택했든 정의된 일정에 따라 보내기로 선택했든 [내보내기 페이지](/help/components/exports/manage-exports.md)에서 보고 관리할 수 있으며 [내보내기 로그](/help/components/exports/manage-export-logs.md)에서 볼 수 있습니다.</p>

## 내보내기 관리

Analysis Workspace에서 데이터를 내보낸 후에는 기존 내보내기를 편집, 다시 내보내기, 복제, 태그 지정 또는 삭제할 수 있습니다. 자세한 내용은 [내보내기 관리](/help/components/exports/manage-exports.md)에 설명되어 있습니다.

## 클라우드로 내보낼 때의 이점

Customer Journey Analytics 데이터를 클라우드로 내보내면 다음 작업이 가능합니다.

* Google Cloud Platform, Microsoft Azure 및 Amazon S3과 같은 공유 위치로 내보냅니다.

* 대량의 내역 데이터를 저장합니다.

  이러한 유형의 데이터는 장기적인 추세를 감지하여 비즈니스 인텔리전스를 확보하고 궁극적으로 더 나은 비즈니스 의사 결정으로 이어질 수 있습니다.

* 내보낸 Customer Journey Analytics 데이터에 계산된 지표를 포함합니다.

* 연결된 값으로 데이터 출력을 구조화합니다.

* 한 번 또는 일정에 따라 내보냅니다.

* Excel, PDF 또는 CSV 형식으로 파일을 내보냅니다.

* 여러 차원이 포함된 데이터 블록을 내보냅니다.

## 내보내기 요구 사항 {#export-requirements}

### 최소 요구 사항

데이터 블록, 환경 및 권한이 다음 요구 사항을 충족하는지 확인하십시오.

* **데이터 블록:** 모든 데이터 블록에는 열, 행 또는 값에 대한 구성 요소가 하나 이상 포함되어야 합니다.

* **환경:** Customer Journey Analytics에서 사용하는 [IP 주소](/help/technotes/ip-addresses.md)와 [도메인](/help/technotes/domains.md)이 해당 조직의 방화벽을 통과할 수 있는지 확인합니다.
