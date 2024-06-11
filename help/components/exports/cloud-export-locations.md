---
description: Customer Journey Analytics 데이터를 전송할 수 있는 클라우드 내보내기 위치 구성
keywords: Analysis Workspace
title: 클라우드 내보내기 위치 구성
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 1bf36f60b0b3aec04bb1452e5f63f97051d9bb50
workflow-type: tm+mt
source-wordcount: '1932'
ht-degree: 21%

---

# 클라우드 내보내기 위치 구성

에 설명된 대로 Customer Journey Analytics 보고서를 클라우드 대상으로 내보내기 전에 [클라우드로 Customer Journey Analytics 보고서 내보내기](/help/analysis-workspace/export/export-cloud.md)데이터를 전송할 위치를 추가하고 구성해야 합니다.

이 프로세스는에 설명된 대로 계정을 추가 및 구성(Amazon S3, Google Cloud Platform 등)하는 과정으로 구성됩니다 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md)이 문서에 설명된 대로 해당 계정(계정 내 폴더 등) 내에 위치를 추가하고 구성합니다.

위치 보기, 편집 및 삭제를 포함하여 기존 위치를 관리하는 방법에 대한 자세한 내용은 [클라우드 내보내기 위치 및 계정 관리](/help/components/exports/manage-export-locations.md).

## 클라우드 내보내기 위치 만들기 시작

1. 위치를 추가하려면 먼저 계정을 추가해야 합니다. 아직 계정이 없다면 의 설명에 따라 계정을 추가합니다. [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md).

1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].

1. 다음 항목 선택 [!UICONTROL **위치**] 탭을 선택한 다음 를 선택합니다 [!UICONTROL **위치 추가**].

   ![위치 추가 버튼이 강조 표시된 위치 탭이 선택된 창 내보내기](assets/location-add.png)

   또는

   다음 항목 선택 [!UICONTROL **위치 계정**] 탭에서 위치를 추가하려는 기존 계정에서 3점 아이콘을 선택한 다음 을 선택합니다 [!UICONTROL **위치 추가**].

   ![위치 추가 가 선택되었음을 보여 주는 GCP 계정 및 생략 드롭다운 메뉴](assets/add-location-existing-account.png)

   위치 대화 상자가 표시됩니다.

1. 다음 정보를 지정합니다. |필드 | 함수 | ------------------- | [!UICONTROL **이름**] | 위치의 이름입니다.  | | [!UICONTROL **설명**] | 계정의 다른 위치와 구분하는 데 도움이 되도록 위치에 대한 간단한 설명을 입력합니다. | | [!UICONTROL **조직의 모든 사용자가 위치를 사용할 수 있도록 설정**] | **참고:** 이 기능은 릴리스의 제한된 테스트 단계에 있으며 사용자 환경에서 아직 사용하지 못할 수 있습니다. 기능이 일반적으로 제공되면 이 메모는 제거됩니다. Analytics 릴리스 프로세스에 대한 자세한 내용은 [Customer Journey Analytics 기능 릴리스](/help/release-notes/releases.md)를 참조하십시오. <p>조직의 다른 사용자가 위치를 사용할 수 있도록 하려면 이 옵션을 활성화합니다.</p> <p>위치를 공유할 때는 다음 사항을 고려하십시오.</p><ul><li>공유하는 위치는 공유 해제할 수 없습니다.</li><li>공유 위치는 해당 위치의 소유자만 편집할 수 있습니다.</li><li>위치가 연결된 계정도 공유된 경우에만 위치를 공유할 수 있습니다.</li></ul> | | [!UICONTROL **위치 계정**] | 위치를 만들 계정을 선택합니다. 계정을 만드는 방법에 대한 자세한 내용은 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md). |

1. [!UICONTROL **위치 속성**] 섹션에서 위치 계정의 계정 유형과 관련된 정보를 지정합니다.

   에서 선택한 계정 유형에 해당하는 아래 섹션을 계속 진행합니다. [!UICONTROL **위치 계정**] 필드.

   * [AEP 데이터 랜딩 구역](#aep-data-landing-zone)
   * [Amazon S3 Role ARN](#amazon-s3-role-arn)
   * [Google Cloud 플랫폼](#google-cloud-platform)
   * [Azure SAS](#azure-sas)
   * [Azure RBAC](#azure-rbac)
   * [Snowflake](#snowflake)

### AEP 데이터 랜딩 구역

>[!IMPORTANT]
>
>Customer Journey Analytics 보고서를 Adobe Experience Platform 데이터 랜딩 구역으로 내보낼 때 7일 이내에 데이터를 다운로드한 다음 AEP 데이터 랜딩 구역에서 삭제해야 합니다. 7일 후 데이터는 AEP 데이터 랜딩 구역에서 자동으로 삭제됩니다.

1. 다음 방법 중 하나로 클라우드 내보내기 위치를 만들기 시작합니다.

   * 위에 설명된 대로 내보내기 페이지에서 [클라우드 내보내기 위치 만들기 시작](#begin-creating-a-cloud-export-location)

   * 날짜 [Analysis Workspace에서 전체 표 내보내기](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 다음에서 [!UICONTROL **위치 속성**] 의 섹션 [!UICONTROL **위치 추가**] 대화 상자에서 다음 정보를 지정하여 Adobe Experience Platform 데이터 랜딩 영역 위치를 구성합니다.

   <!-- still need to update; can't create AEP account -->

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **접두사**] | 데이터를 입력할 컨테이너 내부 폴더입니다. 폴더 이름을 지정한 다음 이름 뒤에 슬래시를 추가하여 폴더를 만듭니다. 예를 들어 `folder_name/` |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

1. 이제 Analysis Workspace에서 구성한 계정 및 위치로 데이터를 내보낼 수 있습니다. 데이터를 클라우드로 내보내는 방법에 대한 자세한 내용은 [클라우드로 프로젝트 데이터 내보내기](/help/analysis-workspace/export/export-cloud.md).

1. AEP 데이터 랜딩 구역에서 데이터에 액세스하는 가장 쉬운 방법은 Microsoft Azure Storage Explorer를 사용하는 것입니다. 이는 을 구성하는 지침에 사용되는 것과 동일한 도구입니다. [AEP 데이터 랜딩 영역 계정](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone).

   1. 를 엽니다. [Microsoft Azure 스토리지 탐색기](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. 다음으로 이동 [!UICONTROL **저장소 계정**] > [!UICONTROL **(첨부된 컨테이너)**] > [!UICONTROL **Blob 컨테이너**] > **[!UICONTROL cjaexport-_숫자_]**>*** your_container_name ***.

      >[!NOTE]
      >
      >폴더 이름 **[!UICONTROL cjaexport-_숫자_]**은 Azure Storage Explorer에서 제공하는 기본 이름입니다. SAS URI(일반)와 연결된 연결이 하나만 있는 경우 이 폴더의 이름은 다음과 같습니다.**[!UICONTROL cjaexport-1]**.


      ![Azure 스토리지 탐색기에서 파일 액세스](assets/azure-storage-explorer-access.png)

   1. 다운로드할 내보내기를 선택한 다음 을 선택합니다 [!UICONTROL **다운로드**] 다운로드.

### Amazon S3 Role ARN

1. 다음 방법 중 하나로 클라우드 내보내기 위치를 만들기 시작합니다.

   * 위에 설명된 대로 내보내기 페이지에서 [클라우드 내보내기 위치 만들기 시작](#begin-creating-a-cloud-export-location)

   * 날짜 [Analysis Workspace에서 전체 표 내보내기](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 다음에서 [!UICONTROL **위치 속성**] 의 섹션 [!UICONTROL **위치 추가**] 대화 상자에서 다음 정보를 지정하여 Amazon S3 역할 ARN 위치를 구성합니다.

   <!-- still need to update; can't create S3 role ARN account -->

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **버킷**] | Customer Journey Analytics 데이터를 전송할 Amazon S3 계정 내의 버킷입니다. <p>Adobe이 제공한 사용자 ARN에 `S3:PutObject` 이 버킷에 파일을 업로드할 수 있는 권한입니다. </p><p>버킷 이름은 특정 이름 지정 규칙을 충족해야 합니다. 예를 들면 3~63자 사이여야 하며 소문자, 숫자, 점(.), 하이픈(-)만 사용할 수 있고 문자나 숫자로 시작하고 끝나야 합니다. [이름 지정 규칙의 전체 목록은 AWS 설명서에서 확인할 수 있습니다](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **접두사**] | 데이터를 입력할 버킷 내부 폴더입니다. 폴더 이름을 지정한 다음 이름 뒤에 슬래시를 추가하여 폴더를 만듭니다. 예를 들어 폴더 이름/ |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

1. 이제 Analysis Workspace에서 구성한 계정 및 위치로 데이터를 내보낼 수 있습니다. 데이터를 클라우드로 내보내는 방법에 대한 자세한 내용은 [클라우드로 프로젝트 데이터 내보내기](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. 다음 방법 중 하나로 클라우드 내보내기 위치를 만들기 시작합니다.

   * 위에 설명된 대로 내보내기 페이지에서 [클라우드 내보내기 위치 만들기 시작](#begin-creating-a-cloud-export-location)

   * 날짜 [Analysis Workspace에서 전체 표 내보내기](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 다음에서 [!UICONTROL **위치 속성**] 의 섹션 [!UICONTROL **위치 추가**] 대화 상자에서 다음 정보를 지정하여 Google Cloud Platform 위치를 구성합니다.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **버킷**] | Customer Journey Analytics 데이터를 전송할 GCP 계정 내의 버킷입니다. <p>다음을 부여했는지 확인합니다. `roles/storage.objectCreator` Adobe이 제공한 사용자에 대한 권한. (다음과 같은 경우 원금이 제공됩니다. [Google Cloud Platform 계정 구성](/help/components/exports/cloud-export-accounts.md).) <p>권한 부여에 대한 자세한 내용은 Google Cloud 설명서에서 [버킷 수준 정책에 주체 추가](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add)를 참조하십시오.</p><p>귀사에서 [조직 정책 제한 사항](https://cloud.google.com/storage/docs/org-policy-constraints)을 사용하여 허용 목록에 Google Cloud Platform 계정만 허용하는 경우 다음과 같은 Adobe 소유의 Google Cloud Platform 조직 ID가 필요합니다. <ul><li>`DISPLAY_NAME`: `adobe.com`</li><li>`ID`: `178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`: `C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **접두사**] | 데이터를 입력할 버킷 내부 폴더입니다. 폴더 이름을 지정한 다음 이름 뒤에 슬래시를 추가하여 폴더를 만듭니다. 예를 들어 폴더 이름/ |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

1. 이제 Analysis Workspace에서 구성한 계정 및 위치로 데이터를 내보낼 수 있습니다. 데이터를 클라우드로 내보내는 방법에 대한 자세한 내용은 [클라우드로 프로젝트 데이터 내보내기](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. 다음 방법 중 하나로 클라우드 내보내기 위치를 만들기 시작합니다.

   * 위에 설명된 대로 내보내기 페이지에서 [클라우드 내보내기 위치 만들기 시작](#begin-creating-a-cloud-export-location)

   * 날짜 [Analysis Workspace에서 전체 표 내보내기](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 다음에서 [!UICONTROL **위치 속성**] 의 섹션 [!UICONTROL **위치 추가**] 대화 상자에서 다음 정보를 지정하여 Azure SAS 위치를 구성하십시오.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **컨테이너 이름**] | Customer Journey Analytics 데이터를 전송할 지정한 계정 내의 컨테이너입니다. |
   | [!UICONTROL **접두사**] | 데이터를 입력할 컨테이너 내부 폴더입니다. 폴더 이름을 지정한 다음 이름 뒤에 슬래시를 추가하여 폴더를 만듭니다. 예를 들어 `folder_name/`<p>Azure SAS 계정 구성 시 Key Vault 암호 이름 필드에 지정된 SAS 토큰 저장소에 `Write` 권한이 있는지 확인합니다. 이렇게 하면 SAS 토큰이 Azure 컨테이너에서 파일을 만들 수 있습니다. <p>SAS 토큰을 사용하여 파일을 덮어쓰려면 SAS 토큰 저장소에 `Delete` 권한이 있는지 확인합니다.</p><p>자세한 내용은 Azure Blob Storage 설명서에서 [Blob 스토리지 리소스](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) 를 참조하십시오.</p> |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

1. 이제 Analysis Workspace에서 구성한 계정 및 위치로 데이터를 내보낼 수 있습니다. 데이터를 클라우드로 내보내는 방법에 대한 자세한 내용은 [클라우드로 프로젝트 데이터 내보내기](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. 다음 방법 중 하나로 클라우드 내보내기 위치를 만들기 시작합니다.

   * 위에 설명된 대로 내보내기 페이지에서 [클라우드 내보내기 위치 만들기 시작](#begin-creating-a-cloud-export-location)

   * 날짜 [Analysis Workspace에서 전체 표 내보내기](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 다음에서 [!UICONTROL **위치 속성**] 의 섹션 [!UICONTROL **위치 추가**] 대화 상자에서 다음 정보를 지정하여 Azure RBAC 위치를 구성하십시오.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **컨테이너**] | Customer Journey Analytics 데이터를 전송할 지정한 계정 내의 컨테이너입니다. 앞서 만든 Azure 애플리케이션에 파일을 업로드할 권한을 부여하고 있는지 확인합니다. |
   | [!UICONTROL **접두사**] | 데이터를 입력할 컨테이너 내부 폴더입니다. 폴더 이름을 지정한 다음 이름 뒤에 슬래시를 추가하여 폴더를 만듭니다. 예를 들어 `folder_name/`<p>컨테이너(폴더)에 액세스하려면 Azure RBAC 계정 구성 시 지정한 애플리케이션 ID에 `Storage Blob Data Contributor` 역할이 부여되었는지 확인합니다.</p> <p>자세한 내용은 [Azure 기본 제공 역할](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles)을 참조하십시오.</p> |
   | [!UICONTROL **계정**] | Azure 스토리지 계정입니다. |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

1. 이제 Analysis Workspace에서 구성한 계정 및 위치로 데이터를 내보낼 수 있습니다. 데이터를 클라우드로 내보내는 방법에 대한 자세한 내용은 [클라우드로 프로젝트 데이터 내보내기](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. 다음 방법 중 하나로 클라우드 내보내기 위치를 만들기 시작합니다.

   * 위에 설명된 대로 내보내기 페이지에서 [클라우드 내보내기 위치 만들기 시작](#begin-creating-a-cloud-export-location)

   * 날짜 [Analysis Workspace에서 전체 표 내보내기](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 다음에서 [!UICONTROL **위치 속성**] 의 섹션 [!UICONTROL **위치 추가**] 대화 상자에서 다음 정보를 지정하여 Snowflake 위치를 구성합니다.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **DB**] | 지정한 데이터베이스는 기존 데이터베이스여야 합니다. 생성한 롤은 이 데이터베이스에 액세스할 수 있는 권한이 있어야 합니다.<p>스테이지 이름과 연관된 데이터베이스입니다.</p><p>다음 명령을 사용하여 Snowflake의 데이터베이스에 이 롤 권한을 부여할 수 있습니다. `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>자세한 내용은 [Snowflake 설명서의 데이터베이스, 스키마 및 공유 명령 페이지](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **스키마**] | 지정된 스키마는 기존 스키마여야 합니다. 이 스키마에 액세스하려면 만든 역할에 권한이 있어야 합니다.<p>단계 이름과 연결된 스키마입니다.<p>다음 명령을 사용하여 Snowflake의 스키마에 대한 권한을 생성한 롤에 부여할 수 있습니다. `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>자세한 내용은 [Snowflake 설명서의 데이터베이스, 스키마 및 공유 명령 페이지](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **단계 이름**] | 데이터 파일이 Snowflake에 저장되는 내부 단계의 이름입니다.<p>계정에서 지정한 역할에 이 단계 이름에 대한 읽기 및 쓰기 권한이 있는지 확인하십시오. (읽기 및 쓰기 액세스 권한을 부여하므로 Adobe 시에만 사용되는 단계를 사용하는 것이 좋습니다.)<p>다음 명령을 사용하여 Snowflake의 단계 이름에 읽기 및 쓰기 액세스 권한을 부여할 수 있습니다. `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>롤에 권한을 부여하는 방법에 대한 자세한 내용은 [Snowflake 설명서에서 권한 부여](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>스테이지 이름에 대한 자세한 내용은 [Snowflake 설명서의 로컬 파일에 대한 내부 단계 선택](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **스테이지 경로**] | Snowflake에서 데이터 파일이 저장되는 위치에 대한 경로입니다. <p>자세한 내용은 [Snowflake 설명서의 로컬 파일에 대한 내부 단계 선택](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

1. 이제 Analysis Workspace에서 구성한 계정 및 위치로 데이터를 내보낼 수 있습니다. 데이터를 클라우드로 내보내는 방법에 대한 자세한 내용은 [클라우드로 프로젝트 데이터 내보내기](/help/analysis-workspace/export/export-cloud.md).
