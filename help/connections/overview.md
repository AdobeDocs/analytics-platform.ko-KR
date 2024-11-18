---
title: Customer Journey Analytics 연결 개요
description: Customer Journey Analytics에서 연결에 대해 알아보십시오.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 2f78905c2a1e94174a52269becc15474baf59f71
workflow-type: ht
source-wordcount: '224'
ht-degree: 100%

---

# 연결 개요

연결을 통해 Customer Journey Analytics 제품 관리자는 이벤트, 조회 및 프로필 데이터 세트 등 다양한 [!DNL Adobe Experience Platform] 데이터 소스 간의 연결을 설정할 수 있습니다. 이러한 연결로 데이터를 연결에서 파생 데이터 보기로 통합할 수 있습니다. 연결은 CJA의 기반이며 [!DNL Experience Platform] 소스 데이터 세트에서 만들어집니다. 연결에 대한 액세스 권한을 사용하면 연결을 구성하는 기본 데이터 세트를 보고 중요한 편집 및 구성을 선택할 수 있는 연결 관리자를 볼 수 있습니다.

연결 관리에 대한 액세스 권한을 핵심 관리 그룹으로 제한하는 것이 좋습니다. 연결 수준의 구성에는 Customer Journey Analytics로 가져온 데이터의 볼륨 할당과 관련하여 계약상 의미가 포함됩니다.

다음은 비디오 개요입니다.

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## 필요 권한

Customer Journey Analytics 연결을 만들려면 다음 권한이 필요합니다. 권한에 대한 자세한 내용은 [Adobe Admin Console](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) 및 [Adobe Experience Platform 권한](https://experienceleague.adobe.com/ko/docs/experience-platform/access-control/home)에 대한 설명서를 참조하십시오.

### Adobe Admin Console 내에서:

* Customer Journey Analytics: 제품 관리자
* Adobe Experience Platform: *AEP-Default-All-Users*&#x200B;라는 이름의 제품 프로필에 추가됨

### Adobe Experience Platform 권한 내에서:

* 데이터 모델링: 스키마 보기, 스키마 관리
* 데이터 관리: 데이터 세트 보기, 데이터 세트 관리
* 데이터 수집: 소스 관리
* Identity Management: ID 네임스페이스 보기
* 샌드박스: Customer Journey Analytics 연결에 사용되는 샌드박스

>[!IMPORTANT]
>
>여러 [!DNL Experience Platform] 데이터 세트를 하나의 연결로 결합할 수 있습니다.
