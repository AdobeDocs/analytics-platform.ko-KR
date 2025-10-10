---
title: Customer Journey Analytics에서 데이터를 분류하기 위한 조회 데이터 세트 만들기
description: Customer Journey Analytics에서 데이터를 분류하기 위한 조회 데이터 세트를 만드는 방법에 대해 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f5443ddd-81d0-43cc-99cb-215e7ddf5acf
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 100%

---

# Customer Journey Analytics에서 데이터를 분류하기 위한 조회 데이터 세트 만들기 {#upgrade-lookup-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-lookup-dataset-create"
>title="분류 데이터를 포함하는 각 차원에 대한 조회 데이터 세트 만들기"
>abstract="조회 데이터 세트는 Adobe Analytics의 분류 데이터와 유사하게 Customer Journey Analytics에서 데이터를 분류하는 방법입니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

조회 데이터 세트는 Adobe Analytics의 분류 데이터와 유사하게 Customer Journey Analytics에서 데이터를 분류하는 방법입니다.

Analytics 소스 커넥터를 사용하면 일부 표준 조회 데이터 세트가 보고 시점에 자동으로 적용됩니다. 자세한 내용은 [데이터 세트에 표준 조회 추가](/help/connections/standard-lookups.md)를 참조하십시오.

Customer Journey Analytics에서 Experience Platform Web SDK를 사용할 때 데이터를 분류하려면 분류하려는 데이터를 포함하는 각 차원에 대한 사용자 정의 스키마와 조회 데이터 세트를 만들어야 합니다.

## 조회 데이터 세트와 함께 사용할 사용자 정의 스키마 만들기

Customer Journey Analytics에서 분류하고자 하는 데이터를 포함하는 각 차원에 대한 새로운 사용자 정의 스키마를 생성합니다. 이후 단계에서 조회 데이터 세트를 생성하면 이 스키마를 참조할 것입니다.

분류하려는 데이터가 포함된 각 차원에 대해 이 과정을 반복합니다.

Customer Journey Analytics에서 조회 데이터 세트와 함께 사용할 스키마를 만드는 방법:

1. Adobe Experience Platform UI에서 왼쪽 레일의 **[!UICONTROL 데이터 관리]** 섹션에 있는 **[!UICONTROL 스키마]**&#x200B;를 선택합니다.

1. **[!UICONTROL 스키마 만들기]**&#x200B;를 선택합니다.

   ![스키마 만들기 버튼](assets/schema-create.png)

1. **[!UICONTROL 수동]**&#x200B;을 선택합니다. 이를 통해 스키마에 필드와 필드 그룹을 수동으로 추가할 수 있습니다. **[!UICONTROL 선택]**&#x200B;을 선택해 생성 마법사의 다음 페이지로 넘어갑니다.

1. **[!UICONTROL 스키마 세부 정보]** 페이지에서 **[!UICONTROL 기타]**&#x200B;를 선택한 다음 **[!UICONTROL 사용자 정의]**&#x200B;를 선택합니다.

   ![사용자 정의 만들기](assets/schema-custom.png)

1. **[!UICONTROL 클래스 만들기]**&#x200B;를 선택합니다.

   <!-- add screenshot -->

1. **[!UICONTROL 클래스 만들기]** 대화 상자에서 스키마의 이름과 설명을 지정하고, **[!UICONTROL 레코드]**&#x200B;를 선택한 다음 **[!UICONTROL 만들기]**&#x200B;를 선택합니다.

1. [조회 데이터 세트 만들기](#create-a-lookup-dataset)를 계속 진행합니다.

## 조회 데이터 세트 만들기

조회 데이터 세트에 사용할 [사용자 정의 스키마](#create-a-custom-schema-to-use-with-the-lookup-dataset)를 만든 후에는 조회 데이터 세트를 생성하여 스키마에 매핑해야 합니다.

분류하려는 데이터가 포함된 각 차원에 대해 이 과정을 반복합니다.

Customer Journey Analytics에서 스키마와 함께 사용할 조회 데이터 세트를 만드는 방법:

>[!NOTE]
>
>다음 프로세스에서는 CSV 파일을 사용하여 데이터 세트를 만듭니다. 데이터스트림 설정과 같은 다른 방법을 사용하여 Experience Platform으로 데이터를 가져올 수도 있습니다.

1. Adobe Experience Platform의 왼쪽 레일에서 **[!UICONTROL 워크플로]**&#x200B;를 선택합니다.

   ![사용자 정의 만들기](assets/lookup-dataset-workflows.png)

1. **[!UICONTROL CSV를 XDM 스키마에 매핑]**&#x200B;을 선택한 다음 **[!UICONTROL 실행]**&#x200B;을 선택합니다.

1. **[!UICONTROL 데이터 세트 세부 정보]** 섹션에서 **[!UICONTROL 새 데이터 세트]**&#x200B;를 선택합니다.

1. 데이터 세트의 이름과 설명을 지정합니다.

1. **[!UICONTROL 스키마]** 필드에서 [조회 데이터 세트에 대한 스키마 만들기](#create-a-schema-for-lookup-datasets)에 설명된 대로 조회 데이터 세트에 대해 만든 스키마를 선택합니다.

1. **[!UICONTROL 다음]**&#x200B;을 선택합니다.

1. **[!UICONTROL CSV를 XDM 스키마에 매핑]** 페이지의 **[!UICONTROL 파일 업로드]** 섹션에서 **[!UICONTROL 파일 선택]**&#x200B;을 선택한 다음 분류 데이터를 적용하려는 차원에 대한 분류 정보가 들어 있는 파일을 파일 시스템에서 찾습니다. 예를 들어 이것은 필드 ID와 해당 필드 이름을 나열하는 스프레드시트일 수 있습니다. <!-- correct? How can I better explain what this file is?-->

   ![CSV 파일 매핑](assets/lookup-map-csv.png)

1. **[!UICONTROL 다음]** 선택

1. 파일을 업로드한 후 매핑을 검토하여 정확한지 확인합니다. CSV 파일의 열은 **[!UICONTROL 소스 데이터]** 아래에 나열되어 있고, 해당 XDM 스키마 필드는 **[!UICONTROL 대상 필드]** 아래에 나열되어 있습니다.

   Platform은 사용자가 선택한 대상 스키마나 데이터 세트를 기반으로 자동 매핑된 필드에 대한 지능형 추천을 자동으로 제공합니다. 사용 사례에 맞게 매핑 규칙을 수동으로 조정할 수 있습니다.

   매핑 프로세스에 대한 자세한 내용은 Experience Platform 설명서의 [CSV 파일을 기존 XDM 스키마에 매핑](https://experienceleague.adobe.com/ko/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema)을 참조하십시오.

1. **[!UICONTROL 마침]**&#x200B;을 선택합니다.

1. [Customer Journey Analytics에서 연결에 조회 데이터 세트 추가](#add-the-lookup-dataset-to-your-connection-in-customer-journey-analytics)를 계속 진행합니다.

## Customer Journey Analytics에서 연결에 조회 데이터 세트 추가

[사용자 정의 스키마를 만들고](#create-a-custom-schema-to-use-with-the-lookup-dataset) [조회 데이터 세트를 만든](#create-a-lookup-dataset) 후 Customer Journey Analytics에서 연결에 조회 데이터 세트를 추가해야 합니다.

분류하려는 데이터가 포함된 각 차원에 대해 이 과정을 반복합니다.

Customer Journey Analytics에서 연결에 조회 데이터 세트를 추가하는 방법:

1. Customer Journey Analytics에서 상단 메뉴의 **[!UICONTROL 데이터 관리]**&#x200B;에서(선택 사항) **[!UICONTROL 연결]**&#x200B;을 선택합니다.

1. 조회 데이터 세트를 추가하려는 연결 옆에 있는 ![자세히 아이콘](assets/More.svg)을 선택한 다음 **[!UICONTROL 편집]**&#x200B;을 선택합니다.

   <!-- add screenshot -->

1. **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 세트 추가]** 대화 상자에서 생성한 조회 데이터 세트를 선택한 후 **[!UICONTROL 다음]**&#x200B;을 선택합니다.

1. **[!UICONTROL 개인 ID]** 필드에서 Experience Platform에서 구성한 데이터 세트 스키마에 정의된 사용 가능한 ID 중에서 개인 ID를 선택합니다. <!-- fill out other fields? -->

1. **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택한 다음 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

   <!-- is there a step right in between here where you select the dataset -->

1. **[!UICONTROL 키]** 필드와 **[!UICONTROL 일치하는 키]** 필드를 사용하여 조회 데이터 세트의 필드와 이벤트 또는 요약 데이터 세트의 필드 간의 상관 관계를 만듭니다.

1. 모든 조회 데이터 세트가 Customer Journey Analytics의 연결에 추가될 때까지 이 프로세스를 반복합니다.

{{upgrade-final-step}}

