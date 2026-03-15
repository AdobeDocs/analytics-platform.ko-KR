---
title: 결합 활성화
description: Customer Journey Analytics에서 이벤트 데이터 세트에 대한 ID 결합을 활성화합니다. 데이터를 연결하기 위해 연결 UI에서 영구 ID, 개인 ID 및 재생 창을 구성하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 1e0d028db957743416bc7840f5a3682206a3edf3
workflow-type: tm+mt
source-wordcount: '1808'
ht-degree: 9%

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

     여기서

      * `{PERSISTENT_ID_FIELD}`은(는) 영구 ID의 필드입니다. 예: `identityMap.ecid[0]`.
      * `{DATASET_TABLE_NAME}`은(는) 이벤트 데이터 세트의 테이블 이름입니다.
      * `{FORMAT_STRING}`은(는) 타임스탬프 필드의 형식 문자열입니다. 예: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE} `은(는) 시작 날짜입니다. 예: `2024-01-01 00:00:00`.
      * `{END_DATE}`은(는) 표준 형식의 종료 날짜입니다. 예: `2024-01-08 00:00:00`.


   * **개인 ID**
      * 그래프 기반 결합의 경우, ID 그래프가 선택한 영구 ID 네임스페이스 및 개인 ID 네임스페이스의 ID 값을 연결하는 조각을 포함하는지 확인하십시오. [Experience Platform ID 그래프 뷰어](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"}(으)로 이동하여 테스트를 실행하고 일부 샘플 영구 ID 값으로 그래프를 쿼리할 수 있습니다. 이러한 영구 ID 값이 그래프의 개인 ID 값에 연결되어 있는지 확인합니다.
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

        여기서

         * `{PERSON_ID_FIELD}`은(는) 개인 ID에 대한 필드입니다. 예: `identityMap.crmId[0]`.
         * `{DATASET_TABLE_NAME}`은(는) 이벤트 데이터 세트의 테이블 이름입니다.
         * `{FORMAT_STRING}`은(는) 타임스탬프 필드의 형식 문자열입니다. 예: `MM/DD/YY HH12:MI AM`.
         * `{START_DATE}`은(는) 시작 날짜입니다. 예: `2024-01-01 00:00:00`.
         * `{END_DATE}`은(는) 표준 형식의 종료 날짜입니다. 예: `2024-01-08 00:00:00`.



## ID 결합 활성화 {#enable-identity-stitching}

사용자 기반 연결에서 이벤트 데이터 세트를 [추가](/help/connections/create-connection.md#add-datasets) 또는 [편집](/help/connections/create-connection.md#edit-a-dataset)할 때 ID 결합을 활성화할 수 있습니다. 계정 기반 연결에는 ID 결합을 사용할 수 없습니다.

>[!CONTEXTUALHELP]
>id="connection_changeto_identitygraph"
>title="ID 그래프로 변경"
>abstract="결합할 ID 그래프를 사용하기 전에 ID 그래프 설정을 완료했는지 확인하십시오."
>additional-url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/stitching/gbs" text="그래프 기반 결합"

>[!CONTEXTUALHELP]
>id="connection_stitching_personid"
>title="개인 ID"
>abstract="사용 가능한 ID에서 개인 ID(개인에 대한 고유 식별자)를 선택합니다. 라이선스에 그래프 기반 연결이 포함되어 있고 이 연결 방법을 사용하려면 **[!UICONTROL ID 그래프]**&#x200B;를 선택하세요."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics"
>title="결합 지표"
>abstract="결합 지표는 지난 7일 내에 이벤트의 타임스탬프가 있는 샘플 데이터 세트를 사용하여 계산되고 있습니다.<br>이 샘플 데이터 집합은 일반적으로 **[!UICONTROL 미리 보기]** 테이블에 사용된 샘플 데이터와 다릅니다."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_gbs_personidcoverage"
>title="개인 ID 적용 범위"
>abstract="결합 프로세스(라이브 및 재생) 중에 식별에 사용되는 선택한 개인 ID의 범위.<br/>최상의 결합 결과를 얻으려면 (영구 ID, 개인 ID) 관계가 각 영구 ID의 ID 그래프에 있어야 합니다."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_fbs_personidcoverage"
>title="개인 ID 적용 범위"
>abstract="결합 프로세스(라이브 및 재생) 중에 식별에 사용되는 선택한 개인 ID의 범위.<br/>최상의 결합 결과를 얻으려면 각 영구 ID(장치 정보)에 대해 하나 이상의 이벤트에서 개인 ID(사용자 정보)를 보내야 합니다."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_persistentidcoverage"
>title="영구 ID 적용 범위"
>abstract="이 값은 개인 ID 값을 검색할 수 없는 경우 결합 프로세스(라이브 및 재생) 중에 식별에 사용됩니다. <br/>영구 ID와 개인 ID가 없는 이벤트는 데이터에서 삭제됩니다. 최상의 결합 결과를 얻으려면 모든 이벤트에 영구 ID가 있어야 합니다."


>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_badids"
>title="잘못된 ID"
>abstract="잘못된 ID는 보고 데이터에 심각한 영향을 주는 ID 값입니다."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/technotes/badids" text="잘못된 ID"


### 데이터 세트 설정

결합을 활성화하려면 **[!UICONTROL 데이터 세트 추가]** 또는 **[!UICONTROL 데이터 세트 편집]** 대화 상자의 이벤트 데이터 세트 **[!UICONTROL 데이터 세트 설정]** 섹션에서 다음을 수행하십시오.

![ID 결합을 활성화할 때 ID 결합 옵션](assets/identity-stitching-ui.png)

1. **[!UICONTROL ID 연결 사용]**&#x200B;을 선택합니다.

   연결에 저장된 이벤트 데이터 세트에 대해 연결을 활성화하거나 비활성화하면 **[!UICONTROL 개인 ID 변경]** 대화 상자에 개인 ID 변경의 의미가 표시됩니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

   **[!UICONTROL ID 연결 사용]** 대화 상자에는 ID 연결 결과가 요약되어 있습니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

1. **[!UICONTROL 영구 ID]** 드롭다운 메뉴에서 영구 ID를 선택합니다.

   영구 ID로 **[!UICONTROL ID 맵]**&#x200B;을(를) 선택하는 경우 네임스페이스 를 선택해야 합니다. 다음 두 가지 옵션이 있습니다.

   * 기본 ID 네임스페이스를 사용하려면 **[!UICONTROL 기본 ID 네임스페이스 사용]**&#x200B;을(를) 선택하십시오.
   * **[!UICONTROL 네임스페이스]** 드롭다운 메뉴에서 네임스페이스를 선택합니다.

1. **[!UICONTROL 개인 ID]** 드롭다운 메뉴에서 개인 ID를 선택합니다.

   개인 ID로 **[!UICONTROL ID 맵]**&#x200B;을(를) 선택하는 경우 네임스페이스를 선택해야 합니다. 다음 두 가지 옵션이 있습니다.

   * 기본 ID 네임스페이스를 사용하려면 **[!UICONTROL 기본 ID 네임스페이스 사용]**&#x200B;을(를) 선택하십시오.
   * **[!UICONTROL 네임스페이스]** 드롭다운 메뉴에서 네임스페이스를 선택합니다.


   개인 ID로 **[!UICONTROL ID 그래프]**&#x200B;을(를) 선택하는 경우([그래프 기반 결합](/help/stitching/gbs.md) 사용) 네임스페이스를 선택해야 합니다.

   >[!NOTE]
   >
   >ID 그래프를 사용할 권한이 있는지 확인합니다.
   >

   그 전에 데이터 집합에 대한 ID 그래프 설정을 완료했는지 확인하기 위해 **[!UICONTROL ID 그래프로 변경]** 대화 상자가 표시됩니다. ID 그래프를 사용하여 결합하기 전에 이 설정은 [그래프 기반 필수 구성 요소](/help/stitching/gbs.md#prerequisites)의 일부입니다. 계속하려면 **[!UICONTROL 계속]**&#x200B;을 선택하세요.

   * **[!UICONTROL 네임스페이스]** 드롭다운 메뉴에서 네임스페이스를 선택합니다.

1. **[!UICONTROL 재생 창]** 드롭다운 메뉴에서 재생 창을 선택합니다. 사용 가능한 옵션은 권한이 부여된 Customer Journey Analytics 패키지에 따라 다릅니다.

1. 결합할 이벤트 데이터 집합의 미리 보기를 보려면 **[!UICONTROL 다음]**&#x200B;을 선택하십시오.


### 데이터 세트 미리보기

>[!AVAILABILITY]
>
>이 섹션에 설명된 향상된 **[!UICONTROL 데이터 세트 미리 보기]** 인터페이스(**[!UICONTROL 결합 지표]** 및 **[!UICONTROL 잘못된 ID]** 포함)는 릴리스의 제한된 테스트 단계에 있으며 사용자 환경에서 아직 사용할 수 없습니다. 사용할 수 없는 경우 데이터 세트 미리 보기는 **[!UICONTROL 데이터 세트 설정]** 인터페이스의 일부로 표시됩니다. 기능이 일반적으로 제공되면 이 메모는 제거됩니다. Customer Journey Analytics 릴리스 프로세스에 대한 자세한 내용은 [Customer Journey Analytics 기능 릴리스](/help/release-notes/releases.md)를 참조하십시오.
>

표준 **[!UICONTROL 데이터 세트 미리 보기]** 인터페이스 위에, 사용자 기반 연결에서 [데이터 세트를 추가](/help/connections/create-connection.md#add-datasets)하거나 [편집](/help/connections/create-connection.md#edit-a-dataset)할 때 두 개의 추가 정보 패널을 사용할 수 있습니다.

>[!NOTE]
>AWS에 Customer Journey Analytics을 배포한 고객의 경우 이 기능은 릴리스 보류 중입니다.
>

![ID 결합을 활성화할 때 ID 결합 옵션](assets/identity-stitching-ui-preview.png)

#### 결합 지표

**[!UICONTROL 결합 지표]**&#x200B;은(는) 지난 7일 내에 이벤트 타임스탬프가 있는 샘플 데이터 집합을 사용하여 계산되고 있습니다. 이 샘플 데이터 집합은 일반적으로 **[!UICONTROL Preview]** 테이블에 사용된 샘플 데이터와 다릅니다. 결합 지표는 다음에 대한 세부 정보를 제공합니다.

* **[!UICONTROL 개인 ID 범위]**: 결합 프로세스(실시간 및 재생) 중에 식별에 사용되는 선택한 개인 ID의 범위입니다.
   * 최상의 필드 기반 결합 결과를 얻으려면 각 영구 ID(장치 정보)에 대해 하나 이상의 이벤트에서 개인 ID(사용자 정보)가 전송되어야 합니다.
   * 최상의 그래프 기반 결합 결과를 위해 (영구 ID, 개인 ID) 관계가 각 영구 ID의 ID 그래프에 존재해야 합니다.

  개인 ID 범위는 백분율로 표시되며, 안정적인 개발 또는 프로덕션 설정에서 권장되는 사항과 비교됩니다. 이 적용 범위 값이 높을수록 선택한 개인 ID로 더 나은 결합 결과를 얻을 수 있습니다.

* **[!UICONTROL 영구 ID 범위]**: 이 값은 개인 ID 값을 검색할 수 없는 경우 결합 프로세스(실시간 및 재생) 중에 식별에 사용됩니다. 영구 ID와 개인 ID가 없는 이벤트는 데이터에서 삭제됩니다. 최상의 결합 결과를 얻으려면 모든 이벤트에 영구 ID가 있어야 합니다.

  영구 ID 범위는 백분율로 표시되며, 안정적인 개발 또는 프로덕션 설정에서 권장되는 최소 사항과 비교됩니다.


#### 잘못된 ID

>[!INFO]
>
>잘못된 ID는 Customer Journey Analytics 인터페이스에서 BAVID라고도 합니다.
> 

Customer Journey Analytics에서 잘못된 ID는 식별자입니다.

* 연결을 사용할 수 있는 데이터 세트의 영구 ID 또는 개인 ID 필드에서 비롯된 특정 ID 값으로 **과(와)**
* 는 한 달 내에 연결 데이터의 백만 개 이상의 이벤트(100만 개)에 있습니다.

ID 값이 잘못된 ID로 표시되면 해당 ID 값이 포함된 이후 이벤트는 연결 데이터에서 삭제되고 보고에 표시되지 않습니다.

잘못된 ID 사용 사례의 예:

* 개인 ID 필드에 사용자 지정 또는 자리 표시자 값이 있습니다(예: `undefined`). 이러한 값은 [결합 및 보고 데이터 품질](/help/stitching/faq.md#undefined-person-id-values)에도 영향을 줄 수 있습니다.
* 필드 기반 결합 구성에서 여러 사람이 장치를 공유하고 사용자 간 총 전환 수가 50,000개를 초과하는 경우. 이 시나리오에서는 결합 프로세스가 중지되어 해당 디바이스에 대한 개인 ID 정보가 사용되고 대신 영구 ID 정보만 사용됩니다. 따라서 해당 장치의 모든 데이터 세트 이벤트가 영구 ID ID를 가진 연결 데이터로 전송되어 잘못된 ID 상황이 발생할 가능성이 높습니다.


>[!NOTE]
>**[!UICONTROL 잘못된 ID]**&#x200B;을(를) 포함한 **[!UICONTROL 결합 지표]**&#x200B;은(는) 제한된 데이터 집합을 기반으로 계산됩니다. 결합에 사용할 데이터 세트에 대해 잘못된 ID가 있는지 식별하려면 [잘못된 ID 기술 정보](/help/technotes/badids.md)를 참조하세요.
>


### 저장

연결을 저장하면 이러한 데이터 세트에 대한 데이터 수집이 시작되는 즉시 활성화된 데이터 세트를 결합하기 위한 결합 프로세스가 시작됩니다.

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
