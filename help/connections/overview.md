---
title: Customer Journey Analytics 연결 개요
description: Customer Journey Analytics에서 연결에 대해 알아보십시오.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 7a5fa07e3bafa3da5b044ce37299196a006f1d64
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---

# 연결 개요

연결을 통해 Customer Journey Analytics 제품 관리자는 이벤트, 조회 및 프로필 데이터 세트 등 다양한 [!DNL Adobe Experience Platform] 데이터 소스 간의 연결을 설정할 수 있습니다. 이러한 연결로 데이터를 연결에서 파생 데이터 보기로 통합할 수 있습니다. 연결은 CJA의 기반이며 [!DNL Experience Platform] 소스 데이터 세트에서 만들어집니다. 연결에 대한 액세스 권한을 사용하면 연결을 구성하는 기본 데이터 세트를 보고 중요한 편집 및 구성을 선택할 수 있는 연결 관리자를 볼 수 있습니다.

연결 관리에 대한 액세스 권한을 핵심 관리 그룹으로 제한하는 것이 좋습니다. 연결 수준의 구성에는 Customer Journey Analytics로 가져온 데이터의 볼륨 할당과 관련하여 계약상 의미가 포함됩니다.

다음은 비디오 개요입니다.

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## 필요 권한

Customer Journey Analytics 연결을 만들려면 [Adobe Admin Console](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html)에서 다음 권한이 필요합니다.

Adobe Experience Platform:

* 데이터 모델링: 스키마 보기, 스키마 관리
* 데이터 관리: 데이터 세트 보기, 데이터 세트 관리
* 데이터 수집: 소스 관리
* ID 네임스페이스 보기

Customer Journey Analytics

* 제품 관리자 액세스

>[!IMPORTANT]
>
>여러 [!DNL Experience Platform] 데이터 세트를 하나의 연결로 결합할 수 있습니다.
