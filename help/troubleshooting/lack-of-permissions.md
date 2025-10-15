---
title: 권한 부족
description: 권한 부족으로 인해 발생하는 문제를 해결하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 100%

---

# 권한 부족

Customer Journey Analytics는 특정 Adobe Experience Platform 권한이 없으면 제대로 작동하지 않습니다.

예를 들어, [연결](../connections/overview.md) 및 [데이터 보기](../data-views/data-views.md)를 생성한 후에 [구성 요소](/help/data-views/create-dataview.md#components) 섹션에 다음과 같은 오류 메시지가 표시될 수 있습니다.


>[!BEGINSHADEBOX]

*[!UICONTROL DULE 정책을 가져오는 도중 문제가 발생했습니다. 계정 권한, 정책 또는 레이블을 확인해 주십시오. 메시지: 금지됨]*

>[!ENDSHADEBOX]


1. 올바른 액세스 제어가 있는지 확인하십시오.

   * Experience Platform 제품을 보유한 조직에 대한 시스템 또는 제품 관리자 권한이 있어야 합니다. 자세한 내용은 [액세스 제어 개요](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions)를 참조하십시오.

   * AEP-Default-All-Users 제품 프로필의 사용자여야 합니다. 이 프로필에 자신을 추가할 권한이 없는 경우 관리자에게 문의하십시오. 자세한 내용은 [액세스 제어 계층 구조 및 워크플로](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow)를 참조하십시오.


1. Adobe Experience Platform UI로 이동합니다.

1. 왼쪽 레일에서 **[!UICONTROL 권한]**&#x200B;을 선택합니다.

1. **[!UICONTROL 역할]**&#x200B;을 선택합니다.

1. 관련 역할로 이동합니다.

1. 역할을 편집하려면 ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 편집]**&#x200B;을 선택합니다.

1. **[!UICONTROL 데이터 거버넌스]**&#x200B;에 **[!UICONTROL 데이터 사용 정책 관리]** 및 **[!UICONTROL 데이터 사용 정책 조회]**&#x200B;가 추가되었는지 확인합니다.

1. 변경 내용을 저장하려면 **[!UICONTROL 저장]**&#x200B;을 선택합니다.
