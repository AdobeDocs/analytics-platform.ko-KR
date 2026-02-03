---
title: 결합 활성화
description: 연결 UI에서 결합을 활성화하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: cbb18e9d0990d5df64995c2dabe8362c7c37bb45
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 5%

---

# 결합 활성화

연결의 일부로 구성한 하나 이상의 이벤트 데이터 세트에 대한 결합을 활성화할 수 있습니다. 라이선스가 부여된 Customer Journey Analytics 패키지에 따라 결합에 사용할 수 있는 이벤트 데이터 세트의 수가 결정됩니다.

[연결을 만들거나](/help/connections/create-connection.md#dataset-settings) [연결을 편집](/help/connections/create-connection.md)할 때 이벤트 데이터 세트에 대한 [데이터 세트 설정](/help/connections/manage-connections.md#edit-a-connection)의 일부로 연결을 활성화합니다.

## 사전 요구 사항

지정한 연결 방법에 대한 필수 구성 요소를 확인하고 충족해야 합니다. [필드 기반 연결](fbs.md#prerequisites) 또는 [그래프 기반 연결](gbs.md#prerequisites).


## Preflight 확인

사전 요구 사항을 충족하는 경우 ID 결합을 활성화하기 전에 이벤트 데이터 세트의 데이터에 대해 일부 프리플라이트 검사를 수행할 수 있습니다.

* 영구 ID 또는 개인 ID에 XDM 스키마 필드를 사용하려는 경우 이벤트 데이터 세트에 대한 스키마에서 ID가 올바르게 표시되는지 확인하십시오. [ID 네임스페이스 개요](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/namespaces)를 참조하십시오.
* 영구 ID와 개인 ID 모두에 대한 ID 범위 확인:

   * **영구 ID**

     영구 ID 필드가 null이 아닌 7일 데이터를 쿼리하고 데이터 세트의 모든 이벤트에 대한 7일 데이터 쿼리로 나눕니다. 이 비율은 95% 이상이어야 합니다.

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


   * **개인 ID**
      * 그래프 기반 결합의 경우, ID 그래프가 선택한 영구 ID 네임스페이스 및 개인 ID 네임스페이스의 ID 값을 연결하는 조각을 포함하는지 확인하십시오. [Experience Platform ID 그래프 뷰어](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"}(으)로 이동하여 테스트를 실행하고 일부 테스트 영구 ID 값으로 그래프를 쿼리할 수 있습니다. 이러한 영구 ID 값이 그래프의 개인 ID 값에 연결되어 있는지 확인합니다.
      * 필드 기반 결합의 경우 개인 ID 필드가 null이 아닌 7일 데이터를 쿼리하고 데이터 세트의 모든 이벤트에 대한 7일 데이터 쿼리로 나눕니다. 이 비율은 이상적으로 5%를 초과해야 합니다.

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



## ID 결합 활성화 {#enable-identity-stitching}

>[!CONTEXTUALHELP]
>id="connection_changeto_identitygraph"
>title="ID 그래프로 변경"
>abstract="결합할 ID 그래프를 사용하기 전에 ID 그래프 설정을 완료했는지 확인하십시오."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs" text="그래프 기반 결합"

결합을 활성화하려면 **[!UICONTROL 데이터 세트 추가]** 또는 **[!UICONTROL 데이터 세트 편집]** 대화 상자의 이벤트 데이터 세트 섹션에서 다음을 수행합니다.

![ID 결합을 활성화할 때 ID 결합 옵션](assets/identity-stitching-ui.png)

1. **[!UICONTROL ID 연결 사용]**&#x200B;을 선택합니다.

   연결에 저장된 이벤트 데이터 세트에 대해 연결을 활성화하거나 비활성화하면 **[!UICONTROL 개인 ID 변경]** 대화 상자에 개인 ID 변경의 의미가 표시됩니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

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

   그 전에 결합을 위해 ID 그래프를 사용하기 전에 **[!UICONTROL 그래프 기반 필수 구성 요소]**&#x200B;의 일부로 데이터 집합에 대한 ID 그래프 설정을 완료했는지 확인하는 [ID 그래프에 대한 변경](/help/stitching/gbs.md#prerequisites) 대화 상자가 표시됩니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

   * **[!UICONTROL 네임스페이스]** 드롭다운 메뉴에서 네임스페이스를 선택합니다.


1. **[!UICONTROL 재생 창]** 드롭다운 메뉴에서 재생 창을 선택합니다. 사용 가능한 옵션은 권한이 부여된 Customer Journey Analytics 패키지에 따라 다릅니다.

연결을 저장하면 이러한 데이터 세트에 대한 데이터 수집이 시작될 때 결합 킥에 대해 활성화된 데이터 세트에 대한 결합 프로세스가 시작됩니다.

>[!CAUTION]
>
>연결 인터페이스에서 연결을 사용하도록 설정된 데이터 세트의 경우 완료된 다시 채우기 횟수에 대해 다시 채우기 상태가 즉시 ![녹색 상태](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _다시 채우기 완료됨]**(으)로 잘못 보고됩니다. 다른 방법을 사용하여 결합된 데이터 세트의 데이터가 채워졌는지 확인하십시오.
>


## 제한 사항

[필드 기반 결합 제한](/help/stitching/fbs.md#limitations) 및 [그래프 기반 결합 제한](/help/stitching/gbs.md#limitations) 외에 연결 인터페이스에서 결합을 활성화할 경우 다음 제한이 적용됩니다.

* 이벤트 데이터 세트는 단일 연결의 일부로 한 번만 연결할 수 있습니다. 동일한 이벤트 데이터 세트를 두 번 이상 정의하고 각 인스턴스에 대해 별도의 결합 구성을 사용할 수 없습니다. 동일한 데이터 세트에 다른 결합 구성을 적용하려면 각 구성에 대해 별도의 연결을 사용합니다.


## 마이그레이션

연결 인터페이스에서 활성화된 결합은 요청 기반 결합의 문제 없이 공존할 수 있습니다.

예를 들어 이전 또는 현재 결합 요청의 결과로 데이터 레이크에 웹 기반 결합 데이터 세트가 있는 경우. 연결 인터페이스를 사용하여 콜 센터 데이터 세트에서 결합된 데이터를 추가하여 해당 데이터를 웹 기반 데이터와 결합할 수 있습니다.

결국, Adobe은 요청 기반의 결합된 데이터 세트를 연결 경험의 새 결합으로 마이그레이션합니다.
