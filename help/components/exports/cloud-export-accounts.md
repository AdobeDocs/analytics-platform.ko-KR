---
description: Customer Journey Analytics 데이터를 전송할 수 있는 클라우드 내보내기 계정 구성
keywords: Analysis Workspace
title: 클라우드 내보내기 계정 구성
feature: Components
hide: true
hidefromtoc: true
source-git-commit: a2b2c6bca0557521ac7b6bcf635f467ca41731b7
workflow-type: tm+mt
source-wordcount: '1580'
ht-degree: 6%

---

# 클라우드 내보내기 계정 구성

에 설명된 대로 Customer Journey Analytics 보고서를 클라우드 대상으로 내보내기 전에 [클라우드로 Customer Journey Analytics 보고서 내보내기](/help/analysis-workspace/export/export-cloud.md)데이터를 전송할 대상을 추가하고 구성해야 합니다.

이 프로세스는 이 문서에 설명된 대로 계정(예: Amazon S3, Google Cloud Platform 등)을 추가 및 구성한 다음, 설명된 대로 해당 계정 내에 위치(예: 계정 내 폴더)를 추가 및 구성합니다 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md).

계정 보기, 편집 및 삭제를 포함하여 기존 계정을 관리하는 방법에 대한 자세한 내용은 [클라우드 내보내기 위치 및 계정 관리](/help/components/exports/manage-export-locations.md).

## 클라우드 내보내기 계정 만들기 시작

1. Customer Journey Analytics에서 [!UICONTROL **구성 요소**] > [!UICONTROL **내보내기**].
1. 다음에서 [!UICONTROL 내보내기] 페이지에서 [!UICONTROL **위치 계정**] 탭.
1. 선택 [!UICONTROL **계정 추가**].

   ![계정 추가](assets/account-add.png)

   계정 추가 대화 상자가 표시됩니다.

1. 다음에서 [!UICONTROL **위치 계정 이름**] 필드에서 위치 계정의 이름을 지정합니다. 이 이름은 위치를 만들 때 나타납니다.

1. 다음에서 [!UICONTROL **위치 계정 설명**] 필드에서는 동일한 계정 유형의 다른 계정과 구별할 수 있도록 계정에 대한 간단한 설명을 제공합니다.

1. 다음에서 [!UICONTROL **계정 유형**] 필드에서 내보내려는 클라우드 계정 유형을 선택합니다. 사용 가능한 계정 유형은 Amazon S3 역할 ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake 및 Adobe Experience Platform 데이터 랜딩 영역입니다.

1. 에 해당하는 아래 섹션을 계속합니다. [!UICONTROL **계정 유형**] 을(를) 선택했습니다.

   * [Adobe Experience Platform 데이터 랜딩 영역](#adobe-experience-platform)

   * [Amazon S3 Role ARN](#amazon-s3-role-arn)

   * [Google Cloud 플랫폼](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### Adobe Experience Platform 데이터 랜딩 영역

>[!IMPORTANT]
>
>Customer Journey Analytics 보고서를 Adobe Experience Platform 데이터 랜딩 구역으로 내보낼 때 7일 이내에 데이터를 다운로드한 다음 AEP 데이터 랜딩 구역에서 삭제해야 합니다. 7일 후 데이터는 AEP 데이터 랜딩 구역에서 자동으로 삭제됩니다.

1. [클라우드 내보내기 계정 만들기 시작](#begin-creating-a-cloud-export-account), 위에서 설명한 대로

1. 다음에서 [!UICONTROL **계정 속성**] 의 섹션 [!UICONTROL **계정 추가**] 대화 상자에는 다음 정보가 표시됩니다.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **IMS 조직 ID**] | IMS 조직 ID는 Adobe에서 제공합니다. 이 정보는 일반적으로 필요하지 않습니다. 계정에 문제가 발생하여 고객 지원 센터에 문의해야 하는 경우 유용할 수 있습니다. |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

   다음 [!UICONTROL **내보내기 계정 생성됨**] 대화 상자가 표시됩니다.

   <!-- add screen shot -->

1. 의 내용을 복사합니다. [!UICONTROL **SAS**] 필드를 클립보드에 추가합니다. 이 SAS 토큰을 사용하여 AEP 랜딩 영역에서 Analysis Workspace으로 내보낸 데이터에 액세스합니다. 데이터에 액세스하는 방법에 대해 알아보기&quot; |

1. [!UICONTROL **닫기**]&#x200B;를 선택합니다.

1. 계속 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. [클라우드 내보내기 계정 만들기 시작](#begin-creating-a-cloud-export-account), 위에서 설명한 대로

1. 다음에서 [!UICONTROL **계정 속성**] 의 섹션 [!UICONTROL **계정 추가**] 대화 상자에서 다음 정보를 지정합니다.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **역할 ARN**] | Adobe이 Amazon S3 계정에 대한 액세스 권한을 받는 데 사용할 수 있는 역할 ARN(Amazon 리소스 이름)을 제공해야 합니다. 이렇게 하려면 소스 계정에 대한 IAM 권한 정책을 만들고, 이 정책을 사용자에게 연결한 다음 대상 계정에 대한 역할을 만듭니다. 자세한 내용은 다음을 참조하십시오. [이 AWS 설명서](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

   다음 [!UICONTROL **내보내기 계정 생성됨**] 대화 상자가 표시됩니다.

   <!-- add screen shot -->

1. 의 내용을 복사합니다. [!UICONTROL **사용자 ARN**] 필드를 클립보드에 추가합니다. Adobe ARN(Amazon 리소스 이름)은 사용자가 제공합니다. Amazon S3 역할 ARN에서 생성한 정책에 이 사용자를 연결해야 합니다.

1. [!UICONTROL **닫기**]&#x200B;를 선택합니다.

1. 계속 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md).

### Google Cloud 플랫폼

1. [클라우드 내보내기 계정 만들기 시작](#begin-creating-a-cloud-export-account), 위에서 설명한 대로

1. 다음에서 [!UICONTROL **계정 속성**] 의 섹션 [!UICONTROL **계정 추가**] 대화 상자에서 다음 정보를 지정합니다.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **프로젝트 ID**] | Google Cloud 계정에서 복사하는 Google Cloud 프로젝트 ID입니다. 다음을 참조하십시오. [프로젝트 ID 가져오기에 대한 Google Cloud 설명서](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

   다음 [!UICONTROL **내보내기 계정 생성됨**] 대화 상자가 표시됩니다.

   <!-- add screen shot -->

1. 의 내용을 복사합니다. [!UICONTROL **사용자**] 필드를 클립보드에 넣은 다음 사용자에게 Google Cloud Platform의 이 버킷에 파일을 업로드할 수 있는 권한을 부여했는지 확인하십시오. <!-- add link to Google Cloud docs on how to do this -->

1. [!UICONTROL **닫기**]&#x200B;를 선택합니다.

1. 계속 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. [클라우드 내보내기 계정 만들기 시작](#begin-creating-a-cloud-export-account), 위에서 설명한 대로

1. 다음에서 [!UICONTROL **계정 속성**] 의 섹션 [!UICONTROL **계정 추가**] 대화 상자에서 다음 정보를 지정합니다.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **애플리케이션 ID**] | 생성한 Azure 애플리케이션에서 이 ID를 복사합니다. Microsoft Azure에서 이 정보는 **개요** 응용 프로그램 내의 탭입니다. 자세한 내용은 [Microsoft ID 플랫폼을 사용하여 애플리케이션을 등록하는 방법에 대한 Microsoft Azure 설명서](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **테넌트 ID**] | 생성한 Azure 애플리케이션에서 이 ID를 복사합니다. Microsoft Azure에서 이 정보는 **개요** 응용 프로그램 내의 탭입니다. 자세한 내용은 [Microsoft ID 플랫폼을 사용하여 애플리케이션을 등록하는 방법에 대한 Microsoft Azure 설명서](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **키 자격 증명 모음 URI**] | <p>Azure Key Vault의 SAS 토큰 경로.  Azure SAS를 구성하려면 Azure 키 자격 증명 모음을 사용하여 SAS 토큰을 비밀로 저장해야 합니다. 자세한 내용은 [Azure Key Vault에서 암호를 설정하고 검색하는 방법에 대한 Microsoft Azure 설명서](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Key Vault URI가 만들어진 후 Key Vault에 액세스 정책을 추가하여 만든 Azure 애플리케이션에 권한을 부여합니다. 자세한 내용은 [주요 자격 증명 모음 액세스 정책을 할당하는 방법에 대한 Microsoft Azure 설명서](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **키 자격 증명 모음 암호 이름**] | Azure Key Vault에 암호를 추가할 때 만든 암호 이름입니다. Microsoft Azure에서 이 정보는 만든 Key Vault의 **주요 자격 증명 모음** 설정 페이지를 참조하십시오. 자세한 내용은 [Azure Key Vault에서 암호를 설정하고 검색하는 방법에 대한 Microsoft Azure 설명서](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **위치 계정 암호**] <!-- nothing for us to have them do on the second screen. Just need to permission the container if they haven't --> | 생성한 Azure 애플리케이션에서 암호를 복사합니다. Microsoft Azure에서 이 정보는 **인증서 및 암호** 응용 프로그램 내의 탭입니다. 자세한 내용은 [Microsoft ID 플랫폼을 사용하여 애플리케이션을 등록하는 방법에 대한 Microsoft Azure 설명서](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

   다음 [!UICONTROL **내보내기 계정 생성됨**] 대화 상자가 표시됩니다.

   <!-- add screen shot -->

1. 아직 권한이 없는 경우 Azure SAS의 버킷에 권한을 부여했는지 확인하십시오. <!-- add link to Google Cloud docs on how to do this -->

1. [!UICONTROL **닫기**]&#x200B;를 선택합니다.

1. 계속 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. [클라우드 내보내기 계정 만들기 시작](#begin-creating-a-cloud-export-account), 위에서 설명한 대로

1. 다음에서 [!UICONTROL **계정 속성**] 의 섹션 [!UICONTROL **계정 추가**] 대화 상자에서 다음 정보를 지정합니다.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **애플리케이션 ID**] | 생성한 Azure 애플리케이션에서 이 ID를 복사합니다. Microsoft Azure에서 이 정보는 **개요** 응용 프로그램 내의 탭입니다. 자세한 내용은 [Microsoft ID 플랫폼을 사용하여 애플리케이션을 등록하는 방법에 대한 Microsoft Azure 설명서](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **테넌트 ID**] | 생성한 Azure 애플리케이션에서 이 ID를 복사합니다. Microsoft Azure에서 이 정보는 **개요** 응용 프로그램 내의 탭입니다. 자세한 내용은 [Microsoft ID 플랫폼을 사용하여 애플리케이션을 등록하는 방법에 대한 Microsoft Azure 설명서](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **위치 계정 암호**] | 생성한 Azure 애플리케이션에서 암호를 복사합니다. Microsoft Azure에서 이 정보는 **인증서 및 암호** 응용 프로그램 내의 탭입니다. 자세한 내용은 [Microsoft ID 플랫폼을 사용하여 애플리케이션을 등록하는 방법에 대한 Microsoft Azure 설명서](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

   다음 [!UICONTROL **내보내기 계정 생성됨**] 대화 상자가 표시됩니다.

   <!-- add screen shot -->

1. 아직 권한이 없는 경우 Azure RBAC의 버킷에 권한을 부여했는지 확인하십시오. <!-- add link to Google Cloud docs on how to do this -->

1. [!UICONTROL **닫기**]&#x200B;를 선택합니다.

1. 계속 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. [클라우드 내보내기 계정 만들기 시작](#begin-creating-a-cloud-export-account), 위에서 설명한 대로

1. 다음에서 [!UICONTROL **계정 속성**] 의 섹션 [!UICONTROL **계정 추가**] 대화 상자에서 다음 정보를 지정합니다.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **계정 식별자**] | 조직 내뿐만 아니라 Snowflake이 지원하는 클라우드 플랫폼 및 클라우드 지역의 글로벌 네트워크 전체에서 Snowflake 계정을 고유하게 식별합니다. <p>Snowflake 계정에서 계정 식별자를 가져온 다음 여기에 정보를 붙여넣어야 합니다.</p><p>이 정보를 얻을 수 있는 위치를 알아보려면 [Snowflake 설명서의 계정 식별자 페이지](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **사용자**] | 연결에 사용할 사용자의 로그인 이름입니다. 이는 특히 Adobe에 사용될 사용자입니다. 여기에 이름을 지정한 다음 같은 이름의 Snowflake 사용자를 만드십시오. <p>자세한 내용은 [Snowflake 설명서의 JDBC 드라이버 연결 매개 변수 참조 페이지](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **역할**] | 드라이버에서 시작한 Snowflake 세션에서 사용할 기본 액세스 제어 역할입니다. 이는 특히 Adobe 시 사용되는 역할입니다. 여기에 역할을 지정한 다음 Snowflake에서 동일한 이름의 역할을 만들고 읽기 및 쓰기 액세스 권한을 부여합니다.<p>자세한 내용은 [Snowflake 설명서의 JDBC 드라이버 연결 매개 변수 참조 페이지](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |

   {style="table-layout:auto"}

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

   다음 [!UICONTROL **내보내기 계정 생성됨**] 대화 상자가 표시됩니다.

   <!-- add screen shot -->

1. 의 내용을 복사합니다. [!UICONTROL **공개 키**] 필드를 클립보드에 추가합니다. 공개 키는 Adobe에서 제공합니다. Snowflake의 공개 키를 사용하여 Snowflake 계정에 연결합니다. 자세한 내용은 [Snowflake 설명서의 키 쌍 인증 및 키 쌍 회전 페이지](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

1. [!UICONTROL **닫기**]&#x200B;를 선택합니다.

1. 계속 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md).



