---
title: 스티칭 사용
description: 결합 사용 방법
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
badgePremium: label="Beta" type="Informative"
source-git-commit: 23b890ec6a3266d1ca0621b09264f1d6a2f82645
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 3%

---

# 스티칭 사용

연결의 일부로 구성한 하나 이상의 이벤트 데이터 세트에 대한 결합을 활성화할 수 있습니다. 라이선스가 부여된 Customer Journey Analytics 패키지에 따라 결합에 사용할 수 있는 이벤트 데이터 세트의 수가 결정됩니다.

{{release-limited-testing}}

[연결을 만들거나](/help/connections/create-connection.md#dataset-settings) [연결을 편집](/help/connections/create-connection.md)할 때 이벤트 데이터 세트에 대한 [데이터 세트 설정](/help/connections/manage-connections.md#edit-a-connection)의 일부로 연결을 활성화할 수 있습니다.

## 사전 요구 사항

연결 UI 내에서 이벤트 데이터 세트에 대한 연결을 활성화하려면 다음을 수행하십시오.

* 데이터 세트가 기반으로 삼는 스키마에는 다음이 있어야 합니다.

   * id로 구성되고 영구 ID 및 개인 ID에 대해 서로 다른 값을 선택할 수 있는 여러 필드.
   * 영구 ID 또는 개인 ID에 ID 맵 및 기본 ID 네임스페이스를 사용하려는 경우 연결된 네임스페이스와 함께 기본 ID로 표시되는 하나 이상의 필드.

* ID 그래프 및 그래프 기반 결합을 사용하려면 이벤트 데이터 세트가 ID 서비스에 대해 [활성화되어야 합니다](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).


## Preflight 확인

사전 요구 사항을 충족하는 경우 ID 결합을 활성화하기 전에 이벤트 데이터 세트의 데이터에 대해 일부 프리플라이트 검사를 수행할 수 있습니다.

* 이벤트 데이터 세트에 대한 스키마에서 ID가 올바르게 표시되는지 확인합니다. [ID 네임스페이스 개요](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/namespaces)를 참조하십시오.
* 영구 ID와 개인 ID 모두에 대한 ID 범위 확인:
   * 영구 ID: 영구 ID 필드가 null이 아닌 7일 데이터를 쿼리하고 데이터 세트의 모든 이벤트에 대한 7일 데이터 쿼리로 나눕니다. 이 비율은 95% 이상이어야 합니다.

     확인에 사용할 수 있는 쿼리의 예:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
       ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     위치:

      * `{PERSISTENT_ID_FIELD}`은(는) 영구 ID의 필드입니다. 예: `identityMap.ecid[0]`.
      * `{DATASET_TABLE_NAME}`은(는) 이벤트 데이터 세트의 테이블 이름입니다.
      * `{FORMAT_STRING}`은(는) 타임스탬프 필드의 형식 문자열입니다. 예: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE} `은(는) 시작 날짜입니다. 예: `2024-01-01 00:00:00`.
      * `{END_DATE}`은(는) 표준 형식의 종료 날짜입니다. 예: `2024-01-08 00:00:00`.


   * 개인 ID - 개인 ID 필드가 null이 아닌 7일 데이터를 쿼리하고 데이터 세트의 모든 이벤트에 대한 7일 데이터 쿼리로 나눕니다. 이 비율은 5% 이상이어야 합니다.

     확인에 사용할 수 있는 쿼리의 예:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSON_ID_FIELD}) AS events_with_personid,
       ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     위치:

      * `{PERSON_ID_FIELD}`은(는) 개인 ID에 대한 필드입니다. 예: `identityMap.crmId[0]`.
      * `{DATASET_TABLE_NAME}`은(는) 이벤트 데이터 세트의 테이블 이름입니다.
      * `{FORMAT_STRING}`은(는) 타임스탬프 필드의 형식 문자열입니다. 예: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE}`은(는) 시작 날짜입니다. 예: `2024-01-01 00:00:00`.
      * `{END_DATE}`은(는) 표준 형식의 종료 날짜입니다. 예: `2024-01-08 00:00:00`.



## ID 결합 활성화

>[!NOTE]
>
>연결 인터페이스에서 **[!UICONTROL ID 연결 활성화]**&#x200B;를 사용할 수 없는 경우 [요청 프로시저를 사용하여 데이터 집합에 연결을 활성화](/help/stitching/use-stitching.md)하십시오.



결합을 활성화하려면 **[!UICONTROL 데이터 세트 추가]** 또는 **[!UICONTROL 데이터 세트 편집]** 대화 상자의 이벤트 데이터 세트 섹션에서 다음을 수행합니다.

![ID 결합을 활성화할 때 ID 결합 옵션](assets/identity-stitching-ui.png)

1. **[!UICONTROL ID 연결 사용]**&#x200B;을 선택합니다.

   기존 이벤트 데이터 세트에 대해 연결을 활성화하면 **[!UICONTROL 개인 ID 변경]** 대화 상자에 연결 사용으로 인한 개인 ID 변경의 의미가 표시됩니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

   **[!UICONTROL ID 연결 사용]** 대화 상자에는 ID 연결 결과가 요약되어 있습니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

1. **[!UICONTROL 영구 ID]** 드롭다운 메뉴에서 영구 ID를 선택합니다.

   영구 ID로 **[!UICONTROL ID 맵]**&#x200B;을(를) 선택하는 경우 네임스페이스 를 선택해야 합니다. 다음 두 가지 옵션이 있습니다.

   * 기본 ID 네임스페이스를 사용하려면 **[!UICONTROL 기본 ID 네임스페이스를 사용]**&#x200B;하세요.
   * **[!UICONTROL 네임스페이스]** 드롭다운 메뉴에서 네임스페이스를 선택합니다.

1. **[!UICONTROL 개인 ID]** 드롭다운 메뉴에서 개인 ID를 선택합니다.

   개인 ID로 **[!UICONTROL ID 맵]**&#x200B;을(를) 선택하는 경우 네임스페이스를 선택해야 합니다. 다음 두 가지 옵션이 있습니다.

   * 기본 ID 네임스페이스를 사용하려면 **[!UICONTROL 기본 ID 네임스페이스를 사용]**&#x200B;하세요.
   * **[!UICONTROL 네임스페이스]** 드롭다운 메뉴에서 네임스페이스를 선택합니다.


   개인 ID로 **[!UICONTROL ID 그래프]**&#x200B;을(를) 선택하는 경우([그래프 기반 결합](/help/stitching/gbs.md) 사용) 네임스페이스를 선택해야 합니다.

   >[!NOTE]
   >
   >ID 그래프를 사용할 권한이 있는지 확인합니다.
   >

   그 전에 **[!UICONTROL ID 그래프로 변경]** 대화 상자가 표시되어 데이터 집합에 대한 ID 그래프 설정을 [마쳤는지 확인](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)한 후에 결합을 위해 ID 그래프를 사용합니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

   * **[!UICONTROL 네임스페이스]** 드롭다운 메뉴에서 네임스페이스를 선택합니다.


1. **[!UICONTROL 전환 확인 기간]** 드롭다운 메뉴에서 전환 확인 기간을 선택합니다. 사용 가능한 옵션은 권한이 부여된 Customer Journey Analytics 패키지에 따라 다릅니다.

ID 결합을 위해 활성화된 데이터 세트가 포함된 연결을 저장하면 각 데이터 세트에 대한 데이터 수집이 시작될 때 각 데이터 세트에 대한 결합 프로세스가 시작됩니다.

## 제한 사항

[필드 기반 결합 제한](/help/stitching/fbs.md#limitations) 및 [그래프 기반 결합 제한](/help/stitching/gbs.md#limitations) 외에 연결 인터페이스에서 결합을 활성화할 경우 다음 제한이 적용됩니다.

* 이벤트 데이터 세트는 단일 연결의 일부로 한 번만 연결할 수 있습니다. 동일한 이벤트 데이터 세트를 두 번 이상 정의하고 각 인스턴스에 대해 별도의 결합 구성을 사용할 수 없습니다. 동일한 데이터 세트에 다른 결합 구성을 적용하려면 각 구성에 대해 별도의 연결을 사용합니다.

