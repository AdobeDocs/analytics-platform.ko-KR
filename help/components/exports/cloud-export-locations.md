---
description: Customer Journey Analytics 데이터를 전송할 수 있는 클라우드 내보내기 위치 구성
keywords: Analysis Workspace
title: 클라우드 내보내기 위치 구성
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 6%

---

# 클라우드 내보내기 위치 구성

{{select-package}}

에 설명된 대로 Customer Journey Analytics 데이터를 클라우드 대상으로 내보내기 전에 [클라우드로 Customer Journey Analytics 데이터 내보내기](/help/analysis-workspace/export/export-cloud.md)데이터를 전송할 위치를 추가하고 구성해야 합니다.

이 프로세스는에 설명된 대로 계정을 추가 및 구성(Amazon S3, Google Cloud Platform 등)하는 과정으로 구성됩니다 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md)이 문서에 설명된 대로 해당 계정(계정 내 폴더 등) 내에 위치를 추가하고 구성합니다.

위치 보기, 편집 및 삭제를 포함하여 기존 위치를 관리하는 방법에 대한 자세한 내용은 [클라우드 내보내기 위치 및 계정 관리](/help/components/exports/manage-export-locations.md).

클라우드 내보내기 위치를 구성하려면:

1. 위치를 추가하려면 먼저 계정을 추가해야 합니다. 아직 계정이 없다면 의 설명에 따라 계정을 추가합니다. [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md).
1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].
1. 다음에서 [!UICONTROL 내보내기] 페이지에서 [!UICONTROL **위치**] 탭.
1. 선택 [!UICONTROL **위치 추가**].

   ![위치 추가 단추](assets/location-add.png)

   위치 대화 상자가 표시됩니다.

1. 다음 정보를 지정합니다. |필드 | 함수 | ------------------- | [!UICONTROL **이름**] | 위치의 이름입니다.  | | [!UICONTROL **설명**] | 같은 계정 유형의 다른 계정과 구분할 수 있도록 계정에 대한 간단한 설명을 제공합니다. | | [!UICONTROL **위치 계정**] | 만든 위치 계정 선택 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md). |

1. 다음에서 [!UICONTROL **위치 속성**] 섹션에서 위치 계정의 계정 유형과 관련된 정보를 지정합니다.

   구성 지침을 보려면 아래에서 선택한 계정 유형에 해당하는 아래 섹션을 확장합니다. [!UICONTROL **위치 계정**] 필드.

   +++Amazon S3 Role ARN

   Amazon S3 역할 ARN 위치를 구성하려면 다음 정보를 지정하십시오.

   <!-- still need to update; can't create S3 role ARN account -->

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **버킷**] | Adobe Analytics 데이터를 전송할 Amazon S3 계정 내의 버킷입니다. Adobe이 제공한 사용자 ARN이 이 버킷에 파일을 업로드할 수 있는 액세스 권한이 있는지 확인하십시오. |
   | [!UICONTROL **접두사**] | 데이터를 저장할 버킷 내의 폴더입니다. 폴더 이름을 지정한 다음 이름 뒤에 백슬래시를 추가하여 폴더를 만듭니다. 예: folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud 플랫폼

   다음 정보를 지정하여 Google Cloud Platform 위치를 구성하십시오.

   <!-- still need to update; can't create GCP account -->

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **버킷**] | Customer Journey Analytics 데이터를 전송할 GCP 계정 내의 버킷입니다. 이 버킷에 파일을 업로드할 수 있도록 Adobe이 제공한 사용자에 대한 권한을 부여했는지 확인하십시오. (다음과 같은 경우 원금이 제공됩니다. [Google Cloud Platform 계정 구성](/help/components/exports/cloud-export-accounts.md).) 권한 부여에 대한 자세한 내용은 [버킷 수준 정책에 사용자 추가](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) Google Cloud 설명서에서 확인할 수 있습니다. |
   | [!UICONTROL **접두사**] | 데이터를 저장할 버킷 내의 폴더입니다. 폴더 이름을 지정한 다음 이름 뒤에 백슬래시를 추가하여 폴더를 만듭니다. 예: folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Azure SAS 위치를 구성하려면 다음 정보를 지정하십시오.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **컨테이너 이름**] | Customer Journey Analytics 데이터를 전송할 지정한 계정 내의 컨테이너입니다. |
   | [!UICONTROL **접두사**] | 데이터를 저장할 컨테이너 내의 폴더입니다. 폴더 이름을 지정한 다음 이름 뒤에 백슬래시를 추가하여 폴더를 만듭니다. 예, `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Azure RBAC 위치를 구성하려면 다음 정보를 지정하십시오.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **컨테이너**] | Adobe Analytics 데이터를 전송할 지정한 계정 내의 컨테이너입니다. 이전에 만든 Azure 애플리케이션에 파일을 업로드할 수 있는 권한을 부여했는지 확인하십시오. |
   | [!UICONTROL **접두사**] | 데이터를 저장할 컨테이너 내의 폴더입니다. 폴더 이름을 지정한 다음 이름 뒤에 백슬래시를 추가하여 폴더를 만듭니다. 예, `folder_name/` |
   | [!UICONTROL **계정**] | Azure 스토리지 계정입니다. |

   {style="table-layout:auto"}

+++

   +++Snowflake

   Snowflake 위치를 구성하려면 다음 정보를 지정하십시오.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **DB**] | 연결되면 사용할 기본 데이터베이스이거나 빈 문자열을 지정합니다. 지정한 데이터베이스는 지정한 기본 역할에 권한이 있는 기존 데이터베이스여야 합니다. <p>자세한 내용은 [Snowflake 설명서의 JDBC 드라이버 연결 매개 변수 참조 페이지](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **스키마**] | 연결된 후 지정된 데이터베이스에 사용할 기본 스키마이거나 빈 문자열을 지정합니다. 지정된 스키마는 지정된 기본 역할에 권한이 있는 기존 스키마여야 합니다. <p>자세한 내용은 [Snowflake 설명서의 JDBC 드라이버 연결 매개 변수 참조 페이지](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **단계 이름**] | Snowflake에서 데이터 파일이 저장되는 위치의 이름입니다. <p>자세한 내용은 [Snowflake 설명서의 로컬 파일에 대한 내부 단계 선택](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **단계 경로**] | Snowflake에서 데이터 파일이 저장되는 위치에 대한 경로입니다. <p>자세한 내용은 [Snowflake 설명서의 로컬 파일에 대한 내부 단계 선택](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

+++

   +++Adobe Experience Platform

   Adobe Experience Platform 위치를 구성하려면 다음 정보를 지정하십시오.

   <!-- still need to update; can't create AEP account -->

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **IMS 조직 ID**] | IMS 조직 ID는 Adobe에서 제공합니다. 다음 옆에 있는 복사 아이콘을 클릭합니다. [!UICONTROL **IMS 조직 ID**] 필드를 사용하여 필드의 내용을 복사한 다음, Adobe Experience Platform 계정의 ID를 사용하십시오. |
   | [!UICONTROL **접두사**] | 데이터를 저장할 컨테이너 내의 폴더입니다. 폴더 이름을 지정한 다음 이름 뒤에 백슬래시를 추가하여 폴더를 만듭니다. 예, `folder_name/` |

+++

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

1. 이제 Analysis Workspace에서 구성한 계정 및 위치로 데이터를 내보낼 수 있습니다. 데이터를 클라우드로 내보내는 방법에 대한 자세한 내용은 [클라우드로 프로젝트 데이터 내보내기](/help/analysis-workspace/export/export-cloud.md).