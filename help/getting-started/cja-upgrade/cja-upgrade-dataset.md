---
title: Customer Journey Analytics용 스키마 만들기
description: Adobe Analytics에서 Customer Journey Analytics로 업그레이드할 때 권장되는 경로 자세히 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
autotag-review: '2026-05-19T08:12:18.647Z'
TQID: 'https://experienceleague.adobe.com/ti9UiQzAa9wBCCH-44dmUxTzojuh5ZHu9YJ9HNC8OHI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 100%

---

# Customer Journey Analytics에 사용할 데이터 세트 만들기 {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="Adobe Experience Platform에 데이터 세트 만들기"
>abstract="데이터 세트는 수집된 데이터가 있는 위치입니다. Adobe Experience Platform에 이 위치를 만듭니다.<br><br>스키마를 염두에 두고 데이터 세트를 만들면 몇 분이면 충분합니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

데이터 세트는 Adobe Experience Platform에 수집한 데이터를 저장하고 관리하는 구성 요소입니다.

데이터 세트를 만드는 방법:

1. 왼쪽 레일의 Adobe Experience Platform에서 [!UICONTROL 데이터 관리]에 있는 **[!UICONTROL 데이터 세트]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 세트 만들기]**&#x200B;를 선택합니다.

   ![데이터 세트 만들기](assets/create-dataset.png)

1. **[!UICONTROL 스키마에서 데이터 세트 만들기]**&#x200B;를 선택합니다.

   ![스키마에서 데이터 세트 만들기](assets/create-dataset-from-schema.png)

1. 이전에 만든 스키마를 선택하고 **[!UICONTROL 다음]**&#x200B;을 선택합니다.

1. 데이터 세트의 이름을 지정하고 (선택 사항) 설명을 제공합니다.

   ![데이터 세트 이름 지정](assets/name-your-datatest.png)

1. **[!UICONTROL 마침]**&#x200B;을 선택합니다.

1. **[!UICONTROL 프로필]** 전환을 선택합니다.

   데이터 세트를 프로필용으로 활성화하라는 메시지가 표시됩니다. 활성화되면 데이터 세트는 수집된 데이터로 실시간 고객 프로필을 강화합니다.

   >[!IMPORTANT]
   >
   >    데이터 세트가 준수하는 스키마가 프로필용으로 활성화된 경우에만 데이터 세트를 프로필용으로 활성화할 수 있습니다.

   ![프로필용으로 스키마 활성화](assets/aepwebsdk-dataset-profile.png)

   데이터 세트를 보고, 미리 보고, 만들고, 삭제하는 방법에 대한 자세한 내용은 [데이터 세트 UI 가이드](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html)를 참조하십시오. 데이터 세트를 실시간 고객 프로필용으로 활성화하는 방법도 배울 수 있습니다.

{{upgrade-final-step}}
