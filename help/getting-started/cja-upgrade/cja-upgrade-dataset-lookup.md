---
title: Customer Journey Analytics에서 데이터를 분류하기 위한 조회 데이터 세트 만들기
description: 조회 데이터 세트를 만들어 Customer Journey Analytics에서 데이터를 분류하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f5443ddd-81d0-43cc-99cb-215e7ddf5acf
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 10%

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

Analytics 소스 커넥터를 사용하는 경우 일부 표준 조회 데이터 세트가 보고서 시간에 자동으로 적용됩니다. 자세한 내용은 [데이터 세트에 표준 조회 추가](/help/connections/standard-lookups.md)를 참조하십시오.

Experience Platform Web SDK을 사용할 때 Customer Journey Analytics에서 데이터를 분류하려면 분류할 데이터가 포함된 각 차원에 대한 사용자 지정 스키마 및 조회 데이터 세트를 만들어야 합니다.

## 조회 데이터 세트에 사용할 사용자 지정 스키마 만들기

Customer Journey Analytics에서 분류할 데이터가 포함된 각 차원에 대해 새 사용자 지정 스키마를 만듭니다. 이후 단계에서 조회 데이터 세트를 만들면 이 스키마를 참조합니다.

분류할 데이터가 포함된 각 차원에 대해 이 프로세스를 반복합니다.

Customer Journey Analytics에서 조회 데이터 세트와 함께 사용할 스키마를 만들려면:

1. Adobe Experience Platform의 왼쪽 레일의 **[!UICONTROL 데이터 관리]** 섹션에서 **[!UICONTROL 스키마]**&#x200B;를 선택합니다.

1. **[!UICONTROL 스키마 만들기]**&#x200B;를 선택합니다.

   ![스키마 만들기 단추](assets/schema-create.png)

1. **[!UICONTROL 수동]**&#x200B;을 선택하세요. 이를 통해 스키마에 필드 및 필드 그룹을 수동으로 추가할 수 있습니다. 만들기 마법사의 다음 페이지로 진행하려면 **[!UICONTROL 선택]**&#x200B;을 선택하십시오.

1. **[!UICONTROL 스키마 세부 정보]** 페이지에서 **[!UICONTROL 기타]**&#x200B;를 선택한 다음 **[!UICONTROL 사용자 지정]**&#x200B;을 선택합니다.

   ![사용자 지정 만들기](assets/schema-custom.png)

1. **[!UICONTROL 클래스 만들기]**&#x200B;를 선택합니다.

   <!-- add screenshot -->

1. **[!UICONTROL 클래스 만들기]** 대화 상자에서 스키마의 이름과 설명을 지정하고 **[!UICONTROL 레코드]**&#x200B;을 선택한 다음 **[!UICONTROL 만들기]**&#x200B;를 선택합니다.

1. [조회 데이터 세트 만들기](#create-a-lookup-dataset)를 계속합니다.

## 조회 데이터 세트 만들기

조회 데이터 세트에 사용할 [사용자 지정 스키마를 만들기](#create-a-custom-schema-to-use-with-the-lookup-dataset)한 후에는 조회 데이터 세트를 만들고 이를 스키마에 매핑해야 합니다.

분류할 데이터가 포함된 각 차원에 대해 이 프로세스를 반복합니다.

Customer Journey Analytics의 스키마와 함께 사용할 조회 데이터 세트를 만들려면 다음 작업을 수행하십시오.

>[!NOTE]
>
>다음 프로세스는 CSV 파일을 사용하여 데이터 세트를 만듭니다. 데이터 스트림 설정과 같이 데이터를 Experience Platform으로 가져오는 데 사용할 수 있는 다른 방법을 사용할 수도 있습니다.

1. Adobe Experience Platform의 왼쪽 레일에서 **[!UICONTROL 워크플로]**&#x200B;를 선택합니다.

   ![사용자 지정 만들기](assets/lookup-dataset-workflows.png)

1. **[!UICONTROL XDM 스키마에 CSV 매핑]**&#x200B;을 선택한 다음 **[!UICONTROL 시작]**&#x200B;을 선택합니다.

1. **[!UICONTROL 데이터 집합 세부 정보]** 섹션에서 **[!UICONTROL 새 데이터 집합]**&#x200B;을 선택합니다.

1. 데이터 세트의 이름과 설명을 지정합니다.

1. [조회 데이터 세트에 대한 스키마 만들기](#create-a-schema-for-lookup-datasets)에 설명된 대로 **[!UICONTROL 스키마]** 필드에서 조회 데이터 세트에 대해 만든 스키마를 선택합니다.

1. **[!UICONTROL 다음]**&#x200B;을 선택합니다.

1. **[!UICONTROL XDM 스키마에 CSV 매핑]**&#x200B;의 **[!UICONTROL 파일 업로드]** 섹션에서 **[!UICONTROL 파일 선택]**&#x200B;을 선택한 다음 파일 시스템에서 분류 데이터를 적용할 차원의 분류 정보가 포함된 파일을 찾습니다. 예를 들어 필드 ID와 해당 필드 이름을 나열하는 스프레드시트일 수 있습니다. <!-- correct? How can I better explain what this file is?-->

   ![CSV 파일 매핑](assets/lookup-map-csv.png)

1. **[!UICONTROL 다음]** 선택

1. 파일이 업로드된 후 매핑을 검토하여 정확한지 확인합니다. CSV 파일의 열은 **[!UICONTROL Source 데이터]**&#x200B;에 나열되고 해당 XDM 스키마 필드는 **[!UICONTROL 대상 필드]**&#x200B;에 나열됩니다.

   Platform은 사용자가 선택한 대상 스키마 또는 데이터 세트를 기반으로 자동 매핑된 필드에 대한 지능형 권장 사항을 자동으로 제공합니다. 사용 사례에 맞게 매핑 규칙을 수동으로 조정할 수 있습니다.

   매핑 프로세스에 대한 자세한 내용은 Experience Platform 설명서의 [기존 XDM 스키마에 CSV 파일 매핑](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema)을 참조하십시오.

1. **[!UICONTROL 마침]**&#x200B;을 선택합니다.

1. [Customer Journey Analytics의 연결에 조회 데이터 세트를 추가](#add-the-lookup-dataset-to-your-connection-in-customer-journey-analytics)하여 계속합니다.

## Customer Journey Analytics에서 연결에 조회 데이터 세트 추가

[사용자 지정 스키마를 만들고](#create-a-custom-schema-to-use-with-the-lookup-dataset) [조회 데이터 세트를 만들고](#create-a-lookup-dataset)한 후에는 Customer Journey Analytics의 연결에 조회 데이터 세트를 추가해야 합니다.

분류할 데이터가 포함된 각 차원에 대해 이 프로세스를 반복합니다.

Customer Journey Analytics에서 연결에 조회 데이터 세트를 추가하려면 다음을 수행하십시오.

1. Customer Journey Analytics에서 **[!UICONTROL 연결]** 탭을 선택합니다.

1. 조회 데이터 세트를 추가할 연결 옆에 있는 ![기타 아이콘](assets/More.svg)을 선택한 다음 **[!UICONTROL 편집]**&#x200B;을 선택합니다.

   <!-- add screenshot -->

1. **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 세트 추가]** 대화 상자에서 생성한 조회 데이터 세트를 선택한 후 **[!UICONTROL 다음]**&#x200B;을 선택합니다.

1. **[!UICONTROL 개인 ID]** 필드의 Experience Platform에서 구성한 데이터 세트 스키마에 정의된 사용 가능한 ID에서 개인 ID를 선택합니다. <!-- fill out other fields? -->

1. **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택한 다음 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

   <!-- is there a step right in between here where you select the dataset -->

1. **[!UICONTROL 키]** 필드와 **[!UICONTROL 일치하는 키]** 필드를 사용하여 조회 데이터 세트의 필드와 이벤트 또는 요약 데이터 세트의 필드 간의 상관 관계를 만듭니다.

1. 모든 조회 데이터 세트가 Customer Journey Analytics의 연결에 추가될 때까지 이 프로세스를 반복합니다.

{{upgrade-final-step}}

