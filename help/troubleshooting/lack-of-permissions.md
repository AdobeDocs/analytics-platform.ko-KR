---
title: 권한 부족
description: 권한 부족으로 인한 문제를 해결하는 방법 알아보기
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
source-git-commit: 84a1cd485110be23b1977d916fc39e058b370066
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---


# 권한 부족

특정 Adobe Experience Platform 권한이 없는 경우 Customer Journey Analytics이 제대로 작동하지 않습니다.

예를 들어 를 만든 후 [연결](../connections/overview.md) 및 [데이터 보기](../data-views/data-views.md)에 다음 오류 메시지가 표시될 수 있습니다. [구성 요소](/help/data-views/create-dataview.md#components) 섹션:


>[!BEGINSHADEBOX]

*[!UICONTROL 문제가 발생하여 스키마 필드를 로드할 수 없습니다. 다시 시도하십시오.]*

>[!ENDSHADEBOX]


이 오류를 수정하려면 Experience Platform 제품이 있는 조직에 대한 시스템 또는 제품 관리자 권한이 있어야 합니다. 다음을 참조하십시오 [액세스 제어 개요](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) 추가 정보.

1. Adobe Experience Platform UI로 이동합니다.

1. 선택 **[!UICONTROL 권한]** 왼쪽 레일에서.

1. 선택 **[!UICONTROL 역할]**.

1. 관련 역할로 이동합니다.

1. 선택 ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 편집]** 을 눌러 역할을 편집합니다.

1. 확인 **[!UICONTROL 데이터 사용 정책 관리]** 및 **[!UICONTROL 데이터 사용 정책 보기]** 에 추가됩니다. **[!UICONTROL 데이터 거버넌스]** 컨테이너.

1. 선택 **[!UICONTROL 저장]** 변경 내용을 저장합니다.


