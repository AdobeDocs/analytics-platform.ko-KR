---
title: 권한 부족
description: 권한 부족으로 인한 문제를 해결하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# 권한 부족

특정 Adobe Experience Platform 권한이 없는 경우 Customer Journey Analytics이 제대로 작동하지 않습니다.

예를 들어 를 만든 후 [연결](../connections/overview.md) 및 [데이터 보기](../data-views/data-views.md)에 다음 오류 메시지가 표시될 수 있습니다. [구성 요소](/help/data-views/create-dataview.md#components) 섹션:


>[!BEGINSHADEBOX]

*[!UICONTROL DULE 정책을 검색하는 도중 문제가 발생했습니다. 계정 권한, 정책 또는 레이블을 확인하십시오. 메시지: 사용할 수 없음.]*

>[!ENDSHADEBOX]


1. 올바른 액세스 제어 권한이 있는지 확인합니다.

   * Experience Platform 제품이 있는 조직에 대해 시스템 또는 제품 관리자 권한이 있어야 합니다. 다음을 참조하십시오 [액세스 제어 개요](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions) 추가 정보.

   * AEP-Default-All-Users 제품 프로필의 사용자여야 합니다. 이 프로필에 자신을 추가할 수 있는 권한이 없는 경우 관리자에게 문의하십시오. 다음을 참조하십시오 [액세스 제어 계층 및 워크플로](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow) 추가 정보.


1. Adobe Experience Platform UI로 이동합니다.

1. 선택 **[!UICONTROL 권한]** 왼쪽 레일에서.

1. 선택 **[!UICONTROL 역할]**.

1. 관련 역할로 이동합니다.

1. 선택 ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 편집]** 을 눌러 역할을 편집합니다.

1. 확인 **[!UICONTROL 데이터 사용 정책 관리]** 및 **[!UICONTROL 데이터 사용 정책 보기]** 에 추가됩니다. **[!UICONTROL 데이터 거버넌스]** 컨테이너.

1. 선택 **[!UICONTROL 저장]** 변경 내용을 저장합니다.
